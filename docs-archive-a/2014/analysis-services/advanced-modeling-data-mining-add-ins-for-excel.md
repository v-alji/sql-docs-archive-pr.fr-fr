---
title: Modélisation avancée (compléments d’exploration de données pour Excel) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures, creating
ms.assetid: 042270a3-6ec7-4b52-b2ba-2adb6c4740d5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 771eb6111765b558995ee3b0eb98196c63951567
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602687"
---
# <a name="advanced-modeling-data-mining-add-ins-for-excel"></a><span data-ttu-id="9299b-102">Modélisation avancée (Compléments d'exploration de données pour Excel)</span><span class="sxs-lookup"><span data-stu-id="9299b-102">Advanced Modeling (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="9299b-103">Vous pouvez utiliser les options de modélisation **avancée** des données pour créer des modèles et des structures d’exploration de données personnalisés avec des paramètres différents de ceux créés par les assistants.</span><span class="sxs-lookup"><span data-stu-id="9299b-103">You can use the **Advanced** data modeling options to create custom data mining structures and models with parameters different from those created by the wizards.</span></span> <span data-ttu-id="9299b-104">Les deux Assistants décrits de cette section vous aident à créer une nouvelle structure d'exploration de données et un nouveau modèle d'exploration de données à appliquer à une structure d'exploration de données existante.</span><span class="sxs-lookup"><span data-stu-id="9299b-104">The two wizards described in this section help you create a completely new data mining structure, and a new mining model to apply to an existing data mining structure.</span></span>  
  
## <a name="create-mining-structure"></a><span data-ttu-id="9299b-105">Créer une structure d’exploration de données</span><span class="sxs-lookup"><span data-stu-id="9299b-105">Create Mining Structure</span></span>  
 <span data-ttu-id="9299b-106">![Bouton Créer une structure d'exploration de données, ruban Exploration de données](media/dmc-createstruct.gif "Bouton Créer une structure d'exploration de données, ruban Exploration de données")</span><span class="sxs-lookup"><span data-stu-id="9299b-106">![Create Mining Structure button, Data Mining ribbon](media/dmc-createstruct.gif "Create Mining Structure button, Data Mining ribbon")</span></span>  
  
 <span data-ttu-id="9299b-107">L' **Assistant Création** d’une structure d’exploration de données vous aide à générer une nouvelle structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9299b-107">The **Create Mining Structure Wizard** helps you build a new data mining structure.</span></span> <span data-ttu-id="9299b-108">Une structure désigne un ensemble de données extraites depuis une source de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9299b-108">A structure is a collection of data extracted from a specified data source.</span></span>  <span data-ttu-id="9299b-109">Une structure d'exploration de données peut être mise à jour avec de nouvelles données à la source, mais lorsque vous créez la structure d'exploration de données, vous définissez les types de données et les noms qui déterminent la façon dont les données sont utilisées pour l'analyse.</span><span class="sxs-lookup"><span data-stu-id="9299b-109">A mining structure can be updated with new data at the source, but when you create the mining structure, you define data types and names that define how the data is used for analysis.</span></span>  
  
 <span data-ttu-id="9299b-110">Vous pouvez utiliser les sources de données suivantes pour concevoir votre structure : un tableau Excel, une plage Excel, ou toutes les données d'une source de données externe qui a déjà été définie comme vue de source de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9299b-110">You can use the following data sources to build your structure: an Excel table, an Excel range, or any data in an external data source that has already been defined as an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source view.</span></span>  
  
 <span data-ttu-id="9299b-111">Pour chaque structure, vous pouvez mettre de côté certaines données à utiliser pour le test et la validation.</span><span class="sxs-lookup"><span data-stu-id="9299b-111">For each structure, you have the option of setting aside some of the data to use for testing and validation.</span></span> <span data-ttu-id="9299b-112">En créant ce *jeu de données exclusion* lorsque vous configurez vos sources de données, vous pouvez vous assurer que tous les modèles basés sur la structure sont en mesure d’utiliser un jeu de données cohérent à des fins de test.</span><span class="sxs-lookup"><span data-stu-id="9299b-112">By creating this *holdout data set* when you set up your data sources, you can ensure that all models that are based on the structure are able to use a consistent data set for testing.</span></span>  
  
 <span data-ttu-id="9299b-113">Après avoir créé une structure d'exploration de données, vous pouvez ajouter plusieurs modèles pour appliquer différentes méthodes d'analyse.</span><span class="sxs-lookup"><span data-stu-id="9299b-113">After you have created a mining structure, you can add multiple models to apply different methods of analysis.</span></span>  
  
 <span data-ttu-id="9299b-114">Pour plus d’informations sur l’utilisation de l' **Assistant Création**d’une structure d’exploration de données, consultez [créer une structure d’exploration de données &#40;SQL Server des compléments d’exploration de données&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="9299b-114">For more information about how to use the **Create Mining Structure Wizard**, see [Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;](create-mining-structure-sql-server-data-mining-add-ins.md).</span></span>  
  
## <a name="add-model-to-structure"></a><span data-ttu-id="9299b-115">Ajouter un modèle à une structure</span><span class="sxs-lookup"><span data-stu-id="9299b-115">Add Model to Structure</span></span>  
 <span data-ttu-id="9299b-116">![Bouton Ajouter le modèle à la structure](media/dmc-addmodel.gif "Bouton Ajouter le modèle à la structure")</span><span class="sxs-lookup"><span data-stu-id="9299b-116">![Add Model to Structure button](media/dmc-addmodel.gif "Add Model to Structure button")</span></span>  
  
 <span data-ttu-id="9299b-117">Lorsque vous ajoutez un nouveau modèle à une structure, vous analysez les données à l'aide d'un autre algorithme ou avec d'autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="9299b-117">When you add a new model to a structure, you analyze the data by using a different algorithm, or with different parameters.</span></span> <span data-ttu-id="9299b-118">Cette option est notamment utile si vous souhaitez créer un modèle à l'aide d'un des algorithmes non exposés dans les outils du client d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="9299b-118">This option is particularly useful if you want to create a model using one of the algorithms not exposed in the Data Mining Client tools.</span></span>  
  
 <span data-ttu-id="9299b-119">Par exemple, vous pouvez utiliser les algorithmes pris en charge par [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], tels que :</span><span class="sxs-lookup"><span data-stu-id="9299b-119">For example, you can use any of the algorithms supported by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], such as:</span></span>  
  
-   <span data-ttu-id="9299b-120">Régression linéaire</span><span class="sxs-lookup"><span data-stu-id="9299b-120">Linear regression</span></span>  
  
-   <span data-ttu-id="9299b-121">Sequence clustering</span><span class="sxs-lookup"><span data-stu-id="9299b-121">Sequence clustering</span></span>  
  
-   <span data-ttu-id="9299b-122">Analyse d'association sur les jeux de données imbriqués</span><span class="sxs-lookup"><span data-stu-id="9299b-122">Association analysis on nested data sets</span></span>  
  
 <span data-ttu-id="9299b-123">Pour voir quels types de structures d’exploration de données sont disponibles, vous pouvez parcourir les modèles et les structures stockés dans [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] en cliquant sur **gérer les modèles** ou sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="9299b-123">To see what kind of mining structures are available, you can browse the models and structures stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] by clicking either **Manage Models** or **Browse**.</span></span>  
  
 <span data-ttu-id="9299b-124">Vous êtes limité aux structures d'exploration de données qui ont été créées pendant la session active, ou aux structures d'exploration de données qui ont été enregistrées dans une instance de [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9299b-124">You are limited to data mining structures that were created during the current session, or mining structures that were saved to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="9299b-125">Pour plus d’informations, consultez [Ajouter un modèle à une Structure &#40;compléments d’exploration de données pour Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span><span class="sxs-lookup"><span data-stu-id="9299b-125">For more information, see [Add Model to Structure &#40;Data Mining Add-ins for Excel&#41;](add-model-to-structure-data-mining-add-ins-for-excel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9299b-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9299b-126">See Also</span></span>  
 <span data-ttu-id="9299b-127">[Gérer les modèles &#40;SQL Server des compléments d’exploration de données&#41;](manage-models-sql-server-data-mining-add-ins.md) </span><span class="sxs-lookup"><span data-stu-id="9299b-127">[Manage Models &#40;SQL Server Data Mining Add-ins&#41;](manage-models-sql-server-data-mining-add-ins.md) </span></span>  
 [<span data-ttu-id="9299b-128">Exploration des modèles dans Excel &#40;SQL Server les compléments d’exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="9299b-128">Browsing Models in Excel &#40;SQL Server Data Mining Add-ins&#41;</span></span>](browsing-models-in-excel-sql-server-data-mining-add-ins.md)  
  
  
