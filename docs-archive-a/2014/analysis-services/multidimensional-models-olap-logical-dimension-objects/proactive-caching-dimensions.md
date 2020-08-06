---
title: Mise en cache proactive (dimensions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- dimensions [Analysis Services], proactive caching
- proactive caching [Analysis Services]
ms.assetid: 7d57fe93-6e5f-4a50-844f-dd2bbdbb94a5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 50c723d46b6c51fae0ccc227b5e58cf96f72c7b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601756"
---
# <a name="proactive-caching-dimensions"></a><span data-ttu-id="b19d6-102">Mise en cache proactive (dimensions)</span><span class="sxs-lookup"><span data-stu-id="b19d6-102">Proactive Caching (Dimensions)</span></span>
  <span data-ttu-id="b19d6-103">La mise en cache proactive fournit la création et la gestion de la mise en cache MOLAP automatique pour les objets OLAP.</span><span class="sxs-lookup"><span data-stu-id="b19d6-103">Proactive caching provides automatic MOLAP cache creation and management for OLAP objects.</span></span> <span data-ttu-id="b19d6-104">Les cubes incorporent immédiatement les modifications apportées aux données dans la base de données, en fonction des notifications reçues de cette dernière.</span><span class="sxs-lookup"><span data-stu-id="b19d6-104">The cubes immediately incorporate changes that are made to the data in the database, based upon notifications received from the database.</span></span> <span data-ttu-id="b19d6-105">L'objectif de la mise en cache proactive est de fournir la performance MOLAP traditionnelle tout en conservant la rapidité et la facilité de gestion offertes par ROLAP.</span><span class="sxs-lookup"><span data-stu-id="b19d6-105">The goal of proactive caching is to provide the performance of traditional MOLAP, while retaining the immediacy and ease of management offered by ROLAP.</span></span>  
  
 <span data-ttu-id="b19d6-106">Un objet <xref:Microsoft.AnalysisServices.ProactiveCaching> simple est composé d'une spécification temporelle et d'une notification de table.</span><span class="sxs-lookup"><span data-stu-id="b19d6-106">A simple <xref:Microsoft.AnalysisServices.ProactiveCaching> object is composed of: timing specification, and table notification.</span></span> <span data-ttu-id="b19d6-107">La spécification temporelle définit le délai de mise à jour du cache après qu'une notification de modification a été reçue.</span><span class="sxs-lookup"><span data-stu-id="b19d6-107">The timing specification defines the timeframe for updating the cache after a change notification has been received.</span></span> <span data-ttu-id="b19d6-108">La notification de table définit le schéma de notification entre la table de données et l'objet <xref:Microsoft.AnalysisServices.ProactiveCaching>.</span><span class="sxs-lookup"><span data-stu-id="b19d6-108">The table notification defines the notification schema between the data table and the <xref:Microsoft.AnalysisServices.ProactiveCaching> object.</span></span>  
  
  
