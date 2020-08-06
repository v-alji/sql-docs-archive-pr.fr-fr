---
title: Boîte de dialogue analyse d’impact (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.process.impactanalysisdialog.f1
ms.assetid: 208268eb-4e14-44db-9c64-6f74b776adb6
author: minewiskan
ms.author: owend
ms.openlocfilehash: e47ab806b9bd10afc812113b69fe0849437068b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696288"
---
# <a name="impact-analysis-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="90ee9-102">Boîte de dialogue Analyse d'impact (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="90ee9-102">Impact Analysis Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="90ee9-103">Utilisez la boîte de dialogue **Analyse d'impact** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] et [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour identifier et éventuellement traiter les objets dépendants affectés si les objets figurant dans la boîte de dialogue **Traiter** sont traités.</span><span class="sxs-lookup"><span data-stu-id="90ee9-103">Use the **Impact Analysis** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] and [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to identify and optionally process dependent objects that are affected if the objects listed in the **Process** dialog box are processed.</span></span> <span data-ttu-id="90ee9-104">Pour afficher la boîte de dialogue **Analyse d'impact** , cliquez sur **Analyse d'impact** dans la boîte de dialogue **Traiter** .</span><span class="sxs-lookup"><span data-stu-id="90ee9-104">You can display the **Impact Analysis** dialog box by clicking **Impact Analysis** from the **Process** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90ee9-105">Un objet apparaît plusieurs fois s'il est affecté de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="90ee9-105">An object appears more than once if it is affected in more than one way.</span></span>  
  
## <a name="options"></a><span data-ttu-id="90ee9-106">Options</span><span class="sxs-lookup"><span data-stu-id="90ee9-106">Options</span></span>  
 <span data-ttu-id="90ee9-107">**Liste d’objets**</span><span class="sxs-lookup"><span data-stu-id="90ee9-107">**Object list**</span></span>  
 <span data-ttu-id="90ee9-108">Affiche la liste des objets dépendants dans une grille.</span><span class="sxs-lookup"><span data-stu-id="90ee9-108">Displays a list of dependent objects in a grid.</span></span> <span data-ttu-id="90ee9-109">Cette grille comporte les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="90ee9-109">The grid contains the following columns:</span></span>  
  
 <span data-ttu-id="90ee9-110">**Nom de l’objet**</span><span class="sxs-lookup"><span data-stu-id="90ee9-110">**Object Name**</span></span>  
 <span data-ttu-id="90ee9-111">Affiche le nom des objets dépendants qui devront peut-être être traités.</span><span class="sxs-lookup"><span data-stu-id="90ee9-111">Displays the name of the dependent object that may need to be processed.</span></span> <span data-ttu-id="90ee9-112">L'icône à gauche du nom indique le type de l'objet.</span><span class="sxs-lookup"><span data-stu-id="90ee9-112">The icon to the left of the name indicates the object type.</span></span>  
  
 <span data-ttu-id="90ee9-113">**Type**</span><span class="sxs-lookup"><span data-stu-id="90ee9-113">**Type**</span></span>  
 <span data-ttu-id="90ee9-114">Affiche le type des objets dépendants qui devront peut-être être traités.</span><span class="sxs-lookup"><span data-stu-id="90ee9-114">Displays the type of dependent object that may need to be processed.</span></span>  
  
 <span data-ttu-id="90ee9-115">**Type d'impact**</span><span class="sxs-lookup"><span data-stu-id="90ee9-115">**Impact Type**</span></span>  
 <span data-ttu-id="90ee9-116">Affiche l’effet que le traitement des objets mentionnés dans la boîte de dialogue **Traiter** aura sur l’objet dépendant.</span><span class="sxs-lookup"><span data-stu-id="90ee9-116">Displays the effect that processing the objects in the **Process** dialog box has on the dependent object.</span></span> <span data-ttu-id="90ee9-117">Le tableau suivant répertorie les effets possibles du traitement et indique si chaque traitement génère un avertissement ou une erreur.</span><span class="sxs-lookup"><span data-stu-id="90ee9-117">The following table lists the possible effects of processing and notes whether each one results in a warning or an error.</span></span>  
  
|<span data-ttu-id="90ee9-118">Impact</span><span class="sxs-lookup"><span data-stu-id="90ee9-118">Impact</span></span>|<span data-ttu-id="90ee9-119">Message</span><span class="sxs-lookup"><span data-stu-id="90ee9-119">Message</span></span>|  
|------------|-------------|  
|<span data-ttu-id="90ee9-120">L'objet sera exclu (non traité)</span><span class="sxs-lookup"><span data-stu-id="90ee9-120">Object will be cleared (unprocessed)</span></span>|<span data-ttu-id="90ee9-121">Warning</span><span class="sxs-lookup"><span data-stu-id="90ee9-121">Warning</span></span>|  
|<span data-ttu-id="90ee9-122">L'objet serait non valide</span><span class="sxs-lookup"><span data-stu-id="90ee9-122">Object would be invalid</span></span>|<span data-ttu-id="90ee9-123">Error</span><span class="sxs-lookup"><span data-stu-id="90ee9-123">Error</span></span>|  
|<span data-ttu-id="90ee9-124">L'agrégation serait supprimée</span><span class="sxs-lookup"><span data-stu-id="90ee9-124">Aggregation would be dropped</span></span>|<span data-ttu-id="90ee9-125">Warning</span><span class="sxs-lookup"><span data-stu-id="90ee9-125">Warning</span></span>|  
|<span data-ttu-id="90ee9-126">L'agrégation flexible serait supprimée</span><span class="sxs-lookup"><span data-stu-id="90ee9-126">Flexible aggregation would be dropped</span></span>|<span data-ttu-id="90ee9-127">Warning</span><span class="sxs-lookup"><span data-stu-id="90ee9-127">Warning</span></span>|  
|<span data-ttu-id="90ee9-128">Les index vont être supprimés</span><span class="sxs-lookup"><span data-stu-id="90ee9-128">Indexes will be dropped</span></span>|<span data-ttu-id="90ee9-129">Warning</span><span class="sxs-lookup"><span data-stu-id="90ee9-129">Warning</span></span>|  
|<span data-ttu-id="90ee9-130">L'objet non enfant va être traité</span><span class="sxs-lookup"><span data-stu-id="90ee9-130">Non-child object will be processed</span></span>|<span data-ttu-id="90ee9-131">Warning</span><span class="sxs-lookup"><span data-stu-id="90ee9-131">Warning</span></span>|  
  
 <span data-ttu-id="90ee9-132">**Traiter l'objet**</span><span class="sxs-lookup"><span data-stu-id="90ee9-132">**Process Object**</span></span>  
 <span data-ttu-id="90ee9-133">Sélectionnez les objets dépendants à traiter.</span><span class="sxs-lookup"><span data-stu-id="90ee9-133">Select the dependent objects that you want to process with the processing operation.</span></span> <span data-ttu-id="90ee9-134">Les objets dépendants non sélectionnés doivent être traités une fois le traitement terminé.</span><span class="sxs-lookup"><span data-stu-id="90ee9-134">Dependent objects that are not selected must be processed after the processing operation is finished.</span></span> <span data-ttu-id="90ee9-135">Sinon, ils ne pourront pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="90ee9-135">Otherwise, they cannot be used.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90ee9-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90ee9-136">See Also</span></span>  
 <span data-ttu-id="90ee9-137">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="90ee9-137">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="90ee9-138">Boîte de dialogue traiter &#40;Analysis Services-données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="90ee9-138">Process Dialog Box &#40;Analysis Services - Multidimensional Data&#41;</span></span>](process-dialog-box-analysis-services-multidimensional-data.md)  
  
  
