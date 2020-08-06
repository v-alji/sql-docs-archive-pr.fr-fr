---
title: Propriétés du serveur (page Exécution) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.swb.reportserver.serverproperties.execution.f1
ms.assetid: 53b77db1-b013-4dac-82dd-30c0de276639
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f0ec8725a0cec9e15cb6d8402f8d654320c38471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610968"
---
# <a name="server-properties-execution-page"></a><span data-ttu-id="50aa0-102">Propriétés du serveur (page Exécution)</span><span class="sxs-lookup"><span data-stu-id="50aa0-102">Server Properties (Execution Page)</span></span>
  <span data-ttu-id="50aa0-103">Utilisez cette page pour définir un délai d'attente pour l'exécution des rapports.</span><span class="sxs-lookup"><span data-stu-id="50aa0-103">Use this page to set a timeout value for report execution.</span></span> <span data-ttu-id="50aa0-104">Cette valeur s'applique à tous les rapports traités par l'instance actuelle du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="50aa0-104">This value applies to all reports that are processed by the current report server instance.</span></span> <span data-ttu-id="50aa0-105">Vous pouvez remplacer cette valeur pour des rapports individuels.</span><span class="sxs-lookup"><span data-stu-id="50aa0-105">You can override this value for individual reports.</span></span> <span data-ttu-id="50aa0-106">La valeur que vous spécifiez doit convenir à tout le traitement des rapports qui se produit sur le serveur de rapports, outre le traitement des requêtes effectué sur le serveur de base de données lorsque le serveur de rapports récupère les données utilisées dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="50aa0-106">The value you specify must accommodate all report processing that occurs on the report server, plus query processing performed on the database server when the report server retrieves data that is used in the report.</span></span>  
  
 <span data-ttu-id="50aa0-107">Pour ouvrir cette page, démarrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à une instance de serveur de rapports, cliquez avec le bouton droit sur le nom du serveur de rapports, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="50aa0-107">To open this page, start [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to a report server instance, right-click the report server name, and select **Properties**.</span></span> <span data-ttu-id="50aa0-108">Cliquez sur **Exécution** pour ouvrir cette page.</span><span class="sxs-lookup"><span data-stu-id="50aa0-108">Click **Execution** to open this page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="50aa0-109">Options</span><span class="sxs-lookup"><span data-stu-id="50aa0-109">Options</span></span>  
 <span data-ttu-id="50aa0-110">**Ne pas appliquer de délai d'attente pour l'exécution des rapports**</span><span class="sxs-lookup"><span data-stu-id="50aa0-110">**Do not timeout report execution**</span></span>  
 <span data-ttu-id="50aa0-111">Permettez à un serveur de rapports de terminer le traitement d'un rapport sans limite de temps.</span><span class="sxs-lookup"><span data-stu-id="50aa0-111">Allow a report server unlimited time to complete report processing.</span></span>  
  
 <span data-ttu-id="50aa0-112">**Limiter l'exécution du rapport au nombre de secondes suivant**</span><span class="sxs-lookup"><span data-stu-id="50aa0-112">**Limit report execution to the following number of seconds**</span></span>  
 <span data-ttu-id="50aa0-113">Définissez une contrainte de temps sur l'exécution de rapport.</span><span class="sxs-lookup"><span data-stu-id="50aa0-113">Set a time constraint on report execution.</span></span> <span data-ttu-id="50aa0-114">Le compte à rebours débute lorsque le rapport est demandé.</span><span class="sxs-lookup"><span data-stu-id="50aa0-114">The time period starts when the report is requested.</span></span> <span data-ttu-id="50aa0-115">Si la durée est dépassée avant la fin du traitement du rapport, le serveur de rapports annule le processus et toutes les requêtes intra-processus vers les sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="50aa0-115">If the time period ends before the report is fully processed, the report server cancels the process and any in-process queries to external data sources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50aa0-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50aa0-116">See Also</span></span>  
 <span data-ttu-id="50aa0-117">[Définir les propriétés du serveur de rapports &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="50aa0-117">[Set Report Server Properties &#40;Management Studio&#41;](set-report-server-properties-management-studio.md) </span></span>  
 <span data-ttu-id="50aa0-118">[Se connecter à un serveur de rapports dans Management Studio](connect-to-a-report-server-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="50aa0-118">[Connect to a Report Server in Management Studio](connect-to-a-report-server-in-management-studio.md) </span></span>  
 <span data-ttu-id="50aa0-119">[Définir les propriétés de traitement d’un rapport](../report-server/set-report-processing-properties.md) </span><span class="sxs-lookup"><span data-stu-id="50aa0-119">[Set Report Processing Properties](../report-server/set-report-processing-properties.md) </span></span>  
 <span data-ttu-id="50aa0-120">[Définition des valeurs de délai d’attente pour le traitement d’un rapport et d’un dataset partagé &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="50aa0-120">[Setting Time-out Values for Report and Shared Dataset Processing &#40;SSRS&#41;](../report-server/setting-time-out-values-for-report-and-shared-dataset-processing-ssrs.md) </span></span>  
 [<span data-ttu-id="50aa0-121">Aide du serveur de rapports dans Management Studio via la touche F1</span><span class="sxs-lookup"><span data-stu-id="50aa0-121">Report Server in Management Studio F1 Help</span></span>](report-server-in-management-studio-f1-help.md)  
  
  
