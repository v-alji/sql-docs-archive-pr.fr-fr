---
title: Ajouter des colonnes à une table (moteur de base de données)| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- inserting columns
- columns [SQL Server], adding
- adding columns
ms.assetid: abeb8d52-d562-4e29-9e1e-2923ae874859
author: stevestein
ms.author: sstein
ms.openlocfilehash: f7e9294de10be0df9ef470c75d0934e9f8787b55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605330"
---
# <a name="add-columns-to-a-table-database-engine"></a><span data-ttu-id="4f101-102">Ajouter des colonnes à une table (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="4f101-102">Add Columns to a Table (Database Engine)</span></span>
  <span data-ttu-id="4f101-103">Cette rubrique explique comment ajouter des colonnes à une table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f101-103">This topic describes how to add new columns to a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="4f101-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="4f101-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="4f101-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="4f101-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="4f101-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4f101-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="4f101-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4f101-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="4f101-108">**Pour insérer des colonnes, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="4f101-108">**To insert columns, using:**</span></span>  
  
     [<span data-ttu-id="4f101-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f101-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="4f101-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f101-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="4f101-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="4f101-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="4f101-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="4f101-112">Limitations and Restrictions</span></span>  
 <span data-ttu-id="4f101-113">L'instruction ALTER TABLE permettant d'ajouter des colonnes à une table, ajoute automatiquement ces colonnes à la fin de la table.</span><span class="sxs-lookup"><span data-stu-id="4f101-113">Using the ALTER TABLE statement to add columns to a table automatically adds those columns to the end of the table.</span></span> <span data-ttu-id="4f101-114">Si vous souhaitez classer les colonnes dans la table dans un ordre spécifique, utilisez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f101-114">If you want the columns in a specific order in the table, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="4f101-115">Cependant, notez que cette méthode n'est pas recommandée pour concevoir une base de données.</span><span class="sxs-lookup"><span data-stu-id="4f101-115">However, note that this is not a database design best practice.</span></span> <span data-ttu-id="4f101-116">La recommandation est de spécifier l'ordre dans lequel les colonnes sont renvoyées au niveau de l'application et de la requête.</span><span class="sxs-lookup"><span data-stu-id="4f101-116">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="4f101-117">Vous ne pouvez pas compter sur l'utilisation de SELECT \* pour retourner toutes les colonnes dans une commande prévue d'après l'ordre dans lequel elles sont définies dans la table.</span><span class="sxs-lookup"><span data-stu-id="4f101-117">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="4f101-118">Spécifiez toujours le nom des colonnes dans vos requêtes et applications dans l'ordre dans lequel vous souhaitez qu'elles apparaissent.</span><span class="sxs-lookup"><span data-stu-id="4f101-118">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="4f101-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="4f101-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="4f101-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4f101-120">Permissions</span></span>  
 <span data-ttu-id="4f101-121">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="4f101-121">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="4f101-122">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4f101-122">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-insert-columns-into-a-table-with-table-designer"></a><span data-ttu-id="4f101-123">Pour insérer des colonnes dans une table à l'aide du Concepteur de tables</span><span class="sxs-lookup"><span data-stu-id="4f101-123">To insert columns into a table with Table Designer</span></span>  
  
1.  <span data-ttu-id="4f101-124">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur la table dans laquelle vous souhaitez ajouter des colonnes et choisissez **Conception**.</span><span class="sxs-lookup"><span data-stu-id="4f101-124">In **Object Explorer**, right-click the table to which you want to add columns and choose **Design**.</span></span>  
  
2.  <span data-ttu-id="4f101-125">Cliquez sur la première cellule vide dans la colonne **Nom de la colonne** .</span><span class="sxs-lookup"><span data-stu-id="4f101-125">Click in the first blank cell in the **Column Name** column.</span></span>  
  
3.  <span data-ttu-id="4f101-126">Tapez le nom de la colonne dans la cellule.</span><span class="sxs-lookup"><span data-stu-id="4f101-126">Type the column name in the cell.</span></span> <span data-ttu-id="4f101-127">Le nom de la colonne est une valeur requise.</span><span class="sxs-lookup"><span data-stu-id="4f101-127">The column name is a required value.</span></span>  
  
4.  <span data-ttu-id="4f101-128">Appuyez sur la touche TAB pour passer à la cellule **Type de données** et sélectionnez le type de données dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="4f101-128">Press the TAB key to go to the **Data Type** cell and select a data type from the dropdown.</span></span> <span data-ttu-id="4f101-129">Il s'agit également d'une valeur requise qui sera utilisée comme valeur par défaut si vous n'en choisissez pas.</span><span class="sxs-lookup"><span data-stu-id="4f101-129">This too is a required value, and will be assigned the default value if you don't choose one.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f101-130"> Vous pouvez modifier la valeur par défaut dans la boîte de dialogue **Options** située sous **Outils de base de données**.</span><span class="sxs-lookup"><span data-stu-id="4f101-130">You can change the default value in the **Options** dialog box under **Database Tools**.</span></span>  
  
5.  <span data-ttu-id="4f101-131">Continuez à définir éventuellement d'autres propriétés des colonnes dans l'onglet **Propriétés des Colonnes** .</span><span class="sxs-lookup"><span data-stu-id="4f101-131">Continue to define any other column properties in the **Column Properties** tab.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f101-132"> Les valeurs par défaut des propriétés des colonnes sont ajoutées lorsque vous créez une nouvelle colonne, mais vous pouvez les modifier dans l'onglet **Propriétés de la colonne** .</span><span class="sxs-lookup"><span data-stu-id="4f101-132">The default values for your column properties are added when you create a new column, but you can change them in the **Column Properties** tab.</span></span>  
  
6.  <span data-ttu-id="4f101-133">Quand vous avez fini d’ajouter des colonnes, dans le menu **Fichier**, choisissez **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="4f101-133">When you are finished adding columns, from the **File** menu, choose **Save**_table name_.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="4f101-134">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="4f101-134">Using Transact-SQL</span></span>  
  
#### <a name="to-insert-columns-into-a-table"></a><span data-ttu-id="4f101-135">Pour insérer des colonnes dans une table</span><span class="sxs-lookup"><span data-stu-id="4f101-135">To insert columns into a table</span></span>  
  
1.  <span data-ttu-id="4f101-136">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f101-136">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f101-137">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="4f101-137">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="4f101-138">L'exemple suivant ajoute deux colonnes à la table `dbo.doc_exa`.</span><span class="sxs-lookup"><span data-stu-id="4f101-138">The following example adds two columns to the table `dbo.doc_exa`.</span></span> <span data-ttu-id="4f101-139">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="4f101-139">Copy and paste the following example into the query window and click **Execute**</span></span>  
  
```  
ALTER TABLE dbo.doc_exa ADD column_b VARCHAR(20) NULL, column_c INT NULL ;  
```  
  
##  <a name="for-more-information-see-alter-table-40transact-sql41"></a><a name="FollowUp"></a><span data-ttu-id="4f101-140">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="4f101-140">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
