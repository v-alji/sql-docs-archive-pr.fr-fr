---
title: Exécuter le Moniteur système | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- System Monitor [SQL Server], running
- Windows System Monitor [SQL Server], running
- remote procedure calls [SQL Server]
- starting Windows NT System Monitor
- RPC
ms.assetid: 05297984-bc8d-43df-829c-032387f7ea61
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3dd0baf32402d69e36dc5120d0259b2f8d689897
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707391"
---
# <a name="run-system-monitor"></a><span data-ttu-id="0ad3e-102">Exécuter le Moniteur système</span><span class="sxs-lookup"><span data-stu-id="0ad3e-102">Run System Monitor</span></span>
  <span data-ttu-id="0ad3e-103">Le Moniteur système utilise les appels de procédures distantes (RPC) pour collecter les informations de Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ad3e-103">System Monitor uses remote procedure calls (RPCs) to collect information from Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ad3e-104">Tout utilisateur qui dispose des autorisations Microsoft Windows pour exécuter le Moniteur système peut l'utiliser pour surveiller le fonctionnement de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ad3e-104">Any user who has Microsoft Windows permissions to run System Monitor can use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ad3e-105">Lorsque vous utilisez le Moniteur système ou l'Analyseur de performances, vous ne pouvez pas vous connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonctionnant sous Microsoft Windows 98.</span><span class="sxs-lookup"><span data-stu-id="0ad3e-105">When using System Monitor or Performance Monitor, you cannot connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on Windows 98.</span></span>  
  
 <span data-ttu-id="0ad3e-106">Comme avec tous les outils d'analyse de performances, attendez-vous à une certaine diminution des performances due à une surcharge du système, lorsque vous utilisez le Moniteur système pour surveiller [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ad3e-106">As with all performance monitoring tools, expect some performance overhead when you use System Monitor to monitor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0ad3e-107">La surcharge effective de toute instance particulière dépend de la plateforme matérielle, du nombre de compteurs et de la fréquence de mise à jour choisie.</span><span class="sxs-lookup"><span data-stu-id="0ad3e-107">The actual overhead in any specific instance depends on the hardware platform, the number of counters, and the selected update interval.</span></span> <span data-ttu-id="0ad3e-108">Cependant, l'intégration du Moniteur système à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est conçue pour minimiser toute diminution des performances.</span><span class="sxs-lookup"><span data-stu-id="0ad3e-108">However, the integration of System Monitor with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is designed to minimize any reduction in performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0ad3e-109">Si vous avez sélectionné les compteurs de performances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour les surveiller via le composant logiciel enfichable Moniteur système, vous verrez ces compteurs même si [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ne s'exécute pas.</span><span class="sxs-lookup"><span data-stu-id="0ad3e-109">If you have selected [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performance counters to monitor in the System Monitor snap-in, you will see the counters even if [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not running.</span></span>  
  
 <span data-ttu-id="0ad3e-110">Pour plus d’informations sur le démarrage du Moniteur système, consultez [Démarrer le Moniteur système &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span><span class="sxs-lookup"><span data-stu-id="0ad3e-110">For information about starting System Monitor, see [Start System Monitor &#40;Windows&#41;](../performance/start-system-monitor-windows.md).</span></span>  
  
  
