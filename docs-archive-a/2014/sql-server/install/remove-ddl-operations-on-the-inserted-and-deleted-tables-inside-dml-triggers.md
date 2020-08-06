---
title: Supprimer les opérations DDL sur les tables insérées et supprimées à l’intérieur des déclencheurs DML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- data definition language [SQL Server]
- DDL statements [SQL Server]
- DML triggers, removing DDL operations
ms.assetid: e49ba7d5-787f-4052-b985-b699195d982b
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 61f7ab78b5ab6251b7f27401d36423ec27141c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704744"
---
# <a name="remove-ddl-operations-on-the-inserted-and-deleted-tables-inside-dml-triggers"></a><span data-ttu-id="3cd90-102">Supprimer les opérations DDL sur les tables insérées et supprimées à l'intérieur des déclencheurs DML</span><span class="sxs-lookup"><span data-stu-id="3cd90-102">Remove DDL operations on the inserted and deleted tables inside DML triggers</span></span>
  <span data-ttu-id="3cd90-103">Les instructions DDL (Data Definition Language), telles que CREATe INDEX, ne peuvent pas être exécutées sur les tables inserted et Deleted dans les déclencheurs DML.</span><span class="sxs-lookup"><span data-stu-id="3cd90-103">Data definition language (DDL) statements, such as CREATE INDEX, cannot be performed on the inserted and deleted tables inside DML triggers.</span></span> <span data-ttu-id="3cd90-104">Certaines instructions DDL sur les tables insérées et supprimées sont autorisées dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cd90-104">Some DDL statements on the inserted and deleted tables are permitted in earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3cd90-105">Pour plus d'informations, consultez « Utilisation des tables insérées et supprimées » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cd90-105">For more information, see "Using the inserted and deleted Tables" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="3cd90-106">Composant</span><span class="sxs-lookup"><span data-stu-id="3cd90-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="3cd90-107">Action corrective</span><span class="sxs-lookup"><span data-stu-id="3cd90-107">Corrective Action</span></span>  
 <span data-ttu-id="3cd90-108">Supprimez toutes les opérations DDL effectuées sur les tables insérées et supprimées à l'intérieur des déclencheurs DML.</span><span class="sxs-lookup"><span data-stu-id="3cd90-108">Remove any DDL operations that are performed on the inserted and deleted tables inside DML triggers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd90-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3cd90-109">See Also</span></span>  
 <span data-ttu-id="3cd90-110">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="3cd90-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="3cd90-111">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="3cd90-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
