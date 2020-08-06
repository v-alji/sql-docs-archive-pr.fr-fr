---
title: Boîte de dialogue créer-modifier le calcul nommé (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsveditor.createnamedcalculation.f1
helpviewer_keywords:
- Named Calculation dialog box
ms.assetid: 66fb30ae-f5c5-4bfc-80ca-8c8a3a9bb30d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0b6777feb47a1ce6b601d0190e413b4baae35f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600355"
---
# <a name="create-edit-named-calculation-dialog-box-analysis-services"></a><span data-ttu-id="2f203-102">Boîte de dialogue créer-modifier le calcul nommé (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="2f203-102">Create-Edit Named Calculation Dialog Box (Analysis Services)</span></span>
  <span data-ttu-id="2f203-103">Utilisez la boîte de dialogue **créer/modifier le calcul nommé** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour définir ou modifier un calcul nommé pour une table dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="2f203-103">Use the **Create/Edit Named Calculation** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a named calculation for a table in a data source view.</span></span> <span data-ttu-id="2f203-104">Vous pouvez afficher la boîte de dialogue **Créer un calcul nommé/Modifier le calcul nommé** en :</span><span class="sxs-lookup"><span data-stu-id="2f203-104">You can display the **Create/Edit Named Calculation** dialog box by:</span></span>  
  
-   <span data-ttu-id="2f203-105">cliquant sur **Nouveau calculé nommé** dans le volet **Barre d’outils** du **Concepteur de vue de source de données** ;</span><span class="sxs-lookup"><span data-stu-id="2f203-105">Clicking **New Named Calculation** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="2f203-106">cliquant avec le bouton droit sur une table dans le volet **Tables** ou **Schéma** du **Concepteur de vue de source de données** et en sélectionnant **Nouveau calcul nommé** ;</span><span class="sxs-lookup"><span data-stu-id="2f203-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Named Calculation**.</span></span>  
  
-   <span data-ttu-id="2f203-107">cliquant avec le bouton droit sur le nom d’un calcul nommé dans le volet **Schéma** du **Concepteur de vue de source de données** et en sélectionnant **Modifier le calcul nommé**.</span><span class="sxs-lookup"><span data-stu-id="2f203-107">Right-clicking the name of a named calculation in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Named Calculation**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2f203-108">Options</span><span class="sxs-lookup"><span data-stu-id="2f203-108">Options</span></span>  
 <span data-ttu-id="2f203-109">**Nom de la colonne**</span><span class="sxs-lookup"><span data-stu-id="2f203-109">**Column Name**</span></span>  
 <span data-ttu-id="2f203-110">Entrez le nom du calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="2f203-110">Type the name of the named calculation.</span></span>  
  
 <span data-ttu-id="2f203-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="2f203-111">**Description**</span></span>  
 <span data-ttu-id="2f203-112">Entrez la description facultative du calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="2f203-112">Type the optional description of the named calculation.</span></span>  
  
 <span data-ttu-id="2f203-113">**Expression**</span><span class="sxs-lookup"><span data-stu-id="2f203-113">**Expression**</span></span>  
 <span data-ttu-id="2f203-114">Entrez une expression SQL valide qui retourne une valeur scalaire.</span><span class="sxs-lookup"><span data-stu-id="2f203-114">Type a valid SQL expression that returns a scalar value.</span></span> <span data-ttu-id="2f203-115">L'expression est envoyée au fournisseur et validée dans l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="2f203-115">The expression is sent to the provider, and validated in the following expression:</span></span>  
  
```  
SELECT <Table Name in Data Source>.* , <Expression> AS <Column Name> FROM <Table Name in Data Source>AS <Table Name in Data Source View>  
```  
  
 <span data-ttu-id="2f203-116">L'expression peut contenir des références à d'autres tables via une instruction sub-select.</span><span class="sxs-lookup"><span data-stu-id="2f203-116">The expression can contain references to other tables, by means of a sub-select statement.</span></span> <span data-ttu-id="2f203-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span><span class="sxs-lookup"><span data-stu-id="2f203-117">If the expression would require parentheses in a SELECT statement, the expression entered must be enclosed between parentheses.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f203-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f203-118">See Also</span></span>  
 <span data-ttu-id="2f203-119">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2f203-119">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2f203-120">Concepteur de vue de source de données &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="2f203-120">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
