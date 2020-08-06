---
title: Création d’une vue de source de données (didacticiel sur l’exploration de données de base) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: c1e68a88-0f82-415d-becc-78d180d4f845
author: minewiskan
ms.author: owend
manager: kfile
ms.openlocfilehash: 4582845c905ef95601cbff2c810633f0cc901e3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603736"
---
# <a name="creating-a-data-source-view-basic-data-mining-tutorial"></a><span data-ttu-id="8956c-102">Création d'une vue de source de données (Didacticiel sur l'exploration de données de base)</span><span class="sxs-lookup"><span data-stu-id="8956c-102">Creating a Data Source View (Basic Data Mining Tutorial)</span></span>
  <span data-ttu-id="8956c-103">Une vue de source de données est créée à partir d'une source de données et définit un sous-ensemble des données, que vous pouvez ensuite utiliser dans vos structures d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="8956c-103">A data source view is built on a data source and defines a subset of the data, which you can then use in your mining structures.</span></span> <span data-ttu-id="8956c-104">Vous pouvez également utiliser la vue de source de données pour ajouter des colonnes, créer des colonnes calculées et des agrégats, et ajouter des vues nommées.</span><span class="sxs-lookup"><span data-stu-id="8956c-104">You can also use the data source view to add columns, create calculated columns and aggregates, and add named views.</span></span> <span data-ttu-id="8956c-105">En utilisant des vues de source de données, vous pouvez sélectionner les données qui se rapportent à un projet en particulier, établir des relations entre les tables et modifier la structure des données, sans modifier la source de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="8956c-105">By using data source views, you can select the data that relates to your project, establish relationships between tables, and modify the structure of the data, without modifying the original data source.</span></span> <span data-ttu-id="8956c-106">Pour plus d’informations, consultez [Vues de sources de données dans les modèles multidimensionnels](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span><span class="sxs-lookup"><span data-stu-id="8956c-106">For more information, see [Data Source Views in Multidimensional Models](https://docs.microsoft.com/analysis-services/multidimensional-models/data-source-views-in-multidimensional-models).</span></span>  
  
### <a name="to-create-a-data-source-view"></a><span data-ttu-id="8956c-107">Pour créer une vue de source de données</span><span class="sxs-lookup"><span data-stu-id="8956c-107">To create a data source view</span></span>  
  
1.  <span data-ttu-id="8956c-108">Dans **Explorateur de solutions**, cliquez avec le bouton droit sur **vues de source de données**, puis sélectionnez **nouvelle vue de source de données**.</span><span class="sxs-lookup"><span data-stu-id="8956c-108">In **Solution Explorer**, right-click **Data Source Views**, and select **New Data Source View**.</span></span>  
  
2.  <span data-ttu-id="8956c-109">Sur la page **Bienvenue dans l'Assistant Sources de données** , cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8956c-109">On the **Welcome to the Data Source View Wizard** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="8956c-110">Dans la page **Sélectionner une source de données** , sous **sources de données relationnelles**, sélectionnez la source de données Adventure Works DW 2012 que vous avez créée dans la dernière tâche.</span><span class="sxs-lookup"><span data-stu-id="8956c-110">On the **Select a Data Source** page, under **Relational data sources**, select the Adventure Works DW 2012 data source that you created in the last task.</span></span> <span data-ttu-id="8956c-111">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8956c-111">Click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8956c-112">Si vous souhaitez créer une source de données, cliquez avec le bouton droit sur **sources de données** , puis cliquez sur **nouvelle source de données** pour démarrer l’Assistant source de données.</span><span class="sxs-lookup"><span data-stu-id="8956c-112">If you want to create a data source, right-click **Data Sources** and then click **New Data Source** to start the Data Source Wizard.</span></span>  
  
4.  <span data-ttu-id="8956c-113">Sur la page **Sélectionner des tables et des vues** , sélectionnez les objets suivants, puis cliquez sur la flèche droite pour les inclure dans la nouvelle vue de source de données :</span><span class="sxs-lookup"><span data-stu-id="8956c-113">On the **Select Tables and Views** page, select the following objects, and then click the right arrow to include them in the new data source view:</span></span>  
  
    -   <span data-ttu-id="8956c-114">**ProspectiveBuyer (DBO)** -table des acheteurs de bicyclettes potentiels</span><span class="sxs-lookup"><span data-stu-id="8956c-114">**ProspectiveBuyer (dbo)** - table of prospective bike buyers</span></span>  
  
    -   <span data-ttu-id="8956c-115">**vTargetMail (DBO)** : vue des données historiques sur les derniers acheteurs de bicyclettes</span><span class="sxs-lookup"><span data-stu-id="8956c-115">**vTargetMail (dbo)** - view of historical data about past bike buyers</span></span>  
  
5.  <span data-ttu-id="8956c-116">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="8956c-116">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="8956c-117">Dans la page **fin de l’Assistant** , par défaut, la vue de source de données est nommée Adventure Works DW 2012.</span><span class="sxs-lookup"><span data-stu-id="8956c-117">On the **Completing the Wizard** page, by default the data source view is named Adventure Works DW 2012.</span></span> <span data-ttu-id="8956c-118">Remplacez le nom par `Targeted Mailing` , puis cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="8956c-118">Change the name to `Targeted Mailing`, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="8956c-119">La nouvelle vue de source de données s’ouvre dans l’onglet **Publipostage ciblé. DSV [conception]** .</span><span class="sxs-lookup"><span data-stu-id="8956c-119">The new data source view opens in the **Targeted Mailing.dsv [Design]** tab.</span></span>  
  
## <a name="previous-task-in-lesson"></a><span data-ttu-id="8956c-120">Tâche précédente de la leçon</span><span class="sxs-lookup"><span data-stu-id="8956c-120">Previous Task in Lesson</span></span>  
 [<span data-ttu-id="8956c-121">Création d’une source de données &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="8956c-121">Creating a Data Source &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/creating-a-data-source-basic-data-mining-tutorial.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="8956c-122">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="8956c-122">Next Lesson</span></span>  
 [<span data-ttu-id="8956c-123">Leçon 2 : création d’une structure de publipostage ciblée &#40;didacticiel sur l’exploration de données de base&#41;</span><span class="sxs-lookup"><span data-stu-id="8956c-123">Lesson 2: Building a Targeted Mailing Structure &#40;Basic Data Mining Tutorial&#41;</span></span>](../../2014/tutorials/lesson-2-building-a-targeted-mailing-structure-basic-data-mining-tutorial.md)  
  
## <a name="see-also"></a><span data-ttu-id="8956c-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8956c-124">See Also</span></span>  
 [<span data-ttu-id="8956c-125">Définition d’une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8956c-125">Defining a Data Source View &#40;Analysis Services&#41;</span></span>](https://docs.microsoft.com/analysis-services/multidimensional-models/defining-a-data-source-view-analysis-services)  
  
  
