---
title: Outils externes, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- adding external tools
- external tools [SQL Server Management Studio]
- SQL Server Management Studio [SQL Server], external tools
ms.assetid: ba797203-24d0-4922-9b97-8ab483f1db14
author: stevestein
ms.author: sstein
ms.openlocfilehash: 5789dc150e45c1a0364b7acc0ea7fda443efcf17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702320"
---
# <a name="external-tools-dialog-box"></a><span data-ttu-id="f0e61-102">Boîte de dialogue Outils externes</span><span class="sxs-lookup"><span data-stu-id="f0e61-102">External Tools Dialog Box</span></span>
  <span data-ttu-id="f0e61-103">Utilisez la boîte de dialogue **Outils externes** pour ajouter des outils externes tels que SQLCMD ou le Bloc-notes au menu **Outils**.</span><span class="sxs-lookup"><span data-stu-id="f0e61-103">Use the **External Tools** dialog box to add external tools such as SQLCMD or Notepad to the **Tools** menu.</span></span> <span data-ttu-id="f0e61-104">L'ajout d'outils externes vous permet de lancer facilement d'autres applications tout en travaillant dans l'environnement [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0e61-104">Adding external tools allows you to easily launch other applications while working in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] environment.</span></span> <span data-ttu-id="f0e61-105">Vous pouvez spécifier des arguments et un répertoire de travail lors du lancement de l'outil.</span><span class="sxs-lookup"><span data-stu-id="f0e61-105">You can specify arguments and a working directory when launching the tool.</span></span> <span data-ttu-id="f0e61-106">En outre, la sortie de certains outils peut être affichée dans la fenêtre **Sortie** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-106">In addition, the output from some tools can be displayed in the **Output** window.</span></span> <span data-ttu-id="f0e61-107">La boîte de dialogue **Outils externes** est accessible via le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-107">The **External Tools** dialog box is available on the **Tools** menu.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f0e61-108">Options</span><span class="sxs-lookup"><span data-stu-id="f0e61-108">Options</span></span>  
 <span data-ttu-id="f0e61-109">**Sommaire du menu**</span><span class="sxs-lookup"><span data-stu-id="f0e61-109">**Menu contents**</span></span>  
 <span data-ttu-id="f0e61-110">Répertorie les titres des éléments ajoutés au menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-110">Lists the titles of the items currently added to the **Tools** menu.</span></span> <span data-ttu-id="f0e61-111">Utilisez les flèches **Monter** et **Descendre** pour modifier l'ordre d'apparition des éléments dans le menu.</span><span class="sxs-lookup"><span data-stu-id="f0e61-111">Use the **Move Up** and **Move Down** arrows to change the order the items that appear on the menu.</span></span> <span data-ttu-id="f0e61-112">Utilisez le bouton **Supprimer** pour supprimer un élément du menu.</span><span class="sxs-lookup"><span data-stu-id="f0e61-112">Use the **Delete** button to remove an item from the menu.</span></span>  
  
 <span data-ttu-id="f0e61-113">**Monter**</span><span class="sxs-lookup"><span data-stu-id="f0e61-113">**Move Up**</span></span>  
 <span data-ttu-id="f0e61-114">Déplace l'outil sélectionné vers le haut de la liste des outils qui apparaissent dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-114">Move the selected tool higher in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="f0e61-115">**Descendre**</span><span class="sxs-lookup"><span data-stu-id="f0e61-115">**Move Down**</span></span>  
 <span data-ttu-id="f0e61-116">Déplace l'outil sélectionné vers le bas de la liste des outils qui apparaissent dans le menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-116">Move the selected tool lower in the list of tools that appear on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="f0e61-117">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="f0e61-117">**Add**</span></span>  
 <span data-ttu-id="f0e61-118">Vide les zones de texte pour que vous puissiez spécifier un nouvel outil.</span><span class="sxs-lookup"><span data-stu-id="f0e61-118">Clear the text boxes so you can specify a new tool.</span></span>  
  
 <span data-ttu-id="f0e61-119">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="f0e61-119">**Delete**</span></span>  
 <span data-ttu-id="f0e61-120">Supprime l'outil ou la commande de la liste **Contenu du menu** , ainsi que du menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-120">Remove the tool or command from the **Menu Contents** list as well as from the **Tools** menu.</span></span>  
  
 <span data-ttu-id="f0e61-121">**Titre**</span><span class="sxs-lookup"><span data-stu-id="f0e61-121">**Title**</span></span>  
 <span data-ttu-id="f0e61-122">Entrez le nom sous lequel l'outil ou la commande sera affiché dans le sous-menu **Outils externes** du menu **Outils** .</span><span class="sxs-lookup"><span data-stu-id="f0e61-122">Enter the name of the tool or command that will appear on the **External Tools** submenu of the **Tools** menu.</span></span> <span data-ttu-id="f0e61-123">Faites précéder une des lettres de ce nom du caractère & pour la définir comme touche de raccourci de l'outil.</span><span class="sxs-lookup"><span data-stu-id="f0e61-123">Place an ampersand (&) before a letter in the name of the tool to specify that letter as a keyboard shortcut.</span></span> <span data-ttu-id="f0e61-124">Par exemple, « &SQLCMD » s'afficherait sous la forme SQLCMD dans le menu **Outils**.</span><span class="sxs-lookup"><span data-stu-id="f0e61-124">For example, "&SQLCMD" would display SQLCMD on the **Tools** menu.</span></span>  
  
 <span data-ttu-id="f0e61-125">**Commande**</span><span class="sxs-lookup"><span data-stu-id="f0e61-125">**Command**</span></span>  
 <span data-ttu-id="f0e61-126">Spécifiez le chemin d'accès au fichier à lancer.</span><span class="sxs-lookup"><span data-stu-id="f0e61-126">Specify the path to the file to launch.</span></span>  
  
 <span data-ttu-id="f0e61-127">**Arguments**</span><span class="sxs-lookup"><span data-stu-id="f0e61-127">**Arguments**</span></span>  
 <span data-ttu-id="f0e61-128">Spécifiez les variables qui sont passées à l'outil lorsque celui-ci est sélectionné dans le menu.</span><span class="sxs-lookup"><span data-stu-id="f0e61-128">Specify the variables that are passed to the tool when the tool is selected on the menu.</span></span> <span data-ttu-id="f0e61-129">Les arguments peuvent spécifier des valeurs qui sont passées à l'outil ou à la commande au moment de son lancement.</span><span class="sxs-lookup"><span data-stu-id="f0e61-129">Arguments can specify values that are passed to the tool or command when it is launched.</span></span> <span data-ttu-id="f0e61-130">Par exemple, une valeur peut spécifier un nom de fichier ou un répertoire.</span><span class="sxs-lookup"><span data-stu-id="f0e61-130">For example, a value can specify a file name or directory.</span></span> <span data-ttu-id="f0e61-131">Utilisez le bouton fléché pour faire votre sélection dans une liste d'arguments prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="f0e61-131">Use the arrow button to select from a list of predefined arguments.</span></span> <span data-ttu-id="f0e61-132">Vous pouvez en ajouter plusieurs.</span><span class="sxs-lookup"><span data-stu-id="f0e61-132">You can add more than one.</span></span> <span data-ttu-id="f0e61-133">Pour obtenir la liste complète des arguments prédéfinis et leur définition, consultez [Arguments for External Tools](menu-help/external-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f0e61-133">For a complete list of predefined arguments and their definitions, see [Arguments for External Tools](menu-help/external-tools.md).</span></span> <span data-ttu-id="f0e61-134">Vous pouvez entrer également des arguments personnalisés, par exemple, des commutateurs de ligne de commande, selon la commande ou l'outil utilisé.</span><span class="sxs-lookup"><span data-stu-id="f0e61-134">You can also enter custom arguments (for example, command line switches), depending on the command or tool you use.</span></span>  
  
 <span data-ttu-id="f0e61-135">**Utiliser la fenêtre de sortie**</span><span class="sxs-lookup"><span data-stu-id="f0e61-135">**Use Output window**</span></span>  
 <span data-ttu-id="f0e61-136">Ouvre la fenêtre de sortie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] pour afficher la sortie de la commande en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f0e61-136">Opens the [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] Output window to display output of the command being run.</span></span> <span data-ttu-id="f0e61-137">Tous les outils ne présentent pas de sortie dans un format affichable dans la fenêtre Sortie.</span><span class="sxs-lookup"><span data-stu-id="f0e61-137">Not all tools present output in a format that can be presented in the Output window.</span></span> <span data-ttu-id="f0e61-138">Pour plus d’informations, consultez [Fenêtre Sortie](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span><span class="sxs-lookup"><span data-stu-id="f0e61-138">For more information, see [Output Window](../relational-databases/scripting/transact-sql-debugger-output-window.md).</span></span>  
  
 <span data-ttu-id="f0e61-139">**Considérer la sortie en Unicode**</span><span class="sxs-lookup"><span data-stu-id="f0e61-139">**Treat output as Unicode**</span></span>  
 <span data-ttu-id="f0e61-140">Interprète la sortie comme Unicode.</span><span class="sxs-lookup"><span data-stu-id="f0e61-140">Interprets the output as Unicode.</span></span>  
  
 <span data-ttu-id="f0e61-141">**Répertoire initial**</span><span class="sxs-lookup"><span data-stu-id="f0e61-141">**Initial directory**</span></span>  
 <span data-ttu-id="f0e61-142">Spécifie le répertoire de travail de l'outil.</span><span class="sxs-lookup"><span data-stu-id="f0e61-142">Specify the working directory of the tool.</span></span> <span data-ttu-id="f0e61-143">Utilisez le bouton fléché pour sélectionner des répertoires.</span><span class="sxs-lookup"><span data-stu-id="f0e61-143">Use the arrow button to select directories.</span></span> <span data-ttu-id="f0e61-144">Vous pouvez en sélectionner plusieurs.</span><span class="sxs-lookup"><span data-stu-id="f0e61-144">You can select more than one.</span></span>  
  
 <span data-ttu-id="f0e61-145">**Demander les arguments**</span><span class="sxs-lookup"><span data-stu-id="f0e61-145">**Prompt for arguments**</span></span>  
 <span data-ttu-id="f0e61-146">Affiche la boîte de dialogue **Arguments** pour vous permettre d'entrer ou de modifier des valeurs pour les arguments chaque fois que vous lancez l'outil externe.</span><span class="sxs-lookup"><span data-stu-id="f0e61-146">Display the **Arguments** dialog box to allow you to enter or edit values for the arguments each time you launch the external tool.</span></span>  
  
 <span data-ttu-id="f0e61-147">**Fermer en quittant**</span><span class="sxs-lookup"><span data-stu-id="f0e61-147">**Close on exit**</span></span>  
 <span data-ttu-id="f0e61-148">Ferme en même temps que l'outil la fenêtre qu'il a ouverte.</span><span class="sxs-lookup"><span data-stu-id="f0e61-148">Close the window opened by the tool when the tool is closed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0e61-149">Exemple</span><span class="sxs-lookup"><span data-stu-id="f0e61-149">Example</span></span>  
 <span data-ttu-id="f0e61-150">La saisie des valeurs suivantes dans la boîte de dialogue **Outils externes** crée un élément de menu libellé « DAC » qui, une fois sélectionné, ouvre une invite de commandes et exécute l'utilitaire **sqlcmd** à l'aide de la connexion administrateur dédiée.</span><span class="sxs-lookup"><span data-stu-id="f0e61-150">Entering the following values in the **External Tools** dialog box will create a menu item labeled "DAC" that when selected, opens a command prompt and runs the **sqlcmd** utility using the dedicated administrator connection.</span></span>  
  
|<span data-ttu-id="f0e61-151">Box</span><span class="sxs-lookup"><span data-stu-id="f0e61-151">Box</span></span>|<span data-ttu-id="f0e61-152">Valeur</span><span class="sxs-lookup"><span data-stu-id="f0e61-152">Value</span></span>|  
|---------|-----------|  
|<span data-ttu-id="f0e61-153">**Titre**</span><span class="sxs-lookup"><span data-stu-id="f0e61-153">**Title**</span></span>|<span data-ttu-id="f0e61-154">DAC</span><span class="sxs-lookup"><span data-stu-id="f0e61-154">DAC</span></span>|  
|<span data-ttu-id="f0e61-155">**Commande**</span><span class="sxs-lookup"><span data-stu-id="f0e61-155">**Command**</span></span>|[!INCLUDE[ssInstallPath](../includes/ssinstallpath-md.md)]<span data-ttu-id="f0e61-156">Tools\Binn\SQLCMD.exe</span><span class="sxs-lookup"><span data-stu-id="f0e61-156">Tools\Binn\SQLCMD.exe</span></span>|  
|<span data-ttu-id="f0e61-157">**Arguments**</span><span class="sxs-lookup"><span data-stu-id="f0e61-157">**Arguments**</span></span>|<span data-ttu-id="f0e61-158">-A</span><span class="sxs-lookup"><span data-stu-id="f0e61-158">-A</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0e61-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f0e61-159">See Also</span></span>  
 <span data-ttu-id="f0e61-160">[Arguments des outils externes](menu-help/external-tools.md) </span><span class="sxs-lookup"><span data-stu-id="f0e61-160">[Arguments for External Tools](menu-help/external-tools.md) </span></span>  
 [<span data-ttu-id="f0e61-161">Éléments généraux de l’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="f0e61-161">General User Interface Elements</span></span>](general-user-interface-elements.md)  
  
  
