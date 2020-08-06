---
title: Créer, supprimer ou modifier un dossier (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- removing folders
- modifying folders
- deleting folders
- folders [Reporting Services], creating
- folders [Reporting Services], deleting
- folders [Reporting Services], modifying
ms.assetid: d62159a8-ec67-4e28-a9f1-05a9250065bb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9bd7d5ceebdb7b3a48ded66ed108bddda25d8a46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611540"
---
# <a name="create-delete-or-modify-a-folder-report-manager"></a><span data-ttu-id="e7464-102">création, suppression ou modification d'un dossier (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="e7464-102">Create, Delete, or Modify a Folder (Report Manager)</span></span>
  <span data-ttu-id="e7464-103">Vous pouvez créer des dossiers pour organiser et gérer les éléments à publier sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="e7464-103">You can create folders to organize and manage the items you publish to a report server.</span></span> <span data-ttu-id="e7464-104">La création de dossiers peut permettre aux utilisateurs de rechercher les rapports qui les intéressent.</span><span class="sxs-lookup"><span data-stu-id="e7464-104">Creating folders can help users find reports of interest to them.</span></span> <span data-ttu-id="e7464-105">Pour les gestionnaires de contenu, les dossiers fournissent l'infrastructure nécessaire à l'application d'autorisations.</span><span class="sxs-lookup"><span data-stu-id="e7464-105">For content managers, folders provide a framework for applying permissions.</span></span> <span data-ttu-id="e7464-106">Vous pouvez créer des attributions de rôles pour des dossiers spécifiques afin de restreindre l'accès aux rapports en cours de développement ou dont la diffusion doit être restreinte.</span><span class="sxs-lookup"><span data-stu-id="e7464-106">You can create role assignments on specific folders to restrict access to reports that are in development or that should not be widely distributed.</span></span>  
  
### <a name="to-create-a-folder"></a><span data-ttu-id="e7464-107">Pour créer un dossier</span><span class="sxs-lookup"><span data-stu-id="e7464-107">To create a folder</span></span>  
  
1.  <span data-ttu-id="e7464-108">Démarrez le [Gestionnaire de rapports &#40;SSRS en mode natif&#41;](../report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e7464-108">Start [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="e7464-109">Dans le Gestionnaire de rapports, sélectionnez le dossier de base et cliquez sur **Nouveau dossier**.</span><span class="sxs-lookup"><span data-stu-id="e7464-109">In Report Manager, select the Home folder and click **New Folder**.</span></span> <span data-ttu-id="e7464-110">Vous pouvez également, pour créer un sous-dossier dans un dossier existant, naviguer jusqu’au dossier de votre choix dans la page **Contenu** , cliquer dessus pour l’ouvrir,</span><span class="sxs-lookup"><span data-stu-id="e7464-110">Or, to create a folder under an existing folder, navigate to that folder in the **Contents** page and click the folder to open it.</span></span> <span data-ttu-id="e7464-111">puis cliquer sur **Nouveau dossier**.</span><span class="sxs-lookup"><span data-stu-id="e7464-111">Then click **New Folder**.</span></span>  
  
     <span data-ttu-id="e7464-112">La page **Nouveau dossier** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="e7464-112">The **New Folder** page opens.</span></span>  
  
3.  <span data-ttu-id="e7464-113">Tapez le nom du dossier.</span><span class="sxs-lookup"><span data-stu-id="e7464-113">Type a folder name.</span></span> <span data-ttu-id="e7464-114">Un nom de dossier peut contenir des espaces, mais aucun caractère réservé au codage d'URL, par exemple les caractères : ; ?</span><span class="sxs-lookup"><span data-stu-id="e7464-114">A folder name can include spaces, but cannot include reserved characters that are used for URL encoding: ; ?</span></span> <span data-ttu-id="e7464-115">: \@ & = +, $/\* \< > |.</span><span class="sxs-lookup"><span data-stu-id="e7464-115">: \@ & = + , $ / \* \< > |.</span></span> <span data-ttu-id="e7464-116">Vous ne pouvez pas taper une série de noms de dossiers pour créer plusieurs dossiers en même temps.</span><span class="sxs-lookup"><span data-stu-id="e7464-116">You cannot type a series of folder names to create several folders at once.</span></span>  
  
4.  <span data-ttu-id="e7464-117">Tapez éventuellement une description.</span><span class="sxs-lookup"><span data-stu-id="e7464-117">Optionally type a description.</span></span>  
  
5.  <span data-ttu-id="e7464-118">Sélectionnez **Masquer en mode Liste** pour faire disparaître le dossier de l’affichage par défaut de la page **Contenu** .</span><span class="sxs-lookup"><span data-stu-id="e7464-118">Select **Hide in list view** if you do not want to display the folder in the default view of the **Contents** page.</span></span> <span data-ttu-id="e7464-119">Le dossier est visible uniquement par les utilisateurs qui cliquent sur **Afficher les détails** dans la page **Contenu** .</span><span class="sxs-lookup"><span data-stu-id="e7464-119">The folder will be visible to users only when they click **Show Details** on the **Contents** page.</span></span>  
  
6.  <span data-ttu-id="e7464-120">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7464-120">Click **OK**.</span></span>  
  
### <a name="to-delete-a-folder"></a><span data-ttu-id="e7464-121">Pour supprimer un dossier</span><span class="sxs-lookup"><span data-stu-id="e7464-121">To delete a folder</span></span>  
  
1.  <span data-ttu-id="e7464-122">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , puis recherchez l’élément à modifier.</span><span class="sxs-lookup"><span data-stu-id="e7464-122">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="e7464-123">Pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="e7464-123">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e7464-124">Dans le menu déroulant, cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e7464-124">In the drop-down menu, click **Delete**.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-modify-or-delete-a-folder"></a><span data-ttu-id="e7464-125">Pour modifier ou supprimer un dossier</span><span class="sxs-lookup"><span data-stu-id="e7464-125">To modify or delete a folder</span></span>  
  
1.  <span data-ttu-id="e7464-126">Dans le Gestionnaire de rapports, accédez à la page **Contenu** , puis recherchez l’élément à modifier.</span><span class="sxs-lookup"><span data-stu-id="e7464-126">In Report Manager, navigate to the **Contents** page, and locate the item that you want to modify.</span></span>  
  
2.  <span data-ttu-id="e7464-127">Pointez sur l'élément et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="e7464-127">Hover over the item, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="e7464-128">Dans le menu déroulant, cliquez sur **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="e7464-128">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="e7464-129">La page des propriétés générales s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="e7464-129">The General Properties page opens.</span></span>  
  
4.  <span data-ttu-id="e7464-130">Pour changer l’emplacement du dossier, cliquez sur **Déplacer**.</span><span class="sxs-lookup"><span data-stu-id="e7464-130">To change the folder location, click **Move**.</span></span> <span data-ttu-id="e7464-131">Indiquez l’emplacement du dossier de destination ou choisissez ce dossier dans l’arborescence, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7464-131">Type the location of the destination folder, or choose the destination folder from the tree, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e7464-132">Vous pouvez aussi modifier les propriétés du dossier en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="e7464-132">Or, modify folder properties in the following ways:</span></span>  
  
    -   <span data-ttu-id="e7464-133">Pour modifier les informations qui s'affichent sur le dossier, tapez un nom ou une description.</span><span class="sxs-lookup"><span data-stu-id="e7464-133">To modify display text about the folder, type a name or description.</span></span>  
  
    -   <span data-ttu-id="e7464-134">Pour afficher le dossier dans l’affichage par défaut de la page **Contenu** , décochez la case **Masquer en mode liste**.</span><span class="sxs-lookup"><span data-stu-id="e7464-134">To display the folder in the default view on the **Contents** page, clear **Hide in list view**.</span></span>  
  
6.  <span data-ttu-id="e7464-135">Vous pouvez également supprimer le dossier et son contenu en cliquant sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e7464-135">Or, to remove the folder and its contents, click **Delete**.</span></span>  
  
7.  <span data-ttu-id="e7464-136">Cliquez sur **Appliquer** pour enregistrer les modifications.</span><span class="sxs-lookup"><span data-stu-id="e7464-136">Click **Apply** to save changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7464-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7464-137">See Also</span></span>  
 <span data-ttu-id="e7464-138">[Page nouveau dossier &#40;Gestionnaire de rapports&#41;](../new-folder-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e7464-138">[New Folder Page &#40;Report Manager&#41;](../new-folder-page-report-manager.md) </span></span>  
 <span data-ttu-id="e7464-139">[Page contenu &#40;Gestionnaire de rapports&#41;](../contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="e7464-139">[Contents Page &#40;Report Manager&#41;](../contents-page-report-manager.md) </span></span>  
 [<span data-ttu-id="e7464-140">Recherche, affichage et gestion de rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="e7464-140">Finding, Viewing, and Managing Reports &#40;Report Builder and SSRS &#41;</span></span>](../report-builder/finding-viewing-and-managing-reports-report-builder-and-ssrs.md)  
  
  
