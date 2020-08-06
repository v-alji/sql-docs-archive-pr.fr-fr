---
title: Vérifier des requêtes (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:100644
helpviewer_keywords:
- verifying queries
- queries [SQL Server], verifying
- checking queries
ms.assetid: 1382c0c0-46dc-45f9-ab38-9bba1d347eea
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7bf24de9bdc0e8b7b7ceb33bb881812b180ce112
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610917"
---
# <a name="verify-queries-visual-database-tools"></a><span data-ttu-id="8be57-102">Vérifier des requêtes (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="8be57-102">Verify Queries (Visual Database Tools)</span></span>
  <span data-ttu-id="8be57-103">Pour éviter tout problème, vous pouvez vérifier la requête que vous avez conçue afin de vous assurer que sa syntaxe est correcte.</span><span class="sxs-lookup"><span data-stu-id="8be57-103">To avoid problems, you can check the query you have built to ensure its syntax is correct.</span></span> <span data-ttu-id="8be57-104">Cette option s’avère particulièrement utile quand vous entrez des instructions dans le [volet SQL](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8be57-104">This option is especially useful when you enter statements in the [SQL pane](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="8be57-105">Tenez compte des remarques suivantes lors de la vérification de requêtes :</span><span class="sxs-lookup"><span data-stu-id="8be57-105">Some notes to keep in mind about verifying queries:</span></span>  
  
-   <span data-ttu-id="8be57-106">Une instruction peut être valide et ne pas présenter d’erreur au moment de sa vérification, sans pour autant pouvoir être représentée dans les volets **Schéma** et **Critères**.</span><span class="sxs-lookup"><span data-stu-id="8be57-106">A statement can be valid, and therefore be verified successfully, even if it cannot be represented in the **Diagram Pane** and **Criteria Pane**.</span></span>  
  
-   <span data-ttu-id="8be57-107">La vérification SQL parvient à détecter certaines erreurs SQL, mais pas toutes.</span><span class="sxs-lookup"><span data-stu-id="8be57-107">SQL Verification can detect some, but not all SQL errors.</span></span> <span data-ttu-id="8be57-108">Lorsqu'une requête comporte une erreur n'ayant pas été détectée au cours de la vérification SQL, la base de données détecte cette erreur lors de l'exécution de la requête.</span><span class="sxs-lookup"><span data-stu-id="8be57-108">If a query contains an error not detected during SQL verification, the database will detect the error when you run the query.</span></span>  
  
-   <span data-ttu-id="8be57-109">Les requêtes contenant des paramètres ne peuvent pas être vérifiées.</span><span class="sxs-lookup"><span data-stu-id="8be57-109">Queries that contain parameters cannot be verified.</span></span>  
  
### <a name="to-verify-an-sql-statement"></a><span data-ttu-id="8be57-110">Pour vérifier une instruction SQL</span><span class="sxs-lookup"><span data-stu-id="8be57-110">To verify an SQL statement</span></span>  
  
-   <span data-ttu-id="8be57-111">Cliquez avec le bouton droit sur le **Volet SQL**, puis sélectionnez **Vérifier la syntaxe SQL** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="8be57-111">Right-click in the **SQL Pane**, and select **Verify SQL Syntax** from the shortcut menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be57-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8be57-112">See Also</span></span>  
 <span data-ttu-id="8be57-113">[Exécuter des requêtes &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="8be57-113">[Run Queries &#40;Visual Database Tools&#41;](run-queries-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="8be57-114">Effectuer des opérations de base concernant les requêtes &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="8be57-114">Perform Basic Operations with Queries &#40;Visual Database Tools&#41;</span></span>](perform-basic-operations-with-queries-visual-database-tools.md)  
  
  
