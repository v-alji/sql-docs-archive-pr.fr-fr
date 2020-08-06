---
title: INFORMATION_SCHEMA. SCHEMATA retourne des noms de schéma dans une base de données, et non des bases de données dans une instance | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- INFORMATION_SCHEMA.SCHEMATA view
ms.assetid: 4337b643-910d-47d7-bea8-f4052066b9a2
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cb2a34a59bf6257c188210fc7bf2aeacb70f6b7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613783"
---
# <a name="information_schemaschemata-returns-schema-names-in-a-database-not-databases-in-an-instance"></a><span data-ttu-id="1a605-102">INFORMATION_SCHEMA.SCHEMATA retourne les noms de schémas dans une base de données, pas les bases de données dans une instance</span><span class="sxs-lookup"><span data-stu-id="1a605-102">INFORMATION_SCHEMA.SCHEMATA returns schema names in a database, not databases in an instance</span></span>
  <span data-ttu-id="1a605-103">Le Conseiller de mise à niveau a détecté des instructions faisant référence à la vue INFORMATION_SCHEMA.SCHEMATA.</span><span class="sxs-lookup"><span data-stu-id="1a605-103">Upgrade Advisor detected statements that reference the INFORMATION_SCHEMA.SCHEMATA view.</span></span> <span data-ttu-id="1a605-104">Dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], cette vue retourne toutes les bases de données d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a605-104">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], this view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1a605-105">Dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ou version ultérieure, la vue retourne tous les schémas d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="1a605-105">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later, the view returns all schemas in a database.</span></span>  
  
## <a name="component"></a><span data-ttu-id="1a605-106">Composant</span><span class="sxs-lookup"><span data-stu-id="1a605-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="1a605-107">Description</span><span class="sxs-lookup"><span data-stu-id="1a605-107">Description</span></span>  
 <span data-ttu-id="1a605-108">Dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la vue INFORMATION_SCHEMA.SCHEMATA retourne toutes les bases de données d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1a605-108">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the INFORMATION_SCHEMA.SCHEMATA view returned all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1a605-109">La vue retourne tous les schémas d'une base de données, conformément à la norme SQL.</span><span class="sxs-lookup"><span data-stu-id="1a605-109">Now, the view returns all schemas in a database, which complies with the SQL Standard.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="1a605-110">Action corrective</span><span class="sxs-lookup"><span data-stu-id="1a605-110">Corrective Action</span></span>  
 <span data-ttu-id="1a605-111">Modifiez votre application pour qu’elle fasse référence à l’affichage catalogue **sys. databases** afin de retourner toutes les bases de données d’une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1a605-111">Modify your application to reference the **sys.databases** catalog view to return all databases in an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a605-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a605-112">See Also</span></span>  
 <span data-ttu-id="1a605-113">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="1a605-113">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="1a605-114">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="1a605-114">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
