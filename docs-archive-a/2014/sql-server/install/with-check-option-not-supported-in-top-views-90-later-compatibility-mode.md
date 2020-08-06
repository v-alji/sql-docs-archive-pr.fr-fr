---
title: L’OPTION WITH CHECK OPTION n’est pas prise en charge dans les vues qui contiennent TOP en mode de compatibilité 90 ou ultérieur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- TOP clause
- WITH CHECK OPTION clause
ms.assetid: 1b9581d0-bad9-43e0-b8fc-f32d8a8a04ca
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee7775c875e33f104341a1da39f5fe6c9326f284
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604834"
---
# <a name="with-check-option-is-not-supported-in-views-that-contain-top-in-90-or-later-compatibility-modes"></a><span data-ttu-id="b73a9-102">L'option WITH CHECK OPTION n'est pas prise en charge dans les vues contenant TOP en mode de compatibilité 90 ou ultérieur</span><span class="sxs-lookup"><span data-stu-id="b73a9-102">WITH CHECK OPTION is not supported in views that contain TOP in 90 or later compatibility modes</span></span>
  <span data-ttu-id="b73a9-103">Le Conseiller de mise à niveau a détecté qu'une vue est définie à l'aide du mot clé WITH CHECK OPTION et d'une clause TOP dans l'instruction SELECT de la vue ou dans une vue référencée.</span><span class="sxs-lookup"><span data-stu-id="b73a9-103">Upgrade Advisor detected a view that uses the WITH CHECK OPTION and a TOP clause in the SELECT statement of the view or in a referenced view.</span></span> <span data-ttu-id="b73a9-104">Les vues ainsi définies autorisent de manière incorrecte la modification des données par le biais de la vue, ce qui peut produire des résultats imprécis lorsque la base de données est définie en mode de compatibilité 80 ou antérieur.</span><span class="sxs-lookup"><span data-stu-id="b73a9-104">Views defined this way incorrectly allow data to be modified through the view and may produce inaccurate results when the database compatibility mode is set to 80 and earlier.</span></span> <span data-ttu-id="b73a9-105">Les données ne peuvent pas être insérées ou mises à jour par le biais d'une vue qui utilise le mot clé WITH CHECK OPTION si la vue ou une vue référencée utilise la clause TOP et que la base de données est définie en mode de compatibilité 90 ou ultérieur.</span><span class="sxs-lookup"><span data-stu-id="b73a9-105">Data cannot be inserted or updated through a view that uses WITH CHECK OPTION when the view or a referenced view uses the TOP clause and the database compatibility mode is set to 90 or later.</span></span>  
  
## <a name="component"></a><span data-ttu-id="b73a9-106">Composant</span><span class="sxs-lookup"><span data-stu-id="b73a9-106">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="b73a9-107">Action corrective</span><span class="sxs-lookup"><span data-stu-id="b73a9-107">Corrective Action</span></span>  
 <span data-ttu-id="b73a9-108">Lorsque vous effectuez une mise à niveau, les bases de données utilisateur conservent leur mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="b73a9-108">When you upgrade, user databases maintain their compatibility mode.</span></span> <span data-ttu-id="b73a9-109">Avant de définir la base de données en mode de compatibilité 100 ou ultérieur, modifiez les vues qui utilisent WITH CHECK OPTION et TOP si la modification des données par le biais de la vue est requise.</span><span class="sxs-lookup"><span data-stu-id="b73a9-109">Before you change the database compatibility mode to 100 or later, modify views that use both WITH CHECK OPTION and TOP if data modification through the view is required.</span></span> <span data-ttu-id="b73a9-110">Pour plus d’informations, consultez [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b73a9-110">For more information, see [sp_dbcmptlevel &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dbcmptlevel-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73a9-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b73a9-111">See Also</span></span>  
 <span data-ttu-id="b73a9-112">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="b73a9-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="b73a9-113">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="b73a9-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
