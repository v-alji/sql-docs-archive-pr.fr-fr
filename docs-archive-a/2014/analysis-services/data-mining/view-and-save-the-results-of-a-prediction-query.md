---
title: Afficher et enregistrer les résultats d’une requête de prédiction | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- prediction queries [Analysis Services]
- viewing prediction query results
- displaying prediction query results
- Mining Model Prediction [Analysis Services], viewing results
ms.assetid: abba4d24-3619-44c1-8279-88f27ad627d3
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6da4b515c4280969f665dba2cf5bee5281df0a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604270"
---
# <a name="view-and-save-the-results-of-a-prediction-query"></a><span data-ttu-id="2c3ec-102">Afficher et enregistrer les résultats d'une requête de prédiction</span><span class="sxs-lookup"><span data-stu-id="2c3ec-102">View and Save the Results of a Prediction Query</span></span>
  <span data-ttu-id="2c3ec-103">Une fois que vous avez défini une requête dans à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] l’aide d’générateur de requêtes de prédiction, vous pouvez exécuter la requête et afficher les résultats en basculant vers l’affichage des résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-103">After you have defined a query in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] by using Prediction Query Builder, you can run the query and view the results by switching to the query result view.</span></span>  
  
 <span data-ttu-id="2c3ec-104">Vous pouvez enregistrer les résultats d’une requête de prédiction dans une table d’une source de données définie dans un [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] projet.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-104">You can save the results of a prediction query to a table in any data source that is defined in a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> <span data-ttu-id="2c3ec-105">Vous pouvez créer une table ou enregistrer les résultats de la requête dans une table existante.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-105">You can either create a new table or save the query results to an existing table.</span></span> <span data-ttu-id="2c3ec-106">Si vous enregistrez les résultats dans une table existante, vous pouvez remplacer les données actuellement stockées dans la table. Sinon, les résultats de la requête sont ajoutés aux données existantes dans la table.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-106">If you save the results to an existing table, you can choose to overwrite the data that is currently stored in the table; otherwise, the query results are appended to the existing data in the table.</span></span>  
  
### <a name="run-a-query-and-view-the-results"></a><span data-ttu-id="2c3ec-107">Exécuter une requête et afficher les résultats</span><span class="sxs-lookup"><span data-stu-id="2c3ec-107">Run a query and view the results</span></span>  
  
1.  <span data-ttu-id="2c3ec-108">Dans la barre d’outils de l’onglet **Prédiction de modèle d’exploration de données** du Concepteur d’exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur **Résultat** .</span><span class="sxs-lookup"><span data-stu-id="2c3ec-108">On the toolbar of the **Mining Model Prediction** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click **Result** .</span></span>  
  
     <span data-ttu-id="2c3ec-109">L'affichage des résultats de la requête s'ouvre et exécute la requête.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-109">The query results view opens and runs the query.</span></span> <span data-ttu-id="2c3ec-110">Les résultats s'affichent dans une grille de la visionneuse.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-110">The results are displayed in a grid in the viewer.</span></span>  
  
### <a name="save-the-results-of-a-prediction-query-to-a-table"></a><span data-ttu-id="2c3ec-111">Enregistrer les résultats d'une requête de prédiction dans une table</span><span class="sxs-lookup"><span data-stu-id="2c3ec-111">Save the results of a prediction query to a table</span></span>  
  
1.  <span data-ttu-id="2c3ec-112">Dans la barre d’outils de l’onglet **Prédiction de modèle d’exploration de données** du Concepteur d’exploration de données, cliquez sur **Enregistrer le résultat de la requête**.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-112">On the toolbar of the **Mining Model Prediction** tab in Data Mining Designer, click **Save query result**.</span></span>  
  
     <span data-ttu-id="2c3ec-113">La boîte de dialogue **Enregistrer le résultat de la requête d’exploration de données** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-113">The **Save Data Mining Query Result** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="2c3ec-114">Sélectionnez une source de données dans la liste **Source de données** ou cliquez sur **Nouvelle** pour créer une source de données.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-114">Select a data source from the **Data Source** list, or click **New** to create a new data source.</span></span>  
  
3.  <span data-ttu-id="2c3ec-115">Dans la zone **Nom de la table** , tapez le nom de la table.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-115">In the **Table Name** box, enter the name of the table.</span></span> <span data-ttu-id="2c3ec-116">Si la table existe, sélectionnez **Remplacer en cas d’existence** pour remplacer le contenu de la table par les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-116">If the table already exists, select **Overwrite if exists** to replace the contents of the table with the query results.</span></span> <span data-ttu-id="2c3ec-117">Si vous ne voulez pas remplacer le contenu de la table, n'activez pas cette case à cocher.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-117">If you do not want to overwrite the contents of the table, do not select this check box.</span></span> <span data-ttu-id="2c3ec-118">Les résultats de la nouvelle requête seront ajoutés aux données existantes dans la table.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-118">The new query results will be appended to the existing data in the table.</span></span>  
  
4.  <span data-ttu-id="2c3ec-119">Sélectionnez une vue de source de données dans **Ajouter à la vue de source de données** si vous voulez ajouter la table à une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-119">Select a data source view from **Add to DSV** if you want to add the table to a data source view.</span></span>  
  
5.  <span data-ttu-id="2c3ec-120">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-120">Click **Save**.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="2c3ec-121">Si la destination ne prend pas en charge les ensembles de lignes hiérarchiques, vous pouvez ajouter le mot clé FALTTENED aux résultats pour les enregistrer sous forme de table plate.</span><span class="sxs-lookup"><span data-stu-id="2c3ec-121">If the destination does not support hierarchical rowsets, you can add the FALTTENED keyword to the results to save as a flat table.</span></span>  
  
  
