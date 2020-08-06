---
title: rrRenderingError- Erreur Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rrRenderingError
ms.assetid: 0751efc3-b81b-44ee-8aac-8560f86ca322
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b44b042c5f3c0cfdb9ffb99d3f45ed073beb972a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700638"
---
# <a name="rrrenderingerror---reporting-services-error"></a><span data-ttu-id="dac44-102">rrRenderingError - Erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="dac44-102">rrRenderingError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="dac44-103">Détails</span><span class="sxs-lookup"><span data-stu-id="dac44-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dac44-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="dac44-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="dac44-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="dac44-105">Event ID</span></span>|<span data-ttu-id="dac44-106">rrRenderingError</span><span class="sxs-lookup"><span data-stu-id="dac44-106">rrRenderingError</span></span>|  
|<span data-ttu-id="dac44-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="dac44-107">Event Source</span></span>|<span data-ttu-id="dac44-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span><span class="sxs-lookup"><span data-stu-id="dac44-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings.resources.Strings</span></span>|  
|<span data-ttu-id="dac44-109">Composant</span><span class="sxs-lookup"><span data-stu-id="dac44-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="dac44-110">Texte du message</span><span class="sxs-lookup"><span data-stu-id="dac44-110">Message Text</span></span>|<span data-ttu-id="dac44-111">Une erreur s'est produite lors du rendu du rapport.</span><span class="sxs-lookup"><span data-stu-id="dac44-111">An error occurred during rendering of the report.</span></span> <span data-ttu-id="dac44-112">(rrRenderingError) %1</span><span class="sxs-lookup"><span data-stu-id="dac44-112">(rrRenderingError) %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dac44-113">Explication</span><span class="sxs-lookup"><span data-stu-id="dac44-113">Explanation</span></span>  
 <span data-ttu-id="dac44-114">Ce message s'affiche lorsque [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ne peut pas restituer ou exporter le rapport.</span><span class="sxs-lookup"><span data-stu-id="dac44-114">This message is returned when [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] cannot render or export the report.</span></span>  
  
 <span data-ttu-id="dac44-115">Un message indiquant que la taille n'est pas prise en charge est généralement dû à une taille de page RDL non valide spécifiée.</span><span class="sxs-lookup"><span data-stu-id="dac44-115">A message that indicates that the size is not supported is typically caused when the specified RDL page size is not valid.</span></span> <span data-ttu-id="dac44-116">Spécifiez une taille de page RDL valide puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-116">Specify a valid RDL page size and then try again.</span></span>  
  
 <span data-ttu-id="dac44-117">Un message indiquant qu'une mesure de taille RDL n'est pas prise en charge est en général provoqué par la spécification d'un type d'unité non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="dac44-117">A message that indicates that an RDL size measurement is not supported is typically caused when an unsupported unit type is specified.</span></span> <span data-ttu-id="dac44-118">Les types d'unités valides sont cm, in, mm, pc et pt.</span><span class="sxs-lookup"><span data-stu-id="dac44-118">Valid unit types are cm, in, mm, pc, and pt.</span></span> <span data-ttu-id="dac44-119">Spécifiez un type d'unité valide puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-119">Specify a valid unit type and then try again.</span></span>  
  
 <span data-ttu-id="dac44-120">Un message indiquant qu'une taille négative n'est pas prise en charge est en général provoqué par la spécification d'une mesure négative pour la taille de la page, par exemple -5 cm.</span><span class="sxs-lookup"><span data-stu-id="dac44-120">A message that indicates that a negative size is not supported is typically caused when a negative measurement for the page size, for example -5 cm, is specified.</span></span> <span data-ttu-id="dac44-121">Spécifiez un nombre positif comme taille de page puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-121">Specify a positive number for the page size and then try again.</span></span>  
  
 <span data-ttu-id="dac44-122">Un message indiquant qu'une taille RDL hors limites a été spécifiée est en général provoqué par une mesure de taille de page qui dépasse la taille de marge de page valide.</span><span class="sxs-lookup"><span data-stu-id="dac44-122">A message that indicates that an RDL size is specified out of range is typically caused when a measurement for the page size is outside of the valid page margin size.</span></span> <span data-ttu-id="dac44-123">Spécifiez une mesure pour la taille de page comprise entre les tailles de marge de page valides.</span><span class="sxs-lookup"><span data-stu-id="dac44-123">Specify a measurement for the page size that is within the valid page margin sizes.</span></span>  
  
 <span data-ttu-id="dac44-124">Un message indiquant qu'une couleur spécifiée n'est pas prise en charge est généralement dû à une couleur non valide spécifiée dans l'élément RDL.</span><span class="sxs-lookup"><span data-stu-id="dac44-124">A message that indicates that a color specified is not supported is typically caused when a color specified in the RDL is not valid.</span></span> <span data-ttu-id="dac44-125">Choisissez une couleur prise en charge par l'élément RDL puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-125">Choose a color supported by RDL and then try again.</span></span>  
  
 <span data-ttu-id="dac44-126">Un message indiquant que l'étiquette d'action est facultative uniquement lors de l'utilisation d'une action unique et que l'ajout de plusieurs actions requiert des étiquettes pour chaque action est en général provoqué par la spécification d'une étiquette d'action non valide.</span><span class="sxs-lookup"><span data-stu-id="dac44-126">A message that indicates that the action label is only optional when using a single action and that adding multiple actions requires labels for each action is typically caused when an action label is specified and it is not valid.</span></span> <span data-ttu-id="dac44-127">Spécifiez une étiquette d'action valide pour chaque action.</span><span class="sxs-lookup"><span data-stu-id="dac44-127">Specify a valid action label for each action.</span></span>  
  
 <span data-ttu-id="dac44-128">Un message indiquant que l'argument de style doit être d'un type spécifique est en général provoqué par la spécification d'une valeur de style incorrecte pour le type de données.</span><span class="sxs-lookup"><span data-stu-id="dac44-128">A message that indicates the style argument has to be of a specific type is typically caused when an incorrect style value for the data type is specified.</span></span> <span data-ttu-id="dac44-129">La spécification RDL identifie les types valides que vous pouvez utiliser dans les valeurs de style d'éléments RDL différents.</span><span class="sxs-lookup"><span data-stu-id="dac44-129">The RDL specification identifies the valid types that you can use in the style values of different RDL elements.</span></span> <span data-ttu-id="dac44-130">Par exemple, "2pt" est une valeur de style incorrecte pour la couleur d'arrière-plan et "true" est une valeur incorrecte de hauteur.</span><span class="sxs-lookup"><span data-stu-id="dac44-130">For example, an incorrect style value for background color is "2pt" and incorrect value for height is "true".</span></span> <span data-ttu-id="dac44-131">Spécifiez une valeur correcte puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-131">Specify a correct value and then try again.</span></span>  
  
 <span data-ttu-id="dac44-132">Un message indiquant que le style de bordure n'est pas pris en charge est généralement dû à la spécification d'un style de bordure non valide.</span><span class="sxs-lookup"><span data-stu-id="dac44-132">A message that indicates that the border style is not supported is typically caused when the border style specified is not valid.</span></span> <span data-ttu-id="dac44-133">Spécifiez un style de bordure pris en charge puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-133">Specify a supported border style and then try again.</span></span>  
  
 <span data-ttu-id="dac44-134">Un message indiquant que le type MIME de l'image n'est pas pris en charge est en général provoqué par la spécification d'un type MIME non valide pour un élément de rapport de type image.</span><span class="sxs-lookup"><span data-stu-id="dac44-134">A message that indicates that the image mimetype is not supported is typically caused when the specified mimetype for an image report item is not valid.</span></span> <span data-ttu-id="dac44-135">Spécifiez un type MIME pris en charge pour l'élément de rapport puis réessayez.</span><span class="sxs-lookup"><span data-stu-id="dac44-135">Specify a supported mimetype for the report item and then try again.</span></span>  
  
 <span data-ttu-id="dac44-136">Un message indiquant que le nombre de lignes dépasse le nombre maximal de lignes possibles par feuille est en général dû au dépassement de ce nombre de lignes dans une feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="dac44-136">A message that indicates that the number of rows exceeds the maximum possible rows per sheet is typically caused when the number of rows in an Excel worksheet is exceeded.</span></span> <span data-ttu-id="dac44-137">Excel prend en charge un maximum de 65 000 lignes.</span><span class="sxs-lookup"><span data-stu-id="dac44-137">Excel supports up to 65,000 rows.</span></span>  
  
 <span data-ttu-id="dac44-138">Un message indiquant que le nombre de colonnes dépasse le nombre maximal de colonnes possibles par feuille est en général dû au dépassement de ce nombre de colonnes dans une feuille de calcul Excel.</span><span class="sxs-lookup"><span data-stu-id="dac44-138">A message that indicates that the number of columns exceeds the maximum possible columns per sheet is typically caused when the number of columns in an Excel worksheet is exceeded.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dac44-139">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="dac44-139">User Action</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="dac44-140">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="dac44-140">Internal-Only</span></span>  
  
