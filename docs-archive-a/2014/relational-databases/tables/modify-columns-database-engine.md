---
title: Modifier des colonnes (moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying data types
- column data types [SQL Server]
- data types [SQL Server], columns
ms.assetid: b67b95c5-61ef-4bd8-9a3e-1640eb7583ac
author: stevestein
ms.author: sstein
ms.openlocfilehash: a73c25d91b742f1cc1f7edcc8a95cdf226b2683c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610985"
---
# <a name="modify-columns-database-engine"></a><span data-ttu-id="f62f3-102">Modifier des colonnes (moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="f62f3-102">Modify Columns (Database Engine)</span></span>
  <span data-ttu-id="f62f3-103">Vous pouvez modifier le type de données d'une colonne dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f62f3-103">You can modify the data type of a column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f62f3-104">La modification du type de données d'une colonne qui contient déjà des données peut entraîner la perte définitive des données lors de leur conversion en ce nouveau type.</span><span class="sxs-lookup"><span data-stu-id="f62f3-104">Modifying the data type of a column that already contains data can result in the permanent loss of data when the existing data is converted to the new type.</span></span> <span data-ttu-id="f62f3-105">De plus, le code et les applications qui dépendent de la colonne modifiée peuvent échouer.</span><span class="sxs-lookup"><span data-stu-id="f62f3-105">In addition, code and applications that depend on the modified column may fail.</span></span> <span data-ttu-id="f62f3-106">Il peut s'agir de requêtes, de vues, de procédures stockées, de fonctions définies par l'utilisateur et d'applications clientes.</span><span class="sxs-lookup"><span data-stu-id="f62f3-106">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="f62f3-107">Notez que ces défaillances se produisent en cascade.</span><span class="sxs-lookup"><span data-stu-id="f62f3-107">Note that these failures will cascade.</span></span> <span data-ttu-id="f62f3-108">Par exemple, une procédure stockée qui appelle une fonction définie par l'utilisateur dépendant de la colonne modifiée peut échouer.</span><span class="sxs-lookup"><span data-stu-id="f62f3-108">For example, a stored procedure that calls a user-defined function that depends on the modified column may fail.</span></span> <span data-ttu-id="f62f3-109">Prenez toutes les précautions nécessaires avant de modifier une colonne.</span><span class="sxs-lookup"><span data-stu-id="f62f3-109">Carefully consider any changes you want to make to a column before making it.</span></span>  
  
 <span data-ttu-id="f62f3-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f62f3-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f62f3-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f62f3-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f62f3-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f62f3-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f62f3-113">**Pour modifier le type de données d'une colonne à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f62f3-113">**To modify the data type of a column, using:**</span></span>  
  
     [<span data-ttu-id="f62f3-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f62f3-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="f62f3-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f62f3-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f62f3-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f62f3-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f62f3-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f62f3-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f62f3-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f62f3-118">Permissions</span></span>  
 <span data-ttu-id="f62f3-119">Requiert une autorisation ALTER sur la table.</span><span class="sxs-lookup"><span data-stu-id="f62f3-119">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f62f3-120">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f62f3-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="f62f3-121">Pour modifier le type de données d'une colonne</span><span class="sxs-lookup"><span data-stu-id="f62f3-121">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="f62f3-122">Dans **l’Explorateur d’objets**, cliquez avec le bouton droit sur la table contenant les colonnes dont vous souhaitez modifier l’échelle et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="f62f3-122">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="f62f3-123">Sélectionnez la colonne pour laquelle vous souhaitez modifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="f62f3-123">Select the column for which you want to modify the data type.</span></span>  
  
3.  <span data-ttu-id="f62f3-124">Sous l’onglet **Propriétés des colonnes** , cliquez sur la cellule de grille correspondant à la propriété **Type de données** et choisissez un nouveau type de données dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="f62f3-124">In the **Column Properties** tab, click the grid cell for the **Data Type** property and choose a new data type from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="f62f3-125">Dans le menu **Fichier**, cliquez sur **Enregistrer**_nom de la table_.</span><span class="sxs-lookup"><span data-stu-id="f62f3-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f62f3-126">Lorsque vous modifiez le type de données d'une colonne, le Concepteur de tables applique la longueur par défaut du type de données que vous avez sélectionné, même si vous en avez déjà spécifié une autre.</span><span class="sxs-lookup"><span data-stu-id="f62f3-126">When you modify the data type of a column, Table Designer applies the default length of the data type you selected, even if you have already specified another.</span></span> <span data-ttu-id="f62f3-127">Affectez toujours la valeur souhaitée comme longueur de type de données après avoir spécifié le type de données.</span><span class="sxs-lookup"><span data-stu-id="f62f3-127">Always set the data type length for to the desired value after specifying the data type.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="f62f3-128">Si vous tentez de modifier le type de données d'une colonne associée à d'autres tables, le Concepteur de tables vous demande de confirmer que la modification concerne également les colonnes d'autres tables.</span><span class="sxs-lookup"><span data-stu-id="f62f3-128">If you attempt to modify the data type of a column that relates to other tables, Table Designer asks you to confirm that the change should be made to the columns in the other tables as well.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f62f3-129">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f62f3-129">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="f62f3-130">Pour modifier le type de données d'une colonne</span><span class="sxs-lookup"><span data-stu-id="f62f3-130">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="f62f3-131">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f62f3-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="f62f3-132">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="f62f3-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="f62f3-133">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="f62f3-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exy (column_a INT ) ;  
    GO  
    INSERT INTO dbo.doc_exy (column_a) VALUES (10) ;  
    GO  
    ALTER TABLE dbo.doc_exy ALTER COLUMN column_a DECIMAL (5, 2) ;  
    GO  
  
    ```  
  
 <span data-ttu-id="f62f3-134">Pour plus d’informations, consultez [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f62f3-134">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
