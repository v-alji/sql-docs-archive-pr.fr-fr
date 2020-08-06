---
title: Modifier des contraintes de validation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- CHECK constraints, modifying
- modifying constraints
- constraints [SQL Server], check
- constraints [SQL Server], modifying
ms.assetid: f22daef8-e350-40ef-8ff0-b5f87d1d9e56
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8377c80590612c8b68c315f7c37823eb8f5c5093
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610986"
---
# <a name="modify-check-constraints"></a><span data-ttu-id="ab2c1-102">Modifier des contraintes de validation</span><span class="sxs-lookup"><span data-stu-id="ab2c1-102">Modify Check Constraints</span></span>
  <span data-ttu-id="ab2c1-103">Vous pouvez modifier une contrainte de validation dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)] lorsque vous voulez changer l'expression de contrainte ou les options qui activent ou désactivent la contrainte pour des conditions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-103">You can modify a check constraint in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] when you want to change the constraint expression or the options that enable or disable the constraint for specific conditions.</span></span>  
  
 <span data-ttu-id="ab2c1-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ab2c1-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ab2c1-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ab2c1-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ab2c1-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ab2c1-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ab2c1-107">**Pour modifier une contrainte de validation à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ab2c1-107">**To modify a check constraint using:**</span></span>  
  
     [<span data-ttu-id="ab2c1-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab2c1-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ab2c1-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab2c1-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ab2c1-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ab2c1-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ab2c1-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ab2c1-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ab2c1-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ab2c1-112">Permissions</span></span>  
 <span data-ttu-id="ab2c1-113">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-113">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ab2c1-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ab2c1-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-a-check-constraint"></a><span data-ttu-id="ab2c1-115">Pour modifier une contrainte de validation</span><span class="sxs-lookup"><span data-stu-id="ab2c1-115">To modify a check constraint</span></span>  
  
1.  <span data-ttu-id="ab2c1-116">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table contenant la contrainte de validation, puis sélectionnez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-116">In the **Object Explorer**, right-click the table containing the check constraint and select **Design**.</span></span>  
  
2.  <span data-ttu-id="ab2c1-117">Dans le menu **Concepteur de tables** , cliquez sur **Vérifier les contraintes...** .</span><span class="sxs-lookup"><span data-stu-id="ab2c1-117">On the **Table Designer** menu, click **Check Constraints...**.</span></span>  
  
3.  <span data-ttu-id="ab2c1-118">Sélectionnez dans la liste **Contrainte de validation sélectionnée** de la boîte de dialogue **Contraintes de validation**la la contrainte que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-118">In the **Check Constraints** dialog box, under **Selected Check Constraint**, select the constraint you wish to edit.</span></span>  
  
4.  <span data-ttu-id="ab2c1-119">Effectuez l'une des actions décrites dans le tableau suivant :</span><span class="sxs-lookup"><span data-stu-id="ab2c1-119">Complete an action from the following table:</span></span>  
  
    |<span data-ttu-id="ab2c1-120">À</span><span class="sxs-lookup"><span data-stu-id="ab2c1-120">To</span></span>|<span data-ttu-id="ab2c1-121">Procédez comme suit</span><span class="sxs-lookup"><span data-stu-id="ab2c1-121">Follow these steps</span></span>|  
    |--------|------------------------|  
    |<span data-ttu-id="ab2c1-122">Modifier l'expression de contrainte</span><span class="sxs-lookup"><span data-stu-id="ab2c1-122">Edit the constraint expression</span></span>|<span data-ttu-id="ab2c1-123">Tapez la nouvelle expression dans le champ **Expression** .</span><span class="sxs-lookup"><span data-stu-id="ab2c1-123">Type the new expression in the **Expression** field.</span></span>|  
    |<span data-ttu-id="ab2c1-124">Renommer la contrainte</span><span class="sxs-lookup"><span data-stu-id="ab2c1-124">Rename the constraint</span></span>|<span data-ttu-id="ab2c1-125">Tapez un nouveau nom dans le champ **Nom** .</span><span class="sxs-lookup"><span data-stu-id="ab2c1-125">Type a new name in the **Name** field.</span></span>|  
    |<span data-ttu-id="ab2c1-126">Appliquer la contrainte à des données existantes</span><span class="sxs-lookup"><span data-stu-id="ab2c1-126">Apply the constraint to existing data</span></span>|<span data-ttu-id="ab2c1-127">Choisissez Oui pour l'option **Vérifier les données existantes à la création ou à la réactivation** .</span><span class="sxs-lookup"><span data-stu-id="ab2c1-127">Select the **Check Existing Data on Creation or Enabling** option.</span></span>|  
    |<span data-ttu-id="ab2c1-128">Désactiver la contrainte lorsque de nouvelles données sont ajoutées à la table ou lorsque les données existantes sont mises à jour dans la table</span><span class="sxs-lookup"><span data-stu-id="ab2c1-128">Disable the constraint when new data is added to the table or when existing data is updated in the table.</span></span>|<span data-ttu-id="ab2c1-129">Désactivez la case à cocher **Appliquer la contrainte pour INSERT et UPDATE** .</span><span class="sxs-lookup"><span data-stu-id="ab2c1-129">Clear the **Enforce Constraint for INSERTs and UPDATEs** option.</span></span>|  
    |<span data-ttu-id="ab2c1-130">Désactiver la contrainte lorsque l'Agent de réplication insère ou met à jour les données dans votre table.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-130">Disable the constraint when a replication agent inserts or updates data in your table.</span></span>|<span data-ttu-id="ab2c1-131">Désactivez la case à cocher **Appliquer la réplication** .</span><span class="sxs-lookup"><span data-stu-id="ab2c1-131">Clear the **Enforce For Replication** option.</span></span>|  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab2c1-132">Certaines bases de données offrent des fonctionnalités différentes pour les contraintes de validation.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-132">Some databases have different functionality for check constraints.</span></span>  
  
5.  <span data-ttu-id="ab2c1-133">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-133">Click **Close**.</span></span>  
  
6.  <span data-ttu-id="ab2c1-134">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-134">On the **File** menu, click **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ab2c1-135">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ab2c1-135">Using Transact-SQL</span></span>  
 <span data-ttu-id="ab2c1-136">**Pour modifier une contrainte de validation**</span><span class="sxs-lookup"><span data-stu-id="ab2c1-136">**To modify a check constraint**</span></span>  
  
 <span data-ttu-id="ab2c1-137">Pour modifier une contrainte `CHECK` à l'aide de [!INCLUDE[tsql](../../includes/tsql-md.md)], vous devez d'abord supprimer la contrainte `CHECK` existante, puis la recréer avec la nouvelle définition.</span><span class="sxs-lookup"><span data-stu-id="ab2c1-137">To modify a `CHECK` constraint using [!INCLUDE[tsql](../../includes/tsql-md.md)], you must first delete the existing `CHECK` constraint and then re-create it with the new definition.</span></span> <span data-ttu-id="ab2c1-138">Pour plus d’informations, consultez [Supprimer des contraintes de validation](delete-check-constraints.md) et [Créer des contraintes de validation](create-check-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="ab2c1-138">For more information, see [Delete Check Constraints](delete-check-constraints.md) and [Create Check Constraints](create-check-constraints.md).</span></span>  
  
###  <a name="TsqlExample"></a>  
