---
title: Propriétés de la trace (onglet général) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.traceproperties.general.f1
helpviewer_keywords:
- Trace Properties dialog box
ms.assetid: 25227268-143b-477e-aac9-8268bcaf2078
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 30de30c88db35a41f8f118b6545d56a78b2dec79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708576"
---
# <a name="trace-properties-general-tab"></a><span data-ttu-id="7f49c-102">Propriétés de la trace (onglet Général)</span><span class="sxs-lookup"><span data-stu-id="7f49c-102">Trace Properties (General Tab)</span></span>
  <span data-ttu-id="7f49c-103">Utilisez l’onglet **Général** de la boîte de dialogue **Propriétés de la trace** pour consulter ou spécifier les propriétés d’une trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-103">Use the **General** tab of the **Trace Properties** dialog box to view or specify properties of a trace.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f49c-104">Options</span><span class="sxs-lookup"><span data-stu-id="7f49c-104">Options</span></span>  
 <span data-ttu-id="7f49c-105">**Nom de la trace**</span><span class="sxs-lookup"><span data-stu-id="7f49c-105">**Trace name**</span></span>  
 <span data-ttu-id="7f49c-106">Spécifiez le nom de la trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-106">Specify the name of the trace.</span></span>  
  
 <span data-ttu-id="7f49c-107">**Nom du fournisseur de trace**</span><span class="sxs-lookup"><span data-stu-id="7f49c-107">**Trace provider name**</span></span>  
 <span data-ttu-id="7f49c-108">Affiche le nom de l'instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui va être tracée.</span><span class="sxs-lookup"><span data-stu-id="7f49c-108">Shows the name of the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that will be traced.</span></span> <span data-ttu-id="7f49c-109">Ce champ est automatiquement rempli avec le nom du serveur que vous avez spécifié lorsque vous vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="7f49c-109">This field is populated automatically with the name of the server that you specified when you connected.</span></span> <span data-ttu-id="7f49c-110">Pour modifier le nom du fournisseur de la trace, cliquez sur **Annuler** pour fermer la boîte de dialogue et démarrez une nouvelle trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-110">To change the name of the trace provider, click **Cancel** to close the dialog box, and start a new trace.</span></span>  
  
 <span data-ttu-id="7f49c-111">**Type de fournisseur de trace**</span><span class="sxs-lookup"><span data-stu-id="7f49c-111">**Trace provider type**</span></span>  
 <span data-ttu-id="7f49c-112">Affiche le type de serveur qui fournit la trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-112">Shows the server type that is providing the trace.</span></span> <span data-ttu-id="7f49c-113">Le champ **Type de fournisseur de trace** est rempli automatiquement par le fichier de définition de trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-113">The trace definition file populates the **Trace provider type** field automatically.</span></span> <span data-ttu-id="7f49c-114">Vous ne pouvez pas modifier ce champ.</span><span class="sxs-lookup"><span data-stu-id="7f49c-114">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="7f49c-115">**version**</span><span class="sxs-lookup"><span data-stu-id="7f49c-115">**version**</span></span>  
 <span data-ttu-id="7f49c-116">Affiche la version du serveur qui fournit la trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-116">Shows the version of the server that is providing the trace.</span></span> <span data-ttu-id="7f49c-117">Le champ **Version** est rempli automatiquement par le fichier de définition de trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-117">The trace definition file populates the **Version** field automatically.</span></span> <span data-ttu-id="7f49c-118">Vous ne pouvez pas modifier ce champ.</span><span class="sxs-lookup"><span data-stu-id="7f49c-118">You cannot modify this field.</span></span>  
  
 <span data-ttu-id="7f49c-119">**Utiliser le modèle**</span><span class="sxs-lookup"><span data-stu-id="7f49c-119">**Use the template**</span></span>  
 <span data-ttu-id="7f49c-120">Sélectionnez un modèle dans le répertoire des modèles.</span><span class="sxs-lookup"><span data-stu-id="7f49c-120">Select a template from the template directory.</span></span> <span data-ttu-id="7f49c-121">Le répertoire contient les modèles par défaut et tous les modèles définis par l'utilisateur créés pour le type de fournisseur de trace actuel.</span><span class="sxs-lookup"><span data-stu-id="7f49c-121">The directory is populated with the default templates and any user-defined templates created for the current trace provider type.</span></span>  
  
 <span data-ttu-id="7f49c-122">**Enregistrer dans le fichier**</span><span class="sxs-lookup"><span data-stu-id="7f49c-122">**Save to file**</span></span>  
 <span data-ttu-id="7f49c-123">Cette option permet de capturer les données de trace dans un fichier .trc.</span><span class="sxs-lookup"><span data-stu-id="7f49c-123">Capture the trace data to a .trc file.</span></span> <span data-ttu-id="7f49c-124">L'enregistrement des données de trace vous permet de consulter et d'analyser ces données plus tard.</span><span class="sxs-lookup"><span data-stu-id="7f49c-124">Saving trace data is useful for later review and analysis.</span></span>  
  
 <span data-ttu-id="7f49c-125">**Définir la taille de fichier maximale (Mo)**</span><span class="sxs-lookup"><span data-stu-id="7f49c-125">**Set maximum file size (MB)**</span></span>  
 <span data-ttu-id="7f49c-126">Si vous décidez d'enregistrer les données de trace dans un fichier, vous devez indiquer la taille maximale de ce fichier.</span><span class="sxs-lookup"><span data-stu-id="7f49c-126">If you choose to save the trace data to a file, you must specify the maximum size of the trace file.</span></span> <span data-ttu-id="7f49c-127">La valeur par défaut est 5 mégaoctets (Mo).</span><span class="sxs-lookup"><span data-stu-id="7f49c-127">The default is 5 megabytes (MB).</span></span> <span data-ttu-id="7f49c-128">La taille maximale est uniquement limitée par le système de fichiers (NTFS, FAT) dans lequel le fichier est enregistré.</span><span class="sxs-lookup"><span data-stu-id="7f49c-128">The maximum size is limited only by the file system (NTFS, FAT) where the file is saved.</span></span>  
  
 <span data-ttu-id="7f49c-129">\<Graphic>**Enregistrer sous**</span><span class="sxs-lookup"><span data-stu-id="7f49c-129">\<Graphic> **Save As**</span></span>  
 <span data-ttu-id="7f49c-130">Une fois que vous avez choisi d'enregistrer les données dans un fichier, vous pouvez sélectionner cette icône pour modifier le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="7f49c-130">After you have selected to save, you can select this icon to change the file name.</span></span>  
  
 <span data-ttu-id="7f49c-131">**Activer la substitution de fichier**</span><span class="sxs-lookup"><span data-stu-id="7f49c-131">**Enable file rollover**</span></span>  
 <span data-ttu-id="7f49c-132">Sélectionnez cette option pour autoriser la création de fichiers supplémentaires pour accueillir les données de trace lorsque la taille de fichier maximale est atteinte.</span><span class="sxs-lookup"><span data-stu-id="7f49c-132">Select to enable the creation of additional files to accept the trace data when the maximum file size is reached.</span></span> <span data-ttu-id="7f49c-133">Chaque nouveau nom de fichier correspond au nom du fichier .trc d'origine numéroté séquentiellement.</span><span class="sxs-lookup"><span data-stu-id="7f49c-133">Each new file name consists of the original .trc file name, numbered sequentially.</span></span> <span data-ttu-id="7f49c-134">Par exemple, une fois qu’il a atteint la taille de fichier maximale, **NouvelleTrace.trc** se ferme et un nouveau fichier, **NouvelleTrace_1.trc**, s’ouvre, suivi par **NouvelleTrace_2.trc**, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7f49c-134">For example, once it reaches maximum file size, **NewTrace.trc** closes, and a new file, **NewTrace_1.trc**, opens, followed by **NewTrace_2.trc**, and so on.</span></span> <span data-ttu-id="7f49c-135">La substitution de fichier est activée par défaut lorsque vous enregistrez une trace dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="7f49c-135">File rollover is enabled by default when you save a trace to a file.</span></span>  
  
 <span data-ttu-id="7f49c-136">**Le serveur traite les données de trace**</span><span class="sxs-lookup"><span data-stu-id="7f49c-136">**Server processes trace data**</span></span>  
 <span data-ttu-id="7f49c-137">Cette option indique que le serveur exécutant la trace doit traiter les données de trace.</span><span class="sxs-lookup"><span data-stu-id="7f49c-137">Specify that the server running the trace should process the trace data.</span></span> <span data-ttu-id="7f49c-138">L'utilisation de cette option réduit la charge de travail générée par le traçage.</span><span class="sxs-lookup"><span data-stu-id="7f49c-138">Using this option reduces the performance overhead incurred by tracing.</span></span> <span data-ttu-id="7f49c-139">Lorsque cette option est activée, aucun événement n'est ignoré même en cas de charge importante.</span><span class="sxs-lookup"><span data-stu-id="7f49c-139">If selected, no events are skipped even under stress conditions.</span></span> <span data-ttu-id="7f49c-140">Si cette option n'est pas activée, c'est le Générateur de profils SQL Server qui traite les événements et il se peut que certains ne soient pas tracés en cas de conditions difficiles.</span><span class="sxs-lookup"><span data-stu-id="7f49c-140">If this check box is cleared, processing is performed by SQL Server Profiler, and there is a possibility that some events are not traced under stress conditions.</span></span>  
  
 <span data-ttu-id="7f49c-141">**Enregistrer dans la table**</span><span class="sxs-lookup"><span data-stu-id="7f49c-141">**Save to table**</span></span>  
 <span data-ttu-id="7f49c-142">Cette option permet de capturer les données de trace dans une table de base de données.</span><span class="sxs-lookup"><span data-stu-id="7f49c-142">Capture the trace data to a database table.</span></span> <span data-ttu-id="7f49c-143">L'enregistrement des données de trace vous permet de consulter et d'analyser ces données plus tard.</span><span class="sxs-lookup"><span data-stu-id="7f49c-143">Saving trace data is useful for later review and analysis.</span></span> <span data-ttu-id="7f49c-144">Ce choix peut néanmoins provoquer un surcroît de charge important sur le serveur où les données de trace sont enregistrées.</span><span class="sxs-lookup"><span data-stu-id="7f49c-144">However, saving trace data to a table can incur significant overhead on the server where the trace is being saved.</span></span> <span data-ttu-id="7f49c-145">Si possible, n'enregistrez pas la table de trace sur le serveur qui est tracé.</span><span class="sxs-lookup"><span data-stu-id="7f49c-145">If possible, do not save the trace table on the same server that is being traced.</span></span>  
  
 <span data-ttu-id="7f49c-146">\<Graphic>**Table de destination**</span><span class="sxs-lookup"><span data-stu-id="7f49c-146">\<Graphic> **Destination Table**</span></span>  
 <span data-ttu-id="7f49c-147">Une fois que vous avez choisi d'enregistrer les données de trace dans une table de base de données, vous pouvez sélectionner cette icône pour modifier le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="7f49c-147">After you have selected to save the trace data to a database table, you can select this icon to change the table name.</span></span>  
  
 <span data-ttu-id="7f49c-148">**Définir le nombre de lignes maximal (en milliers)**</span><span class="sxs-lookup"><span data-stu-id="7f49c-148">**Set maximum rows (in thousands)**</span></span>  
 <span data-ttu-id="7f49c-149">Spécifiez le nombre maximal de lignes pour l'enregistrement des données.</span><span class="sxs-lookup"><span data-stu-id="7f49c-149">Specify the largest number of rows in which to save data.</span></span> <span data-ttu-id="7f49c-150">La valeur par défaut est 1000 lignes.</span><span class="sxs-lookup"><span data-stu-id="7f49c-150">The default is 1000 rows.</span></span>  
  
 <span data-ttu-id="7f49c-151">**Activer l'heure d'arrêt de la trace**</span><span class="sxs-lookup"><span data-stu-id="7f49c-151">**Enable trace stop time**</span></span>  
 <span data-ttu-id="7f49c-152">Définissez la date et l'heure auxquelles la trace doit s'arrêter et se fermer.</span><span class="sxs-lookup"><span data-stu-id="7f49c-152">Set the date and time for the trace to end and close itself.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f49c-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f49c-153">See Also</span></span>  
 [<span data-ttu-id="7f49c-154">Créer une trace &#40;SQL Server Profiler&#41;</span><span class="sxs-lookup"><span data-stu-id="7f49c-154">Create a Trace &#40;SQL Server Profiler&#41;</span></span>](../tools/sql-server-profiler/create-a-trace-sql-server-profiler.md)  
  
  
