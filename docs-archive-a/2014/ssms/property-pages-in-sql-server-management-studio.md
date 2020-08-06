---
title: Pages des propriétés dans SQL Server Management Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- property pages [SQL Server Management Studio]
ms.assetid: 719282c3-e9cc-4e0e-9a83-7fb8b8b17f67
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3fae6a07fbaa2a259fcca5c3807094b31e0d52d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705851"
---
# <a name="property-pages-in-sql-server-management-studio"></a><span data-ttu-id="4a4c6-102">Pages des propriétés dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="4a4c6-102">Property Pages in SQL Server Management Studio</span></span>
  <span data-ttu-id="4a4c6-103">Les boîtes de dialogue de page de propriétés de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] utilisent toutes un format commun pour l’affichage des informations avec des catégories pouvant être développées et réduites.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-103">Property page dialog boxes in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] all use a common format displaying information with expanding and collapsing categories.</span></span> <span data-ttu-id="4a4c6-104">Les champs affichés varient selon la propriété.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-104">The fields shown depend on the particular property.</span></span> <span data-ttu-id="4a4c6-105">Les propriétés affichées en gris sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-105">Properties shown in gray are read-only.</span></span> <span data-ttu-id="4a4c6-106">Les boutons Par catégorie et Alphabétique se trouvent en haut de chaque page de propriétés.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-106">Categorized and Alphabetic buttons are near the top of each property page.</span></span>  
  
 <span data-ttu-id="4a4c6-107">Le tableau ci-dessous décrit les éléments communs des boîtes de dialogue de page de propriétés [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4a4c6-107">The following table describes the common elements of [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] property page dialog boxes.</span></span>  
  
|<span data-ttu-id="4a4c6-108">Élément</span><span class="sxs-lookup"><span data-stu-id="4a4c6-108">Element</span></span>|<span data-ttu-id="4a4c6-109">Description</span><span class="sxs-lookup"><span data-stu-id="4a4c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a4c6-110">**Par catégorie**</span><span class="sxs-lookup"><span data-stu-id="4a4c6-110">**Categorized**</span></span>|<span data-ttu-id="4a4c6-111">Répertorie toutes les propriétés et les valeurs de propriété, triées par catégorie, pour l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-111">Lists all properties and property values for the selected object, sorted by category.</span></span> <span data-ttu-id="4a4c6-112">Dans le mode catégorie, vous pouvez réduire une catégorie afin de diminuer le nombre de propriétés visibles.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-112">In category view, you can collapse a category to reduce the number of visible properties.</span></span> <span data-ttu-id="4a4c6-113">Lorsque vous développez ou réduisez une catégorie, un signe plus (+) ou moins (-) s'affiche à gauche du nom de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-113">When you expand or collapse a category, you see a plus sign (+) or minus sign (-) to the left of the category name.</span></span> <span data-ttu-id="4a4c6-114">Les catégories s'affichent par ordre alphabétique.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-114">Categories are listed alphabetically.</span></span>|  
|<span data-ttu-id="4a4c6-115">**Alphabétique**</span><span class="sxs-lookup"><span data-stu-id="4a4c6-115">**Alphabetic**</span></span>|<span data-ttu-id="4a4c6-116">Répertorie l'ensemble des propriétés et des valeurs de propriétés, triées par ordre alphabétique, de l'objet sélectionné.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-116">Lists all properties and property values for the selected object, sorted alphabetically.</span></span>|  
|<span data-ttu-id="4a4c6-117">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="4a4c6-117">Property name</span></span>|<span data-ttu-id="4a4c6-118">La première colonne dans la grille répertorie les noms des propriétés.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-118">The first column in the grid lists the property names.</span></span>|  
|<span data-ttu-id="4a4c6-119">Propriétés</span><span class="sxs-lookup"><span data-stu-id="4a4c6-119">Properties</span></span>|<span data-ttu-id="4a4c6-120">La seconde colonne dans la grille répertorie les valeurs des propriétés.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-120">The second column in the grid lists the property values.</span></span>|  
|<span data-ttu-id="4a4c6-121">Volet Description</span><span class="sxs-lookup"><span data-stu-id="4a4c6-121">Description pane</span></span>|<span data-ttu-id="4a4c6-122">Le volet Description apparaît dans la partie inférieure de la page et affiche le type de la propriété ainsi qu'une description succincte de celle-ci.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-122">The description pane appears at the bottom of the page and shows the property type and a short description of the property.</span></span> <span data-ttu-id="4a4c6-123">Vous pouvez activer et désactiver la description de la propriété via la commande **Description** située dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="4a4c6-123">You can turn the description of the property off and on using the **Description** command on the shortcut menu.</span></span>|  
  
  
