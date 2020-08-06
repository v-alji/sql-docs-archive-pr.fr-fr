---
title: Créer et gérer des rôles (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.rolemanager.f1
- sql12.asvs.bidtoolset.roledb.f1
ms.assetid: e23d27a8-e968-4082-9dbe-963fc724b5d9
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 335e0e311d97ea452449cd0c5d6550f6dbcca4f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601745"
---
# <a name="create-and-manage-roles-ssas-tabular"></a><span data-ttu-id="38f5a-102">Créer et gérer des rôles (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="38f5a-102">Create and Manage Roles (SSAS Tabular)</span></span>
  <span data-ttu-id="38f5a-103">Les rôles, dans les modèles tabulaires, définissent des autorisations de membre pour un modèle.</span><span class="sxs-lookup"><span data-stu-id="38f5a-103">Roles, in tabular models, define member permissions for a model.</span></span> <span data-ttu-id="38f5a-104">Les rôles sont définis pour un projet de modèle à l'aide de la boîte de dialogue Gestionnaire de rôles de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f5a-104">Roles are defined for a model project by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="38f5a-105">Lorsqu'un modèle est déployé, les administrateurs de base de données peuvent gérer les rôles à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f5a-105">When a model is deployed, database administrators can manage roles by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="38f5a-106">Les tâches de cette rubrique expliquent comment créer et gérer les rôles pendant la création du modèle à l'aide de la boîte de dialogue Gestionnaire de rôles de [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f5a-106">The tasks in this topic describe how to create and manage roles during model authoring by using the Role Manager dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="38f5a-107">Pour plus d’informations sur la gestion des rôles dans une base de données model déployée, consultez [Rôles de modèles tabulaires &#40;SSAS Tabulaire&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="38f5a-107">For information about managing roles in a deployed model database, see [Tabular Model Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="38f5a-108">Tâches</span><span class="sxs-lookup"><span data-stu-id="38f5a-108">Tasks</span></span>  
 <span data-ttu-id="38f5a-109">Pour créer, modifier, copier et supprimer des rôles, utilisez la boîte de dialogue **Gestionnaire de rôles** .</span><span class="sxs-lookup"><span data-stu-id="38f5a-109">To create, edit, copy, and delete roles, you will use the **Role Manager** dialog box.</span></span> <span data-ttu-id="38f5a-110">Pour consulter la boîte de dialogue **Gestionnaire de rôles** , dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Gestionnaire de rôles**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-110">To view the **Role Manager** dialog box, in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
###  <a name="to-create-a-new-role"></a><a name="bkmk_new_role"></a> <span data-ttu-id="38f5a-111">Pour créer un rôle</span><span class="sxs-lookup"><span data-stu-id="38f5a-111">To create a new role</span></span>  
  
1.  <span data-ttu-id="38f5a-112">Dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], cliquez sur le menu **Modèle** , puis sur **Gestionnaire de rôles**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Role Manager**.</span></span>  
  
2.  <span data-ttu-id="38f5a-113">Dans la boîte de dialogue **Gestionnaire de rôles** , cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-113">In the **Role Manager** dialog box, click **New**.</span></span>  
  
     <span data-ttu-id="38f5a-114">Un nouveau rôle en surbrillance est ajouté à la liste de rôles.</span><span class="sxs-lookup"><span data-stu-id="38f5a-114">A new highlighted role is added to the Roles list.</span></span>  
  
3.  <span data-ttu-id="38f5a-115">Dans la liste **Rôles** , dans le champ **Nom** , tapez un nom pour le rôle.</span><span class="sxs-lookup"><span data-stu-id="38f5a-115">In the **Roles** list, in the **Name** field, type a name for the role.</span></span>  
  
     <span data-ttu-id="38f5a-116">Par défaut, le nom du rôle par défaut est numéroté de manière incrémentielle pour chaque nouveau rôle.</span><span class="sxs-lookup"><span data-stu-id="38f5a-116">By default, the name of the default role will be incrementally numbered for each new role.</span></span> <span data-ttu-id="38f5a-117">Il est recommandé de taper un nom qui identifie sans ambiguïté le type de membre, par exemple, Directeurs financiers ou Responsables des ressources humaines.</span><span class="sxs-lookup"><span data-stu-id="38f5a-117">It is recommended you type a name that clearly identifies the member type, for example, Finance Managers or Human Resources Specialists.</span></span>  
  
4.  <span data-ttu-id="38f5a-118">Dans le champ **Autorisations** , cliquez sur la flèche Bas, puis sélectionnez un des types d'autorisation suivants :</span><span class="sxs-lookup"><span data-stu-id="38f5a-118">In the **Permissions** field, click the down arrow and then select one of the following permission types:</span></span>  
  
    |<span data-ttu-id="38f5a-119">Autorisation</span><span class="sxs-lookup"><span data-stu-id="38f5a-119">Permission</span></span>|<span data-ttu-id="38f5a-120">Description</span><span class="sxs-lookup"><span data-stu-id="38f5a-120">Description</span></span>|  
    |----------------|-----------------|  
    |<span data-ttu-id="38f5a-121">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="38f5a-121">**None**</span></span>|<span data-ttu-id="38f5a-122">Les membres ne peuvent pas apporter de modifications au schéma de modèle et ne peuvent pas interroger les données.</span><span class="sxs-lookup"><span data-stu-id="38f5a-122">Members cannot make any modifications to the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="38f5a-123">**Lire**</span><span class="sxs-lookup"><span data-stu-id="38f5a-123">**Read**</span></span>|<span data-ttu-id="38f5a-124">Les membres sont autorisés à interroger des données (selon les filtres de lignes) mais ne peuvent pas apporter de modifications au schéma de modèle.</span><span class="sxs-lookup"><span data-stu-id="38f5a-124">Members are allowed to query data (based on row filters) but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="38f5a-125">**Lecture et traitement**</span><span class="sxs-lookup"><span data-stu-id="38f5a-125">**Read and Process**</span></span>|<span data-ttu-id="38f5a-126">Les membres sont autorisés à interroger des données (selon les filtres au niveau de la ligne) et à exécuter toutes les opérations Traiter et Traiter tout, mais ils ne peuvent pas apporter de modifications au schéma de modèle.</span><span class="sxs-lookup"><span data-stu-id="38f5a-126">Members are allowed to query data (based on row-level filters) and run Process and Process All operations, but cannot make any changes to the model schema.</span></span>|  
    |<span data-ttu-id="38f5a-127">**Processus**</span><span class="sxs-lookup"><span data-stu-id="38f5a-127">**Process**</span></span>|<span data-ttu-id="38f5a-128">Les membres peuvent exécuter des processus et traiter toutes les opérations.</span><span class="sxs-lookup"><span data-stu-id="38f5a-128">Members can run Process and Process All operations.</span></span> <span data-ttu-id="38f5a-129">Impossible de modifier le schéma de modèle et d'interroger les données.</span><span class="sxs-lookup"><span data-stu-id="38f5a-129">Cannot modify the model schema and cannot query data.</span></span>|  
    |<span data-ttu-id="38f5a-130">**Administrateur**</span><span class="sxs-lookup"><span data-stu-id="38f5a-130">**Administrator**</span></span>|<span data-ttu-id="38f5a-131">Les membres peuvent apporter des modifications au schéma de modèle et peuvent interroger toutes les données.</span><span class="sxs-lookup"><span data-stu-id="38f5a-131">Members can make modifications to the model schema and can query all data.</span></span>|  
  
5.  <span data-ttu-id="38f5a-132">Pour entrer une description du rôle, cliquez sur le champ **Description** et tapez une description.</span><span class="sxs-lookup"><span data-stu-id="38f5a-132">To enter a description for the role, click the **Description** field, and then type a description.</span></span>  
  
6.  <span data-ttu-id="38f5a-133">Si le rôle que vous créez dispose d'autorisations de lecture ou de lecture et traitement, vous pouvez ajouter des filtres de lignes à l'aide d'une formule DAX.</span><span class="sxs-lookup"><span data-stu-id="38f5a-133">If the role you are creating has Read or Read and Process permission, you can add row filters using a DAX formula.</span></span> <span data-ttu-id="38f5a-134">Pour ajouter des filtres de lignes, cliquez sur l'onglet **Filtres de lignes** , sélectionnez une table, cliquez sur le champ **Filtre DAX** , puis tapez une formule DAX.</span><span class="sxs-lookup"><span data-stu-id="38f5a-134">To add row filters, click the **Row Filters** tab, then select a table, then click the **DAX Filter** field, and then type a DAX formula.</span></span>  
  
7.  <span data-ttu-id="38f5a-135">Pour ajouter des membres au rôle, cliquez sur l'onglet **Membres** , puis sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-135">To add members to the role, click the **Members** tab, and then click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="38f5a-136">Les membres du rôle peuvent également être ajoutés à un modèle déployé à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="38f5a-136">Role members can also be added to a deployed model by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="38f5a-137">Pour plus d’informations, consultez [Gérer les rôles à l’aide de SSMS &#40;SSAS Tabulaire&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="38f5a-137">For more information, see [Manage Roles by using SSMS &#40;SSAS Tabular&#41;](manage-roles-by-using-ssms-ssas-tabular.md).</span></span>  
  
8.  <span data-ttu-id="38f5a-138">Dans la boîte de dialogue **Sélectionner les utilisateurs ou les groupes** , entrez des objets utilisateur ou de groupe Windows comme membres.</span><span class="sxs-lookup"><span data-stu-id="38f5a-138">In the **Select Users or Groups** dialog box, enter Windows user or Windows group objects as members.</span></span>  
  
9. <span data-ttu-id="38f5a-139">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-139">Click **Ok**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38f5a-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="38f5a-140">See Also</span></span>  
 <span data-ttu-id="38f5a-141">[Rôles &#40;&#41;tabulaire SSAS](roles-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="38f5a-141">[Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md) </span></span>  
 <span data-ttu-id="38f5a-142">[Perspectives &#40;&#41;tabulaire SSAS](perspectives-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="38f5a-142">[Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md) </span></span>  
 <span data-ttu-id="38f5a-143">[Analyser dans Excel &#40;la&#41;tabulaire SSAS](analyze-in-excel-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="38f5a-143">[Analyze in Excel &#40;SSAS Tabular&#41;](analyze-in-excel-ssas-tabular.md) </span></span>  
 <span data-ttu-id="38f5a-144">[Fonction USERNAME &#40;&#41;DAX](/dax/username-function-dax) </span><span class="sxs-lookup"><span data-stu-id="38f5a-144">[USERNAME Function &#40;DAX&#41;](/dax/username-function-dax) </span></span>  
 [<span data-ttu-id="38f5a-145">Fonction CUSTOMDATA &#40;&#41;DAX</span><span class="sxs-lookup"><span data-stu-id="38f5a-145">CUSTOMDATA Function &#40;DAX&#41;</span></span>](/dax/customdata-function-dax)  
  
  
