---
title: Suppression des objets de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- deleting database objects
ms.assetid: dbb94fdf-c85b-477b-8e84-f830d259bade
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 6bd69935dbfac020c4c75bb391e7932009fd4197
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601247"
---
# <a name="deleting-database-objects"></a><span data-ttu-id="81fa0-102">Suppression des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="81fa0-102">Deleting Database Objects</span></span>
  <span data-ttu-id="81fa0-103">Pour supprimer toutes les traces de ce didacticiel, vous pouvez simplement supprimer la base de données.</span><span class="sxs-lookup"><span data-stu-id="81fa0-103">To remove all traces of this tutorial, you could just delete the database.</span></span> <span data-ttu-id="81fa0-104">Cependant, dans cette rubrique, vous allez parcourir les étapes pour inverser chaque action effectuée au cours du didacticiel.</span><span class="sxs-lookup"><span data-stu-id="81fa0-104">However, in this topic, you will go through the steps to reverse every action you took doing the tutorial.</span></span>  
  
### <a name="removing-permissions-and-objects"></a><span data-ttu-id="81fa0-105">Suppression des autorisations et des objets</span><span class="sxs-lookup"><span data-stu-id="81fa0-105">Removing permissions and objects</span></span>  
  
1.  <span data-ttu-id="81fa0-106">Avant de supprimer des objets, vérifiez que vous êtes dans la bonne base de données :</span><span class="sxs-lookup"><span data-stu-id="81fa0-106">Before you delete objects, make sure you are in the correct database:</span></span>  
  
    ```  
    USE TestData;  
    GO  
    ```  
  
2.  <span data-ttu-id="81fa0-107">Utilisez l'instruction `REVOKE` pour supprimer une autorisation d'exécution pour `Mary` sur la procédure stockée :</span><span class="sxs-lookup"><span data-stu-id="81fa0-107">Use the `REVOKE` statement to remove execute permission for `Mary` on the stored procedure:</span></span>  
  
    ```  
    REVOKE EXECUTE ON pr_Names FROM Mary;  
    GO  
  
    ```  
  
3.  <span data-ttu-id="81fa0-108">Utilisez l'instruction `DROP` pour supprimer une autorisation pour `Mary` d'accéder à la base de données `TestData` :</span><span class="sxs-lookup"><span data-stu-id="81fa0-108">Use the `DROP` statement to remove permission for `Mary` to access the `TestData` database:</span></span>  
  
    ```  
    DROP USER Mary;  
    GO  
  
    ```  
  
4.  <span data-ttu-id="81fa0-109">Utilisez l'instruction `DROP` pour supprimer une autorisation pour `Mary` d'accéder à cette instance de [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="81fa0-109">Use the `DROP` statement to remove permission for `Mary` to access this instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]:</span></span>  
  
    ```  
    DROP LOGIN [<computer_name>\Mary];  
    GO  
  
    ```  
  
5.  <span data-ttu-id="81fa0-110">Utilisez l'instruction `DROP` pour supprimer la procédure stockée `pr_Names`:</span><span class="sxs-lookup"><span data-stu-id="81fa0-110">Use the `DROP` statement to remove the store procedure `pr_Names`:</span></span>  
  
    ```  
    DROP PROC pr_Names;  
    GO  
  
    ```  
  
6.  <span data-ttu-id="81fa0-111">Utilisez l'instruction `DROP` pour supprimer la vue `vw_Names`:</span><span class="sxs-lookup"><span data-stu-id="81fa0-111">Use the `DROP` statement to remove the view `vw_Names`:</span></span>  
  
    ```  
    DROP View vw_Names;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="81fa0-112">Utilisez l'instruction `DELETE` pour supprimer toutes les lignes de la table `Products` :</span><span class="sxs-lookup"><span data-stu-id="81fa0-112">Use the `DELETE` statement to remove all rows from the `Products` table:</span></span>  
  
    ```  
    DELETE FROM Products;  
    GO  
  
    ```  
  
8.  <span data-ttu-id="81fa0-113">Utilisez l'instruction `DROP` pour supprimer la table `Products` :</span><span class="sxs-lookup"><span data-stu-id="81fa0-113">Use the `DROP` statement to remove the `Products` table:</span></span>  
  
    ```  
    DROP Table Products;  
    GO  
  
    ```  
  
9. <span data-ttu-id="81fa0-114">Vous ne pouvez pas supprimer la base de données `TestData` lorsque vous êtes dans celle-ci ; par conséquent, basculez d'abord le contexte vers une autre base de données, puis utilisez l'instruction `DROP` pour supprimer la base de données `TestData` :</span><span class="sxs-lookup"><span data-stu-id="81fa0-114">You cannot remove the `TestData` database while you are in the database; therefore, first switch context to another database, and then use the `DROP` statement to remove the `TestData` database:</span></span>  
  
    ```  
    USE MASTER;  
    GO  
    DROP DATABASE TestData;  
    GO  
  
    ```  
  
 <span data-ttu-id="81fa0-115">Cette étape conclut le didacticiel d'écriture d'instructions [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81fa0-115">This concludes the Writing [!INCLUDE[tsql](../includes/tsql-md.md)] Statements tutorial.</span></span> <span data-ttu-id="81fa0-116">N'oubliez pas que ce didacticiel est une brève présentation et ne décrit pas toutes les options des instructions utilisées.</span><span class="sxs-lookup"><span data-stu-id="81fa0-116">Remember, this tutorial is a brief overview and it does not describe all the options to the statements that are used.</span></span> <span data-ttu-id="81fa0-117">La conception et la création d'une structure de base de données efficace et la configuration de l'accès sécurisé aux données nécessitent une base de données plus complexe que celle de ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="81fa0-117">Designing and creating an efficient database structure and configuring secure access to the data requires a more complex database than that shown in this tutorial.</span></span>  
  
## <a name="return-to-sql-server-tools-portal"></a><span data-ttu-id="81fa0-118">Revenir au portail des outils SQL Server</span><span class="sxs-lookup"><span data-stu-id="81fa0-118">Return to SQL Server Tools Portal</span></span>  
 [<span data-ttu-id="81fa0-119">Tutoriel : Écriture d’instructions Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="81fa0-119">Tutorial: Writing Transact-SQL Statements</span></span>](tutorial-writing-transact-sql-statements.md)  
  
## <a name="see-also"></a><span data-ttu-id="81fa0-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81fa0-120">See Also</span></span>  
 <span data-ttu-id="81fa0-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-121">[REVOKE &#40;Transact-SQL&#41;](/sql/t-sql/statements/revoke-transact-sql) </span></span>  
 <span data-ttu-id="81fa0-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-122">[DROP USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-user-transact-sql) </span></span>  
 <span data-ttu-id="81fa0-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-123">[DROP LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-login-transact-sql) </span></span>  
 <span data-ttu-id="81fa0-124">[SUPPRIMER la procédure &#40;&#41;Transact-SQL](/sql/t-sql/statements/drop-procedure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-124">[DROP PROCEDURE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-procedure-transact-sql) </span></span>  
 <span data-ttu-id="81fa0-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-125">[DROP VIEW &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-view-transact-sql) </span></span>  
 <span data-ttu-id="81fa0-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-126">[DELETE &#40;Transact-SQL&#41;](/sql/t-sql/statements/delete-transact-sql) </span></span>  
 <span data-ttu-id="81fa0-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="81fa0-127">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 [<span data-ttu-id="81fa0-128">DROP DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="81fa0-128">DROP DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-database-audit-specification-transact-sql)  
  
  
