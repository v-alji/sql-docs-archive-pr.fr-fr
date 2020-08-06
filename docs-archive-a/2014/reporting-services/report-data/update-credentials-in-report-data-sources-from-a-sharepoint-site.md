---
title: Mettre à jour les informations d’identification dans les sources de données de rapport à partir d’un site SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e0c50b6e-89e7-4b4d-8fe5-c90682c5d1b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 923fee5656ed6032201fb4276fcca75be799e42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600559"
---
# <a name="update-credentials-in-report-data-sources-from-a-sharepoint-site"></a><span data-ttu-id="6520c-102">Mettre à jour les informations d'identification dans les sources de données de rapport à partir d'un site SharePoint</span><span class="sxs-lookup"><span data-stu-id="6520c-102">Update Credentials in Report Data Sources from a SharePoint Site</span></span>
  <span data-ttu-id="6520c-103">Cette rubrique explique comment mettre à jour les sources de données incorporées dans les rapports et les sources de données partagées enregistrées dans une bibliothèque de documents SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6520c-103">This topic describes how to update data sources embedded in reports and shared data sources that are saved in a SharePoint document library.</span></span>  
  
 <span data-ttu-id="6520c-104">Plusieurs de vos rapports peuvent inclure des sources de données ou utiliser des sources de données partagées configurées pour utiliser l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="6520c-104">Many of your reports might include data sources or use shared data sources that are configured to use Windows Authentication.</span></span> <span data-ttu-id="6520c-105">Dans certaines circonstances, comme lors de la création d'alertes de données sur les rapports enregistrés dans une bibliothèque de documents SharePoint, vous devez mettre à jour les informations d'identification de la source de données avec les informations d'identification stockées, ou bien vous pouvez choisir de ne configurer aucune information d'identification.</span><span class="sxs-lookup"><span data-stu-id="6520c-105">Under some circumstances, such as creating data alerts on reports saved to a SharePoint document library, you need to update the data source credentials to stored credentials or require no credentials.</span></span>  
  
 <span data-ttu-id="6520c-106">Pour utiliser les informations d'identification stockées dans les rapports, vous pouvez décider de créer et utiliser un nouveau compte de connexion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6520c-106">To use stored credentials in reports, you might decide to create and use a new SQL Server login.</span></span> <span data-ttu-id="6520c-107">Pour plus d’informations, consultez [Créer un compte de connexion](../../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="6520c-107">For more information, see [Create a Login](../../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
### <a name="to-update-an-embedded-data-source-to-use-stored-credentials"></a><span data-ttu-id="6520c-108">Pour mettre à jour une source de données incorporée et utiliser les informations d'identification stockées</span><span class="sxs-lookup"><span data-stu-id="6520c-108">To update an embedded data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="6520c-109">Allez à la bibliothèque de documents SharePoint où vous avez enregistré le rapport.</span><span class="sxs-lookup"><span data-stu-id="6520c-109">Go to the SharePoint document library where you saved the report.</span></span>  
  
2.  <span data-ttu-id="6520c-110">Cliquez sur l’icône pour développer le menu déroulant sur le rapport, puis cliquez sur **Gérer les sources de données**.</span><span class="sxs-lookup"><span data-stu-id="6520c-110">Click the icon for the expand drop-down menu on the report and then click **Manage Data Sources**.</span></span>  
  
     <span data-ttu-id="6520c-111">La page de gestion des sources de données s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="6520c-111">The Manage Data Sources page opens.</span></span>  
  
3.  <span data-ttu-id="6520c-112">Dans la colonne **Nom** , cliquez sur la source de données.</span><span class="sxs-lookup"><span data-stu-id="6520c-112">In the **Name** column, click the data source.</span></span>  
  
4.  <span data-ttu-id="6520c-113">Pour **Type de connexion** vérifiez que l’option **Source de données personnalisée** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6520c-113">For **Connection Type** verify that the **Custom data source** option is selected.</span></span>  
  
     <span data-ttu-id="6520c-114">Cette option indique que la source de données est incorporée dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="6520c-114">This option indicates that the data source is embedded in the report.</span></span>  
  
5.  <span data-ttu-id="6520c-115">Laissez les options **Type de source de données** et **Chaîne de connexion** comme elles sont, sauf si vous souhaitez que le rapport se connecte à un type de source de données, ou à un serveur ou magasin de données différent.</span><span class="sxs-lookup"><span data-stu-id="6520c-115">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the report to connect to different type of data source, a different server, or data store.</span></span>  
  
6.  <span data-ttu-id="6520c-116">Pour **Informations d’identification**, sélectionnez **Informations d’identification stockées**.</span><span class="sxs-lookup"><span data-stu-id="6520c-116">For **Credentials**, select **Stored credentials**.</span></span> <span data-ttu-id="6520c-117">Cette option fonctionne uniquement si la source de données n'accepte pas les informations d'identification ou si vous transmettez les informations d'identification d'une autre façon.</span><span class="sxs-lookup"><span data-stu-id="6520c-117">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="6520c-118">L’option **Informations d’identification non requises** peut également être utilisée dans certains cas.</span><span class="sxs-lookup"><span data-stu-id="6520c-118">The **Credentials are not required** option can also be used under some circumstances.</span></span>  
  
     <span data-ttu-id="6520c-119">Pour certains types de sources de données, le compte d'exécution sans assistance doit être configuré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6520c-119">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="6520c-120">Pour plus d’informations, consultez la rubrique relative au type de source de données correspondant dans [Ajouter des données à partir de sources de données externes &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) et [Configurer le compte d’exécution sans assistance &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6520c-120">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
7.  <span data-ttu-id="6520c-121">Tapez un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="6520c-121">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="6520c-122">Si le compte est un compte d’utilisateur de domaine Windows, spécifiez-le au format suivant : \<domain> \\<compte \> , puis sélectionnez **utiliser comme informations d’identification Windows lors de la connexion à la source de données**.</span><span class="sxs-lookup"><span data-stu-id="6520c-122">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source**.</span></span>  
  
    -   <span data-ttu-id="6520c-123">Si le nom d'utilisateur et le mot de passe sont des informations d'identification de base de données, ne sélectionnez pas **Utiliser comme informations d'identification Windows lors de la connexion à la source de données**.</span><span class="sxs-lookup"><span data-stu-id="6520c-123">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="6520c-124">Si le serveur de base de données prend en charge l'emprunt d'identité ou la délégation, vous pouvez sélectionner **Définir le contexte d'exécution pour ce compte**.</span><span class="sxs-lookup"><span data-stu-id="6520c-124">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
8.  <span data-ttu-id="6520c-125">Pour vérifier que la source de données peut se connecter à l’aide des informations d’identification mises à jour, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="6520c-125">To verify the data source can connect by using the updated credentials, click **Test connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-update-a-shared-data-source-to-use-stored-credentials"></a><span data-ttu-id="6520c-126">Pour mettre à jour une source de données partagée et utiliser les informations d'identification stockées</span><span class="sxs-lookup"><span data-stu-id="6520c-126">To update a shared data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="6520c-127">Accédez à la bibliothèque de documents SharePoint où vous avez enregistré la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="6520c-127">Go to the SharePoint document library where you saved the shared data source.</span></span>  
  
2.  <span data-ttu-id="6520c-128">Cliquez sur l’icône pour développer le menu déroulant sur la source de données partagée, puis cliquez sur **Modifier la définition de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="6520c-128">Click the icon for the expand drop-down menu on shared data source, and then click **Edit Data Source Definition**.</span></span>  
  
     <span data-ttu-id="6520c-129">La page de la source de données s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6520c-129">The Data Source page opens.</span></span>  
  
3.  <span data-ttu-id="6520c-130">Laissez les options **Type de source de données** et **Chaîne de connexion** comme elles sont, sauf si vous souhaitez que la source de données partagée se connecte à un type de source de données, ou à un serveur ou magasin de données différent.</span><span class="sxs-lookup"><span data-stu-id="6520c-130">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the shared data source to connect to different type of data source, a different server, or data store.</span></span>  
  
4.  <span data-ttu-id="6520c-131">Pour **Informations d’identification**, sélectionnez **Informations d’identification stockées**.</span><span class="sxs-lookup"><span data-stu-id="6520c-131">For **Credentials**, select **Stored credentials**.</span></span>  
  
     <span data-ttu-id="6520c-132">L’option **Informations d’identification non requises** peut également être utilisée dans certains cas.</span><span class="sxs-lookup"><span data-stu-id="6520c-132">The **Credentials are not required** option can also be used under some circumstances.</span></span> <span data-ttu-id="6520c-133">Cette option fonctionne uniquement si la source de données n'accepte pas les informations d'identification ou si vous transmettez les informations d'identification d'une autre façon.</span><span class="sxs-lookup"><span data-stu-id="6520c-133">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="6520c-134">Pour certains types de sources de données, le compte d'exécution sans assistance doit être configuré sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="6520c-134">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="6520c-135">Pour plus d’informations, consultez la rubrique relative au type de source de données correspondant dans [Ajouter des données à partir de sources de données externes &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) et [Configurer le compte d’exécution sans assistance &#40;Gestionnaire de configuration de SSRS&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="6520c-135">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="6520c-136">Tapez un nom d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="6520c-136">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="6520c-137">Si le compte est un compte d’utilisateur de domaine Windows, spécifiez-le au format suivant : \<domain> \\<compte \> , puis sélectionnez **utiliser comme informations d’identification Windows lors de la connexion à la source de données.**</span><span class="sxs-lookup"><span data-stu-id="6520c-137">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>  
  
    -   <span data-ttu-id="6520c-138">Si le nom d'utilisateur et le mot de passe sont des informations d'identification de base de données, ne sélectionnez pas **Utiliser comme informations d'identification Windows lors de la connexion à la source de données**.</span><span class="sxs-lookup"><span data-stu-id="6520c-138">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="6520c-139">Si le serveur de base de données prend en charge l'emprunt d'identité ou la délégation, vous pouvez sélectionner **Définir le contexte d'exécution pour ce compte**.</span><span class="sxs-lookup"><span data-stu-id="6520c-139">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
6.  <span data-ttu-id="6520c-140">Pour vérifier que la source de données peut se connecter à l’aide des informations d’identification mises à jour, cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="6520c-140">To verify the data source can connect using the updated credentials, **Test connection**.</span></span>  
  
7.  <span data-ttu-id="6520c-141">Vérifiez que l'option Activer cette source de données est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="6520c-141">Verify that Enable this data source is selected.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6520c-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6520c-142">See Also</span></span>  
 [<span data-ttu-id="6520c-143">Télécharger des documents vers une bibliothèque SharePoint &#40;Reporting Services en mode SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="6520c-143">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
  
