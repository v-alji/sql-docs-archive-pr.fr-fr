---
title: Spécifier les premier et dernier déclencheurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- first triggers [SQL Server]
- last triggers
- DML triggers, first or last triggers
- INSTEAD OF triggers
- AFTER triggers
ms.assetid: 9e6c7684-3dd3-46bb-b7be-523b33fae4d5
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ddb352b00dc759362c8f6ef1e861e55b6f184f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613869"
---
# <a name="specify-first-and-last-triggers"></a><span data-ttu-id="3ddae-102">Spécifier les premier et dernier déclencheurs</span><span class="sxs-lookup"><span data-stu-id="3ddae-102">Specify First and Last Triggers</span></span>
  <span data-ttu-id="3ddae-103">Vous pouvez définir l'un des déclencheurs AFTER associés à une table comme étant le premier ou le dernier déclencheur AFTER activé pour chaque action de déclenchement INSERT, DELETE et UPDATE.</span><span class="sxs-lookup"><span data-stu-id="3ddae-103">You can specify that one of the AFTER triggers associated with a table be either the first AFTER trigger or the last AFTER trigger that is fired for each INSERT, DELETE, and UPDATE triggering actions.</span></span> <span data-ttu-id="3ddae-104">L'ordre d'exécution des déclencheurs AFTER activés entre les premier et dernier déclencheurs est indéfini.</span><span class="sxs-lookup"><span data-stu-id="3ddae-104">The AFTER triggers that are fired between the first and last triggers are executed in undefined order.</span></span>  
  
 <span data-ttu-id="3ddae-105">Pour spécifier l’ordre d’exécution d’un déclencheur AFTER, utilisez la procédure stockée **sp_settriggerorder** .</span><span class="sxs-lookup"><span data-stu-id="3ddae-105">To specify the order for an AFTER trigger, use the **sp_settriggerorder** stored procedure.</span></span> <span data-ttu-id="3ddae-106">**sp_settriggerorder** comporte les options suivantes.</span><span class="sxs-lookup"><span data-stu-id="3ddae-106">**sp_settriggerorder** has the following options.</span></span>  
  
|<span data-ttu-id="3ddae-107">Option</span><span class="sxs-lookup"><span data-stu-id="3ddae-107">Option</span></span>|<span data-ttu-id="3ddae-108">Description</span><span class="sxs-lookup"><span data-stu-id="3ddae-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="3ddae-109">**Première**</span><span class="sxs-lookup"><span data-stu-id="3ddae-109">**First**</span></span>|<span data-ttu-id="3ddae-110">Spécifie que le déclencheur DML est le premier déclencheur AFTER activé dans le cadre d'une action de déclenchement.</span><span class="sxs-lookup"><span data-stu-id="3ddae-110">Specifies that the DML trigger is the first AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="3ddae-111">**Dernière**</span><span class="sxs-lookup"><span data-stu-id="3ddae-111">**Last**</span></span>|<span data-ttu-id="3ddae-112">Spécifie que le déclencheur DML est le dernier déclencheur AFTER activé dans le cadre d'une action de déclenchement.</span><span class="sxs-lookup"><span data-stu-id="3ddae-112">Specifies that the DML trigger is the last AFTER trigger fired for a triggering action.</span></span>|  
|<span data-ttu-id="3ddae-113">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="3ddae-113">**None**</span></span>|<span data-ttu-id="3ddae-114">Spécifie qu'il n'existe aucun ordre spécifique pour l'activation du déclencheur DML.</span><span class="sxs-lookup"><span data-stu-id="3ddae-114">Specifies that there is no specific order in which the DML trigger should be fired.</span></span> <span data-ttu-id="3ddae-115">Cette option est principalement destinée à réinitialiser un déclencheur qui était le premier ou le dernier déclencheur.</span><span class="sxs-lookup"><span data-stu-id="3ddae-115">Used mainly to reset a trigger from being either first or last.</span></span>|  
  
 <span data-ttu-id="3ddae-116">L’exemple suivant illustre l’utilisation de la procédure stockée **sp_settriggerorder**:</span><span class="sxs-lookup"><span data-stu-id="3ddae-116">The following example shows using **sp_settriggerorder**:</span></span>  
  
```  
sp_settriggerorder @triggername = 'MyTrigger', @order = 'first', @stmttype = 'UPDATE'  
```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3ddae-117">Le premier déclencheur et le dernier déclencheur doivent être deux déclencheurs DML distincts.</span><span class="sxs-lookup"><span data-stu-id="3ddae-117">The first and last triggers must be two different DML triggers.</span></span>  
  
 <span data-ttu-id="3ddae-118">Plusieurs déclencheurs INSERT, UPDATE et DELETE peuvent être définis simultanément sur une table.</span><span class="sxs-lookup"><span data-stu-id="3ddae-118">A table can have INSERT, UPDATE, and DELETE triggers defined on it at the same time.</span></span> <span data-ttu-id="3ddae-119">Chaque type d'instruction peut posséder ses propres premier et dernier déclencheurs à condition qu'ils soient différents.</span><span class="sxs-lookup"><span data-stu-id="3ddae-119">Each statement type can have its own first and last triggers, but they cannot be the same triggers.</span></span>  
  
 <span data-ttu-id="3ddae-120">Si le premier ou dernier déclencheur défini pour une table ne couvre pas une action de déclenchement, telle que FOR UPDATE, FOR DELETE ou FOR INSERT, aucun premier ou dernier déclencheur n'est associé aux actions manquantes.</span><span class="sxs-lookup"><span data-stu-id="3ddae-120">If the first or last trigger defined for a table does not cover a triggering action, such as not covering FOR UPDATE, FOR DELETE, or FOR INSERT, there is no first or last trigger for the missing actions.</span></span>  
  
 <span data-ttu-id="3ddae-121">Un déclencheur INSTEAD OF ne peut pas être défini en tant que premier ou dernier déclencheur.</span><span class="sxs-lookup"><span data-stu-id="3ddae-121">INSTEAD OF triggers cannot be specified as first or last triggers.</span></span> <span data-ttu-id="3ddae-122">Il est activé avant l'apport de mises à jour aux tables sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="3ddae-122">INSTEAD OF triggers are fired before updates are made to the underlying tables.</span></span> <span data-ttu-id="3ddae-123">Si des mises à jour sont apportées par un déclencheur INSTEAD OF à des tables sous-jacentes, elles se produisent avant l'activation des déclencheurs AFTER définis sur la table.</span><span class="sxs-lookup"><span data-stu-id="3ddae-123">If updates are made by an INSTEAD OF trigger to underlying tables, the updates occur before any AFTER triggers defined on the table are fired.</span></span> <span data-ttu-id="3ddae-124">Par exemple, si un déclencheur INSTEAD OF INSERT sur une vue insère des données dans une table de base et si la table de base contient un déclencheur INSTEAD OF INSERT et trois déclencheurs AFTER INSERT, le déclencheur INSTEAD OF INSERT sur la table de base est activé au lieu de l'action d'insertion, et les déclencheurs AFTER sur la table de base sont activés après toute action d'insertion sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="3ddae-124">For example, if an INSTEAD OF INSERT trigger on a view inserts data into a base table and the base table itself contains an INSTEAD OF INSERT trigger and three AFTER INSERT triggers, the INSTEAD OF INSERT trigger on the base table is fired instead of the inserting action, and the AFTER triggers on the base table are fired after any inserting action on the base table.</span></span> <span data-ttu-id="3ddae-125">Pour plus d'informations, consultez [DML Triggers](dml-triggers.md).</span><span class="sxs-lookup"><span data-stu-id="3ddae-125">For more information, see [DML Triggers](dml-triggers.md).</span></span>  
  
 <span data-ttu-id="3ddae-126">Si une instruction ALTER TRIGGER modifie un premier ou un dernier déclencheur, l’attribut **First** ou **Last** est supprimé et l’ordre d’exécution prend la valeur **None**.</span><span class="sxs-lookup"><span data-stu-id="3ddae-126">If an ALTER TRIGGER statement changes a first or last trigger, the **First** or **Last** attribute is dropped and the order value is set to **None**.</span></span> <span data-ttu-id="3ddae-127">L’ordre d’exécution doit être réinitialisé à l’aide de **sp_settriggerorder**.</span><span class="sxs-lookup"><span data-stu-id="3ddae-127">The order must be reset by using **sp_settriggerorder**.</span></span>  
  
 <span data-ttu-id="3ddae-128">La fonction OBJECTPROPERTY signale si un déclencheur est défini comme le premier ou le dernier à l’aide des propriétés **ExecIsFirstTrigger** et **ExecIsLastTrigger**.</span><span class="sxs-lookup"><span data-stu-id="3ddae-128">The OBJECTPROPERTY function reports whether a trigger is a first or last trigger by using the properties **ExecIsFirstTrigger** and **ExecIsLastTrigger**.</span></span>  
  
 <span data-ttu-id="3ddae-129">La réplication génère automatiquement un premier déclencheur pour toute table qui est incluse dans un abonnement avec mise à jour immédiate ou en attente.</span><span class="sxs-lookup"><span data-stu-id="3ddae-129">Replication automatically generates a first trigger for any table that is included in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="3ddae-130">Elle nécessite un déclencheur qui soit le premier.</span><span class="sxs-lookup"><span data-stu-id="3ddae-130">Replication requires that its trigger be the first trigger.</span></span> <span data-ttu-id="3ddae-131">Elle génère une erreur si vous essayez d'inclure une table détenant un premier déclencheur dans un abonnement mis à jour immédiatement ou en attente.</span><span class="sxs-lookup"><span data-stu-id="3ddae-131">Replication raises an error when you try to include a table with a first trigger in an immediate updating or queued updating subscription.</span></span> <span data-ttu-id="3ddae-132">Si vous tentez de définir un déclencheur comme premier déclencheur après qu’une table a été incluse dans un abonnement, **sp_settriggerorder** retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="3ddae-132">If you try to make a trigger a first trigger after a table has been included in a subscription, **sp_settriggerorder** returns an error.</span></span> <span data-ttu-id="3ddae-133">Si vous utilisez ALTER sur le déclencheur de réplication ou si vous utilisez **sp_settriggerorder** pour que l’ordre corresponde au premier déclencheur ou pour qu’il n’y ait aucun ordre spécifique, l’abonnement ne fonctionnera pas correctement.</span><span class="sxs-lookup"><span data-stu-id="3ddae-133">If you use ALTER on the replication trigger or use **sp_settriggerorder** to change the replication trigger to a last or none trigger, the subscription will not function correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ddae-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3ddae-134">See Also</span></span>  
 <span data-ttu-id="3ddae-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3ddae-135">[OBJECTPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/objectpropertyex-transact-sql) </span></span>  
 [<span data-ttu-id="3ddae-136">sp_settriggerorder &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3ddae-136">sp_settriggerorder &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-settriggerorder-transact-sql)  
  
  
