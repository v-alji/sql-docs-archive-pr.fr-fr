---
title: Sauvegarder et restaurer des applications de service Reporting Services SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: dfb4ed77-90e5-4273-b690-89a945508ed2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 488659d269542381be9bcf1b1b6115acf89f8a98
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605264"
---
# <a name="backup-and-restore-reporting-services-sharepoint-service-applications"></a><span data-ttu-id="605ac-102">Applications de service SharePoint de sauvegarde et de restauration Reporting Services</span><span class="sxs-lookup"><span data-stu-id="605ac-102">Backup and Restore Reporting Services SharePoint Service Applications</span></span>
  <span data-ttu-id="605ac-103">Cette rubrique explique comment sauvegarder et restaurer une application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] à l'aide de l'Administration centrale de SharePoint ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="605ac-103">This topic describes how to backup and restore a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services application using SharePoint Central Administration or PowerShell.</span></span> <span data-ttu-id="605ac-104">La rubrique contient :</span><span class="sxs-lookup"><span data-stu-id="605ac-104">The topic contains:</span></span>  
  
-   [<span data-ttu-id="605ac-105">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="605ac-105">Limitations and Restrictions</span></span>](#bkmk_Restrictions)  
  
-   [<span data-ttu-id="605ac-106">Sauvegarder l’application de service</span><span class="sxs-lookup"><span data-stu-id="605ac-106">Backup The Service application</span></span>](#bkmk_backup)  
  
-   [<span data-ttu-id="605ac-107">Restaurer l'application de service</span><span class="sxs-lookup"><span data-stu-id="605ac-107">Restore the Service Application</span></span>](#bkmk_restore)  
  
##  <a name="before-you-begin"></a><a name="bkmk_BeforeYouBegin"></a> <span data-ttu-id="605ac-108">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="605ac-108">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="bkmk_Restrictions"></a> <span data-ttu-id="605ac-109">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="605ac-109">Limitations and Restrictions</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="605ac-110">Les applications de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] peuvent être partiellement sauvegardées et restaurées à l’aide de la fonctionnalité SharePoint de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="605ac-110">[!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service applications can partially be backed up and restored using the SharePoint backup and restore functionality.</span></span> <span data-ttu-id="605ac-111">**Des étapes supplémentaires sont nécessaires** ; celles-ci sont documentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="605ac-111">**Additional steps are required** and the steps are documented in this topic.</span></span> <span data-ttu-id="605ac-112">Actuellement, le processus de sauvegarde **ne permet pas** de sauvegarder les clés de chiffrement et les informations d’identification pour les comptes d’exécution sans assistance (UEA) ou l’authentification Windows à la base de données [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="605ac-112">Currently the backup process **does not** backup encryption keys and credentials for unattended execution accounts (UEA) or windows authentication to the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] database.</span></span>  
  
###  <a name="recommendations"></a><a name="bkmk_recommendations"></a> <span data-ttu-id="605ac-113">Recommandations</span><span class="sxs-lookup"><span data-stu-id="605ac-113">Recommendations</span></span>  
  
-   <span data-ttu-id="605ac-114">Sauvegardez les clés de chiffrement avant de démarrer la sauvegarde SharePoint.</span><span class="sxs-lookup"><span data-stu-id="605ac-114">Backup the encryption keys before starting the SharePoint backup.</span></span> <span data-ttu-id="605ac-115">Si vous ne sauvegardez pas les clés de chiffrement, vous ne pourrez pas accéder à vos données chiffrées après la restauration de l'application de service.</span><span class="sxs-lookup"><span data-stu-id="605ac-115">If you do not backup the encryption keys, then you will not be able to access your encrypted data, following the restore of the service application.</span></span> <span data-ttu-id="605ac-116">Vous devrez alors les supprimer.</span><span class="sxs-lookup"><span data-stu-id="605ac-116">You will need to delete your encrypted data.</span></span>  
  
-   <span data-ttu-id="605ac-117">Vérifiez si votre application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] utilise un compte UEA ou l'authentification Windows pour l'accès aux bases de données.</span><span class="sxs-lookup"><span data-stu-id="605ac-117">Verify if your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application is using UEA or Windows authentication for database access.</span></span> <span data-ttu-id="605ac-118">Si elle utilise l'un ou l'autre, vérifiez quelles sont les informations d'identification appropriées pour que vous puissiez correctement configurer l'application de service après le processus de restauration.</span><span class="sxs-lookup"><span data-stu-id="605ac-118">If it is using either, verify what the proper credentials are so you can correctly configure the service application after the restore process.</span></span>  
  
-   <span data-ttu-id="605ac-119">Vérifiez que le journal de sauvegarde SharePoint est créé dans le même dossier que le fichier de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="605ac-119">Review the SharePoint backup log is created in the same folder as the backup file.</span></span> <span data-ttu-id="605ac-120">Le fichier est généralement nommé **spbackup.log**.</span><span class="sxs-lookup"><span data-stu-id="605ac-120">The file is typically named **spbackup.log**</span></span>  
  
##  <a name="backup-the-service-application"></a><a name="bkmk_backup"></a><span data-ttu-id="605ac-121">Sauvegarder l’application de service</span><span class="sxs-lookup"><span data-stu-id="605ac-121">Backup The Service application</span></span>  
 <span data-ttu-id="605ac-122">Exécutez les étapes suivantes dans l'ordre :</span><span class="sxs-lookup"><span data-stu-id="605ac-122">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="605ac-123">Sauvegarder les clés de chiffrement</span><span class="sxs-lookup"><span data-stu-id="605ac-123">Backup the encryption keys</span></span>  
  
2.  <span data-ttu-id="605ac-124">Sauvegarder l'application de service</span><span class="sxs-lookup"><span data-stu-id="605ac-124">Backup the Service application</span></span>  
  
3.  <span data-ttu-id="605ac-125">Vérifiez si votre application de service utilise un compte UEA ou l'authentification Windows pour l'accès aux bases de données.</span><span class="sxs-lookup"><span data-stu-id="605ac-125">Verify if you service application uses an UEA or Windows authentication for database access.</span></span> <span data-ttu-id="605ac-126">Si c'est le cas, notez les informations d'identification afin de pouvoir les utiliser pour configurer l'application de service après sa restauration.</span><span class="sxs-lookup"><span data-stu-id="605ac-126">If it does, make a note of the credentials so you can use them to configure the service application after it is restored.</span></span>  
  
### <a name="backup-the-encryption-keys-using-central-administration"></a><span data-ttu-id="605ac-127">Sauvegarder les clés de chiffrement à l'aide de l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="605ac-127">Backup the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="605ac-128">Pour plus d’informations sur la sauvegarde des clés de chiffrement [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consultez la section Clés de chiffrement de l’article [Gérer une application de service SharePoint Reporting Services](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="605ac-128">For information on backing up the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
###  <a name="backup-the-service-application-using-sharepoint-central-administration"></a><a name="bkmk_centraladmin"></a><span data-ttu-id="605ac-129">Sauvegarder l’application de service à l’aide de l’administration centrale de SharePoint</span><span class="sxs-lookup"><span data-stu-id="605ac-129">Backup the Service application Using SharePoint Central Administration</span></span>  
 <span data-ttu-id="605ac-130">Pour sauvegarder l'application de service, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="605ac-130">To back up the Service Application, complete the following steps:</span></span>  
  
1.  <span data-ttu-id="605ac-131">Dans l'Administration centrale de SharePoint, cliquez sur **Effectuer une sauvegarde** dans le groupe **Sauvegarde et restauration** .</span><span class="sxs-lookup"><span data-stu-id="605ac-131">In SharePoint Central Administration Click **Perform a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="605ac-132">Sous le nœud **Services partagés** , développez **Applications de services partagés** et sélectionnez votre application de service.</span><span class="sxs-lookup"><span data-stu-id="605ac-132">Under the **Shared Services** node, expand **Shared Service Applications** and select your service application.</span></span> <span data-ttu-id="605ac-133">Elle sera du type **Application de service SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="605ac-133">It will have a type of **SQL Server Reporting Services Service Application**.</span></span>  
  
3.  <span data-ttu-id="605ac-134">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="605ac-134">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="605ac-135">Tapez le chemin d'accès pour l'**Emplacement de sauvegarde :** et cliquez sur **Démarrer la sauvegarde**.</span><span class="sxs-lookup"><span data-stu-id="605ac-135">Type the path for the **Backup location:** and click **Start Backup**</span></span>  
  
5.  <span data-ttu-id="605ac-136">Répétez le processus ci-dessus mais au lieu de sélectionner l'application de service, développez le nœud **Proxys de services partagés** , puis sélectionnez le proxy de l'application de service.</span><span class="sxs-lookup"><span data-stu-id="605ac-136">Repeat the process above but instead of selecting the service application, expand the **Shared Services Proxies** node, and select service application proxy.</span></span> <span data-ttu-id="605ac-137">Elle sera du type **Proxy d'application de service SQL Server Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="605ac-137">It will have a type of **SQL Server Reporting Services Service Application Proxy**.</span></span>  
  
 <span data-ttu-id="605ac-138">Pour plus d'informations, consultez les rubriques suivantes dans la documentation de SharePoint :</span><span class="sxs-lookup"><span data-stu-id="605ac-138">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="605ac-139">[Enregistrer une application de service (SharePoint Foundation 2010) dans la documentation SharePoint](https://msdn.microsoft.com/library/ee748601.aspx).</span><span class="sxs-lookup"><span data-stu-id="605ac-139">[Back up a service application (SharePoint Foundation 2010) in the SharePoint documenttation](https://msdn.microsoft.com/library/ee748601.aspx).</span></span>  
  
 [<span data-ttu-id="605ac-140">Enregistrer une application de service (SharePoint Server 2010)</span><span class="sxs-lookup"><span data-stu-id="605ac-140">Back up a service application (SharePoint Server 2010)</span></span>](https://technet.microsoft.com/library/ee428318.aspx)  
  
### <a name="verify-execution-account-and-database-authentication"></a><span data-ttu-id="605ac-141">Vérifier le compte d'exécution et l'authentification de la base de données</span><span class="sxs-lookup"><span data-stu-id="605ac-141">Verify Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="605ac-142">**Compte d'exécution :** pour vérifier si votre application de service utilise un compte d'exécution :</span><span class="sxs-lookup"><span data-stu-id="605ac-142">**Execution Account:** To verify if your service application is using an execution account:</span></span>  
  
1.  <span data-ttu-id="605ac-143">Dans l’administration centrale de SharePoint, cliquez sur **gérer les applications de service** dans le groupe gestion des **applications** .</span><span class="sxs-lookup"><span data-stu-id="605ac-143">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="605ac-144">Cliquez sur le nom de votre application de service, puis cliquez sur **gérer** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="605ac-144">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="605ac-145">Cliquez sur **Compte d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="605ac-145">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="605ac-146">Si un compte d'exécution est configuré, vous devez connaître les informations d'identification lorsqu'il est temps de restaurer la sauvegarde de l'application de service.</span><span class="sxs-lookup"><span data-stu-id="605ac-146">If an execution account is configured, you need to know the credentials when it is time to restore the service application backup.</span></span> <span data-ttu-id="605ac-147">N'effectuez pas la procédure de sauvegarde et restauration avant de connaître les informations d'identification correctes.</span><span class="sxs-lookup"><span data-stu-id="605ac-147">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
 <span data-ttu-id="605ac-148">**Authentification de base de données :** pour vérifier si votre application de service utilise l'authentification Windows pour l'authentification de base de données :</span><span class="sxs-lookup"><span data-stu-id="605ac-148">**Database Authentication:** To verify if your service application is using Windows Authentication for the database authentication:</span></span>  
  
1.  <span data-ttu-id="605ac-149">Dans l’administration centrale de SharePoint, cliquez sur **gérer les applications de service** dans le groupe gestion des **applications** .</span><span class="sxs-lookup"><span data-stu-id="605ac-149">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="605ac-150">Cliquez sur le nom de votre application de service et cliquez sur **Propriétés** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="605ac-150">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="605ac-151">Consultez la section **Base de données de service SQL Server Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="605ac-151">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="605ac-152">Si l'authentification Windows est configurée, vous devez connaître les informations d'identification pour que vous puissiez configurer l'application de service après l'avoir restaurée.</span><span class="sxs-lookup"><span data-stu-id="605ac-152">If Windows Authentication is configured, you need to know the credentials so you can configure the service application after you restore it.</span></span> <span data-ttu-id="605ac-153">N'effectuez pas la procédure de sauvegarde et restauration avant de connaître les informations d'identification correctes.</span><span class="sxs-lookup"><span data-stu-id="605ac-153">Do not proceed with the backup and restore procedure until you know the correct credentials.</span></span>  
  
##  <a name="restore-the-service-application"></a><a name="bkmk_restore"></a><span data-ttu-id="605ac-154">Restaurer l’application de service</span><span class="sxs-lookup"><span data-stu-id="605ac-154">Restore the Service Application</span></span>  
 <span data-ttu-id="605ac-155">Exécutez les étapes suivantes dans l'ordre :</span><span class="sxs-lookup"><span data-stu-id="605ac-155">Complete the following steps in order:</span></span>  
  
1.  <span data-ttu-id="605ac-156">Restaurez l'application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="605ac-156">Restore the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] service application.</span></span>  
  
2.  <span data-ttu-id="605ac-157">Restaurer les clés de chiffrement</span><span class="sxs-lookup"><span data-stu-id="605ac-157">Restore the encryption keys</span></span>  
  
3.  <span data-ttu-id="605ac-158">Si votre application de service utilisait un compte d'exécution ou une authentification Windows pour l'accès aux bases de données, configurez les informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="605ac-158">If your service application was using an execution account or Windows authentication for database access, configure the credentials.</span></span>  
  
### <a name="restore-the-service-application-using-sharepoint-central-administration"></a><span data-ttu-id="605ac-159">Restaurer l'application de service à l'aide de l'Administration centrale de SharePoint</span><span class="sxs-lookup"><span data-stu-id="605ac-159">Restore the Service application Using SharePoint Central Administration</span></span>  
  
1.  <span data-ttu-id="605ac-160">Dans l'Administration centrale de SharePoint, cliquez sur **Restauration à partir d’une sauvegarde** dans le groupe **Sauvegarde et restauration** .</span><span class="sxs-lookup"><span data-stu-id="605ac-160">In SharePoint Central Administration Click **Restore from a backup** in the **Backup and Restore** group.</span></span>  
  
2.  <span data-ttu-id="605ac-161">Tapez le chemin d'accès à votre fichier de sauvegarde dans la zone **Emplacement de l'historique de sauvegarde** et cliquez sur **Actualiser**.</span><span class="sxs-lookup"><span data-stu-id="605ac-161">Type the path to your backup file in **Backup Directory Location** box and click **Refresh**.</span></span>  
  
3.  <span data-ttu-id="605ac-162">Sélectionnez votre sauvegarde d'application de service dans la liste **Composant de niveau supérieur** puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="605ac-162">Select your service application backup from the **Top Component** list and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="605ac-163">Sélectionnez votre application [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="605ac-163">Select your [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] application and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="605ac-164">Dans la section **Noms de connexion et mots de passe** , entrez le mot de passe pour le nom de connexion.</span><span class="sxs-lookup"><span data-stu-id="605ac-164">In the **Login Names and Passwords** section type the password for the login name.</span></span> <span data-ttu-id="605ac-165">Cette zone doit être renseignée avec le nom de connexion que l'application de service utilisait avant la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="605ac-165">The login name box should be populated with the login the service application was using prior to the backup.</span></span>  
  
6.  <span data-ttu-id="605ac-166">Cliquez sur **Démarrer la restauration**.</span><span class="sxs-lookup"><span data-stu-id="605ac-166">Click **Start Restore**.</span></span>  
  
7.  <span data-ttu-id="605ac-167">Répétez le processus ci-dessus mais au lieu de restaurer l'application de service, développez le nœud **Services partagés** , puis développez le nœud **Applications de services partagés** .</span><span class="sxs-lookup"><span data-stu-id="605ac-167">Repeat the process above but instead of restoring the service application, expand the **Shared Services** node and then expand the **Shared Service Applications** node.</span></span>  
  
 <span data-ttu-id="605ac-168">Pour plus d'informations, consultez les rubriques suivantes dans la documentation de SharePoint :</span><span class="sxs-lookup"><span data-stu-id="605ac-168">For more information, see the following topics in the SharePoint documentation:</span></span>  
  
 <span data-ttu-id="605ac-169">[Restaurer une application de service (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span><span class="sxs-lookup"><span data-stu-id="605ac-169">[Restore a service application (SharePoint Foundation 2010)](https://msdn.microsoft.com/library/ee748615.aspx).</span></span>  
  
 <span data-ttu-id="605ac-170">[Restaurer une application de service (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span><span class="sxs-lookup"><span data-stu-id="605ac-170">[Restore a service application (SharePoint Server 2010)](https://technet.microsoft.com/library/ee428305.aspx).</span></span>  
  
### <a name="restore-the-encryption-keys-using-central-administration"></a><span data-ttu-id="605ac-171">Restaurer les clés de chiffrement à l'aide de l'Administration centrale</span><span class="sxs-lookup"><span data-stu-id="605ac-171">Restore the Encryption Keys using Central Administration</span></span>  
 <span data-ttu-id="605ac-172">Pour plus d’informations sur la restauration des clés de chiffrement [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], consultez la section Clés de chiffrement de l’article [Gérer une application de service SharePoint Reporting Services](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="605ac-172">For information on restoring the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] encryption keys, see the "Encryption Keys" section of [Manage a Reporting Services SharePoint Service Application](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md).</span></span>  
  
### <a name="configure-the-execution-account-and-database-authentication"></a><span data-ttu-id="605ac-173">Configurer le compte d'exécution et l'authentification de base de données</span><span class="sxs-lookup"><span data-stu-id="605ac-173">Configure the Execution Account and Database Authentication</span></span>  
 <span data-ttu-id="605ac-174">**Compte d'exécution :** si votre application de service utilisait un compte d'exécution, procédez comme suit pour le configurer :</span><span class="sxs-lookup"><span data-stu-id="605ac-174">**Execution Account:** If your service application was using an execution account complete the following steps to configure it:</span></span>  
  
1.  <span data-ttu-id="605ac-175">Dans l’administration centrale de SharePoint, cliquez sur **gérer les applications de service** dans le groupe gestion des **applications** .</span><span class="sxs-lookup"><span data-stu-id="605ac-175">In SharePoint Central Administration, click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="605ac-176">Cliquez sur le nom de votre application de service, puis cliquez sur **gérer** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="605ac-176">Click the name of your service application and then click **Manage** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="605ac-177">Cliquez sur **Compte d'exécution**.</span><span class="sxs-lookup"><span data-stu-id="605ac-177">Click **Execution Account**.</span></span>  
  
4.  <span data-ttu-id="605ac-178">Tapez le compte et le mot de passe, puis sélectionnez la zone **Spécifier un compte d'exécution** .</span><span class="sxs-lookup"><span data-stu-id="605ac-178">Type the account, password, and select the **Specify and Execution Account** box.</span></span>  
  
5.  <span data-ttu-id="605ac-179">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="605ac-179">Click **OK**.</span></span>  
  
 <span data-ttu-id="605ac-180">**Authentification de base de données :** si votre application de service utilisait l'authentification Windows pour l'authentification de base de données procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="605ac-180">**Database Authentication:** If your service application was using Windows Authentication for the database authentication complete the following steps:</span></span>  
  
1.  <span data-ttu-id="605ac-181">Dans l’administration centrale de SharePoint, cliquez sur **gérer les applications de service** dans le groupe gestion des **applications** .</span><span class="sxs-lookup"><span data-stu-id="605ac-181">In SharePoint Central Administration click **Manage Service Applications** in the **Application Management** group.</span></span>  
  
2.  <span data-ttu-id="605ac-182">Cliquez sur le nom de votre application de service et cliquez sur **Propriétés** dans le ruban SharePoint.</span><span class="sxs-lookup"><span data-stu-id="605ac-182">Click the name of your service application and then click **Properties** in the SharePoint Ribbon.</span></span>  
  
3.  <span data-ttu-id="605ac-183">Consultez la section **Base de données de service SQL Server Reporting Services (SSRS)** .</span><span class="sxs-lookup"><span data-stu-id="605ac-183">Review the **Reporting Services (SSRS) Service Database** section.</span></span>  
  
4.  <span data-ttu-id="605ac-184">Sélectionnez **Authentification Windows**.</span><span class="sxs-lookup"><span data-stu-id="605ac-184">Select **Windows Authentication**.</span></span>  
  
5.  <span data-ttu-id="605ac-185">Tapez le compte et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="605ac-185">Type the account and password.</span></span> <span data-ttu-id="605ac-186">Sélectionnez **Utiliser comme informations d'identification Windows** si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="605ac-186">Select **Use as Windows Credentials** if appropriate.</span></span>  
  
6.  <span data-ttu-id="605ac-187">Cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="605ac-187">Click **Ok**</span></span>  
  
  
