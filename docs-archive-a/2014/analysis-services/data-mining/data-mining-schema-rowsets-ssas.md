---
title: Interrogation des ensembles de lignes de schéma d’exploration de données (Analysis Services-exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- schema rowsets [Analysis Services], data mining
- data mining [Analysis Services], queries
- mining model content
- data mining [Analysis Services], schema rowsets
- schema rowsets [Analysis Services], retrieving
- data mining [Analysis Services], troubleshooting
ms.assetid: 442d8c29-07c7-45de-9a15-d556059f68d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: d60c802256454ee68d04392e685fa4acabf6c12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612632"
---
# <a name="querying-the-data-mining-schema-rowsets-analysis-services---data-mining"></a><span data-ttu-id="0e263-102">Interrogation des ensembles de lignes de schéma d'exploration de données (Analysis Services - Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="0e263-102">Querying the Data Mining Schema Rowsets (Analysis Services - Data Mining)</span></span>
  <span data-ttu-id="0e263-103">Dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], la plupart des ensembles de lignes de schéma d'exploration de données OLE DB existants sont exposés sous forme d'un jeu de tables système que vous pouvez interroger à l'aide d'instructions DMX (Data Mining Extensions).</span><span class="sxs-lookup"><span data-stu-id="0e263-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], many of the existing OLE DB data mining schema rowsets are exposed as a set of system tables that you can query by using Data Mining Extensions (DMX) statements.</span></span> <span data-ttu-id="0e263-104">En créant des requêtes sur l'ensemble de lignes de schéma d'exploration de données, vous pouvez identifier les services qui sont disponibles, obtenir des mises à jour sur l'état de vos modèles et de vos structures, et obtenir des détails sur le contenu ou les paramètres du modèle.</span><span class="sxs-lookup"><span data-stu-id="0e263-104">By creating queries against the data mining schema rowset, you can identify the services that are available, get updates on the status of your models and structures, and find out details about the model content or parameters.</span></span> <span data-ttu-id="0e263-105">Pour obtenir une description des ensembles de lignes de schéma d’exploration de données, consultez [Ensembles de lignes de schéma d’exploration de données](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="0e263-105">For a description of the data mining schema rowsets, see [Data Mining Schema Rowsets](../../relational-databases/native-client-ole-db-rowsets/rowsets.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0e263-106">Vous pouvez également interroger les ensembles de lignes de schéma d'exploration de données à l'aide de XMLA.</span><span class="sxs-lookup"><span data-stu-id="0e263-106">You can also query the data mining schema rowsets by using XMLA.</span></span> <span data-ttu-id="0e263-107">Pour plus d’informations sur la procédure à suivre dans SQL Server Management Studio, consultez [Créer une requête d’exploration de données en utilisant XMLA](create-a-data-mining-query-by-using-xmla.md).</span><span class="sxs-lookup"><span data-stu-id="0e263-107">For more information about how to do this in SQL Server Management Studio, see [Create a Data Mining Query by Using XMLA](create-a-data-mining-query-by-using-xmla.md).</span></span>  
  
## <a name="list-of-data-mining-schema-rowsets"></a><span data-ttu-id="0e263-108">Liste des ensembles de lignes de schéma d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="0e263-108">List of Data Mining Schema Rowsets</span></span>  
 <span data-ttu-id="0e263-109">Le tableau suivant répertorie les ensembles de lignes de schéma d'exploration de données qui peuvent s'avérer utiles pour l'interrogation et l'analyse.</span><span class="sxs-lookup"><span data-stu-id="0e263-109">The following table lists the data mining schema rowsets that may be useful for querying and monitoring.</span></span>  
  
|<span data-ttu-id="0e263-110">Nom de l'ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="0e263-110">Rowset name</span></span>|<span data-ttu-id="0e263-111">Description</span><span class="sxs-lookup"><span data-stu-id="0e263-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0e263-112">DMSCHEMA_MINING_MODELS</span><span class="sxs-lookup"><span data-stu-id="0e263-112">DMSCHEMA_MINING_MODELS</span></span>|<span data-ttu-id="0e263-113">Répertorie tous les modèles d'exploration de données dans le contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="0e263-113">Lists all mining models in the current context.</span></span><br /><br /> <span data-ttu-id="0e263-114">Inclut des informations telles que la date de création, les paramètres utilisés pour créer le modèle et la taille du jeu d'apprentissage.</span><span class="sxs-lookup"><span data-stu-id="0e263-114">Includes such information as the date created, parameters used to create the model, and the size of the training set.</span></span>|  
|<span data-ttu-id="0e263-115">DMSCHEMA_MINING_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="0e263-115">DMSCHEMA_MINING_COLUMNS</span></span>|<span data-ttu-id="0e263-116">Répertorie toutes les colonnes utilisées dans les modèles d'exploration de données dans le contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="0e263-116">Lists all columns used in mining models in the current context.</span></span><br /><br /> <span data-ttu-id="0e263-117">Les informations incluent le mappage à la colonne source de la structure d'exploration de données, le type de données, la précision et les fonctions de prédiction pouvant être utilisées avec la colonne.</span><span class="sxs-lookup"><span data-stu-id="0e263-117">Information includes mapping to mining structure source column, data type, precision, and prediction functions that can be used with the column.</span></span>|  
|<span data-ttu-id="0e263-118">DMSCHEMA_MINING_STRUCTURES</span><span class="sxs-lookup"><span data-stu-id="0e263-118">DMSCHEMA_MINING_STRUCTURES</span></span>|<span data-ttu-id="0e263-119">Répertorie toute la structure d'exploration de données dans le contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="0e263-119">Lists all mining structure in the current context.</span></span><br /><br /> <span data-ttu-id="0e263-120">Les informations contenues indiquent notamment si la structure est remplie, la date à laquelle la structure a été traitée pour la dernière fois et, le cas échéant, la définition du jeu de données d'exclusion pour la structure.</span><span class="sxs-lookup"><span data-stu-id="0e263-120">Information includes whether the structure is populated, the date the structure was last processed, and the definition of the holdout data set for the structure, if any.</span></span>|  
|<span data-ttu-id="0e263-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="0e263-121">DMSCHEMA_MINING_STRUCTURE_COLUMNS</span></span>|<span data-ttu-id="0e263-122">Répertorie toutes les colonnes utilisées dans les structures d'exploration de données dans le contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="0e263-122">Lists all columns used in mining structures in the current context.</span></span><br /><br /> <span data-ttu-id="0e263-123">Les informations indiquent notamment le type de contenu et le type de données, la possibilité de valeur NULL et si la colonne contient ou non des données de table imbriquées.</span><span class="sxs-lookup"><span data-stu-id="0e263-123">Information includes content type and data type, nullability, and whether the column contains nested table data.</span></span>|  
|<span data-ttu-id="0e263-124">DMSCHEMA_MINING_SERVICES</span><span class="sxs-lookup"><span data-stu-id="0e263-124">DMSCHEMA_MINING_SERVICES</span></span>|<span data-ttu-id="0e263-125">Répertorie tous les services d'exploration de données, ou algorithmes, qui sont disponibles sur le serveur spécifié.</span><span class="sxs-lookup"><span data-stu-id="0e263-125">Lists all mining services, or algorithms, that are available on the specified server.</span></span><br /><br /> <span data-ttu-id="0e263-126">Les informations indiquent notamment les indicateurs de modélisation pris en charge, les types d'entrée et les types de source de données pris en charge.</span><span class="sxs-lookup"><span data-stu-id="0e263-126">Information includes supported modeling flags, input types, and supported data source types.</span></span>|  
|<span data-ttu-id="0e263-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e263-127">DMSCHEMA_MINING_SERVICE_PARAMETERS</span></span>|<span data-ttu-id="0e263-128">Répertorie tous les paramètres pour les services d'exploration de données qui sont disponibles sur l'instance actuelle.</span><span class="sxs-lookup"><span data-stu-id="0e263-128">Lists all parameters for the mining services that are available on the current instance.</span></span><br /><br /> <span data-ttu-id="0e263-129">Les informations indiquent notamment le type de données pour chaque paramètre, les valeurs par défaut et les limites supérieures et inférieures.</span><span class="sxs-lookup"><span data-stu-id="0e263-129">Information includes the data type for each parameter, the default values, and the upper and lower limits.</span></span>|  
|<span data-ttu-id="0e263-130">DMSCHEMA_MODEL_CONTENT</span><span class="sxs-lookup"><span data-stu-id="0e263-130">DMSCHEMA_MODEL_CONTENT</span></span>|<span data-ttu-id="0e263-131">Retourne le contenu du modèle si le modèle a été traité.</span><span class="sxs-lookup"><span data-stu-id="0e263-131">Returns the content of the model if the model has been processed.</span></span><br /><br /> <span data-ttu-id="0e263-132">Pour plus d’informations, consultez [Contenu du modèle d’exploration &#40;Analysis Services - Exploration de données&#41;](mining-model-content-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="0e263-132">For more information, see [Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md).</span></span>|  
|<span data-ttu-id="0e263-133">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="0e263-133">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="0e263-134">Répertorie toutes les bases de données (catalogues) dans l'instance actuelle d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0e263-134">Lists all databases (catalogs) in the current instance of Analysis Services.</span></span>|  
|<span data-ttu-id="0e263-135">MDSCHEMA_INPUT_DATASOURCES</span><span class="sxs-lookup"><span data-stu-id="0e263-135">MDSCHEMA_INPUT_DATASOURCES</span></span>|<span data-ttu-id="0e263-136">Répertorie toutes les sources de données dans l'instance actuelle d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="0e263-136">Lists all data sources in the current instance of Analysis Services.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="0e263-137">La liste dans la table n'est pas complète ; elle affiche uniquement les ensembles de lignes les plus intéressants pour le dépannage.</span><span class="sxs-lookup"><span data-stu-id="0e263-137">The list in the table is not comprehensive; it shows only those rowsets that may be of most interest for troubleshooting.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0e263-138">Exemples</span><span class="sxs-lookup"><span data-stu-id="0e263-138">Examples</span></span>  
 <span data-ttu-id="0e263-139">La section suivante fournit quelques exemples de requêtes sur les ensembles de lignes de schéma d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="0e263-139">The following section provides some examples of queries against the data mining schema rowsets.</span></span>  
  
### <a name="example-1-list-data-mining-services"></a><span data-ttu-id="0e263-140">Exemple 1 : Répertorier les services d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="0e263-140">Example 1: List Data Mining Services</span></span>  
 <span data-ttu-id="0e263-141">La requête suivante retourne une liste des services d'exploration de données qui sont disponibles sur le serveur actuel, c'est-à-dire les algorithmes qui sont activés.</span><span class="sxs-lookup"><span data-stu-id="0e263-141">The following query returns a list of the mining services that are available on the current server, meaning the algorithms that are enabled.</span></span> <span data-ttu-id="0e263-142">Les colonnes fournies pour chaque service d'exploration de données comprennent notamment les indicateurs de modélisation et les types de contenu qui peuvent être utilisés par chaque algorithme, le GUID pour chaque service et toute limite de prédiction ayant pu être ajoutée pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="0e263-142">The columns provided for each mining service include the modeling flags and content types that can be used by each algorithm, the GUID for each service, and any prediction limits that may have been added for each service.</span></span>  
  
```  
SELECT *  
FROM $system.DMSCHEMA_MINING_SERVICES  
```  
  
### <a name="example-2-list-mining-model-parameters"></a><span data-ttu-id="0e263-143">Exemple 2 : Répertorier les paramètres du modèle d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="0e263-143">Example 2: List Mining Model Parameters</span></span>  
 <span data-ttu-id="0e263-144">L'exemple suivant retourne les paramètres utilisés pour créer un modèle d'exploration de données spécifique :</span><span class="sxs-lookup"><span data-stu-id="0e263-144">The following example returns the parameters that were used to create a specific mining model:</span></span>  
  
```  
SELECT MINING_PARAMETERS   
FROM $system.DMSCHEMA_MINING_MODELS  
WHERE MODEL_NAME = 'TM Clustering'  
```  
  
### <a name="example-3-list-all-rowsets"></a><span data-ttu-id="0e263-145">Exemple 3 : Répertorier tous les ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="0e263-145">Example 3: List All Rowsets</span></span>  
 <span data-ttu-id="0e263-146">L'exemple suivant retourne une liste complète des ensembles de lignes disponibles sur le serveur actuel :</span><span class="sxs-lookup"><span data-stu-id="0e263-146">The following example returns a comprehensive list of the rowsets that are available on the current server:</span></span>  
  
```  
SELECT *   
FROM $system.DBSCHEMA_TABLES  
```  
  
## <a name="see-also"></a><span data-ttu-id="0e263-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e263-147">See Also</span></span>  
 [<span data-ttu-id="0e263-148">Concepts de dépannage (Analysis Services - Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="0e263-148">Troubleshooting Concepts (Analysis Services - Data Mining)</span></span>](https://msdn.microsoft.com/library/cc645881.aspx)  
  
  
