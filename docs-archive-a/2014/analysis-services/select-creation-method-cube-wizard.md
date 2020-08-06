---
title: Sélectionner la méthode de création (Assistant Cube) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubewizard.cubedefinition.f1
ms.assetid: 985d3b5b-7891-465b-862d-f7e75431b342
author: minewiskan
ms.author: owend
ms.openlocfilehash: c8c4d611e00a2b3f5d115ea5749b1e494a44bf57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613147"
---
# <a name="select-creation-method-cube-wizard"></a><span data-ttu-id="160dc-102">Sélectionner la méthode de création (Assistant Cube)</span><span class="sxs-lookup"><span data-stu-id="160dc-102">Select Creation Method (Cube Wizard)</span></span>
  <span data-ttu-id="160dc-103">Utilisez la page **Sélectionner la méthode de création** pour spécifier la méthode de création du cube.</span><span class="sxs-lookup"><span data-stu-id="160dc-103">Use the **Select Creation Method** page to specify how to create the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="160dc-104">Options</span><span class="sxs-lookup"><span data-stu-id="160dc-104">Options</span></span>  
 <span data-ttu-id="160dc-105">**Utiliser des tables existantes**</span><span class="sxs-lookup"><span data-stu-id="160dc-105">**Use existing tables**</span></span>  
 <span data-ttu-id="160dc-106">Sélectionnez pour créer un cube en utilisant des tables existantes dans une source de données.</span><span class="sxs-lookup"><span data-stu-id="160dc-106">Select to create a cube by using existing tables in a data source.</span></span> <span data-ttu-id="160dc-107">L'Assistant vous guidera à travers le processus de sélection et de définition des groupes de mesures et de dimensions d'après des tables existantes pour générer votre nouveau cube.</span><span class="sxs-lookup"><span data-stu-id="160dc-107">The wizard will guide you through the process of selecting and defining measure groups and dimensions based on existing tables to build your new cube.</span></span>  
  
 <span data-ttu-id="160dc-108">**Créer un cube vide**</span><span class="sxs-lookup"><span data-stu-id="160dc-108">**Create an empty cube**</span></span>  
 <span data-ttu-id="160dc-109">Sélectionnez pour créer un cube vide.</span><span class="sxs-lookup"><span data-stu-id="160dc-109">Select to create an empty cube.</span></span> <span data-ttu-id="160dc-110">Cette option est utile lorsque vous souhaitez tout créer manuellement, ou lorsque tous les groupes de mesures dans le cube sont des groupes de mesures liés.</span><span class="sxs-lookup"><span data-stu-id="160dc-110">This option is useful when you want to create everything manually, or when all measure groups in the cube are linked measure groups.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="160dc-111">Cette option est disponible uniquement lorsque vous travaillez avec un projet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] et pas lorsque vous êtes connecté directement à une base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="160dc-111">This option is only available when you are working with an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] project and not when you are connected directly to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="160dc-112">**Générer des tables dans la source de données**</span><span class="sxs-lookup"><span data-stu-id="160dc-112">**Generate tables in the data source**</span></span>  
 <span data-ttu-id="160dc-113">Sélectionnez cette option pour créer d'abord un cube puis générer de nouvelles tables dans la source de données selon la définition de cube.</span><span class="sxs-lookup"><span data-stu-id="160dc-113">Select to create a cube first and then generate new tables in the data source based on the cube definition.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="160dc-114">Pour utiliser cette option, vous devez avoir l'autorisation de créer des objets dans la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="160dc-114">To use this option, you must have permission to create objects in the underlying data source.</span></span>  
  
 <span data-ttu-id="160dc-115">Si vous sélectionnez cette option, l'option **Modèle** devient alors disponible.</span><span class="sxs-lookup"><span data-stu-id="160dc-115">Selecting this option will make the **Template** option available.</span></span>  
  
 <span data-ttu-id="160dc-116">**Modèle**</span><span class="sxs-lookup"><span data-stu-id="160dc-116">**Template**</span></span>  
 <span data-ttu-id="160dc-117">Sélectionnez le modèle que vous souhaitez utiliser pour créer le cube.</span><span class="sxs-lookup"><span data-stu-id="160dc-117">Select the template that you want to use to create the cube.</span></span> <span data-ttu-id="160dc-118">Les modèles fournissent un jeu de définitions orienté vers un objectif commercial spécifique.</span><span class="sxs-lookup"><span data-stu-id="160dc-118">Templates provide a set of definitions oriented towards a specific business purpose.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="160dc-119">Cette option est disponible uniquement quand l’option **Générer des tables dans la source de données** a été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="160dc-119">This option is only available when the **Generate tables in the data source** option has been selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160dc-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="160dc-120">See Also</span></span>  
 <span data-ttu-id="160dc-121">[Objets de cube &#40;Analysis Services-données multidimensionnelles&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="160dc-121">[Cube Objects &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-cube-objects/cube-objects-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="160dc-122">[Cubes dans les modèles multidimensionnels](multidimensional-models/cubes-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="160dc-122">[Cubes in Multidimensional Models](multidimensional-models/cubes-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="160dc-123">Dimensions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="160dc-123">Dimensions in Multidimensional Models</span></span>](multidimensional-models/dimensions-in-multidimensional-models.md)  
  
  
