---
title: Fournisseur WMI pour les classes et propriétés d’événements de serveur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event classes [WMI]
- WMI Provider for Server Events, events listed
- classes [WMI]
ms.assetid: e2916cd7-a3ed-41e6-97b4-2ee060754cbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 471e77cb7afa4e6aed441dcbbc8b3b70064f6737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707319"
---
# <a name="wmi-provider-for-server-events-classes-and-properties"></a><span data-ttu-id="63924-102">Fournisseur WMI pour les classes et propriétés d'événements serveur</span><span class="sxs-lookup"><span data-stu-id="63924-102">WMI Provider for Server Events Classes and Properties</span></span>
  <span data-ttu-id="63924-103">Les événements serveur suivants composent le modèle de programmation du fournisseur WMI pour les événements serveur.</span><span class="sxs-lookup"><span data-stu-id="63924-103">The following server events make up the programming model for the WMI Provider for Server Events.</span></span> <span data-ttu-id="63924-104">Deux catégories principales d'événements peuvent être interrogées en émettant des requêtes WQL sur le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="63924-104">There are two main categories of events that can be queried by issuing WQL queries against the provider.</span></span> <span data-ttu-id="63924-105">Il s'agit des événements DDL (Data Definition Language) et des événements de trace.</span><span class="sxs-lookup"><span data-stu-id="63924-105">These are data definition language (DDL) events and trace events.</span></span> <span data-ttu-id="63924-106">Les événements de Service Broker QUEUE_ACTIVATION et BROKER_QUEUE_DISABLED peuvent également être interrogés.</span><span class="sxs-lookup"><span data-stu-id="63924-106">The QUEUE_ACTIVATION and BROKER_QUEUE_DISABLED service broker events can also be queried.</span></span> <span data-ttu-id="63924-107">Notez la nature inclusive des arborescences suivantes.</span><span class="sxs-lookup"><span data-stu-id="63924-107">Note the inclusive nature of the following tree diagrams.</span></span> <span data-ttu-id="63924-108">L'événement DDL_ASSEMBLY_EVENTS, par exemple, inclut tout événement ALTER_ASSEMBLY, CREATE_ASSEMBLY et DROP_ASSEMBLY.</span><span class="sxs-lookup"><span data-stu-id="63924-108">The DDL_ASSEMBLY_EVENTS event, for example, includes any ALTER_ASSEMBLY, CREATE_ASSEMBLY, and DROP_ASSEMBLY event.</span></span> <span data-ttu-id="63924-109">De la même façon, l'événement TRC_FULL_TEXT inclut tout événement FT_CRAWL_ABORTED, FT_CRAWL_STARTED et FT_CRAWL_STOPPED.</span><span class="sxs-lookup"><span data-stu-id="63924-109">Similarly, the TRC_FULL_TEXT event includes any FT_CRAWL_ABORTED, FT_CRAWL_STARTED, and FT_CRAWL_STOPPED event.</span></span> <span data-ttu-id="63924-110">ALL_EVENTS couvre tous les événements DDL, événements de trace, QUEUE_ACTIVATION et BROKER_QUEUE_DISABLED.</span><span class="sxs-lookup"><span data-stu-id="63924-110">ALL_EVENTS covers all DDL events, trace events, QUEUE_ACTIVATION, and BROKER_QUEUE_DISABLED.</span></span>  
  
 <span data-ttu-id="63924-111">Pour savoir quelles propriétés d'un événement ou d'un groupe d'événements peuvent être interrogées, reportez-vous au schéma d'événement.</span><span class="sxs-lookup"><span data-stu-id="63924-111">To learn which properties can be queried from an event or event group, refer to the event schema.</span></span> <span data-ttu-id="63924-112">Par défaut, le schéma d'événement est installé dans le répertoire suivant : [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events .xsd.</span><span class="sxs-lookup"><span data-stu-id="63924-112">By default, the event schema is installed in the following directory: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span></span>  
  
 <span data-ttu-id="63924-113">Vous pouvez également vous référer au schéma d’événement publié à l’adresse [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100) .</span><span class="sxs-lookup"><span data-stu-id="63924-113">Alternatively, you can refer to the event schema published at [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
 <span data-ttu-id="63924-114">Par exemple, si vous consultez l'événement ALTER_DATABASE, vous apprendrez que son événement parent est DDL_SERVER_LEVEL_EVENTS et que ses propriétés sont `TSQLCommand` et `DatabaseName`.</span><span class="sxs-lookup"><span data-stu-id="63924-114">For example, by referring to the ALTER_DATABASE event, you will learn that its parent event is DDL_SERVER_LEVEL_EVENTS and its properties are `TSQLCommand` and `DatabaseName`.</span></span> <span data-ttu-id="63924-115">Cet événement hérite également des propriétés `SQLInstance`, `PostTime`, `ComputerName`, `SPID` et `LoginName`.</span><span class="sxs-lookup"><span data-stu-id="63924-115">The event also inherits the properties `SQLInstance`, `PostTime`, `ComputerName`, `SPID`, and `LoginName`.</span></span> <span data-ttu-id="63924-116">Il ne possède pas d'événements enfants.</span><span class="sxs-lookup"><span data-stu-id="63924-116">The event has no children events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="63924-117">Les procédures stockées système qui exécutent des opérations de type DDL peuvent également déclencher des notifications d'événements.</span><span class="sxs-lookup"><span data-stu-id="63924-117">System stored procedures that perform DDL-like operations can also fire event notifications.</span></span> <span data-ttu-id="63924-118">Testez vos notifications d'événements pour déterminer leur réponse aux procédures stockées du système qui sont exécutées.</span><span class="sxs-lookup"><span data-stu-id="63924-118">Test your event notifications to determine their responses to system stored procedures that are run.</span></span> <span data-ttu-id="63924-119">Par exemple, l’instruction CREATe TYPE et la procédure stockée **sp_addtype** déclenchent toutes deux une notification d’événement qui est créée sur un événement CREATE_TYPE.</span><span class="sxs-lookup"><span data-stu-id="63924-119">For example, the CREATE TYPE statement and **sp_addtype** stored procedure will both fire an event notification that is created on a CREATE_TYPE event.</span></span> <span data-ttu-id="63924-120">Pour plus d’informations, consultez[événements DDL](../../relational-databases/triggers/ddl-events.md).</span><span class="sxs-lookup"><span data-stu-id="63924-120">For more information, see[DDL Events](../../relational-databases/triggers/ddl-events.md).</span></span>  
  
 <span data-ttu-id="63924-121">**Événements et groupes d'événements DDL (Data Definition Language)**</span><span class="sxs-lookup"><span data-stu-id="63924-121">**Data Definition Language Events and Event Groups**</span></span>  
  
 <span data-ttu-id="63924-122">![Fournisseur WMI pour l'arborescence d'événements de serveur](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "Fournisseur WMI pour l'arborescence d'événements de serveur")</span><span class="sxs-lookup"><span data-stu-id="63924-122">![WMI Provider for Server Events Event Tree](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI Provider for Server Events Event Tree")</span></span>  
  
 <span data-ttu-id="63924-123">**Événements de trace et groupes d’événements**</span><span class="sxs-lookup"><span data-stu-id="63924-123">**Trace Events and Event Groups**</span></span>  
  
 <span data-ttu-id="63924-124">![Événements et groupes d'événements de trace](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Événements et groupes d'événements de trace")</span><span class="sxs-lookup"><span data-stu-id="63924-124">![Trace events and event groups](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Trace events and event groups")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63924-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="63924-125">See Also</span></span>  
 <span data-ttu-id="63924-126">[Fournisseur WMI pour les concepts des événements de serveur](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="63924-126">[WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span></span>  
 [<span data-ttu-id="63924-127">Utilisation de WQL avec le fournisseur WMI pour les événements de serveur</span><span class="sxs-lookup"><span data-stu-id="63924-127">Using WQL with the WMI Provider for Server Events</span></span>](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)  
  
  
