---
title: Annulation des extractions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- VisualStudio.SourcControl.UndoCheckDialog
helpviewer_keywords:
- checking out files
- checkout source controls [SQL Server]
- undoing checkouts
ms.assetid: a6596b20-3aa5-4dc4-a4c5-3649f1f5a20e
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ff6e6041b59caa75bf7f8530d915db48e0379338
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601049"
---
# <a name="undo-checkouts"></a><span data-ttu-id="8e95c-102">Annuler des extractions</span><span class="sxs-lookup"><span data-stu-id="8e95c-102">Undo Checkouts</span></span>
  <span data-ttu-id="8e95c-103">Vous pouvez utiliser la commande **Annuler l’extraction** pour annuler une extraction existante.</span><span class="sxs-lookup"><span data-stu-id="8e95c-103">You can use the **Undo Checkout** command to cancel an existing checkout.</span></span> <span data-ttu-id="8e95c-104">Cette opération s'avère particulièrement utile lorsque vous avez modifié et enregistré un fichier et que vous devez par la suite annuler vos modifications.</span><span class="sxs-lookup"><span data-stu-id="8e95c-104">This is particularly useful when you have modified and saved a file, and then later need to roll back your changes.</span></span>  
  
 <span data-ttu-id="8e95c-105">En fonction des options que vous avez définies dans la boîte de dialogue **Annuler l’extraction options avancées** , l’environnement Studio conserve la copie de travail de l’élément sur votre disque local ou le remplace par la dernière version sous contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="8e95c-105">Depending on the options you set in the **Undo Checkout Advanced Options** dialog box, the Studio environment either leaves the working copy of the item on your local disk or replaces it with the latest source-controlled version.</span></span> <span data-ttu-id="8e95c-106">Si un utilisateur a modifié l'élément en dehors du contexte du système de contrôle de code source, la version extraite peut ne pas être la toute dernière.</span><span class="sxs-lookup"><span data-stu-id="8e95c-106">If someone has modified the item outside the context of the source control system, the retrieved version may not be the latest one.</span></span>  
  
### <a name="to-undo-a-checkout"></a><span data-ttu-id="8e95c-107">Pour annuler une extraction</span><span class="sxs-lookup"><span data-stu-id="8e95c-107">To undo a checkout</span></span>  
  
1.  <span data-ttu-id="8e95c-108">Dans l’Explorateur de solutions, sélectionnez le projet.</span><span class="sxs-lookup"><span data-stu-id="8e95c-108">In Solution Explorer, select the project.</span></span>  
  
2.  <span data-ttu-id="8e95c-109">Dans le menu **fichier** , pointez sur **contrôle de code source**, puis cliquez sur **Annuler l’extraction**.</span><span class="sxs-lookup"><span data-stu-id="8e95c-109">On the **File** menu, point to **Source Control**, and then click **Undo Checkout**.</span></span>  
  
3.  <span data-ttu-id="8e95c-110">Dans la boîte de dialogue **Annuler l’extraction** , sélectionnez les options appropriées, puis cliquez sur le bouton **Annuler l’extraction** .</span><span class="sxs-lookup"><span data-stu-id="8e95c-110">In the **Undo Checkout** dialog box, select the appropriate options, and then click the **Undo Checkout** button.</span></span>  
  
     <span data-ttu-id="8e95c-111">**Colonnes**</span><span class="sxs-lookup"><span data-stu-id="8e95c-111">**Columns**</span></span>  
     <span data-ttu-id="8e95c-112">Identifiez les colonnes à afficher et l'ordre dans lequel elles s'affichent.</span><span class="sxs-lookup"><span data-stu-id="8e95c-112">Identify the columns to display and the order in which they are displayed.</span></span>  
  
     <span data-ttu-id="8e95c-113">**Affichage en 2D**</span><span class="sxs-lookup"><span data-stu-id="8e95c-113">**Flat View**</span></span>  
     <span data-ttu-id="8e95c-114">Permet d'afficher les éléments sous forme de liste en 2D sous leur connexion de contrôle de code source.</span><span class="sxs-lookup"><span data-stu-id="8e95c-114">Display the items as flat lists under their source control connection.</span></span>  
  
     <span data-ttu-id="8e95c-115">**Nom**</span><span class="sxs-lookup"><span data-stu-id="8e95c-115">**Name**</span></span>  
     <span data-ttu-id="8e95c-116">Indique les noms des éléments pour lesquels annuler l'extraction.</span><span class="sxs-lookup"><span data-stu-id="8e95c-116">Displays the names of the items for which to undo the checkout.</span></span> <span data-ttu-id="8e95c-117">Les cases à cocher en regard des éléments affichés sont activées.</span><span class="sxs-lookup"><span data-stu-id="8e95c-117">Items appear with the check boxes next to them selected.</span></span> <span data-ttu-id="8e95c-118">Si vous ne voulez pas annuler l'extraction d'un élément, désactivez sa case à cocher.</span><span class="sxs-lookup"><span data-stu-id="8e95c-118">If you do not want to undo the checkout of an item, clear its check box.</span></span>  
  
     <span data-ttu-id="8e95c-119">**Options**</span><span class="sxs-lookup"><span data-stu-id="8e95c-119">**Options**</span></span>  
     <span data-ttu-id="8e95c-120">Affiche les options d'annulation d'extraction spécifiques au plug-in de contrôle de code source lorsque vous cliquez sur la flèche à droite du bouton.</span><span class="sxs-lookup"><span data-stu-id="8e95c-120">Displays source control plug-in-specific undo checkout options when the arrow to the right of the button is clicked.</span></span>  
  
     <span data-ttu-id="8e95c-121">**Sort**</span><span class="sxs-lookup"><span data-stu-id="8e95c-121">**Sort**</span></span>  
     <span data-ttu-id="8e95c-122">Permet d'ordonner les colonnes d'affichage.</span><span class="sxs-lookup"><span data-stu-id="8e95c-122">Sort the order of the display columns.</span></span>  
  
     <span data-ttu-id="8e95c-123">**Arborescence**</span><span class="sxs-lookup"><span data-stu-id="8e95c-123">**Tree View**</span></span>  
     <span data-ttu-id="8e95c-124">Permet d'afficher la hiérarchie des dossiers et des éléments pour les éléments dont vous annulez l'extraction.</span><span class="sxs-lookup"><span data-stu-id="8e95c-124">Display the folder and item hierarchy for items on which you are reversing the checkout.</span></span>  
  
     <span data-ttu-id="8e95c-125">**Annuler l’extraction**</span><span class="sxs-lookup"><span data-stu-id="8e95c-125">**Undo Checkout**</span></span>  
     <span data-ttu-id="8e95c-126">Permet d'annuler l'extraction, en supprimant toutes les modifications apportées au fichier extrait.</span><span class="sxs-lookup"><span data-stu-id="8e95c-126">Revert the checkout, discarding any changes to the checked-out file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e95c-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8e95c-127">See Also</span></span>  
 <span data-ttu-id="8e95c-128">[Extraire les fichiers](../../2014/database-engine/check-out-files.md) </span><span class="sxs-lookup"><span data-stu-id="8e95c-128">[Check Out Files](../../2014/database-engine/check-out-files.md) </span></span>  
 [<span data-ttu-id="8e95c-129">Gérer les extractions</span><span class="sxs-lookup"><span data-stu-id="8e95c-129">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
