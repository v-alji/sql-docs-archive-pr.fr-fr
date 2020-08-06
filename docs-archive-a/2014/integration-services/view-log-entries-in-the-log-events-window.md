---
title: Afficher les entrées de journal dans la fenêtre journaux d’événements | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], viewing
- Integration Services packages, logs
- packages [Integration Services], logs
ms.assetid: c02123c3-67fc-4370-ad14-91ed259f1873
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16b6f11758d7de2c833731cd007426000a01d8ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695795"
---
# <a name="view-log-entries-in-the-log-events-window"></a><span data-ttu-id="87847-102">Afficher les entrées de journal dans la fenêtre Journaux d’événements</span><span class="sxs-lookup"><span data-stu-id="87847-102">View Log Entries in the Log Events Window</span></span>
  <span data-ttu-id="87847-103">Cette procédure explique comment exécuter un package et afficher les entrées de journal qu'il écrit.</span><span class="sxs-lookup"><span data-stu-id="87847-103">This procedure describes how to run a package and view the log entries it writes.</span></span> <span data-ttu-id="87847-104">Vous pouvez visualiser les entrées du journal en temps réel.</span><span class="sxs-lookup"><span data-stu-id="87847-104">You can view the log entries in real time.</span></span> <span data-ttu-id="87847-105">Les entrées de journal écrites dans la fenêtre **Journaux d’événements** peuvent également être copiées et enregistrées pour une analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="87847-105">The log entries that are written to the **Log Events** window can also be copied and saved for further analysis.</span></span>  
  
 <span data-ttu-id="87847-106">Il n’est pas nécessaire d’écrire les entrées de journal dans un journal pour écrire ces entrées dans la fenêtre **Journaux d’événements** .</span><span class="sxs-lookup"><span data-stu-id="87847-106">It is not necessary to write the log entries to a log to write the entries to the **Log Events** window.</span></span>  
  
### <a name="to-view-log-entries"></a><span data-ttu-id="87847-107">Pour afficher les entrées de journal</span><span class="sxs-lookup"><span data-stu-id="87847-107">To view log entries</span></span>  
  
1.  <span data-ttu-id="87847-108">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="87847-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="87847-109">Dans le menu **SSIS** , cliquez sur **Journaux d'événements**.</span><span class="sxs-lookup"><span data-stu-id="87847-109">On the **SSIS** menu, click **Log Events**.</span></span> <span data-ttu-id="87847-110">Vous pouvez éventuellement afficher la fenêtre **Journaux d’événements** en mappant la commande View.LogEvents à une combinaison de clés de votre choix dans la page **Clavier** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="87847-110">You can optionally display the **Log Events** window by mapping the View.LogEvents command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="87847-111">Dans le menu **Déboguer**, cliquez sur **Démarrer le débogage**.</span><span class="sxs-lookup"><span data-stu-id="87847-111">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="87847-112">Dès que l’exécution rencontre les événements et les messages personnalisés activés à des fins de journalisation, les entrées de journal de chaque événement ou message sont écrites dans la fenêtre **Journaux d’événements** .</span><span class="sxs-lookup"><span data-stu-id="87847-112">As the runtime encounters the events and custom messages that are enabled for logging, log entries for each event or message are written to the **Log Events** window.</span></span>  
  
4.  <span data-ttu-id="87847-113">Dans le menu **Déboguer**, cliquez sur **Arrêter le débogage**.</span><span class="sxs-lookup"><span data-stu-id="87847-113">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
     <span data-ttu-id="87847-114">Les entrées de journal restent disponibles dans la fenêtre **Journaux d’événements** jusqu’à la prochaine exécution du package, l’exécution d’un autre package ou la fermeture de [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="87847-114">The log entries remain available in the **Log Events** window until you rerun the package, run a different package, or close [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
5.  <span data-ttu-id="87847-115">Affichez les entrées de journal dans la fenêtre **Journaux d’événements** .</span><span class="sxs-lookup"><span data-stu-id="87847-115">View the log entries in the **Log Events** window.</span></span>  
  
6.  <span data-ttu-id="87847-116">Le cas échéant, cliquez sur les entrées de journal à copier, cliquez avec le bouton droit, puis cliquez sur **Copier**.</span><span class="sxs-lookup"><span data-stu-id="87847-116">Optionally, click the log entries to copy, right-click, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="87847-117">Vous pouvez également double-cliquer sur une entrée de journal, puis dans la boîte de dialogue **Entrée de journal** , afficher les détails d’une seule entrée de journal.</span><span class="sxs-lookup"><span data-stu-id="87847-117">Optionally, double-click a log entry, and in the **Log Entry** dialog box, view the details for a single log entry.</span></span>  
  
8.  <span data-ttu-id="87847-118">Dans la boîte de dialogue **Entrée de journal** , cliquez sur les flèches haut et bas pour afficher l’entrée de journal précédente ou suivante, puis cliquez sur l’icône de copie pour copier l’entrée de journal.</span><span class="sxs-lookup"><span data-stu-id="87847-118">In the **Log Entry** dialog box, click the up and down arrows to display the previous or next log entry, and click the copy icon to copy the log entry.</span></span>  
  
9. <span data-ttu-id="87847-119">Ouvrez un éditeur de texte, collez, puis enregistrez l'entrée de journal dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="87847-119">Open a text editor, paste, and then save the log entry to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87847-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87847-120">See Also</span></span>  
 [<span data-ttu-id="87847-121">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="87847-121">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
