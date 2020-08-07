---
title: Liaison d’objets, boîte de dialogue | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql.asvs.dimensiondesigner.dbv.objectbinding.f1
helpviewer_keywords:
- Object Binding dialog box
ms.assetid: 2bb5ad7c-2962-4559-8c95-cf7148bd2e72
author: minewiskan
ms.author: owend
ms.openlocfilehash: a10c91e0222b826066aeede96aa665cc22540637
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611344"
---
# <a name="object-binding-dialog-box"></a><span data-ttu-id="71872-102">Boîte de dialogue Liaison d'objets</span><span class="sxs-lookup"><span data-stu-id="71872-102">Object Binding Dialog Box</span></span>
  <span data-ttu-id="71872-103">Utilisez la boîte de dialogue **Liaison d'objets** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour définir des liaisons entre la propriété d'un objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et une table ou une colonne dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="71872-103">Use the **Object Binding** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define bindings between the property of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object and a table or column in a data source view.</span></span> <span data-ttu-id="71872-104">Pour afficher la boîte de dialogue **Liaison d’objets** , sélectionnez **(nouvelle)** dans la liste déroulante pour la valeur des propriétés suivantes d’un objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] dans la fenêtre **Propriétés** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="71872-104">You can display the **Object Binding** dialog box by selecting **(new)** from the drop-down list for the value of the following properties of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object in the **Properties** window of [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]:</span></span>  
  
-   <span data-ttu-id="71872-105">NameColumn</span><span class="sxs-lookup"><span data-stu-id="71872-105">NameColumn</span></span>  
  
-   <span data-ttu-id="71872-106">ValueColumn</span><span class="sxs-lookup"><span data-stu-id="71872-106">ValueColumn</span></span>  
  
-   <span data-ttu-id="71872-107">CustomRollupColumn</span><span class="sxs-lookup"><span data-stu-id="71872-107">CustomRollupColumn</span></span>  
  
-   <span data-ttu-id="71872-108">CustomRollupPropertiesColumn</span><span class="sxs-lookup"><span data-stu-id="71872-108">CustomRollupPropertiesColumn</span></span>  
  
-   <span data-ttu-id="71872-109">UnaryOperatorColumn</span><span class="sxs-lookup"><span data-stu-id="71872-109">UnaryOperatorColumn</span></span>  
  
## <a name="options"></a><span data-ttu-id="71872-110">Options</span><span class="sxs-lookup"><span data-stu-id="71872-110">Options</span></span>  
 <span data-ttu-id="71872-111">**Type de liaison**</span><span class="sxs-lookup"><span data-stu-id="71872-111">**Binding type**</span></span>  
 <span data-ttu-id="71872-112">Sélectionne la liaison à utiliser pour l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71872-112">Select the binding to use for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="71872-113">Les types de liaisons suivants peuvent être utilisés :</span><span class="sxs-lookup"><span data-stu-id="71872-113">The following types of binding can be used:</span></span>  
  
 <span data-ttu-id="71872-114">Liaison de colonne</span><span class="sxs-lookup"><span data-stu-id="71872-114">Column binding</span></span>  
 <span data-ttu-id="71872-115">Lie l'objet à une table et colonne existantes au sein d'une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="71872-115">Binds the object to an existing table and column within a data source view.</span></span>  
  
 <span data-ttu-id="71872-116">Générer une colonne</span><span class="sxs-lookup"><span data-stu-id="71872-116">Generate column</span></span>  
 <span data-ttu-id="71872-117">Indique qu'une nouvelle colonne doit être définie dans la vue de source de données et qu'une liaison de colonne lui sera ensuite associée.</span><span class="sxs-lookup"><span data-stu-id="71872-117">Indicates that a new column is to be defined in the data source view, and a column binding is then associated with it.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71872-118">Si cette option est sélectionnée, vous devez exécuter **l’Assistant Génération de schéma** avant de déployer l’objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71872-118">If this option is selected, you must run the **Schema Generation Wizard** before deploying the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="71872-119">Liaison de lignes</span><span class="sxs-lookup"><span data-stu-id="71872-119">Row binding</span></span>  
 <span data-ttu-id="71872-120">Lie l'objet à une ligne dans une table de faits et permet de faciliter les mesures de comptage en fonction du nombre de lignes traitées dans la table de faits.</span><span class="sxs-lookup"><span data-stu-id="71872-120">Binds the object to a row in a fact table and is used to facilitate count measures based on the number of rows processed in the fact table.</span></span>  
  
 <span data-ttu-id="71872-121">**Table source**</span><span class="sxs-lookup"><span data-stu-id="71872-121">**Source table**</span></span>  
 <span data-ttu-id="71872-122">Affiche la liste des tables de la vue de source de données associée à l’objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="71872-122">Displays a list of tables in the data source view associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="71872-123">**Colonne source**</span><span class="sxs-lookup"><span data-stu-id="71872-123">**Source column**</span></span>  
 <span data-ttu-id="71872-124">Affiche la liste des colonnes de la table sélectionnée dans le champ **Table source**.</span><span class="sxs-lookup"><span data-stu-id="71872-124">Displays a list of columns in the table selected in **Source table**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71872-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71872-125">See Also</span></span>  
 [<span data-ttu-id="71872-126">Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="71872-126">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
