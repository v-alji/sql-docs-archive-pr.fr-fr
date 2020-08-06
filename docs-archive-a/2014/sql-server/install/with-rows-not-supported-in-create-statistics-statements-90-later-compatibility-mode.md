---
title: WITH ROWS n’est pas pris en charge dans les instructions CREATe STATISTICs dans le mode de compatibilité 90 ou ultérieur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- WITH ROWS in CREATE STATISTICS statement
ms.assetid: 197b2ecf-a1a3-4a3a-a523-a0ee919c1dde
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d28a05e7cd025e213e2cebdce9d582a9df446fea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604833"
---
# <a name="with-rows-is-not-supported-in-create-statistics-statements-in-the-compatibility-mode-of-90-or-later"></a><span data-ttu-id="a4ddb-102">La clause WITH ROWS n'est pas prise en charge dans les instructions CREATE STATISTICS en mode de compatibilité 90 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="a4ddb-102">WITH ROWS is not supported in CREATE STATISTICS statements in the compatibility mode of 90 or later</span></span>
  <span data-ttu-id="a4ddb-103">La spécification de la clause WITH ROWS dans les instructions CREATE STATISTICS n'est pas prise en charge lorsque vous exécutez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en mode de compatibilité 90 ou ultérieur.</span><span class="sxs-lookup"><span data-stu-id="a4ddb-103">Specifying WITH ROWS in CREATE STATISTICS statements is not supported when you run [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] set to the compatibility mode of 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="a4ddb-104">Composant</span><span class="sxs-lookup"><span data-stu-id="a4ddb-104">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="a4ddb-105">Action corrective</span><span class="sxs-lookup"><span data-stu-id="a4ddb-105">Corrective Action</span></span>  
 <span data-ttu-id="a4ddb-106">Modifiez les instructions CREATe STATISTICs qui incluent WITH ROWS en spécifiant WITH SAMPLE *Number* Rows, ou en spécifiant d’autres options conformes à la syntaxe documentée.</span><span class="sxs-lookup"><span data-stu-id="a4ddb-106">Modify CREATE STATISTICS statements that include WITH ROWS by specifying WITH SAMPLE *number* ROWS, or by specifying other options that comply with the documented syntax.</span></span> <span data-ttu-id="a4ddb-107">Pour plus d’informations, consultez la rubrique «CREATe STATISTICs (Transact-SQL) dans Documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="a4ddb-107">For more information, see the topic "CREATE STATISTICS (Transact-SQL) in SQL Server Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ddb-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4ddb-108">See Also</span></span>  
 <span data-ttu-id="a4ddb-109">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="a4ddb-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="a4ddb-110">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="a4ddb-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
