---
title: Analyse rapide | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- fast parse [Integration Services]
ms.assetid: 6688707d-3c5b-404e-aa2f-e13092ac8d95
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 343b8b8b74338512dbf29b3d2efd436df1ffa8ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704308"
---
# <a name="fast-parse"></a><span data-ttu-id="a7da9-102">Analyse rapide</span><span class="sxs-lookup"><span data-stu-id="a7da9-102">Fast Parse</span></span>
  <span data-ttu-id="a7da9-103">L'analyse rapide propose un ensemble de routines simples et rapides d'analyse des données.</span><span class="sxs-lookup"><span data-stu-id="a7da9-103">Fast parse provides a fast, simple set of routines for parsing data.</span></span> <span data-ttu-id="a7da9-104">Ces routines ne tiennent pas compte des paramètres régionaux et prennent en charge uniquement un sous-ensemble de formats de date, d'heure et d'entier.</span><span class="sxs-lookup"><span data-stu-id="a7da9-104">These routines are not locale-sensitive and they support only a subset of date, time, and integer formats.</span></span>  
  
## <a name="requirements-and-limitations"></a><span data-ttu-id="a7da9-105">Limitations et exigences</span><span class="sxs-lookup"><span data-stu-id="a7da9-105">Requirements and Limitations</span></span>  
 <span data-ttu-id="a7da9-106">En implémentant l'analyse rapide, un package perd sa capacité d'interpréter les données de type date, heure et nombre dans des formats régionaux et dans de nombreux formats de base et étendus ISO 9601 couramment utilisés, mais il améliore ses performances.</span><span class="sxs-lookup"><span data-stu-id="a7da9-106">By implementing fast parse, a package forfeits its ability to interpret date, time, and numeric data in locale-specific formats and many frequently used ISO 8601 basic and extended formats, but the package enhances its performance.</span></span> <span data-ttu-id="a7da9-107">Par exemple, l'analyse rapide prend uniquement en charge les formats de date les plus courants, tels que AAAAMMJJ et AAAA-MM-JJ, n'effectue aucune analyse des spécificités régionales, ne reconnaît pas les caractères spéciaux dans les devises et ne peut pas convertir les représentations hexadécimales ou scientifiques des entiers.</span><span class="sxs-lookup"><span data-stu-id="a7da9-107">For example, fast parse supports only the most commonly used date format representations such as YYYYMMDD and YYYY-MM-DD, does not perform locale-specific parsing, does not recognize special characters in currency data, and cannot convert hexadecimal or scientific representation of integers.</span></span>  
  
 <span data-ttu-id="a7da9-108">L'analyse rapide est disponible uniquement lorsque vous utilisez la source de fichier plat ou la transformation de conversion de données.</span><span class="sxs-lookup"><span data-stu-id="a7da9-108">Fast parse is available only when you use the Flat File source or the Data Conversion transformation.</span></span> <span data-ttu-id="a7da9-109">L'amélioration des performances pouvant être significative, pensez à utiliser si possible l'analyse rapide dans ces composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="a7da9-109">The increase in performance can be significant, and you should consider using fast parse in these data flow components if you can.</span></span>  
  
 <span data-ttu-id="a7da9-110">Si le flux de données du package requiert une analyse des spécificités régionales, il est préférable d'utiliser l'analyse standard.</span><span class="sxs-lookup"><span data-stu-id="a7da9-110">If the data flow in the package requires locale-sensitive parsing, standard parse is recommended instead of fast parse.</span></span> <span data-ttu-id="a7da9-111">Par exemple, l'analyse rapide ne reconnaît pas les données qui incluent des symboles décimaux comme la virgule, les formats de date autres que année-mois-jour ou encore les symboles de devises.</span><span class="sxs-lookup"><span data-stu-id="a7da9-111">For example, fast parse does not recognize locale-sensitive data that includes decimal symbols such as the comma, date formats other than year-month-date formats, and currency symbols.</span></span>  
  
 <span data-ttu-id="a7da9-112">Les représentations tronquées qui laissent supposer une ou plusieurs parties de la date, comme un siècle, une année ou un mois, ne sont pas reconnues par l'analyse rapide.</span><span class="sxs-lookup"><span data-stu-id="a7da9-112">Truncated representations that imply one or more date parts, such as a century, a year, or a month, are not recognized by fast parse.</span></span> <span data-ttu-id="a7da9-113">Par exemple, l’analyse rapide ne reconnaît pas le format '**-AAMM**', qui indique une année et un mois dans un siècle implicite, ni le format '**--MM**', qui spécifie un mois dans une année implicite.</span><span class="sxs-lookup"><span data-stu-id="a7da9-113">For example, fast parse recognizes neither the '**-YYMM**' format, which specifies a year and month in an implied century, nor '**--MM**', which specifies a month in an implied year.</span></span> <span data-ttu-id="a7da9-114">Cependant, certaines représentations avec une précision réduite sont reconnues.</span><span class="sxs-lookup"><span data-stu-id="a7da9-114">However, some representations with reduced precision are recognized.</span></span> <span data-ttu-id="a7da9-115">Ainsi, l'analyse rapide reconnaît le format 'hhmm', qui indique les heures et les minutes uniquement, et '**AAAA**', qui indique l'année uniquement.</span><span class="sxs-lookup"><span data-stu-id="a7da9-115">For example, fast parse recognizes the 'hhmm;' format, which indicates hour and minute only, and '**YYYY**', which indicates year only.</span></span>  
  
 <span data-ttu-id="a7da9-116">L'analyse rapide est spécifiée au niveau de la colonne.</span><span class="sxs-lookup"><span data-stu-id="a7da9-116">Fast parse is specified at the column level.</span></span> <span data-ttu-id="a7da9-117">Dans la source de fichier plat et la transformation de conversion de données, vous pouvez spécifier l'analyse rapide sur les colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="a7da9-117">In the Flat File source and the Data Conversion transformation, you can specify Fast parse on output columns.</span></span> <span data-ttu-id="a7da9-118">Les entrées et les sorties peuvent inclure des colonnes respectant des spécificités régionales et des colonnes n'en respectant pas.</span><span class="sxs-lookup"><span data-stu-id="a7da9-118">Inputs and outputs can include both locale-sensitive and locale-insensitive columns.</span></span>  
  
 <span data-ttu-id="a7da9-119">Pour plus d'informations sur les formats de données pris en charge par l'analyse rapide, consultez [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) et [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span><span class="sxs-lookup"><span data-stu-id="a7da9-119">For more information about the data formats that Fast parse supports, see [Numeric Data Formats](../../2014/integration-services/numeric-data-formats.md) and [Date and Time Formats](../../2014/integration-services/date-and-time-formats.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a7da9-120">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a7da9-120">Related Tasks</span></span>  
 [<span data-ttu-id="a7da9-121">Définir l'analyse rapide</span><span class="sxs-lookup"><span data-stu-id="a7da9-121">Set Fast Parse</span></span>](../../2014/integration-services/set-fast-parse.md)  
  
  
