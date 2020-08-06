---
title: Créer une structure d’exploration de données relationnelle | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], relational
- mining structures [Analysis Services], creating
- relational mining models [Analysis Services]
ms.assetid: 55bac3bd-700e-4f91-bcc6-f3cd8c026da1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2b41dd3ac2e6144011c1b3acde27c4b5829a1661
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601786"
---
# <a name="create-a-new-relational-mining-structure"></a><span data-ttu-id="81a69-102">créer une structure d'exploration de données relationnelle</span><span class="sxs-lookup"><span data-stu-id="81a69-102">Create a New Relational Mining Structure</span></span>
  <span data-ttu-id="81a69-103">Utilisez l’Assistant Exploration de données pour créer une nouvelle structure d’exploration de données, en utilisant les données d’une base de données relationnelle ou d’une autre source, puis enregistrer la structure et tous les modèles associés dans une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="81a69-103">Use the Data Mining Wizard to create a new mining structure, using data from a relational database or other source, and then save the structure and any related models to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
### <a name="to-create-a-relational-mining-structure"></a><span data-ttu-id="81a69-104">Pour créer une structure d'exploration de données relationnelle</span><span class="sxs-lookup"><span data-stu-id="81a69-104">To create a relational mining structure</span></span>  
  
1.  <span data-ttu-id="81a69-105">Dans l’Explorateur de solutions, cliquez avec le bouton droit sur le dossier **Structures d’exploration de données** d’un projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] , puis cliquez sur **Nouvelle structure d’exploration de données**.</span><span class="sxs-lookup"><span data-stu-id="81a69-105">In Solution Explorer, right-click the **Mining Structures** folder in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project, and then click **New Mining Structure**.</span></span>  
  
     <span data-ttu-id="81a69-106">L'Assistant Exploration de données s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="81a69-106">The Data Mining Wizard opens.</span></span>  
  
2.  <span data-ttu-id="81a69-107">Dans la page **Assistant Exploration de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81a69-107">On the **Welcome to the Data Mining Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="81a69-108">Dans la page **Sélectionner la méthode de définition** , sélectionnez **À partir d'une base de données relationnelles ou d'un entrepôt de données qui existent déjà**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81a69-108">On the **Select the Definition Method** page, select **From existing relational database or data warehouse**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="81a69-109">Dans la page **Sélectionner la technique d’exploration de données** , sélectionnez l’algorithme d’exploration de données à utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81a69-109">On the **Select the Data Mining Technique** page, select the data mining algorithm that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="81a69-110">Pour plus d’informations sur les algorithmes d’exploration de données, consultez [Algorithmes d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="81a69-110">For more information about data mining algorithms, see [Data Mining Algorithms &#40;Analysis Services - Data Mining&#41;](data-mining-algorithms-analysis-services-data-mining.md).</span></span>  
  
5.  <span data-ttu-id="81a69-111">Dans la page **Sélectionner une vue de source de données** , sous **Vues de sources de données disponibles**, cliquez sur la vue de source de données à utiliser, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81a69-111">On the **Select Data Source View** page, under **Available data source views**, click the data source view that you want to use, and then click **Next**.</span></span>  
  
     <span data-ttu-id="81a69-112">Pour plus d’informations sur la création d’une vue de source de données, consultez [Vues de sources de données dans les modèles multidimensionnels](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="81a69-112">For more information about creating a data source view, see [Data Source Views in Multidimensional Models](../multidimensional-models/data-source-views-in-multidimensional-models.md).</span></span>  
  
6.  <span data-ttu-id="81a69-113">Dans la page **Spécifier les types des tables** sous **Tables d’entrée**, sélectionnez une table de cas et une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="81a69-113">On the **Specify Table Types** page, under **Input tables**, select a case table and a nested table.</span></span>  
  
7.  <span data-ttu-id="81a69-114">Dans la page **Spécifier les données d’apprentissage** , sous **Structure du modèle d’exploration de données**, sélectionnez les colonnes clés, d’entrée et prédictibles.</span><span class="sxs-lookup"><span data-stu-id="81a69-114">On the **Specify the Training Data** page, under **Mining model structure**, select the key, input, and predictable columns.</span></span>  
  
     <span data-ttu-id="81a69-115">Après avoir sélectionné la colonne prédictible, cliquez sur le bouton **Suggérer** pour ouvrir la boîte de dialogue **Suggérer des colonnes associées** .</span><span class="sxs-lookup"><span data-stu-id="81a69-115">After you select the predictable column, you can click the **Suggest** button to open the **Suggest Related Columns** dialog box.</span></span> <span data-ttu-id="81a69-116">Vous pouvez accepter les colonnes suggérées en cliquant sur **OK** dans cette boîte de dialogue pour inclure les colonnes sélectionnées dans la structure d’exploration de données, ou vous pouvez changer les sélections dans la colonne **Entrée** , puis cliquer sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81a69-116">You can accept the suggested columns by clicking **OK** in this dialog box to include the selected columns in the mining structure, or you can change the selections in the **Input** column first, and then click **OK**.</span></span> <span data-ttu-id="81a69-117">Pour ignorer les suggestions, cliquez sur **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="81a69-117">To ignore the suggestions, click **Cancel**.</span></span>  
  
8.  <span data-ttu-id="81a69-118">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81a69-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="81a69-119">Dans la page **Spécifier le type de contenu et de données des colonnes** , sous **Structure du modèle d’exploration de données**, vous pouvez définir le type de contenu et le type de données de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="81a69-119">On the **Specify Columns' Content and Data Type** page, under **Mining model structure**, you can adjust the content type and data type for each column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="81a69-120">Cliquez sur **Détecter** pour détecter automatiquement si une colonne contient des données continues ou des données discrètes.</span><span class="sxs-lookup"><span data-stu-id="81a69-120">You can click **Detect** to automatically detect whether a column contains continuous or discrete data.</span></span> <span data-ttu-id="81a69-121">Après avoir cliqué sur ce bouton, le type de contenu et le type de données sont mis à jour dans les colonnes **Type de contenu** et **Type de données** .</span><span class="sxs-lookup"><span data-stu-id="81a69-121">After you click this button, the column content and data types will be updated in the **Content Type** and **Data Type** columns.</span></span> <span data-ttu-id="81a69-122">Pour plus d’informations sur les types de contenu et les types de données, consultez [Types de contenu &#40;Exploration de données&#41;](content-types-data-mining.md) et [Types de données &#40;Exploration de données&#41;](data-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="81a69-122">For more information about content types and data types, see [Content Types &#40;Data Mining&#41;](content-types-data-mining.md) and [Data Types &#40;Data Mining&#41;](data-types-data-mining.md).</span></span>  
  
10. <span data-ttu-id="81a69-123">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="81a69-123">Click **Next**.</span></span>  
  
11. <span data-ttu-id="81a69-124">Dans la page **Fin de l'Assistant** , entrez le nom de la structure d’exploration de données et le modèle d’exploration de données associé initial à créer, puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="81a69-124">On the **Completing the Wizard** page, provide a name for the mining structure and the related initial mining model that will be created, and then click **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81a69-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81a69-125">See Also</span></span>  
 [<span data-ttu-id="81a69-126">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="81a69-126">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
