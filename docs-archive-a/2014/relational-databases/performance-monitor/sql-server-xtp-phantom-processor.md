---
title: Processeur fantôme XTP | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
ms.assetid: 0f691b3d-a8fd-4459-ad21-2cfc8574a8c0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 14158b7097427b6704cf5e747fa998a11217ecd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698040"
---
# <a name="xtp-phantom-processor"></a><span data-ttu-id="6be0d-102">Processeur fantôme XTP</span><span class="sxs-lookup"><span data-stu-id="6be0d-102">XTP Phantom Processor</span></span>
  <span data-ttu-id="6be0d-103">L'objet de performance Processeur fantôme XTP contient des compteurs connexes au sous-système de traitement fantôme du moteur XTP.</span><span class="sxs-lookup"><span data-stu-id="6be0d-103">The XTP Phantom Processor performance object contains counters related to the XTP engine's phantom processing subsystem.</span></span> <span data-ttu-id="6be0d-104">Ce composant détecte les lignes fantômes dans les transactions exécutées dans le niveau d'isolation SERIALIZABLE.</span><span class="sxs-lookup"><span data-stu-id="6be0d-104">This component is responsible for detecting phantom rows in transactions running at the SERIALIZABLE isolation level.</span></span>  
  
 <span data-ttu-id="6be0d-105">Ce tableau décrit les compteurs **Processeur fantôme XTP** .</span><span class="sxs-lookup"><span data-stu-id="6be0d-105">This table describes the **XTP Phantom Processor** counters.</span></span>  
  
|<span data-ttu-id="6be0d-106">Compteur</span><span class="sxs-lookup"><span data-stu-id="6be0d-106">Counter</span></span>|<span data-ttu-id="6be0d-107">Description</span><span class="sxs-lookup"><span data-stu-id="6be0d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6be0d-108">**Nouvelles tentatives d'analyse d'angles inutilisés par seconde (sortie fantôme)**</span><span class="sxs-lookup"><span data-stu-id="6be0d-108">**Dusty corner scan retries/sec (Phantom-issued)**</span></span>|<span data-ttu-id="6be0d-109">Nombre de tentatives d'analyse dues à des conflits d'écriture lors des nettoyages d'angles inutilisés indiqué par le processeur fantôme (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="6be0d-109">The number of scan retries due to write conflicts during dusty corner sweeps issued by the phantom processor (on average), per second.</span></span> <span data-ttu-id="6be0d-110">Il s'agit d'un compteur de très bas niveau, non destiné au client.</span><span class="sxs-lookup"><span data-stu-id="6be0d-110">This is a very low-level counter, not intended for customer use.</span></span>|  
|<span data-ttu-id="6be0d-111">**Lignes fantômes expirées, supprimées par seconde**</span><span class="sxs-lookup"><span data-stu-id="6be0d-111">**Phantom expired rows removed/sec**</span></span>|<span data-ttu-id="6be0d-112">Nombre de lignes expirées supprimées par les analyses fantômes (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="6be0d-112">The number of expired rows removed by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6be0d-113">**Lignes expirées fantômes, touchées par seconde**</span><span class="sxs-lookup"><span data-stu-id="6be0d-113">**Phantom expired rows touched/sec**</span></span>|<span data-ttu-id="6be0d-114">Nombre de lignes expirées touchées par les analyses fantômes (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="6be0d-114">The number of expired rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6be0d-115">**Lignes expirant fantômes, touchées par seconde**</span><span class="sxs-lookup"><span data-stu-id="6be0d-115">**Phantom expiring rows touched/sec**</span></span>|<span data-ttu-id="6be0d-116">Nombre de lignes expirant touchées par les analyses fantômes (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="6be0d-116">The number of expiring rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6be0d-117">**Lignes fantômes touchées par seconde**</span><span class="sxs-lookup"><span data-stu-id="6be0d-117">**Phantom rows touched/sec**</span></span>|<span data-ttu-id="6be0d-118">Nombre de lignes touchées par les analyses fantômes (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="6be0d-118">The number of rows touched by phantom scans (on average), per second.</span></span>|  
|<span data-ttu-id="6be0d-119">**Analyses fantômes démarrées par seconde**</span><span class="sxs-lookup"><span data-stu-id="6be0d-119">**Phantom scans started/sec**</span></span>|<span data-ttu-id="6be0d-120">Nombre d'analyses fantômes démarrées (en moyenne), par seconde.</span><span class="sxs-lookup"><span data-stu-id="6be0d-120">The number of phantom scans started (on average), per second.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6be0d-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6be0d-121">See Also</span></span>  
 [<span data-ttu-id="6be0d-122">Les compteurs de performances de l’OLTP en mémoire &#40;de XTP&#41;</span><span class="sxs-lookup"><span data-stu-id="6be0d-122">XTP &#40;In-Memory OLTP&#41; Performance Counters</span></span>](../../integration-services/performance/performance-counters.md)  
  
  
