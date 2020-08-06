---
title: Opérateurs dans les expressions (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d22dc8b6-4353-40e7-91a1-65e8dae6325d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fa8042df39e535425a05414c1e39ee6a12ff2f39
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605182"
---
# <a name="operators-in-expressions-report-builder-and-ssrs"></a><span data-ttu-id="6cbaf-102">Opérateurs dans les expressions (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="6cbaf-102">Operators in Expressions (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6cbaf-103">Un opérateur est un symbole qui représente des actions exécutées sur un ou plusieurs termes d'une expression.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-103">An operator is a symbol that represents actions applied to one or more terms in an expression.</span></span> <span data-ttu-id="6cbaf-104">Les catégories d'opérateurs suivantes sont prises en charge dans une expression : arithmétique, de comparaison, de concaténation, logique ou au niveau du bit, et de décalage de bits.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-104">The following categories of operators are supported in an expression: arithmetic, comparison, concatenation, logical or bitwise, and bit shift.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="arithmetic"></a><span data-ttu-id="6cbaf-105">Arithmétique</span><span class="sxs-lookup"><span data-stu-id="6cbaf-105">Arithmetic</span></span>  
 <span data-ttu-id="6cbaf-106">Les opérateurs arithmétiques effectuent des opérations mathématiques sur deux termes numériques d'une expression.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-106">Arithmetic operators perform mathematical operations on two numeric terms in an expression.</span></span>  
  
|<span data-ttu-id="6cbaf-107">Opérateur</span><span class="sxs-lookup"><span data-stu-id="6cbaf-107">Operator</span></span>|<span data-ttu-id="6cbaf-108">Description</span><span class="sxs-lookup"><span data-stu-id="6cbaf-108">Description</span></span>|  
|--------------|-----------------|  
|^|<span data-ttu-id="6cbaf-109">Élève un nombre à la puissance d'un autre nombre.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-109">Raises a number to the power of another number.</span></span>|  
|*|<span data-ttu-id="6cbaf-110">Multiplie deux nombres.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-110">Multiplies two numbers.</span></span>|  
|/|<span data-ttu-id="6cbaf-111">Effectue la division entre deux nombres et retourne un résultat à virgule flottante.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-111">Divides two numbers and returns a floating-point result.</span></span>|  
|<span data-ttu-id="6cbaf-112">\|Effectue la division entre deux nombres et retourne un résultat sous forme d'entier.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-112">\|Divides two numbers and returns an integer result.</span></span>|  
|<span data-ttu-id="6cbaf-113">Mod</span><span class="sxs-lookup"><span data-stu-id="6cbaf-113">Mod</span></span>|<span data-ttu-id="6cbaf-114">Retourne le reste entier d'une division.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-114">Returns the integer remainder of a division.</span></span> <span data-ttu-id="6cbaf-115">Par exemple, 7 Mod 5 = 2 parce que le reste de 7 divisé par 5 est 2.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-115">For example, 7 Mod 5 = 2 because the remainder of 7 divided by 5 is 2.</span></span>|  
|+|<span data-ttu-id="6cbaf-116">Additionne deux nombres.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-116">Adds two numbers together.</span></span>|  
|-|<span data-ttu-id="6cbaf-117">Retourne la différence entre deux nombres ou indique la valeur négative d'un terme numérique.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-117">Returns the difference between two numbers or indicates the negative value of a numeric term.</span></span>|  
  
### <a name="comparison"></a><span data-ttu-id="6cbaf-118">Comparaison</span><span class="sxs-lookup"><span data-stu-id="6cbaf-118">Comparison</span></span>  
 <span data-ttu-id="6cbaf-119">Les opérateurs de comparaison testent si deux expressions sont identiques.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-119">Comparison operators test whether two expressions are the same.</span></span>  
  
|<span data-ttu-id="6cbaf-120">Opérateur</span><span class="sxs-lookup"><span data-stu-id="6cbaf-120">Operator</span></span>|<span data-ttu-id="6cbaf-121">Description</span><span class="sxs-lookup"><span data-stu-id="6cbaf-121">Description</span></span>|  
|--------------|-----------------|  
|<|<span data-ttu-id="6cbaf-122">Inférieur à.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-122">Less than.</span></span>|  
|\<=|<span data-ttu-id="6cbaf-123">Inférieur ou égal à.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-123">Less than or equal to.</span></span>|  
|>|<span data-ttu-id="6cbaf-124">Supérieur à.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-124">Greater than.</span></span>|  
|>=|<span data-ttu-id="6cbaf-125">Supérieur ou égal à.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-125">Greater than or equal to.</span></span>|  
|=|<span data-ttu-id="6cbaf-126">Égal à.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-126">Equal to.</span></span>|  
|<>|<span data-ttu-id="6cbaf-127">Non égal à.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-127">Not equal to.</span></span>|  
|<span data-ttu-id="6cbaf-128">Correspond à</span><span class="sxs-lookup"><span data-stu-id="6cbaf-128">Like</span></span>|<span data-ttu-id="6cbaf-129">Détermine si une chaîne de caractères donnée correspond à un modèle spécifié.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-129">Determines whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="6cbaf-130">Une chaîne peut comprendre des caractères normaux ainsi que des caractères génériques.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-130">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="6cbaf-131">Au cours de l'analyse, les caractères normaux doivent correspondre exactement aux caractères spécifiés dans la chaîne de caractères.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-131">During pattern matching, regular characters must exactly match the characters specified in the character string.</span></span> <span data-ttu-id="6cbaf-132">Toutefois, les caractères génériques peuvent être associés à des portions aléatoires de la chaîne de caractères.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-132">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="6cbaf-133">L'utilisation de caractères génériques rend l'opérateur LIKE plus flexible que lorsque les opérateurs de comparaison des chaînes = et != sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-133">Using wildcard characters makes the LIKE operator more flexible than using the = and != string comparison operators.</span></span><br /><br /> <span data-ttu-id="6cbaf-134">La liste suivante répertorie les caractères qui peuvent être utilisés comme caractères génériques :</span><span class="sxs-lookup"><span data-stu-id="6cbaf-134">The following lists characters that can be used as wildcards:</span></span><br /><br /> <span data-ttu-id="6cbaf-135">**%**: Toute chaîne de zéro caractère ou plus.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-135">**%**: Any string of zero or more characters.</span></span><br /><br /> <span data-ttu-id="6cbaf-136">**_**: Tout caractère unique.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-136">**_**: Any single character.</span></span><br /><br /> <span data-ttu-id="6cbaf-137">**[]**: Tout caractère unique dans la plage spécifiée (par exemple, [a-f]) ou défini (par exemple, [aeiou]).</span><span class="sxs-lookup"><span data-stu-id="6cbaf-137">**[ ]**: Any single character within the specified range (for example, [a-f]) or set (for example, [aeiou]).</span></span><br /><br /> <span data-ttu-id="6cbaf-138">**[^]**: Tout caractère unique qui ne figure pas dans la plage spécifiée (par exemple, [^ a-f]) ou défini (par exemple, [^ aeiou]).</span><span class="sxs-lookup"><span data-stu-id="6cbaf-138">**[^]**: Any single character not within the specified range (for example, [^a-f]) or set (for example, [^aeiou]).</span></span>|  
|<span data-ttu-id="6cbaf-139">Is</span><span class="sxs-lookup"><span data-stu-id="6cbaf-139">Is</span></span>|<span data-ttu-id="6cbaf-140">Compare deux références d'objet.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-140">Compares two object references.</span></span>|  
  
### <a name="string-concatenation"></a><span data-ttu-id="6cbaf-141">Concaténation de chaînes</span><span class="sxs-lookup"><span data-stu-id="6cbaf-141">String Concatenation</span></span>  
 <span data-ttu-id="6cbaf-142">La concaténation de chaînes ajoute la seconde chaîne à la fin de la première dans une expression.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-142">String concatenation appends the second string to the first string in an expression.</span></span> <span data-ttu-id="6cbaf-143">Pour d'autres opérations sur les chaînes, utilisez les fonctions intégrées.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-143">For other string operations, use built-in functions.</span></span>  
  
|<span data-ttu-id="6cbaf-144">Opérateur</span><span class="sxs-lookup"><span data-stu-id="6cbaf-144">Operator</span></span>|<span data-ttu-id="6cbaf-145">Description</span><span class="sxs-lookup"><span data-stu-id="6cbaf-145">Description</span></span>|  
|--------------|-----------------|  
|&|<span data-ttu-id="6cbaf-146">Concatène deux chaînes.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-146">Concatenates two strings</span></span>|  
|+|<span data-ttu-id="6cbaf-147">Concatène deux chaînes.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-147">Concatenates two strings</span></span>|  
  
### <a name="logical-and-bitwise"></a><span data-ttu-id="6cbaf-148">Logique et au niveau du bit</span><span class="sxs-lookup"><span data-stu-id="6cbaf-148">Logical and Bitwise</span></span>  
 <span data-ttu-id="6cbaf-149">Les opérateurs logique et au niveau du bit effectuent des manipulations logiques entre deux termes entiers dans une expression.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-149">Logical and bitwise operators perform logical manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="6cbaf-150">Opérateur</span><span class="sxs-lookup"><span data-stu-id="6cbaf-150">Operator</span></span>|<span data-ttu-id="6cbaf-151">Description</span><span class="sxs-lookup"><span data-stu-id="6cbaf-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6cbaf-152">and</span><span class="sxs-lookup"><span data-stu-id="6cbaf-152">And</span></span>|<span data-ttu-id="6cbaf-153">Effectue une conjonction logique sur deux expressions booléennes ou une conjonction au niveau du bit sur deux expressions numériques.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-153">Performs a logical conjunction on two Boolean expressions, or bitwise conjunction on two numeric expressions.</span></span>|  
|<span data-ttu-id="6cbaf-154">Not</span><span class="sxs-lookup"><span data-stu-id="6cbaf-154">Not</span></span>|<span data-ttu-id="6cbaf-155">Effectue une négation logique sur une expression booléenne ou une négation au niveau du bit sur une expression numérique.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-155">Performs logical negation on a Boolean expression, or bitwise negation on a numeric expression.</span></span>|  
|<span data-ttu-id="6cbaf-156">ou</span><span class="sxs-lookup"><span data-stu-id="6cbaf-156">Or</span></span>|<span data-ttu-id="6cbaf-157">Effectue une disjonction logique sur deux expressions booléennes ou une disjonction au niveau du bit sur deux valeurs numériques.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-157">Performs a logical disjunction on two Boolean expressions, or bitwise disjunction on two numeric values.</span></span>|  
|<span data-ttu-id="6cbaf-158">Xor</span><span class="sxs-lookup"><span data-stu-id="6cbaf-158">Xor</span></span>|<span data-ttu-id="6cbaf-159">Effectue une exclusion logique sur deux expressions booléennes ou une exclusion au niveau du bit sur deux expressions numériques.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-159">Performs a logical exclusion operation on two Boolean expressions, or a bitwise exclusion on two numeric expressions.</span></span>|  
|<span data-ttu-id="6cbaf-160">AndAlso</span><span class="sxs-lookup"><span data-stu-id="6cbaf-160">AndAlso</span></span>|<span data-ttu-id="6cbaf-161">Effectue une conjonction logique sur deux expressions.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-161">Performs logical conjunction on two expressions.</span></span>|  
|<span data-ttu-id="6cbaf-162">OrElse</span><span class="sxs-lookup"><span data-stu-id="6cbaf-162">OrElse</span></span>|<span data-ttu-id="6cbaf-163">Effectue une disjonction logique sur deux expressions.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-163">Performs logical disjunction on two expressions.</span></span>|  
  
### <a name="bit-shift"></a><span data-ttu-id="6cbaf-164">Décalage de bits</span><span class="sxs-lookup"><span data-stu-id="6cbaf-164">Bit Shift</span></span>  
 <span data-ttu-id="6cbaf-165">Les opérateurs de décalage de bits effectuent des manipulations de bits entre deux termes entiers dans une expression.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-165">Bitwise operators perform bit manipulations between two integer terms in an expression.</span></span>  
  
|<span data-ttu-id="6cbaf-166">Opérateur</span><span class="sxs-lookup"><span data-stu-id="6cbaf-166">Operator</span></span>|<span data-ttu-id="6cbaf-167">Description</span><span class="sxs-lookup"><span data-stu-id="6cbaf-167">Description</span></span>|  
|--------------|-----------------|  
|<\<|<span data-ttu-id="6cbaf-168">Effectue un décalage arithmétique vers la gauche sur un modèle binaire.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-168">Performs an arithmetic left-shift on a bit pattern.</span></span>|  
|>>|<span data-ttu-id="6cbaf-169">Effectue un décalage arithmétique vers la droite sur un modèle binaire.</span><span class="sxs-lookup"><span data-stu-id="6cbaf-169">Performs an arithmetic right-shift on a bit pattern.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6cbaf-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cbaf-170">See Also</span></span>  
 <span data-ttu-id="6cbaf-171">[Boîte de dialogue Expression](../expression-dialog-box.md) </span><span class="sxs-lookup"><span data-stu-id="6cbaf-171">[Expression Dialog Box](../expression-dialog-box.md) </span></span>  
 <span data-ttu-id="6cbaf-172">[Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6cbaf-172">[Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6cbaf-173">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6cbaf-173">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="6cbaf-174">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6cbaf-174">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](data-types-in-expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6cbaf-175">Boîte de dialogue Expression &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="6cbaf-175">Expression Dialog Box &#40;Report Builder&#41;</span></span>](../expression-dialog-box-report-builder.md)  
  
  
