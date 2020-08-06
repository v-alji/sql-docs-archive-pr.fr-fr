---
title: Calculs (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 738816e3-0e1d-44a5-8d1b-81068dce8ac0
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2da86ae5c5652c8b2614cae4bbb721802700d973
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604163"
---
# <a name="calculations-ssas-tabular"></a><span data-ttu-id="c2780-102">Calculs (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="c2780-102">Calculations (SSAS Tabular)</span></span>
  <span data-ttu-id="c2780-103">Après avoir importé des données dans votre modèle, vous pouvez ajouter des calculs pour agréger, filtrer, étendre, combiner et sécuriser les données.</span><span class="sxs-lookup"><span data-stu-id="c2780-103">After you have imported data into your model, you can add calculations to aggregate, filter, extend, combine, and secure that data.</span></span> <span data-ttu-id="c2780-104">Les modèles tabulaires utilisent DAX (Data Analysis Expressions), un langage de formule pour la création de calculs personnalisés.</span><span class="sxs-lookup"><span data-stu-id="c2780-104">Tabular models use Data Analysis Expressions (DAX), a formula language for creating custom calculations.</span></span> <span data-ttu-id="c2780-105">Dans les modèles tabulaires, les calculs que vous pouvez créer à l'aide de formules DAX sont utilisés dans des *colonnes calculées*, des *mesures*et des *filtres de lignes*.</span><span class="sxs-lookup"><span data-stu-id="c2780-105">In tabular models, the calculations you create by using DAX formulas are used in *Calculated Columns*, *Measures*, and *Row Filters*.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2780-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c2780-106">In This Section</span></span>  
  
|<span data-ttu-id="c2780-107">Rubrique</span><span class="sxs-lookup"><span data-stu-id="c2780-107">Topic</span></span>|<span data-ttu-id="c2780-108">Description</span><span class="sxs-lookup"><span data-stu-id="c2780-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c2780-109">Fonctionnement de DAX dans les modèles tabulaires &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="c2780-109">Understanding DAX in Tabular Models &#40;SSAS Tabular&#41;</span></span>](understanding-dax-in-tabular-models-ssas-tabular.md)|<span data-ttu-id="c2780-110">Décrit le langage de formule DAX (Data Analysis Expressions) utilisé pour créer des calculs pour les colonnes calculées, les mesures et les filtres de lignes dans les modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="c2780-110">Describes the Data Analysis Expressions (DAX) formula language used to create calculations for calculated columns, measures, and row filters in tabular models.</span></span>|  
|[<span data-ttu-id="c2780-111">Compatibilité des formules en mode DirectQuery</span><span class="sxs-lookup"><span data-stu-id="c2780-111">Formula Compatibility in DirectQuery Mode</span></span>](../dax-formula-compatibility-in-directquery-mode-ssas-2014.md)|<span data-ttu-id="c2780-112">Décrit les différences, répertorie les fonctions qui ne sont pas prises en charge en mode DirectQuery et les fonctions prises en charge mais pouvant retourner des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="c2780-112">Describes the differences, lists the functions that are not supported in DirectQuery mode, and lists the functions that are supported but could return different results.</span></span>|  
|[<span data-ttu-id="c2780-113">Expressions d’analyse de données &#40;référence de&#41; DAX</span><span class="sxs-lookup"><span data-stu-id="c2780-113">Data Analysis Expressions &#40;DAX&#41; Reference</span></span>](/dax/data-analysis-expressions-dax-reference)|<span data-ttu-id="c2780-114">Cette section fournit une description détaillée de la syntaxe, des opérateurs et des fonctions DAX.</span><span class="sxs-lookup"><span data-stu-id="c2780-114">This section provides detailed descriptions of DAX syntax, operators, and functions.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="c2780-115">Les tâches pas à pas de création des calculs ne sont pas fournies dans cette section.</span><span class="sxs-lookup"><span data-stu-id="c2780-115">Step-by-step tasks for creating calculations are not provided in this section.</span></span> <span data-ttu-id="c2780-116">Étant donné que les calculs sont spécifiés dans les colonnes calculées, les mesures et les filtres de lignes (dans les rôles), les instructions indiquant où créer des formules DAX sont fournies dans les tâches associées à ces fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="c2780-116">Because calculations are specified in calculated columns, measures, and row filters (in roles), instructions on where to create DAX formulas are provided in tasks related to those features.</span></span> <span data-ttu-id="c2780-117">Pour plus d’informations, consultez [Créer une colonne calculée &#40;SSAS Tabulaire&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Créer et gérer des mesures &#40;SSAS Tabulaire&#41;](measures-ssas-tabular.md), et [Créer et gérer des rôles &#40;SSAS Tabulaire&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c2780-117">For more information, see [Create a Calculated Column &#40;SSAS Tabular&#41;](ssas-calculated-columns-create-a-calculated-column.md), [Create and Manage Measures &#40;SSAS Tabular&#41;](measures-ssas-tabular.md), and [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c2780-118">Bien que DAX puisse également être utilisé pour interroger un modèle tabulaire, les rubriques de cette section traitent spécifiquement de l'utilisation des formules DAX pour créer des calculs.</span><span class="sxs-lookup"><span data-stu-id="c2780-118">While DAX can also be used to query a tabular model, topics in this section focus specifically on using DAX formulas to create calculations.</span></span>  
  
  
