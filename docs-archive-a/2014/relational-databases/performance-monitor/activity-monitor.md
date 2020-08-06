---
title: Moniteur d’activité | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Activity Monitor [SQL Server]
ms.assetid: 1e6c430d-3a2a-468e-a3d5-ef5459c36c15
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 71fd0d1172b4fcd5739a3af1a60246cc7dce3b93
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707415"
---
# <a name="activity-monitor"></a><span data-ttu-id="392e5-102">Moniteur d'activité</span><span class="sxs-lookup"><span data-stu-id="392e5-102">Activity Monitor</span></span>
  <span data-ttu-id="392e5-103">Le Moniteur d'activité affiche des informations sur les processus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et sur la façon dont ces processus affectent l'instance actuelle de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="392e5-103">Activity Monitor displays information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] processes and how these processes affect the current instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="benefits-of-activity-monitor"></a><span data-ttu-id="392e5-104">Avantages du Moniteur d'activité</span><span class="sxs-lookup"><span data-stu-id="392e5-104">Benefits of Activity Monitor</span></span>  
 <span data-ttu-id="392e5-105">Le moniteur d’activité est une fenêtre de document avec onglets qui contient les volets extensibles et réductibles suivants : **vue d’ensemble**, **tâches utilisateur actives**, **attentes de ressources**, **e/s de fichier de données**et **requêtes coûteuses récentes**.</span><span class="sxs-lookup"><span data-stu-id="392e5-105">Activity Monitor is a tabbed document window that has the following expandable and collapsible panes: **Overview**, **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries**.</span></span> <span data-ttu-id="392e5-106">Lorsqu'un volet est développé, le Moniteur d'activité interroge l'instance pour obtenir des informations.</span><span class="sxs-lookup"><span data-stu-id="392e5-106">When any pane is expanded, Activity Monitor queries the instance for information.</span></span> <span data-ttu-id="392e5-107">Lorsqu'un volet est réduit, toutes les activités d'interrogation cessent pour ce volet.</span><span class="sxs-lookup"><span data-stu-id="392e5-107">When a pane is collapsed, all querying activity stops for that pane.</span></span> <span data-ttu-id="392e5-108">Vous pouvez également développer en même temps un ou plusieurs volets pour afficher différents types d'activité sur l'instance.</span><span class="sxs-lookup"><span data-stu-id="392e5-108">You can also expand one or more panes at the same time to view different kinds of activity on the instance.</span></span>  
  
 <span data-ttu-id="392e5-109">Pour les colonnes incluses dans les volets **tâches utilisateur actives**, **attentes de ressources**, **e/s de fichier de données**et **requêtes coûteuses récentes** , vous pouvez personnaliser l’affichage des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="392e5-109">For the columns that are included in the **Active User Tasks**, **Resource Waits**, **Data File I/O**, and **Recent Expensive Queries** panes, you can customize the display in the following ways:</span></span>  
  
1.  <span data-ttu-id="392e5-110">Pour réorganiser l'ordre des colonnes, cliquez sur l'en-tête de colonne et faites-le glisser vers un autre emplacement dans le ruban de titre.</span><span class="sxs-lookup"><span data-stu-id="392e5-110">To rearrange the order of the columns, click the column heading and drag it to another location in the heading ribbon.</span></span>  
  
2.  <span data-ttu-id="392e5-111">Pour trier une colonne, cliquez sur son nom.</span><span class="sxs-lookup"><span data-stu-id="392e5-111">To sort a column, click the column name.</span></span>  
  
3.  <span data-ttu-id="392e5-112">Pour effectuer un filtrage sur une ou plusieurs colonnes, cliquez sur la flèche de déroulement de l'en-tête de colonne, puis sélectionnez une valeur.</span><span class="sxs-lookup"><span data-stu-id="392e5-112">To filter on one or more columns, click the drop-down arrow in the column heading, and then select a value.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="392e5-113">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="392e5-113">Related Tasks</span></span>  
 <span data-ttu-id="392e5-114">Utilisez les tâches suivantes pour commencer à utiliser le Moniteur d'activité :</span><span class="sxs-lookup"><span data-stu-id="392e5-114">Use the following tasks to get started with Activity Monitor:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="392e5-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="392e5-115">**Description**</span></span>|<span data-ttu-id="392e5-116">**Rubrique**</span><span class="sxs-lookup"><span data-stu-id="392e5-116">**Topic**</span></span>|  
|<span data-ttu-id="392e5-117">Décrit comment ouvrir le Moniteur d'activité et définir son intervalle d'actualisation.</span><span class="sxs-lookup"><span data-stu-id="392e5-117">Describes how to open Activity Monitor and how to set the Activity Monitor refresh interval.</span></span>|[<span data-ttu-id="392e5-118">Ouvrir le Moniteur d’activité &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="392e5-118">Open Activity Monitor &#40;SQL Server Management Studio&#41;</span></span>](../performance-monitor/open-activity-monitor-sql-server-management-studio.md)|  
|<span data-ttu-id="392e5-119">Liens vers des rubriques relatives à la surveillance des performances et de l'activité du serveur.</span><span class="sxs-lookup"><span data-stu-id="392e5-119">Links to topics for server performance and activity monitoring.</span></span>|[<span data-ttu-id="392e5-120">Analyse des performances et surveillance de l'activité du serveur</span><span class="sxs-lookup"><span data-stu-id="392e5-120">Server Performance and Activity Monitoring</span></span>](../performance/server-performance-and-activity-monitoring.md)|  
  
  
