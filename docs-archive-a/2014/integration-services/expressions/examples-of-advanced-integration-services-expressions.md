---
title: Exemples d’expressions Integration Services avancées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- functions [Integration Services]
- operators [Integration Services]
- expressions [Integration Services], examples
- examples [Integration Services]
ms.assetid: c7794ba3-0de5-466b-ae8a-9ddd27360049
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fb1e8dc6f9bffd22c917414f80f6ba9f257b25b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604666"
---
# <a name="examples-of-advanced-integration-services-expressions"></a><span data-ttu-id="c3cd7-102">Exemples d'expressions Integration Services avancées</span><span class="sxs-lookup"><span data-stu-id="c3cd7-102">Examples of Advanced Integration Services Expressions</span></span>
  <span data-ttu-id="c3cd7-103">Cette section donne des exemples d'expressions avancées qui combinent plusieurs opérateurs et fonctions.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-103">This section provides examples of advanced expressions that combine multiple operators and functions.</span></span> <span data-ttu-id="c3cd7-104">Si une expression est utilisée dans une contrainte de priorité ou dans la transformation de fractionnement conditionnel, elle doit renvoyer une valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-104">If an expression is used in a precedence constraint or the Conditional Split transformation, it must evaluate to a Boolean.</span></span> <span data-ttu-id="c3cd7-105">Toutefois, cette restriction ne s'applique pas aux expressions utilisées dans les expressions de propriété, les variables, la transformation de colonne dérivée ou le conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-105">That restriction, however, does not apply to expressions used in property expressions, variables, the Derived Column transformation, or the For Loop container.</span></span>  
  
 <span data-ttu-id="c3cd7-106">Les exemples suivants utilisent les bases de données **AdventureWorks** et [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3cd7-106">The following examples use the **AdventureWorks** and the [!INCLUDE[ssSampleDBDWobject](../../includes/sssampledbdwobject-md.md)][!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases.</span></span> <span data-ttu-id="c3cd7-107">Chaque exemple indique les tables utilisées.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-107">Each example identifies the tables it uses.</span></span>  
  
## <a name="boolean-expressions"></a><span data-ttu-id="c3cd7-108">Expressions booléennes</span><span class="sxs-lookup"><span data-stu-id="c3cd7-108">Boolean Expressions</span></span>  
  
-   <span data-ttu-id="c3cd7-109">L’exemple suivant utilise la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-109">This example uses the **Product** table.</span></span> <span data-ttu-id="c3cd7-110">L’expression évalue l’entrée du mois dans la colonne **SellStartDate** et retourne TRUE si le mois est Juin ou un mois ultérieur.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-110">The expression evaluates the month entry in the **SellStartDate** column and returns TRUE if the month is June or later.</span></span>  
  
    ```  
    DATEPART("mm",SellStartDate) > 6  
    ```  
  
-   <span data-ttu-id="c3cd7-111">L’exemple suivant utilise la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-111">This example uses the **Product** table.</span></span> <span data-ttu-id="c3cd7-112">L’expression évalue le résultat arrondi de la division de la colonne **ListPrice** par la colonne **StandardCost** et retourne TRUE si le résultat est supérieur à 1,5.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-112">The expression evaluates the rounded result of dividing the **ListPrice** column by the **StandardCost** column, and returns TRUE if the result is greater than 1.5.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) > 1.50  
    ```  
  
-   <span data-ttu-id="c3cd7-113">L’exemple suivant utilise la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-113">This example uses the **Product** table.</span></span> <span data-ttu-id="c3cd7-114">L'expression renvoie TRUE si les trois opérations produisent la valeur TRUE.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-114">The expression returns TRUE if all three operations evaluate to TRUE.</span></span> <span data-ttu-id="c3cd7-115">Si la colonne **Size** et la variable **BikeSize** ont des types de données incompatibles, l’expression requiert une conversion explicite, comme le montre le deuxième exemple.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-115">If the **Size** column and the **BikeSize** variable have incompatible data types, the expression requires an explicit cast as shown the second example.</span></span> <span data-ttu-id="c3cd7-116">La conversion vers le type de données DT_WSTR comprend la longueur de la chaîne.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-116">The cast to DT_WSTR includes the length of the string.</span></span>  
  
    ```  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE && Size != @BikeSize  
    MakeFlag ==  TRUE && FinishedGoodsFlag == TRUE  && Size != (DT_WSTR,10)@BikeSize  
    ```  
  
-   <span data-ttu-id="c3cd7-117">L’exemple suivant utilise la table **CurrencyRate** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-117">This example uses the **CurrencyRate** table.</span></span> <span data-ttu-id="c3cd7-118">L'expression compare des valeurs de tables et de variables.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-118">The expression compares values in tables and variables.</span></span> <span data-ttu-id="c3cd7-119">Elle retourne TRUE si les entrées des colonnes **FromCurrencyCode** ou **ToCurrencyCode** sont égales aux valeurs des variables et si la valeur de **AverageRate** est supérieure à celle de **EndOfDayRate**.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-119">It returns TRUE if entries in the **FromCurrencyCode** or **ToCurrencyCode** columns are equal to variable values and if the value in **AverageRate** is greater that the value in **EndOfDayRate**.</span></span>  
  
    ```  
    (FromCurrencyCode == @FromCur || ToCurrencyCode == @ToCur) && AverageRate > EndOfDayRate  
    ```  
  
-   <span data-ttu-id="c3cd7-120">L’exemple suivant utilise la table **Currency** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-120">This example uses the **Currency** table.</span></span> <span data-ttu-id="c3cd7-121">L’expression retourne TRUE si le premier caractère de la colonne **Name** n’est pas « a » ou « A ».</span><span class="sxs-lookup"><span data-stu-id="c3cd7-121">The expression returns TRUE if the first character in the **Name** column is not a or A.</span></span>  
  
    ```  
    SUBSTRING(UPPER(Name),1,1) != "A"  
    ```  
  
     <span data-ttu-id="c3cd7-122">L'expression suivante donne le même résultat, mais elle est plus efficace car seul un caractère est converti en majuscule.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-122">The following expression provides the same results, but it is more efficient because only one character is converted to uppercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Name,1,1)) != "A"  
    ```  
  
## <a name="non-boolean-expressions"></a><span data-ttu-id="c3cd7-123">Expressions non booléennes</span><span class="sxs-lookup"><span data-stu-id="c3cd7-123">Non-Boolean Expressions</span></span>  
 <span data-ttu-id="c3cd7-124">Les expressions non booléennes sont utilisées dans la transformation de colonne dérivée, les expressions de propriété et le conteneur de boucles For.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-124">Non-Boolean expressions are used in the Derived Column transformation, property expressions, and the For Loop container.</span></span>  
  
-   <span data-ttu-id="c3cd7-125">L’exemple suivant utilise la table **Contact** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-125">This example uses the **Contact** table.</span></span> <span data-ttu-id="c3cd7-126">L’expression supprime les espaces de début et de fin des colonnes **FirstName**, **MiddleName**et **LastName** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-126">The expression removes leading and trailing spaces from the **FirstName**, **MiddleName**, and **LastName** columns.</span></span> <span data-ttu-id="c3cd7-127">Elle extrait la première lettre de la colonne **MiddleName** si elle n’est pas égale à Null, concatène l’initiale de milieu et les valeurs des colonnes **FirstName** et **LastName**et insère les espaces appropriés entre les valeurs.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-127">It extracts the first letter of the **MiddleName** column if it is not null, concatenates the middle initial and the values in **FirstName** and **LastName**, and inserts appropriate spaces between values.</span></span>  
  
    ```  
    TRIM(FirstName) + " " + (!ISNULL(MiddleName) ? SUBSTRING(MiddleName,1,1) + " " : "") + TRIM(LastName)  
    ```  
  
-   <span data-ttu-id="c3cd7-128">L’exemple suivant utilise la table **Contact** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-128">This example uses the **Contact** table.</span></span> <span data-ttu-id="c3cd7-129">L’expression valide les entrées de la colonne **Salutation** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-129">The expression validates entries in the **Salutation** column.</span></span> <span data-ttu-id="c3cd7-130">Elle retourne une entrée **Salutation** ou une chaîne vide.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-130">It returns a **Salutation** entry or an empty string.</span></span>  
  
    ```  
    (Salutation == "Sr." || Salutation == "Ms." || Salutation == "Sra." || Salutation == "Mr.") ? Salutation : ""  
    ```  
  
-   <span data-ttu-id="c3cd7-131">L’exemple suivant utilise la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-131">This example uses the **Product** table.</span></span> <span data-ttu-id="c3cd7-132">L’expression convertit le premier caractère de la colonne **Color** en majuscules et les autres caractères en minuscules.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-132">The expression converts the first character in the **Color** column to uppercase and converts remaining characters to lowercase.</span></span>  
  
    ```  
    UPPER(SUBSTRING(Color,1,1)) + LOWER(SUBSTRING(Color,2,15))  
    ```  
  
-   <span data-ttu-id="c3cd7-133">L’exemple suivant utilise la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-133">This example uses the **Product** table.</span></span> <span data-ttu-id="c3cd7-134">L’expression calcule le nombre de mois pendant lesquels un produit a été vendu et retourne la chaîne « Unknown » si la colonne **SellStartDate** ou **SellEndDate** contient une valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-134">The expression calculates the number of months a product has been sold and returns the string "Unknown" if either the **SellStartDate** or the **SellEndDate** column contains NULL.</span></span>  
  
    ```  
    !(ISNULL(SellStartDate)) && !(ISNULL(SellEndDate)) ? (DT_WSTR,2)DATEDIFF("mm",SellStartDate,SellEndDate) : "Unknown"  
    ```  
  
-   <span data-ttu-id="c3cd7-135">L’exemple suivant utilise la table **Product** .</span><span class="sxs-lookup"><span data-stu-id="c3cd7-135">This example uses the **Product** table.</span></span> <span data-ttu-id="c3cd7-136">L’expression calcule la marge sur la colonne **StandardCost** et arrondit le résultat avec une précision de deux.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-136">The expression calculates the markup on the **StandardCost** column and rounds the result to a precision of two.</span></span> <span data-ttu-id="c3cd7-137">Le résultat est exprimé en pourcentage.</span><span class="sxs-lookup"><span data-stu-id="c3cd7-137">The result is presented as a percentage.</span></span>  
  
    ```  
    ROUND(ListPrice / StandardCost,2) * 100  
    ```  
  
## <a name="related-tasks"></a><span data-ttu-id="c3cd7-138">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="c3cd7-138">Related Tasks</span></span>  
 [<span data-ttu-id="c3cd7-139">Utiliser une expression dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="c3cd7-139">Use an Expression in a Data Flow Component</span></span>](../use-an-expression-in-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="c3cd7-140">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="c3cd7-140">Related Content</span></span>  
 <span data-ttu-id="c3cd7-141">Article technique, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), sur pragmaticworks.com</span><span class="sxs-lookup"><span data-stu-id="c3cd7-141">Technical article, [SSIS Expression Cheat Sheet](https://pragmaticworks.com/Resources/Cheat-Sheets/SSIS-Expression-Cheat-Sheet), on pragmaticworks.com</span></span>  
  
  
