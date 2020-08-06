---
title: Le déclencheur AFTER imbriqué s’active même lorsque l’imbrication des déclencheurs est désactivée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- DML triggers, nested
- nested triggers option
- triggers [SQL Server], nested
ms.assetid: 94d72960-676e-40d9-81bc-08bffe778110
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: f91c04e8d69880b451c1479e2907cd1910e8f9c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710176"
---
# <a name="nested-after-trigger-fires-even-when-trigger-nesting-is-off"></a><span data-ttu-id="93d82-102">Un déclencheur AFTER imbriqué est exécuté même lorsque l'imbrication du déclencheur est OFF</span><span class="sxs-lookup"><span data-stu-id="93d82-102">Nested AFTER trigger fires even when trigger nesting is OFF</span></span>
  <span data-ttu-id="93d82-103">Le Conseiller de mise à niveau a détecté un déclencheur AFTER imbriqué à l'intérieur d'un déclencheur INSTEAD OF défini sur une ou plusieurs tables.</span><span class="sxs-lookup"><span data-stu-id="93d82-103">Upgrade Advisor detected an AFTER trigger nested inside an INSTEAD OF trigger that is defined on one or more tables.</span></span> <span data-ttu-id="93d82-104">Les déclencheurs imbriqués AFTER peuvent s'exécuter même lorsque l'option de configuration du serveur `nested triggers` a la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="93d82-104">Nested AFTER triggers may fire even when the `nested triggers` server configuration option is set to 0.</span></span>  
  
## <a name="component"></a><span data-ttu-id="93d82-105">Composant</span><span class="sxs-lookup"><span data-stu-id="93d82-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="93d82-106">Description</span><span class="sxs-lookup"><span data-stu-id="93d82-106">Description</span></span>  
 <span data-ttu-id="93d82-107">Le premier déclencheur AFTER imbriqué dans un déclencheur INSTEAD OF se déclenche même si l'option de configuration du serveur `nested triggers` est définie à 0.</span><span class="sxs-lookup"><span data-stu-id="93d82-107">The first AFTER trigger nested inside an INSTEAD OF trigger fires even if the `nested triggers` server configuration option is set to 0.</span></span> <span data-ttu-id="93d82-108">Toutefois, les déclencheurs AFTER suivants ne se déclenchent pas sous ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="93d82-108">However, under this setting, subsequent AFTER triggers do not fire.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="93d82-109">Action corrective</span><span class="sxs-lookup"><span data-stu-id="93d82-109">Corrective Action</span></span>  
 <span data-ttu-id="93d82-110">Contrôlez les déclencheurs imbriqués de vos applications afin de déterminer si ces applications sont toujours conformes aux règles d'entreprise relatives à ce nouveau comportement lorsque l'option de configuration du serveur de `nested triggers` est définie à 0, puis effectuez les modifications nécessaires.</span><span class="sxs-lookup"><span data-stu-id="93d82-110">Review your applications for nested triggers to determine whether the applications still comply with your business rules with regard to this new behavior when the `nested triggers` server configuration option is set to 0, and then make appropriate modifications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d82-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="93d82-111">See Also</span></span>  
 <span data-ttu-id="93d82-112">[Problèmes de mise à niveau Moteur de base de données](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="93d82-112">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="93d82-113">Le conseiller de mise à niveau de SQL Server 2014 &#91;nouveau&#93;</span><span class="sxs-lookup"><span data-stu-id="93d82-113">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
