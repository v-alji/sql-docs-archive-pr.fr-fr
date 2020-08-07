---
title: Créer un plan de maintenance (aire de conception de plan de maintenance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- Maintenance Plan Design Surface
ms.assetid: 2ef803ee-a9f8-454a-ad63-fedcbe6838d1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 77e347720824198ba7d6abaddedd7a581ace98a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612314"
---
# <a name="create-a-maintenance-plan-maintenance-plan-design-surface"></a><span data-ttu-id="64c7b-102">Créer un plan de maintenance (aire de conception de plan de maintenance)</span><span class="sxs-lookup"><span data-stu-id="64c7b-102">Create a Maintenance Plan (Maintenance Plan Design Surface)</span></span>
  <span data-ttu-id="64c7b-103">Cette rubrique explique comment créer un plan de maintenance de serveur unique ou multiserveur à l'aide de l'aire de conception de plan de maintenance de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="64c7b-103">This topic describes how to create a single server or multiserver maintenance plan using the Maintenance Plan Design Surface in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="64c7b-104">L' **Assistant Plan de maintenance** est conseillé pour créer des plans de maintenance de base, tandis que l'aire de conception permet d'utiliser un flux de travail optimisé.</span><span class="sxs-lookup"><span data-stu-id="64c7b-104">While the **Maintenance Plan Wizard** is best for creating basic maintenance plans, creating a plan using the design surface allows you to utilize enhanced workflow.</span></span>  
  
 <span data-ttu-id="64c7b-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="64c7b-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="64c7b-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="64c7b-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="64c7b-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="64c7b-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="64c7b-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="64c7b-108">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="64c7b-109">Création d'un plan de maintenance à l'aide de l'aire de conception de plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="64c7b-109">Creating a maintenance plan using the Maintenance Plan Design Surface</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="64c7b-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="64c7b-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="64c7b-111">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="64c7b-111">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="64c7b-112">Pour créer un plan de maintenance multiserveurs, vous devez configurer un environnement multiserveurs contenant un serveur maître et un ou plusieurs serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="64c7b-112">To create a multiserver maintenance plan, a multiserver environment containing one master server and one or more target servers must be configured.</span></span> <span data-ttu-id="64c7b-113">Les plans de maintenance multiserveurs doivent être créés et conservés sur le serveur maître.</span><span class="sxs-lookup"><span data-stu-id="64c7b-113">Multiserver maintenance plans must be created and maintained on the master server.</span></span> <span data-ttu-id="64c7b-114">Ces plans peuvent être consultés mais ne peuvent pas être conservés sur les serveurs cibles.</span><span class="sxs-lookup"><span data-stu-id="64c7b-114">These plans can be viewed, but not maintained, on target servers.</span></span>  
  
-   <span data-ttu-id="64c7b-115">Les membres du rôle **db_ssisadmin** et du rôle **dc_admin** peuvent être en mesure d’élever leurs privilèges à **sysadmin**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-115">Members of the **db_ssisadmin** and **dc_admin** roles may be able to elevate their privileges to **sysadmin**.</span></span> <span data-ttu-id="64c7b-116">Cette élévation de privilège est possible, car ces rôles peuvent modifier les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , qui sont exécutables par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le contexte de sécurité **sysadmin** de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="64c7b-116">This elevation of privilege can occur because these roles can modify [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages; these packages can be executed by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **sysadmin** security context of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="64c7b-117">Pour empêcher cette élévation de privilège durant l’exécution de plans de maintenance, de jeux d’éléments de collecte de données et d’autres packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] , configurez les travaux de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent qui exécutent des packages de façon à utiliser un compte proxy doté de privilèges limités ou ajoutez uniquement des membres **sysadmin** aux rôles **db_ssisadmin** et **dc_admin** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-117">To guard against this elevation of privilege when running maintenance plans, data collection sets, and other [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages, configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs that run packages to use a proxy account with limited privileges or only add **sysadmin** members to the **db_ssisadmin** and **dc_admin** roles.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="64c7b-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="64c7b-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="64c7b-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="64c7b-119">Permissions</span></span>  
 <span data-ttu-id="64c7b-120">Pour créer ou gérer des plans de maintenance, vous devez être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-120">To create or manage maintenance plans, you must be a member of the **sysadmin** fixed server role.</span></span> <span data-ttu-id="64c7b-121">L'Explorateur d'objets affiche uniquement le nœud **Plans de maintenance** pour les utilisateurs membres du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-121">Object Explorer only displays the **Maintenance Plans** node for users who are members of the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-maintenance-plan-design-surface"></a><a name="SSMSProcedure"></a> <span data-ttu-id="64c7b-122">Utilisation de l'aire de conception de plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="64c7b-122">Using Maintenance Plan Design Surface</span></span>  
  
#### <a name="to-create-a-maintenance-plan"></a><span data-ttu-id="64c7b-123">Pour créer un plan de maintenance</span><span class="sxs-lookup"><span data-stu-id="64c7b-123">To create a maintenance plan</span></span>  
  
1.  <span data-ttu-id="64c7b-124">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer un plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="64c7b-124">In Object Explorer, click the plus sign to expand the server where you want to create a maintenance plan.</span></span>  
  
2.  <span data-ttu-id="64c7b-125">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-125">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="64c7b-126">Cliquez avec le bouton droit sur le dossier **Plans de maintenance** et sélectionnez **Nouveau plan de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-126">Right-click the **Maintenance Plans** folder and select **New Maintenance Plan**.</span></span>  
  
4.  <span data-ttu-id="64c7b-127">Dans la boîte de dialogue **Nouveau plan de maintenance** , dans la zone **Nom** , tapez un nom pour le plan, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-127">In the **New Maintenance Plan** dialog box, in the **Name** box, type a name for the plan and click **OK**.</span></span> <span data-ttu-id="64c7b-128">Vous ouvrez ainsi la boîte à outils et l’aire _nom_plan_maintenance_ **[Conception]** avec le sous-plan **Sous-plan_1** créé dans la grille principale.</span><span class="sxs-lookup"><span data-stu-id="64c7b-128">This opens the  Toolbox and the _maintenance_plan_name_ **[Design]** surface with the **Subplan_1** subplan created in the main grid.</span></span>  
  
     <span data-ttu-id="64c7b-129">Les options suivantes sont disponibles dans l'en-tête de l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="64c7b-129">The following options are available in the design space's header.</span></span>  
  
     <span data-ttu-id="64c7b-130">**Ajouter le sous-plan**</span><span class="sxs-lookup"><span data-stu-id="64c7b-130">**Add Subplan**</span></span>  
     <span data-ttu-id="64c7b-131">Ajoute un sous-plan que vous pouvez configurer.</span><span class="sxs-lookup"><span data-stu-id="64c7b-131">Adds a subplan that you can configure.</span></span>  
  
     <span data-ttu-id="64c7b-132">**Propriétés du sous-plan**</span><span class="sxs-lookup"><span data-stu-id="64c7b-132">**Subplan Properties**</span></span>  
     <span data-ttu-id="64c7b-133">Affiche la boîte de dialogue **Propriétés du sous-plan** du sous-plan sélectionné dans la grille principale.</span><span class="sxs-lookup"><span data-stu-id="64c7b-133">Displays the **Subplan Properties** dialog box for the selected subplan in the main grid.</span></span> <span data-ttu-id="64c7b-134">Vous pouvez également double-cliquer sur un sous-plan dans la grille pour afficher la boîte de dialogue **Propriétés du sous-plan** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-134">Alternately, double-click a subplan in the grid to display the **Subplan Properties** dialog box.</span></span> <span data-ttu-id="64c7b-135">Pour plus d'informations sur cette boîte de dialogue, voir ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="64c7b-135">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="64c7b-136">**Supprimer le sous-plan sélectionné**</span><span class="sxs-lookup"><span data-stu-id="64c7b-136">**Delete Selected Subplan**</span></span>  
     <span data-ttu-id="64c7b-137">Supprime le sous-plan sélectionné.</span><span class="sxs-lookup"><span data-stu-id="64c7b-137">Deletes the selected subplan.</span></span>  
  
     <span data-ttu-id="64c7b-138">**Planification du sous-plan**</span><span class="sxs-lookup"><span data-stu-id="64c7b-138">**Subplan Schedule**</span></span>  
     <span data-ttu-id="64c7b-139">Affiche la boîte de dialogue **Nouvelle planification du travail** du sous-plan sélectionné.</span><span class="sxs-lookup"><span data-stu-id="64c7b-139">Displays the **New Job Schedule** dialog box for the selected subplan.</span></span>  
  
     <span data-ttu-id="64c7b-140">**Supprimer la planification**</span><span class="sxs-lookup"><span data-stu-id="64c7b-140">**Remove Schedule**</span></span>  
     <span data-ttu-id="64c7b-141">Supprime une planification du sous-plan sélectionné.</span><span class="sxs-lookup"><span data-stu-id="64c7b-141">Removes a schedule from the selected subplan.</span></span>  
  
     <span data-ttu-id="64c7b-142">**Gérer les connexions**</span><span class="sxs-lookup"><span data-stu-id="64c7b-142">**Manage Connections**</span></span>  
     <span data-ttu-id="64c7b-143">Affiche la boîte de dialogue **Gérer les connexions** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-143">Displays the **Manage Connections** dialog box.</span></span> <span data-ttu-id="64c7b-144">Permet d'ajouter des connexions d'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] supplémentaires au plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="64c7b-144">Used to add additional [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance connections to the maintenance plan.</span></span> <span data-ttu-id="64c7b-145">Pour plus d'informations sur cette boîte de dialogue, voir ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="64c7b-145">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="64c7b-146">**Création de rapport et enregistrement**</span><span class="sxs-lookup"><span data-stu-id="64c7b-146">**Reporting and Logging**</span></span>  
     <span data-ttu-id="64c7b-147">Affiche la boîte de dialogue **Création de rapport et enregistrement** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-147">Displays the **Reporting and Logging** dialog box.</span></span> <span data-ttu-id="64c7b-148">Pour plus d'informations sur cette boîte de dialogue, voir ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="64c7b-148">See below for more information on this dialog box.</span></span>  
  
     <span data-ttu-id="64c7b-149">**Serveurs**</span><span class="sxs-lookup"><span data-stu-id="64c7b-149">**Servers**</span></span>  
     <span data-ttu-id="64c7b-150">Affichez la boîte de dialogue **Serveurs** qui permet de sélectionner les serveurs où sont exécutées les tâches du sous-plan.</span><span class="sxs-lookup"><span data-stu-id="64c7b-150">Display the **Servers** dialog box, which is used to select the servers where the subplan tasks will be run.</span></span> <span data-ttu-id="64c7b-151">Cette option est activée uniquement sur des serveurs maîtres dans des environnements multiserveurs.</span><span class="sxs-lookup"><span data-stu-id="64c7b-151">This option is enabled only on master servers in multiserver environments.</span></span> <span data-ttu-id="64c7b-152">Pour plus d’informations, consultez [Créer un environnement multiserveur](../../ssms/agent/create-a-multiserver-environment.md) et [Plan de maintenance &#40;Serveurs&#41;](maintenance-plan-servers.md).</span><span class="sxs-lookup"><span data-stu-id="64c7b-152">For more information, see [Create a Multiserver Environment](../../ssms/agent/create-a-multiserver-environment.md) and [Maintenance Plan &#40;Servers&#41;](maintenance-plan-servers.md).</span></span>  
  
     <span data-ttu-id="64c7b-153">**Nom**</span><span class="sxs-lookup"><span data-stu-id="64c7b-153">**Name**</span></span>  
     <span data-ttu-id="64c7b-154">Affichez le nom du plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="64c7b-154">Display the maintenance plan name.</span></span> <span data-ttu-id="64c7b-155">Pour les nouveaux plans de maintenance, le nom est spécifié dans une boîte de dialogue avant l'ouverture du concepteur de plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="64c7b-155">For new maintenance plans, the name is specified in a dialog box before the maintenance plan designer opens.</span></span> <span data-ttu-id="64c7b-156">Pour renommer un plan de maintenance, cliquez dessus avec le bouton droit dans l’Explorateur d’objets, puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-156">To rename a maintenance plan, right-click the plan in Object Explorer, and then click **Rename**.</span></span>  
  
     <span data-ttu-id="64c7b-157">**Description**</span><span class="sxs-lookup"><span data-stu-id="64c7b-157">**Description**</span></span>  
     <span data-ttu-id="64c7b-158">Permet d'afficher ou de spécifier une description du plan de maintenance.</span><span class="sxs-lookup"><span data-stu-id="64c7b-158">View or specify a description for the maintenance plan.</span></span> <span data-ttu-id="64c7b-159">La longueur maximale de la description est 512 caractères.</span><span class="sxs-lookup"><span data-stu-id="64c7b-159">The maximum length for a description is 512 characters.</span></span>  
  
     <span data-ttu-id="64c7b-160">**Aire du concepteur**</span><span class="sxs-lookup"><span data-stu-id="64c7b-160">**Designer Surface**</span></span>  
     <span data-ttu-id="64c7b-161">Conception et entretien des plans de maintenance.</span><span class="sxs-lookup"><span data-stu-id="64c7b-161">Design and maintain maintenance plans.</span></span> <span data-ttu-id="64c7b-162">Utilisez l'aire du concepteur pour ajouter des tâches de maintenance à un plan, supprimer des tâches d'un plan, spécifier des liens de précédence entre des tâches et indiquer les branchements et le parallélisme des tâches.</span><span class="sxs-lookup"><span data-stu-id="64c7b-162">Use the designer surface to add maintenance tasks to a plan, remove tasks from a plan, specify precedence links between the tasks, and indicate task branching and parallelism.</span></span>  
  
     <span data-ttu-id="64c7b-163">Un lien de précédence entre deux tâches établit une relation entre ces tâches.</span><span class="sxs-lookup"><span data-stu-id="64c7b-163">A precedence link between two tasks establishes a relationship between the tasks.</span></span> <span data-ttu-id="64c7b-164">La seconde tâche (la *tâche dépendante*) s’exécute seulement si le résultat d’exécution de la première tâche (la *tâche prioritaire*) correspond aux critères spécifiés.</span><span class="sxs-lookup"><span data-stu-id="64c7b-164">The second task (the *dependent task*) executes only if the execution result of the first task (the *precedent task*) matches specified criteria.</span></span> <span data-ttu-id="64c7b-165">En général, le résultat d'exécution spécifié est **Succès**, **Échec**ou **À l'achèvement**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-165">Typically the execution result specified is **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="64c7b-166">Pour plus d'informations, consultez l'étape **8** ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="64c7b-166">For more information, see step **8** below.</span></span>  
  
5.  <span data-ttu-id="64c7b-167">Dans l’en-tête de l’aire de conception, double-cliquez sur **Sous-plan_1** et entrez un nom et une description pour le sous-plan dans la boîte de dialogue **Propriétés du sous-plan** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-167">In the design space's header, double-click **Subplan_1** and enter a name and description for the subplan in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="64c7b-168">Les options suivantes sont disponibles dans la boîte de dialogue **Propriétés du sous-plan** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-168">The following options are available in the **Subplan Properties** dialog box.</span></span>  
  
     <span data-ttu-id="64c7b-169">**Nom**</span><span class="sxs-lookup"><span data-stu-id="64c7b-169">**Name**</span></span>  
     <span data-ttu-id="64c7b-170">Nom du sous-plan.</span><span class="sxs-lookup"><span data-stu-id="64c7b-170">The name of the subplan.</span></span>  
  
     <span data-ttu-id="64c7b-171">**Description**</span><span class="sxs-lookup"><span data-stu-id="64c7b-171">**Description**</span></span>  
     <span data-ttu-id="64c7b-172">Brève description du sous-plan.</span><span class="sxs-lookup"><span data-stu-id="64c7b-172">A brief description of the subplan.</span></span>  
  
     <span data-ttu-id="64c7b-173">**Planification**</span><span class="sxs-lookup"><span data-stu-id="64c7b-173">**Schedule**</span></span>  
     <span data-ttu-id="64c7b-174">Indique pour quelle planification le sous-plan sera exécuté.</span><span class="sxs-lookup"><span data-stu-id="64c7b-174">Indicates on what schedule the subplan will be run.</span></span> <span data-ttu-id="64c7b-175">Cliquez sur **Planification du sous-plan** pour ouvrir la boîte de dialogue **Nouvelle planification du travail** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-175">Click **Subplan Schedule** to open the **New Job Schedule** dialog box.</span></span> <span data-ttu-id="64c7b-176">Cliquez sur **Supprimer la planification** pour supprimer la planification du sous-plan.</span><span class="sxs-lookup"><span data-stu-id="64c7b-176">Click **Remove Schedule** to delete the schedule from the subplan.</span></span>  
  
     <span data-ttu-id="64c7b-177">Liste**Exécuter en tant que**</span><span class="sxs-lookup"><span data-stu-id="64c7b-177">**Run as** list</span></span>  
     <span data-ttu-id="64c7b-178">Sélectionnez le compte à utiliser pour exécuter cette sous-tâche.</span><span class="sxs-lookup"><span data-stu-id="64c7b-178">Select the account to use to run this subtask.</span></span>  
  
6.  <span data-ttu-id="64c7b-179">Cliquez sur l'icône **Planification du sous-plan** pour entrer les informations de la planification dans la boîte de dialogue **Nouvelle planification du travail** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-179">Click **Subplan Schedule** to enter schedule details in the **New Job Schedule** dialog box.</span></span>  
  
7.  <span data-ttu-id="64c7b-180">Pour générer le sous-plan, faites glisser les éléments de flux des tâches de la **Boîte à outils** vers l'aire de conception du plan.</span><span class="sxs-lookup"><span data-stu-id="64c7b-180">To build the subplan, drag and drop task flow elements from the **Toolbox** to the plan design surface.</span></span> <span data-ttu-id="64c7b-181">Double-cliquez sur des tâches pour ouvrir les boîtes de dialogue permettant de configurer les options des tâches.</span><span class="sxs-lookup"><span data-stu-id="64c7b-181">Double-click tasks to open dialog boxes to configure the task options.</span></span>  
  
     <span data-ttu-id="64c7b-182">Les tâches de plan de maintenance suivantes sont disponibles dans la **Boîte à outils**:</span><span class="sxs-lookup"><span data-stu-id="64c7b-182">The following maintenance plan tasks are available in the **Toolbox**:</span></span>  
  
    -   <span data-ttu-id="64c7b-183">**Tâche Sauvegarder la base de données**</span><span class="sxs-lookup"><span data-stu-id="64c7b-183">**Back up Database Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-184">**Tâche Vérifier l'intégrité de la base de données**</span><span class="sxs-lookup"><span data-stu-id="64c7b-184">**Check Database Integrity Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-185">**Tâche Exécuter le travail de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="64c7b-185">**Execute SQL Server Agent Job Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-186">**Tâche Exécuter l'instruction T-SQL**</span><span class="sxs-lookup"><span data-stu-id="64c7b-186">**Execute T-SQL Statement Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-187">**Tâche de nettoyage d'historique**</span><span class="sxs-lookup"><span data-stu-id="64c7b-187">**History Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-188">**Tâche de nettoyage de maintenance**</span><span class="sxs-lookup"><span data-stu-id="64c7b-188">**Maintenance Cleanup Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-189">**Tâche Notifier l'opérateur**</span><span class="sxs-lookup"><span data-stu-id="64c7b-189">**Notify Operator Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-190">**Tâche Reconstruire l'index**</span><span class="sxs-lookup"><span data-stu-id="64c7b-190">**Rebuild Index Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-191">**Tâche Réorganiser l'index**</span><span class="sxs-lookup"><span data-stu-id="64c7b-191">**Reorganize Index Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-192">**Tâche Réduire la base de données**</span><span class="sxs-lookup"><span data-stu-id="64c7b-192">**Shrink Database Task**</span></span>  
  
    -   <span data-ttu-id="64c7b-193">**Tâche Mettre à jour les statistiques**</span><span class="sxs-lookup"><span data-stu-id="64c7b-193">**Update Statistics Task**</span></span>  
  
     <span data-ttu-id="64c7b-194">Pour ajouter des tâches à la **Boîte à outils**:</span><span class="sxs-lookup"><span data-stu-id="64c7b-194">To add tasks to the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="64c7b-195">Dans le menu **Outils** , cliquez sur **Choisir des éléments de boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-195">On the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="64c7b-196">Sélectionnez les outils que vous souhaitez voir afficher dans la **Boîte à outils**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-196">Select the tools you want to appear in the **Toolbox**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="64c7b-197">Les tâches de plan de maintenance que vous ajoutez à la **Boîte à outils** sont également disponibles dans l' **Assistant Plan de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-197">Adding maintenance plan tasks to the **Toolbox** also makes them available in the **Maintenance Plan Wizard**.</span></span> <span data-ttu-id="64c7b-198">Pour plus d’informations sur les différentes tâches présentées ci-dessus, consultez [Utilisation de l’Assistant Plan de maintenance](use-the-maintenance-plan-wizard.md#SSMSProcedure) sous **Démarrer l’Assistant Plan de maintenance**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-198">For more information on the individual tasks above, see [Using Maintenance Plan Wizard](use-the-maintenance-plan-wizard.md#SSMSProcedure) under **Start the Maintenance Plan Wizard**.</span></span>  
  
8.  <span data-ttu-id="64c7b-199">Pour définir un flux de travail entre les tâches :</span><span class="sxs-lookup"><span data-stu-id="64c7b-199">To define a workflow between tasks:</span></span>  
  
    1.  <span data-ttu-id="64c7b-200">Cliquez avec le bouton droit sur la tâche prioritaire et sélectionnez **Ajouter une contrainte de précédence**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-200">Right-click the precedent task and select **Add Precedence Constraint**.</span></span>  
  
    2.  <span data-ttu-id="64c7b-201">Dans la boîte de dialogue **Flux de contrôle** , dans la liste **À** , sélectionnez la tâche dépendante et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-201">In the **Control Flow** dialog box, in the **To** list, select the dependent task and click **OK**.</span></span>  
  
    3.  <span data-ttu-id="64c7b-202">Double-cliquez sur le connecteur entre les deux tâches pour ouvrir la boîte de dialogue **Éditeur de contrainte de précédence** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-202">Double click the connector between the two tasks to open the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="64c7b-203">Les options suivantes sont disponibles dans la boîte de dialogue **Éditeur de contrainte de précédence** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-203">The following options are available in the **Precedence Constraint Editor** dialog box.</span></span>  
  
         <span data-ttu-id="64c7b-204">**Option de contrainte**</span><span class="sxs-lookup"><span data-stu-id="64c7b-204">**Constraint option**</span></span>  
         <span data-ttu-id="64c7b-205">Définit la manière dont une contrainte fonctionne entre deux tâches.</span><span class="sxs-lookup"><span data-stu-id="64c7b-205">Defines how a constraint works between two tasks.</span></span>  
  
         <span data-ttu-id="64c7b-206">Liste**Opération d’évaluation**</span><span class="sxs-lookup"><span data-stu-id="64c7b-206">**Evaluation operation**  list</span></span>  
         <span data-ttu-id="64c7b-207">Spécifiez l'opération d'évaluation utilisée par la contrainte de précédence.</span><span class="sxs-lookup"><span data-stu-id="64c7b-207">Specify the evaluation operation that the precedence constraint uses.</span></span> <span data-ttu-id="64c7b-208">Ces opérations sont : **Contrainte**, **Expression**, **Expression et contrainte** et **Expression ou contrainte**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-208">The operations are: **Constraint**, **Expression**, **Expression and Constraint**, and **Expression or Constraint**.</span></span>  
  
         <span data-ttu-id="64c7b-209">Liste**Valeur**</span><span class="sxs-lookup"><span data-stu-id="64c7b-209">**Value** list</span></span>  
         <span data-ttu-id="64c7b-210">Spécifiez la valeur de contrainte : **Réussite**, **Échec** ou **À l'achèvement**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-210">Specify the constraint value: **Success**, **Failure**, or **Completion**.</span></span> <span data-ttu-id="64c7b-211">**Réussite** est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="64c7b-211">**Success** is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="64c7b-212">La ligne de contrainte de précédence est verte pour **Réussite**, rouge pour **Échec**et bleue pour **À l’achèvement**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-212">The precedence constraint line is green for **Success**, red for **Failure**, and blue for **Completion**.</span></span>  
  
         <span data-ttu-id="64c7b-213">**Expression**</span><span class="sxs-lookup"><span data-stu-id="64c7b-213">**Expression**</span></span>  
         <span data-ttu-id="64c7b-214">Si vous utilisez les opérations **Expression**, **Expression et contrainte**ou **Expression ou contrainte**, tapez une expression.</span><span class="sxs-lookup"><span data-stu-id="64c7b-214">If using the operations **Expression**, **Expression and Constraint**, or **Expression or Constraint**, type an expression.</span></span> <span data-ttu-id="64c7b-215">L'expression doit prendre une valeur de type Boolean.</span><span class="sxs-lookup"><span data-stu-id="64c7b-215">The expression must evaluate to a Boolean.</span></span>  
  
         <span data-ttu-id="64c7b-216">**Test**</span><span class="sxs-lookup"><span data-stu-id="64c7b-216">**Test**</span></span>  
         <span data-ttu-id="64c7b-217">Validez l'expression.</span><span class="sxs-lookup"><span data-stu-id="64c7b-217">Validate the expression.</span></span>  
  
         <span data-ttu-id="64c7b-218">**Contraintes multiples**</span><span class="sxs-lookup"><span data-stu-id="64c7b-218">**Multiple constraints**</span></span>  
         <span data-ttu-id="64c7b-219">Définissez la manière dont plusieurs contraintes interopèrent pour contrôler l'exécution de la tâche contrainte.</span><span class="sxs-lookup"><span data-stu-id="64c7b-219">Define how multiple constraints interoperate to control the execution of the constrained task.</span></span>  
  
         <span data-ttu-id="64c7b-220">**ET logique**</span><span class="sxs-lookup"><span data-stu-id="64c7b-220">**Logical AND**</span></span>  
         <span data-ttu-id="64c7b-221">Sélectionnez cette option pour spécifier que plusieurs contraintes de précédence sur le même exécutable doivent être évaluées ensemble.</span><span class="sxs-lookup"><span data-stu-id="64c7b-221">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="64c7b-222">Toutes les contraintes doivent prendre la valeur True.</span><span class="sxs-lookup"><span data-stu-id="64c7b-222">All constraints must evaluate to True.</span></span> <span data-ttu-id="64c7b-223">Cette option est celle par défaut.</span><span class="sxs-lookup"><span data-stu-id="64c7b-223">This option is the default.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="64c7b-224">Ce type de contrainte de précédence s'affiche sous forme de ligne pleine verte, rouge ou bleue.</span><span class="sxs-lookup"><span data-stu-id="64c7b-224">This type of precedence constraint appears as a solid green, red, or blue line.</span></span>  
  
         <span data-ttu-id="64c7b-225">**OU logique**</span><span class="sxs-lookup"><span data-stu-id="64c7b-225">**Logical OR**</span></span>  
         <span data-ttu-id="64c7b-226">Sélectionnez cette option pour spécifier que plusieurs contraintes de précédence sur le même exécutable doivent être évaluées ensemble.</span><span class="sxs-lookup"><span data-stu-id="64c7b-226">Select to specify that multiple precedence constraints on the same executable must be evaluated together.</span></span> <span data-ttu-id="64c7b-227">Au moins une contrainte doit prendre la valeur True.</span><span class="sxs-lookup"><span data-stu-id="64c7b-227">At least one constraint must evaluate to True.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="64c7b-228">Ce type de contrainte de précédence s'affiche sous forme de ligne pointillée verte, rouge ou bleue.</span><span class="sxs-lookup"><span data-stu-id="64c7b-228">This type of precedence constraint appears as a dotted green, red, or blue line.</span></span>  
  
9. <span data-ttu-id="64c7b-229">Pour ajouter un autre sous-plan qui contient les tâches exécutées sur une autre planification, cliquez sur **Ajouter un sous-plan** dans la barre d'outils pour ouvrir la boîte de dialogue **Propriétés du sous-plan** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-229">To add another subplan that contains tasks run on a different schedule, click **Add Subplan** on the toolbar to open the **Subplan Properties** dialog box.</span></span>  
  
10. <span data-ttu-id="64c7b-230">Pour ajouter des connexions à d'autres serveurs :</span><span class="sxs-lookup"><span data-stu-id="64c7b-230">To add connections to different servers:</span></span>  
  
    1.  <span data-ttu-id="64c7b-231">Dans la barre d'outils de l'aire de conception, cliquez sur **Gérer les connexions**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-231">In the design space's toolbar, click **Manage Connections**.</span></span>  
  
    2.  <span data-ttu-id="64c7b-232">Dans la boîte de dialogue **Gérer les connexions** , cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-232">In the **Manage Connections** dialog box, click **Add**.</span></span>  
  
    3.  <span data-ttu-id="64c7b-233">Dans la boîte de dialogue **Propriétés de connexion** , dans la zone **Nom de la connexion** , entrez le nom de la connexion que vous créez.</span><span class="sxs-lookup"><span data-stu-id="64c7b-233">In the **Connection Properties** dialog box, in the **Connection name** box, enter the name of the connection you are creating.</span></span>  
  
    4.  <span data-ttu-id="64c7b-234">Sous **Spécifiez les éléments suivants pour vous connecter aux données de SQL Server**, dans la zone **Sélectionnez ou entrez un nom de serveur**, entrez le nom du serveur SQL Server à utiliser ou cliquez sur les points de suspension **(…)** et sélectionnez un serveur dans la boîte de dialogue **SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-234">Under **Specify the following to connect to SQL Server data**, in the **Select or enter a server name** box, either enter the name of the SQL server you want to use or click the ellipsis **(...)** and select a server in the **SQL Server** dialog box.</span></span> <span data-ttu-id="64c7b-235">Si vous sélectionnez un serveur dans la boîte de dialogue **SQL Server** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-235">If you select a server from the **SQL Server** dialog box, click **OK**.</span></span>  
  
    5.  <span data-ttu-id="64c7b-236">Sous **Entrez des informations pour vous connecter au serveur**, sélectionnez **Utiliser la sécurité intégrée de Windows NT** ou **Utiliser un nom d'utilisateur et un mot de passe spécifiques**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-236">Under **Enter information to log on to the server**, select either **Use Windows NT Integrated security** or **Use a specific user name and password**.</span></span> <span data-ttu-id="64c7b-237">Si vous choisissez d'utiliser un nom d'utilisateur et un mot de passe spécifiques, entrez ces informations dans les zones **Nom d'utilisateur** et **Mot de passe** , respectivement.</span><span class="sxs-lookup"><span data-stu-id="64c7b-237">If you elect to use a specific user name and password, enter that information in the **User name** and **Password** boxes, respectively.</span></span>  
  
    6.  <span data-ttu-id="64c7b-238">Dans la boîte de dialogue **Propriétés de connexion** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-238">In the **Connection Properties** dialog box, click **OK**.</span></span>  
  
    7.  <span data-ttu-id="64c7b-239">Dans la boîte de dialogue **Gérer les connexions** , cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-239">In the **Manage Connections** dialog box, click **Close**.</span></span>  
  
11. <span data-ttu-id="64c7b-240">Pour spécifier des options de création de rapports :</span><span class="sxs-lookup"><span data-stu-id="64c7b-240">To specify reporting options:</span></span>  
  
    1.  <span data-ttu-id="64c7b-241">Dans la barre d'outils de l'aire de conception, cliquez sur **Création de rapport et enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-241">In the design space's toolbar, click **Reporting and Logging**.</span></span>  
  
    2.  <span data-ttu-id="64c7b-242">Dans la boîte de dialogue **Création de rapport et enregistrement** , sous **Création de rapports**, sélectionnez **Générer un rapport de fichier texte** ou **Envoyer le rapport à un destinataire de messagerie** ou les deux.</span><span class="sxs-lookup"><span data-stu-id="64c7b-242">In the **Reporting and Logging** dialog box, under **Reporting**, select **Generate a text file report** or **Send report to an email recipient** or both.</span></span>  
  
        1.  <span data-ttu-id="64c7b-243">Si vous sélectionnez **Générer un rapport de fichier texte**, sélectionnez **Créer un nouveau fichier** ou **Ajouter au fichier**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-243">If you select **Generate a text file report**, select either **Create a new file** or **Append to file**.</span></span>  
  
        2.  <span data-ttu-id="64c7b-244">En fonction de la sélection ci-dessus, entrez le nom et le chemin complet du nouveau fichier ou du fichier à ajouter dans les zones **Dossier** ou **Nom de fichier** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-244">Depending on the selection above, enter the name and full path of the new file or file to be appended by entering the information in the **Folder** or **File name** boxes.</span></span> <span data-ttu-id="64c7b-245">Vous pouvez également cliquer sur les points de suspension **(...)** et sélectionner le chemin d’accès au dossier ou au nom de fichier dans les boîtes de dialogue **localiser le dossier-**_SERVER_NAME_ ou **Rechercher les fichiers de base de données-**_SERVER_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="64c7b-245">Alternately, click on the ellipsis **(...)** and select the path to the folder or file name from the **Locate Folder -**_server_name_ or **Locate Database Files -**_server_name_ dialog boxes.</span></span>  
  
        3.  <span data-ttu-id="64c7b-246">Si vous sélectionnez **Envoyer le rapport à un destinataire de messagerie**, dans la liste **Opérateur d'agent** , sélectionnez le destinataire du rapport envoyé par messagerie électronique.</span><span class="sxs-lookup"><span data-stu-id="64c7b-246">If you select **Send report to an email recipient**, on the **Agent operator** list, select the recipient of the emailed report.</span></span>  
  
            > [!NOTE]  
            >  <span data-ttu-id="64c7b-247">L'Agent SQL Server doit être configuré pour utiliser la messagerie de base de données afin d'envoyer le message.</span><span class="sxs-lookup"><span data-stu-id="64c7b-247">SQL Server Agent must be configured to use Database Mail in order to send mail.</span></span> <span data-ttu-id="64c7b-248">Pour plus d'informations, consultez [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span><span class="sxs-lookup"><span data-stu-id="64c7b-248">For more information, see [Configure SQL Server Agent Mail to Use Database Mail](../database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)</span></span>  
  
    3.  <span data-ttu-id="64c7b-249">Pour enregistrer des informations plus détaillées, sous **Enregistrement**, sélectionnez **Enregistrer les informations étendues**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-249">To save more detailed information, under **Logging**, select **Log extended information**.</span></span>  
  
    4.  <span data-ttu-id="64c7b-250">Pour écrire les informations de résultats de plan de maintenance sur un autre serveur, sélectionnez **Se connecter à un serveur distant** , puis sélectionnez une connexion au serveur dans la liste **Connexion** , ou cliquez sur **Nouveau** pour entrer les informations de connexion dans la boîte de dialogue **Propriétés de connexion** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-250">To write maintenance plan results information to another server, select **Log to remote server** and either select a server connection from the **Connection** list or click **New** and enter the connection information in the **Connection Properties** dialog box.</span></span>  
  
    5.  <span data-ttu-id="64c7b-251">Dans la boîte de dialogue **Création de rapport et enregistrement** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-251">In the **Reporting and Logging** dialog box, click **OK**.</span></span>  
  
12. <span data-ttu-id="64c7b-252">Pour consulter les résultats dans la visionneuse du fichier journal, dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur le dossier **Plans de maintenance** ou sur le plan de maintenance spécifique et sélectionnez **Afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-252">To view the results in the log file viewer, in **Object Explorer**, right-click either the **Maintenance Plans** folder or the specific maintenance plan and select **View History**.</span></span>  
  
     <span data-ttu-id="64c7b-253">Les options suivantes sont disponibles dans la boîte de dialogue **visionneuse du fichier journal-**_SERVER_NAME_ .</span><span class="sxs-lookup"><span data-stu-id="64c7b-253">The following options are available on the **Log File Viewer -**_server_name_ dialog box.</span></span>  
  
     <span data-ttu-id="64c7b-254">**Charger le journal**</span><span class="sxs-lookup"><span data-stu-id="64c7b-254">**Load Log**</span></span>  
     <span data-ttu-id="64c7b-255">Ouvre une boîte de dialogue dans laquelle vous pouvez spécifier un fichier journal à charger.</span><span class="sxs-lookup"><span data-stu-id="64c7b-255">Open a dialog box where you can specify a log file to load.</span></span>  
  
     <span data-ttu-id="64c7b-256">**Export**</span><span class="sxs-lookup"><span data-stu-id="64c7b-256">**Export**</span></span>  
     <span data-ttu-id="64c7b-257">Ouvre une boîte de dialogue qui vous permet d’exporter les informations figurant dans la grille **Résumé du fichier journal** vers un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="64c7b-257">Open a dialog box that lets you export the information that is shown in the **Log file summary** grid to a text file.</span></span>  
  
     <span data-ttu-id="64c7b-258">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="64c7b-258">**Refresh**</span></span>  
     <span data-ttu-id="64c7b-259">Actualise l'affichage des journaux sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="64c7b-259">Refresh the view of the selected logs.</span></span> <span data-ttu-id="64c7b-260">Le bouton **Actualiser** permet de relire les journaux sélectionnés à partir du serveur cible lors de l'application des paramètres de filtre.</span><span class="sxs-lookup"><span data-stu-id="64c7b-260">The **Refresh** button rereads the selected logs from the target server while applying any filter settings.</span></span>  
  
     <span data-ttu-id="64c7b-261">**Filter**</span><span class="sxs-lookup"><span data-stu-id="64c7b-261">**Filter**</span></span>  
     <span data-ttu-id="64c7b-262">Ouvre une boîte de dialogue qui vous permet de spécifier les paramètres utilisés pour filtrer le fichier journal, notamment **Connexion**, **Date**et d’autres critères de filtre **Général** .</span><span class="sxs-lookup"><span data-stu-id="64c7b-262">Open a dialog box that lets you specify settings that are used to filter the log file, such as **Connection**, **Date**, or other **General** filter criteria.</span></span>  
  
     <span data-ttu-id="64c7b-263">**action**</span><span class="sxs-lookup"><span data-stu-id="64c7b-263">**Search**</span></span>  
     <span data-ttu-id="64c7b-264">Permet de rechercher un texte spécifique dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="64c7b-264">Search the log file for specific text.</span></span> <span data-ttu-id="64c7b-265">La recherche des caractères génériques n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="64c7b-265">Searching with wildcard characters is not supported.</span></span>  
  
     <span data-ttu-id="64c7b-266">**Stop**</span><span class="sxs-lookup"><span data-stu-id="64c7b-266">**Stop**</span></span>  
     <span data-ttu-id="64c7b-267">Arrête le chargement des entrées du fichier-journal.</span><span class="sxs-lookup"><span data-stu-id="64c7b-267">Stops loading the log file entries.</span></span> <span data-ttu-id="64c7b-268">Par exemple, vous pouvez utiliser cette option si un fichier de journal distant ou hors connexion est long à charger, et que vous souhaitez seulement consulter les entrées les plus récentes.</span><span class="sxs-lookup"><span data-stu-id="64c7b-268">For example, you can use this option if a remote or offline log file takes a long time to load, and you only want to view the most recent entries.</span></span>  
  
     <span data-ttu-id="64c7b-269">**Résumé du fichier journal**</span><span class="sxs-lookup"><span data-stu-id="64c7b-269">**Log file summary**</span></span>  
     <span data-ttu-id="64c7b-270">Ce volet d'informations affiche un résumé du filtrage du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="64c7b-270">This information panel displays a summary of the log file filtering.</span></span> <span data-ttu-id="64c7b-271">Si le fichier n'est pas filtré, le texte suivant s'affiche : **Aucun filtre appliqué**.</span><span class="sxs-lookup"><span data-stu-id="64c7b-271">If the file is not filtered, you will see the following text, **No filter applied**.</span></span> <span data-ttu-id="64c7b-272">Si un filtre est appliqué au journal, le texte suivant s’affiche : **Filtrer les entrées du journal pour :** \<filter criteria>.</span><span class="sxs-lookup"><span data-stu-id="64c7b-272">If a filter is applied to the log, you will see the following text, **Filter log entries where:** \<filter criteria>.</span></span>  
  
     <span data-ttu-id="64c7b-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="64c7b-273">**Date**</span></span>  
     <span data-ttu-id="64c7b-274">Affiche la date de l'événement.</span><span class="sxs-lookup"><span data-stu-id="64c7b-274">Displays the date of the event.</span></span>  
  
     <span data-ttu-id="64c7b-275">**Source**</span><span class="sxs-lookup"><span data-stu-id="64c7b-275">**Source**</span></span>  
     <span data-ttu-id="64c7b-276">Affiche la fonctionnalité source à partir de laquelle l'événement est créé, par exemple le nom du service (comme MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="64c7b-276">Displays the source feature from which the event is created, such as the name of the service (MSSQLSERVER, for example).</span></span> <span data-ttu-id="64c7b-277">Ceci n'apparaît pas pour tous les types de journaux.</span><span class="sxs-lookup"><span data-stu-id="64c7b-277">This does not appear for all log types.</span></span>  
  
     <span data-ttu-id="64c7b-278">**Message**</span><span class="sxs-lookup"><span data-stu-id="64c7b-278">**Message**</span></span>  
     <span data-ttu-id="64c7b-279">Affiche les messages associés à l'événement.</span><span class="sxs-lookup"><span data-stu-id="64c7b-279">Displays any messages associated with the event.</span></span>  
  
     <span data-ttu-id="64c7b-280">**Type de journal**</span><span class="sxs-lookup"><span data-stu-id="64c7b-280">**Log Type**</span></span>  
     <span data-ttu-id="64c7b-281">Affiche le type de journal auquel appartient l'événement.</span><span class="sxs-lookup"><span data-stu-id="64c7b-281">Displays the type of log to which the event belongs.</span></span> <span data-ttu-id="64c7b-282">Tous les journaux sélectionnés s'affichent dans la fenêtre de résumé du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="64c7b-282">All selected logs appear in the log file summary window.</span></span>  
  
     <span data-ttu-id="64c7b-283">**Source du journal**</span><span class="sxs-lookup"><span data-stu-id="64c7b-283">**Log Source**</span></span>  
     <span data-ttu-id="64c7b-284">Affiche une description du journal source dans lequel l'événement est capturé.</span><span class="sxs-lookup"><span data-stu-id="64c7b-284">Displays a description of the source log in which the event is captured.</span></span>  
  
     <span data-ttu-id="64c7b-285">**Détails de la ligne sélectionnée**</span><span class="sxs-lookup"><span data-stu-id="64c7b-285">**Selected row details**</span></span>  
     <span data-ttu-id="64c7b-286">Sélectionnez une ligne pour afficher des détails supplémentaires sur la ligne d'événement sélectionnée en bas de la page.</span><span class="sxs-lookup"><span data-stu-id="64c7b-286">Select a row to display additional details about the selected event row at the bottom of the page.</span></span> <span data-ttu-id="64c7b-287">Vous pouvez changer l'ordre des colonnes en les faisant glisser sur la grille.</span><span class="sxs-lookup"><span data-stu-id="64c7b-287">The columns can be reordered by dragging them to new locations in the grid.</span></span> <span data-ttu-id="64c7b-288">Vous pouvez redimensionner les colonnes en faisant glisser les barres de séparation des colonnes dans l'en-tête de la grille vers la gauche ou la droite.</span><span class="sxs-lookup"><span data-stu-id="64c7b-288">The columns can be resized by dragging the column separator bars in the grid header to the left or right.</span></span> <span data-ttu-id="64c7b-289">Double-cliquez sur les barres de séparation des colonnes dans l'en-tête de la grille pour ajuster automatiquement la largeur de la colonne au contenu.</span><span class="sxs-lookup"><span data-stu-id="64c7b-289">Double-click the column separator bars in the grid header to automatically size the column to the content width.</span></span>  
  
     <span data-ttu-id="64c7b-290">**Instance**</span><span class="sxs-lookup"><span data-stu-id="64c7b-290">**Instance**</span></span>  
     <span data-ttu-id="64c7b-291">Nom de l'instance pour laquelle l'événement s'est produit.</span><span class="sxs-lookup"><span data-stu-id="64c7b-291">The name of the instance on which the event occurred.</span></span> <span data-ttu-id="64c7b-292">Il est affiché sous la forme *nom de l'ordinateur*\\*nom de l'instance*.</span><span class="sxs-lookup"><span data-stu-id="64c7b-292">This is displayed as *computer name*\\*instance name*.</span></span>  
  
  
