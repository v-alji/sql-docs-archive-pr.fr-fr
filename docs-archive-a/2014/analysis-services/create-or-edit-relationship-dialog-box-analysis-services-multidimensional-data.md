---
title: Boîte de dialogue créer ou modifier une relation (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.createrelationship.f1
helpviewer_keywords:
- Create Relationship dialog box
ms.assetid: da3c7074-623e-4ddf-a707-d3276a47cf1c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4edae3f78ac6b764d91e1be97787fe59d49421db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603727"
---
# <a name="create-or-edit-relationship-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="032d7-102">Boîte de dialogue Créer/Modifier une relation (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="032d7-102">Create or Edit Relationship Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="032d7-103">Utilisez la boîte de dialogue **Créer/Modifier une relation** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour définir ou modifier une relation dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="032d7-103">Use the **Create/Edit Relationship** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to define or modify a relationship in a data source view.</span></span> <span data-ttu-id="032d7-104">Pour afficher la boîte de dialogue **Créer/Modifier une relation** , vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="032d7-104">You can display the **Create/Edit Relationship** dialog box by:</span></span>  
  
-   <span data-ttu-id="032d7-105">cliquer sur **Nouvelle relation** dans le volet **Barre d’outils** du **Concepteur de vues de source de données**;</span><span class="sxs-lookup"><span data-stu-id="032d7-105">Clicking **New Relationship** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="032d7-106">cliquer avec le bouton droit sur une table dans le volet **Tables** ou **Diagramme** du **Concepteur de vues de source de données** et sélectionner **Nouvelle relation**;</span><span class="sxs-lookup"><span data-stu-id="032d7-106">Right-clicking a table in either the **Tables** or **Diagram** pane of **Data Source View Designer** and selecting **New Relationship**.</span></span>  
  
-   <span data-ttu-id="032d7-107">cliquer avec le bouton droit sur une relation dans le volet **Diagramme** du **Concepteur de vues de source de données** et sélectionner **Modifier la relation**.</span><span class="sxs-lookup"><span data-stu-id="032d7-107">Right-clicking a relationship in the **Diagram** pane of **Data Source View Designer** and selecting **Edit Relationship**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="032d7-108">Vous pouvez créer des relations dans le **Concepteur de vues de source de données** , qui n’existent pas dans la source de données sous-jacente, et supprimer des relations créées par le **Concepteur de vues de source de données** à partir de relations de clé étrangère existantes dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="032d7-108">You can create relationships in **Data Source View Designer** that do not exist in the underlying data source, and remove relationships created by **Data Source View Designer** from existing foreign key relationships in the underlying data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="032d7-109">Options</span><span class="sxs-lookup"><span data-stu-id="032d7-109">Options</span></span>  
 <span data-ttu-id="032d7-110">**Table source (clé étrangère)**</span><span class="sxs-lookup"><span data-stu-id="032d7-110">**Source (foreign key) table**</span></span>  
 <span data-ttu-id="032d7-111">Sélectionnez la table ou la requête nommée qui contient la référence à une ou plusieurs colonnes de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="032d7-111">Select the table or named query that contains the reference to one or more columns in the destination table.</span></span>  
  
 <span data-ttu-id="032d7-112">**Table de destination (clé primaire)**</span><span class="sxs-lookup"><span data-stu-id="032d7-112">**Destination (primary key) table**</span></span>  
 <span data-ttu-id="032d7-113">Sélectionnez la table qui contient une ou plusieurs colonnes référencées par la table source.</span><span class="sxs-lookup"><span data-stu-id="032d7-113">Select the table that contains one or more columns referenced by the source table.</span></span> <span data-ttu-id="032d7-114">Pour les jointures réflexives, sélectionnez la même table que celle sélectionnée dans **Table source (clé étrangère)**.</span><span class="sxs-lookup"><span data-stu-id="032d7-114">For self-joins, select the same table selected in **Source (foreign key) table**.</span></span>  
  
 <span data-ttu-id="032d7-115">**Colonnes source**</span><span class="sxs-lookup"><span data-stu-id="032d7-115">**Source columns**</span></span>  
 <span data-ttu-id="032d7-116">Sélectionnez les colonnes qui font référence à des colonnes de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="032d7-116">Select the columns that reference columns in the destination table.</span></span>  
  
 <span data-ttu-id="032d7-117">**Colonnes de destination**</span><span class="sxs-lookup"><span data-stu-id="032d7-117">**Destination columns**</span></span>  
 <span data-ttu-id="032d7-118">Sélectionnez les colonnes qui sont référencées par des colonnes de la table source.</span><span class="sxs-lookup"><span data-stu-id="032d7-118">Select the columns that are referenced by columns in the source table.</span></span>  
  
 <span data-ttu-id="032d7-119">**TVA**</span><span class="sxs-lookup"><span data-stu-id="032d7-119">**Reverse**</span></span>  
 <span data-ttu-id="032d7-120">Inverse le sens de la relation.</span><span class="sxs-lookup"><span data-stu-id="032d7-120">Click to reverse the direction of the relationship.</span></span>  
  
 <span data-ttu-id="032d7-121">**Description**</span><span class="sxs-lookup"><span data-stu-id="032d7-121">**Description**</span></span>  
 <span data-ttu-id="032d7-122">Tapez une description facultative de la relation.</span><span class="sxs-lookup"><span data-stu-id="032d7-122">Type an optional description for the relationship.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="032d7-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="032d7-123">See Also</span></span>  
 <span data-ttu-id="032d7-124">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="032d7-124">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="032d7-125">Concepteur de vue de source de données &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="032d7-125">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
