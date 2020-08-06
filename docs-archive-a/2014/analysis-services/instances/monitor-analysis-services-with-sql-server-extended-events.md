---
title: Utiliser SQL Server événements étendus (XEvents) pour analyser Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9d12d9bc8d6a56702e1b44f8404b25681a1033f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611991"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a><span data-ttu-id="b428b-102">Utiliser des événements étendus SQL Server (XEvents) pour surveiller Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b428b-102">Use SQL Server Extended Events (XEvents) to Monitor Analysis Services</span></span>
  <span data-ttu-id="b428b-103">Analysis Services fournit des fonctionnalités de suivi par le biais de l’utilisation d' [événements étendus](../../relational-databases/extended-events/extended-events.md).</span><span class="sxs-lookup"><span data-stu-id="b428b-103">Analysis Services provides tracing capabilities through the usage of [Extended Events](../../relational-databases/extended-events/extended-events.md).</span></span>  
  
 <span data-ttu-id="b428b-104">Les événements étendus constituent une infrastructure d'événements qui est très évolutive et configurable pour les systèmes serveur.</span><span class="sxs-lookup"><span data-stu-id="b428b-104">Extended Events is an event infrastructure that is highly scalable and configurable for server systems.</span></span> <span data-ttu-id="b428b-105">Les événements étendus sont un système léger d'analyse des performances qui utilise très peu de ressources de performances.</span><span class="sxs-lookup"><span data-stu-id="b428b-105">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span>  
  
 <span data-ttu-id="b428b-106">Tous les événements de Analysis Services peuvent être capturés et ciblés sur des consommateurs spécifiques, comme défini dans [événements étendus](../../relational-databases/extended-events/extended-events.md), via XEvents.</span><span class="sxs-lookup"><span data-stu-id="b428b-106">All Analysis Services events can be captured and target to specific consumers, as defined in [Extended Events](../../relational-databases/extended-events/extended-events.md), through XEvents.</span></span>  
  
## <a name="initiating-extended-events-in-analysis-services"></a><span data-ttu-id="b428b-107">Initialisation d'événements étendus dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b428b-107">Initiating Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="b428b-108">Le traçage d'événements étendus est activé à l'aide d'une commande de script de création d'objet XMLA semblable à celle ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="b428b-108">Extended Event tracing is enabled using a similar XMLA create object script command as shown below:</span></span>  
  
```  
<Execute ...>  
   <Command>  
      <Batch ...>  
         <Create ...>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session ...>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" .../>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="b428b-109">Les éléments suivants seront définis par l'utilisateur, selon les besoins de suivi :</span><span class="sxs-lookup"><span data-stu-id="b428b-109">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="b428b-110">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="b428b-110">*trace_id*</span></span>  
 <span data-ttu-id="b428b-111">Définit l'identificateur unique pour cette trace.</span><span class="sxs-lookup"><span data-stu-id="b428b-111">Defines the unique identifier for this trace.</span></span>  
  
 <span data-ttu-id="b428b-112">*trace_name*</span><span class="sxs-lookup"><span data-stu-id="b428b-112">*trace_name*</span></span>  
 <span data-ttu-id="b428b-113">Nom donné à cette trace ; habituellement une définition compréhensible de la trace.</span><span class="sxs-lookup"><span data-stu-id="b428b-113">The name given to this trace; usually a human readable definition of the trace.</span></span> <span data-ttu-id="b428b-114">On utilise généralement la valeur *trace_id* comme nom.</span><span class="sxs-lookup"><span data-stu-id="b428b-114">It is a common practice to use the *trace_id* value as the name.</span></span>  
  
 <span data-ttu-id="b428b-115">*AS_event*</span><span class="sxs-lookup"><span data-stu-id="b428b-115">*AS_event*</span></span>  
 <span data-ttu-id="b428b-116">Événement Analysis Services à exposer.</span><span class="sxs-lookup"><span data-stu-id="b428b-116">The Analysis Services event to be exposed.</span></span> <span data-ttu-id="b428b-117">Consultez [Événements de trace Analysis Services](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) pour les noms des événements.</span><span class="sxs-lookup"><span data-stu-id="b428b-117">See [Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) for names of the events.</span></span>  
  
 <span data-ttu-id="b428b-118">*data_filename*</span><span class="sxs-lookup"><span data-stu-id="b428b-118">*data_filename*</span></span>  
 <span data-ttu-id="b428b-119">Nom du fichier qui contient les données d'événement.</span><span class="sxs-lookup"><span data-stu-id="b428b-119">The name of the file that contains the events data.</span></span> <span data-ttu-id="b428b-120">Ce nom est suffixé avec un horodatage pour éviter que les données soient écrasées si la trace est envoyée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="b428b-120">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
 <span data-ttu-id="b428b-121">*metadata_filename*</span><span class="sxs-lookup"><span data-stu-id="b428b-121">*metadata_filename*</span></span>  
 <span data-ttu-id="b428b-122">Nom du fichier qui contient les métadonnées d'événement.</span><span class="sxs-lookup"><span data-stu-id="b428b-122">The name of the file that contains the events metadata.</span></span> <span data-ttu-id="b428b-123">Ce nom est suffixé avec un horodatage pour éviter que les données soient écrasées si la trace est envoyée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="b428b-123">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
## <a name="stopping-extended-events-in-analysis-services"></a><span data-ttu-id="b428b-124">Arrêt des événements étendus dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="b428b-124">Stopping Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="b428b-125">Pour arrêter les événements étendus qui tracent l'objet, vous devez supprimer cet objet à l'aide d'une commande de script de suppression d'objet XMLA semblable à celle ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="b428b-125">To stop the Extended Events tracing object you need to delete that object using a similar XMLA delete object script command as shown below:</span></span>  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch ...>  
         <Delete ...>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="b428b-126">Les éléments suivants seront définis par l'utilisateur, selon les besoins de suivi :</span><span class="sxs-lookup"><span data-stu-id="b428b-126">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="b428b-127">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="b428b-127">*trace_id*</span></span>  
 <span data-ttu-id="b428b-128">Définit l'identificateur unique pour la trace à supprimer.</span><span class="sxs-lookup"><span data-stu-id="b428b-128">Defines the unique identifier for the trace to be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b428b-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b428b-129">See Also</span></span>  
 [<span data-ttu-id="b428b-130">Événements étendus</span><span class="sxs-lookup"><span data-stu-id="b428b-130">Extended Events</span></span>](../../relational-databases/extended-events/extended-events.md)  
  
  
