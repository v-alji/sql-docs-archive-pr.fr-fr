---
title: Gérer des rôles à l’aide de SSMS (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 652faac0-1cfc-438b-8119-2f4b090a2381
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4ee34d5e75d5d4ce3679d46d29af3215852d2bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696164"
---
# <a name="manage-roles-by-using-ssms-ssas-tabular"></a><span data-ttu-id="93782-102">Gérer les rôles à l'aide de SSMS (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="93782-102">Manage Roles by using SSMS (SSAS Tabular)</span></span>
  <span data-ttu-id="93782-103">Vous pouvez créer, modifier et gérer les rôles pour un modèle tabulaire déployé à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93782-103">You can create, edit, and manage roles for a deployed tabular model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="93782-104">Tâches de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="93782-104">Tasks in this topic:</span></span>  
  
-   [<span data-ttu-id="93782-105">Pour créer un nouveau rôle</span><span class="sxs-lookup"><span data-stu-id="93782-105">To create a new role</span></span>](#bkmk_new_role)  
  
-   [<span data-ttu-id="93782-106">Pour copier un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-106">To copy a role</span></span>](#bkmk_copy_role)  
  
-   [<span data-ttu-id="93782-107">Pour modifier un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-107">To edit a role</span></span>](#bkmk_edit_role)  
  
-   [<span data-ttu-id="93782-108">Pour supprimer un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-108">To delete a role</span></span>](#bkmk_deletet_role)  
  
> [!CAUTION]  
>  <span data-ttu-id="93782-109">Le redéploiement d'un projet de modèle tabulaire avec les rôles définis à l'aide du Gestionnaire de rôles de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] remplace les rôles définis dans un modèle tabulaire déployé.</span><span class="sxs-lookup"><span data-stu-id="93782-109">Re-deploying a tabular model project with roles defined by using Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)] will overwrite roles defined in a deployed tabular model.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="93782-110">L'utilisation de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour gérer une base de données d'espace de travail model tabulaire alors que le projet de modèle est ouvert dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] peut entraîner l'altération du fichier Model.bim.</span><span class="sxs-lookup"><span data-stu-id="93782-110">Using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to manage a tabular model workspace database while the model project is open in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] may cause the Model.bim file to become corrupted.</span></span> <span data-ttu-id="93782-111">Lors de la création et de la gestion des rôles pour une base de données d'espace de travail model tabulaire, utilisez le Gestionnaire de rôles de [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93782-111">When creating and managing roles for a tabular model workspace database, use Role Manager in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="93782-112">Pour créer un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-112">To create a new role</span></span>  
  
1.  <span data-ttu-id="93782-113">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez la base de données model tabulaire pour laquelle vous voulez créer un rôle, cliquez avec le bouton droit sur **Rôles**, puis cliquez sur **Nouveau rôle**.</span><span class="sxs-lookup"><span data-stu-id="93782-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database for which you want to create a new role, then right click on **Roles**, and then click **New Role**.</span></span>  
  
2.  <span data-ttu-id="93782-114">Dans la boîte de dialogue **Créer un rôle** , dans la fenêtre Sélectionner une page, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="93782-114">In the **Create Role** dialog box, in the Select a page window, click **General**.</span></span>  
  
3.  <span data-ttu-id="93782-115">Dans la fenêtre des paramètres généraux, dans le champ **Nom** , tapez un nom pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="93782-115">In the general settings window, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="93782-116">Par défaut, le nom du rôle par défaut est numéroté de manière incrémentielle pour chaque nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="93782-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="93782-117">Il est recommandé de taper un nom qui identifie sans ambiguïté le type de membre, par exemple, Directeurs financiers ou Responsables des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="93782-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="93782-118">Dans **Définissez les autorisations de base de données pour ce rôle**, sélectionnez l'une des options d'autorisations suivantes :</span><span class="sxs-lookup"><span data-stu-id="93782-118">In **Set the database permissions for this role**, select one of the following permissions options:</span></span>  
  
    |<span data-ttu-id="93782-119">Autorisation</span><span class="sxs-lookup"><span data-stu-id="93782-119">Permission</span></span>|<span data-ttu-id="93782-120">Description</span><span class="sxs-lookup"><span data-stu-id="93782-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="93782-121">**Contrôle total (administrateur)**</span><span class="sxs-lookup"><span data-stu-id="93782-121">**Full control (Administrator)**</span></span>|<span data-ttu-id="93782-122">Les membres peuvent apporter des modifications au schéma de modèle et peuvent afficher toutes les données.</span><span class="sxs-lookup"><span data-stu-id="93782-122">Members can make modifications to the model schema and can view all data.</span></span>|  
    |<span data-ttu-id="93782-123">**Base de données de processus**</span><span class="sxs-lookup"><span data-stu-id="93782-123">**Process database**</span></span>|<span data-ttu-id="93782-124">Les membres peuvent exécuter des processus et traiter toutes les opérations.</span><span class="sxs-lookup"><span data-stu-id="93782-124">Members can run Process and Process All operations.</span></span> <span data-ttu-id="93782-125">Impossible de modifier le schéma de modèle et d'afficher les données.</span><span class="sxs-lookup"><span data-stu-id="93782-125">Cannot modify the model schema and cannot view data.</span></span>|  
    |<span data-ttu-id="93782-126">**Lire**</span><span class="sxs-lookup"><span data-stu-id="93782-126">**Read**</span></span>|<span data-ttu-id="93782-127">Les membres sont autorisés à afficher des données (selon les filtres de lignes) mais ne peuvent pas apporter de modifications au schéma de modèle.</span><span class="sxs-lookup"><span data-stu-id="93782-127">Members are allowed to view data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
  
5.  <span data-ttu-id="93782-128">Dans la boîte de dialogue **Créer un rôle** , dans la fenêtre Sélectionner une page, cliquez sur **Appartenance**.</span><span class="sxs-lookup"><span data-stu-id="93782-128">In the **Create Role** dialog box, in the Select a page window, click **Membership**.</span></span>  
  
6.  <span data-ttu-id="93782-129">Dans la fenêtre de paramètres d'appartenance, cliquez sur **Ajouter**, puis dans la boîte de dialogue **Sélectionner les utilisateurs ou les groupes** , ajoutez les utilisateurs ou groupes Windows que vous souhaitez ajouter comme membres.</span><span class="sxs-lookup"><span data-stu-id="93782-129">In the membership settings window, click **Add**, and then in the **Select Users or Groups** dialog box, add the Windows users or groups you want to add as members.</span></span>  
  
7.  <span data-ttu-id="93782-130">Si le rôle que vous créez dispose d'autorisations de lecture, vous pouvez ajouter des filtres de lignes à une table à l'aide d'une formule DAX.</span><span class="sxs-lookup"><span data-stu-id="93782-130">If the role you are creating has Read permissions, you can add row filters for any table using a DAX formula.</span></span> <span data-ttu-id="93782-131">Pour ajouter des filtres de lignes, dans la boîte de dialogue \*\*Propriétés du rôle- \<rolename> \*\* , dans **Sélectionner une page**, cliquez sur **filtres de lignes**.</span><span class="sxs-lookup"><span data-stu-id="93782-131">To add row filters, in the **Role Properties - \<rolename>** dialog box, in **Select a page**, click on **Row Filters**.</span></span>  
  
8.  <span data-ttu-id="93782-132">Dans la fenêtre filtres de lignes, sélectionnez une table, cliquez sur le champ **filtre Dax** , puis dans le champ \*\*filtre Dax- \<tablename> \*\* , tapez une formule Dax.</span><span class="sxs-lookup"><span data-stu-id="93782-132">In the row filters window, select a table, then click on the **DAX Filter** field, and then in the **DAX Filter - \<tablename>** field, type a DAX formula.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="93782-133">Le champ filtre DAX- \<tablename> ne contient pas d’éditeur de requête de saisie semi-automatique ni de fonction d’insertion de fonction.</span><span class="sxs-lookup"><span data-stu-id="93782-133">The DAX Filter - \<tablename> field does not contain an AutoComplete query editor or insert function feature.</span></span> <span data-ttu-id="93782-134">Pour utiliser la saisie semi-automatique lorsque vous écrivez une formule DAX, vous devez utiliser un éditeur de formules DAX dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93782-134">To use AutoComplete when writing a DAX formula, you must use a DAX formula editor in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
9. <span data-ttu-id="93782-135">Cliquez sur **OK** pour enregistrer le rôle.</span><span class="sxs-lookup"><span data-stu-id="93782-135">Click **Ok** to save the role.</span></span>  
  
###  <a name="to-copy-a-role"></a><a name="bkmk_copy_role"></a> <span data-ttu-id="93782-136">Pour copier un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-136">To copy a role</span></span>  
  
1.  <span data-ttu-id="93782-137">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez la base de données model tabulaire qui contient le rôle que vous souhaitez copier, développez **Rôles**, cliquez avec le bouton droit sur le rôle, puis cliquez sur **Dupliquer**.</span><span class="sxs-lookup"><span data-stu-id="93782-137">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to copy, then expand **Roles**, then right click on the role, and then click **Duplicate**.</span></span>  
  
###  <a name="to-edit-a-role"></a><a name="bkmk_edit_role"></a><span data-ttu-id="93782-138">Pour modifier un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-138">To edit a role</span></span>  
  
-   <span data-ttu-id="93782-139">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez la base de données model tabulaire qui contient le rôle que vous souhaitez modifier, développez **Rôles**, cliquez avec le bouton droit sur le rôle, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="93782-139">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to edit, then expand **Roles**, then right click on the role, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="93782-140">Dans la boîte de dialogue **Propriétés du rôle** \<rolename> , vous pouvez modifier les autorisations, ajouter ou supprimer des membres, et ajouter/modifier des filtres de lignes.</span><span class="sxs-lookup"><span data-stu-id="93782-140">In the **Role Properties** \<rolename> dialog box, you can change permissions, add or remove members, and add/edit row filters.</span></span>  
  
###  <a name="to-delete-a-role"></a><a name="bkmk_deletet_role"></a><span data-ttu-id="93782-141">Pour supprimer un rôle</span><span class="sxs-lookup"><span data-stu-id="93782-141">To delete a role</span></span>  
  
-   <span data-ttu-id="93782-142">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], développez la base de données model tabulaire qui contient le rôle que vous souhaitez supprimer, développez **Rôles**, cliquez avec le bouton droit sur le rôle, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="93782-142">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], expand the tabular model database that contains the role you want to delete, then expand **Roles**, then right click on the role, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93782-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93782-143">See Also</span></span>  
 [<span data-ttu-id="93782-144">Rôles &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="93782-144">Roles &#40;SSAS Tabular&#41;</span></span>](roles-ssas-tabular.md)  
  
  
