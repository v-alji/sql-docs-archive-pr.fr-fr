---
title: Spécifier le mot clé WITH lors de l’utilisation d’indicateurs de table en mode de compatibilité 90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH keyword
- table hints [SQL Server]
ms.assetid: 7636cc85-5155-44db-baf6-df807761adb8
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ecd13475395cef4257d97eb7480f32420932e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604897"
---
# <a name="specify-the-with-keyword-when-using-table-hints-in-90-compatibility-mode"></a><span data-ttu-id="6b437-102">Spécifier le mot clé WITH lors de l'utilisation d'indicateurs de table en mode de compatibilité 90</span><span class="sxs-lookup"><span data-stu-id="6b437-102">Specify the WITH keyword when using table hints in 90 compatibility mode</span></span>
  <span data-ttu-id="6b437-103">À quelques exceptions près, les indicateurs de table ne sont pris en charge dans la clause FROM d'une requête que s'ils sont spécifiés à l'aide du mot clé WITH.</span><span class="sxs-lookup"><span data-stu-id="6b437-103">With some exceptions, table hints are supported in the FROM clause of a query only when the hints are specified by using the WITH keyword.</span></span> <span data-ttu-id="6b437-104">Pour plus d'informations, consultez les rubriques « FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)]) » et « Indicateur de table ([!INCLUDE[tsql](../../includes/tsql-md.md)]) » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6b437-104">For more information, see the topics "FROM ([!INCLUDE[tsql](../../includes/tsql-md.md)])" and "Table Hint ([!INCLUDE[tsql](../../includes/tsql-md.md)])" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="component"></a><span data-ttu-id="6b437-105">Composant</span><span class="sxs-lookup"><span data-stu-id="6b437-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="6b437-106">Action corrective</span><span class="sxs-lookup"><span data-stu-id="6b437-106">Corrective Action</span></span>  
 <span data-ttu-id="6b437-107">Modifiez les requêtes comportant des indicateurs de table dans la clause FROM en incluant le mot clé WITH avant les indicateurs de table.</span><span class="sxs-lookup"><span data-stu-id="6b437-107">Modify queries that include table hints in the FROM clause by including the WITH keyword before the table hints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b437-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b437-108">See Also</span></span>  
 <span data-ttu-id="6b437-109">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="6b437-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="6b437-110">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="6b437-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
