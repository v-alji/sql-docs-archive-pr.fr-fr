---
title: Objet SqlTriggerContext | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlTriggerContext object
- triggers [CLR integration]
- context [CLR integration]
ms.assetid: 472a2d0b-64ae-4877-8f11-a5620aa698b7
author: rothja
ms.author: jroth
ms.openlocfilehash: f7eae3d290a70bedee0ed9badf9e6d0503caa2bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709671"
---
# <a name="sqltriggercontext-object"></a><span data-ttu-id="eba20-102">Objet SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="eba20-102">SqlTriggerContext Object</span></span>
  <span data-ttu-id="eba20-103">La classe `SqlTriggerContext` fournit des informations de contexte sur le déclencheur.</span><span class="sxs-lookup"><span data-stu-id="eba20-103">The `SqlTriggerContext` class provides context information about the trigger.</span></span> <span data-ttu-id="eba20-104">Ces informations contextuelles comprennent le type d'action ayant provoqué l'activation du déclencheur, les colonnes qui ont été modifiées dans une opération UPDATE et, dans le cas d'un déclencheur en langage de définition de données (DDL), une structure `EventData` XML qui décrit l'opération de déclenchement.</span><span class="sxs-lookup"><span data-stu-id="eba20-104">This contextual information includes the type of action that caused the trigger to fire, which columns were modified in an UPDATE operation, and, in the case of a data definition language (DDL) trigger, an XML `EventData` structure that describes the triggering operation.</span></span> <span data-ttu-id="eba20-105">Pour plus d’informations et pour obtenir des exemples d’utilisation de la `SqlTriggerContext` classe, consultez [déclencheurs CLR](../../database-engine/dev-guide/clr-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="eba20-105">For more information and examples of how to use the `SqlTriggerContext` class, see [CLR Triggers](../../database-engine/dev-guide/clr-triggers.md).</span></span>  
  
 <span data-ttu-id="eba20-106">Pour plus d’informations, consultez la `Microsoft.SqlServer.Server.SqlTriggerContext` documentation de référence sur les classes dans la documentation du kit de développement logiciel (SDK) .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eba20-106">For more information, see the `Microsoft.SqlServer.Server.SqlTriggerContext` class reference documentation in the .NET Framework SDK documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba20-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eba20-107">See Also</span></span>  
 <span data-ttu-id="eba20-108">[Déclencheurs CLR](../../database-engine/dev-guide/clr-triggers.md) </span><span class="sxs-lookup"><span data-stu-id="eba20-108">[CLR Triggers](../../database-engine/dev-guide/clr-triggers.md) </span></span>  
 [<span data-ttu-id="eba20-109">EVENTDATA &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="eba20-109">EVENTDATA &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/eventdata-transact-sql)  
  
  
