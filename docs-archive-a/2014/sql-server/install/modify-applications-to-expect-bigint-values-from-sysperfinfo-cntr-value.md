---
title: Modifier les applications pour qu’elles attendent des valeurs bigint de sysperfinfo. cntr_value | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- sysperfinfo
- bigint values [SQL Server]
ms.assetid: b0345303-6e9a-4078-8148-6e1bce207b8c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 108a9b981debc95e182b16847c39a03d4b242088
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708056"
---
# <a name="modify-applications-to-expect-bigint-values-from-sysperfinfocntr_value"></a><span data-ttu-id="a7831-102">Modifier les applications pour qu'elles attendent des valeurs bigint de sysperfinfo.cntr_value</span><span class="sxs-lookup"><span data-stu-id="a7831-102">Modify applications to expect bigint values from sysperfinfo.cntr_value</span></span>
  <span data-ttu-id="a7831-103">sysperfinfo retourne une `bigint` valeur pour la colonne cntr_value.</span><span class="sxs-lookup"><span data-stu-id="a7831-103">sysperfinfo returns a `bigint` value for the cntr_value column.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a7831-104">Composant</span><span class="sxs-lookup"><span data-stu-id="a7831-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="a7831-105">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a7831-105">Corrective Action</span></span>  
 <span data-ttu-id="a7831-106">Modifiez les applications qui utilisent sysperfinfo pour vous assurer qu'elles peuvent traiter les valeurs `bigint` de la colonne cntr_value.</span><span class="sxs-lookup"><span data-stu-id="a7831-106">Modify applications that use sysperfinfo to ensure that they can handle the `bigint` values of the cntr_value column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a7831-107">sysperfinfo est une vue de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="a7831-107">sysperfinfo is a compatibility view.</span></span> <span data-ttu-id="a7831-108">Utilisez de préférence la vue de gestion dynamique sys.dm_os_performance_counter.</span><span class="sxs-lookup"><span data-stu-id="a7831-108">You should use the sys.dm_os_performance_counter dynamic management view instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7831-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7831-109">See Also</span></span>  
 <span data-ttu-id="a7831-110">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a7831-110">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a7831-111">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="a7831-111">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
