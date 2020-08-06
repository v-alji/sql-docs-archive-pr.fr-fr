---
title: Journalisation dans le composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], logging
ms.assetid: 17c19787-379e-43fe-9107-e36e17ecda53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c29dfffee6cacb39272aef07caa5539555cdd4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611162"
---
# <a name="logging-in-the-script-component"></a><span data-ttu-id="8d935-102">Journalisation dans le composant Script</span><span class="sxs-lookup"><span data-stu-id="8d935-102">Logging in the Script Component</span></span>
  <span data-ttu-id="8d935-103">La journalisation dans des packages [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] vous permet d'enregistrer des informations détaillées sur l'avancement, les résultats et les problèmes d'exécution en enregistrant des événements prédéfinis ou des messages définis par l'utilisateur en vue d'une analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="8d935-103">Logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="8d935-104">Le composant Script peut utiliser la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> de la classe `ScriptMain` pour enregistrer des données définies par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d935-104">The Script component can use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class to log user-defined data.</span></span> <span data-ttu-id="8d935-105">Si la journalisation est activée et que l’événement **ScriptComponentLogEntry** est sélectionné pour la journalisation sous l’onglet **Détails** de la boîte de dialogue **Configurer les journaux SSIS**, un seul appel à la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> stocke les informations sur l’événement dans tous les modules fournisseurs d’informations configurés pour la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="8d935-105">If logging is enabled, and the **ScriptComponentLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method stores the event information in all the log providers that have been configured for the data flow task.</span></span>  
  
 <span data-ttu-id="8d935-106">Voici un exemple simple de journalisation :</span><span class="sxs-lookup"><span data-stu-id="8d935-106">Here is a simple example of logging:</span></span>  
  
 `Dim bt(0) As Byte`  
  
 `Me.Log("Test Log Event", _`  
  
 `0, _`  
  
 `bt)`  
  
> [!NOTE]  
>  <span data-ttu-id="8d935-107">Bien qu'il soit possible d'exécuter la journalisation directement à partir du composant Script, il peut être préférable d'implémenter des événements plutôt que la journalisation.</span><span class="sxs-lookup"><span data-stu-id="8d935-107">Although you can perform logging directly from your Script component, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="8d935-108">L'utilisation d'événements vous permet non seulement d'activer la journalisation des messages d'événements, mais également de répondre à un événement à l'aide de gestionnaires d'événements par défaut ou définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8d935-108">When using events, not only can you enable the logging of event messages, but you can respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="8d935-109">Pour plus d’informations sur la journalisation, consultez [Journalisation Integration Services &#40;SSIS&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="8d935-109">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
<span data-ttu-id="8d935-110">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="8d935-110">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="8d935-111">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="8d935-111">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="8d935-112">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="8d935-112">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="8d935-113">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="8d935-113">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d935-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d935-114">See Also</span></span>  
 [<span data-ttu-id="8d935-115">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8d935-115">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
