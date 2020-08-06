---
title: Modifier l’ordre des colonnes dans une table | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- columns [SQL Server], change order in a table
- column order, change
ms.assetid: cd99ef56-9085-431a-a0fc-58e7add5399f
author: stevestein
ms.author: sstein
ms.openlocfilehash: d162f9dc793ceb9ea423d94922f7358f1729712e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605331"
---
# <a name="change-column-order-in-a-table"></a><span data-ttu-id="ad8a0-102">Modifier l'ordre des colonnes dans une table</span><span class="sxs-lookup"><span data-stu-id="ad8a0-102">Change Column Order in a Table</span></span>
  <span data-ttu-id="ad8a0-103">Vous pouvez changer l'ordre des colonnes dans le Concepteur de tables dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ad8a0-103">You can change the order of columns in Table Designer in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="ad8a0-104">Changer l'ordre des colonnes d'une table peut avoir une incidence sur le code et les applications qui dépendent de l'ordre spécifique des colonnes.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-104">Changing the column order of a table may affect code and applications that depend on the specific order of columns.</span></span> <span data-ttu-id="ad8a0-105">Il peut s'agir de requêtes, de vues, de procédures stockées, de fonctions définies par l'utilisateur et d'applications clientes.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-105">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="ad8a0-106">Prenez toutes les précautions nécessaires avant de changer l'ordre des colonnes.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-106">Carefully consider any changes you want to make to column order before making it.</span></span> <span data-ttu-id="ad8a0-107">La recommandation est de spécifier l'ordre dans lequel les colonnes sont renvoyées au niveau de l'application et de la requête.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-107">Best practice is to specify the order in which the columns are returned at the application and query level.</span></span> <span data-ttu-id="ad8a0-108">Vous ne pouvez pas compter sur l'utilisation de SELECT \* pour retourner toutes les colonnes dans une commande prévue d'après l'ordre dans lequel elles sont définies dans la table.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-108">You should not rely on the use of SELECT \* to return all columns in an expected order based on the order in which they are defined in the table.</span></span> <span data-ttu-id="ad8a0-109">Spécifiez toujours le nom des colonnes dans vos requêtes et applications dans l'ordre dans lequel vous souhaitez qu'elles apparaissent.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-109">Always specify the columns by name in your queries and applications in the order in which you would like them to appear.</span></span>  
  
 <span data-ttu-id="ad8a0-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad8a0-111">**Pour changer l'ordre des colonnes à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-111">**To change the column order, using:**</span></span>  
  
     [<span data-ttu-id="ad8a0-112">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad8a0-112">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="ad8a0-113">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad8a0-113">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad8a0-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad8a0-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-the-column-order"></a><span data-ttu-id="ad8a0-115">Pour changer l'ordre des colonnes</span><span class="sxs-lookup"><span data-stu-id="ad8a0-115">To change the column order</span></span>  
  
1.  <span data-ttu-id="ad8a0-116">Dans l’ **Explorateur d’objets**, cliquez avec le bouton droit sur la table dont vous souhaitez réorganiser les colonnes et cliquez sur **Conception**.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-116">In **Object Explorer**, right-click the table with columns you want to reorder and click **Design**.</span></span>  
  
2.  <span data-ttu-id="ad8a0-117">Sélectionnez la case à gauche du nom de la colonne à réordonner.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-117">Select the box to the left of the column name that you want to reorder.</span></span>  
  
3.  <span data-ttu-id="ad8a0-118">Faites glisser la colonne vers un autre emplacement dans la table.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-118">Drag the column to another location within the table.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="ad8a0-119">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="ad8a0-119">Using Transact-SQL</span></span>  
 <span data-ttu-id="ad8a0-120">**Pour changer l'ordre des colonnes**</span><span class="sxs-lookup"><span data-stu-id="ad8a0-120">**To change the column order**</span></span>  
  
 <span data-ttu-id="ad8a0-121">Cette tâche ne peut pas être effectuée à l'aide d'instructions Transact-SQL.</span><span class="sxs-lookup"><span data-stu-id="ad8a0-121">This task cannot be performed using Transact-SQL statements.</span></span>  
  
###  <a name="TsqlExample"></a>  
