---
title: Cast (expression SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- CAST function
- cast operator
- converting data types [Integration Services]
- data types [Integration Services], expressions
- data types [Integration Services], converting
ms.assetid: d4e915cc-1c7b-4b2e-93b0-13a8b0cb9242
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 65d60eca4340b65b8a82855c3f2b29a6cda56e15
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705352"
---
# <a name="cast-ssis-expression"></a><span data-ttu-id="26a62-102">Cast (expression SSIS)</span><span class="sxs-lookup"><span data-stu-id="26a62-102">Cast (SSIS Expression)</span></span>
  <span data-ttu-id="26a62-103">Convertit explicitement une expression d'un type de données vers un autre.</span><span class="sxs-lookup"><span data-stu-id="26a62-103">Explicitly converts an expression from one data type to a different data type.</span></span> <span data-ttu-id="26a62-104">L'opérateur de conversion peut également fonctionner comme opérateur de troncation.</span><span class="sxs-lookup"><span data-stu-id="26a62-104">The cast operator can also function as a truncation operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="26a62-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="26a62-105">Syntax</span></span>

```

(type_spec) expression

```

## <a name="arguments"></a><span data-ttu-id="26a62-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="26a62-106">Arguments</span></span>
 <span data-ttu-id="26a62-107">*type_spec* Est un [!INCLUDE[ssIS](../../includes/ssis-md.md)] type de données valide.</span><span class="sxs-lookup"><span data-stu-id="26a62-107">*type_spec* Is a valid [!INCLUDE[ssIS](../../includes/ssis-md.md)] data type.</span></span>

 <span data-ttu-id="26a62-108">*expression* Est une expression valide.</span><span class="sxs-lookup"><span data-stu-id="26a62-108">*expression* Is a valid expression.</span></span>

## <a name="result-types"></a><span data-ttu-id="26a62-109">Types des résultats</span><span class="sxs-lookup"><span data-stu-id="26a62-109">Result Types</span></span>
 <span data-ttu-id="26a62-110">Type de données de *type_spec*.</span><span class="sxs-lookup"><span data-stu-id="26a62-110">The data type of *type_spec*.</span></span> <span data-ttu-id="26a62-111">Pour plus d’informations, consultez [Types de données Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="26a62-111">For more information, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="26a62-112">Notes</span><span class="sxs-lookup"><span data-stu-id="26a62-112">Remarks</span></span>
 <span data-ttu-id="26a62-113">Le schéma suivant montre les opérations de conversion valides.</span><span class="sxs-lookup"><span data-stu-id="26a62-113">The following diagram shows legal cast operations.</span></span>

 <span data-ttu-id="26a62-114">![Conversions légales et illégales entre types de données](../media/data-conversion.gif "Conversions légales et illégales entre types de données")</span><span class="sxs-lookup"><span data-stu-id="26a62-114">![Legal and not legal casts between data types](../media/data-conversion.gif "Legal and not legal casts between data types")</span></span>

 <span data-ttu-id="26a62-115">La conversion vers certains types de données nécessite des paramètres.</span><span class="sxs-lookup"><span data-stu-id="26a62-115">Casting to some data types requires parameters.</span></span> <span data-ttu-id="26a62-116">Le tableau suivant décrit ces types de données et leurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="26a62-116">The following table lists these data types and their parameters.</span></span>

|<span data-ttu-id="26a62-117">Type de données</span><span class="sxs-lookup"><span data-stu-id="26a62-117">Data type</span></span>|<span data-ttu-id="26a62-118">Paramètre</span><span class="sxs-lookup"><span data-stu-id="26a62-118">Parameter</span></span>|<span data-ttu-id="26a62-119">Exemple</span><span class="sxs-lookup"><span data-stu-id="26a62-119">Example</span></span>|
|---------------|---------------|-------------|
|<span data-ttu-id="26a62-120">DT_STR</span><span class="sxs-lookup"><span data-stu-id="26a62-120">DT_STR</span></span>|<span data-ttu-id="26a62-121">*charcount*</span><span class="sxs-lookup"><span data-stu-id="26a62-121">*charcount*</span></span><br /><br /> <span data-ttu-id="26a62-122">*courante*</span><span class="sxs-lookup"><span data-stu-id="26a62-122">*codepage*</span></span>|<span data-ttu-id="26a62-123">L'expression (DT_STR,30,1252) convertit 30 octets, ou 30 caractères codés sur un octet, vers le type de données DT_STR à l'aide de la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="26a62-123">(DT_STR,30,1252) casts 30 bytes, or 30 single characters, to the DT_STR data type using the 1252 code page.</span></span>|
|<span data-ttu-id="26a62-124">DT_WSTR</span><span class="sxs-lookup"><span data-stu-id="26a62-124">DT_WSTR</span></span>|<span data-ttu-id="26a62-125">*CharCount*</span><span class="sxs-lookup"><span data-stu-id="26a62-125">*Charcount*</span></span>|<span data-ttu-id="26a62-126">L'expression (DT_WSTR,20) convertit 20 paires d'octets, ou 20 caractères Unicode, vers le type de données DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="26a62-126">(DT_WSTR,20) casts 20 byte pairs, or 20 Unicode characters, to the DT_WSTR data type.</span></span>|
|<span data-ttu-id="26a62-127">DT_BYTES</span><span class="sxs-lookup"><span data-stu-id="26a62-127">DT_BYTES</span></span>|<span data-ttu-id="26a62-128">*ByteCount*</span><span class="sxs-lookup"><span data-stu-id="26a62-128">*Bytecount*</span></span>|<span data-ttu-id="26a62-129">L'expression (DT_BYTES,50) convertit 50 octets vers le type de données DT_BYTES.</span><span class="sxs-lookup"><span data-stu-id="26a62-129">(DT_BYTES,50) casts 50 bytes to the DT_BYTES data type.</span></span>|
|<span data-ttu-id="26a62-130">DT_DECIMAL</span><span class="sxs-lookup"><span data-stu-id="26a62-130">DT_DECIMAL</span></span>|<span data-ttu-id="26a62-131">*Mise à l’échelle*</span><span class="sxs-lookup"><span data-stu-id="26a62-131">*Scale*</span></span>|<span data-ttu-id="26a62-132">L'expression (DT_DECIMAL,2) convertit une valeur numérique dans le type de données DT_DECIMAL avec une échelle égale à 2.</span><span class="sxs-lookup"><span data-stu-id="26a62-132">(DT_DECIMAL,2) casts a numeric value to the DT_DECIMAL data type using a scale of 2.</span></span>|
|<span data-ttu-id="26a62-133">DT_NUMERIC</span><span class="sxs-lookup"><span data-stu-id="26a62-133">DT_NUMERIC</span></span>|<span data-ttu-id="26a62-134">*Précision*</span><span class="sxs-lookup"><span data-stu-id="26a62-134">*Precision*</span></span><br /><br /> <span data-ttu-id="26a62-135">*Mise à l’échelle*</span><span class="sxs-lookup"><span data-stu-id="26a62-135">*Scale*</span></span>|<span data-ttu-id="26a62-136">L'expression (DT_NUMERIC,10,3) convertit une valeur numérique dans le type de données DT_NUMERIC avec une précision de 10 et une échelle de 3.</span><span class="sxs-lookup"><span data-stu-id="26a62-136">(DT_NUMERIC,10,3) casts a numeric value to the DT_NUMERIC data type using a precision of 10 and a scale of 3.</span></span>|
|<span data-ttu-id="26a62-137">DT_TEXT</span><span class="sxs-lookup"><span data-stu-id="26a62-137">DT_TEXT</span></span>|<span data-ttu-id="26a62-138">*Courante*</span><span class="sxs-lookup"><span data-stu-id="26a62-138">*Codepage*</span></span>|<span data-ttu-id="26a62-139">L'expression (DT_TEXT,1252) convertit une valeur vers le type de données DT_TEXT à l'aide de la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="26a62-139">(DT_TEXT,1252) casts a value to the DT_TEXT data type using the 1252 code page.</span></span>|

 <span data-ttu-id="26a62-140">Lorsque vous convertissez une chaîne vers un type de données DT_DATE ou vice versa, les paramètres régionaux de la transformation sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="26a62-140">When a string is cast to a DT_DATE, or vice versa, the locale of the transformation is used.</span></span> <span data-ttu-id="26a62-141">Toutefois, la date se présente dans le format ISO AAAA-MM-JJJ, que les préférences des paramètres régionaux utilisent ou non le format ISO.</span><span class="sxs-lookup"><span data-stu-id="26a62-141">However, the date is in the ISO format of YYYY-MM-DD, regardless of whether the locale preference uses the ISO format.</span></span>

> [!NOTE]
>  <span data-ttu-id="26a62-142">Pour convertir une chaîne en un type de données date autre que DT_DATE, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="26a62-142">To convert a string to a date data type other than DT_DATE, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

 <span data-ttu-id="26a62-143">Si la page de codes est une page de codes de caractères multi-octets, le nombre d'octets et de caractères peut différer.</span><span class="sxs-lookup"><span data-stu-id="26a62-143">If the code page is a multibyte character code page, the number of bytes and characters may differ.</span></span> <span data-ttu-id="26a62-144">La conversion d’un type de données (transtypage) DT_WSTR en DT_STR avec la même valeur *charcount* peut provoquer la troncation des caractères finaux dans la chaîne convertie.</span><span class="sxs-lookup"><span data-stu-id="26a62-144">Casting from a DT_WSTR to a DT_STR with the same *charcount* value may cause truncation of the final characters in the converted string.</span></span> <span data-ttu-id="26a62-145">Si l’espace de stockage disponible est suffisant dans la colonne de la table de destination, définissez la valeur du paramètre *charcount* de façon à refléter le nombre d’octets nécessaires à la page de codes multioctets.</span><span class="sxs-lookup"><span data-stu-id="26a62-145">If sufficient storage is available in the column of the destination table, set the value of the *charcount* parameter to reflect the number of bytes that the multibyte code page requires.</span></span> <span data-ttu-id="26a62-146">Par exemple, si vous convertissez des données de type caractère en un type de données DT_STR en utilisant la page de codes 936, vous devez définir le paramètre *charcount* sur une valeur jusqu’à deux fois supérieure au nombre de caractères attendus dans les données. Si vous convertissez des données de type caractère en utilisant la page de codes UTF-8, vous devez attribuer au paramètre *charcount* une valeur jusqu’à quatre fois supérieure.</span><span class="sxs-lookup"><span data-stu-id="26a62-146">For example, if you cast character data to a DT_STR data type using the 936 code page, you should set *charcount* to a value up to two times greater than the number of characters that you expect the data to contain; if you cast character data using the UTF-8 code page, you should set *charcount* to a value up to four times greater.</span></span>

 <span data-ttu-id="26a62-147">Pour plus d’informations sur la structure des types de données date, consultez [Types de données d’Integration Services](../data-flow/integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="26a62-147">For more information about the structure of date data types, see [Integration Services Data Types](../data-flow/integration-services-data-types.md).</span></span>

## <a name="ssis-expression-examples"></a><span data-ttu-id="26a62-148">Exemples d'expressions SSIS</span><span class="sxs-lookup"><span data-stu-id="26a62-148">SSIS Expression Examples</span></span>
 <span data-ttu-id="26a62-149">L'exemple suivant convertit une valeur numérique en un entier.</span><span class="sxs-lookup"><span data-stu-id="26a62-149">This example casts a numeric value to an integer.</span></span>

```
(DT_I4) 3.57
```

 <span data-ttu-id="26a62-150">L'exemple suivant convertit un entier en une chaîne de caractères à l'aide de la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="26a62-150">This example casts an integer to a character string using the 1252 code page.</span></span>

```
(DT_STR,1,1252)5
```

 <span data-ttu-id="26a62-151">L'exemple suivant convertit une chaîne de trois caractères en caractères codés sur deux octets.</span><span class="sxs-lookup"><span data-stu-id="26a62-151">This example casts a three-character string to double-byte characters.</span></span>

```
(DT_WSTR,3)"Cat"
```

 <span data-ttu-id="26a62-152">L'exemple suivant convertit un entier en un nombre décimal avec une échelle de deux.</span><span class="sxs-lookup"><span data-stu-id="26a62-152">This example casts an integer to a decimal with a scale of two.</span></span>

```
(DT_DECIMAl,2)500
```

 <span data-ttu-id="26a62-153">L'exemple suivant convertit un entier en une valeur numérique avec une précision de sept et une échelle de trois.</span><span class="sxs-lookup"><span data-stu-id="26a62-153">This example casts an integer to a numeric with a precision of seven and scale of three.</span></span>

```
(DT_NUMERIC,7,3)4000
```

 <span data-ttu-id="26a62-154">L’exemple suivant convertit les valeurs de la colonne **FirstName** , définie avec un type de données **nvarchar** et une longueur de 50, en une chaîne de caractères en utilisant la page de codes 1252.</span><span class="sxs-lookup"><span data-stu-id="26a62-154">This example casts values in the **FirstName** column, defined with an **nvarchar** data type and a length of 50, to a character string using the 1252 code page.</span></span>

```
(DT_STR,50,1252)FirstName
```

 <span data-ttu-id="26a62-155">L’exemple suivant convertit les valeurs de la colonne **DateFirstPurchase** de type DT_DBDATE, en une chaîne de caractères Unicode avec une longueur de 20.</span><span class="sxs-lookup"><span data-stu-id="26a62-155">This example casts values in the **DateFirstPurchase** column of type DT_DBDATE, to a Unicode character string with a length of 20.</span></span>

```
(DT_WSTR,20)DateFirstPurchase
```

 <span data-ttu-id="26a62-156">L'exemple suivant convertit le littéral de chaîne "True" en une valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="26a62-156">This example casts the string literal "True" to a Boolean.</span></span>

```
(DT_BOOL)"True"
```

 <span data-ttu-id="26a62-157">Cet exemple convertit un littéral de chaîne en DT_DBDATE.</span><span class="sxs-lookup"><span data-stu-id="26a62-157">This example casts a string literal to DT_DBDATE.</span></span>

```
(DT_DBDATE) "1999-10-11"
```

 <span data-ttu-id="26a62-158">Cet exemple convertit un littéral de chaîne en type de données DT_DBTIME2 qui utilise 5 chiffres pour les fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="26a62-158">This example casts a string literal to the DT_DBTIME2 data type that uses 5 digits for fractional seconds.</span></span> <span data-ttu-id="26a62-159">(Le type de données DT_DBTIME2 peut avoir entre 0 et 7 chiffres spécifiés pour les fractions de seconde.)</span><span class="sxs-lookup"><span data-stu-id="26a62-159">(The DT_DBTIME2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIME2, 5) "16:34:52.12345"
```

 <span data-ttu-id="26a62-160">Cet exemple convertit un littéral de chaîne en type de données DT_DBTIMESTAMP2 qui utilise 4 chiffres pour les fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="26a62-160">This example casts a string literal to the DT_DBTIMESTAMP2 data type that uses 4 digits for fractional seconds.</span></span> <span data-ttu-id="26a62-161">(Le type de données DT_DBTIMESTAMP2 peut avoir entre 0 et 7 chiffres spécifiés pour les fractions de seconde.)</span><span class="sxs-lookup"><span data-stu-id="26a62-161">(The DT_DBTIMESTAMP2 data type can have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMP2, 4) "1999-10-11 16:34:52.1234"
```

 <span data-ttu-id="26a62-162">Cet exemple convertit un littéral de chaîne en type de données DT_DBTIMESTAMPOFFSET qui utilise 7 chiffres pour les fractions de seconde.</span><span class="sxs-lookup"><span data-stu-id="26a62-162">This example casts a string literal to the DT_DBTIMESTAMPOFFSET data type that uses 7 digits for fractional seconds.</span></span> <span data-ttu-id="26a62-163">(Le type de données DT_DBTIMESTAMPOFFSET peut avoir entre 0 et 7 chiffres spécifiés pour les fractions de seconde.)</span><span class="sxs-lookup"><span data-stu-id="26a62-163">(The DT_DBTIMESTAMPOFFSET data typecan have between 0 and 7 digits specified for fractional seconds.)</span></span>

```
(DT_DBTIMESTAMPOFFSET, 7) "1999-10-11 16:34:52.1234567 + 5:35"
```

## <a name="see-also"></a><span data-ttu-id="26a62-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26a62-164">See Also</span></span>
 <span data-ttu-id="26a62-165">Opérateurs de [priorité et d’associativité des](operator-precedence-and-associativity.md) opérateurs [&#40;&#41;d’expression SSIS](operators-ssis-expression.md) [Integration Services des expressions de&#41; SSIS &#40;](integration-services-ssis-expressions.md) [Integration Services des types de données dans les expressions](integration-services-data-types-in-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="26a62-165">[Operator Precedence and Associativity](operator-precedence-and-associativity.md) [Operators &#40;SSIS Expression&#41;](operators-ssis-expression.md) [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) [Integration Services Data Types in Expressions](integration-services-data-types-in-expressions.md)</span></span>


