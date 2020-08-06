---
title: Modifier le contrôle de code source | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- IDD_SCC_CONNECTION_DIALOG
helpviewer_keywords:
- Change Source Control dialog box
ms.assetid: e6a5d83c-5809-4c56-907a-73d0c7ccdd7a
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 55831529243608e8c71972a31009e5672fb0234f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611321"
---
# <a name="change-source-control"></a><span data-ttu-id="d12f5-102">Modifier le contrôle de code source</span><span class="sxs-lookup"><span data-stu-id="d12f5-102">Change Source Control</span></span>
  <span data-ttu-id="d12f5-103">Cette boîte de dialogue permet de créer et de gérer les connexions et liaisons entre une solution ou un projet enregistré en local et un dossier de base de données de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d12f5-103">Creates and manages the connections and bindings that link a locally saved solution or project to a source control database folder.</span></span>  
  
## <a name="dialog-box-access"></a><span data-ttu-id="d12f5-104">Accès à la boîte de dialogue</span><span class="sxs-lookup"><span data-stu-id="d12f5-104">Dialog Box Access</span></span>  
 <span data-ttu-id="d12f5-105">Dans l'Explorateur de solutions de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], sélectionnez un élément.</span><span class="sxs-lookup"><span data-stu-id="d12f5-105">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], select an item in Solution Explorer.</span></span> <span data-ttu-id="d12f5-106">Dans le menu **Fichier** , cliquez sur **Contrôle de code source**, puis sur **Modifier le contrôle de code source**.</span><span class="sxs-lookup"><span data-stu-id="d12f5-106">On the **File** menu, click **Source Control**, and then **Change Source Control**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d12f5-107">Cette boîte de dialogue est également disponible en cliquant avec le bouton droit sur l'élément dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="d12f5-107">This dialog box is also available by right-clicking the item in Solution Explorer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d12f5-108">Options</span><span class="sxs-lookup"><span data-stu-id="d12f5-108">Options</span></span>  
 <span data-ttu-id="d12f5-109">**Établis**</span><span class="sxs-lookup"><span data-stu-id="d12f5-109">**Bind**</span></span>  
 <span data-ttu-id="d12f5-110">Associe les éléments sélectionnés à un emplacement de serveur de contrôle de code source spécifié.</span><span class="sxs-lookup"><span data-stu-id="d12f5-110">Associate selected items with a specified source control server location.</span></span> <span data-ttu-id="d12f5-111">Par exemple, vous pouvez utiliser cette option pour effectuer une liaison vers le dernier dossier et la dernière base de données connus du serveur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d12f5-111">For example, you can use this button to bind to the last known source control server folder and database.</span></span> <span data-ttu-id="d12f5-112">Si aucun dossier ou base de données récent n'est trouvé, vous devez en spécifier un ou une autre.</span><span class="sxs-lookup"><span data-stu-id="d12f5-112">If a recent server folder or database cannot be found, you are prompted to specify another.</span></span>  
  
 <span data-ttu-id="d12f5-113">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="d12f5-113">**Browse**</span></span>  
 <span data-ttu-id="d12f5-114">Permet d'accéder à un autre emplacement de serveur de contrôle de code source pour l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d12f5-114">Navigate to a new source control server location for the specified item.</span></span>  
  
 <span data-ttu-id="d12f5-115">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="d12f5-115">**Columns**</span></span>  
 <span data-ttu-id="d12f5-116">Identifie les colonnes à afficher et l'ordre dans lequel elles s'affichent.</span><span class="sxs-lookup"><span data-stu-id="d12f5-116">Identify columns to display and the order in which they are displayed.</span></span>  
  
 <span data-ttu-id="d12f5-117">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="d12f5-117">**Connect**</span></span>  
 <span data-ttu-id="d12f5-118">Crée une connexion entre les éléments sélectionnés et le serveur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d12f5-118">Create a connection between selected items and the source control server.</span></span>  
  
 <span data-ttu-id="d12f5-119">**Connecté**</span><span class="sxs-lookup"><span data-stu-id="d12f5-119">**Connected**</span></span>  
 <span data-ttu-id="d12f5-120">Affiche l'état de connexion d'une solution ou d'un projet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d12f5-120">Displays the connection status of a selected solution or project.</span></span>  
  
 <span data-ttu-id="d12f5-121">**Déconnexion**</span><span class="sxs-lookup"><span data-stu-id="d12f5-121">**Disconnect**</span></span>  
 <span data-ttu-id="d12f5-122">Déconnecte la copie locale d'une solution ou d'un projet, sur votre ordinateur personnel, de sa copie principale dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="d12f5-122">Disconnect the local copy of a solution or project on your computer from its master copy in the database.</span></span> <span data-ttu-id="d12f5-123">Utilisez cette commande avant de déconnecter votre ordinateur du serveur de contrôle de code source (par exemple, en mode hors connexion sur votre ordinateur portable).</span><span class="sxs-lookup"><span data-stu-id="d12f5-123">Use this command before disconnecting your computer from the source control server, for example, when working offline on your laptop.</span></span>  
  
 <span data-ttu-id="d12f5-124">**OK**</span><span class="sxs-lookup"><span data-stu-id="d12f5-124">**OK**</span></span>  
 <span data-ttu-id="d12f5-125">Enregistre les changements apportés dans la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d12f5-125">Accept changes made in the dialog box.</span></span>  
  
 <span data-ttu-id="d12f5-126">**Fournisseur**</span><span class="sxs-lookup"><span data-stu-id="d12f5-126">**Provider**</span></span>  
 <span data-ttu-id="d12f5-127">Affiche le nom de votre plug-in de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d12f5-127">Displays the name of your source control plug-in.</span></span>  
  
 <span data-ttu-id="d12f5-128">**Actualiser**</span><span class="sxs-lookup"><span data-stu-id="d12f5-128">**Refresh**</span></span>  
 <span data-ttu-id="d12f5-129">Actualise les informations de connexion relatives à tous les projets répertoriés dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="d12f5-129">Refreshes the connection information for all projects listed in this dialog box.</span></span>  
  
 <span data-ttu-id="d12f5-130">**Liaison du serveur**</span><span class="sxs-lookup"><span data-stu-id="d12f5-130">**Server Binding**</span></span>  
 <span data-ttu-id="d12f5-131">Indique la liaison entre l'élément et un serveur de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d12f5-131">Indicates the item's binding to a source control server.</span></span>  
  
 <span data-ttu-id="d12f5-132">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="d12f5-132">**Server Name**</span></span>  
 <span data-ttu-id="d12f5-133">Affiche le nom du serveur de contrôle de code source auquel la solution ou le projet correspondant est lié.</span><span class="sxs-lookup"><span data-stu-id="d12f5-133">Displays the name of the source control server to which the corresponding solution or project is bound.</span></span>  
  
 <span data-ttu-id="d12f5-134">**Solution/Projet**</span><span class="sxs-lookup"><span data-stu-id="d12f5-134">**Solution/Project**</span></span>  
 <span data-ttu-id="d12f5-135">Affiche le nom de chaque solution et projet dans la sélection en cours.</span><span class="sxs-lookup"><span data-stu-id="d12f5-135">Displays the name of each solution and project in the current selection.</span></span>  
  
 <span data-ttu-id="d12f5-136">**Sort**</span><span class="sxs-lookup"><span data-stu-id="d12f5-136">**Sort**</span></span>  
 <span data-ttu-id="d12f5-137">Trie les colonnes affichées.</span><span class="sxs-lookup"><span data-stu-id="d12f5-137">Sort the order of displayed columns.</span></span>  
  
 <span data-ttu-id="d12f5-138">**État**</span><span class="sxs-lookup"><span data-stu-id="d12f5-138">**Status**</span></span>  
 <span data-ttu-id="d12f5-139">Identifie l'état de liaison et de connexion d'un élément.</span><span class="sxs-lookup"><span data-stu-id="d12f5-139">Identifies the binding and connection status of an item.</span></span> <span data-ttu-id="d12f5-140">Les options possibles sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="d12f5-140">Possible options are:</span></span>  
  
|<span data-ttu-id="d12f5-141">**Option**</span><span class="sxs-lookup"><span data-stu-id="d12f5-141">**Option**</span></span>|<span data-ttu-id="d12f5-142">**Description**</span><span class="sxs-lookup"><span data-stu-id="d12f5-142">**Description**</span></span>|  
|----------------|---------------------|  
|<span data-ttu-id="d12f5-143">Valide</span><span class="sxs-lookup"><span data-stu-id="d12f5-143">Valid</span></span>|<span data-ttu-id="d12f5-144">L'élément est correctement lié et connecté au dossier de serveur auquel il appartient.</span><span class="sxs-lookup"><span data-stu-id="d12f5-144">The item is correctly bound and connected to the server folder to which it belongs.</span></span>|  
|<span data-ttu-id="d12f5-145">Non valide</span><span class="sxs-lookup"><span data-stu-id="d12f5-145">Invalid</span></span>|<span data-ttu-id="d12f5-146">L'élément n'est pas correctement lié au dossier de serveur auquel il appartient ou il en est déconnecté.</span><span class="sxs-lookup"><span data-stu-id="d12f5-146">The item is incorrectly bound to or disconnected from the folder to which it belongs.</span></span> <span data-ttu-id="d12f5-147">Sélectionnez la commande **Ajouter au contrôle de code source** au lieu de la commande **Lier** pour cet élément.</span><span class="sxs-lookup"><span data-stu-id="d12f5-147">Use the **Add to Source Control** command instead of **Bind** for this item.</span></span>|  
|<span data-ttu-id="d12f5-148">Unknown</span><span class="sxs-lookup"><span data-stu-id="d12f5-148">Unknown</span></span>|<span data-ttu-id="d12f5-149">L'état de l'élément sous contrôle de code source n'a pas encore été déterminé.</span><span class="sxs-lookup"><span data-stu-id="d12f5-149">The status of the item under source control has not yet been determined.</span></span>|  
|<span data-ttu-id="d12f5-150">Pas contrôlé</span><span class="sxs-lookup"><span data-stu-id="d12f5-150">Not Controlled</span></span>|<span data-ttu-id="d12f5-151">L'élément n'est pas placé sous contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="d12f5-151">The item has not been placed under source control.</span></span>|  
  
 <span data-ttu-id="d12f5-152">**Annuler la liaison**</span><span class="sxs-lookup"><span data-stu-id="d12f5-152">**Unbind**</span></span>  
 <span data-ttu-id="d12f5-153">Affiche la boîte de dialogue **Contrôle de code source** pour vous permettre de supprimer des éléments du contrôle de code source et de les dissocier de façon permanente de leurs dossiers actuels.</span><span class="sxs-lookup"><span data-stu-id="d12f5-153">Display the **Source Control** dialog box to allow you to remove selected items from source control and permanently disassociate the items from their present folders.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d12f5-154">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d12f5-154">See Also</span></span>  
 [<span data-ttu-id="d12f5-155">Contrôle de code source de l'Explorateur de solutions</span><span class="sxs-lookup"><span data-stu-id="d12f5-155">Solution Explorer Source Control</span></span>](../../2014/database-engine/solution-explorer-source-control.md)  
  
  
