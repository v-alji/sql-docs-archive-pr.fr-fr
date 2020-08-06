---
title: Exemples de tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script task [Integration Services], examples
- examples [Integration Services]
- SSIS Script task, examples
ms.assetid: b0dd77ee-ee11-4cd9-87aa-61dd67f2fe1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 920d2ee5cc2e64db1048d10522d9be644794e55b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701291"
---
# <a name="script-task-examples"></a><span data-ttu-id="354a0-102">Exemples de tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-102">Script Task Examples</span></span>
  <span data-ttu-id="354a0-103">La tâche de script est un outil polyvalent que vous pouvez utiliser dans un package pour remplir presque toutes les conditions requises qui ne sont pas satisfaites par les tâches incluses dans [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="354a0-103">The Script task is a multi-purpose tool that you can use in a package to fill almost any requirement that is not met by the tasks included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="354a0-104">Cette rubrique répertorie des exemples de code de tâche de script qui montrent quelques-unes des fonctionnalités disponibles.</span><span class="sxs-lookup"><span data-stu-id="354a0-104">This topic lists Script task code samples that demonstrate some of the available functionality.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="354a0-105">Si vous souhaitez créer des tâches que vous pouvez réutiliser plus facilement dans plusieurs packages, envisagez d'utiliser le code indiqué dans ces exemples de tâche de script comme point de départ pour des tâches personnalisées.</span><span class="sxs-lookup"><span data-stu-id="354a0-105">If you want to create tasks that you can more easily reuse across multiple packages, consider using the code in these Script task samples as the starting point for custom tasks.</span></span> <span data-ttu-id="354a0-106">Pour plus d’informations, consultez [Développement d’une tâche personnalisée](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span><span class="sxs-lookup"><span data-stu-id="354a0-106">For more information, see [Developing a Custom Task](../extending-packages-custom-objects/task/developing-a-custom-task.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="354a0-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="354a0-107">In This Section</span></span>  
  
### <a name="example-topics"></a><span data-ttu-id="354a0-108">Rubriques d'exemples</span><span class="sxs-lookup"><span data-stu-id="354a0-108">Example Topics</span></span>  
 <span data-ttu-id="354a0-109">Cette section contient des exemples de code qui montrent différentes utilisations des classes [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] que vous pouvez incorporer dans une tâche de script [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="354a0-109">This section contains code examples that demonstrate various uses of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that you can incorporate into an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Script task:</span></span>  
  
 [<span data-ttu-id="354a0-110">Détection d’un fichier plat vide à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-110">Detecting an Empty Flat File with the Script Task</span></span>](../extending-packages-scripting-task-examples/detecting-an-empty-flat-file-with-the-script-task.md)  
 <span data-ttu-id="354a0-111">Vérifie un fichier plat pour déterminer s'il contient des lignes de données, puis enregistre le résultat dans une variable à utiliser dans le cadre du branchement de flux de contrôle.</span><span class="sxs-lookup"><span data-stu-id="354a0-111">Checks a flat file to determine whether it contains rows of data, and saves the result to a variable for use in control flow branching.</span></span>  
  
 [<span data-ttu-id="354a0-112">Création d’une liste pour la boucle Foreach à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-112">Gathering a List for the ForEach Loop with the Script Task</span></span>](../extending-packages-scripting-task-examples/gathering-a-list-for-the-foreach-loop-with-the-script-task.md)  
 <span data-ttu-id="354a0-113">Rassemble la liste des fichiers qui répondent aux critères spécifiés par l'utilisateur et renseigne une variable à des fins d'utilisation ultérieure par l'énumérateur Foreach à partir d'une variable.</span><span class="sxs-lookup"><span data-stu-id="354a0-113">Gathers a list of files that meet user-specified criteria, and populates a variable for later use by the Foreach from Variable Enumerator.</span></span>  
  
 [<span data-ttu-id="354a0-114">Interrogation d’Active Directory avec la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-114">Querying the Active Directory with the Script Task</span></span>](../extending-packages-scripting-task-examples/querying-the-active-directory-with-the-script-task.md)  
 <span data-ttu-id="354a0-115">Extrait des informations utilisateur d’Active Directory en fonction de la valeur d’une variable [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], en utilisant des classes de l’espace de noms System.DirectoryServices.</span><span class="sxs-lookup"><span data-stu-id="354a0-115">Retrieves user information from Active Directory based on the value of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] variable, by using classes in the System.DirectoryServices namespace.</span></span>  
  
 [<span data-ttu-id="354a0-116">Surveillance des compteurs de performances à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-116">Monitoring Performance Counters with the Script Task</span></span>](../extending-packages-scripting-task-examples/monitoring-performance-counters-with-the-script-task.md)  
 <span data-ttu-id="354a0-117">Crée un compteur de performances personnalisé qui peut être utilisé pour suivre la progression de l’exécution d’un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], en utilisant des classes de l’espace de noms System.Diagnostics.</span><span class="sxs-lookup"><span data-stu-id="354a0-117">Creates a custom performance counter that can be used to track the execution progress of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package, by using classes in the System.Diagnostics namespace.</span></span>  
  
 [<span data-ttu-id="354a0-118">Utilisation d’images à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-118">Working with Images with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-images-with-the-script-task.md)  
 <span data-ttu-id="354a0-119">Compresse des images au format JPEG et crée des images miniatures à partir de celles-ci, en utilisant des classes de l’espace de noms System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="354a0-119">Compresses images into the JPEG format and creates thumbnail images from them, by using classes in the System.Drawing namespace.</span></span>  
  
 [<span data-ttu-id="354a0-120">Recherche d’imprimantes installées à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-120">Finding Installed Printers with the Script Task</span></span>](../extending-packages-scripting-task-examples/finding-installed-printers-with-the-script-task.md)  
 <span data-ttu-id="354a0-121">Localise des imprimantes installées qui prennent en charge un format de papier spécifique, en utilisant des classes de l’espace de noms System.Drawing.Printing.</span><span class="sxs-lookup"><span data-stu-id="354a0-121">Locates installed printers that support a specific paper size, by using classes in the System.Drawing.Printing namespace.</span></span>  
  
 [<span data-ttu-id="354a0-122">Envoi d’un message électronique HTML à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-122">Sending an HTML Mail Message with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-an-html-mail-message-with-the-script-task.md)  
 <span data-ttu-id="354a0-123">Envoie un message électronique au format HTML plutôt qu'au format texte brut.</span><span class="sxs-lookup"><span data-stu-id="354a0-123">Sends a mail message in HTML format instead of plain text format.</span></span>  
  
 [<span data-ttu-id="354a0-124">Utilisation de fichiers Excel avec la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-124">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
 <span data-ttu-id="354a0-125">Répertorie les feuilles de calcul d'un fichier Excel et vérifie l'existence d'une feuille de calcul spécifique.</span><span class="sxs-lookup"><span data-stu-id="354a0-125">Lists the worksheets in an Excel file and checks for the existence of a specific worksheet.</span></span>  
  
 [<span data-ttu-id="354a0-126">Envoi vers une file d’attente de messages privée distante à l’aide de la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-126">Sending to a Remote Private Message Queue with the Script Task</span></span>](../extending-packages-scripting-task-examples/sending-to-a-remote-private-message-queue-with-the-script-task.md)  
 <span data-ttu-id="354a0-127">Envoie un message à une file d'attente de messages privée distante.</span><span class="sxs-lookup"><span data-stu-id="354a0-127">Sends a message to a remote private message queue.</span></span>  
  
### <a name="other-examples"></a><span data-ttu-id="354a0-128">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="354a0-128">Other Examples</span></span>  
 <span data-ttu-id="354a0-129">Les rubriques suivantes contiennent également des exemples de code à utiliser avec la tâche de script :</span><span class="sxs-lookup"><span data-stu-id="354a0-129">The following topics also contain code examples for use with the Script task:</span></span>  
  
 [<span data-ttu-id="354a0-130">Utilisation de variables dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-130">Using Variables in the Script Task</span></span>](../extending-packages-scripting/task/using-variables-in-the-script-task.md)  
 <span data-ttu-id="354a0-131">Demande à l'utilisateur de confirmer la poursuite de l'exécution du package, selon la valeur d'une variable du package susceptible de dépasser la limite spécifiée dans une autre variable.</span><span class="sxs-lookup"><span data-stu-id="354a0-131">Asks the user for confirmation of whether the package should continue to run, based on the value of a package variable that may exceed the limit specified in another variable.</span></span>  
  
 [<span data-ttu-id="354a0-132">Connexion à des sources de données dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-132">Connecting to Data Sources in the Script Task</span></span>](../extending-packages-scripting/task/connecting-to-data-sources-in-the-script-task.md)  
 <span data-ttu-id="354a0-133">Extrait une connexion ou des informations de connexion auprès des gestionnaires de connexions définis dans le package.</span><span class="sxs-lookup"><span data-stu-id="354a0-133">Retrieves a connection or connection information from connection managers defined in the package.</span></span>  
  
 [<span data-ttu-id="354a0-134">Déclenchement d’événements dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-134">Raising Events in the Script Task</span></span>](../extending-packages-scripting/task/raising-events-in-the-script-task.md)  
 <span data-ttu-id="354a0-135">Génère une erreur, un avertissement ou un message d'information selon l'état de la connexion Internet sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="354a0-135">Raises an error, a warning, or an informational message based on the status of the Internet connection on the server.</span></span>  
  
 [<span data-ttu-id="354a0-136">Journalisation dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="354a0-136">Logging in the Script Task</span></span>](../extending-packages-scripting/task/logging-in-the-script-task.md)  
 <span data-ttu-id="354a0-137">Enregistre le nombre d'éléments traités par la tâche dans les modules fournisseurs d'informations activés.</span><span class="sxs-lookup"><span data-stu-id="354a0-137">Logs the number of items processed by the task to enabled log providers.</span></span>  
  
<span data-ttu-id="354a0-138">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="354a0-138">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="354a0-139">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="354a0-139">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="354a0-140">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="354a0-140">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="354a0-141">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="354a0-141">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
