---
title: Afficher la définition de table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- showing table properties
- displaying table properties
- tables [SQL Server], properties
- viewing table properties
ms.assetid: 1865fb7c-f480-4100-9007-df5364cd002a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53170a78a104bfce4b4e4177015461f2eb9093e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615077"
---
# <a name="view-the-table-definition"></a><span data-ttu-id="d7543-102">Afficher la définition de table</span><span class="sxs-lookup"><span data-stu-id="d7543-102">View the Table Definition</span></span>
  <span data-ttu-id="d7543-103">Vous pouvez afficher les propriétés d'une table dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7543-103">You can display properties for a table in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d7543-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d7543-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d7543-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d7543-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d7543-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d7543-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d7543-107">**Pour afficher les propriétés d'une table, à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="d7543-107">**To display table properties, using:**</span></span>  
  
     [<span data-ttu-id="d7543-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d7543-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d7543-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d7543-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d7543-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d7543-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d7543-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d7543-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d7543-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d7543-112">Permissions</span></span>  
 <span data-ttu-id="d7543-113">Vous pouvez uniquement afficher les propriétés d'une table si vous possédez la table ou si vous avez l'autorisation d'y accéder.</span><span class="sxs-lookup"><span data-stu-id="d7543-113">You can only see properties in a table if you either own the table or have been granted permissions to that table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d7543-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d7543-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-show-table-properties-in-the-properties-window"></a><span data-ttu-id="d7543-115">Pour afficher les propriétés d'une table dans la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="d7543-115">To show table properties in the Properties window</span></span>  
  
1.  <span data-ttu-id="d7543-116">Dans l'Explorateur d'objets, sélectionnez la table pour laquelle vous souhaitez afficher les propriétés.</span><span class="sxs-lookup"><span data-stu-id="d7543-116">In Object Explorer, select the table for which you want to show properties.</span></span>  
  
2.  <span data-ttu-id="d7543-117">Cliquez avec le bouton droit sur la table et, dans le menu contextuel, cliquez sur **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="d7543-117">Right-click the table and choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="d7543-118">Pour plus d’informations, consultez [Table Properties](table-properties-ssms.md).</span><span class="sxs-lookup"><span data-stu-id="d7543-118">For more information, see [Table Properties](table-properties-ssms.md).</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d7543-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d7543-119">Using Transact-SQL</span></span>  
  
#### <a name="to-show-table-properties"></a><span data-ttu-id="d7543-120">Pour afficher les propriétés de la table</span><span class="sxs-lookup"><span data-stu-id="d7543-120">To show table properties</span></span>  
  
1.  <span data-ttu-id="d7543-121">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7543-121">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d7543-122">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d7543-122">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d7543-123">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d7543-123">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="d7543-124">L'exemple retourne toutes les colonnes de l'affichage catalogue de `sys.tables` pour l'objet spécifié.</span><span class="sxs-lookup"><span data-stu-id="d7543-124">The example returns all columns from the `sys.tables` catalog view for the specified object.</span></span>  
  
    ```  
    SELECT * FROM sys.tables  
    WHERE object_id = 1973582069;  
  
    ```  
  
 <span data-ttu-id="d7543-125">Pour plus d’informations, consultez [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d7543-125">For more information, see [sys.tables &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-tables-transact-sql).</span></span>  
  
###  <a name="TsqlExample"></a>  
