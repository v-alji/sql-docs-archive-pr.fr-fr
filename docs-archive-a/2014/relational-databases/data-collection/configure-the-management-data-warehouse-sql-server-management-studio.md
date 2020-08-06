---
title: Configurer l’entrepôt de données de gestion (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollection.wizard_finish.f1
- sql12.swb.dc.datacollection.wizard_maploginuser.f1
- sql12.swb.dc.datacollection.wizard_welcome.f1
- sql12.swb.dc.datacollection.wizard_choosemdw.f1
- sql12.swb.dc.datacollection.wizard_completecfg.f1
- sql12.swb.dc.datacollection.wizard_config.f1
- sql12.swb.dc.datacollection.wizard_createmdw.f1
helpviewer_keywords:
- data warehouse [SQL Server], multiple instances
- data warehouse [SQL Server], configuring
- Configure Management Data Warehouse Wizard
- management data warehouse, configuring
ms.assetid: 23a584f3-c5e1-414c-9afe-73cd7efbda4b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1ef4ddd518343a3076c72ecc41f9b15ddf092dc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615165"
---
# <a name="configure-the-management-data-warehouse-sql-server-management-studio"></a><span data-ttu-id="7e252-102">Configurer l'entrepôt de données de gestion (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="7e252-102">Configure the Management Data Warehouse (SQL Server Management Studio)</span></span>
  <span data-ttu-id="7e252-103">Cette rubrique explique comment configurer l'entrepôt de données de gestion pour prendre en charge le stockage des données sur une instance unique ou plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui utilisent le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="7e252-103">This topic describes how to configure the management data warehouse to support data storage on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the data collector.</span></span> <span data-ttu-id="7e252-104">Ces instances peuvent se trouver sur le même serveur ou sur différents serveurs.</span><span class="sxs-lookup"><span data-stu-id="7e252-104">These instances can be on the same server or on different servers.</span></span> <span data-ttu-id="7e252-105">Cette rubrique fournit également des descriptions de l'interface utilisateur pour la boîte de dialogue [Assistant Configuration de l'entrepôt de gestion des données](#Wizard) .</span><span class="sxs-lookup"><span data-stu-id="7e252-105">This topic also provides descriptions of the user interface for the [Configure Data Management Warehouse Wizard](#Wizard) dialog box.</span></span> <span data-ttu-id="7e252-106">Pour plus d'informations sur la configuration d'un collecteur de données, consultez [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span><span class="sxs-lookup"><span data-stu-id="7e252-106">For information about configuring a data collector, see [Configure Properties of a Data Collector](configure-properties-of-a-data-collector.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e252-107">Si l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour s'exécuter à l'aide de l'un des comptes de service système (système local, service réseau ou service local) et que l'entrepôt de données de gestion est créé sur une instance différente du collecteur de données, vous devez configurer les jeux d'éléments de collecte de sorte qu'ils utilisent un proxy pour télécharger les données vers l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is configured to run using one of the System service accounts (Local System, Network Service, or Local Service), and the management data warehouse is created on a different instance from the data collector, you must configure collection sets to use a proxy for uploading data to the management data warehouse.</span></span>  
  
### <a name="configure-the-management-data-warehouse-on-a-single-instance-or-multiple-instances-of-ssnoversion"></a><span data-ttu-id="7e252-108">Configurer l'entrepôt de données de gestion sur une instance unique ou plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e252-108">Configure the management data warehouse on a single instance or multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
1.  <span data-ttu-id="7e252-109">Vérifiez que l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] s'exécute.</span><span class="sxs-lookup"><span data-stu-id="7e252-109">Ensure that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running.</span></span>  
  
2.  <span data-ttu-id="7e252-110">Dans l'Explorateur d'objets, développez le nœud **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="7e252-110">In Object Explorer, expand the **Management** node.</span></span>  
  
3.  <span data-ttu-id="7e252-111">Cliquez avec le bouton droit sur **Collecte de données**, développez **Tâches**, puis cliquez sur **Configurer l’entrepôt de données de gestion**.</span><span class="sxs-lookup"><span data-stu-id="7e252-111">Right-click **Data Collection**, expand **Tasks**, and then click **Configure Management Data Warehouse**.</span></span>  
  
4.  <span data-ttu-id="7e252-112">Utilisez l' [Assistant Configuration de l'entrepôt de données de gestion](#Wizard) pour créer un entrepôt de données de gestion, configurer des connexions, activer la collecte de données et démarrer les **jeux d'éléments de collecte de données système**.</span><span class="sxs-lookup"><span data-stu-id="7e252-112">Use the [Configure Management Data Warehouse Wizard](#Wizard) to create a management data warehouse, configure logins, enable data collection, and start the **System Data Collection Sets**.</span></span>  
  
     <span data-ttu-id="7e252-113">Pour configurer plusieurs instances, passez à l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="7e252-113">To configure multiple instances, continue with step 5.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e252-114">L'utilisation de proxys dans les déploiements où le collecteur de données est installé sur plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui utilisent le même entrepôt de données de gestion est considérée comme étant la meilleure pratique.</span><span class="sxs-lookup"><span data-stu-id="7e252-114">It is considered best practice to use proxies in deployments where the data collector is installed on multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are using the same management data warehouse.</span></span>  
  
5.  <span data-ttu-id="7e252-115">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sur une autre instance et procédez de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="7e252-115">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] on another instance and do either of the following:</span></span>  
  
    -   <span data-ttu-id="7e252-116">Utilisez l'Assistant Configuration de l'entrepôt de données de gestion pour configurer la collecte de données pour l'entrepôt de données de gestion existant.</span><span class="sxs-lookup"><span data-stu-id="7e252-116">Use the Configure Management Data Warehouse wizard to configure data collection for the existing management data warehouse.</span></span>  
  
    -   <span data-ttu-id="7e252-117">Cliquez avec le bouton droit sur **Collecte de données**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="7e252-117">Right-click **Data Collection**, and then click **Properties**.</span></span> <span data-ttu-id="7e252-118">Sous l'onglet **Général** , spécifiez l'entrepôt de données de gestion existant et le serveur sur lequel il est installé.</span><span class="sxs-lookup"><span data-stu-id="7e252-118">On the **General** tab, specify the existing management data warehouse and the server that it is installed on.</span></span>  
  
6.  <span data-ttu-id="7e252-119">Répétez l'étape 5 jusqu'à ce que toutes les instances de base de données qui utilisent le collecteur de données soient configurées pour télécharger les données vers l'entrepôt de données de gestion partagé.</span><span class="sxs-lookup"><span data-stu-id="7e252-119">Repeat step 5 until all the database instances that use the data collector are configured to upload data to the shared management data warehouse.</span></span>  
  
####  <a name="configure-management-data-warehouse-wizard"></a><a name="Wizard"></a> <span data-ttu-id="7e252-120">Assistant Configuration de l'entrepôt de données de gestion</span><span class="sxs-lookup"><span data-stu-id="7e252-120">Configure Management Data Warehouse Wizard</span></span>  
 <span data-ttu-id="7e252-121">**Page d'accueil**</span><span class="sxs-lookup"><span data-stu-id="7e252-121">**Welcome Page**</span></span>  
  
 <span data-ttu-id="7e252-122">La page d'accueil est la page de démarrage de l'Assistant Configuration de la collecte de données.</span><span class="sxs-lookup"><span data-stu-id="7e252-122">The Welcome page is the starting page of the Configure Data Collection Wizard.</span></span> <span data-ttu-id="7e252-123">L'affichage de cette page est facultatif.</span><span class="sxs-lookup"><span data-stu-id="7e252-123">Displaying this page is optional.</span></span>  
  
 <span data-ttu-id="7e252-124">**Ne plus afficher cette page de démarrage.**</span><span class="sxs-lookup"><span data-stu-id="7e252-124">**Do not show this starting page again.**</span></span>  
 <span data-ttu-id="7e252-125">Sélectionnez cette option pour supprimer cette page la prochaine fois vous lancez l'Assistant Configuration de la collecte de données.</span><span class="sxs-lookup"><span data-stu-id="7e252-125">Select to suppress this page the next time you launch the Configure Data Collection Wizard.</span></span>  
  
 <span data-ttu-id="7e252-126">**Page Configuration du stockage de l'entrepôt de données de gestion**</span><span class="sxs-lookup"><span data-stu-id="7e252-126">**Configure Management Data Warehouse Storage Page**</span></span>  
  
 <span data-ttu-id="7e252-127">Utilisez cette page pour sélectionner un serveur de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et un entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-127">Use this page to select a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and management data warehouse.</span></span> <span data-ttu-id="7e252-128">L'entrepôt de données de gestion est une base de données relationnelle qui sert de stockage pour les données collectées.</span><span class="sxs-lookup"><span data-stu-id="7e252-128">The management data warehouse is a relational database that will store collected data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e252-129">Vous devez disposer du niveau d'autorisations approprié pour créer l'entrepôt de données de gestion sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7e252-129">You must have the appropriate level of permissions in order to create the management data warehouse on the server.</span></span> <span data-ttu-id="7e252-130">Pour plus d’informations, consultez [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e252-130">For more information, see [CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql).</span></span> <span data-ttu-id="7e252-131">Vous devez également disposer du niveau d'autorisations approprié pour créer des connexions pour les rôles d'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-131">You also must have the appropriate level of permissions to create logins for management data warehouse roles.</span></span>  
  
 <span data-ttu-id="7e252-132">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="7e252-132">**Server name**</span></span>  
 <span data-ttu-id="7e252-133">Spécifie le nom du serveur qui hébergera l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-133">Specifies the name of the server that will host the management data warehouse.</span></span>  
  
 <span data-ttu-id="7e252-134">Lors de la configuration d'un entrepôt de données de gestion, **Nom du serveur** est toujours le nom du serveur local et ne peut pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="7e252-134">When configuring a management data warehouse, **Server name** is always the name of the local server and cannot be modified.</span></span>  
  
 <span data-ttu-id="7e252-135">**Nom de la base de données**</span><span class="sxs-lookup"><span data-stu-id="7e252-135">**Database name**</span></span>  
 <span data-ttu-id="7e252-136">Spécifie la base de données relationnelle qui stockera les données collectées.</span><span class="sxs-lookup"><span data-stu-id="7e252-136">Specifies the relational database that will store collected data.</span></span> <span data-ttu-id="7e252-137">Utilisez la liste pour sélectionner une base de données existante ou cliquez sur **Nouveau** pour créer une base de données à l'aide de la boîte de dialogue **Nouvelle base de données** .</span><span class="sxs-lookup"><span data-stu-id="7e252-137">Use the list to select an existing database or click **New** to create a new database using the **New Database** dialog.</span></span>  
  
 <span data-ttu-id="7e252-138">L'option **Nouveau** est disponible uniquement lors de la configuration d'un jeu d'éléments de collecte de données.</span><span class="sxs-lookup"><span data-stu-id="7e252-138">The **New** option is available only when configuring a data collection set</span></span>  
  
 <span data-ttu-id="7e252-139">**Page Mapper les connexions et les utilisateurs**</span><span class="sxs-lookup"><span data-stu-id="7e252-139">**Map Logins and Users Page**</span></span>  
  
 <span data-ttu-id="7e252-140">Utilisez cette page pour mapper des connexions à des rôles d'utilisateur de base de données pour l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-140">Use this page to map logins to database user roles for the management data warehouse.</span></span>  
  
 <span data-ttu-id="7e252-141">**Utilisateurs mappés à cette connexion**</span><span class="sxs-lookup"><span data-stu-id="7e252-141">**Users mapped to this login**</span></span>  
 <span data-ttu-id="7e252-142">Affiche les connexions existantes sur le serveur qui hébergera l'entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-142">Displays the existing logins on the server that will host the management data warehouse.</span></span> <span data-ttu-id="7e252-143">Chaque ligne contient une case à cocher **Mappage** modifiable, un nom de **Connexion** et un **Type** de connexion.</span><span class="sxs-lookup"><span data-stu-id="7e252-143">Each row contains an editable **Map** check box, a **Login** name, and a **Type** of login.</span></span>  
  
 <span data-ttu-id="7e252-144">Spécifiez une connexion en activant la case à cocher **Mappage** pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="7e252-144">Specify a login by selecting the **Map** checkbox for the login.</span></span>  
  
 <span data-ttu-id="7e252-145">**Appartenance au rôle de base de données :**  *\<data warehouse name>*</span><span class="sxs-lookup"><span data-stu-id="7e252-145">**Database role membership for:**  *\<data warehouse name>*</span></span>  
 <span data-ttu-id="7e252-146">Sélectionnez le rôle d'entrepôt de données de gestion auquel la connexion est mappée en cliquant sur une ou plusieurs cases à cocher en regard des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="7e252-146">Select the management data warehouse role that the login is mapped to by clicking the checkbox by one or more of the following options:</span></span>  
  
-   <span data-ttu-id="7e252-147">**mdw_admin**</span><span class="sxs-lookup"><span data-stu-id="7e252-147">**mdw_admin**</span></span>  
  
-   <span data-ttu-id="7e252-148">**mdw_reader**</span><span class="sxs-lookup"><span data-stu-id="7e252-148">**mdw_reader**</span></span>  
  
-   <span data-ttu-id="7e252-149">**mdw_writer**</span><span class="sxs-lookup"><span data-stu-id="7e252-149">**mdw_writer**</span></span>  
  
 <span data-ttu-id="7e252-150">**Nouvelle connexion**</span><span class="sxs-lookup"><span data-stu-id="7e252-150">**New Login**</span></span>  
 <span data-ttu-id="7e252-151">Ouvrez la boîte de dialogue **Nouvelle connexion** et créez une connexion pour l’entrepôt de données de gestion.</span><span class="sxs-lookup"><span data-stu-id="7e252-151">Open the **Login - New** dialog box and create a new login for the management data warehouse.</span></span>  
  
 <span data-ttu-id="7e252-152">**Page Fin de l'Assistant**</span><span class="sxs-lookup"><span data-stu-id="7e252-152">**Complete the Wizard Page**</span></span>  
  
 <span data-ttu-id="7e252-153">Utilisez cette page pour vérifier et terminer la configuration de la collecte de données.</span><span class="sxs-lookup"><span data-stu-id="7e252-153">Use this page to verify and complete data collection configuration.</span></span> <span data-ttu-id="7e252-154">L'arborescence contenue dans la fenêtre d'affichage indique les configurations qui s'appliquent ainsi que les actions qui sont entreprises lorsque vous cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="7e252-154">The tree displayed in the viewing window shows what configurations will applied as well as what actions will take place when you click **Finish**.</span></span>  
  
 <span data-ttu-id="7e252-155">**Page Progression de l'Assistant Configuration de la collecte de données**</span><span class="sxs-lookup"><span data-stu-id="7e252-155">**Configure Data Collection Wizard Progress Page**</span></span>  
  
 <span data-ttu-id="7e252-156">Utilisez cette page pour consulter les résultats de chaque étape de configuration.</span><span class="sxs-lookup"><span data-stu-id="7e252-156">Use this page to view the results of each configuration step.</span></span>  
  
 <span data-ttu-id="7e252-157">**Détails**</span><span class="sxs-lookup"><span data-stu-id="7e252-157">**Details**</span></span>  
 <span data-ttu-id="7e252-158">Affiche chaque étape de configuration sous la forme d’une ligne dans la grille **Détails** .</span><span class="sxs-lookup"><span data-stu-id="7e252-158">Displays each configuration step as a row in the **Details** grid.</span></span> <span data-ttu-id="7e252-159">Chaque ligne contient une colonne **Action** qui décrit l'étape et une colonne **État** qui indique la réussite ou l'échec de l'étape.</span><span class="sxs-lookup"><span data-stu-id="7e252-159">Each row contains an **Action** column that describes the step, and a **Status** column that indicates the success or failure of the step.</span></span> <span data-ttu-id="7e252-160">En cas d'erreur, un message s'affiche dans la colonne **Message** .</span><span class="sxs-lookup"><span data-stu-id="7e252-160">If there is an error, a message appears in the **Message** column.</span></span>  
  
 <span data-ttu-id="7e252-161">**Stop**</span><span class="sxs-lookup"><span data-stu-id="7e252-161">**Stop**</span></span>  
 <span data-ttu-id="7e252-162">Arrête le traitement de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="7e252-162">Stop wizard processing.</span></span>  
  
 <span data-ttu-id="7e252-163">**Report**</span><span class="sxs-lookup"><span data-stu-id="7e252-163">**Report**</span></span>  
 <span data-ttu-id="7e252-164">Affiche un rapport de la configuration de la collecte de données.</span><span class="sxs-lookup"><span data-stu-id="7e252-164">View a report of the data collection configuration.</span></span> <span data-ttu-id="7e252-165">Les options de rapport suivantes sont fournies :</span><span class="sxs-lookup"><span data-stu-id="7e252-165">The following report options are provided:</span></span>  
  
-   <span data-ttu-id="7e252-166">Afficher le rapport</span><span class="sxs-lookup"><span data-stu-id="7e252-166">View Report</span></span>  
  
-   <span data-ttu-id="7e252-167">Enregistrer le rapport dans un fichier</span><span class="sxs-lookup"><span data-stu-id="7e252-167">Save Report to File</span></span>  
  
-   <span data-ttu-id="7e252-168">Copier le rapport dans le Presse-papiers</span><span class="sxs-lookup"><span data-stu-id="7e252-168">Copy Report to Clipboard</span></span>  
  
-   <span data-ttu-id="7e252-169">Envoyer le rapport sous forme de courrier électronique</span><span class="sxs-lookup"><span data-stu-id="7e252-169">Send Report as E-mail</span></span>  
  
 <span data-ttu-id="7e252-170">**Close**</span><span class="sxs-lookup"><span data-stu-id="7e252-170">**Close**</span></span>  
 <span data-ttu-id="7e252-171">Ferme l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="7e252-171">Close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e252-172">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e252-172">See Also</span></span>  
 <span data-ttu-id="7e252-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e252-173">[sp_syscollector_enable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-enable-collector-transact-sql) </span></span>  
 <span data-ttu-id="7e252-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="7e252-174">[sp_syscollector_disable_collector &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syscollector-disable-collector-transact-sql) </span></span>  
 <span data-ttu-id="7e252-175">[Collecte de données](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="7e252-175">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="7e252-176">Gérer la collecte de données</span><span class="sxs-lookup"><span data-stu-id="7e252-176">Manage Data Collection</span></span>](manage-data-collection.md)  
  
  
