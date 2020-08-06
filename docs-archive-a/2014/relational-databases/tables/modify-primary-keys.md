---
title: Modifier des clés primaires | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying primary keys
- primary keys [SQL Server], modifying
ms.assetid: 8e2a15ba-1cd1-4408-b860-16c3ee37d635
author: stevestein
ms.author: sstein
ms.openlocfilehash: f24deeac45491f9097d90ee0407464f928a0713b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599843"
---
# <a name="modify-primary-keys"></a><span data-ttu-id="7e663-102">Modifier des clés primaires</span><span class="sxs-lookup"><span data-stu-id="7e663-102">Modify Primary Keys</span></span>
  <span data-ttu-id="7e663-103">Vous pouvez modifier une clé primaire dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e663-103">You can modify a primary key in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="7e663-104">Vous pouvez modifier la clé primaire d'une table en changeant l'ordre des colonnes, le nom de l'index, l'option clustered ou le facteur de remplissage.</span><span class="sxs-lookup"><span data-stu-id="7e663-104">You can modify the primary key of a table by changing the column order, index name, clustered option, or fill factor.</span></span>  
  
 <span data-ttu-id="7e663-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="7e663-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="7e663-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="7e663-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="7e663-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e663-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="7e663-108">**Pour modifier une clé primaire à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="7e663-108">**To modify a primary key, using:**</span></span>  
  
     [<span data-ttu-id="7e663-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e663-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="7e663-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e663-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="7e663-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="7e663-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="7e663-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="7e663-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="7e663-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="7e663-113">Permissions</span></span>  
 <span data-ttu-id="7e663-114">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="7e663-114">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="7e663-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="7e663-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-primary-key"></a><span data-ttu-id="7e663-116">Pour modifier une clé primaire</span><span class="sxs-lookup"><span data-stu-id="7e663-116">To modify a primary key</span></span>  
  
1.  <span data-ttu-id="7e663-117">Ouvrez le Concepteur de tables pour la table dont vous souhaitez modifier la clé primaire, cliquez avec le bouton droit dans le Concepteur de tables, puis cliquez sur **Index/Clés** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="7e663-117">Open the Table Designer for the table whose primary key you want to modify, right-click in the Table Designer, and choose **Indexes/Keys** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="7e663-118">Dans la boîte de dialogue **Index/Clés** , sélectionnez l’index de clé primaire dans la liste **Index ou clé unique/primaire sélectionné(e)** .</span><span class="sxs-lookup"><span data-stu-id="7e663-118">In the **Indexes/Keys** dialog box, select the primary key index from the **Selected Primary/Unique Key or Index** list.</span></span>  
  
3.  <span data-ttu-id="7e663-119">Effectuez l'une des actions décrites dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="7e663-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="7e663-120">À</span><span class="sxs-lookup"><span data-stu-id="7e663-120">To</span></span>|<span data-ttu-id="7e663-121">Procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="7e663-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="7e663-122">Renommer la clé primaire</span><span class="sxs-lookup"><span data-stu-id="7e663-122">Rename the primary key</span></span>|<span data-ttu-id="7e663-123">Tapez un nouveau nom dans la zone **Nom** .</span><span class="sxs-lookup"><span data-stu-id="7e663-123">Type a new name in the **Name** box.</span></span> <span data-ttu-id="7e663-124">Assurez-vous que le nouveau nom n’existe pas déjà dans la liste **Index ou clé unique/primaire sélectionné(e)** .</span><span class="sxs-lookup"><span data-stu-id="7e663-124">Make sure that your new name does not duplicate a name in the **Selected Primary/Unique Key or Index** list.</span></span>|  
    |<span data-ttu-id="7e663-125">Définir l'option clustered</span><span class="sxs-lookup"><span data-stu-id="7e663-125">Set the clustered option</span></span>|<span data-ttu-id="7e663-126">Pour créer un index cluster pour la clé primaire, sélectionnez **Créer comme CLUSTERED**, puis sélectionnez l’option dans la zone de liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="7e663-126">To create a clustered index for the primary key, select **Create as CLUSTERED**, and select the option from the drop-down list box.</span></span> <span data-ttu-id="7e663-127">Il ne peut exister qu'un seul index cluster par table.</span><span class="sxs-lookup"><span data-stu-id="7e663-127">Only one clustered index can exist per table.</span></span> <span data-ttu-id="7e663-128">Si cette option n'est pas disponible pour votre index, désactivez d'abord ce paramètre sur l'index cluster existant.</span><span class="sxs-lookup"><span data-stu-id="7e663-128">If this option is not available for your index, you must first clear this setting on the existing clustered index.</span></span><br /><br /> <span data-ttu-id="7e663-129">Si cette option n'est pas sélectionnée, un index non-cluster unique est créé.</span><span class="sxs-lookup"><span data-stu-id="7e663-129">If this option is not selected, a unique nonclustered index is created.</span></span>|  
    |<span data-ttu-id="7e663-130">Définir un taux de remplissage</span><span class="sxs-lookup"><span data-stu-id="7e663-130">Define a fill factor</span></span>|<span data-ttu-id="7e663-131">Développez la catégorie **Spécification du remplissage** et tapez un entier compris entre 0 et 100 dans la zone **Taux de remplissage** .</span><span class="sxs-lookup"><span data-stu-id="7e663-131">Expand the **Fill Specification** category and type an integer from 0 to 100 in the **Fill factor** box.</span></span> <span data-ttu-id="7e663-132">Pour plus d’informations sur les facteurs de remplissage et leurs utilisations, consultez [Spécifier un facteur de remplissage pour un index](../indexes/specify-fill-factor-for-an-index.md).</span><span class="sxs-lookup"><span data-stu-id="7e663-132">For more information about fill factors and their uses, see [Specify Fill Factor for an Index](../indexes/specify-fill-factor-for-an-index.md).</span></span>|  
    |<span data-ttu-id="7e663-133">Changer l'ordre des colonnes</span><span class="sxs-lookup"><span data-stu-id="7e663-133">Change the column order</span></span>|<span data-ttu-id="7e663-134">Sélectionnez **Colonnes**, puis cliquez sur le bouton de sélection **(...)** situé à droite de la propriété.</span><span class="sxs-lookup"><span data-stu-id="7e663-134">Select **Columns**, and then click the ellipses **(...)** to the right of the property.</span></span> <span data-ttu-id="7e663-135">Dans la boîte de dialogue  **Colonnes d'index** , supprimez les colonnes de la clé primaire.</span><span class="sxs-lookup"><span data-stu-id="7e663-135">In the  **Index Columns** dialog box, remove the columns from the primary key.</span></span> <span data-ttu-id="7e663-136">Rajoutez-les ensuite dans l'ordre voulu.</span><span class="sxs-lookup"><span data-stu-id="7e663-136">Then add the columns back in the order you want.</span></span> <span data-ttu-id="7e663-137">Pour supprimer une colonne clé, retirez simplement le nom de la colonne de la liste **Nom de la colonne** .</span><span class="sxs-lookup"><span data-stu-id="7e663-137">To remove a column from the key, simply remove the column name from the **Column** name list.</span></span>|  
  
4.  <span data-ttu-id="7e663-138">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="7e663-138">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="7e663-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="7e663-139">Using Transact-SQL</span></span>  
 <span data-ttu-id="7e663-140">**Pour modifier une clé primaire**</span><span class="sxs-lookup"><span data-stu-id="7e663-140">**To modify a primary key**</span></span>  
  
 <span data-ttu-id="7e663-141">Pour modifier une contrainte PRIMARY KEY à l'aide de Transact-SQL, vous devez supprimer auparavant la contrainte PRIMARY KEY existante, puis la créer à nouveau en précisant sa nouvelle définition.</span><span class="sxs-lookup"><span data-stu-id="7e663-141">To modify a PRIMARY KEY constraint using Transact-SQL, you must first delete the existing PRIMARY KEY constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="7e663-142">Pour plus d'informations, consultez [Delete Primary Keys](delete-primary-keys.md) et [Create Primary Keys](create-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="7e663-142">For more information, see [Delete Primary Keys](delete-primary-keys.md) and [Create Primary Keys](create-primary-keys.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
