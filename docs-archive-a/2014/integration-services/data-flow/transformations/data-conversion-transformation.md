---
title: Conversion de données, transformation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.dataconversiontrans.f1
helpviewer_keywords:
- converting data types [Integration Services]
- Data Conversion transformation
- data types [Integration Services], converting
ms.assetid: fd515bbc-6f49-4d0c-ae7f-6ea3c3f24a1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57b1f70c070cdf81dc0bc899ed365d048db26cc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601021"
---
# <a name="data-conversion-transformation"></a><span data-ttu-id="a0321-102">transformation de conversion de données</span><span class="sxs-lookup"><span data-stu-id="a0321-102">Data Conversion Transformation</span></span>
  <span data-ttu-id="a0321-103">La transformation de conversion de données convertit les données d'une colonne d'entrée en un type de données différent, puis les copie dans une nouvelle colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="a0321-103">The Data Conversion transformation converts the data in an input column to a different data type and then copies it to a new output column.</span></span> <span data-ttu-id="a0321-104">Par exemple, un package peut extraire des données de plusieurs sources, puis utiliser cette transformation pour convertir des colonnes vers le type de données requis par la banque de données de destination.</span><span class="sxs-lookup"><span data-stu-id="a0321-104">For example, a package can extract data from multiple sources, and then use this transformation to convert columns to the data type required by the destination data store.</span></span> <span data-ttu-id="a0321-105">Vous pouvez appliquer plusieurs conversions à une même colonne d'entrée.</span><span class="sxs-lookup"><span data-stu-id="a0321-105">You can apply multiple conversions to a single input column.</span></span>  
  
 <span data-ttu-id="a0321-106">Cette transformation permet à un package de réaliser les types de conversions de données suivants :</span><span class="sxs-lookup"><span data-stu-id="a0321-106">Using this transformation, a package can perform the following types of data conversions:</span></span>  
  
-   <span data-ttu-id="a0321-107">Modifier le type de données.</span><span class="sxs-lookup"><span data-stu-id="a0321-107">Change the data type.</span></span> <span data-ttu-id="a0321-108">Pour plus d’informations, consultez [Types de données Integration Services](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="a0321-108">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0321-109">Si vous convertissez des données en un type de données date ou datetime, la date de la colonne de sortie est exprimée dans le format ISO, bien que la préférence des paramètres régionaux puisse spécifier un format différent.</span><span class="sxs-lookup"><span data-stu-id="a0321-109">If you are converting data to a date or a datetime data type, the date in the output column is in the ISO format, although the locale preference may specify a different format.</span></span>  
  
-   <span data-ttu-id="a0321-110">Définir la longueur de colonne des données de chaîne ainsi que la précision et l'échelle des données numériques.</span><span class="sxs-lookup"><span data-stu-id="a0321-110">Set the column length of string data and the precision and scale on numeric data.</span></span> <span data-ttu-id="a0321-111">Pour plus d’informations, consultez [Précision, échelle et longueur &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a0321-111">For more information, see [Precision, Scale, and Length &#40;Transact-SQL&#41;](/sql/t-sql/data-types/precision-scale-and-length-transact-sql).</span></span>  
  
-   <span data-ttu-id="a0321-112">Spécifier une page de codes.</span><span class="sxs-lookup"><span data-stu-id="a0321-112">Specify a code page.</span></span> <span data-ttu-id="a0321-113">Pour plus d'informations, voir [Comparing String Data](../comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="a0321-113">For more information, see [Comparing String Data](../comparing-string-data.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a0321-114">Lors d'une copie entre deux colonnes de type de données chaîne, celles-ci doivent utiliser la même page de codes.</span><span class="sxs-lookup"><span data-stu-id="a0321-114">When copying between columns with a string data type, the two columns must use the same code page.</span></span>  
  
 <span data-ttu-id="a0321-115">Si une colonne de sortie de données de type chaîne est plus courte que la colonne d'entrée correspondante, les données de sortie sont tronquées.</span><span class="sxs-lookup"><span data-stu-id="a0321-115">If the length of an output column of string data is shorter than the length of its corresponding input column, the output data is truncated.</span></span> <span data-ttu-id="a0321-116">Pour plus d’informations, consultez [Gestion des erreurs dans les données](../error-handling-in-data.md).</span><span class="sxs-lookup"><span data-stu-id="a0321-116">For more information, see [Error Handling in Data](../error-handling-in-data.md).</span></span>  
  
 <span data-ttu-id="a0321-117">Cette transformation a une entrée, une sortie et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a0321-117">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a0321-118">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a0321-118">Related Tasks</span></span>  
 <span data-ttu-id="a0321-119">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programme.</span><span class="sxs-lookup"><span data-stu-id="a0321-119">You can set properties through the [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="a0321-120">Pour plus d’informations sur l’utilisation de la transformation de conversion de données dans le Concepteur SSIS, consultez [Convertir des données en un type différent à l’aide de la transformation de conversion de données](data-conversion-transformation.md) et [Éditeur de transformation de conversion de données](../../data-conversion-transformation-editor.md).</span><span class="sxs-lookup"><span data-stu-id="a0321-120">For information about using the Data Conversion Transformation in the SSIS Designer, see [Convert Data to a Different Data Type by Using the Data Conversion Transformation](data-conversion-transformation.md) and [Data Conversion Transformation Editor](../../data-conversion-transformation-editor.md).</span></span> <span data-ttu-id="a0321-121">Pour plus d’informations sur la définition des propriétés de cette transformation par programmation, consultez [Propriétés courantes](../../common-properties.md) et [Propriétés personnalisées des transformations](transformation-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="a0321-121">For information about setting properties of this transformation programmatically, see [Common Properties](../../common-properties.md) and [Transformation Custom Properties](transformation-custom-properties.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="a0321-122">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="a0321-122">Related Content</span></span>  
 <span data-ttu-id="a0321-123">Entrée de blog, [Comparaison des performances des différentes techniques de conversion de type de données dans SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), sur blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="a0321-123">Blog entry, [Performance Comparison between Data Type Conversion Techniques in SSIS 2008](https://techcommunity.microsoft.com/t5/datacat/performance-comparison-between-data-type-conversion-techniques/ba-p/305035), on blogs.msdn.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0321-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0321-124">See Also</span></span>  
 <span data-ttu-id="a0321-125">[Analyse rapide](../../fast-parse.md) </span><span class="sxs-lookup"><span data-stu-id="a0321-125">[Fast Parse](../../fast-parse.md) </span></span>  
 <span data-ttu-id="a0321-126">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="a0321-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="a0321-127">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="a0321-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
