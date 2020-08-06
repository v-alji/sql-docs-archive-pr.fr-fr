---
title: Analyse de données | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- parsing [Integration Services]
- data parsing [Integration Services]
ms.assetid: 8893ea9d-634c-4309-b52c-6337222dcb39
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3bd34cd83351e31313ae96ff5709ec999a60f2f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602926"
---
# <a name="parsing-data"></a><span data-ttu-id="f035b-102">Analyse de données</span><span class="sxs-lookup"><span data-stu-id="f035b-102">Parsing Data</span></span>
  <span data-ttu-id="f035b-103">Les flux de données des packages extraient et chargent des données à partir de banques de données hétérogènes qui peuvent utiliser différents types de données standard et personnalisés.</span><span class="sxs-lookup"><span data-stu-id="f035b-103">Data flows in packages extract and load data between heterogeneous data stores, which may use a variety of standard and custom data types.</span></span> <span data-ttu-id="f035b-104">Dans un flux de données, les sources [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sont chargées d’extraire les données, d’analyser les données de type string et de les convertir en données de type [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f035b-104">In a data flow, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sources do the work of extracting data, parsing string data, and converting data to an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] data type.</span></span> <span data-ttu-id="f035b-105">Les transformations effectuées par la suite peuvent analyser les données afin de les convertir en un type distinct ou créer des copies de colonnes avec d'autres types de données.</span><span class="sxs-lookup"><span data-stu-id="f035b-105">Subsequent transformations may parse data to convert it to a different data type, or create column copies with different data types.</span></span> <span data-ttu-id="f035b-106">Les expressions utilisées dans les composants peuvent également convertir les arguments et opérandes en d'autres types de données.</span><span class="sxs-lookup"><span data-stu-id="f035b-106">Expressions used in components may also cast arguments and operands to different data types.</span></span> <span data-ttu-id="f035b-107">Enfin, lorsque les données sont chargées dans une banque de données, la destination peut analyser les données afin de les convertir en un type de données utilisé par la destination.</span><span class="sxs-lookup"><span data-stu-id="f035b-107">Finally, when the data is loaded into a data store, the destination may parse the data to convert it to a data type that the destination uses.</span></span> <span data-ttu-id="f035b-108">Pour plus d’informations, consultez [Types de données Integration Services](integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="f035b-108">For more information, see [Integration Services Data Types](integration-services-data-types.md).</span></span>  
  
## <a name="types-of-parsing"></a><span data-ttu-id="f035b-109">Types d'analyses</span><span class="sxs-lookup"><span data-stu-id="f035b-109">Types of Parsing</span></span>  
 [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="f035b-110">propose deux types d’analyses en vue de convertir les données : l’analyse rapide et l’analyse standard.</span><span class="sxs-lookup"><span data-stu-id="f035b-110">provides two types of parsing for converting data: Fast parse and Standard parse.</span></span>  
  
-   <span data-ttu-id="f035b-111">L'analyse rapide est un ensemble de routines simple et rapide d'analyse des données. Elle ne prend pas en charge la conversion des données présentant des spécificités régionales et accepte uniquement les formats de date et d'heure les plus courants.</span><span class="sxs-lookup"><span data-stu-id="f035b-111">Fast parse is a fast, simple set of parsing routines that does not support locale-specific data type conversions, and supports only the most frequently used date and time formats.</span></span> <span data-ttu-id="f035b-112">Pour plus d’informations, consultez [Analyse rapide](../fast-parse.md).</span><span class="sxs-lookup"><span data-stu-id="f035b-112">For more information, see [Fast Parse](../fast-parse.md).</span></span>  
  
-   <span data-ttu-id="f035b-113">L'analyse standard est un ensemble complet de routines d'analyse qui prend en charge la conversion de tous les types de données fournis par les API de conversion de type de données Automation disponibles dans Oleaut32.dll et Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="f035b-113">Standard parse is a rich set of parsing routines that supports all the data type conversions that are provided by the Automation data type conversion APIs available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="f035b-114">Pour plus d’informations, consultez [Analyse standard](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="f035b-114">For more information, see [Standard Parse](../standard-parse.md).</span></span>  
  
  
