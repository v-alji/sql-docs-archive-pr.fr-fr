---
title: '&lt; (Inférieur à) (expression SSIS) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- less than (<)
- < (less than operator)
ms.assetid: 8674afdc-4276-46cb-be08-5aadfe8b9624
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d8367e337fe92667d5bdc39638d03af390797b28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704327"
---
# <a name="lt-less-than-ssis-expression"></a><span data-ttu-id="4d71e-102">&lt; (Inférieur à) (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="4d71e-102">&lt; (Less Than) (SSIS Expression)</span></span>
  <span data-ttu-id="4d71e-103">Effectue une comparaison pour déterminer si la première expression est inférieure à la deuxième.</span><span class="sxs-lookup"><span data-stu-id="4d71e-103">Performs a comparison to determine if the first expression is less than the second one.</span></span> <span data-ttu-id="4d71e-104">L'évaluateur d'expression convertit automatiquement de nombreux types de données avant de réaliser la comparaison.</span><span class="sxs-lookup"><span data-stu-id="4d71e-104">The expression evaluator automatically converts many data types before it performs the comparison.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4d71e-105">Cet opérateur ne prend pas en charge les comparaisons qui utilisent les types de données DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="4d71e-105">This operator does not support comparisons that use the DT_TEXT, DT_NTEXT, or DT_IMAGE data types.</span></span>  
  
 <span data-ttu-id="4d71e-106">Toutefois, pour certains types de données, il est nécessaire que l'expression contienne une conversion explicite afin qu'elle puisse être évaluée correctement.</span><span class="sxs-lookup"><span data-stu-id="4d71e-106">However, some data types require that the expression include an explicit cast before the expression can be evaluated successfully.</span></span> <span data-ttu-id="4d71e-107">Pour plus d’informations sur les conversions valides entre les types de données, consultez [Cast &#40;expression SSIS&#41;](cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4d71e-107">For more information about legal casts between data types, see [Cast &#40;SSIS Expression&#41;](cast-ssis-expression.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d71e-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4d71e-108">Syntax</span></span>  
  
```  
  
expression1 < expression2  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d71e-109">Arguments</span><span class="sxs-lookup"><span data-stu-id="4d71e-109">Arguments</span></span>  
 <span data-ttu-id="4d71e-110">*expression1, expression2*</span><span class="sxs-lookup"><span data-stu-id="4d71e-110">*expression1, expression2*</span></span>  
 <span data-ttu-id="4d71e-111">Peut être toute expression valide.</span><span class="sxs-lookup"><span data-stu-id="4d71e-111">Is any valid expression.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="4d71e-112">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="4d71e-112">Result Types</span></span>  
 <span data-ttu-id="4d71e-113">DT_BOOL</span><span class="sxs-lookup"><span data-stu-id="4d71e-113">DT_BOOL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d71e-114">Notes</span><span class="sxs-lookup"><span data-stu-id="4d71e-114">Remarks</span></span>  
 <span data-ttu-id="4d71e-115">Si l'une des expressions de la comparaison est NULL, le résultat de la comparaison est NULL.</span><span class="sxs-lookup"><span data-stu-id="4d71e-115">If either expression in the comparison is null, the comparison result is null.</span></span> <span data-ttu-id="4d71e-116">Si les deux expressions sont NULL, le résultat est NULL.</span><span class="sxs-lookup"><span data-stu-id="4d71e-116">If both expressions are null, the result is null.</span></span>  
  
 <span data-ttu-id="4d71e-117">Le jeu d’expressions, *expression1* et *expression2*, doit suivre une des règles suivantes :</span><span class="sxs-lookup"><span data-stu-id="4d71e-117">The expression set, *expression1* and *expression2*, must follow one of these rules:</span></span>  
  
-   <span data-ttu-id="4d71e-118">**Numérique** : *expression1* et *expression2* doivent toutes deux être d’un type de données numérique.</span><span class="sxs-lookup"><span data-stu-id="4d71e-118">**Numeric** Both *expression1* and *expression2* must be a numeric data type.</span></span> <span data-ttu-id="4d71e-119">L'intersection des types de données doit être de type de données numérique, comme le spécifient les règles relatives aux conversions numériques implicites effectuées par l'évaluateur d'expression.</span><span class="sxs-lookup"><span data-stu-id="4d71e-119">The intersection of the data types must be a numeric data type as specified in the rules about the implicit numeric conversions that the expression evaluator performs.</span></span> <span data-ttu-id="4d71e-120">L'intersection des deux types de données numériques ne peut pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="4d71e-120">The intersection of the two numeric data types cannot be null.</span></span> <span data-ttu-id="4d71e-121">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4d71e-121">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
-   <span data-ttu-id="4d71e-122">**Caractère** : *expression1* et *expression2* doivent toutes deux s’évaluer à un type de données DT_STR ou DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="4d71e-122">**Character** Both *expression1* and *expression2* must evaluate to either a DT_STR or a DT_WSTR data type.</span></span> <span data-ttu-id="4d71e-123">Les deux expressions peuvent avoir une valeur de types de données chaîne différents.</span><span class="sxs-lookup"><span data-stu-id="4d71e-123">The two expressions can evaluate to different string data types.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d71e-124">Les comparaisons de chaîne respectent la casse, les accents, le jeu de caractères Kana et la largeur.</span><span class="sxs-lookup"><span data-stu-id="4d71e-124">String comparisons are case, accent, kana, and width-sensitive.</span></span>  
  
-   <span data-ttu-id="4d71e-125">**Date, Heure ou Date/Heure** : *expression1* et *expression2* doivent toutes deux s’évaluer à un des types de données suivants : DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET ou DT_FILETIME.</span><span class="sxs-lookup"><span data-stu-id="4d71e-125">**Date, Time, or Date/Time** Both *expression1* and *expression2* must evaluate to one of the following data types: DT_DBDATE, DT_DATE, DT_DBTIME, DT_DBTIME2, DT_DBTIMESTAMP, DT_DBTIMESTAMP2, DT_DBTIMESTAPMOFFSET, or DT_FILETIME.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4d71e-126">Le système ne prend pas en charge les comparaisons entre une expression qui correspond à un type de données heure et une expression qui correspond à un type de données date ou date/heure.</span><span class="sxs-lookup"><span data-stu-id="4d71e-126">The system does not support comparisons between an expression that evaluates to a time data type and an expression that evaluates to either a date or a date/time data type.</span></span> <span data-ttu-id="4d71e-127">Le système génère alors une erreur.</span><span class="sxs-lookup"><span data-stu-id="4d71e-127">The system generates an error.</span></span>  
  
     <span data-ttu-id="4d71e-128">Lors de la comparaison des expressions, le système applique les règles de conversion suivantes dans l'ordre indiqué :</span><span class="sxs-lookup"><span data-stu-id="4d71e-128">When comparing the expressions, the system applies the following conversion rules in the order listed:</span></span>  
  
    -   <span data-ttu-id="4d71e-129">Lorsque les deux expressions correspondent au même type de données, une comparaison de ce type de données est effectuée.</span><span class="sxs-lookup"><span data-stu-id="4d71e-129">When the two expressions evaluate to the same data type, a comparison of that data type is performed.</span></span>  
  
    -   <span data-ttu-id="4d71e-130">Si une expression est d'un type de données DT_DBTIMESTAMPOFFSET, l'autre expression est implicitement convertie en DT_DBTIMESTAMPOFFSET et une comparaison DT_DBTIMESTAMPOFFSET est effectuée.</span><span class="sxs-lookup"><span data-stu-id="4d71e-130">If one expression is a DT_DBTIMESTAMPOFFSET data type, the other expression is implicitly converted to DT_DBTIMESTAMPOFFSET and a DT_DBTIMESTAMPOFFSET comparison is performed.</span></span> <span data-ttu-id="4d71e-131">Pour plus d’informations, consultez [Types de données Integration Services dans les expressions](integration-services-data-types-in-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4d71e-131">For more information, see [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md).</span></span>  
  
    -   <span data-ttu-id="4d71e-132">Si une expression est d'un type de données DT_DBTIMESTAMP2, l'autre expression est implicitement convertie en DT_DBTIMESTAMP2 et une comparaison DT_DBTIMESTAMP2 est effectuée.</span><span class="sxs-lookup"><span data-stu-id="4d71e-132">If one expression is a DT_DBTIMESTAMP2 data type, the other expression is implicitly converted to DT_DBTIMESTAMP2 and a DT_DBTIMESTAMP2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="4d71e-133">Si une expression est d'un type de données DT_DBTIME2, l'autre expression est implicitement convertie en DT_DBTIME2 et une comparaison DT_DBTIME2 est effectuée.</span><span class="sxs-lookup"><span data-stu-id="4d71e-133">If one expression is a DT_DBTIME2 data type, the other expression is implicitly converted to DT_DBTIME2, and a DT_DBTIME2 comparison is performed.</span></span>  
  
    -   <span data-ttu-id="4d71e-134">Si une expression est d'un type autre que DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2 ou DT_DBTIME2, les expressions sont converties en type de données DT_DBTIMESTAMP avant leur comparaison.</span><span class="sxs-lookup"><span data-stu-id="4d71e-134">If one expression is of a type other than DT_DBTIMESTAMPOFFSET, DT_DBTIMESTAMP2, or DT_DBTIME2, the expressions are converted to the DT_DBTIMESTAMP data type before they are compared.</span></span>  
  
     <span data-ttu-id="4d71e-135">Lors de la comparaison des expressions, le système émet les hypothèses suivantes :</span><span class="sxs-lookup"><span data-stu-id="4d71e-135">When comparing the expressions, the system makes the following assumptions:</span></span>  
  
    -   <span data-ttu-id="4d71e-136">Si chaque expression est d'un type de données qui inclut des fractions de seconde, le système suppose que le type de données avec le moins grand nombre de chiffres pour les fractions de seconde inclut des zéros pour les chiffres restants.</span><span class="sxs-lookup"><span data-stu-id="4d71e-136">If each expression is a data type that includes fractional seconds, the system assumes that the data type with the least number of digits for fractional seconds has zeros for the remaining digits.</span></span>  
  
    -   <span data-ttu-id="4d71e-137">Si chaque expression est d'un type de données date, mais qu'une seule a un décalage de fuseau horaire, le système suppose que le type de données date sans le décalage de fuseau horaire est exprimé en temps universel coordonné (UTC).</span><span class="sxs-lookup"><span data-stu-id="4d71e-137">If each expression is a date data type, but only one has a time zone offset, the system assumes that the date data type without the time zone offset is in Coordinated Universal Time (UTC).</span></span>  
  
 <span data-ttu-id="4d71e-138">Pour plus d'informations sur les types de données, consultez [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="4d71e-138">For more information about data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>  
  
## <a name="expression-examples"></a><span data-ttu-id="4d71e-139">Exemples d'expressions</span><span class="sxs-lookup"><span data-stu-id="4d71e-139">Expression Examples</span></span>  
 <span data-ttu-id="4d71e-140">L'exemple suivant renvoie la valeur TRUE si la date actuelle est ultérieure au 4 juillet 2003.</span><span class="sxs-lookup"><span data-stu-id="4d71e-140">This example evaluates to TRUE if the current date is later than July 4, 2003.</span></span> <span data-ttu-id="4d71e-141">Pour plus d’informations, consultez [GETDATE &#40;expression SSIS&#41;](getdate-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="4d71e-141">For more information, see [GETDATE &#40;SSIS Expression&#41;](getdate-ssis-expression.md).</span></span>  
  
```  
"7/4/2003" < GETDATE()  
```  
  
 <span data-ttu-id="4d71e-142">L’exemple suivant renvoie la valeur TRUE si la valeur de la colonne **ListPrice** est inférieure à 500.</span><span class="sxs-lookup"><span data-stu-id="4d71e-142">This example evaluates to TRUE if the value in the **ListPrice** column is less than 500.</span></span>  
  
```  
ListPrice < 500  
```  
  
 <span data-ttu-id="4d71e-143">Cet exemple utilise la variable **LPrice**.</span><span class="sxs-lookup"><span data-stu-id="4d71e-143">This example uses the variable **LPrice**.</span></span> <span data-ttu-id="4d71e-144">Il renvoie la valeur TRUE si la valeur de la variable **LPrice** est inférieure à 500.</span><span class="sxs-lookup"><span data-stu-id="4d71e-144">It evaluates to TRUE if the value of **LPrice** is less than 500.</span></span> <span data-ttu-id="4d71e-145">Le type de données de la variable doit être numérique pour permettre l'analyse de l'expression.</span><span class="sxs-lookup"><span data-stu-id="4d71e-145">The data type of the variable must be numeric in order for the expression to parse.</span></span>  
  
```  
@LPrice < 500  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d71e-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4d71e-146">See Also</span></span>  
 <span data-ttu-id="4d71e-147">[&#62; &#40;Supérieur à&#41; &#40;expression SSIS&#41;](greater-than-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d71e-147">[&#62; &#40;Greater Than&#41; &#40;SSIS Expression&#41;](greater-than-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d71e-148">[&#62;= &#40;Supérieur ou égal à&#41; &#40;expression SSIS&#41;](greater-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d71e-148">[&#62;= &#40;Greater Than or Equal To&#41; &#40;SSIS Expression&#41;](greater-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d71e-149">[&#60;= &#40;Inférieur ou égal à&#41; &#40;expression SSIS&#41;](less-than-or-equal-to-ssis-expression.md) </span><span class="sxs-lookup"><span data-stu-id="4d71e-149">[&#60;= &#40;Less Than or Equal To&#41; &#40;SSIS Expression&#41;](less-than-or-equal-to-ssis-expression.md) </span></span>  
 <span data-ttu-id="4d71e-150">[Priorités et associativité des opérateurs](operator-precedence-and-associativity.md) </span><span class="sxs-lookup"><span data-stu-id="4d71e-150">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) </span></span>  
 [<span data-ttu-id="4d71e-151">Opérateurs &#40;expression SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4d71e-151">Operators &#40;SSIS Expression&#41;</span></span>](operators-ssis-expression.md)  
  
  
