---
title: Créer et gérer des partitions de modèles tabulaires (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: dab72cf0-95bc-4b63-95dc-505b5cd881c1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58c408c712d6ac4b6bd590bd0f8c895dc1a88700
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612480"
---
# <a name="create-and-manage-tabular-model-partitions-ssas-tabular"></a><span data-ttu-id="ace8e-102">Créer et gérer des partitions de modèles tabulaires (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="ace8e-102">Create and Manage Tabular Model Partitions (SSAS Tabular)</span></span>
  <span data-ttu-id="ace8e-103">Les partitions divisent une table en sections logiques.</span><span class="sxs-lookup"><span data-stu-id="ace8e-103">Partitions divide a table into logical parts.</span></span> <span data-ttu-id="ace8e-104">Chaque partition peut ensuite être traitée (actualisée) indépendamment d'autres partitions.</span><span class="sxs-lookup"><span data-stu-id="ace8e-104">Each partition can then be processed (Refreshed) independent of other partitions.</span></span> <span data-ttu-id="ace8e-105">Les partitions définies pour un modèle au cours de la création de modèles sont dupliquées dans un modèle déployé.</span><span class="sxs-lookup"><span data-stu-id="ace8e-105">Partitions defined for a model during model authoring are duplicated in a deployed model.</span></span> <span data-ttu-id="ace8e-106">Une fois le déploiement terminé, vous pouvez gérer ces partitions à l'aide de la boîte de dialogue **Partitions** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou à l'aide d'un script.</span><span class="sxs-lookup"><span data-stu-id="ace8e-106">Once deployed, you can manage those partitions by using the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by using a script.</span></span> <span data-ttu-id="ace8e-107">Les tâches fournies dans cette rubrique décrivent comment créer et gérer des partitions pour un modèle déployé.</span><span class="sxs-lookup"><span data-stu-id="ace8e-107">Tasks provided in this topic describe how to create and manage partitions for a deployed model.</span></span>  
  
 <span data-ttu-id="ace8e-108">Cette rubrique inclut les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="ace8e-108">This topic includes the following tasks:</span></span>  
  
-   [<span data-ttu-id="ace8e-109">Pour créer une nouvelle partition</span><span class="sxs-lookup"><span data-stu-id="ace8e-109">To create a new partition</span></span>](#bkmk_create_new)  
  
-   [<span data-ttu-id="ace8e-110">Pour copier une partition</span><span class="sxs-lookup"><span data-stu-id="ace8e-110">To copy a partition</span></span>](#bkmk_copy)  
  
-   [<span data-ttu-id="ace8e-111">Pour fusionner deux ou plusieurs partitions</span><span class="sxs-lookup"><span data-stu-id="ace8e-111">To merge two or more partitions</span></span>](#bkmk_merge)  
  
-   [<span data-ttu-id="ace8e-112">Pour supprimer une partition</span><span class="sxs-lookup"><span data-stu-id="ace8e-112">To delete a partition</span></span>](#bkmk_delete)  
  
## <a name="tasks"></a><span data-ttu-id="ace8e-113">Tâches</span><span class="sxs-lookup"><span data-stu-id="ace8e-113">Tasks</span></span>  
 <span data-ttu-id="ace8e-114">Pour créer et gérer des partitions d'une base de données de modèle tabulaire déployée, vous utiliserez la boîte de dialogue **Partitions** dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ace8e-114">To create and manage partitions for a deployed tabular model database, you will use the **Partitions** dialog box in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="ace8e-115">Pour afficher la boîte de dialogue **Partitions** , dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], cliquez avec le bouton droit sur une table, puis cliquez sur **Partitions**.</span><span class="sxs-lookup"><span data-stu-id="ace8e-115">To view the **Partitions** dialog box, in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], right-click on a table, and then click **Partitions**.</span></span>  
  
###  <a name="to-create-a-new-partition"></a><a name="bkmk_create_new"></a><span data-ttu-id="ace8e-116">Pour créer une nouvelle partition</span><span class="sxs-lookup"><span data-stu-id="ace8e-116">To create a new partition</span></span>  
  
1.  <span data-ttu-id="ace8e-117">Dans la boîte de dialogue **Partitions** , cliquez sur le bouton **Nouveau** .</span><span class="sxs-lookup"><span data-stu-id="ace8e-117">In the **Partitions** dialog box, click the **New** button.</span></span>  
  
2.  <span data-ttu-id="ace8e-118">Dans **Nom de la partition**, tapez un nom pour la partition.</span><span class="sxs-lookup"><span data-stu-id="ace8e-118">In **Partition Name**, type a name for the partition.</span></span> <span data-ttu-id="ace8e-119">Par défaut, le nom de la partition par défaut est numéroté de manière incrémentielle pour chaque nouvelle partition.</span><span class="sxs-lookup"><span data-stu-id="ace8e-119">By default, the name of the default partition will be incrementally numbered for each new partition.</span></span>  
  
3.  <span data-ttu-id="ace8e-120">Dans **Instruction SQL**, tapez ou collez une instruction de requête SQL qui définit les colonnes et toutes les clauses que vous souhaitez inclure à la partition dans la fenêtre de requête.</span><span class="sxs-lookup"><span data-stu-id="ace8e-120">In **SQL Statement**, type or paste a SQL query statement that defines the columns and any clauses you want to include in the partition into the query window.</span></span>  
  
4.  <span data-ttu-id="ace8e-121">Pour valider l'instruction, cliquez sur **Vérifier la syntaxe**.</span><span class="sxs-lookup"><span data-stu-id="ace8e-121">To validate the statement, click **Check Syntax**.</span></span>  
  
###  <a name="to-copy-a-partition"></a><a name="bkmk_copy"></a> <span data-ttu-id="ace8e-122">Pour copier une partition</span><span class="sxs-lookup"><span data-stu-id="ace8e-122">To copy a partition</span></span>  
  
1.  <span data-ttu-id="ace8e-123">Dans la boîte de dialogue **Partitions** , dans la liste **Partitions** , sélectionnez la partition à copier, puis cliquez sur le bouton **Copier** .</span><span class="sxs-lookup"><span data-stu-id="ace8e-123">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to copy, and then click the **Copy** button.</span></span>  
  
2.  <span data-ttu-id="ace8e-124">Dans **Nom de la partition**, tapez un nouveau nom pour la partition.</span><span class="sxs-lookup"><span data-stu-id="ace8e-124">In **Partition Name**, type a new name for the partition.</span></span>  
  
3.  <span data-ttu-id="ace8e-125">Dans **Instruction SQL**, modifiez l'instruction de requête SQL.</span><span class="sxs-lookup"><span data-stu-id="ace8e-125">In **SQL Statement**, edit the SQL query statement.</span></span>  
  
###  <a name="to-merge-two-or-more-partitions"></a><a name="bkmk_merge"></a> <span data-ttu-id="ace8e-126">Pour fusionner deux ou plusieurs partitions</span><span class="sxs-lookup"><span data-stu-id="ace8e-126">To merge two or more partitions</span></span>  
  
-   <span data-ttu-id="ace8e-127">Dans la boîte de dialogue **Partitions** , dans la liste **Partitions** , utilisez Ctrl+clic pour sélectionner les partitions à fusionner, puis cliquez sur le bouton **Fusionner** .</span><span class="sxs-lookup"><span data-stu-id="ace8e-127">In the **Partitions** dialog box, in the **Partitions** list, use Ctrl+click to select the partitions you want to merge, and then click the **Merge** button.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ace8e-128">Le fait de fusionner les partitions ne met pas à jour les métadonnées des partitions.</span><span class="sxs-lookup"><span data-stu-id="ace8e-128">Merging partitions does not update the partition metadata.</span></span> <span data-ttu-id="ace8e-129">Les administrateurs doivent modifier l'instruction SQL pour la partition obtenue afin de veiller à ce que les opérations de traitement traitent toutes les données dans la partition fusionnée.</span><span class="sxs-lookup"><span data-stu-id="ace8e-129">Administrators must alter the SQL Statement for the resulting partition to make sure processing operations process all data in the merged partition.</span></span>  
  
###  <a name="to-delete-a-partition"></a><a name="bkmk_delete"></a><span data-ttu-id="ace8e-130">Pour supprimer une partition</span><span class="sxs-lookup"><span data-stu-id="ace8e-130">To delete a partition</span></span>  
  
-   <span data-ttu-id="ace8e-131">Dans la boîte de dialogue **Partitions** , dans la liste **Partitions** , sélectionnez la partition à supprimer, puis cliquez sur le bouton **Supprimer** .</span><span class="sxs-lookup"><span data-stu-id="ace8e-131">In the **Partitions** dialog box, in the **Partitions** list, select the partition you want to delete, and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace8e-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ace8e-132">See Also</span></span>  
 <span data-ttu-id="ace8e-133">[Partitions de modèles tabulaires &#40;&#41;SSAS tabulaire](partitions-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ace8e-133">[Tabular Model Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="ace8e-134">Traiter les partitions de modèles tabulaires &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ace8e-134">Process Tabular Model Partitions &#40;SSAS Tabular&#41;</span></span>](process-tabular-model-partitions-ssas-tabular.md)  
  
  
