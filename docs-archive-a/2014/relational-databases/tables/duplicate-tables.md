---
title: Dupliquer des tables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 793a38416f86a5b43a3e3bb2420127d7acf2af1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603366"
---
# <a name="duplicate-tables"></a><span data-ttu-id="9b45a-102">Dupliquer des tables</span><span class="sxs-lookup"><span data-stu-id="9b45a-102">Duplicate Tables</span></span>
  <span data-ttu-id="9b45a-103">Vous pouvez dupliquer une table existante dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)] en créant une table puis en copiant les informations sur les colonnes d'une table existante.</span><span class="sxs-lookup"><span data-stu-id="9b45a-103">You can duplicate an existing table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)] by creating a new table and then copying column information from an existing table.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="9b45a-104">Cette opération permet de dupliquer uniquement la structure d'une table, elle ne duplique aucune ligne de table.</span><span class="sxs-lookup"><span data-stu-id="9b45a-104">This operation duplicates only the structure of a table; it does not duplicate any table rows.</span></span>  
  
 <span data-ttu-id="9b45a-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="9b45a-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9b45a-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="9b45a-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9b45a-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9b45a-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9b45a-108">**Pour dupliquer une table à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="9b45a-108">**To duplicate a table, using:**</span></span>  
  
     [<span data-ttu-id="9b45a-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b45a-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9b45a-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b45a-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9b45a-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="9b45a-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9b45a-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9b45a-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9b45a-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="9b45a-113">Permissions</span></span>  
 <span data-ttu-id="9b45a-114">Requiert l'autorisation CREATE TABLE dans la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="9b45a-114">Requires CREATE TABLE permission in the destination database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9b45a-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9b45a-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-duplicate-a-table"></a><span data-ttu-id="9b45a-116">Pour dupliquer une table</span><span class="sxs-lookup"><span data-stu-id="9b45a-116">To duplicate a table</span></span>  
  
1.  <span data-ttu-id="9b45a-117">Vérifiez que vous êtes connecté à la base de données dans laquelle vous voulez créer la table et que la base de données est sélectionnée dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="9b45a-117">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="9b45a-118">Dans l’Explorateur d'objets, cliquez avec le bouton droit sur **Tables** , puis cliquez sur **Nouvelle table**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-118">In Object Explorer, right-click **Tables** and click **New Table**.</span></span>  
  
3.  <span data-ttu-id="9b45a-119">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur la table que vous souhaitez copier et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-119">In Object Explorer right-click the table you want to copy and click **Design**.</span></span>  
  
4.  <span data-ttu-id="9b45a-120">Sélectionnez les colonnes dans la table existante et, dans le menu **Edition** , cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-120">Select the columns in the existing table and, from the **Edit** menu, click **Copy**.</span></span>  
  
5.  <span data-ttu-id="9b45a-121">Revenez à la nouvelle table et sélectionnez la première ligne.</span><span class="sxs-lookup"><span data-stu-id="9b45a-121">Switch back to the new table and select the first row.</span></span>  
  
6.  <span data-ttu-id="9b45a-122">Dans le menu **Edition** , cliquez sur **Coller**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-122">From the **Edit** menu, click **Paste**.</span></span>  
  
7.  <span data-ttu-id="9b45a-123">Dans le menu **Fichier** , cliquez sur **Enregistrer**_nom_table_.</span><span class="sxs-lookup"><span data-stu-id="9b45a-123">From the **File** menu, click **Save**_table name_.</span></span>  
  
8.  <span data-ttu-id="9b45a-124">Dans la boîte de dialogue **Choisir un nom** , tapez un nom pour la nouvelle table et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-124">In the **Choose Name** dialog box, type a name for the new table and click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9b45a-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9b45a-125">Using Transact-SQL</span></span>  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a><span data-ttu-id="9b45a-126">Pour dupliquer une table dans l'éditeur de requête</span><span class="sxs-lookup"><span data-stu-id="9b45a-126">To duplicate a table in Query Editor</span></span>  
  
1.  <span data-ttu-id="9b45a-127">Vérifiez que vous êtes connecté à la base de données dans laquelle vous voulez créer la table et que la base de données est sélectionnée dans l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="9b45a-127">Make sure you are connected to the database in which you want to create the table and that the database is selected in Object Explorer.</span></span>  
  
2.  <span data-ttu-id="9b45a-128">Cliquez avec le bouton droit sur la table que vous souhaitez dupliquer, pointez sur **Générer un script de la table en tant que**, puis pointez sur **CREATE To**et sélectionnez **Nouvelle fenêtre d’éditeur de requête**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-128">Right-click the table you wish to duplicate, point to **Script Table as**, then point to **CREATE to**, and then select **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="9b45a-129">Modifiez le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="9b45a-129">Change the name of the table.</span></span>  
  
4.  <span data-ttu-id="9b45a-130">Supprimez toutes les colonnes qui ne sont pas nécessaires dans la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="9b45a-130">Remove any columns that are not needed in the new table.</span></span>  
  
5.  <span data-ttu-id="9b45a-131">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="9b45a-131">Click **Execute**.</span></span>  
  
  
