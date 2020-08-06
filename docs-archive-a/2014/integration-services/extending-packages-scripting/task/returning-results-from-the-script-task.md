---
title: Retour de résultats de la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], status information
- ExecutionValue property
- status information [Integration Services]
- TaskResult property
- SSIS Script task, status information
ms.assetid: ac06805b-c2db-44bd-af5c-5a0debe36dd7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bef3e93644377f715b5ad24e0a53df053197a03a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700019"
---
# <a name="returning-results-from-the-script-task"></a><span data-ttu-id="a600a-102">Retour de résultats de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="a600a-102">Returning Results from the Script Task</span></span>
  <span data-ttu-id="a600a-103">La tâche de script utilise la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> et la propriété facultative <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> pour renvoyer des informations d'état à l'exécution [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)], lesquelles peuvent être utilisées pour déterminer le chemin d'accès du flux de travail une fois que la tâche de script est terminée.</span><span class="sxs-lookup"><span data-stu-id="a600a-103">The Script task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> and the optional <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> properties to return status information to the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] runtime that can be used to determine the path of the workflow after the Script task has finished.</span></span>  
  
## <a name="taskresult"></a><span data-ttu-id="a600a-104">TaskResult</span><span class="sxs-lookup"><span data-stu-id="a600a-104">TaskResult</span></span>  
 <span data-ttu-id="a600a-105">La propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> indique si la tâche a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="a600a-105">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.TaskResult%2A> property reports whether the task succeeded or failed.</span></span> <span data-ttu-id="a600a-106">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a600a-106">For example:</span></span>  
  
 `Dts.TaskResult = ScriptResults.Success`  
  
## <a name="executionvalue"></a><span data-ttu-id="a600a-107">ExecutionValue</span><span class="sxs-lookup"><span data-stu-id="a600a-107">ExecutionValue</span></span>  
 <span data-ttu-id="a600a-108">La propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> renvoie facultativement un objet défini par l'utilisateur qui quantifie ou fournit des informations supplémentaires sur le succès ou l'échec de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="a600a-108">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property optionally returns a user-defined object that quantifies or provides more information about the success or failure of the Script task.</span></span> <span data-ttu-id="a600a-109">Par exemple, la tâche FTP utilise la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> pour renvoyer le nombre de fichiers transférés.</span><span class="sxs-lookup"><span data-stu-id="a600a-109">For example, the FTP task uses the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> property to return the number of files transferred.</span></span> <span data-ttu-id="a600a-110">La tâche d'exécution SQL renvoie le nombre de lignes affectées par la tâche.</span><span class="sxs-lookup"><span data-stu-id="a600a-110">The Execute SQL task returns the number of rows affected by the task.</span></span> <span data-ttu-id="a600a-111">La propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> peut également servir à déterminer le chemin d'accès du flux de travail.</span><span class="sxs-lookup"><span data-stu-id="a600a-111">The <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.ExecutionValue%2A> can also be used to determine the path of the workflow.</span></span> <span data-ttu-id="a600a-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a600a-112">For example:</span></span>  
  
 `Dim rowsAffected as Integer`  
  
 `...`  
  
 `rowsAffected = 1000`  
  
 `Dts.ExecutionValue = rowsAffected`  
  
<span data-ttu-id="a600a-113">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="a600a-113">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a600a-114">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="a600a-114">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a600a-115">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="a600a-115">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a600a-116">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="a600a-116">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
