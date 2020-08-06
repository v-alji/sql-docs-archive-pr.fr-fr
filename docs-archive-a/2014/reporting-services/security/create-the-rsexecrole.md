---
title: Créer le rôle RSExecRole | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- RSExecRole
ms.assetid: 7ac17341-df7e-4401-870e-652caa2859c0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0037ef0c4d7a949b5a30bb45356613f6114db130
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699288"
---
# <a name="create-the-rsexecrole"></a><span data-ttu-id="5458e-102">Créer le rôle RSExecRole</span><span class="sxs-lookup"><span data-stu-id="5458e-102">Create the RSExecRole</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5458e-103">utilise un rôle de base de données prédéfini appelé `RSExecRole` pour octroyer des autorisations de serveur de rapports à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-103">uses a predefined database role called `RSExecRole` to grant report server permissions to the report server database.</span></span> <span data-ttu-id="5458e-104">Le `RSExecRole` rôle est créé automatiquement avec la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-104">The `RSExecRole` role is created automatically with the report server database.</span></span> <span data-ttu-id="5458e-105">En règle générale, ne modifiez ou n'assignez jamais d'autres utilisateurs au rôle.</span><span class="sxs-lookup"><span data-stu-id="5458e-105">As a rule, you should never modify it or assign other users to the role.</span></span> <span data-ttu-id="5458e-106">Toutefois, lorsque vous déplacez une base de données du serveur de rapports vers un nouveau ou différent [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , doit recréer le rôle dans les bases de données système Master et msdb.</span><span class="sxs-lookup"><span data-stu-id="5458e-106">However, when you move a report server database to a new or different [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssDE](../../../includes/ssde-md.md)], must re-create the role in the Master and MSDB system databases.</span></span>

 <span data-ttu-id="5458e-107">À l'aide des instructions suivantes, vous exécuterez les étapes ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="5458e-107">Using the following instructions, you will perform the following steps:</span></span>

-   <span data-ttu-id="5458e-108">créer et mettre en service le rôle `RSExecRole` dans la base de données système Master ;</span><span class="sxs-lookup"><span data-stu-id="5458e-108">Create and provision the `RSExecRole` in the Master system database.</span></span>

-   <span data-ttu-id="5458e-109">créer et mettre en service le rôle `RSExecRole` dans la base de données système MSDB.</span><span class="sxs-lookup"><span data-stu-id="5458e-109">Create and provision the `RSExecRole` in the MSDB system database.</span></span>

> [!NOTE]
>  <span data-ttu-id="5458e-110">Les instructions de cette rubrique sont destinées aux utilisateurs qui ne souhaitent pas exécuter un script ou écrire du code WMI pour mettre en service la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-110">The instructions in this topic are intended for users who do not want to run a script or write WMI code to provision the report server database.</span></span> <span data-ttu-id="5458e-111">Si vous gérez un grand déploiement et que vous allez déplacer régulièrement des bases de données, il est conseillé d'écrire un script pour automatiser ces étapes.</span><span class="sxs-lookup"><span data-stu-id="5458e-111">If you manage a large deployment and will be moving databases routinely, you should write a script to automate these steps.</span></span> <span data-ttu-id="5458e-112">Pour plus d’informations, consultez [Accéder au fournisseur WMI de Reporting Services](../tools/access-the-reporting-services-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="5458e-112">For more information, see [Access the Reporting Services WMI Provider](../tools/access-the-reporting-services-wmi-provider.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="5458e-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5458e-113">Before you start</span></span>

-   <span data-ttu-id="5458e-114">Effectuez une sauvegarde des clés de chiffrement afin de pouvoir les restaurer après le déplacement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5458e-114">Back up the encryption keys so that you can restore them after the database is moved.</span></span> <span data-ttu-id="5458e-115">Cette étape n'affecte pas directement votre capacité à créer et à mettre en service le rôle `RSExecRole`, mais vous devez disposer d'une sauvegarde des clés afin de vérifier votre travail.</span><span class="sxs-lookup"><span data-stu-id="5458e-115">This is step does not directly affect your ability to create and provision the `RSExecRole`, but you must have a backup of the keys in order to verify your work.</span></span> <span data-ttu-id="5458e-116">Pour plus d’informations, consultez [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span><span class="sxs-lookup"><span data-stu-id="5458e-116">For more information, see [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md).</span></span>

-   <span data-ttu-id="5458e-117">Vérifiez que vous avez ouvert une session en tant que compte d'utilisateur qui dispose d'autorisations `sysadmin` sur l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5458e-117">Verify you are logged on as a user account that has `sysadmin` permissions on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span>

-   <span data-ttu-id="5458e-118">Vérifiez que le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent est installé et en cours d'exécution sur l'instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] que vous envisagez d'utiliser.</span><span class="sxs-lookup"><span data-stu-id="5458e-118">Verify [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service is installed and running on the instance of the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that you plan to use.</span></span>

-   <span data-ttu-id="5458e-119">Attachez les bases de données reportservertempdb and reportserver.</span><span class="sxs-lookup"><span data-stu-id="5458e-119">Attach the reportservertempdb and reportserver databases.</span></span> <span data-ttu-id="5458e-120">Vous n'êtes pas obligé d'attacher les bases de données pour créer le rôle réel, mais elles doivent l'être pour que vous puissiez tester votre travail.</span><span class="sxs-lookup"><span data-stu-id="5458e-120">You are not required to attach the databases to create the actual role, but they must be attached before you can test your work.</span></span>

 <span data-ttu-id="5458e-121">Les instructions permettant de créer manuellement le rôle `RSExecRole` sont destinées à être utilisées dans le contexte de la migration d'une installation du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-121">The instructions for manually creating the `RSExecRole` are intended to be used within the context of migrating a report server installation.</span></span> <span data-ttu-id="5458e-122">Les tâches importantes telles que la sauvegarde et le déplacement de la base de données du serveur de rapports ne sont pas traitées dans cette rubrique, mais sont présentées dans la documentation du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="5458e-122">Important tasks such as backing up and moving the report server database are not addressed in this topic, but are documented in the Database Engine documentation.</span></span>

## <a name="create-rsexecrole-in-master"></a><span data-ttu-id="5458e-123">Création du rôle RSExecRole dans la base de données Master</span><span class="sxs-lookup"><span data-stu-id="5458e-123">Create RSExecRole in Master</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5458e-124">utilise des procédures stockées étendues associées au service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent pour prendre en charge des opérations planifiées.</span><span class="sxs-lookup"><span data-stu-id="5458e-124">uses extended stored procedures for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Agent service to support scheduled operations.</span></span> <span data-ttu-id="5458e-125">Les étapes suivantes expliquent comment octroyer au rôle `RSExecRole` des autorisations Execute pour les procédures.</span><span class="sxs-lookup"><span data-stu-id="5458e-125">The following steps explain how to grant Execute permissions for the procedures to the `RSExecRole` role.</span></span>

#### <a name="to-create-rsexecrole-in-the-master-system-database-using-management-studio"></a><span data-ttu-id="5458e-126">Pour créer RSExecRole dans la base de données système Master à l'aide de Management Studio</span><span class="sxs-lookup"><span data-stu-id="5458e-126">To create RSExecRole in the Master system database using Management Studio</span></span>

1.  <span data-ttu-id="5458e-127">Démarrez [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] et connectez-vous à l'instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)] qui héberge la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-127">Start [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] and connect to the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] instance that hosts the report server database.</span></span>

2.  <span data-ttu-id="5458e-128">Ouvrez **Bases de données**.</span><span class="sxs-lookup"><span data-stu-id="5458e-128">Open **Databases**.</span></span>

3.  <span data-ttu-id="5458e-129">Ouvrez **Bases de données système**.</span><span class="sxs-lookup"><span data-stu-id="5458e-129">Open **System Databases**.</span></span>

4.  <span data-ttu-id="5458e-130">Ouvrez `Master`.</span><span class="sxs-lookup"><span data-stu-id="5458e-130">Open `Master`.</span></span>

5.  <span data-ttu-id="5458e-131">Ouvrez **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="5458e-131">Open **Security**.</span></span>

6.  <span data-ttu-id="5458e-132">Ouvrez **Rôles**.</span><span class="sxs-lookup"><span data-stu-id="5458e-132">Open **Roles**.</span></span>

7.  <span data-ttu-id="5458e-133">Cliquez avec le bouton droit sur **Rôles de base de données**, puis sélectionnez **Nouveau rôle de base de données**.</span><span class="sxs-lookup"><span data-stu-id="5458e-133">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="5458e-134">La page Général s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5458e-134">The General page appears.</span></span>

8.  <span data-ttu-id="5458e-135">Dans **nom du rôle**, tapez `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="5458e-135">In **Role name**, type `RSExecRole`.</span></span>

9. <span data-ttu-id="5458e-136">Dans **propriétaire**, tapez **dbo**.</span><span class="sxs-lookup"><span data-stu-id="5458e-136">In **Owner**, type **DBO**.</span></span>

10. <span data-ttu-id="5458e-137">Cliquez sur **Éléments sécurisables**.</span><span class="sxs-lookup"><span data-stu-id="5458e-137">Click **Securables**.</span></span>

11. <span data-ttu-id="5458e-138">Cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="5458e-138">Click **Search**.</span></span> <span data-ttu-id="5458e-139">La boîte de dialogue **Ajouter des objets** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5458e-139">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="5458e-140">L'option **Objets spécifiques** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="5458e-140">The **Specific Objects** option is selected by default.</span></span>

12. <span data-ttu-id="5458e-141">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-141">Click **OK**.</span></span> <span data-ttu-id="5458e-142">La boîte de dialogue **Sélectionner des objets** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5458e-142">The **Select Objects** dialog box appears.</span></span>

13. <span data-ttu-id="5458e-143">Cliquez sur **Types d'objets**.</span><span class="sxs-lookup"><span data-stu-id="5458e-143">Click **Object Types**.</span></span>

14. <span data-ttu-id="5458e-144">Cliquez sur **Procédures stockées étendues**.</span><span class="sxs-lookup"><span data-stu-id="5458e-144">Click **Extended Stored Procedures**.</span></span>

15. <span data-ttu-id="5458e-145">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-145">Click **OK**.</span></span>

16. <span data-ttu-id="5458e-146">Cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="5458e-146">Click **Browse**.</span></span>

17. <span data-ttu-id="5458e-147">Faites défiler la liste des procédures stockées étendues et sélectionnez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="5458e-147">Scroll down the list of extended stored procedures and select the following:</span></span>

    1.  <span data-ttu-id="5458e-148">xp_sqlagent_enum_jobs</span><span class="sxs-lookup"><span data-stu-id="5458e-148">xp_sqlagent_enum_jobs</span></span>

    2.  <span data-ttu-id="5458e-149">xp_sqlagent_is_starting</span><span class="sxs-lookup"><span data-stu-id="5458e-149">xp_sqlagent_is_starting</span></span>

    3.  <span data-ttu-id="5458e-150">xp_sqlagent_notify</span><span class="sxs-lookup"><span data-stu-id="5458e-150">xp_sqlagent_notify</span></span>

18. <span data-ttu-id="5458e-151">Cliquez sur **OK**, puis à nouveau sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="5458e-151">Click **OK**, and the click **OK** again.</span></span>

19. <span data-ttu-id="5458e-152">Cliquez sur la case à cocher située à l'intersection de la ligne **Execute** et de la colonne **Octroyer** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-152">In the **Execute** row, in the **Grant** column, click the check box, and then click **OK**.</span></span>

20. <span data-ttu-id="5458e-153">Répétez ces étapes pour chacune des procédures stockées restantes.</span><span class="sxs-lookup"><span data-stu-id="5458e-153">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="5458e-154">`RSExecRole` doit disposer des autorisations d'exécution pour les trois procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="5458e-154">`RSExecRole` must be granted Execute permissions for all three stored procedures.</span></span>

 <span data-ttu-id="5458e-155">![Page de propriétés du rôle de base de données](../media/rsexecroledbproperties.gif "Page de propriétés du rôle de base de données")</span><span class="sxs-lookup"><span data-stu-id="5458e-155">![Database Role Properties page](../media/rsexecroledbproperties.gif "Database Role Properties page")</span></span>

## <a name="create-rsexecrole-in-msdb"></a><span data-ttu-id="5458e-156">Création du rôle RSExecRole dans la base de données MSDB</span><span class="sxs-lookup"><span data-stu-id="5458e-156">Create RSExecRole in MSDB</span></span>
 <span data-ttu-id="5458e-157">Reporting Services utilise des procédures stockées associées au service Agent SQL Server et extrait des informations sur les travaux à partir de tables système pour prendre en charge les opérations planifiées.</span><span class="sxs-lookup"><span data-stu-id="5458e-157">Reporting Services uses stored procedures for SQL Server Agent service and retrieves job information from system tables to support scheduled operations.</span></span> <span data-ttu-id="5458e-158">Les étapes suivantes expliquent comment octroyer au rôle RSExecRole des autorisations Execute pour les procédures et des autorisations Select sur les tables.</span><span class="sxs-lookup"><span data-stu-id="5458e-158">The following steps explain how to grant Execute permissions for the procedures and Select permissions on the tables to the RSExecRole.</span></span>

#### <a name="to-create-rsexecrole-in-the-msdb-system-database"></a><span data-ttu-id="5458e-159">Pour créer RSExecRole dans la base de données système MSDB</span><span class="sxs-lookup"><span data-stu-id="5458e-159">To create RSExecRole in the MSDB system database</span></span>

1.  <span data-ttu-id="5458e-160">Répétez les mêmes étapes pour octroyer des autorisations aux procédures stockées et aux tables dans MSDB.</span><span class="sxs-lookup"><span data-stu-id="5458e-160">Repeat similar steps for granting permissions to stored procedures and tables in MSDB.</span></span> <span data-ttu-id="5458e-161">Pour simplifier ces étapes, vous mettrez en service les procédures stockées et les tables séparément.</span><span class="sxs-lookup"><span data-stu-id="5458e-161">To simplify the steps, you will provision the stored procedures and tables separately.</span></span>

2.  <span data-ttu-id="5458e-162">Ouvrez `MSDB`.</span><span class="sxs-lookup"><span data-stu-id="5458e-162">Open `MSDB`.</span></span>

3.  <span data-ttu-id="5458e-163">Ouvrez **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="5458e-163">Open **Security**.</span></span>

4.  <span data-ttu-id="5458e-164">Ouvrez **Rôles**.</span><span class="sxs-lookup"><span data-stu-id="5458e-164">Open **Roles**.</span></span>

5.  <span data-ttu-id="5458e-165">Cliquez avec le bouton droit sur **Rôles de base de données**, puis sélectionnez **Nouveau rôle de base de données**.</span><span class="sxs-lookup"><span data-stu-id="5458e-165">Right-click **Database Roles**, and select **New Database Role**.</span></span> <span data-ttu-id="5458e-166">La page Général s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5458e-166">The General page appears.</span></span>

6.  <span data-ttu-id="5458e-167">Dans nom du rôle, tapez `RSExecRole` .</span><span class="sxs-lookup"><span data-stu-id="5458e-167">In Role name, type `RSExecRole`.</span></span>

7.  <span data-ttu-id="5458e-168">Dans propriétaire, tapez **dbo**.</span><span class="sxs-lookup"><span data-stu-id="5458e-168">In Owner, type **DBO**.</span></span>

8.  <span data-ttu-id="5458e-169">Cliquez sur **Éléments sécurisables**.</span><span class="sxs-lookup"><span data-stu-id="5458e-169">Click **Securables**.</span></span>

9. <span data-ttu-id="5458e-170">Cliquez sur **Add**.</span><span class="sxs-lookup"><span data-stu-id="5458e-170">Click **Add**.</span></span> <span data-ttu-id="5458e-171">La boîte de dialogue **Ajouter des objets** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5458e-171">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="5458e-172">L'option **Spécifier des objets** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="5458e-172">The **Specify Objects** option is selected by default.</span></span>

10. <span data-ttu-id="5458e-173">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-173">Click **OK**.</span></span>

11. <span data-ttu-id="5458e-174">Cliquez sur **Types d'objet**.</span><span class="sxs-lookup"><span data-stu-id="5458e-174">Click **Object Types**.</span></span>

12. <span data-ttu-id="5458e-175">Cliquez sur **Procédures stockées**.</span><span class="sxs-lookup"><span data-stu-id="5458e-175">Click **Stored Procedures.**</span></span>

13. <span data-ttu-id="5458e-176">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-176">Click **OK**.</span></span>

14. <span data-ttu-id="5458e-177">Cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="5458e-177">Click **Browse**.</span></span>

15. <span data-ttu-id="5458e-178">Faites défiler la liste des éléments et sélectionnez les suivants :</span><span class="sxs-lookup"><span data-stu-id="5458e-178">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="5458e-179">sp_add_category</span><span class="sxs-lookup"><span data-stu-id="5458e-179">sp_add_category</span></span>

    2.  <span data-ttu-id="5458e-180">sp_add_job</span><span class="sxs-lookup"><span data-stu-id="5458e-180">sp_add_job</span></span>

    3.  <span data-ttu-id="5458e-181">sp_add_jobschedule</span><span class="sxs-lookup"><span data-stu-id="5458e-181">sp_add_jobschedule</span></span>

    4.  <span data-ttu-id="5458e-182">sp_add_jobserver</span><span class="sxs-lookup"><span data-stu-id="5458e-182">sp_add_jobserver</span></span>

    5.  <span data-ttu-id="5458e-183">sp_add_jobstep</span><span class="sxs-lookup"><span data-stu-id="5458e-183">sp_add_jobstep</span></span>

    6.  <span data-ttu-id="5458e-184">sp_delete_job</span><span class="sxs-lookup"><span data-stu-id="5458e-184">sp_delete_job</span></span>

    7.  <span data-ttu-id="5458e-185">sp_help_category</span><span class="sxs-lookup"><span data-stu-id="5458e-185">sp_help_category</span></span>

    8.  <span data-ttu-id="5458e-186">sp_help_job</span><span class="sxs-lookup"><span data-stu-id="5458e-186">sp_help_job</span></span>

    9. <span data-ttu-id="5458e-187">sp_help_jobschedule</span><span class="sxs-lookup"><span data-stu-id="5458e-187">sp_help_jobschedule</span></span>

    10. <span data-ttu-id="5458e-188">sp_verify_job_identifiers</span><span class="sxs-lookup"><span data-stu-id="5458e-188">sp_verify_job_identifiers</span></span>

16. <span data-ttu-id="5458e-189">Cliquez sur **OK**, puis à nouveau sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="5458e-189">Click **OK**, and the click **OK** again.</span></span>

17. <span data-ttu-id="5458e-190">Sélectionnez la première procédure stockée : sp_add_category.</span><span class="sxs-lookup"><span data-stu-id="5458e-190">Select the first stored procedure: sp_add_category.</span></span>

18. <span data-ttu-id="5458e-191">Cliquez sur la case à cocher située à l'intersection de la ligne **Execute** et de la colonne **Octroyer** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-191">In the **Execute** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

19. <span data-ttu-id="5458e-192">Répétez ces étapes pour chacune des procédures stockées restantes.</span><span class="sxs-lookup"><span data-stu-id="5458e-192">Repeat for each of the remaining stored procedures.</span></span> <span data-ttu-id="5458e-193">Des autorisations Execute doivent être octroyées à RSExecRole pour les dix procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="5458e-193">RSExecRole must be granted Execute permissions for all ten stored procedures.</span></span>

20. <span data-ttu-id="5458e-194">Sous l'onglet Éléments sécurisables, cliquez à nouveau sur **Ajouter** .</span><span class="sxs-lookup"><span data-stu-id="5458e-194">On the Securables tab, and click **Add** again.</span></span> <span data-ttu-id="5458e-195">La boîte de dialogue **Ajouter des objets** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="5458e-195">The **Add Objects** dialog box appears.</span></span> <span data-ttu-id="5458e-196">L'option **Spécifier des objets** est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="5458e-196">The **Specify Objects** option is selected by default.</span></span>

21. <span data-ttu-id="5458e-197">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-197">Click **OK**.</span></span>

22. <span data-ttu-id="5458e-198">Cliquez sur **Types d'objet**.</span><span class="sxs-lookup"><span data-stu-id="5458e-198">Click **Object Types**.</span></span>

23. <span data-ttu-id="5458e-199">Cliquez sur **Tables.**</span><span class="sxs-lookup"><span data-stu-id="5458e-199">Click **Tables.**</span></span>

24. <span data-ttu-id="5458e-200">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-200">Click **OK**.</span></span>

25. <span data-ttu-id="5458e-201">Cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="5458e-201">Click **Browse**.</span></span>

26. <span data-ttu-id="5458e-202">Faites défiler la liste des éléments et sélectionnez les suivants :</span><span class="sxs-lookup"><span data-stu-id="5458e-202">Scroll down the list of items and select the following:</span></span>

    1.  <span data-ttu-id="5458e-203">syscategories</span><span class="sxs-lookup"><span data-stu-id="5458e-203">syscategories</span></span>

    2.  <span data-ttu-id="5458e-204">sysjobs</span><span class="sxs-lookup"><span data-stu-id="5458e-204">sysjobs</span></span>

27. <span data-ttu-id="5458e-205">Cliquez sur **OK**, puis à nouveau sur **OK** .</span><span class="sxs-lookup"><span data-stu-id="5458e-205">Click **OK**, and the click **OK** again.</span></span>

28. <span data-ttu-id="5458e-206">Sélectionnez la première table : syscategories.</span><span class="sxs-lookup"><span data-stu-id="5458e-206">Select the first table: syscategories.</span></span>

29. <span data-ttu-id="5458e-207">Cliquez sur la case à cocher située à l'intersection de la ligne **Select** et de la colonne **Octroyer** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-207">In the **Select** row, in the **Grant** column, click the checkbox, and then click **OK**.</span></span>

30. <span data-ttu-id="5458e-208">Répétez ces étapes pour la table sysjobs.</span><span class="sxs-lookup"><span data-stu-id="5458e-208">Repeat for the sysjobs table.</span></span> <span data-ttu-id="5458e-209">Des autorisations Select doivent être octroyées à RSExecRole pour les deux tables.</span><span class="sxs-lookup"><span data-stu-id="5458e-209">RSExecRole must be granted Select permissions for both tables.</span></span>

## <a name="move-the-report-server-database"></a><span data-ttu-id="5458e-210">Déplacement de la base de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="5458e-210">Move the Report Server Database</span></span>
 <span data-ttu-id="5458e-211">Une fois les rôles créés, vous pouvez déplacer la base de données du serveur de rapports vers une nouvelle instance de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5458e-211">After you create the roles, you can move the report server database to new SQL Server instance.</span></span> <span data-ttu-id="5458e-212">Pour plus d’informations, consultez [Déplacement des bases de données du serveur de rapports vers un autre ordinateur &#40;en mode natif SSRS&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="5458e-212">For more information, see [Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md).</span></span>

 <span data-ttu-id="5458e-213">Si vous mettez à niveau le [!INCLUDE[ssDE](../../../includes/ssde-md.md)] vers [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], vous pouvez effectuer cette opération avant ou après le déplacement de la base de données.</span><span class="sxs-lookup"><span data-stu-id="5458e-213">If you are upgrading the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)], you can upgrade it before or after moving the database.</span></span>

 <span data-ttu-id="5458e-214">La base de données du serveur de rapports sera automatiquement mise à niveau vers [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] lorsque le serveur de rapports s'y connectera.</span><span class="sxs-lookup"><span data-stu-id="5458e-214">The report server database will be upgraded to the [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] automatically when the report server connects to it.</span></span> <span data-ttu-id="5458e-215">Il n'y a pas d'étapes spécifiques requises pour mettre à niveau la base de données.</span><span class="sxs-lookup"><span data-stu-id="5458e-215">There are no specific steps required for upgrading the database.</span></span>

## <a name="restore-encryption-keys-and-verify-your-work"></a><span data-ttu-id="5458e-216">Restauration des clés de chiffrement et vérification de votre travail</span><span class="sxs-lookup"><span data-stu-id="5458e-216">Restore Encryption Keys and Verify Your Work</span></span>
 <span data-ttu-id="5458e-217">Si vous avez attaché les bases de données du serveur de rapports, vous devez maintenant être en mesure d'effectuer les étapes suivantes pour vérifier votre travail.</span><span class="sxs-lookup"><span data-stu-id="5458e-217">If you have attached the report server databases, you should now be able to complete the following steps to verify your work.</span></span>

#### <a name="to-verify-report-server-operability-after-a-database-move"></a><span data-ttu-id="5458e-218">Pour vérifier le bon fonctionnement du serveur de rapports après le déplacement d'une base de données</span><span class="sxs-lookup"><span data-stu-id="5458e-218">To verify report server operability after a database move</span></span>

1.  <span data-ttu-id="5458e-219">Démarrez l'outil de configuration de Reporting Services, puis connectez-vous au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-219">Start the Reporting Services Configuration tool and connect to the report server.</span></span>

2.  <span data-ttu-id="5458e-220">Cliquez sur **Base de données**.</span><span class="sxs-lookup"><span data-stu-id="5458e-220">Click **Database**.</span></span>

3.  <span data-ttu-id="5458e-221">Cliquez sur **Modifier la base de données**.</span><span class="sxs-lookup"><span data-stu-id="5458e-221">Click **Change Database**.</span></span>

4.  <span data-ttu-id="5458e-222">Cliquez sur **Choisir une base de données de serveur de rapports existante**.</span><span class="sxs-lookup"><span data-stu-id="5458e-222">Click **Choose an existing report server database**.</span></span>

5.  <span data-ttu-id="5458e-223">Entrez le nom de serveur du moteur de base de données.</span><span class="sxs-lookup"><span data-stu-id="5458e-223">Enter the server name of the Database Engine.</span></span> <span data-ttu-id="5458e-224">Si vous avez attaché les bases de données du serveur de rapports à une instance nommée, vous devez taper le nom de l’instance au format suivant : \<servername> \\<InstanceName \> .</span><span class="sxs-lookup"><span data-stu-id="5458e-224">If you attached the report server databases to a named instance, you must type the instance name in this format: \<servername>\\<instancename\>.</span></span>

6.  <span data-ttu-id="5458e-225">Cliquez sur **Tester la connexion**.</span><span class="sxs-lookup"><span data-stu-id="5458e-225">Click **Test Connection**.</span></span>

7.  <span data-ttu-id="5458e-226">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="5458e-226">Click **Next**.</span></span>

8.  <span data-ttu-id="5458e-227">Dans Base de données, sélectionnez la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-227">On the Database, select the report server database.</span></span>

9. <span data-ttu-id="5458e-228">Cliquez sur **Suivant** pour terminer l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="5458e-228">Click **Next** and complete the wizard.</span></span>

10. <span data-ttu-id="5458e-229">Cliquez sur **Clés de chiffrement**.</span><span class="sxs-lookup"><span data-stu-id="5458e-229">Click **Encryption Keys**.</span></span>

11. <span data-ttu-id="5458e-230">Cliquez sur **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="5458e-230">Click **Restore**.</span></span>

12. <span data-ttu-id="5458e-231">Sélectionnez le fichier fort (.snk) qui contient la copie de sauvegarde de la clé symétrique utilisée pour déchiffrer les informations d'identification stockées et les informations de connexion dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-231">Select the strong file (.snk) that has the backup copy of the symmetric key used to decrypt stored credentials and connection information in the report server database.</span></span>

13. <span data-ttu-id="5458e-232">Entrez le mot de passe, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5458e-232">Enter the password and click **OK**.</span></span>

14. <span data-ttu-id="5458e-233">Cliquez sur **URL du Gestionnaire de rapports**.</span><span class="sxs-lookup"><span data-stu-id="5458e-233">Click **Report Manager URL**.</span></span>

15. <span data-ttu-id="5458e-234">Cliquez sur le lien pour ouvrir le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="5458e-234">Click the link to open Report Manager.</span></span> <span data-ttu-id="5458e-235">Les éléments du serveur de rapports provenant de la base de données du serveur de rapports doivent s'afficher.</span><span class="sxs-lookup"><span data-stu-id="5458e-235">You should see the report server items from the report server database.</span></span>

## <a name="see-also"></a><span data-ttu-id="5458e-236">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5458e-236">See Also</span></span>
 <span data-ttu-id="5458e-237">[Le déplacement des bases de données du serveur de rapports vers un autre ordinateur &#40;SSRS en mode natif&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [créer une base de données du serveur de rapports en mode natif &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [sauvegarder et restaurer des clés de chiffrement Reporting Services](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span><span class="sxs-lookup"><span data-stu-id="5458e-237">[Moving the Report Server Databases to Another Computer &#40;SSRS Native Mode&#41;](../report-server/moving-the-report-server-databases-to-another-computer-ssrs-native-mode.md) [Reporting Services Configuration Manager &#40;Native Mode&#41;](../../sql-server/install/reporting-services-configuration-manager-native-mode.md) [Create a Native Mode Report Server Database  &#40;SSRS Configuration Manager&#41;](../install-windows/ssrs-report-server-create-a-native-mode-report-server-database.md) [Back Up and Restore Reporting Services Encryption Keys](../install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys.md)</span></span>


