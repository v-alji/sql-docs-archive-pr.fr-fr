---
title: '? : (Conditionnel) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- conditional operator (?:)
- '?: (conditional operator)'
ms.assetid: d38e6890-7338-4ce0-a837-2dbb41823a37
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e607f9ed495184ef47ac2e4f1139b9a9566055ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614184"
---
# <a name="--conditional-ssis-expression"></a><span data-ttu-id="57770-103">?</span><span class="sxs-lookup"><span data-stu-id="57770-103">?</span></span> <span data-ttu-id="57770-104">: (Conditionnel) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="57770-104">: (Conditional) (SSIS Expression)</span></span>
  <span data-ttu-id="57770-105">Renvoie une des deux expressions selon l'évaluation d'une expression booléenne.</span><span class="sxs-lookup"><span data-stu-id="57770-105">Returns one of two expressions based on the evaluation of a Boolean expression.</span></span> <span data-ttu-id="57770-106">Si l'expression booléenne donne la valeur TRUE, la première expression est évaluée et le résultat est le résultat de l'expression.</span><span class="sxs-lookup"><span data-stu-id="57770-106">If the Boolean expression evaluates to TRUE, then the first expression is evaluated and the result is the expression result.</span></span> <span data-ttu-id="57770-107">Si l'expression booléenne donne la valeur FALSE, la deuxième expression est évaluée et son résultat est le résultat de l'expression.</span><span class="sxs-lookup"><span data-stu-id="57770-107">If the Boolean expression evaluates to FALSE then the second expression is evaluated and its result is the expression result.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57770-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="57770-108">Syntax</span></span>  
  
```  
  
boolean_expression?expression1:expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="57770-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="57770-109">Arguments</span></span>  
 <span data-ttu-id="57770-110">*boolean_expression*</span><span class="sxs-lookup"><span data-stu-id="57770-110">*boolean_expression*</span></span>  
 <span data-ttu-id="57770-111">Expression valide qui renvoie TRUE, FALSE ou NULL.</span><span class="sxs-lookup"><span data-stu-id="57770-111">Is any valid expression that evaluates to TRUE, FALSE, or NULL.</span></span>  
  
 <span data-ttu-id="57770-112">*expression1*</span><span class="sxs-lookup"><span data-stu-id="57770-112">*expression1*</span></span>  
 <span data-ttu-id="57770-113">Peut être toute expression valide.</span><span class="sxs-lookup"><span data-stu-id="57770-113">Is any valid expression.</span></span>  
  
 <span data-ttu-id="57770-114">*expression2*</span><span class="sxs-lookup"><span data-stu-id="57770-114">*expression2*</span></span>  
 <span data-ttu-id="57770-115">Peut être toute expression valide.</span><span class="sxs-lookup"><span data-stu-id="57770-115">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="57770-116">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="57770-116">Result Types</span></span>  
 <span data-ttu-id="57770-117">Type de données de *expression1* ou de *expression2*.</span><span class="sxs-lookup"><span data-stu-id="57770-117">The data type of *expression1* or *expression2*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57770-118">Notes</span><span class="sxs-lookup"><span data-stu-id="57770-118">Remarks</span></span>  
 <span data-ttu-id="57770-119">Si l’argument *expression_booléenne* est évalué à NULL, le résultat de l’expression est NULL.</span><span class="sxs-lookup"><span data-stu-id="57770-119">If the *boolean_expression* evaluates to NULL, the expression result is NULL.</span></span> <span data-ttu-id="57770-120">Si une expression sélectionnée, *expression1* ou *expression2* est NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="57770-120">If a selected expression, either *expression1* or *expression2* is NULL, the result is NULL.</span></span> <span data-ttu-id="57770-121">Si une expression sélectionnée n'est pas NULL, mais que l'expression non sélectionnée est NULL, le résultat est la valeur de l'expression sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="57770-121">If a selected expression is not NULL, but the one not selected is NULL, the result is the value of the selected expression.</span></span>  
  
 <span data-ttu-id="57770-122">Si *expression1* et *expression2* ont le même type de données, le résultat est de ce type de données.</span><span class="sxs-lookup"><span data-stu-id="57770-122">If *expression1* and *expression2* have the same data type, the result is that data type.</span></span> <span data-ttu-id="57770-123">Les règles supplémentaires suivantes s'appliquent aux types de résultats :</span><span class="sxs-lookup"><span data-stu-id="57770-123">The following additional rules apply to result types:</span></span>  
  
-   <span data-ttu-id="57770-124">Le type de données DT_TEXT nécessite que *expression1* et *expression2* aient la même page de codes.</span><span class="sxs-lookup"><span data-stu-id="57770-124">The DT_TEXT data type requires that *expression1* and *expression2* have the same code page.</span></span>  
  
-   <span data-ttu-id="57770-125">La longueur d'un résultat dont le type de données est DT_BYTES correspond à la longueur de l'argument le plus long.</span><span class="sxs-lookup"><span data-stu-id="57770-125">The length of a result with the DT_BYTES data type is the length of the longer argument.</span></span>  
  
 <span data-ttu-id="57770-126">L’ensemble d’expressions, *expression1* et *expression2*, doit s’évaluer à des types de données valides et être conforme à une des règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="57770-126">The expression set, *expression1* and *expression2*, must evaluate to valid data types and follow one of these rules:</span></span>  
  
-   <span data-ttu-id="57770-127">**Numérique** : *expression1* et *expression2* doivent toutes deux être d’un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="57770-127">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="57770-128">L'intersection des types de données doit être de type de données numérique, comme le spécifient les règles relatives aux conversions numériques implicites effectuées par l'évaluateur d'expression.</span><span class="sxs-lookup"><span data-stu-id="57770-128">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="57770-129">L'intersection des deux types de données numériques ne peut pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="57770-129">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="57770-130">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="57770-130">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="57770-131">**Chaîne** : *expression1* et *expression2* doivent toutes deux être d’un type de données chaîne : DT_STR ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="57770-131">**String** Both *expression1* and *expression2* must be a string data type: DT_STR or DT_WSTR.</span></span> <span data-ttu-id="57770-132">Les deux expressions peuvent avoir une valeur de types de données chaîne différents.</span><span class="sxs-lookup"><span data-stu-id="57770-132">The two expressions can evaluate to different string data types.</span></span> <span data-ttu-id="57770-133">Le résultat a le type de données DT_WSTR et une longueur équivalente à celle de l'argument le plus long.</span><span class="sxs-lookup"><span data-stu-id="57770-133">The result has the DT_WSTR data type with a length of the longer argument.</span></span>  
  
-   <span data-ttu-id="57770-134">**Date, Heure ou Date/Heure** : *expression1* et *expression2* doivent toutes deux s’évaluer à un des types de données suivants : DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET ou DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="57770-134">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="57770-135">Le système ne prend pas en charge les comparaisons entre une expression qui correspond à un type de données heure et une expression qui correspond à un type de données date ou date/heure.</span><span class="sxs-lookup"><span data-stu-id="57770-135">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="57770-136">Le système génère alors une erreur.</span><span class="sxs-lookup"><span data-stu-id="57770-136">The system generates an error.</span></span>  
  
     <span data-ttu-id="57770-137">Lors de la comparaison des expressions, le système applique les règles de conversion suivantes dans l'ordre indiqué :</span><span class="sxs-lookup"><span data-stu-id="57770-137">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="57770-138">Lorsque les deux expressions correspondent au même type de données, une comparaison de ce type de données est effectuée.</span><span class="sxs-lookup"><span data-stu-id="57770-138">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="57770-139">Si une expression est d'un type de données DT_DBTIMESTAMPOFFSET, l'autre expression est implicitement convertie en DT_DBTIMESTAMPOFFSET et une comparaison DT_DBTIMESTAMPOFFSET est effectuée.</span><span class="sxs-lookup"><span data-stu-id="57770-139">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="57770-140">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="57770-140">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="57770-141">Si une expression est d'un type de données DT_DBTIMESTAMP2, l'autre expression est implicitement convertie en DT_DBTIMESTAMP2 et une comparaison DT_DBTIMESTAMP2 est effectuée.</span><span class="sxs-lookup"><span data-stu-id="57770-141">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="57770-142">Si une expression est d'un type de données DT_DBTIME2, l'autre expression est implicitement convertie en DT_DBTIME2 et une comparaison DT_DBTIME2 est effectuée.</span><span class="sxs-lookup"><span data-stu-id="57770-142">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="57770-143">Si une expression est d'un type autre que DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 ou DT_DBTIME2, les expressions sont converties en type de données DT_DBTIMESTAMP avant leur comparaison.</span><span class="sxs-lookup"><span data-stu-id="57770-143">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="57770-144">Lors de la comparaison des expressions, le système émet les hypothèses suivantes :</span><span class="sxs-lookup"><span data-stu-id="57770-144">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="57770-145">Si chaque expression est d'un type de données qui inclut des fractions de seconde, le système suppose que le type de données avec le moins grand nombre de chiffres pour les fractions de seconde inclut des zéros pour les chiffres restants.</span><span class="sxs-lookup"><span data-stu-id="57770-145">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="57770-146">Si chaque expression est d'un type de données date, mais qu'une seule a un décalage de fuseau horaire, le système suppose que le type de données date sans le décalage de fuseau horaire est exprimé en temps universel coordonné (UTC).</span><span class="sxs-lookup"><span data-stu-id="57770-146">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="57770-147">Pour plus d'informations sur les types de données, consultez [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="57770-147">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="57770-148">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="57770-148">Expression Examples</span></span>  
 <span data-ttu-id="57770-149">L'exemple suivant montre une expression qui selon une condition prend la valeur `savannah` ou `unknown`.</span><span class="sxs-lookup"><span data-stu-id="57770-149">This example shows an expression that conditionally evaluates to `savannah` or `unknown`.</span></span>  
  
```  
@AnimalName == "Elephant"? "savannah": "unknown"  
```  
  
 <span data-ttu-id="57770-150">L’exemple suivant montre une expression qui fait référence une colonne **ListPrice** .</span><span class="sxs-lookup"><span data-stu-id="57770-150">This example shows an expression that references a **ListPrice** column.</span></span> <span data-ttu-id="57770-151">La colonne**ListPrice** a le type de données DT_CY.</span><span class="sxs-lookup"><span data-stu-id="57770-151">**ListPrice** has the DT_CY data type.</span></span> <span data-ttu-id="57770-152">L’expression multiplie selon une condition la valeur de la colonne **ListPrice** par 0,2 ou 0,1.</span><span class="sxs-lookup"><span data-stu-id="57770-152">The expression conditionally multiplies **ListPrice** by .2 or .1.</span></span>  
  
```  
ListPrice < 350.00 ? ListPrice * .2 : ListPrice * .1  
```  
  
## <a name="see-also"></a><span data-ttu-id="57770-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57770-153">See Also</span></span>  
 <span data-ttu-id="57770-154">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="57770-154">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="57770-155">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="57770-155">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
