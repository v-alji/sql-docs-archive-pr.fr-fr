---
title: Éditeur de tâche de profilage de données (page Général) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataprofilingtask.general.f1
helpviewer_keywords:
- Data Profiling Task Editor
ms.assetid: eec15906-d757-4079-b2f6-aca4e52b3b4c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cfcdf472f817d3dd688a5f867ac74d46835ab91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611219"
---
# <a name="data-profiling-task-editor-general-page"></a><span data-ttu-id="e4d42-102">Éditeur de tâche de profilage de données (page Général)</span><span class="sxs-lookup"><span data-stu-id="e4d42-102">Data Profiling Task Editor (General Page)</span></span>
  <span data-ttu-id="e4d42-103">Utilisez la page **Général** de l' **Éditeur de tâche de profilage de données** pour configurer les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4d42-103">Use the **General** page of the **Data Profiling Task Editor** to configure the following options:</span></span>  
  
-   <span data-ttu-id="e4d42-104">Spécifiez la destination de la sortie du profil.</span><span class="sxs-lookup"><span data-stu-id="e4d42-104">Specify the destination for the profile output.</span></span>  
  
-   <span data-ttu-id="e4d42-105">Utilisez les paramètres par défaut pour simplifier la tâche de profilage d'une table ou vue unique.</span><span class="sxs-lookup"><span data-stu-id="e4d42-105">Use the default settings to simplify the task of profiling a single table or view.</span></span>  
  
 <span data-ttu-id="e4d42-106">Pour plus d’informations sur l’utilisation de la tâche de profilage des données, consultez [Configuration de la tâche de profilage des données](data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="e4d42-106">For more information about how to use the Data Profiling task, see [Setup of the Data Profiling Task](data-profiling-task.md).</span></span> <span data-ttu-id="e4d42-107">Pour plus d’informations sur l’utilisation de la visionneuse du profil des données pour analyser le résultat de la tâche de profilage des données, consultez [Visionneuse du profil des données](data-profile-viewer.md).</span><span class="sxs-lookup"><span data-stu-id="e4d42-107">For more information about how to use the Data Profile Viewer to analyze the output of the Data Profiling task, see [Data Profile Viewer](data-profile-viewer.md).</span></span>  
  
 <span data-ttu-id="e4d42-108">**Pour ouvrir la page Général de l'Éditeur de tâche de profilage de données**</span><span class="sxs-lookup"><span data-stu-id="e4d42-108">**To open the General page of the Data Profiling Task Editor**</span></span>  
  
1.  <span data-ttu-id="e4d42-109">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] doté de la tâche de profilage de données.</span><span class="sxs-lookup"><span data-stu-id="e4d42-109">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that has the Data Profiling task.</span></span>  
  
2.  <span data-ttu-id="e4d42-110">Sous l’onglet **Flux de contrôle** , double-cliquez sur la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="e4d42-110">On the **Control Flow** tab, double-click the Data Profiling task.</span></span>  
  
3.  <span data-ttu-id="e4d42-111">Dans l' **Éditeur de tâche de profilage de données**, cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="e4d42-111">In the **Data Profiling Task Editor**, click **General**.</span></span>  
  
## <a name="data-profiling-options"></a><span data-ttu-id="e4d42-112">Options de profilage des données</span><span class="sxs-lookup"><span data-stu-id="e4d42-112">Data Profiling Options</span></span>  
 <span data-ttu-id="e4d42-113">**Délai d'expiration**</span><span class="sxs-lookup"><span data-stu-id="e4d42-113">**Timeout**</span></span>  
 <span data-ttu-id="e4d42-114">Spécifiez le nombre de secondes après lesquelles la tâche de profilage des données doit expirer et ne plus s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="e4d42-114">Specify the number of seconds after which the Data Profiling task should timeout and stop running.</span></span> <span data-ttu-id="e4d42-115">La valeur par défaut est 0, ce qui indique l'absence de délai d'expiration.</span><span class="sxs-lookup"><span data-stu-id="e4d42-115">The default value is 0, which indicates no timeout.</span></span>  
  
## <a name="destination-options"></a><span data-ttu-id="e4d42-116">Options de destination</span><span class="sxs-lookup"><span data-stu-id="e4d42-116">Destination Options</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e4d42-117">Le fichier de sortie peut contenir des données sensibles qui concernent votre base de données et les données qu'elle contient.</span><span class="sxs-lookup"><span data-stu-id="e4d42-117">The output file might contain sensitive data about your database and the data that database contains.</span></span> <span data-ttu-id="e4d42-118">Pour obtenir des suggestions sur la manière de sécuriser davantage ce fichier, consultez [Accéder aux fichiers utilisés par des packages](../access-to-files-used-by-packages.md).</span><span class="sxs-lookup"><span data-stu-id="e4d42-118">For suggestions about how to make this file more secure, see [Access to Files Used by Packages](../access-to-files-used-by-packages.md).</span></span>  
  
 <span data-ttu-id="e4d42-119">**DestinationType**</span><span class="sxs-lookup"><span data-stu-id="e4d42-119">**DestinationType**</span></span>  
 <span data-ttu-id="e4d42-120">Spécifiez si la sortie du profil des données doit être enregistrée dans un fichier ou une variable :</span><span class="sxs-lookup"><span data-stu-id="e4d42-120">Specify whether to save the data profile output to a file or a variable:</span></span>  
  
|<span data-ttu-id="e4d42-121">Valeur</span><span class="sxs-lookup"><span data-stu-id="e4d42-121">Value</span></span>|<span data-ttu-id="e4d42-122">Description</span><span class="sxs-lookup"><span data-stu-id="e4d42-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4d42-123">**FileConnection**</span><span class="sxs-lookup"><span data-stu-id="e4d42-123">**FileConnection**</span></span>|<span data-ttu-id="e4d42-124">Enregistrez la sortie du profil dans un fichier à l'emplacement spécifié dans un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e4d42-124">Save the profile output to a file in the location that is specified in a File connection manager.</span></span><br /><br /> <span data-ttu-id="e4d42-125">Remarque : vous devez spécifier le gestionnaire de connexions de fichiers à utiliser dans l’option **Destination** .</span><span class="sxs-lookup"><span data-stu-id="e4d42-125">Note: You specify which File connection manager to use in the **Destination** option.</span></span>|  
|<span data-ttu-id="e4d42-126">**Variable**</span><span class="sxs-lookup"><span data-stu-id="e4d42-126">**Variable**</span></span>|<span data-ttu-id="e4d42-127">Enregistrez la sortie du profil dans une variable de package.</span><span class="sxs-lookup"><span data-stu-id="e4d42-127">Save the profile output to a package variable.</span></span><br /><br /> <span data-ttu-id="e4d42-128">Remarque : vous devez spécifier la variable de package à utiliser dans l’option **Destination** .</span><span class="sxs-lookup"><span data-stu-id="e4d42-128">Note: You specify which package variable to use in the **Destination** option.</span></span>|  
  
 <span data-ttu-id="e4d42-129">**Destination**</span><span class="sxs-lookup"><span data-stu-id="e4d42-129">**Destination**</span></span>  
 <span data-ttu-id="e4d42-130">Spécifiez le gestionnaire de connexions de fichiers ou la variable de package qui contient la sortie du profil des données :</span><span class="sxs-lookup"><span data-stu-id="e4d42-130">Specify which File connection manager or package variable contains the data profile output:</span></span>  
  
-   <span data-ttu-id="e4d42-131">Si l'option **DestinationType** est définie sur **FileConnection**, l'option **Destination** affiche les gestionnaires de connexions de fichiers disponibles.</span><span class="sxs-lookup"><span data-stu-id="e4d42-131">If the **DestinationType** option is set to **FileConnection**, the **Destination** option displays the available File connection managers.</span></span> <span data-ttu-id="e4d42-132">Choisissez l’un de ces gestionnaires de connexions ou sélectionnez \<New File connection> pour créer un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e4d42-132">Select one of these connection managers, or select \<New File connection> to create a new File connection manager.</span></span>  
  
-   <span data-ttu-id="e4d42-133">Si l'option **DestinationType** est définie sur **Variable**, l'option **Destination** affiche les variables de package disponibles dans la liste **Destination** .</span><span class="sxs-lookup"><span data-stu-id="e4d42-133">If the **DestinationType** option is set to **Variable**, the **Destination** option displays the available package variables in the **Destination** list.</span></span> <span data-ttu-id="e4d42-134">Choisissez l’une de ces variables ou sélectionnez \<New Variable> pour créer une variable.</span><span class="sxs-lookup"><span data-stu-id="e4d42-134">Select one of these variables, or select \<New Variable> to create a new variable.</span></span>  
  
 <span data-ttu-id="e4d42-135">**OverwriteDestination**</span><span class="sxs-lookup"><span data-stu-id="e4d42-135">**OverwriteDestination**</span></span>  
 <span data-ttu-id="e4d42-136">Spécifiez si le fichier de sortie est à remplacer s'il existe déjà.</span><span class="sxs-lookup"><span data-stu-id="e4d42-136">Specify whether to overwrite the output file if it already exists.</span></span> <span data-ttu-id="e4d42-137">La valeur par défaut est **False**.</span><span class="sxs-lookup"><span data-stu-id="e4d42-137">The default value is **False**.</span></span> <span data-ttu-id="e4d42-138">La valeur de cette propriété est utilisée uniquement lorsque l'option DestinationType est définie sur FileConnection.</span><span class="sxs-lookup"><span data-stu-id="e4d42-138">The value of this property is used only when the DestinationType option is set to FileConnection.</span></span> <span data-ttu-id="e4d42-139">Lorsque l'option DestinationType est définie sur Variable, la tâche remplace toujours la valeur précédente de la variable.</span><span class="sxs-lookup"><span data-stu-id="e4d42-139">When the DestinationType option is set to Variable, the task always overwrites the previous value of the variable.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e4d42-140">Si vous tentez d’exécuter la tâche de profilage des données plus d’une fois sans modifier le nom du fichier de sortie ou redéfinir la valeur de la propriété **OverwriteDestination** sur **True**, la tâche échoue et affiche un message indiquant que le fichier de sortie existe déjà.</span><span class="sxs-lookup"><span data-stu-id="e4d42-140">If you try to run the Data Profiling task more than once without changing the output file name or changing the value of the **OverwriteDestination** property to **True**, the task fails with the message that the output file already exists.</span></span>  
  
## <a name="other-options"></a><span data-ttu-id="e4d42-141">Autres options</span><span class="sxs-lookup"><span data-stu-id="e4d42-141">Other Options</span></span>  
 <span data-ttu-id="e4d42-142">**Profil rapide**</span><span class="sxs-lookup"><span data-stu-id="e4d42-142">**Quick Profile**</span></span>  
 <span data-ttu-id="e4d42-143">Affichez le **Formulaire de profil rapide de table simple**.</span><span class="sxs-lookup"><span data-stu-id="e4d42-143">Display the **Single Table Quick Profile Form**.</span></span> <span data-ttu-id="e4d42-144">Ce formulaire simplifie la tâche de profilage d'une table ou d'une vue unique à l'aide des paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="e4d42-144">This form simplifies the task of profiling a single table or view by using default settings.</span></span> <span data-ttu-id="e4d42-145">Pour plus d’informations, consultez [Formulaire de profil rapide de table simple &#40;tâche de profilage des données&#41;](single-table-quick-profile-form-data-profiling-task.md).</span><span class="sxs-lookup"><span data-stu-id="e4d42-145">For more information, see [Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md).</span></span>  
  
 <span data-ttu-id="e4d42-146">**Ouvrir la visionneuse de profil**</span><span class="sxs-lookup"><span data-stu-id="e4d42-146">**Open Profile Viewer**</span></span>  
 <span data-ttu-id="e4d42-147">Ouvre la visionneuse du profil des données.</span><span class="sxs-lookup"><span data-stu-id="e4d42-147">Opens the Data Profile Viewer.</span></span> <span data-ttu-id="e4d42-148">La visionneuse de profil des données autonome affiche la sortie du profil des données de la tâche de profilage des données.</span><span class="sxs-lookup"><span data-stu-id="e4d42-148">The stand-alone Data Profile Viewer displays data profile output from the Data Profiling task.</span></span> <span data-ttu-id="e4d42-149">Pour afficher la sortie du profil des données, vous devez avoir exécuté la tâche de profilage des données dans le package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] et avoir calculé les profils des données.</span><span class="sxs-lookup"><span data-stu-id="e4d42-149">You can view the data profile output after you have run the Data Profiling task inside the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package and computed the data profiles.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e4d42-150">Pour ouvrir la Visionneuse du profil des données, vous pouvez aussi exécuter DataProfileViewer.exe dans le dossier, *\<drive>* :\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="e4d42-150">You can also open the Data Profile Viewer by running the DataProfileViewer.exe in the folder, *\<drive>*:\Program Files (x86) | Program Files\Microsoft SQL Server\110\DTS\Binn.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d42-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e4d42-151">See Also</span></span>  
 <span data-ttu-id="e4d42-152">[Formulaire de profil rapide de table simple &#40;tâche de profilage des données&#41;](single-table-quick-profile-form-data-profiling-task.md) </span><span class="sxs-lookup"><span data-stu-id="e4d42-152">[Single Table Quick Profile Form &#40;Data Profiling Task&#41;](single-table-quick-profile-form-data-profiling-task.md) </span></span>  
 [<span data-ttu-id="e4d42-153">Éditeur de tâche de profilage de données &#40;page Demandes de profil&#41;</span><span class="sxs-lookup"><span data-stu-id="e4d42-153">Data Profiling Task Editor &#40;Profile Requests Page&#41;</span></span>](data-profiling-task-editor-profile-requests-page.md)  
  
  
