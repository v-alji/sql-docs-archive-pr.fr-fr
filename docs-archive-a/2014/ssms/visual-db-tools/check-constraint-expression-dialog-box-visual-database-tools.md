---
title: Expression de contrainte de validation, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.checkconstraintexpression
ms.assetid: beb6ce43-3913-4d66-8826-8e885335b790
author: stevestein
ms.author: sstein
ms.openlocfilehash: 38268d4e49a9c674c100bc22c0782e3e61477967
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599743"
---
# <a name="check-constraint-expression-dialog-box-visual-database-tools"></a><span data-ttu-id="a20f1-102">Boîte de dialogue Expression de contrainte de validation (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="a20f1-102">Check Constraint Expression Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="a20f1-103">Lorsque vous rattachez une contrainte de validation à une table ou une colonne, vous devez inclure une expression SQL.</span><span class="sxs-lookup"><span data-stu-id="a20f1-103">When you attach a check constraint to a table or column, you must include an SQL expression.</span></span> <span data-ttu-id="a20f1-104">Entrez l'expression de contrainte de validation dans la zone fournie à cet effet.</span><span class="sxs-lookup"><span data-stu-id="a20f1-104">Type the check constraint expression in the box provided.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="a20f1-105">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="a20f1-105">UI element list</span></span>  
 <span data-ttu-id="a20f1-106">Expression</span><span class="sxs-lookup"><span data-stu-id="a20f1-106">Expression</span></span>  
 <span data-ttu-id="a20f1-107">Entrez l'expression</span><span class="sxs-lookup"><span data-stu-id="a20f1-107">Enter the expression</span></span>  
  
 <span data-ttu-id="a20f1-108">Vous pouvez créer une expression de contrainte simple pour valider les données en fonction d'une condition simple ou créer une expression complexe, à l'aide d'opérateurs booléens, pour valider les données en fonction de plusieurs conditions.</span><span class="sxs-lookup"><span data-stu-id="a20f1-108">You can create a simple constraint expression to check data for a simple condition; or you can create a complex expression, using Boolean operators, to check data for several conditions.</span></span> <span data-ttu-id="a20f1-109">Supposons, par exemple, que la table authors comporte une colonne zip nécessitant une chaîne de caractères de 5 chiffres.</span><span class="sxs-lookup"><span data-stu-id="a20f1-109">For example, suppose the authors table has a zip column where a 5-digit character string is required.</span></span> <span data-ttu-id="a20f1-110">L'expression de contrainte suivante permet de s'assurer que seuls les nombres de 5 chiffres sont acceptés :</span><span class="sxs-lookup"><span data-stu-id="a20f1-110">This sample constraint expression guarantees that only 5-digit numbers are allowed:</span></span>  
  
```  
zip LIKE '[0-9][0-9][0-9][0-9][0-9]'  
```  
  
 <span data-ttu-id="a20f1-111">Ou imaginons que la table sales comporte une colonne qty dans laquelle il est nécessaire d'entrer des valeurs supérieures à 0.</span><span class="sxs-lookup"><span data-stu-id="a20f1-111">Or suppose the sales table has a column called qty which requires a value greater than 0.</span></span> <span data-ttu-id="a20f1-112">L'expression de contrainte suivante assure que cette colonne contiendra exclusivement des valeurs positives :</span><span class="sxs-lookup"><span data-stu-id="a20f1-112">This sample constraint guarantees that only positive values are allowed:</span></span>  
  
```  
qty > 0  
```  
  
 <span data-ttu-id="a20f1-113">Ou supposons que la table orders indique le type de cartes de crédit qu'il est nécessaire de posséder pour passer une commande.</span><span class="sxs-lookup"><span data-stu-id="a20f1-113">Or suppose the orders table limits the type of credit cards accepted for all credit card orders.</span></span> <span data-ttu-id="a20f1-114">La contrainte suivante garantit que seules les cartes de crédit Visa, MasterCard ou American Express sont acceptées :</span><span class="sxs-lookup"><span data-stu-id="a20f1-114">This sample constraint guarantees that if the order is placed on a credit card, then only Visa, MasterCard, or American Express is accepted:</span></span>  
  
```  
NOT (payment_method = 'credit card') OR  
   (card_type IN ('VISA', 'MASTERCARD', 'AMERICAN EXPRESS'))  
```  
  
## <a name="to-define-a-constraint-expression"></a><span data-ttu-id="a20f1-115">Pour définir une expression de contrainte</span><span class="sxs-lookup"><span data-stu-id="a20f1-115">To define a constraint expression</span></span>  
 <span data-ttu-id="a20f1-116">Sous l'onglet Vérifier les contraintes des pages de propriétés, tapez l'expression dans la zone Expression de contrainte en respectant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="a20f1-116">In the Check Constraints tab of the property pages, type an expression in the Constraint expression box using the following syntax:</span></span>  
  
 `{constant | column_name | function | (subquery)}`  
  
 `[{operator | AND | OR | NOT}`  
  
 `{constant | column_name | function | (subquery)}...]`  
  
 <span data-ttu-id="a20f1-117">La syntaxe SQL est constituée des paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="a20f1-117">The SQL syntax is made up of the following parameters:</span></span>  
  
|<span data-ttu-id="a20f1-118">Paramètre</span><span class="sxs-lookup"><span data-stu-id="a20f1-118">Parameter</span></span>|<span data-ttu-id="a20f1-119">Description</span><span class="sxs-lookup"><span data-stu-id="a20f1-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a20f1-120">constant</span><span class="sxs-lookup"><span data-stu-id="a20f1-120">constant</span></span>|<span data-ttu-id="a20f1-121">Valeur littérale (données numériques ou caractères).</span><span class="sxs-lookup"><span data-stu-id="a20f1-121">A literal value, such as numeric or character data.</span></span> <span data-ttu-id="a20f1-122">N'oubliez pas d'insérer les chaînes de caractères entre guillemets simples (').</span><span class="sxs-lookup"><span data-stu-id="a20f1-122">Character data must be enclosed within single quotation marks (').</span></span>|  
|<span data-ttu-id="a20f1-123">column_name</span><span class="sxs-lookup"><span data-stu-id="a20f1-123">column_name</span></span>|<span data-ttu-id="a20f1-124">Spécifie une colonne.</span><span class="sxs-lookup"><span data-stu-id="a20f1-124">Specifies a column.</span></span>|  
|<span data-ttu-id="a20f1-125">function</span><span class="sxs-lookup"><span data-stu-id="a20f1-125">function</span></span>|<span data-ttu-id="a20f1-126">Fonction intégrée.</span><span class="sxs-lookup"><span data-stu-id="a20f1-126">A built-in function.</span></span>|  
|<span data-ttu-id="a20f1-127">operator</span><span class="sxs-lookup"><span data-stu-id="a20f1-127">operator</span></span>|<span data-ttu-id="a20f1-128">Opérateur arithmétique, de comparaison, de chaîne ou au niveau du bit.</span><span class="sxs-lookup"><span data-stu-id="a20f1-128">Arithmetic, bitwise, comparison, or string operators.</span></span>|  
|<span data-ttu-id="a20f1-129">AND</span><span class="sxs-lookup"><span data-stu-id="a20f1-129">AND</span></span>|<span data-ttu-id="a20f1-130">Utilisez AND dans les expressions booléennes pour relier deux expressions.</span><span class="sxs-lookup"><span data-stu-id="a20f1-130">Use in Boolean expressions to connect two expressions.</span></span> <span data-ttu-id="a20f1-131">Les résultats sont retournés lorsque les deux expressions sont vraies.</span><span class="sxs-lookup"><span data-stu-id="a20f1-131">Results are returned when both expressions are true.</span></span><br /><br /> <span data-ttu-id="a20f1-132">Lorsque AND et OR sont tous deux utilisés dans une instruction, AND est traité en premier.</span><span class="sxs-lookup"><span data-stu-id="a20f1-132">When AND and OR are both used in a statement, AND is processed first.</span></span> <span data-ttu-id="a20f1-133">Vous pouvez changer l'ordre d'exécution en utilisant des parenthèses.</span><span class="sxs-lookup"><span data-stu-id="a20f1-133">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="a20f1-134">OR</span><span class="sxs-lookup"><span data-stu-id="a20f1-134">OR</span></span>|<span data-ttu-id="a20f1-135">Utilisez OR dans les expressions booléennes pour relier plusieurs expressions.</span><span class="sxs-lookup"><span data-stu-id="a20f1-135">Use in Boolean expressions to connect two or more conditions.</span></span> <span data-ttu-id="a20f1-136">Les résultats sont retournés lorsque l'une ou l'autre des expressions est vraie.</span><span class="sxs-lookup"><span data-stu-id="a20f1-136">Results are returned when either condition is true.</span></span><br /><br /> <span data-ttu-id="a20f1-137">Lorsque AND et OR sont tous deux utilisés dans une instruction, OR est évalué après AND.</span><span class="sxs-lookup"><span data-stu-id="a20f1-137">When AND and OR are both used in a statement, OR is evaluated after AND.</span></span> <span data-ttu-id="a20f1-138">Vous pouvez changer l'ordre d'exécution en utilisant des parenthèses.</span><span class="sxs-lookup"><span data-stu-id="a20f1-138">You can change the order of execution by using parentheses.</span></span>|  
|<span data-ttu-id="a20f1-139">NOT</span><span class="sxs-lookup"><span data-stu-id="a20f1-139">NOT</span></span>|<span data-ttu-id="a20f1-140">Inverse une expression booléenne (qui peut inclure des mots clés, tels que LIKE, NULL, BETWEEN, IN et EXISTS).</span><span class="sxs-lookup"><span data-stu-id="a20f1-140">Negates any Boolean expression (which can include keywords, such as LIKE, NULL, BETWEEN, IN, and EXISTS).</span></span><br /><br /> <span data-ttu-id="a20f1-141">Lorsqu'une instruction contient plusieurs opérateurs logiques, NOT est traité en premier.</span><span class="sxs-lookup"><span data-stu-id="a20f1-141">When more than one logical operator is used in a statement, NOT is processed first.</span></span> <span data-ttu-id="a20f1-142">Vous pouvez changer l'ordre d'exécution en utilisant des parenthèses.</span><span class="sxs-lookup"><span data-stu-id="a20f1-142">You can change the order of execution by using parentheses.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a20f1-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a20f1-143">See Also</span></span>  
 <span data-ttu-id="a20f1-144">[Contraintes uniques et contraintes de validation](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span><span class="sxs-lookup"><span data-stu-id="a20f1-144">[Unique Constraints and Check Constraints](../../relational-databases/tables/unique-constraints-and-check-constraints.md) </span></span>  
 [<span data-ttu-id="a20f1-145">Créer des contraintes uniques</span><span class="sxs-lookup"><span data-stu-id="a20f1-145">Create Unique Constraints</span></span>](../../relational-databases/tables/create-unique-constraints.md)  
  
  
