---
title: Sélectionner la dimension de cube source (Assistant Exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.selectsourcecube.f1
ms.assetid: 556e216b-5e21-4160-967d-4c57591fbab4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6295a5312b4501236e0ce8f5776fc43c0d014581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602337"
---
# <a name="select-the-source-cube-dimension-data-mining-wizard"></a><span data-ttu-id="6b3f7-102">Sélectionner la dimension de cube source (Assistant Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="6b3f7-102">Select the Source Cube Dimension (Data Mining Wizard)</span></span>
  <span data-ttu-id="6b3f7-103">Utilisez la page **Sélectionner la dimension de cube source** pour sélectionner la dimension du cube qui contient les cas à analyser.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-103">Use the **Select the Source Cube Dimension** page to select the dimension from the cube that contains the cases you want to analyze.</span></span> <span data-ttu-id="6b3f7-104">Par exemple, si vous créez un modèle qui analyse le comportement d'achat de clients en fonction de données démographiques, vous devez sélectionner la dimension Customer, qui contient généralement un enregistrement unique pour chaque client et différents attributs représentant des données démographiques, telles que le sexe, l'adresse ou le revenu.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-104">For example, if you are building a model that analyzes the purchasing behavior of customers based on demographics, you would select the Customer dimension, which typically contains a unique record for each customer and various attributes that represent demographics, such as gender, location, or income.</span></span> <span data-ttu-id="6b3f7-105">Ultérieurement dans l'Assistant, vous aurez la possibilité d'ajouter une table liée à cette table de cas : par exemple, vous pourrez ajouter une table imbriquée qui montre les produits que le client a achetés.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-105">Later in the wizard you will have the opportunity to add a table that is related to this case table: for example, you might add a nested table that shows which products the customer has purchased.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b3f7-106">Cette page s’affiche uniquement si vous avez sélectionné **À partir d’un cube existant** dans la page **Sélectionner la méthode de définition** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-106">This page will appear only if you have selected **From existing cube** on the **Select the Definition Method** page of the wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6b3f7-107">Options</span><span class="sxs-lookup"><span data-stu-id="6b3f7-107">Options</span></span>  
 <span data-ttu-id="6b3f7-108">**Sélectionnez une dimension du cube source**</span><span class="sxs-lookup"><span data-stu-id="6b3f7-108">**Select a Source Cube Dimension**</span></span>  
 <span data-ttu-id="6b3f7-109">Sélectionnez la dimension du cube qui fournira la source de données à votre structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-109">Select the dimension of the cube that will provide the source data for your mining structure.</span></span>  
  
## <a name="choosing-a-dimension"></a><span data-ttu-id="6b3f7-110">Choix d'une dimension</span><span class="sxs-lookup"><span data-stu-id="6b3f7-110">Choosing a Dimension</span></span>  
 <span data-ttu-id="6b3f7-111">Comme vous pouvez sélectionner une seule dimension à utiliser dans votre modèle, il est important que vous compreniez la structure du cube et que vous sélectionniez la dimension qui fournit les meilleures informations pour votre modèle.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-111">Because you can select only one dimension for use in your model, it is important that you understand the cube structure and select the dimension that provides the best information for your model.</span></span> <span data-ttu-id="6b3f7-112">Si vous ne savez pas précisément quelle dimension utiliser, il peut être utile de parcourir le cube et de passer en revue les champs et les données qu'ils contiennent à l'aide du Concepteur de dimensions.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-112">If you are not sure which dimension to use, it might be helpful to browse the cube and review the fields and the data in them by using Dimension Designer.</span></span> <span data-ttu-id="6b3f7-113">Pour plus d’informations, consultez [Explorer les données d’une dimension dans le Concepteur de dimensions](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span><span class="sxs-lookup"><span data-stu-id="6b3f7-113">For more information, see [Browse Dimension Data in Dimension Designer](multidimensional-models/database-dimensions-browse-dimension-data-in-dimension-designer.md).</span></span>  
  
 <span data-ttu-id="6b3f7-114">Si vous n’êtes pas familiarisé avec les dimensions en général, consultez [Présentation des dimensions &#40;Analysis Services - Données multidimensionnelles&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="6b3f7-114">If you are unfamiliar with dimensions in general, see [Introduction to Dimensions &#40;Analysis Services - Multidimensional Data&#41;](multidimensional-models-olap-logical-dimension-objects/dimensions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="6b3f7-115">Pour plus d’informations sur le type d’informations généralement contenues dans une dimension unique, notamment les attributs et les mesures qui peuvent être utiles pour l’exploration de données, consultez [Relations de dimension](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6b3f7-115">For more information about the type of information that is typically contained in a single dimension, including attributes and measures that might be useful for data mining, see [Dimension Relationships](multidimensional-models-olap-logical-cube-objects/dimension-relationships.md).</span></span>  
  
 <span data-ttu-id="6b3f7-116">Si la dimension que vous choisissez ne contient pas tous les attributs associés dont vous avez besoin pour générer le modèle d'exploration de données, vous devrez peut-être modifier la dimension.</span><span class="sxs-lookup"><span data-stu-id="6b3f7-116">If the dimension that you choose does not contain all of the related attributes that you need to build the data mining model, you might need to modify the dimension.</span></span> <span data-ttu-id="6b3f7-117">Pour plus d’informations, consultez [Définir un article](multidimensional-models/define-database-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="6b3f7-117">For more information, see [Define Database Dimensions](multidimensional-models/define-database-dimensions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3f7-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b3f7-118">See Also</span></span>  
 <span data-ttu-id="6b3f7-119">[Aide (F1) de l’Assistant Exploration de données &#40;Analysis Services-exploration de données&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="6b3f7-119">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="6b3f7-120">[Créer la structure d’exploration de données &#40;l’Assistant Exploration de données&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="6b3f7-120">[Create the Data Mining Structure &#40;Data Mining Wizard&#41;](create-the-data-mining-structure-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="6b3f7-121">Sélectionnez la clé de cas &#40;Assistant Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="6b3f7-121">Select the Case Key &#40;Data Mining Wizard&#41;</span></span>](select-the-case-key-data-mining-wizard.md)  
  
  
