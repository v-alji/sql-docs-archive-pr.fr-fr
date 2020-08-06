---
title: Modifier les instructions UPDATETEXT qui lisent et écrivent dans des objets BLOB (Binary Large Objects) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- UPDATETEXT statement
- text [SQL Server], UPDATETEXT statements
ms.assetid: b85da6a7-42f6-4707-a25e-3ded8958b94f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 061e7bad0bae5a74d103406265ad79195f79f7db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604920"
---
# <a name="modify-updatetext-statements-that-read-and-write-to-binary-large-objects-blobs"></a><span data-ttu-id="2ce69-102">Modifier les instructions UPDATETEXT qui lisent et écrivent dans des objets blog (binary large object)</span><span class="sxs-lookup"><span data-stu-id="2ce69-102">Modify UPDATETEXT statements that read and write to binary large objects (BLOBs)</span></span>
  <span data-ttu-id="2ce69-103">Le Conseiller de mise à niveau a détecté des instructions UPDATETEXT qui lisent et écrivent dans les mêmes objets blob (binary large object) à l'aide du même pointeur de texte.</span><span class="sxs-lookup"><span data-stu-id="2ce69-103">Upgrade Advisor detected UPDATETEXT statements that read and write to the same binary large objects (BLOB) by using the same text pointer.</span></span> [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="2ce69-104">ne prend pas en charge l'utilisation des pointeurs de texte de cette manière.</span><span class="sxs-lookup"><span data-stu-id="2ce69-104">does not support the use of text pointers in this manner.</span></span>  
  
## <a name="component"></a><span data-ttu-id="2ce69-105">Composant</span><span class="sxs-lookup"><span data-stu-id="2ce69-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="2ce69-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="2ce69-106">Corrective Action</span></span>  
 <span data-ttu-id="2ce69-107">Copiez l'objet blob dans une table temporaire ou dans une variable de table, puis réassignez la valeur dans la colonne d'origine.</span><span class="sxs-lookup"><span data-stu-id="2ce69-107">Copy the BLOB to a temporary table or to a table variable, and then assign the value back to the original column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce69-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ce69-108">See Also</span></span>  
 <span data-ttu-id="2ce69-109">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="2ce69-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="2ce69-110">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="2ce69-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
