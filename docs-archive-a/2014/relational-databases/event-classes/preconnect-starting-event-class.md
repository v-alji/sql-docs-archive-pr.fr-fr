---
title: PreConnect:Starting, classe d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
topic_type:
- apiref
helpviewer_keywords:
- PreConnect:Starting Event Class
ms.assetid: d43ed0ad-3dbd-42e0-9cef-8320b8d87497
author: stevestein
ms.author: sstein
ms.openlocfilehash: 67b642d369c73cc144af31f835786613766045f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611764"
---
# <a name="preconnectstarting-event-class"></a><span data-ttu-id="f2fdf-102">PreConnect:Starting, classe d'événements</span><span class="sxs-lookup"><span data-stu-id="f2fdf-102">PreConnect:Starting Event Class</span></span>
  <span data-ttu-id="f2fdf-103">La classe d'événements  PreConnect:Starting indique quand un déclencheur LOGON ou la fonction classifieur du gouverneur de ressources commence à s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-103">The PreConnect:Starting event class indicates when a LOGON trigger or the Resource Governor classifier function starts execution.</span></span>  
  
## <a name="preconnectstarting-event-class-data-columns"></a><span data-ttu-id="f2fdf-104">Colonnes de données de la classe d'événements PreConnect:Starting</span><span class="sxs-lookup"><span data-stu-id="f2fdf-104">PreConnect:Starting Event Class Data Columns</span></span>  
  
|<span data-ttu-id="f2fdf-105">Nom de la colonne de données</span><span class="sxs-lookup"><span data-stu-id="f2fdf-105">Data column name</span></span>|<span data-ttu-id="f2fdf-106">Type de données</span><span class="sxs-lookup"><span data-stu-id="f2fdf-106">Data type</span></span>|<span data-ttu-id="f2fdf-107">Description</span><span class="sxs-lookup"><span data-stu-id="f2fdf-107">Description</span></span>|<span data-ttu-id="f2fdf-108">ID de la colonne</span><span class="sxs-lookup"><span data-stu-id="f2fdf-108">Column ID</span></span>|<span data-ttu-id="f2fdf-109">Filtrable</span><span class="sxs-lookup"><span data-stu-id="f2fdf-109">Filterable</span></span>|  
|----------------------|---------------|-----------------|---------------|----------------|  
|<span data-ttu-id="f2fdf-110">EventClass</span><span class="sxs-lookup"><span data-stu-id="f2fdf-110">EventClass</span></span>|`int`|<span data-ttu-id="f2fdf-111">215</span><span class="sxs-lookup"><span data-stu-id="f2fdf-111">215</span></span>|<span data-ttu-id="f2fdf-112">27</span><span class="sxs-lookup"><span data-stu-id="f2fdf-112">27</span></span>|<span data-ttu-id="f2fdf-113">Non</span><span class="sxs-lookup"><span data-stu-id="f2fdf-113">No</span></span>|  
|<span data-ttu-id="f2fdf-114">SPID</span><span class="sxs-lookup"><span data-stu-id="f2fdf-114">SPID</span></span>|`int`|<span data-ttu-id="f2fdf-115">ID du processus serveur qui déclenche cet événement.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-115">The ID of server process that fires this event.</span></span>|<span data-ttu-id="f2fdf-116">12</span><span class="sxs-lookup"><span data-stu-id="f2fdf-116">12</span></span>|<span data-ttu-id="f2fdf-117">Oui</span><span class="sxs-lookup"><span data-stu-id="f2fdf-117">Yes</span></span>|  
|<span data-ttu-id="f2fdf-118">EventSubClass</span><span class="sxs-lookup"><span data-stu-id="f2fdf-118">EventSubClass</span></span>|`int`|<span data-ttu-id="f2fdf-119">1 pour la fonction classifieur définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-119">1 for the user-defined classifier function.</span></span>|<span data-ttu-id="f2fdf-120">21</span><span class="sxs-lookup"><span data-stu-id="f2fdf-120">21</span></span>|<span data-ttu-id="f2fdf-121">Oui</span><span class="sxs-lookup"><span data-stu-id="f2fdf-121">Yes</span></span>|  
|<span data-ttu-id="f2fdf-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="f2fdf-122">StartTime</span></span>|`datetime`|<span data-ttu-id="f2fdf-123">Heure de démarrage de la fonction classifieur définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-123">The time when the user-defined classifier function starts.</span></span>|<span data-ttu-id="f2fdf-124">14</span><span class="sxs-lookup"><span data-stu-id="f2fdf-124">14</span></span>|<span data-ttu-id="f2fdf-125">Oui</span><span class="sxs-lookup"><span data-stu-id="f2fdf-125">Yes</span></span>|  
|<span data-ttu-id="f2fdf-126">ObjectID</span><span class="sxs-lookup"><span data-stu-id="f2fdf-126">ObjectID</span></span>|`int`|<span data-ttu-id="f2fdf-127">ID de l'objet classifieur défini par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-127">The ID of the user-defined classifier object.</span></span>|<span data-ttu-id="f2fdf-128">22</span><span class="sxs-lookup"><span data-stu-id="f2fdf-128">22</span></span>|<span data-ttu-id="f2fdf-129">Oui</span><span class="sxs-lookup"><span data-stu-id="f2fdf-129">Yes</span></span>|  
|<span data-ttu-id="f2fdf-130">ObjectName</span><span class="sxs-lookup"><span data-stu-id="f2fdf-130">ObjectName</span></span>|`nvarchar(256)`|<span data-ttu-id="f2fdf-131">Nom en deux parties de la fonction classifieur définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-131">The two-part name of the classifier user-defined function.</span></span> <span data-ttu-id="f2fdf-132">Par exemple, dbo.classifier.</span><span class="sxs-lookup"><span data-stu-id="f2fdf-132">For example, dbo.classifier.</span></span>|<span data-ttu-id="f2fdf-133">34</span><span class="sxs-lookup"><span data-stu-id="f2fdf-133">34</span></span>|<span data-ttu-id="f2fdf-134">Oui</span><span class="sxs-lookup"><span data-stu-id="f2fdf-134">Yes</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2fdf-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f2fdf-135">See Also</span></span>  
 <span data-ttu-id="f2fdf-136">[Événements étendus](../extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="f2fdf-136">[Extended Events](../extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="f2fdf-137">[PreConnect : Completed, classe d’événements](preconnect-completed-event-class.md) </span><span class="sxs-lookup"><span data-stu-id="f2fdf-137">[PreConnect:Completed Event Class](preconnect-completed-event-class.md) </span></span>  
 [<span data-ttu-id="f2fdf-138">gouverneur de ressources</span><span class="sxs-lookup"><span data-stu-id="f2fdf-138">Resource Governor</span></span>](../resource-governor/resource-governor.md)  
  
  
