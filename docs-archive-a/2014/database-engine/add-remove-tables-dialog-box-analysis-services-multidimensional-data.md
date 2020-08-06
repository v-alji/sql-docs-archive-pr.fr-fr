---
title: Boîte de dialogue Ajouter-supprimer des tables (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.addremoveobjects.f1
helpviewer_keywords:
- Add/Remove Tables dialog box
ms.assetid: b2760517-b0cb-4268-905d-bb1e1f9d902a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3bf1606ab7a0d43cbc0fa08bd921808792b6c85f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698561"
---
# <a name="add-remove-tables-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="45bca-102">Boîte de dialogue Ajouter-supprimer des tables (Analysis Services-données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="45bca-102">Add-Remove Tables Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="45bca-103">Utilisez la boîte de dialogue **Ajouter/Supprimer des tables** dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour ajouter des tables dans une source de données d’une vue de source de données, ou en supprimer.</span><span class="sxs-lookup"><span data-stu-id="45bca-103">Use the **Add/Remove Tables** dialog box in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add or remove tables in a data source to or from a data source view.</span></span> <span data-ttu-id="45bca-104">Pour afficher la boîte de dialogue **Ajouter/Supprimer des tables**, vous pouvez procéder de deux manières :</span><span class="sxs-lookup"><span data-stu-id="45bca-104">You can display the **Add/Remove Tables** dialog box by:</span></span>  
  
-   <span data-ttu-id="45bca-105">Cliquez sur **Ajouter/supprimer des objets** dans le volet **Barre d’outils** du **Concepteur de vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="45bca-105">Clicking **Add/Remove Objects** in the **Toolbar** pane of **Data Source View Designer**.</span></span>  
  
-   <span data-ttu-id="45bca-106">Cliquez avec le bouton droit sur le volet **Diagramme** du **Concepteur de vue de source de données**, puis sélectionnez **Ajouter/Supprimer des tables**.</span><span class="sxs-lookup"><span data-stu-id="45bca-106">Right-clicking the **Diagram** pane of **Data Source View Designer** and selecting **Add/Remove Tables**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="45bca-107">Options</span><span class="sxs-lookup"><span data-stu-id="45bca-107">Options</span></span>  
 <span data-ttu-id="45bca-108">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="45bca-108">**Data source**</span></span>  
 <span data-ttu-id="45bca-109">Permet de sélectionner la source de données afin d'ajouter ou de supprimer des tables.</span><span class="sxs-lookup"><span data-stu-id="45bca-109">Select the data source to add or remove tables.</span></span>  
  
 <span data-ttu-id="45bca-110">**Objets disponibles**</span><span class="sxs-lookup"><span data-stu-id="45bca-110">**Available objects**</span></span>  
 <span data-ttu-id="45bca-111">Permet d'afficher les objets accompagnés de leur type dans la source de données pour ceux qui ne sont pas déjà inclus dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="45bca-111">Displays the objects and their types in the data source that are not already included in the data source view.</span></span>  
  
 <span data-ttu-id="45bca-112">Cliquez **>>** pour transférer tous les objets répertoriés dans **objets disponibles** vers **objets inclus**, ou sélectionnez un ou plusieurs objets et cliquez sur **>** pour transférer les objets sélectionnés vers **objets inclus**.</span><span class="sxs-lookup"><span data-stu-id="45bca-112">Click **>>** to transfer all objects listed in **Available objects** to **Included objects**, or select one or more objects and click **>** to transfer the selected objects to **Included objects**.</span></span>  
  
 <span data-ttu-id="45bca-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="45bca-113">**Filter**</span></span>  
 <span data-ttu-id="45bca-114">Entrez le filtre à utiliser pour limiter la liste des objets affichés dans **Objets disponibles**, puis cliquez sur le bouton pour filtrer les objets de la liste.</span><span class="sxs-lookup"><span data-stu-id="45bca-114">Type the filter used to restrict the objects listed in **Available objects**, and then click the button to filter the listed objects.</span></span>  
  
 <span data-ttu-id="45bca-115">**Afficher les objets système**</span><span class="sxs-lookup"><span data-stu-id="45bca-115">**Show system objects**</span></span>  
 <span data-ttu-id="45bca-116">Sélectionnez cette option pour afficher les objets système de la source de données dans **Objets disponibles**.</span><span class="sxs-lookup"><span data-stu-id="45bca-116">Select to display system objects for the data source in **Available objects**.</span></span>  
  
 <span data-ttu-id="45bca-117">**Objets inclus**</span><span class="sxs-lookup"><span data-stu-id="45bca-117">**Included objects**</span></span>  
 <span data-ttu-id="45bca-118">Permet d'afficher les objets ajoutés à la vue de source de données ainsi que leur type.</span><span class="sxs-lookup"><span data-stu-id="45bca-118">Displays the objects and their types that have already been added to the data source view.</span></span>  
  
 <span data-ttu-id="45bca-119">Cliquez **<<** pour transférer tous les objets répertoriés dans **objets inclus** vers **objets disponibles**, ou sélectionnez un ou plusieurs objets et cliquez sur **<** pour transférer les objets sélectionnés vers **objets disponibles**.</span><span class="sxs-lookup"><span data-stu-id="45bca-119">Click **<<** to transfer all objects listed in **Included objects** to **Available objects**, or select one or more objects and click **<** to transfer the selected objects to **Available objects**.</span></span>  
  
 <span data-ttu-id="45bca-120">**Ajouter des tables associées**</span><span class="sxs-lookup"><span data-stu-id="45bca-120">**Add related tables**</span></span>  
 <span data-ttu-id="45bca-121">Cliquez sur ce bouton pour ajouter toutes les tables associées aux tables sélectionnées dans **Objets inclus**.</span><span class="sxs-lookup"><span data-stu-id="45bca-121">Click to add all tables that are related to the selected tables in **Included objects**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45bca-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45bca-122">See Also</span></span>  
 <span data-ttu-id="45bca-123">[Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;](../analysis-services/analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="45bca-123">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](../analysis-services/analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="45bca-124">Concepteur de vue de source de données &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="45bca-124">Data Source View Designer &#40;Analysis Services - Multidimensional Data&#41;</span></span>](../analysis-services/data-source-view-designer-analysis-services-multidimensional-data.md)  
  
  
