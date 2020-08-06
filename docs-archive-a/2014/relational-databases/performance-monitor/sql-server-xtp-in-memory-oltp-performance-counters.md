---
title: Compteurs de performance XTP (OLTP en mémoire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: fe3cbaf4-65f4-44c5-acc6-7b735cda0c5d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 4363a526ada3694e92d18cac0d7abe8a26f6a92f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698045"
---
# <a name="xtp-in-memory-oltp-performance-counters"></a><span data-ttu-id="5b8fc-102">Compteurs de performance XTP (OLTP en mémoire)</span><span class="sxs-lookup"><span data-stu-id="5b8fc-102">XTP (In-Memory OLTP) Performance Counters</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5b8fc-103">fournit des objets et des compteurs qui peuvent être utilisés par l’Analyseur de performances pour analyser l’activité de l’OLTP en mémoire.</span><span class="sxs-lookup"><span data-stu-id="5b8fc-103">provides objects and counters that can be used by Performance Monitor to monitor In-Memory OLTP activity.</span></span>  
  
##  <a name="xtp-in-memory-oltp-performance-objects"></a><a name="SQLServerPOs"></a><span data-ttu-id="5b8fc-104">Objets de performance XTP (OLTP en mémoire)</span><span class="sxs-lookup"><span data-stu-id="5b8fc-104">XTP (In-Memory OLTP) Performance Objects</span></span>  
 <span data-ttu-id="5b8fc-105">Le tableau ci-dessous décrit les objets [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b8fc-105">The following table describes [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objects.</span></span>  
  
|<span data-ttu-id="5b8fc-106">Objet de performance</span><span class="sxs-lookup"><span data-stu-id="5b8fc-106">Performance object</span></span>|<span data-ttu-id="5b8fc-107">Description</span><span class="sxs-lookup"><span data-stu-id="5b8fc-107">Description</span></span>|  
|------------------------|-----------------|  
|[<span data-ttu-id="5b8fc-108">Curseurs XTP</span><span class="sxs-lookup"><span data-stu-id="5b8fc-108">XTP Cursors</span></span>](../cursors.md)|<span data-ttu-id="5b8fc-109">L'objet de performance Curseurs XTP contient des compteurs connexes aux curseurs internes du moteur XTP.</span><span class="sxs-lookup"><span data-stu-id="5b8fc-109">The XTP Cursors performance object contains counters related to internal XTP engine cursors.</span></span> <span data-ttu-id="5b8fc-110">Les curseurs sont des blocs de construction de bas niveau que le moteur XTP utilise pour traiter les requêtes [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5b8fc-110">Cursors are the low-level building blocks the XTP engine uses to process [!INCLUDE[tsql](../../includes/tsql-md.md)] queries.</span></span> <span data-ttu-id="5b8fc-111">Par conséquent, vous ne pouvez pas les contrôler directement.</span><span class="sxs-lookup"><span data-stu-id="5b8fc-111">As such, you do not typically have direct control over them.</span></span>|  
|[<span data-ttu-id="5b8fc-112">Garbage collection XTP</span><span class="sxs-lookup"><span data-stu-id="5b8fc-112">XTP Garbage Collection</span></span>](sql-server-xtp-garbage-collection.md)|<span data-ttu-id="5b8fc-113">L'objet de performance Garbage collection XTP contient les compteurs connexes au garbage collector du moteur XTP.</span><span class="sxs-lookup"><span data-stu-id="5b8fc-113">The XTP Garbage Collection performance object contains counters related to the XTP engine's garbage collector.</span></span>|  
|[<span data-ttu-id="5b8fc-114">Processeur fantôme XTP</span><span class="sxs-lookup"><span data-stu-id="5b8fc-114">XTP Phantom Processor</span></span>](sql-server-xtp-phantom-processor.md)|<span data-ttu-id="5b8fc-115">L'objet de performance Processeur fantôme XTP contient des compteurs connexes au sous-système de traitement fantôme du moteur XTP.</span><span class="sxs-lookup"><span data-stu-id="5b8fc-115">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="5b8fc-116">Ce composant détecte les lignes fantômes dans les transactions exécutées dans le niveau d'isolation SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="5b8fc-116">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>|  
|[<span data-ttu-id="5b8fc-117">Storage XTP</span><span class="sxs-lookup"><span data-stu-id="5b8fc-117">XTP Storage</span></span>](sql-server-xtp-storage.md)|<span data-ttu-id="5b8fc-118">L'objet de performance XTP Storage contient des compteurs associés au stockage XTP dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b8fc-118">The XTP Storage performance object contains counters related to XTP storage in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5b8fc-119">Journal des transactions XTP</span><span class="sxs-lookup"><span data-stu-id="5b8fc-119">XTP Transaction Log</span></span>](sql-server-xtp-transaction-log.md)|<span data-ttu-id="5b8fc-120">L'objet de performance Journal des transactions XTP contient des compteurs de journalisation des transactions XTP dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b8fc-120">The XTP Transaction Log performance object contains counters related to XTP transaction logging in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5b8fc-121">Transactions XTP</span><span class="sxs-lookup"><span data-stu-id="5b8fc-121">XTP Transactions</span></span>](sql-server-xtp-transactions.md)|<span data-ttu-id="5b8fc-122">L'objet de performance Transactions XTP contient des compteurs connexes aux transactions du moteur XTP dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b8fc-122">The XTP Transactions performance object contains counters related to XTP engine transactions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>|  
  
  
