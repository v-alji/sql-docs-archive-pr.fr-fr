---
title: Sélectionner des objets (Explorateur d’objets) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.common.selectobjects.f1
ms.assetid: 692477fe-dd7c-403d-acd2-bb108b6077f1
author: stevestein
ms.author: sstein
ms.openlocfilehash: ceec604d9fe07b339af11ed69226d41a7f616678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695219"
---
# <a name="select-objects-object-explorer"></a><span data-ttu-id="20d43-102">Sélectionner des objets (Explorateur d'objets)</span><span class="sxs-lookup"><span data-stu-id="20d43-102">Select Objects (Object Explorer)</span></span>
  <span data-ttu-id="20d43-103">La boîte de dialogue **Sélectionner des objets** vous permet d’ajouter un objet dans une liste d’une autre boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="20d43-103">Use the **Select Objects** dialog box to add an object to a list in another dialog box.</span></span> <span data-ttu-id="20d43-104">Le titre de la boîte de dialogue et les options disponibles dans cette boîte de dialogue dépendent de la manière dont elle a été ouverte.</span><span class="sxs-lookup"><span data-stu-id="20d43-104">The dialog box title and the options available in the dialog box depend upon how it was opened.</span></span> <span data-ttu-id="20d43-105">Seules les options disponibles apparaissent ; par exemple, seuls des noms de connexion sont disponibles lorsque vous sélectionnez un propriétaire pour un nouvel objet.</span><span class="sxs-lookup"><span data-stu-id="20d43-105">Only available options appear; for instance, only logins are available when you are selecting an owner for a new object.</span></span>  
  
## <a name="options"></a><span data-ttu-id="20d43-106">Options</span><span class="sxs-lookup"><span data-stu-id="20d43-106">Options</span></span>  
 <span data-ttu-id="20d43-107">**Sélectionnez ces types d'objets**</span><span class="sxs-lookup"><span data-stu-id="20d43-107">**Select these object types**</span></span>  
 <span data-ttu-id="20d43-108">Affiche la liste des types auxquels les objets à sélectionner appartiennent.</span><span class="sxs-lookup"><span data-stu-id="20d43-108">Displays a list of the types of which the objects to be selected belong.</span></span> <span data-ttu-id="20d43-109">Les types incluent les principaux et éléments sécurisables de niveau de base de données et de niveau [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="20d43-109">The types include [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] level and database level principals and securables.</span></span> <span data-ttu-id="20d43-110">Cette zone est remplie à partir des sélections effectuées dans la boîte de dialogue **Sélectionner les types d’objets** , accessible à l’aide du bouton **Types d’objets** .</span><span class="sxs-lookup"><span data-stu-id="20d43-110">This box is populated from the selections made from the **Select Object Types** dialog box, accessed from the **Objects Type** button.</span></span>  
  
 <span data-ttu-id="20d43-111">**Entrez les noms d'objets à sélectionner**</span><span class="sxs-lookup"><span data-stu-id="20d43-111">**Enter the object names to select**</span></span>  
 <span data-ttu-id="20d43-112">Entrez la liste séparée par des points-virgules des noms des objets à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="20d43-112">Enter a semicolon-separated list of names of the objects to be selected.</span></span> <span data-ttu-id="20d43-113">Les objets à sélectionner doivent être d’un type répertorié dans la zone **Sélectionnez ces types d’objets** .</span><span class="sxs-lookup"><span data-stu-id="20d43-113">Objects to be selected must be of a type listed in the **Select these object types** box.</span></span> <span data-ttu-id="20d43-114">Les objets peuvent être sélectionnés dans une liste accessible en cliquant sur le bouton **Parcourir** .</span><span class="sxs-lookup"><span data-stu-id="20d43-114">Objects can be selected from a list accessed by clicking the **Browse** button.</span></span>  
  
 <span data-ttu-id="20d43-115">**Types d’objets**</span><span class="sxs-lookup"><span data-stu-id="20d43-115">**Object Types**</span></span>  
 <span data-ttu-id="20d43-116">Affiche une liste de types d'objets.</span><span class="sxs-lookup"><span data-stu-id="20d43-116">Displays a list of object types.</span></span> <span data-ttu-id="20d43-117">Sélectionnez un ou plusieurs types en activant les cases à cocher correspondantes.</span><span class="sxs-lookup"><span data-stu-id="20d43-117">Select one or more by selecting the check box corresponding to the type.</span></span>  
  
 <span data-ttu-id="20d43-118">**Vérifier les noms**</span><span class="sxs-lookup"><span data-stu-id="20d43-118">**Check Names**</span></span>  
 <span data-ttu-id="20d43-119">Valide les noms d’objets dans la zone **Entrez les noms d’objets à sélectionner** .</span><span class="sxs-lookup"><span data-stu-id="20d43-119">Validates the object names in the **Enter the object names to select** box.</span></span> <span data-ttu-id="20d43-120">Si un nom d’objet non valide est répertorié, la boîte de dialogue **Nom introuvable** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="20d43-120">If an object name that is not valid is listed, the **Name not Found** dialog box is presented.</span></span> <span data-ttu-id="20d43-121">Cette boîte de dialogue permet de corriger ou supprimer le nom dans la liste des objets à sélectionner.</span><span class="sxs-lookup"><span data-stu-id="20d43-121">With this dialog box, the name can be corrected or removed from the list of objects to select.</span></span>  
  
 <span data-ttu-id="20d43-122">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="20d43-122">**Browse**</span></span>  
 <span data-ttu-id="20d43-123">Affiche la boîte de dialogue **Rechercher des objets** .</span><span class="sxs-lookup"><span data-stu-id="20d43-123">Presents the **Browse for Objects** dialog box.</span></span> <span data-ttu-id="20d43-124">Celle-ci contient la liste des objets des types répertoriés dans la zone **Sélectionnez ces types d’objets** .</span><span class="sxs-lookup"><span data-stu-id="20d43-124">This contains a list of objects of the types listed in the **Select These Object Types** box.</span></span> <span data-ttu-id="20d43-125">Sélectionnez des objets dans cette liste en activant les cases à cocher correspondantes.</span><span class="sxs-lookup"><span data-stu-id="20d43-125">Select objects from this list by selecting the corresponding check boxes.</span></span>  
  
  
