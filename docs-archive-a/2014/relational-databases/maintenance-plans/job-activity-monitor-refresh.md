---
title: Actualisation du moniteur d’activité des travaux | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f290825f8a776c954ef802b184f7600aea5dc9d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605426"
---
# <a name="job-activity-monitor-refresh"></a><span data-ttu-id="be754-102">Actualisation du moniteur d'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="be754-102">Job Activity Monitor Refresh</span></span>
  <span data-ttu-id="be754-103">La boîte de dialogue **Paramètres d'actualisation** vous permet de configurer la fréquence à laquelle le moniteur d'activité des travaux obtient de nouvelles informations sur l'activité du serveur.</span><span class="sxs-lookup"><span data-stu-id="be754-103">Use the **Refresh Settings** dialog box to configure how often Job Activity Monitor obtains new information about server activity.</span></span> <span data-ttu-id="be754-104">Le moniteur d'activité des travaux doit exécuter des requêtes sur le serveur surveillé pour obtenir des informations pour la grille du moniteur d'activité des travaux.</span><span class="sxs-lookup"><span data-stu-id="be754-104">Job Activity Monitor must run queries on the monitored server to obtain information for the Job Activity Monitor grid.</span></span> <span data-ttu-id="be754-105">Si la fréquence d’actualisation automatique est inférieure à 30 secondes, le temps nécessaire à l’exécution des requêtes peut affecter les performances du serveur.</span><span class="sxs-lookup"><span data-stu-id="be754-105">When the auto-refresh interval is set to less than 30 seconds, the time used to run these queries can affect server performance.</span></span>  
  
 <span data-ttu-id="be754-106">Pour ouvrir cette boîte de dialogue, cliquez sur **Afficher les paramètres d'actualisation**dans la section **État** du moniteur d'activité des travaux.</span><span class="sxs-lookup"><span data-stu-id="be754-106">To open this dialog, click **View refresh settings**, in the **Status** section of Job Activity Monitor.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be754-107">Options</span><span class="sxs-lookup"><span data-stu-id="be754-107">Options</span></span>  
 <span data-ttu-id="be754-108">**Actualiser automatiquement toutes les**</span><span class="sxs-lookup"><span data-stu-id="be754-108">**Auto-refresh every**</span></span>  
 <span data-ttu-id="be754-109">Activez pour initier l'actualisation automatique des informations du moniteur d'activité.</span><span class="sxs-lookup"><span data-stu-id="be754-109">Check to initiate automatic refreshing of Activity Monitor information.</span></span> <span data-ttu-id="be754-110">Cette option est désactivée par défaut.</span><span class="sxs-lookup"><span data-stu-id="be754-110">This is off by default.</span></span>  
  
 <span data-ttu-id="be754-111">**secondes**</span><span class="sxs-lookup"><span data-stu-id="be754-111">**seconds**</span></span>  
 <span data-ttu-id="be754-112">Nombre de secondes entre deux tentatives d'actualisation automatique.</span><span class="sxs-lookup"><span data-stu-id="be754-112">The number of seconds between auto-refresh attempts.</span></span> <span data-ttu-id="be754-113">La valeur par défaut est de 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="be754-113">Defaults to 60 seconds.</span></span> <span data-ttu-id="be754-114">L'actualisation s'effectue toutes les 5 secondes lorsque la valeur spécifiée est inférieure ou égale à 5.</span><span class="sxs-lookup"><span data-stu-id="be754-114">Refreshes every 5 seconds when set to 5 or less.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be754-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be754-115">See Also</span></span>  
 [<span data-ttu-id="be754-116">Surveiller l'activité des travaux</span><span class="sxs-lookup"><span data-stu-id="be754-116">Monitor Job Activity</span></span>](../../ssms/agent/monitor-job-activity.md)  
  
  
