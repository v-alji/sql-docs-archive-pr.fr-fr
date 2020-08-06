---
title: Architecture de l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], architecture
- architecture [CLR integration]
ms.assetid: 05e4b872-3d21-46de-b4d5-739b5f2a0cf9
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: bb32e2c7f5eb2079146a2fee64af2e2dbc1d3356
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602996"
---
# <a name="architecture-of-clr-integration"></a><span data-ttu-id="f595f-102">Architecture d'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="f595f-102">Architecture of CLR Integration</span></span>
  <span data-ttu-id="f595f-103">L'intégration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec le Common Language Runtime (CLR) .NET Framework permet aux programmeurs de base de données d'utiliser des langages tels que Visual C#, Visual Basic .NET et Visual C++.</span><span class="sxs-lookup"><span data-stu-id="f595f-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integration with the .NET Framework common language runtime (CLR) enables database programmers to use languages such as Visual C#, Visual Basic .NET, and Visual C++.</span></span> <span data-ttu-id="f595f-104">Les fonctions, procédures stockées, déclencheurs, types de données et agrégats sont parmi les types de logique métier que les programmeurs peuvent écrire avec ces langages.</span><span class="sxs-lookup"><span data-stu-id="f595f-104">Functions, stored procedures, triggers, data types, and aggregates are among the kinds of business logic that programmers can write with these languages.</span></span>  
  
 <span data-ttu-id="f595f-105">Cette section décrit l'architecture d'intégration du CLR à l'intérieur de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et la façon dont cette architecture fournit un environnement sûr, évolutif, sécurisé et efficace pour exécuter du code utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f595f-105">This section describes the architecture of CLR integration inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and how this architecture provides a safe, scalable, secure, and efficient environment to run user code.</span></span>  
  
 <span data-ttu-id="f595f-106">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="f595f-106">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="f595f-107">Environnement hébergé CLR</span><span class="sxs-lookup"><span data-stu-id="f595f-107">CLR Hosted Environment</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-clr-hosted-environment.md)  
 <span data-ttu-id="f595f-108">Discute des objectifs de conception architecturale, des mécanismes et des avantages offerts par l'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="f595f-108">Discusses architectural design goals, mechanisms, and benefits of CLR integration.</span></span>  
  
 [<span data-ttu-id="f595f-109">Performances de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="f595f-109">Performance of CLR Integration</span></span>](../../relational-databases/clr-integration/clr-integration-architecture-performance.md)  
 <span data-ttu-id="f595f-110">Traite des considérations relatives aux performance de l'architecture d'intégration du CLR.</span><span class="sxs-lookup"><span data-stu-id="f595f-110">Covers performance considerations of the CLR integration architecture.</span></span>  
  
  
