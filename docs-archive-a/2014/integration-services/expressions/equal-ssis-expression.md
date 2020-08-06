---
title: == (Égal à) (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- equal operator (==)
- == (equal operator)
ms.assetid: 36fd2354-7b93-4c95-9cf3-51ee24568950
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 12f92a267543c366dee4905010aeb84d93c4f408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701477"
---
# <a name="-equal-ssis-expression"></a><span data-ttu-id="985b7-102">== (Égal à) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="985b7-102">== (Equal) (SSIS Expression)</span></span>
  <span data-ttu-id="985b7-103">Effectue une comparaison pour déterminer si deux expressions sont égales.</span><span class="sxs-lookup"><span data-stu-id="985b7-103">Performs a comparison to determine if two expressions are equal.</span></span> <span data-ttu-id="985b7-104">L'évaluateur d'expression convertit automatiquement de nombreux types de données avant de réaliser la comparaison.</span><span class="sxs-lookup"><span data-stu-id="985b7-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span> <span data-ttu-id="985b7-105">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="985b7-105">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
 <span data-ttu-id="985b7-106">Toutefois, pour certains types de données, il est nécessaire que l'expression contienne une conversion explicite afin qu'elle puisse être évaluée correctement.</span><span class="sxs-lookup"><span data-stu-id="985b7-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="985b7-107">Pour plus d’informations sur les conversions valides entre les types de données, consultez [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="985b7-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="985b7-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="985b7-108">Syntax</span></span>  
  
```  
  
expression1 == expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="985b7-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="985b7-109">Arguments</span></span>  
 <span data-ttu-id="985b7-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="985b7-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="985b7-111">Peut être toute expression valide.</span><span class="sxs-lookup"><span data-stu-id="985b7-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="985b7-112">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="985b7-112">Result Types</span></span>  
 <span data-ttu-id="985b7-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="985b7-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="985b7-114">Notes</span><span class="sxs-lookup"><span data-stu-id="985b7-114">Remarks</span></span>  
 <span data-ttu-id="985b7-115">Si l'une des expressions de la comparaison est NULL, le résultat de la comparaison est NULL.</span><span class="sxs-lookup"><span data-stu-id="985b7-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="985b7-116">Si les deux expressions sont NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="985b7-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="985b7-117">Le jeu d’expressions, *expression1* et *expression2*, doit suivre une des règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="985b7-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="985b7-118">**Numérique** : *expression1* et *expression2* doivent toutes deux être d’un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="985b7-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="985b7-119">L’intersection des types de données doit être un type de données numérique, comme le spécifient les règles relatives aux conversions numériques implicites effectuées par l’évaluateur d’expression.</span><span class="sxs-lookup"><span data-stu-id="985b7-119">The intersection of the data types must be a numeric data type, as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="985b7-120">L'intersection des deux types de données numériques ne peut pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="985b7-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="985b7-121">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="985b7-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="985b7-122">**Caractère** : *expression1* et *expression2* doivent toutes deux s’évaluer à un type de données DT_STR ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="985b7-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="985b7-123">Les deux expressions peuvent avoir une valeur de types de données chaîne différents.</span><span class="sxs-lookup"><span data-stu-id="985b7-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="985b7-124">Les comparaisons de chaîne respectent la casse, les accents, le jeu de caractères Kana et la largeur.</span><span class="sxs-lookup"><span data-stu-id="985b7-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="985b7-125">**Date, Heure ou Date/Heure** : *expression1* et *expression2* doivent toutes deux s’évaluer à un des types de données suivants : DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET ou DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="985b7-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="985b7-126">Le système ne prend pas en charge les comparaisons entre une expression qui correspond à un type de données heure et une expression qui correspond à un type de données date ou date/heure.</span><span class="sxs-lookup"><span data-stu-id="985b7-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="985b7-127">Le système génère alors une erreur.</span><span class="sxs-lookup"><span data-stu-id="985b7-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="985b7-128">Lors de la comparaison des expressions, le système applique les règles de conversion suivantes dans l'ordre indiqué :</span><span class="sxs-lookup"><span data-stu-id="985b7-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="985b7-129">Lorsque les deux expressions correspondent au même type de données, une comparaison de ce type de données est effectuée.</span><span class="sxs-lookup"><span data-stu-id="985b7-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="985b7-130">Si une expression est d'un type de données DT_DBTIMESTAMPOFFSET, l'autre expression est implicitement convertie en DT_DBTIMESTAMPOFFSET et une comparaison DT_DBTIMESTAMPOFFSET est effectuée.</span><span class="sxs-lookup"><span data-stu-id="985b7-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="985b7-131">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="985b7-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="985b7-132">Si une expression est d'un type de données DT_DBTIMESTAMP2, l'autre expression est implicitement convertie en DT_DBTIMESTAMP2 et une comparaison DT_DBTIMESTAMP2 est effectuée.</span><span class="sxs-lookup"><span data-stu-id="985b7-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="985b7-133">Si une expression est d'un type de données DT_DBTIME2, l'autre expression est implicitement convertie en DT_DBTIME2 et une comparaison DT_DBTIME2 est effectuée.</span><span class="sxs-lookup"><span data-stu-id="985b7-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="985b7-134">Si une expression est d'un type autre que DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 ou DT_DBTIME2, les expressions sont converties en type de données DT_DBTIMESTAMP avant leur comparaison.</span><span class="sxs-lookup"><span data-stu-id="985b7-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="985b7-135">Lors de la comparaison des expressions, le système émet les hypothèses suivantes :</span><span class="sxs-lookup"><span data-stu-id="985b7-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="985b7-136">Si chaque expression est d'un type de données qui inclut des fractions de seconde, le système suppose que le type de données avec le moins grand nombre de chiffres pour les fractions de seconde inclut des zéros pour les chiffres restants.</span><span class="sxs-lookup"><span data-stu-id="985b7-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="985b7-137">Si chaque expression est d'un type de données date, mais qu'une seule a un décalage de fuseau horaire, le système suppose que le type de données date sans le décalage de fuseau horaire est exprimé en temps universel coordonné (UTC).</span><span class="sxs-lookup"><span data-stu-id="985b7-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
-   <span data-ttu-id="985b7-138">**Logique** : *expression1* et *expression2* doivent toutes deux s’évaluer à une valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="985b7-138">**Logical** Both *expression1* and *expression2* must evaluate to a Boolean.</span></span>  
  
-   <span data-ttu-id="985b7-139">**GUID** : *expression1* et *expression2* doivent toutes deux s’évaluer au type de données DT_GUID.</span><span class="sxs-lookup"><span data-stu-id="985b7-139">**GUID** Both *expression1* and *expression2* must evaluate to the DT_GUID data type.</span></span>  
  
-   <span data-ttu-id="985b7-140">**Binaire** : *expression1* et *expression2* doivent toutes deux s’évaluer au type de données DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="985b7-140">**Binary** Both *expression1* and *expression2* must evaluate to the DT_BYTES data type.</span></span>  
  
-   <span data-ttu-id="985b7-141">**BLOB** : *expression1* et *expression2* doivent toutes deux s’évaluer au même type de données BLOB (Binary Large Object Block) : DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="985b7-141">**BLOB** Both *expression1* and *expression2* must evaluate to the same Binary Large Object Block (BLOB) data type: DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span>  
  
 <span data-ttu-id="985b7-142">Pour plus d'informations sur les types de données, consultez [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="985b7-142">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="985b7-143">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="985b7-143">Expression Examples</span></span>  
 <span data-ttu-id="985b7-144">L'exemple suivant renvoie la valeur TRUE si la date actuelle est le 4 juillet 2003.</span><span class="sxs-lookup"><span data-stu-id="985b7-144">This example evaluates to TRUE if the current date is July 4, 2003.</span></span> <span data-ttu-id="985b7-145">Pour plus d’informations, consultez [GETDATE &#40;expression SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="985b7-145">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="985b7-146">"7/4/2003" == GETDATE()</span><span class="sxs-lookup"><span data-stu-id="985b7-146">"7/4/2003" == GETDATE()</span></span>  
  
 <span data-ttu-id="985b7-147">L’exemple suivant retourne la valeur TRUE si la valeur de la colonne **ListPrice** est 500.</span><span class="sxs-lookup"><span data-stu-id="985b7-147">This example evaluates to TRUE if the value in the **ListPrice** column is 500.</span></span>  
  
```  
ListPrice == 500  
```  
  
 <span data-ttu-id="985b7-148">Cet exemple utilise la variable **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="985b7-148">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="985b7-149">Il retourne la valeur TRUE si la valeur de la variable **LPrice** est 500.</span><span class="sxs-lookup"><span data-stu-id="985b7-149">It evaluates to TRUE if the value of **LPrice** is 500.</span></span> <span data-ttu-id="985b7-150">Le type de données de la variable doit être numérique pour permettre l'analyse correcte de l'expression.</span><span class="sxs-lookup"><span data-stu-id="985b7-150">The data type of the variable must be numeric for the expression to parse successfully.</span></span>  
  
```  
@LPrice == 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="985b7-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="985b7-151">See Also</span></span>  
 <span data-ttu-id="985b7-152">[\!= &#40;Non égal&#41; &#40;expression SSIS&#41;](equal-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="985b7-152">[!= &#40;Unequal&#41; &#40;SSIS Expression&#41;](equal-ssis-expression.md) </span></span>  
 <span data-ttu-id="985b7-153">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="985b7-153">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="985b7-154">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="985b7-154">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
