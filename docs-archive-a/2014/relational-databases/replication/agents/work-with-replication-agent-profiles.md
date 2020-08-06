---
title: Utiliser des profils d’Agent de réplication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], agents and profiles
- replication agent profiles [SQL Server]
- agents [SQL Server replication], profiles
- profiles [SQL Server], replication agents
ms.assetid: 9c290a88-4e9f-4a7e-aab5-4442137a9918
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fc20451edfb1096fca7e468effb14df78b51f758
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601393"
---
# <a name="work-with-replication-agent-profiles"></a><span data-ttu-id="0d90a-102">Utiliser des profils d'agent de réplication</span><span class="sxs-lookup"><span data-stu-id="0d90a-102">Work with Replication Agent Profiles</span></span>
  <span data-ttu-id="0d90a-103">Cette rubrique explique comment utiliser les profils de l'Agent de réplication dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], de [!INCLUDE[tsql](../../../includes/tsql-md.md)]ou d'objets RMO (Replication Management Objects).</span><span class="sxs-lookup"><span data-stu-id="0d90a-103">This topic describes how to work with Replication Agent Profiles in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../../includes/tsql-md.md)], or Replication Management Objects (RMO).</span></span> <span data-ttu-id="0d90a-104">Le comportement de chaque agent de réplication est contrôlé par un jeu de paramètres que vous pouvez configurer dans un profil de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-104">The behavior of each replication agent is controlled by a set of parameters that can be set through agent profiles.</span></span> <span data-ttu-id="0d90a-105">Chaque agent possède un profil par défaut et certains possèdent d'autres profils prédéfinis ; un Agent ne peut avoir qu'un profil actif à tout moment.</span><span class="sxs-lookup"><span data-stu-id="0d90a-105">Each agent has a default profile, and some have additional predefined profiles; at a given time, only one profile is active for an agent.</span></span>  
  
 <span data-ttu-id="0d90a-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0d90a-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0d90a-107">**Pour utiliser les profils de l'Agent de réplication à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="0d90a-107">**To work with Replication Agent Profiles, using:**</span></span>  
  
     [<span data-ttu-id="0d90a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d90a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
    -   <span data-ttu-id="0d90a-109">Accéder à la boîte de dialogue Profils de l'Agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-109">Access the Agent Profiles dialog box</span></span>  
  
    -   <span data-ttu-id="0d90a-110">Spécifier un profil d'Agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-110">Specify a profile for an agent</span></span>  
  
    -   <span data-ttu-id="0d90a-111">Créer un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-111">Create a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-112">Modifier un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-112">Modify a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-113">Supprimer un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-113">Delete a profile</span></span>  
  
     [<span data-ttu-id="0d90a-114">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d90a-114">Transact-SQL</span></span>](#TsqlProcedure)  
  
    -   <span data-ttu-id="0d90a-115">Créer un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-115">Create a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-116">Modifier un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-116">Modify a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-117">Supprimer un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-117">Delete a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-118">Utiliser des profils d'Agent pendant la synchronisation</span><span class="sxs-lookup"><span data-stu-id="0d90a-118">Use agent profiles during synchronization</span></span>  
  
    -   <span data-ttu-id="0d90a-119">Exemple Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d90a-119">Transact-SQL example</span></span>  
  
     [<span data-ttu-id="0d90a-120">Replication Management Objects</span><span class="sxs-lookup"><span data-stu-id="0d90a-120">Replication Management Objects</span></span>](#RMOProcedure)  
  
    -   <span data-ttu-id="0d90a-121">Créer un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-121">Create a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-122">Modifier un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-122">Modify a profile</span></span>  
  
    -   <span data-ttu-id="0d90a-123">Supprimer un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-123">Delete a profile</span></span>  
  
-   <span data-ttu-id="0d90a-124">**Suivi :**  [Après avoir changé les paramètres de l’Agent](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="0d90a-124">**Follow Up:**  [After Changing Agent Parameters](#FollowUp)</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0d90a-125">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d90a-125">Using SQL Server Management Studio</span></span>  
  
###  <a name="to-access-the-agent-profiles-dialog-box-from-sql-server-management-studio"></a><a name="Access_SSMS"></a> <span data-ttu-id="0d90a-126">Pour accéder à la boîte de dialogue Profils d'Agent à partir de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0d90a-126">To access the Agent Profiles dialog box from SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="0d90a-127">Dans la page **Général** de la boîte de dialogue **Propriétés du serveur de distribution - \<Distributor>** , cliquez sur **Profils par défaut**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-127">On the **General** page of the **Distributor Properties - \<Distributor>** dialog box, click **Profile Defaults**.</span></span>  
  
#### <a name="to-access-the-agent-profiles-dialog-box-from-replication-monitor"></a><span data-ttu-id="0d90a-128">Pour accéder à la boîte de dialogue Profils d'Agent à partir du moniteur de réplication</span><span class="sxs-lookup"><span data-stu-id="0d90a-128">To access the Agent Profiles dialog box from Replication Monitor</span></span>  
  
-   <span data-ttu-id="0d90a-129">Pour ouvrir la boîte de dialogue relative à tous les Agents, cliquez avec le bouton droit sur un serveur de publication puis cliquez sur **Profils d'Agent**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-129">To open the dialog box for all agents, right-click a Publisher, and then click **Agent Profiles**.</span></span>  
  
-   <span data-ttu-id="0d90a-130">Pour ouvrir la boîte de dialogue d'un seul Agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-130">To open the dialog box for a single agent:</span></span>  
  
    1.  <span data-ttu-id="0d90a-131">Développez un groupe Serveur de publication dans le volet gauche du moniteur de réplication, développez un serveur de publication puis cliquez sur une publication.</span><span class="sxs-lookup"><span data-stu-id="0d90a-131">Expand a Publisher group in the left pane of Replication Monitor, expand a Publisher, and then click a publication.</span></span>  
  
    2.  <span data-ttu-id="0d90a-132">Pour les profils de l'Agent de distribution et de l'Agent de fusion, cliquez avec le bouton droit sur un abonnement dans l'onglet **Tous les abonnements** puis cliquez sur **Profil de l'Agent**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-132">For Distribution Agent and Merge Agent profiles, right-click a subscription on the **All Subscriptions** tab, and then click **Agent Profile**.</span></span> <span data-ttu-id="0d90a-133">Pour les autres agents, cliquez avec le bouton droit sur l'agent sous l'onglet **Agents** , puis cliquez sur **Profil d'agent**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-133">For other agents, right-click the agent on the **Agents** tab, and then click **Agent Profile**.</span></span>  
  
###  <a name="to-specify-a-profile-for-an-agent"></a><a name="Specify_SSMS"></a> <span data-ttu-id="0d90a-134">Pour spécifier un profil d'un Agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-134">To specify a profile for an agent</span></span>  
  
1.  <span data-ttu-id="0d90a-135">Si la boîte de dialogue **Profils d'Agent** affiche les profils de plusieurs agents, sélectionnez un Agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-135">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="0d90a-136">Sélectionnez un profil dans la colonne **Valeur par défaut pour nouveau** de la grille **Profils d'Agent** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-136">Select a profile in the **Default for new** column of the **Agent profiles** grid.</span></span> <span data-ttu-id="0d90a-137">Par défaut, le profil est uniquement appliqué aux agents pour les nouveaux abonnements et publications.</span><span class="sxs-lookup"><span data-stu-id="0d90a-137">By default, the profile is only applied to agents for new publications and subscriptions.</span></span>  
  
3.  <span data-ttu-id="0d90a-138">Pour que tous les agents du type sélectionné pour les abonnements ou publications existants utilisent ce profil, cliquez sur **Modifier les Agents existants**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-138">To specify that all agents of the selected type for existing publications or subscriptions should use this profile, click **Change existing agents**.</span></span>  
  
###  <a name="to-view-and-edit-the-parameters-associated-with-a-profile"></a><a name="Modify_SSMS"></a> <span data-ttu-id="0d90a-139">Pour afficher et modifier les paramètres associés à un profil</span><span class="sxs-lookup"><span data-stu-id="0d90a-139">To view and edit the parameters associated with a profile</span></span>  
  
1.  <span data-ttu-id="0d90a-140">Si la boîte de dialogue **Profils d'Agent** affiche les profils de plusieurs agents, sélectionnez un Agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-140">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="0d90a-141">Cliquez sur le bouton des propriétés ( **...** ) en regard d’un profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-141">Click the properties button (**...**) next to a profile.</span></span>  
  
3.  <span data-ttu-id="0d90a-142">Affichez les paramètres et les valeurs dans la boîte de dialogue **Propriétés du profil \<ProfileName>** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-142">View the parameters and values in the **\<ProfileName> Profile Properties** dialog box.</span></span>  
  
    -   <span data-ttu-id="0d90a-143">Les paramètres des profils définis par l'utilisateur peuvent être modifiés, ce qui n'est pas le cas des profils système prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="0d90a-143">Parameters in user-defined profiles can be edited; parameters in predefined system profiles cannot.</span></span>  
  
    -   <span data-ttu-id="0d90a-144">Pour afficher tous les paramètres relatifs à un Agent, désactivez la case à cocher **Afficher uniquement les paramètres utilisés dans ce profil** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-144">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="0d90a-145">Pour plus d'informations sur les paramètres des Agents, consultez les liens à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="0d90a-145">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
4.  <span data-ttu-id="0d90a-146">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-146">Click **Close**.</span></span>  
  
###  <a name="to-create-a-user-defined-profile"></a><a name="Create_SSMS"></a> <span data-ttu-id="0d90a-147">Pour créer un profil défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d90a-147">To create a user-defined profile</span></span>  
  
1.  <span data-ttu-id="0d90a-148">Si la boîte de dialogue **Profils d'Agent** affiche les profils de plusieurs agents, sélectionnez un Agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-148">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="0d90a-149">Cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-149">Click **New**.</span></span>  
  
3.  <span data-ttu-id="0d90a-150">Dans la boîte de dialogue d'initialisation **Nouveau profil de l'Agent** , sélectionnez un profil existant qui servira de base au nouveau profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-150">In the **New Agent Profile** initialization dialog box, select an existing profile on which to base the new profile.</span></span>  
  
4.  <span data-ttu-id="0d90a-151">Dans la boîte de dialogue **Nouveau profil de l'Agent** , entrez des valeurs dans les zones de texte **Nom** et **Description** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-151">In the **New Agent Profile** dialog box, enter values in the **Name** and **Description** text boxes.</span></span>  
  
5.  <span data-ttu-id="0d90a-152">Modifiez les paramètres pour adapter le profil à vos besoins.</span><span class="sxs-lookup"><span data-stu-id="0d90a-152">Modify parameters to tailor the profile.</span></span> <span data-ttu-id="0d90a-153">Pour afficher tous les paramètres relatifs à un Agent, désactivez la case à cocher **Afficher uniquement les paramètres utilisés dans ce profil** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-153">To view all parameters for an agent, clear the **Show only parameters used in this profile** check box.</span></span> <span data-ttu-id="0d90a-154">Pour plus d'informations sur les paramètres des Agents, consultez les liens à la fin de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="0d90a-154">For information about agent parameters, see the links at the end of this topic.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
###  <a name="to-delete-a-user-defined-profile"></a><a name="Delete_SSMS"></a> <span data-ttu-id="0d90a-155">Pour supprimer un profil défini par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0d90a-155">To delete a user-defined profile</span></span>  
  
1.  <span data-ttu-id="0d90a-156">Si la boîte de dialogue **Profils d'Agent** affiche les profils de plusieurs agents, sélectionnez un Agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-156">If the **Agent Profiles** dialog box displays profiles for more than one agent, select an agent.</span></span>  
  
2.  <span data-ttu-id="0d90a-157">Si un profil est associé à un ou plusieurs agents, modifiez le profil de ceux-ci :</span><span class="sxs-lookup"><span data-stu-id="0d90a-157">If a profile is associated with one or more agents, change the profile for those agents:</span></span>  
  
    1.  <span data-ttu-id="0d90a-158">Sélectionnez un autre profil dans la grille **Profils d'Agent** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-158">Select a different profile in the **Agent profiles** grid.</span></span>  
  
    2.  <span data-ttu-id="0d90a-159">Cliquez sur **Modifier les Agents existants**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-159">Click **Change existing agents**.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0d90a-160">Cela modifie le profil de tous les agents du type sélectionné pour les publications ou abonnements existants et pas seulement ceux qui utilisent le profil à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0d90a-160">This will change the profile for all agents of the selected type for existing publications or subscriptions, not only the ones using the profile you want to delete.</span></span>  
  
3.  <span data-ttu-id="0d90a-161">Cliquez sur le profil à supprimer, puis sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-161">Select the profile you want to delete, and then click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0d90a-162">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0d90a-162">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_tsql"></a> <span data-ttu-id="0d90a-163">Pour créer un profil d'agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-163">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="0d90a-164">Sur le serveur de distribution, exécutez [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-164">At the Distributor, execute [sp_add_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql).</span></span> <span data-ttu-id="0d90a-165">Spécifiez **@name** , la valeur **1** pour **@profile_type** et l’une des valeurs suivantes pour **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="0d90a-165">Specify **@name**, a value of **1** for **@profile_type**, and one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="0d90a-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-166">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-167">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-168">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-169">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-170">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="0d90a-171">Si ce profil devient le nouveau profil par défaut pour son type d'agent de réplication, spécifiez une valeur de **1** pour **@default**.</span><span class="sxs-lookup"><span data-stu-id="0d90a-171">If this profile will become the new default profile for its type of replication agent, specify a value of **1** for **@default**.</span></span> <span data-ttu-id="0d90a-172">L’identificateur pour le nouveau profil est retourné à l’aide du **@profile_id** paramètre de sortie.</span><span class="sxs-lookup"><span data-stu-id="0d90a-172">The identifier for the new profile is returned using the **@profile_id** output parameter.</span></span> <span data-ttu-id="0d90a-173">Cela crée un nouveau profil avec un jeu de paramètres de profil basé sur le profil par défaut pour le type d'agent donné.</span><span class="sxs-lookup"><span data-stu-id="0d90a-173">This creates a new profile with a set of profile parameters based on the default profile for the given agent type.</span></span>  
  
2.  <span data-ttu-id="0d90a-174">Après avoir créé le nouveau profil, ajoutez, supprimez ou modifiez les paramètres par défaut pour personnaliser le profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-174">After the new profile has been created, add, remove, or modify the default parameters to customize the profile.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_tsql"></a> <span data-ttu-id="0d90a-175">Pour modifier un profil d'agent existant</span><span class="sxs-lookup"><span data-stu-id="0d90a-175">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="0d90a-176">Sur le serveur de distribution, exécutez [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-176">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="0d90a-177">Spécifiez l’une des valeurs suivantes pour **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="0d90a-177">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="0d90a-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-178">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-179">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-180">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-181">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-182">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="0d90a-183">Tous les profils pour le type d'agent spécifié sont retournés.</span><span class="sxs-lookup"><span data-stu-id="0d90a-183">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="0d90a-184">Notez la valeur de **profile_id** dans le jeu de résultats pour le profil à modifier.</span><span class="sxs-lookup"><span data-stu-id="0d90a-184">Note the value of **profile_id** in the result set for the profile to change.</span></span>  
  
2.  <span data-ttu-id="0d90a-185">Sur le serveur de distribution, exécutez [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-185">At the Distributor, execute [sp_help_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql).</span></span> <span data-ttu-id="0d90a-186">Spécifiez l’identificateur de profil de l’étape 1 pour **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-186">Specify the profile identifier from step 1 for **@profile_id**.</span></span> <span data-ttu-id="0d90a-187">Tous les paramètres du profil sont alors retournés.</span><span class="sxs-lookup"><span data-stu-id="0d90a-187">This returns all parameters for the profile.</span></span> <span data-ttu-id="0d90a-188">Notez le nom de tous les paramètres à modifier ou à supprimer du profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-188">Note the name of any parameters to modify or remove from the profile.</span></span>  
  
3.  <span data-ttu-id="0d90a-189">Pour modifier la valeur d’un paramètre dans un profil, exécutez [sp_change_agent_profile & #40 ; Transact-SQL & #41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-189">To change the value of a parameter in a profile, execute [sp_change_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-change-agent-profile-transact-sql).</span></span> <span data-ttu-id="0d90a-190">Spécifiez l’identificateur de profil de l’étape 1 pour **@profile_id** , le nom du paramètre à modifier pour **@property** et une nouvelle valeur pour le paramètre pour **@value** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-190">Specify the profile identifier from step 1 for **@profile_id**, the name of the parameter to change for **@property**, and a new value for the parameter for **@value**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0d90a-191">Vous ne pouvez pas modifier un profil d'agent existant pour qu'il devienne le profil par défaut d'un agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-191">You cannot change an existing agent profile to become the default profile for an agent.</span></span> <span data-ttu-id="0d90a-192">Vous devez créer à la place un nouveau profil comme profil par défaut, comme illustré dans la procédure précédente.</span><span class="sxs-lookup"><span data-stu-id="0d90a-192">You must instead create a new profile as the default profile, as shown in the previous procedure.</span></span>  
  
4.  <span data-ttu-id="0d90a-193">Pour supprimer un paramètre d’un profil, exécutez [sp_drop_agent_parameter & #40 ; Transact-SQL & #41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-193">To remove a parameter from a profile, execute [sp_drop_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql).</span></span> <span data-ttu-id="0d90a-194">Spécifiez l’identificateur de profil de l’étape 1 pour **@profile_id** et le nom du paramètre à supprimer pour **@parameter_name** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-194">Specify the profile identifier from step 1 for **@profile_id** and the name of the parameter to remove for **@parameter_name**.</span></span>  
  
5.  <span data-ttu-id="0d90a-195">Pour ajouter un nouveau paramètre à un profil, vous devez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0d90a-195">To add a new parameter to a profile, you must do the following:</span></span>  
  
    -   <span data-ttu-id="0d90a-196">Interrogez la table [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) sur le serveur de distribution pour déterminer quels paramètres de profil peuvent être définis pour chaque type d’agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-196">Query the [MSagentparameterlist &#40;Transact-SQL&#41;](/sql/relational-databases/system-tables/msagentparameterlist-transact-sql) table at the Distributor to determine which profile parameters can be set for each agent type.</span></span>  
  
    -   <span data-ttu-id="0d90a-197">Sur le serveur de distribution, exécutez [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-197">At the Distributor, execute [sp_add_agent_parameter &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql).</span></span> <span data-ttu-id="0d90a-198">Spécifiez l’identificateur de profil de l’étape 1 pour **@profile_id** , le nom d’un paramètre valide à ajouter pour **@parameter_name** et la valeur du paramètre pour **@parameter_value** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-198">Specify the profile identifier from step 1 for **@profile_id**, the name of a valid parameter to add for **@parameter_name**, and the value of the parameter for **@parameter_value**.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_tsql"></a> <span data-ttu-id="0d90a-199">Pour supprimer un profil d'agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-199">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="0d90a-200">Sur le serveur de distribution, exécutez [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-200">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="0d90a-201">Spécifiez l’une des valeurs suivantes pour **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="0d90a-201">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="0d90a-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-202">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-203">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-204">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-205">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-206">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="0d90a-207">Tous les profils pour le type d'agent spécifié sont retournés.</span><span class="sxs-lookup"><span data-stu-id="0d90a-207">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="0d90a-208">Notez la valeur de **profile_id** dans le jeu de résultats pour le profil à supprimer.</span><span class="sxs-lookup"><span data-stu-id="0d90a-208">Note the value of **profile_id** in the result set for the profile to remove.</span></span>  
  
2.  <span data-ttu-id="0d90a-209">Sur le serveur de distribution, exécutez [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-209">At the Distributor, execute [sp_drop_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-drop-agent-profile-transact-sql).</span></span> <span data-ttu-id="0d90a-210">Spécifiez l’identificateur de profil de l’étape 1 pour **@profile_id** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-210">Specify the profile identifier from step 1 for **@profile_id**.</span></span>  
  
###  <a name="to-use-agent-profiles-during-synchronization"></a><a name="Synch_tsql"></a> <span data-ttu-id="0d90a-211">Pour utiliser les profils d'agent pendant la synchronisation</span><span class="sxs-lookup"><span data-stu-id="0d90a-211">To use agent profiles during synchronization</span></span>  
  
1.  <span data-ttu-id="0d90a-212">Sur le serveur de distribution, exécutez [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0d90a-212">At the Distributor, execute [sp_help_agent_profile &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-agent-profile-transact-sql).</span></span> <span data-ttu-id="0d90a-213">Spécifiez l’une des valeurs suivantes pour **@agent_type** :</span><span class="sxs-lookup"><span data-stu-id="0d90a-213">Specify one of the following values for **@agent_type**:</span></span>  
  
    -   <span data-ttu-id="0d90a-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-214">**1** - [Replication Snapshot Agent](replication-snapshot-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-215">**2** - [Replication Log Reader Agent](replication-log-reader-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-216">**3** - [Replication Distribution Agent](replication-distribution-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-217">**4** - [Replication Merge Agent](replication-merge-agent.md)</span></span>  
  
    -   <span data-ttu-id="0d90a-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span><span class="sxs-lookup"><span data-stu-id="0d90a-218">**9** - [Replication Queue Reader Agent](replication-queue-reader-agent.md)</span></span>  
  
     <span data-ttu-id="0d90a-219">Tous les profils pour le type d'agent spécifié sont retournés.</span><span class="sxs-lookup"><span data-stu-id="0d90a-219">This returns all profiles for the specified type of agent.</span></span> <span data-ttu-id="0d90a-220">Notez la valeur de `profile_name` dans le jeu de résultats pour le profil à utiliser.</span><span class="sxs-lookup"><span data-stu-id="0d90a-220">Note the value of `profile_name` in the result set for the profile to use.</span></span>  
  
2.  <span data-ttu-id="0d90a-221">Si l’agent est démarré à partir d’un travail de l’agent, modifiez l’étape du travail qui démarre l’agent pour spécifier la valeur `profile_name` obtenue à l’étape 1 après le paramètre de ligne de commande **-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-221">If the agent is started from an agent job, edit the job step that starts the agent to specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span> <span data-ttu-id="0d90a-222">Pour plus d’informations, consultez [Afficher et modifier des paramètres d’invite de commandes d’un Agent de réplication &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="0d90a-222">For more information, see [View and Modify Replication Agent Command Prompt Parameters &#40;SQL Server Management Studio&#41;](view-and-modify-replication-agent-command-prompt-parameters.md).</span></span>  
  
3.  <span data-ttu-id="0d90a-223">Lors du démarrage de l’agent à partir de l’invite de commandes, spécifiez la valeur de `profile_name` obtenue à l’étape 1 après le paramètre de ligne de commande **-ProfileName** .</span><span class="sxs-lookup"><span data-stu-id="0d90a-223">When starting the agent from the command prompt, specify the value of `profile_name` obtained in step 1 after the **-ProfileName** command-line parameter.</span></span>  
  
###  <a name="example-transact-sql"></a><a name="TsqlExample"></a> <span data-ttu-id="0d90a-224">Exemple (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0d90a-224">Example (Transact-SQL)</span></span>  
 <span data-ttu-id="0d90a-225">Cet exemple crée un profil personnalisé pour l'Agent de fusion nommé **custom_merge**, modifie la valeur du paramètre **-UploadReadChangesPerBatch** , ajoute un nouveau paramètre **-ExchangeType** et retourne des informations sur le profil créé.</span><span class="sxs-lookup"><span data-stu-id="0d90a-225">This example creates a custom profile for the Merge Agent named **custom_merge**, changes the value of the **-UploadReadChangesPerBatch** parameter, adds a new **-ExchangeType** parameter, and returns information on the profile that is created.</span></span>  
  
 [!code-sql[HowTo#sp_addagentprofileparam](../../../snippets/tsql/SQL15/replication/howto/tsql/createperfparammerge.sql#sp_addagentprofileparam)]  
  
##  <a name="using-rmo"></a><a name="RMOProcedure"></a> <span data-ttu-id="0d90a-226">Utilisation d'RMO</span><span class="sxs-lookup"><span data-stu-id="0d90a-226">Using RMO</span></span>  
  
###  <a name="to-create-a-new-agent-profile"></a><a name="Create_RMO"></a> <span data-ttu-id="0d90a-227">Pour créer un profil d'agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-227">To create a new agent profile</span></span>  
  
1.  <span data-ttu-id="0d90a-228">Créez une connexion avec le serveur de distribution en utilisant une instance de la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-228">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0d90a-229">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="0d90a-229">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span>  
  
3.  <span data-ttu-id="0d90a-230">Définissez les propriétés suivantes de l'objet :</span><span class="sxs-lookup"><span data-stu-id="0d90a-230">Set the following properties on the object:</span></span>  
  
    -   <span data-ttu-id="0d90a-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - nom du profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-231"><xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> - the name for the profile.</span></span>  
  
    -   <span data-ttu-id="0d90a-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - une valeur <xref:Microsoft.SqlServer.Replication.AgentType> qui spécifie le type d'agent de réplication pour lequel le profil est créé.</span><span class="sxs-lookup"><span data-stu-id="0d90a-232"><xref:Microsoft.SqlServer.Replication.AgentProfile.AgentType%2A> - an <xref:Microsoft.SqlServer.Replication.AgentType> value that specifies the type of replication agent for which the profile is being created.</span></span>  
  
    -   <span data-ttu-id="0d90a-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - le <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé dans l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="0d90a-233"><xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A> - the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> created in step 1.</span></span>  
  
    -   <span data-ttu-id="0d90a-234">(Facultatif) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - une description du profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-234">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Description%2A> - a description of the profile.</span></span>  
  
    -   <span data-ttu-id="0d90a-235">(Facultatif) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A>- définit cette propriété sur `true` si tous les nouveaux travaux d'agent pour ce <xref:Microsoft.SqlServer.Replication.AgentType> utiliseront ce profil par défaut.</span><span class="sxs-lookup"><span data-stu-id="0d90a-235">(Optional) <xref:Microsoft.SqlServer.Replication.AgentProfile.Default%2A> - set this property to `true` if all new agent jobs for this <xref:Microsoft.SqlServer.Replication.AgentType> will use this profile by default.</span></span>  
  
4.  <span data-ttu-id="0d90a-236">Appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> pour créer le profil sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="0d90a-236">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Create%2A> method to create the profile on the server.</span></span>  
  
5.  <span data-ttu-id="0d90a-237">Une fois que le profil existe sur le serveur, vous pouvez le personnaliser en ajoutant, en supprimant ou en modifiant les valeurs des paramètres de l'agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="0d90a-237">Once the profile exists on the server, you can customize it by adding, removing, or changing the values of replication agent parameters.</span></span>  
  
6.  <span data-ttu-id="0d90a-238">Pour assigner le profil à un travail d'agent de réplication existant, appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-238">To assign the profile to an existing replication agent job, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.AssignToAgent%2A> method.</span></span> <span data-ttu-id="0d90a-239">Passez le nom de la base de données de distribution pour *distributionDBName* et l'ID du travail pour *agentID*.</span><span class="sxs-lookup"><span data-stu-id="0d90a-239">Pass the name of the distribution database for *distributionDBName* and the ID of the job for *agentID*.</span></span>  
  
###  <a name="to-modify-an-existing-agent-profile"></a><a name="Modify_RMO"></a> <span data-ttu-id="0d90a-240">Pour modifier un profil d'agent existant</span><span class="sxs-lookup"><span data-stu-id="0d90a-240">To modify an existing agent profile</span></span>  
  
1.  <span data-ttu-id="0d90a-241">Créez une connexion avec le serveur de distribution en utilisant une instance de la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-241">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0d90a-242">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.ReplicationServer>.</span><span class="sxs-lookup"><span data-stu-id="0d90a-242">Create an instance of the <xref:Microsoft.SqlServer.Replication.ReplicationServer> class.</span></span> <span data-ttu-id="0d90a-243">Passez l'objet <xref:Microsoft.SqlServer.Management.Common.ServerConnection> créé dans l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="0d90a-243">Pass the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> object created in step 1.</span></span>  
  
3.  <span data-ttu-id="0d90a-244">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-244">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="0d90a-245">Si cette méthode retourne `false`, vérifiez que le serveur de distribution existe.</span><span class="sxs-lookup"><span data-stu-id="0d90a-245">If this method returns `false`, verify that the Distributor exists.</span></span>  
  
4.  <span data-ttu-id="0d90a-246">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-246">Call the <xref:Microsoft.SqlServer.Replication.ReplicationServer.EnumAgentProfiles%2A> method.</span></span> <span data-ttu-id="0d90a-247">Passez une valeur <xref:Microsoft.SqlServer.Replication.AgentType> pour limiter les profils retournés à un type spécifique d'agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="0d90a-247">Pass an <xref:Microsoft.SqlServer.Replication.AgentType> value to narrow down the returned profiles to a specific type of replication agent.</span></span>  
  
5.  <span data-ttu-id="0d90a-248">Obtenez l'objet <xref:Microsoft.SqlServer.Replication.AgentProfile> souhaité à partir du <xref:System.Collections.ArrayList>retourné, où la propriété <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> de l'objet correspond au nom de profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-248">Get the desired <xref:Microsoft.SqlServer.Replication.AgentProfile> object from the returned <xref:System.Collections.ArrayList>, where the <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> property of the object matches the profile name.</span></span>  
  
6.  <span data-ttu-id="0d90a-249">Appelez l'une des méthodes suivantes de <xref:Microsoft.SqlServer.Replication.AgentProfile> pour modifier le profil :</span><span class="sxs-lookup"><span data-stu-id="0d90a-249">Call one of the following methods of <xref:Microsoft.SqlServer.Replication.AgentProfile> to change the profile:</span></span>  
  
    -   <span data-ttu-id="0d90a-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - ajoute un paramètre pris en charge au profil, où *name* est le nom du paramètre d'agent de réplication et *value* la valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="0d90a-250"><xref:Microsoft.SqlServer.Replication.AgentProfile.AddParameter%2A> - adds a supported parameter to the profile, where *name* is the name of the replication agent parameter and *value* is the specified value.</span></span> <span data-ttu-id="0d90a-251">Pour énumérer tous les paramètres d'agent pris en charge pour un type d'agent donné, appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-251">To enumerate all supported agent parameters for a given agent type, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="0d90a-252">Cette méthode retourne un <xref:System.Collections.ArrayList> des objets <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> qui représentent tous les paramètres pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0d90a-252">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent all supported parameters.</span></span>  
  
    -   <span data-ttu-id="0d90a-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - supprime un paramètre existant du profil, où *name* est le nom du paramètre d'agent de réplication.</span><span class="sxs-lookup"><span data-stu-id="0d90a-253"><xref:Microsoft.SqlServer.Replication.AgentProfile.RemoveParameter%2A> - removes an existing parameter from the profile, where *name* is the name of the replication agent parameter.</span></span> <span data-ttu-id="0d90a-254">Pour énumérer tous les paramètres d'agent actuels définis pour le profil, appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-254">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="0d90a-255">Cette méthode retourne un <xref:System.Collections.ArrayList> des objets <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> qui représentent le paramètre existant de ce profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-255">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span>  
  
    -   <span data-ttu-id="0d90a-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - modifie le paramètre d'un paramètre existant du profil, où *name* est le nom du paramètre d'agent et *newValue* la nouvelle valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="0d90a-256"><xref:Microsoft.SqlServer.Replication.AgentProfile.ChangeParameter%2A> - changes the setting of an existing parameter in the profile, where *name* is the name of the agent parameter and *newValue* is the value to which the parameter is being changed.</span></span> <span data-ttu-id="0d90a-257">Pour énumérer tous les paramètres d'agent actuels définis pour le profil, appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-257">To enumerate all current agent parameters defined for the profile, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameters%2A> method.</span></span> <span data-ttu-id="0d90a-258">Cette méthode retourne un <xref:System.Collections.ArrayList> des objets <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> qui représentent le paramètre existant de ce profil.</span><span class="sxs-lookup"><span data-stu-id="0d90a-258">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameter> objects that represent the existing parameter for this profile.</span></span> <span data-ttu-id="0d90a-259">Pour énumérer toutes les valeurs des paramètres d'agent pris en charge, appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-259">To enumerate all supported agent parameter settings, call the <xref:Microsoft.SqlServer.Replication.AgentProfile.EnumParameterInfo%2A> method.</span></span> <span data-ttu-id="0d90a-260">Cette méthode retourne un <xref:System.Collections.ArrayList> des objets <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> qui représentent les valeurs prises en charge pour tous les paramètres.</span><span class="sxs-lookup"><span data-stu-id="0d90a-260">This method returns an <xref:System.Collections.ArrayList> of <xref:Microsoft.SqlServer.Replication.AgentProfileParameterInfo> objects that represent the supported values for all parameters.</span></span>  
  
###  <a name="to-delete-an-agent-profile"></a><a name="Delete_RMO"></a> <span data-ttu-id="0d90a-261">Pour supprimer un profil d'agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-261">To delete an agent profile</span></span>  
  
1.  <span data-ttu-id="0d90a-262">Créez une connexion avec le serveur de distribution en utilisant une instance de la classe <xref:Microsoft.SqlServer.Management.Common.ServerConnection> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-262">Create a connection to the Distributor by using an instance of the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> class.</span></span>  
  
2.  <span data-ttu-id="0d90a-263">Créez une instance de la classe <xref:Microsoft.SqlServer.Replication.AgentProfile>.</span><span class="sxs-lookup"><span data-stu-id="0d90a-263">Create an instance of the <xref:Microsoft.SqlServer.Replication.AgentProfile> class.</span></span> <span data-ttu-id="0d90a-264">Définissez le nom du profil pour <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> et le <xref:Microsoft.SqlServer.Management.Common.ServerConnection> à partir de l'étape 1 de <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d90a-264">Set the name of the profile for <xref:Microsoft.SqlServer.Replication.AgentProfile.Name%2A> and the <xref:Microsoft.SqlServer.Management.Common.ServerConnection> from step 1 for <xref:Microsoft.SqlServer.Replication.ReplicationObject.ConnectionContext%2A>.</span></span>  
  
3.  <span data-ttu-id="0d90a-265">Appelez la méthode <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> .</span><span class="sxs-lookup"><span data-stu-id="0d90a-265">Call the <xref:Microsoft.SqlServer.Replication.ReplicationObject.LoadProperties%2A> method.</span></span> <span data-ttu-id="0d90a-266">Si cette méthode retourne `false`, le nom spécifié était incorrect ou le profil n'existe pas sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="0d90a-266">If this method returns `false`, either the specified name was incorrect or the profile does not exist on the server.</span></span>  
  
4.  <span data-ttu-id="0d90a-267">Vérifiez que la propriété <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> a la valeur <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, ce qui indique un profil de client.</span><span class="sxs-lookup"><span data-stu-id="0d90a-267">Verify that the <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A> property is set to <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.User>, which indicates a customer profile.</span></span> <span data-ttu-id="0d90a-268">Vous ne devez pas supprimer un profil qui a une valeur de <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> pour <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d90a-268">You should not remove a profile that has a value of <xref:Microsoft.SqlServer.Replication.AgentProfileTypeOption.System> for <xref:Microsoft.SqlServer.Replication.AgentProfile.Type%2A>.</span></span>  
  
5.  <span data-ttu-id="0d90a-269">Appelez la méthode <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> pour supprimer le profil défini par l'utilisateur représenté par cet objet du serveur.</span><span class="sxs-lookup"><span data-stu-id="0d90a-269">Call the <xref:Microsoft.SqlServer.Replication.AgentProfile.Remove%2A> method to remove the user-defined profile represented by this object from the server.</span></span>  
  
##  <a name="follow-up-after-changing-agent-parameters"></a><a name="FollowUp"></a> <span data-ttu-id="0d90a-270">Suivi : Après avoir changé les paramètres de l’Agent</span><span class="sxs-lookup"><span data-stu-id="0d90a-270">Follow Up: After Changing Agent Parameters</span></span>  
 <span data-ttu-id="0d90a-271">Les modifications apportées aux paramètres prennent effet au prochain démarrage de l'Agent.</span><span class="sxs-lookup"><span data-stu-id="0d90a-271">Agent parameter changes take effect the next time the agent is started.</span></span> <span data-ttu-id="0d90a-272">Si l'Agent fonctionne en continu, vous devez l'arrêter, puis le redémarrer.</span><span class="sxs-lookup"><span data-stu-id="0d90a-272">If the agent runs continuously, you must stop and restart the agent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d90a-273">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d90a-273">See Also</span></span>  
 <span data-ttu-id="0d90a-274">[Profils de l’Agent de réplication](replication-agent-profiles.md) </span><span class="sxs-lookup"><span data-stu-id="0d90a-274">[Replication Agent Profiles](replication-agent-profiles.md) </span></span>  
 <span data-ttu-id="0d90a-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span><span class="sxs-lookup"><span data-stu-id="0d90a-275">[Replication Snapshot Agent](replication-snapshot-agent.md) </span></span>  
 <span data-ttu-id="0d90a-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span><span class="sxs-lookup"><span data-stu-id="0d90a-276">[Replication Log Reader Agent](replication-log-reader-agent.md) </span></span>  
 <span data-ttu-id="0d90a-277">[Replication Distribution Agent](replication-distribution-agent.md) </span><span class="sxs-lookup"><span data-stu-id="0d90a-277">[Replication Distribution Agent](replication-distribution-agent.md) </span></span>  
 <span data-ttu-id="0d90a-278">[Replication Merge Agent](replication-merge-agent.md) </span><span class="sxs-lookup"><span data-stu-id="0d90a-278">[Replication Merge Agent](replication-merge-agent.md) </span></span>  
 [<span data-ttu-id="0d90a-279">Agent de lecture de la file d’attente de réplication</span><span class="sxs-lookup"><span data-stu-id="0d90a-279">Replication Queue Reader Agent</span></span>](replication-queue-reader-agent.md)  
  
  
