---
title: Boîte de dialogue Ajouter une dimension de cube (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.addcubedimensiondialog.f1
helpviewer_keywords:
- Add Cube Dimension dialog box
ms.assetid: 625a3b1f-183b-445f-9bb7-96945c324767
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0de75c02c39b0690184f35f2b0b6a07d7ed9a4f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601793"
---
# <a name="add-cube-dimension-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="68186-102">Boîte de dialogue Ajouter une dimension de cube (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="68186-102">Add Cube Dimension Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="68186-103">Utilisez la boîte de dialogue **Ajouter une dimension de cube** dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] pour ajouter une référence à une dimension de base de données à un cube.</span><span class="sxs-lookup"><span data-stu-id="68186-103">Use the **Add Cube Dimension** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to add a reference to a database dimension to a cube.</span></span> <span data-ttu-id="68186-104">Vous pouvez afficher la boîte de dialogue **Ajouter une dimension de cube** en exécutant l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="68186-104">You can display the **Add Cube Dimension** dialog box by doing one of the following:</span></span>  
  
-   <span data-ttu-id="68186-105">Cliquez sur **Ajouter une dimension de cube** dans le volet **Barre d'outils** de l'onglet **Structure de cube** ou **Utilisation de la dimension** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="68186-105">Click **Add Cube Dimension** in the **Toolbar** pane on the **Cube Structure** or **Dimension Usage** tab in Cube Designer.</span></span>  
  
-   <span data-ttu-id="68186-106">Cliquez avec le bouton droit dans le volet **Dimensions** de l’onglet **Structure de cube** du Concepteur de cube et sélectionnez **Ajouter une dimension de cube** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="68186-106">Right-click the **Dimensions** pane on the **Cube Structure** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
-   <span data-ttu-id="68186-107">Cliquez avec le bouton droit dans le volet **Grille** de l’onglet **Utilisation de la dimension** du Concepteur de cube et sélectionnez **Ajouter une dimension de cube** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="68186-107">Right-click the **Grid** pane on the **Dimension Usage** tab in Cube Designer and select **Add Cube Dimension** from the context menu.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68186-108">Chaque dimension de cube ne peut avoir qu'une seule relation avec un groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="68186-108">Each cube dimension can have only one relationship to a measure group.</span></span> <span data-ttu-id="68186-109">Toutefois, vous pouvez créer plusieurs dimensions de cube et les ajouter au cube si la dimension de base de données sur laquelle la dimension de cube repose est associée à des groupes de mesures via plusieurs relations dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="68186-109">However, you can create more than one cube dimension and add it to the cube, if the database dimension on which the cube dimension is based is related to measure groups through more than one relationship in the data source view.</span></span> <span data-ttu-id="68186-110">Ces dimensions s'appellent des dimensions de rôle actif et sont généralement utilisées avec les dimensions de temps.</span><span class="sxs-lookup"><span data-stu-id="68186-110">Such dimensions are referred to as role-playing dimensions and commonly occur with time dimensions.</span></span>  
  
## <a name="options"></a><span data-ttu-id="68186-111">Options</span><span class="sxs-lookup"><span data-stu-id="68186-111">Options</span></span>  
 <span data-ttu-id="68186-112">**Sélectionner une dimension**</span><span class="sxs-lookup"><span data-stu-id="68186-112">**Select dimension**</span></span>  
 <span data-ttu-id="68186-113">Sélectionnez une dimension de base de données existante pour ajouter une dimension de cube basée sur la dimension de base de données au cube sélectionné.</span><span class="sxs-lookup"><span data-stu-id="68186-113">Select an existing database dimension to add a cube dimension based on it to the selected cube.</span></span> <span data-ttu-id="68186-114">Plusieurs dimensions de cube peuvent être définies depuis une même dimension de base de données.</span><span class="sxs-lookup"><span data-stu-id="68186-114">Multiple cube dimensions can be defined from the same database dimension.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="68186-115">Si vous ajoutez à un cube plusieurs dimensions de cube basées sur la même dimension de base de données, les dimensions de cube supplémentaires s'appellent des dimensions de rôle actif.</span><span class="sxs-lookup"><span data-stu-id="68186-115">If more than one cube dimension based on the same database dimension is added to a cube, the additional cube dimensions are called role-playing dimensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68186-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68186-116">See Also</span></span>  
 [<span data-ttu-id="68186-117">Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="68186-117">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
