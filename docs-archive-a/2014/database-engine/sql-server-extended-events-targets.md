---
title: SQL Server les cibles d’événements étendus | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- targets [SQL Server extended events]
- extended events [SQL Server], targets
ms.assetid: e281684c-40d1-4cf9-a0d4-7ea1ecffa384
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 010b7cc29543f266b77aaf180c50173ef9f70346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601060"
---
# <a name="sql-server-extended-events-targets"></a><span data-ttu-id="58720-102">SQL Server Extended Events Targets</span><span class="sxs-lookup"><span data-stu-id="58720-102">SQL Server Extended Events Targets</span></span>
  <span data-ttu-id="58720-103">Les cibles des Événements étendus [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sont des consommateurs d'événements.</span><span class="sxs-lookup"><span data-stu-id="58720-103">[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Extended Events targets are event consumers.</span></span> <span data-ttu-id="58720-104">Les cibles peuvent écrire dans un fichier, stocker des données d'événement dans une mémoire tampon ou agréger des données d'événement.</span><span class="sxs-lookup"><span data-stu-id="58720-104">Targets can write to a file, store event data in a memory buffer, or aggregate event data.</span></span> <span data-ttu-id="58720-105">Les cibles peuvent traiter des données de façon synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-105">Targets can process data synchronously or asynchronously.</span></span>  
  
 <span data-ttu-id="58720-106">La conception des Événements étendus garantit que les cibles sont assurées de recevoir des événements une seule fois par session.</span><span class="sxs-lookup"><span data-stu-id="58720-106">The Extended Events design ensures that targets are guaranteed to receive events once and only once per session.</span></span>  
  
 <span data-ttu-id="58720-107">Les Événements étendus fournissent les cibles suivantes que vous pouvez utiliser pour une session Événements étendus :</span><span class="sxs-lookup"><span data-stu-id="58720-107">Extended Events provide the following targets that you can use for an Extended Events session:</span></span>  
  
-   [<span data-ttu-id="58720-108">Compteur d'événements</span><span class="sxs-lookup"><span data-stu-id="58720-108">Event counter</span></span>](../../2014/database-engine/event-counter-target.md)  
  
     <span data-ttu-id="58720-109">Permet de comptabiliser tous les événements qui surviennent au cours d'une session Événements étendus.</span><span class="sxs-lookup"><span data-stu-id="58720-109">Counts all specified events that occur during an Extended Events session.</span></span> <span data-ttu-id="58720-110">Permet d'obtenir des informations sur les caractéristiques de charge de travail sans ajouter la surcharge de la collecte d'événements complète.</span><span class="sxs-lookup"><span data-stu-id="58720-110">Use to obtain information about workload characteristics without adding the overhead of full event collection.</span></span> <span data-ttu-id="58720-111">Il s'agit d'une cible synchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-111">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="58720-112">Fichier d'événements</span><span class="sxs-lookup"><span data-stu-id="58720-112">Event file</span></span>](../../2014/database-engine/event-file-target.md)  
  
     <span data-ttu-id="58720-113">Permet d'enregistrer sur le disque les résultats d'une session d'événements stockés en mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="58720-113">Use to write event session output from complete memory buffers to disk.</span></span> <span data-ttu-id="58720-114">Il s'agit d'une cible asynchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-114">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="58720-115">Appariement d'événements</span><span class="sxs-lookup"><span data-stu-id="58720-115">Event pairing</span></span>](../../2014/database-engine/event-pairing-target.md)  
  
     <span data-ttu-id="58720-116">De nombreux événements surviennent sous forme de paires, tels que les acquisitions et les libérations de verrous.</span><span class="sxs-lookup"><span data-stu-id="58720-116">Many kinds of events occur in pairs, such as lock acquires and lock releases.</span></span> <span data-ttu-id="58720-117">Permet de savoir si un événement jumelé n'entre pas dans le cadre d'une correspondance.</span><span class="sxs-lookup"><span data-stu-id="58720-117">Use to determine when a specified paired event does not occur in a matched set.</span></span> <span data-ttu-id="58720-118">Il s'agit d'une cible asynchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-118">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="58720-119">Suivi d’événements pour Windows (ETW)</span><span class="sxs-lookup"><span data-stu-id="58720-119">Event Tracing for Windows (ETW)</span></span>](../relational-databases/extended-events/event-tracing-for-windows-target.md)  
  
     <span data-ttu-id="58720-120">Permet de mettre en corrélation les événements [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] avec les données d’événement du système d’exploitation Windows ou des applications.</span><span class="sxs-lookup"><span data-stu-id="58720-120">Use to correlate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] events with Windows operating system or application event data.</span></span> <span data-ttu-id="58720-121">Il s'agit d'une cible synchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-121">This is a synchronous target.</span></span>  
  
-   [<span data-ttu-id="58720-122">Histogramme</span><span class="sxs-lookup"><span data-stu-id="58720-122">Histogram</span></span>](../../2014/database-engine/histogram-target.md)  
  
     <span data-ttu-id="58720-123">À utiliser pour comptabiliser le nombre d'occurrences d'un événement donné, en fonction d'une colonne d'événement ou d'une action définie.</span><span class="sxs-lookup"><span data-stu-id="58720-123">Use to count the number of times that a specified event occurs, based on a specified event column or action.</span></span> <span data-ttu-id="58720-124">Il s'agit d'une cible asynchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-124">This is an asynchronous target.</span></span>  
  
-   [<span data-ttu-id="58720-125">Mémoire tampon en anneau</span><span class="sxs-lookup"><span data-stu-id="58720-125">Ring buffer</span></span>](../../2014/database-engine/ring-buffer-target.md)  
  
     <span data-ttu-id="58720-126">Permet de conserver les événements en mémoire selon le principe FIFO (premier entré/premier sorti) ou au cas par cas.</span><span class="sxs-lookup"><span data-stu-id="58720-126">Use to hold the event data in memory on a first-in first-out (FIFO) basis, or on a per-event FIFO basis.</span></span> <span data-ttu-id="58720-127">Il s'agit d'une cible asynchrone.</span><span class="sxs-lookup"><span data-stu-id="58720-127">This is an asynchronous target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58720-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58720-128">See Also</span></span>  
 <span data-ttu-id="58720-129">[Événements étendus](../relational-databases/extended-events/extended-events.md) </span><span class="sxs-lookup"><span data-stu-id="58720-129">[Extended Events](../relational-databases/extended-events/extended-events.md) </span></span>  
 <span data-ttu-id="58720-130">[SQL Server des packages d’événements étendus](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span><span class="sxs-lookup"><span data-stu-id="58720-130">[SQL Server Extended Events Packages](../relational-databases/extended-events/sql-server-extended-events-packages.md) </span></span>  
 <span data-ttu-id="58720-131">[SQL Server les sessions événements étendus](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span><span class="sxs-lookup"><span data-stu-id="58720-131">[SQL Server Extended Events Sessions](../relational-databases/extended-events/sql-server-extended-events-sessions.md) </span></span>  
 [<span data-ttu-id="58720-132">Moteur des événements étendus SQL Server</span><span class="sxs-lookup"><span data-stu-id="58720-132">SQL Server Extended Events Engine</span></span>](../relational-databases/extended-events/sql-server-extended-events-engine.md)  
  
  
