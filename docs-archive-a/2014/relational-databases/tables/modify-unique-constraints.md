---
title: Modifier des contraintes uniques | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying constraints
- UNIQUE constraints [SQL Server], modifying
- constraints [SQL Server], modifying
- constraints [SQL Server], unique
ms.assetid: fddbdc9e-958b-4614-8e88-6ca205d64a4e
author: stevestein
ms.author: sstein
ms.openlocfilehash: 74b044202f7e8e9bc762f025833cf2d0ff84c4c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615083"
---
# <a name="modify-unique-constraints"></a><span data-ttu-id="2d1c4-102">Modifier des contraintes uniques</span><span class="sxs-lookup"><span data-stu-id="2d1c4-102">Modify Unique Constraints</span></span>
  <span data-ttu-id="2d1c4-103">Vous pouvez modifier une contrainte unique dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d1c4-103">You can modify a unique constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="2d1c4-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="2d1c4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="2d1c4-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="2d1c4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="2d1c4-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2d1c4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="2d1c4-107">**Pour modifier une contrainte unique à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="2d1c4-107">**To modify a unique constraint using:**</span></span>  
  
     [<span data-ttu-id="2d1c4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d1c4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="2d1c4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="2d1c4-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="2d1c4-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="2d1c4-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="2d1c4-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="2d1c4-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="2d1c4-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="2d1c4-112">Permissions</span></span>  
 <span data-ttu-id="2d1c4-113">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="2d1c4-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="2d1c4-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-unique-constraint"></a><span data-ttu-id="2d1c4-115">Pour modifier une contrainte unique</span><span class="sxs-lookup"><span data-stu-id="2d1c4-115">To modify a unique constraint</span></span>  
  
1.  <span data-ttu-id="2d1c4-116">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table contenant la contrainte unique, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-116">In the **Object Explorer**, right-click the table containing the unique constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="2d1c4-117">Dans le menu **Concepteur de tables**, cliquez sur **Index/Clés...** .</span><span class="sxs-lookup"><span data-stu-id="2d1c4-117">On the **Table Designer** menu, click **Indexes/Keys...**.</span></span>  
  
3.  <span data-ttu-id="2d1c4-118">Dans la boîte de dialogue **Index/Clés** , sous **Index ou clé unique/primaire sélectionné(e)** , sélectionnez la contrainte que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-118">In the **Indexes/Keys** dialog box, under **Selected Primary/Unique Key or Index**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="2d1c4-119">Effectuez l'une des actions décrites dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="2d1c4-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="2d1c4-120">À</span><span class="sxs-lookup"><span data-stu-id="2d1c4-120">To</span></span>|<span data-ttu-id="2d1c4-121">Procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="2d1c4-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="2d1c4-122">Changer les colonnes auxquelles la contrainte est associée</span><span class="sxs-lookup"><span data-stu-id="2d1c4-122">Change the columns that the constraint is associated with</span></span>|<span data-ttu-id="2d1c4-123">1) Dans la grille en dessous de **(Général)** , cliquez sur **Colonnes**, puis sur le bouton de sélection **(...)** , à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-123">1) In the grid under **(General)**, click **Columns** and then click the ellipses **(...)** to the right of the property.</span></span><br /><br /> <span data-ttu-id="2d1c4-124">2) Dans la boîte de dialogue **Colonnes d’index** , spécifiez la nouvelle colonne, l’ordre de tri, ou les deux, pour l’index.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-124">2) In the **Index Columns** dialog box, specify the new column or sort order or both for the index.</span></span>|  
    |<span data-ttu-id="2d1c4-125">Renommer la contrainte</span><span class="sxs-lookup"><span data-stu-id="2d1c4-125">Rename the constraint</span></span>|<span data-ttu-id="2d1c4-126">Dans la grille sous **Identité**, tapez un nouveau nom dans la zone **Nom** .</span><span class="sxs-lookup"><span data-stu-id="2d1c4-126">In the grid under **Identity**, type a new name in the **Name** box.</span></span> <span data-ttu-id="2d1c4-127">Assurez-vous que le nouveau nom n’existe pas déjà dans la liste **Index ou clé unique/primaire sélectionné(e)** .</span><span class="sxs-lookup"><span data-stu-id="2d1c4-127">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="2d1c4-128">Définir l'option clustered</span><span class="sxs-lookup"><span data-stu-id="2d1c4-128">Set the clustered option</span></span>|<span data-ttu-id="2d1c4-129">Dans la grille sous **Concepteur de tables**, sélectionnez **Créer sous forme de cluster** et sélectionnez Oui dans la liste déroulante pour créer un index cluster, ou Non pour créer un index non-cluster.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-129">In the grid under **Table Designer**, select **Create As Clustered** and from the dropdown choose Yes to create a clustered index and No to create a nonclustered one.</span></span> <span data-ttu-id="2d1c4-130">Il ne peut exister qu'un seul index cluster par table.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-130">Only one clustered index can exist per table.</span></span> <span data-ttu-id="2d1c4-131">Si un index cluster existe dans la table, vous devez effacer ce paramètre sur l'index d'origine.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-131">If a clustered index already exists in this table, you must clear this setting on the original index.</span></span>|  
    |<span data-ttu-id="2d1c4-132">Définir un taux de remplissage</span><span class="sxs-lookup"><span data-stu-id="2d1c4-132">Define a fill factor</span></span>|<span data-ttu-id="2d1c4-133">Dans la grille sous **Concepteur de tables**, développez la catégorie **Spécification du remplissage** et tapez un entier compris entre 0 et 100 dans la zone **Facteur de remplissage** .</span><span class="sxs-lookup"><span data-stu-id="2d1c4-133">In the grid under **Table Designer**, expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill Factor** box.</span></span>|  
  
5.  <span data-ttu-id="2d1c4-134">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="to-modify-a-unique-constraint"></a><a name="TsqlProcedure"></a> <span data-ttu-id="2d1c4-135">**Pour modifier une contrainte unique**</span><span class="sxs-lookup"><span data-stu-id="2d1c4-135">**To modify a unique constraint**</span></span>  
  
 <span data-ttu-id="2d1c4-136">Pour modifier une contrainte UNIQUE à l'aide deTransact-SQL , vous devez d'abord supprimer la contrainte UNIQUE existante, puis la recréer avec sa nouvelle définition.</span><span class="sxs-lookup"><span data-stu-id="2d1c4-136">To modify a UNIQUE constraint using Transact-SQL, you must first delete the existing UNIQUE constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="2d1c4-137">Pour plus d'informations, consultez [Delete Unique Constraints](delete-unique-constraints.md) et [Create Unique Constraints](create-unique-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="2d1c4-137">For more information, see [Delete Unique Constraints](delete-unique-constraints.md) and [Create Unique Constraints](create-unique-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
