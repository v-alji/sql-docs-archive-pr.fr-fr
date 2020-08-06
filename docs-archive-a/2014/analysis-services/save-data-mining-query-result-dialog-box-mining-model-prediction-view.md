---
title: Boîte de dialogue Enregistrer le résultat de la requête d’exploration de données (vue prévision de modèle d’exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dm.savedataminingqueryresult.f1
helpviewer_keywords:
- Save Data Mining Query Result dialog box
ms.assetid: 112fb527-7466-4fd4-9cf1-75596135648f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0838c90f0797a0db9c8a66cd8c5f877aaecdad0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602373"
---
# <a name="save-data-mining-query-result-dialog-box-mining-model-prediction-view"></a><span data-ttu-id="235c2-102">Boîte de dialogue Enregistrer le résultat de la requête d'exploration de données (vue Prévision de modèle d'exploration de données)</span><span class="sxs-lookup"><span data-stu-id="235c2-102">Save Data Mining Query Result Dialog Box (Mining Model Prediction View)</span></span>
  <span data-ttu-id="235c2-103">Utilisez la boîte de dialogue **Enregistrer le résultat de la requête d'exploration de données** pour enregistrer les résultats d'une requête d'exploration de données dans une nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="235c2-103">Use the **Save Data Mining Query Result** dialog box to save the results of a data mining query to a new table.</span></span>  
  
 <span data-ttu-id="235c2-104">La nouvelle table sera créée dans la base de données définie par la source de données.</span><span class="sxs-lookup"><span data-stu-id="235c2-104">The new table will be created in the database defined by the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="235c2-105">Options</span><span class="sxs-lookup"><span data-stu-id="235c2-105">Options</span></span>  
 <span data-ttu-id="235c2-106">**Source de données**</span><span class="sxs-lookup"><span data-stu-id="235c2-106">**Data Source**</span></span>  
 <span data-ttu-id="235c2-107">Sélectionnez une source de données dans le projet actuel.</span><span class="sxs-lookup"><span data-stu-id="235c2-107">Select a data source from the current project.</span></span> <span data-ttu-id="235c2-108">Si la source de données correcte n'existe pas, cliquez sur **Nouveau** pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="235c2-108">If the correct data source does not exist, click **New** to create a new data source.</span></span>  
  
 <span data-ttu-id="235c2-109">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="235c2-109">**New**</span></span>  
 <span data-ttu-id="235c2-110">Ouvre **l’Assistant Source de données**.</span><span class="sxs-lookup"><span data-stu-id="235c2-110">Opens the **Data Source Wizard**.</span></span>  
  
 <span data-ttu-id="235c2-111">**Nom du tableau**</span><span class="sxs-lookup"><span data-stu-id="235c2-111">**Table Name**</span></span>  
 <span data-ttu-id="235c2-112">Tapez un nom pour la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="235c2-112">Type a name for the new table.</span></span>  
  
 <span data-ttu-id="235c2-113">**Remplacer en cas d'existence**</span><span class="sxs-lookup"><span data-stu-id="235c2-113">**Overwrite if exists**</span></span>  
 <span data-ttu-id="235c2-114">Sélectionnez cette option pour remplacer une table existante portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="235c2-114">Select this option if you want to overwrite an existing table with the same name.</span></span>  
  
 <span data-ttu-id="235c2-115">Remplacer la table existante est nécessaire si l'une des conditions suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="235c2-115">Overwriting the existing table is required if any of the following is true:</span></span>  
  
-   <span data-ttu-id="235c2-116">Vous avez ajouté des colonnes à la requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="235c2-116">You added columns to the prediction query.</span></span>  
  
-   <span data-ttu-id="235c2-117">Vous avez modifié les noms ou les types de données de colonnes dans la requête de prédiction.</span><span class="sxs-lookup"><span data-stu-id="235c2-117">You changed the names or data types of any columns in the prediction query.</span></span>  
  
-   <span data-ttu-id="235c2-118">Vous avez exécuté une instruction ALTER sur la table de destination.</span><span class="sxs-lookup"><span data-stu-id="235c2-118">You ran an ALTER statement on the destination table.</span></span>  
  
 <span data-ttu-id="235c2-119">Si plusieurs colonnes portent le même nom (par exemple, plusieurs colonnes dérivées peuvent porter le nom de colonne par défaut **Expression**), vous devez créer un alias pour chaque colonne ayant un nom dupliqué.</span><span class="sxs-lookup"><span data-stu-id="235c2-119">If multiple columns have the same name (for example, several derived columns might have the default column name **Expression**), you must create an alias for each column with a duplicate name.</span></span> <span data-ttu-id="235c2-120">Si les colonnes n'ont pas de noms uniques, une erreur est générée lorsque le concepteur tente d'enregistrer les résultats dans SQL Server, car les colonnes d'une table doivent porter des noms uniques.</span><span class="sxs-lookup"><span data-stu-id="235c2-120">If the columns do not have unique names, an error will be raised when the designer tries to save the results to SQL Server, because columns in a table must have unique names.</span></span>  
  
 <span data-ttu-id="235c2-121">**Ajouter à la vue de source de données**</span><span class="sxs-lookup"><span data-stu-id="235c2-121">**Add to DSV**</span></span>  
 <span data-ttu-id="235c2-122">(Facultatif) Sélectionnez une vue de source de données contenue dans le projet si vous souhaitez ajouter la table à une source de données existante.</span><span class="sxs-lookup"><span data-stu-id="235c2-122">(Optional) Select a data source view contained in the project if you want to add the table to an existing data source.</span></span>  
  
 <span data-ttu-id="235c2-123">Cette option est utile si vous souhaitez conserver toutes les tables associées pour un modèle, telles que les données d’apprentissage, les données sources de prédiction et les résultats de la requête, dans la même source de données.</span><span class="sxs-lookup"><span data-stu-id="235c2-123">This option is useful if you want to keep all related tables for a model-such as training data, prediction source data, and query results-in the same data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235c2-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="235c2-124">See Also</span></span>  
 <span data-ttu-id="235c2-125">[Prédiction Générateur de requêtes &#40;l’exploration de données&#41;](prediction-query-builder-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="235c2-125">[Prediction Query Builder &#40;Data Mining&#41;](prediction-query-builder-data-mining.md) </span></span>  
 <span data-ttu-id="235c2-126">[Interfaces de requête d’exploration de données](data-mining/data-mining-query-tools.md) </span><span class="sxs-lookup"><span data-stu-id="235c2-126">[Data Mining Query Interfaces](data-mining/data-mining-query-tools.md) </span></span>  
 [<span data-ttu-id="235c2-127">Guide de référence des instructions DMX &#40;Data Mining Extensions&#41;</span><span class="sxs-lookup"><span data-stu-id="235c2-127">Data Mining Extensions &#40;DMX&#41; Statement Reference</span></span>](/sql/dmx/data-mining-extensions-dmx-statements)  
  
  
