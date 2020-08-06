---
title: Vérifier l’intégrité d’une base de données contenant des pages suspectes | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3b1ec9fe-f6c5-46f7-aa63-6e671be1572d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3cc1f87917c78f34ec7722fa21a1a67fda40a8c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695580"
---
# <a name="check-integrity-of-database-with-suspect-pages"></a><span data-ttu-id="e446c-102">Vérifier l'intégrité d'une base de données contenant des pages suspectes</span><span class="sxs-lookup"><span data-stu-id="e446c-102">Check Integrity of Database with Suspect Pages</span></span>
  <span data-ttu-id="e446c-103">Cette règle recherche les bases de données utilisateur dont l'état de base de données a la valeur suspect.</span><span class="sxs-lookup"><span data-stu-id="e446c-103">This rule checks for user databases that have the database status set to suspect.</span></span> <span data-ttu-id="e446c-104">Lorsque le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] lit une page de la base de données contenant une erreur 824, cette page est jugée suspecte, son ID est enregistré dans la table suspect_pages dans msdb et la base de données contenant cette page prend la valeur suspecte.</span><span class="sxs-lookup"><span data-stu-id="e446c-104">When the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] reads a database page that contains an 824 error, the page is considered suspect, its page ID is recorded in the suspect_pages table in msdb, and the database that contains the page is set to suspect.</span></span>  
  
 <span data-ttu-id="e446c-105">L'erreur 824 indique qu'une erreur de cohérence logique a été détectée au cours d'une opération de lecture.</span><span class="sxs-lookup"><span data-stu-id="e446c-105">Error 824 indicates that a logical consistency error was detected during a read operation.</span></span> <span data-ttu-id="e446c-106">Cette erreur indique généralement que des données ont été endommagées par un composant défectueux du sous-système d'E/S.</span><span class="sxs-lookup"><span data-stu-id="e446c-106">This error frequently indicates data corruption caused by a faulty I/O subsystem component.</span></span> <span data-ttu-id="e446c-107">Il s'agit d'une condition d'erreur grave qui menace l'intégrité de la base de données et qui doit être immédiatement corrigée.</span><span class="sxs-lookup"><span data-stu-id="e446c-107">This is a severe error condition that threatens database integrity and must be corrected immediately.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e446c-108">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="e446c-108">Best Practices Recommendations</span></span>  
  
-   <span data-ttu-id="e446c-109">Examinez les détails de l'erreur 824 pour cette base de données dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e446c-109">Review the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the details of the 824 error for this database.</span></span>  
  
-   <span data-ttu-id="e446c-110">Effectuez une vérification complète de la cohérence de la base de données ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span><span class="sxs-lookup"><span data-stu-id="e446c-110">Complete a full database consistency check ([DBCC CHECKDB](/sql/t-sql/database-console-commands/dbcc-checkdb-transact-sql)).</span></span>  
  
-   <span data-ttu-id="e446c-111">Implémentez les actions utilisateur définies dans [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span><span class="sxs-lookup"><span data-stu-id="e446c-111">Implement the user actions that are defined in [MSSQLSERVER_824](https://go.microsoft.com/fwlink/?LinkId=81397).</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e446c-112">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="e446c-112">For More Information</span></span>  
 [<span data-ttu-id="e446c-113">Gérer la table suspect_pages &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e446c-113">Manage the suspect_pages Table &#40;SQL Server&#41;</span></span>](../backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  
