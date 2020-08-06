---
title: Exemples d’expressions (Générateur de rapports et SSRS) | Microsoft Docs
ms.prod: sql-server-2014
ms.technology: reporting-services
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 03/08/2017
ms.openlocfilehash: c7ef06143dafdb5034d0f6202fdc16bc51f74ca8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603857"
---
# <a name="expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="3266a-102">Exemples d'expressions (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="3266a-102">Expression Examples (Report Builder and SSRS)</span></span>

<span data-ttu-id="3266a-103">Les expressions sont fréquemment utilisées dans les rapports pour en contrôler le contenu et l'apparence.</span><span class="sxs-lookup"><span data-stu-id="3266a-103">Expressions are used frequently in reports to control content and report appearance.</span></span> <span data-ttu-id="3266a-104">Les expressions sont écrites dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] et peuvent utiliser des fonctions intégrées du code personnalisé, des variables de rapport et de groupe, et des variables définies par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3266a-104">Expressions are written in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], and can use built-in functions custom code, report and group variables, and user-defined variables.</span></span> <span data-ttu-id="3266a-105">Les expressions commencent par un signe égal (=).</span><span class="sxs-lookup"><span data-stu-id="3266a-105">Expressions begin with an equal sign (=).</span></span> <span data-ttu-id="3266a-106">Pour plus d’informations sur l’éditeur d’expressions et les types de références que vous pouvez inclure, consultez [Utilisation d’expressions dans les rapports &#40;Générateur de rapports et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), et [Ajouter une expression &#40;Générateur de rapports et SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-106">For more information about the expression editor and the types of references that you can include, see [Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md), and [Add an Expression &#40;Report Builder and SSRS&#41;](add-an-expression-report-builder-and-ssrs.md).</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="3266a-107">Lorsque le sandboxing RDL est activé, seuls certains types et membres peuvent être utilisés dans le texte de l'expression au moment de la publication des rapports.</span><span class="sxs-lookup"><span data-stu-id="3266a-107">When RDL Sandboxing is enabled, only certain types and members can be used in expression text at report publish time.</span></span> <span data-ttu-id="3266a-108">Pour plus d’informations, consultez [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-108">For more information, see [Enable and Disable RDL Sandboxing](../enable-and-disable-rdl-sandboxing.md).</span></span>  

<span data-ttu-id="3266a-109">Cette rubrique propose des exemples d'expressions qu'il est possible d'utiliser pour des tâches courantes dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-109">This topic provides examples of expressions that can be used for common tasks in a report.</span></span>  

-   <span data-ttu-id="3266a-110">[Fonctions Visual Basic](#VisualBasicFunctions) Exemples pour les fonctions [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] de date, de chaîne, de conversion et conditionnelles.</span><span class="sxs-lookup"><span data-stu-id="3266a-110">[Visual Basic Functions](#VisualBasicFunctions) Examples for date, string, conversion and conditional [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions.</span></span>  

-   <span data-ttu-id="3266a-111">[Fonctions de rapport](#ReportFunctions) Exemples pour les agrégats et autres fonctions de rapport intégrées.</span><span class="sxs-lookup"><span data-stu-id="3266a-111">[Report Functions](#ReportFunctions) Examples for aggregates and other built-in report functions.</span></span>  

-   <span data-ttu-id="3266a-112">[Apparence des données d'un rapport](#AppearanceofReportData) Exemples pour la modification de l'apparence d'un rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-112">[Appearance of Report Data](#AppearanceofReportData) Examples for changing the appearance of a report.</span></span>  

-   <span data-ttu-id="3266a-113">[Propriétés](#Properties) Exemples pour la définition des propriétés d'élément de rapport permettant de contrôler le format ou la visibilité.</span><span class="sxs-lookup"><span data-stu-id="3266a-113">[Properties](#Properties) Examples for setting report item properties to control format or visibility.</span></span>  

-   <span data-ttu-id="3266a-114">[Paramètres](#Parameters) Exemples pour l'utilisation de paramètres dans une expression.</span><span class="sxs-lookup"><span data-stu-id="3266a-114">[Parameters](#Parameters) Examples for using parameters in an expression.</span></span>  

-   <span data-ttu-id="3266a-115">[Code personnalisé](#CustomCode) Exemples de code personnalisé incorporé.</span><span class="sxs-lookup"><span data-stu-id="3266a-115">[Custom Code](#CustomCode) Examples of embedded custom code.</span></span>  

<span data-ttu-id="3266a-116">Pour obtenir des exemples d'expressions pour des utilisations spécifiques, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="3266a-116">For expression examples for specific uses, see the following topics:</span></span>  

-   [<span data-ttu-id="3266a-117">Exemples d’expressions de groupe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-117">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="3266a-118">Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-118">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="3266a-119">Filtres couramment utilisés &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-119">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)  

-   [<span data-ttu-id="3266a-120">Références à des collections de variables de rapport et de groupe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-120">Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-report-and-group-variables-references-report-builder.md)  

<span data-ttu-id="3266a-121">Pour plus d’informations sur les expressions simples et complexes, l’endroit où vous pouvez utiliser des expressions et les types de références que vous pouvez inclure dans une expression, consultez les rubriques sous [Expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-121">For more information about simple and complex expressions, where you can use expressions, and the types of references that you can include in an expression, see topics under [Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md).</span></span> <span data-ttu-id="3266a-122">Pour plus d’informations sur le contexte dans lequel les expressions sont évaluées pour calculer des agrégats, consultez [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-122">For more information about the context in which expressions are evaluated for calculating aggregates, see [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  

<span data-ttu-id="3266a-123">Pour apprendre à écrire des expressions qui utilisent plusieurs fonctions et opérateurs également utilisés par les exemples d'expressions de cette rubrique, mais dans le contexte de la rédaction d'un rapport, consultez [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-123">To learn how to write expressions that use many of the functions and operators also used by expression examples in this topic, but in the context of writing a report, see [Tutorial: Introducing Expressions](../tutorial-introducing-expressions.md).</span></span>  

<span data-ttu-id="3266a-124">L'éditeur d'expressions inclut une vue hiérarchique des fonctions intégrées.</span><span class="sxs-lookup"><span data-stu-id="3266a-124">The expression editor includes a hierarchical view of built-in functions.</span></span> <span data-ttu-id="3266a-125">Lorsque vous sélectionnez la fonction, un exemple de code apparaît dans le volet Valeurs.</span><span class="sxs-lookup"><span data-stu-id="3266a-125">When you select the function, a code example appears in the Values pane.</span></span> <span data-ttu-id="3266a-126">Pour plus d’informations, consultez la boîte de dialogue [expression](../expression-dialog-box.md) ou [expression &#40;générateur de rapports&#41;](../expression-dialog-box-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-126">For more information, see the [Expression Dialog Box](../expression-dialog-box.md) or [Expression Dialog Box &#40;Report Builder&#41;](../expression-dialog-box-report-builder.md).</span></span>  

## <a name="functions"></a><span data-ttu-id="3266a-127">Fonctions</span><span class="sxs-lookup"><span data-stu-id="3266a-127">Functions</span></span>  

<span data-ttu-id="3266a-128">Dans un rapport, beaucoup d'expressions contiennent des fonctions.</span><span class="sxs-lookup"><span data-stu-id="3266a-128">Many expressions in a report contain functions.</span></span> <span data-ttu-id="3266a-129">Vous pouvez mettre en forme des données, appliquer une logique et accéder aux métadonnées du rapport en utilisant ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="3266a-129">You can format data, apply logic, and access report metadata using these functions.</span></span> <span data-ttu-id="3266a-130">Vous pouvez écrire des expressions qui utilisent des fonctions de la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] bibliothèque Runtime, et des <xref:System.Convert> espaces de <xref:System.Math> noms et.</span><span class="sxs-lookup"><span data-stu-id="3266a-130">You can write expressions that use functions from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] run-time library, and from the <xref:System.Convert> and <xref:System.Math> namespaces.</span></span> <span data-ttu-id="3266a-131">Vous pouvez ajouter des références à des fonctions issues d'autres assemblys ou du code personnalisé.</span><span class="sxs-lookup"><span data-stu-id="3266a-131">You can add references to functions from other assemblies or custom code.</span></span> <span data-ttu-id="3266a-132">Vous pouvez également utiliser des classes du [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] , y compris <xref:System.Text.RegularExpressions> .</span><span class="sxs-lookup"><span data-stu-id="3266a-132">You can also use classes from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], including <xref:System.Text.RegularExpressions>.</span></span>  

###  <a name="visual-basic-functions"></a><a name="VisualBasicFunctions"></a> <span data-ttu-id="3266a-133">Fonctions Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3266a-133">Visual Basic Functions</span></span>  
<span data-ttu-id="3266a-134">Vous pouvez utiliser des fonctions [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] pour manipuler les données affichées dans des zones de texte ou utilisées pour des paramètres, des propriétés et d'autres zones du rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-134">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to manipulate the data that is displayed in text boxes or that is used for parameters, properties, or other areas of the report.</span></span> <span data-ttu-id="3266a-135">Cette section fournit des exemples décrivant certaines de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="3266a-135">This section provides examples demonstrating some of these functions.</span></span> <span data-ttu-id="3266a-136">Pour plus d'informations, consultez [Membres de la bibliothèque runtime Visual Basic](https://go.microsoft.com/fwlink/?LinkId=198941) sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="3266a-136">For more information, see [Visual Basic Runtime Library Members](https://go.microsoft.com/fwlink/?LinkId=198941) on MSDN.</span></span>  

<span data-ttu-id="3266a-137">Le [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] offre de nombreuses options de formats personnalisés, par exemple pour des formats de date spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3266a-137">The [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] provides many custom format options, for example, for specific date formats.</span></span> <span data-ttu-id="3266a-138">Pour plus d'informations, consultez [Mise en forme des types](https://go.microsoft.com/fwlink/?LinkId=112024) sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="3266a-138">For more information, see [Formatting Types](https://go.microsoft.com/fwlink/?LinkId=112024) on MSDN.</span></span>  

#### <a name="math-functions"></a><span data-ttu-id="3266a-139">Fonctions mathématiques</span><span class="sxs-lookup"><span data-stu-id="3266a-139">Math Functions</span></span>  

-   <span data-ttu-id="3266a-140">La fonction `Round` permet d'arrondir des nombres à l'entier le plus proche.</span><span class="sxs-lookup"><span data-stu-id="3266a-140">The `Round` function is useful to round numbers to the nearest integer.</span></span> <span data-ttu-id="3266a-141">L'expression suivante arrondit 1,3 à 1 :</span><span class="sxs-lookup"><span data-stu-id="3266a-141">The following expression rounds a 1.3 to 1:</span></span>  

```  
= Round(1.3)  
```  

<span data-ttu-id="3266a-142">Vous pouvez également écrire une expression pour arrondir une valeur à un multiple de votre choix, de manière semblable à la fonction `MRound` dans Excel.</span><span class="sxs-lookup"><span data-stu-id="3266a-142">You can also write an expression to round a value to a multiple that you specify, similar to the `MRound` function in Excel.</span></span> <span data-ttu-id="3266a-143">Multipliez la valeur par un facteur qui crée un entier, arrondissez le nombre, puis divisez-le par le même facteur.</span><span class="sxs-lookup"><span data-stu-id="3266a-143">Multiply the value by a factor that creates an integer, round the number, and then divide by the same factor.</span></span> <span data-ttu-id="3266a-144">Par exemple, pour arrondir 1,3 au multiple le plus proche de 0,2 (1,4), utilisez l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="3266a-144">For example, to round 1.3 to the nearest multiple of .2 (1.4), use the following expression:</span></span>  

```  
= Round(1.3*5)/5  
```  

####  <a name="date-functions"></a><a name="DateFunctions"></a><span data-ttu-id="3266a-145">Fonctions de date</span><span class="sxs-lookup"><span data-stu-id="3266a-145">Date Functions</span></span>  

-   <span data-ttu-id="3266a-146">La fonction `Today` fournit la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="3266a-146">The `Today` function provides the current date.</span></span> <span data-ttu-id="3266a-147">Cette expression peut être utilisée dans une zone de texte pour afficher la date sur le rapport ou bien, dans un paramètre pour filtrer les données basées sur la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="3266a-147">This expression can be used in a text box to display the date on the report, or in a parameter to filter data based on the current date.</span></span>  

```  
=Today()  
```  

-   <span data-ttu-id="3266a-148">La fonction `DateAdd` est utile pour fournir une plage de dates basées sur un seul paramètre.</span><span class="sxs-lookup"><span data-stu-id="3266a-148">The `DateAdd` function is useful for supplying a range of dates based on a single parameter.</span></span> <span data-ttu-id="3266a-149">L'expression ci-dessous indique une date qui se situe six mois après la date provenant du paramètre nommé *StartDate*.</span><span class="sxs-lookup"><span data-stu-id="3266a-149">The following expression provides a date that is six months after the date from a parameter named *StartDate*.</span></span>  

```  
=DateAdd(DateInterval.Month, 6, Parameters!StartDate.Value)  
```  

-   <span data-ttu-id="3266a-150">La fonction `Year` affiche l'année pour une date particulière.</span><span class="sxs-lookup"><span data-stu-id="3266a-150">The `Year` function displays the year for a particular date.</span></span> <span data-ttu-id="3266a-151">Vous pouvez l'utiliser pour grouper des dates ou pour afficher l'année en tant que libellé d'un ensemble de dates.</span><span class="sxs-lookup"><span data-stu-id="3266a-151">You can use this to group dates together or to display the year as a label for a set of dates.</span></span> <span data-ttu-id="3266a-152">Cette expression affiche l'année pour un groupe donné de dates de commande client.</span><span class="sxs-lookup"><span data-stu-id="3266a-152">This expression provides the year for a given group of sales order dates.</span></span> <span data-ttu-id="3266a-153">La fonction `Month` et d'autres fonctions peuvent également être utilisées pour manipuler des dates.</span><span class="sxs-lookup"><span data-stu-id="3266a-153">The `Month` function and other functions can also be used to manipulate dates.</span></span> <span data-ttu-id="3266a-154">Pour plus d’informations, consultez la documentation de [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3266a-154">For more information, see the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] documentation.</span></span>  

```  
=Year(Fields!OrderDate.Value)  
```  

-   <span data-ttu-id="3266a-155">Vous pouvez combiner des fonctions dans une expression pour personnaliser le format.</span><span class="sxs-lookup"><span data-stu-id="3266a-155">You can combine functions in an expression to customize the format.</span></span> <span data-ttu-id="3266a-156">L'expression suivante modifie le format d'une date écrite sous la forme mois-jour-année en mois-semaine-numéro de semaine.</span><span class="sxs-lookup"><span data-stu-id="3266a-156">The following expression changes the format of a date in the form month-day-year to month-week-week number.</span></span> <span data-ttu-id="3266a-157">Par exemple, 12/23/2009 est remplacé par December Week 3 (Décembre Semaine 3) :</span><span class="sxs-lookup"><span data-stu-id="3266a-157">For example, 12/23/2009 to December Week 3:</span></span>  

```  
=Format(Fields!MyDate.Value, "MMMM") & " Week " &   
(Int(DateDiff("d", DateSerial(Year(Fields!MyDate.Value),   
Month(Fields!MyDate.Value),1), Fields!FullDateAlternateKey.Value)/7)+1).ToString  
```  

<span data-ttu-id="3266a-158">Lorsque cette expression est utilisée comme champ calculé dans un dataset, vous pouvez vous en servir dans un graphique pour agréger les valeurs par semaine dans chaque mois.</span><span class="sxs-lookup"><span data-stu-id="3266a-158">When used as a calculated field in a dataset, you can use this expression on a chart to aggregate values by week within each month.</span></span>  

-   <span data-ttu-id="3266a-159">L'expression suivante affiche la valeur SellStartDate au format MMM-YY.</span><span class="sxs-lookup"><span data-stu-id="3266a-159">The following expression formats the SellStartDate value as MMM-YY.</span></span> <span data-ttu-id="3266a-160">Le champ SellStartDate comprend des données de type datetime.</span><span class="sxs-lookup"><span data-stu-id="3266a-160">SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "MMM-yy")  
```  

-   <span data-ttu-id="3266a-161">L'expression suivante affiche la valeur SellStartDate au format dd/MM/yyyy.</span><span class="sxs-lookup"><span data-stu-id="3266a-161">The following expression formats the SellStartDate value as dd/MM/yyyy.</span></span> <span data-ttu-id="3266a-162">Le champ SellStartDate comprend des données de type datetime.</span><span class="sxs-lookup"><span data-stu-id="3266a-162">The SellStartDate field is a datetime data type.</span></span>  

```  
=FORMAT(Fields!SellStartDate.Value, "dd/MM/yyyy")  
```  

-   <span data-ttu-id="3266a-163">La fonction `CDate` convertit la valeur en date.</span><span class="sxs-lookup"><span data-stu-id="3266a-163">The `CDate` function converts the value to a date.</span></span> <span data-ttu-id="3266a-164">La fonction `Now` retourne une valeur de date contenant la date et l'heure actuelles en fonction de votre système.</span><span class="sxs-lookup"><span data-stu-id="3266a-164">The `Now` function returns a date value containing the current date and time according to your system.</span></span> <span data-ttu-id="3266a-165">`DateDiff` retourne une valeur longue spécifiant le nombre d'intervalles de temps entre deux valeurs de date.</span><span class="sxs-lookup"><span data-stu-id="3266a-165">`DateDiff` returns a Long value specifying the number of time intervals between two Date values.</span></span>  

<span data-ttu-id="3266a-166">L'exemple suivant affiche la date de début de l'année en cours</span><span class="sxs-lookup"><span data-stu-id="3266a-166">The following example displays the start date of the current year</span></span>  

```  
=DateAdd(DateInterval.Year,DateDiff(DateInterval.Year,CDate("01/01/1900"),Now()),CDate("01/01/1900"))  
```  

-   <span data-ttu-id="3266a-167">L'exemple suivant affiche la date de début du mois précédent en fonction du mois actuel.</span><span class="sxs-lookup"><span data-stu-id="3266a-167">The following example displays the start date for the previous month based on the current month.</span></span>  

```  
=DateAdd(DateInterval.Month,DateDiff(DateInterval.Month,CDate("01/01/1900"),Now())-1,CDate("01/01/1900"))  
```  

-   <span data-ttu-id="3266a-168">L'expression suivante génère des années d'intervalle entre SellStartDate et LastReceiptDate.</span><span class="sxs-lookup"><span data-stu-id="3266a-168">The following expression generates the interval years between SellStartDate and LastReceiptDate.</span></span> <span data-ttu-id="3266a-169">Ces champs sont compris dans deux datasets différents, DataSet1 et DataSet2.</span><span class="sxs-lookup"><span data-stu-id="3266a-169">These fields are in two different datasets, DataSet1 and DataSet2.</span></span> <span data-ttu-id="3266a-170">La [fonction First &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-first-function.md), qui est une fonction d’agrégation, renvoie la première valeur de SellStartDate dans DataSet1 et la première valeur de LastReceiptDate dans DataSet2.</span><span class="sxs-lookup"><span data-stu-id="3266a-170">The [First Function &#40;Report Builder and SSRS&#41;](report-builder-functions-first-function.md), which is an aggregate function, returns the first value of SellStartDate in DataSet1 and the first value of LastReceiptDate in DataSet2.</span></span>  

```  
=DATEDIFF("yyyy", First(Fields!SellStartDate.Value, "DataSet1"), First(Fields!LastReceiptDate.Value, "DataSet2"))  
```  

-   <span data-ttu-id="3266a-171">La fonction `DatePart` renvoie une valeur entière contenant le composant spécifié d'une valeur donnée de Date. L'expression suivante renvoie l'année de la première valeur de SellStartDate dans DataSet1.</span><span class="sxs-lookup"><span data-stu-id="3266a-171">The `DatePart` function returns an Integer value containing the specified component of a given Date value.The following expression returns the year for the first value of the SellStartDate in DataSet1.</span></span> <span data-ttu-id="3266a-172">L'étendue du dataset est spécifiée, car le rapport contient plusieurs datasets.</span><span class="sxs-lookup"><span data-stu-id="3266a-172">The dataset scope is specified because there are multiple datasets in the report.</span></span>  

```  
=Datepart("yyyy", First(Fields!SellStartDate.Value, "DataSet1"))  

```  

-   <span data-ttu-id="3266a-173">La fonction `DateSerial` renvoie une valeur Date représentant une année, un mois et un jour spécifiés, avec l'heure définie sur minuit.</span><span class="sxs-lookup"><span data-stu-id="3266a-173">The `DateSerial` function returns a Date value representing a specified year, month, and day, with the time information set to midnight.</span></span> <span data-ttu-id="3266a-174">L'exemple suivant affiche la date de fin du mois précédent en fonction du mois actuel.</span><span class="sxs-lookup"><span data-stu-id="3266a-174">The following example displays the ending date for the prior month, based on the current month.</span></span>  

```  
=DateSerial(Year(Now()), Month(Now()), "1").AddDays(-1)  
```  

-   <span data-ttu-id="3266a-175">Les expressions suivantes affichent plusieurs dates basées sur une valeur de paramètre de date sélectionnée par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3266a-175">The following expressions display various dates based on a date parameter value selected by the user.</span></span>  

|<span data-ttu-id="3266a-176">Description de l'exemple</span><span class="sxs-lookup"><span data-stu-id="3266a-176">Example Description</span></span>|<span data-ttu-id="3266a-177">Exemple</span><span class="sxs-lookup"><span data-stu-id="3266a-177">Example</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="3266a-178">hier</span><span class="sxs-lookup"><span data-stu-id="3266a-178">Yesterday</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-1)`|  
|<span data-ttu-id="3266a-179">Il y a deux jours</span><span class="sxs-lookup"><span data-stu-id="3266a-179">Two Days Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value)-2)`|  
|<span data-ttu-id="3266a-180">Il y a un mois</span><span class="sxs-lookup"><span data-stu-id="3266a-180">One Month Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-1,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="3266a-181">Il y a deux mois</span><span class="sxs-lookup"><span data-stu-id="3266a-181">Two Months Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value),Month(Parameters!TodaysDate.Value)-2,Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="3266a-182">Il y a un an</span><span class="sxs-lookup"><span data-stu-id="3266a-182">One Year Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-1,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  
|<span data-ttu-id="3266a-183">Il y a deux ans</span><span class="sxs-lookup"><span data-stu-id="3266a-183">Two Years Ago</span></span>|`=DateSerial(Year(Parameters!TodaysDate.Value)-2,Month(Parameters!TodaysDate.Value),Day(Parameters!TodaysDate.Value))`|  

####  <a name="string-functions"></a><a name="StringFunctions"></a><span data-ttu-id="3266a-184">Fonctions de chaîne</span><span class="sxs-lookup"><span data-stu-id="3266a-184">String Functions</span></span>  

-   <span data-ttu-id="3266a-185">Vous pouvez combiner plusieurs champs en utilisant des opérateurs de concaténation et des constantes [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3266a-185">Combine more than one field by using concatenation operators and [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] constants.</span></span> <span data-ttu-id="3266a-186">L'expression suivante retourne deux champs, chacun sur une ligne séparée dans la même zone de texte :</span><span class="sxs-lookup"><span data-stu-id="3266a-186">The following expression returns two fields, each on a separate line in the same text box:</span></span>  

```  
=Fields!FirstName.Value & vbCrLf & Fields!LastName.Value   
```  

-   <span data-ttu-id="3266a-187">Vous pouvez mettre en forme des dates et des nombres dans une chaîne avec la fonction `Format`.</span><span class="sxs-lookup"><span data-stu-id="3266a-187">Format dates and numbers in a string with the `Format` function.</span></span> <span data-ttu-id="3266a-188">L'expression suivante affiche les valeurs des paramètres *StartDate* et *EndDate* dans un format de date longue :</span><span class="sxs-lookup"><span data-stu-id="3266a-188">The following expression displays values of the *StartDate* and *EndDate* parameters in long date format:</span></span>  

```  
=Format(Parameters!StartDate.Value, "D") & " through " &  Format(Parameters!EndDate.Value, "D")    
```  

<span data-ttu-id="3266a-189">Si la zone de texte contient uniquement une date ou un nombre, vous devez utiliser la propriété format de la zone de texte pour appliquer la mise en forme au lieu de la `Format` fonction dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-189">If the text box contains only a date or number, you should use the Format property of the text box to apply formatting instead of the `Format` function within the text box.</span></span>  

-   <span data-ttu-id="3266a-190">Les `Right` `Len` fonctions, et `InStr` sont utiles pour retourner une sous-chaîne, par exemple en découpant *DOMAIN* \\ le nom*d'* utilisateur de domaine en nom d’utilisateur uniquement.</span><span class="sxs-lookup"><span data-stu-id="3266a-190">The `Right`, `Len`, and `InStr` functions are useful for returning a substring, for example, trimming *DOMAIN*\\*username* to just the user name.</span></span> <span data-ttu-id="3266a-191">L’expression suivante retourne la partie de la chaîne à droite de la barre oblique inverse (\\) à partir d’un paramètre nommé *User*:</span><span class="sxs-lookup"><span data-stu-id="3266a-191">The following expression returns the part of the string to the right of a backslash (\\) character from a parameter named *User*:</span></span>  

```  
=Right(Parameters!User.Value, Len(Parameters!User.Value) - InStr(Parameters!User.Value, "\"))  
```  

<span data-ttu-id="3266a-192">L’expression suivante produit la même valeur que la précédente, en utilisant les membres de la [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> classe au lieu des [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] fonctions :</span><span class="sxs-lookup"><span data-stu-id="3266a-192">The following expression results in the same value as the previous one, using members of the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.String> class instead of [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions:</span></span>  

```  
=Parameters!User.Value.Substring(Parameters!User.Value.IndexOf("\")+1, Parameters!User.Value.Length-Parameters!User.Value.IndexOf("\")-1)  
```  

-   <span data-ttu-id="3266a-193">Vous pouvez afficher les valeurs sélectionnées à partir d'un paramètre à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="3266a-193">Display the selected values from a multivalue parameter.</span></span> <span data-ttu-id="3266a-194">L’exemple suivant utilise la `Join` fonction pour concaténer les valeurs sélectionnées du paramètre *MySelection* en une chaîne unique qui peut être définie en tant qu’expression pour la valeur d’une zone de texte dans un élément de rapport :</span><span class="sxs-lookup"><span data-stu-id="3266a-194">The following example uses the `Join` function to concatenate the selected values of the parameter *MySelection* into a single string that can be set as an expression for the value of a text box in a report item:</span></span>  

```  
= Join(Parameters!MySelection.Value)  
```  

<span data-ttu-id="3266a-195">L'exemple suivant donne le même résultat que l'exemple ci-dessus et affiche une chaîne de texte avant la liste de valeurs sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="3266a-195">The following example does the same as the above example, as well as displays a text string prior to the list of selected values.</span></span>  

```  
="Report for " & JOIN(Parameters!MySelection.Value, " & ")  

```  

-   <span data-ttu-id="3266a-196">Les `Regex` fonctions de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> sont utiles pour modifier le format des chaînes existantes, par exemple la mise en forme d’un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="3266a-196">The `Regex` functions from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] <xref:System.Text.RegularExpressions> are useful for changing the format of existing strings, for example, formatting a telephone number.</span></span> <span data-ttu-id="3266a-197">L’expression suivante utilise la `Replace` fonction pour modifier le format d’un numéro de téléphone à dix chiffres dans un champ de "*nnn* - *nnn* - *nnnn*" en "(*nnn*) *nnn* - *nnnn*" :</span><span class="sxs-lookup"><span data-stu-id="3266a-197">The following expression uses the `Replace` function to change the format of a ten-digit telephone number in a field from "*nnn*-*nnn*-*nnnn*" to "(*nnn*) *nnn*-*nnnn*":</span></span>  

```  
=System.Text.RegularExpressions.Regex.Replace(Fields!Phone.Value, "(\d{3})[ -.]*(\d{3})[ -.]*(\d{4})", "($1) $2-$3")  
```  

> [!NOTE]  
>  <span data-ttu-id="3266a-198">Vérifiez que la valeur de Fields!Phone.Value n’a pas d’espaces supplémentaires et est de type <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="3266a-198">Verify that the value for Fields!Phone.Value has no extra spaces and is of type <xref:System.String>.</span></span>  

#### <a name="lookup"></a><span data-ttu-id="3266a-199">Recherche</span><span class="sxs-lookup"><span data-stu-id="3266a-199">Lookup</span></span>  

-   <span data-ttu-id="3266a-200">En spécifiant un champ clé, vous pouvez utiliser la fonction `Lookup` pour récupérer une valeur à partir d'un dataset pour une relation un-à-un, par exemple une paire clé-valeur.</span><span class="sxs-lookup"><span data-stu-id="3266a-200">By specifying a key field, you can use the `Lookup` function to retrieve a value from a dataset for a one-to-one relationship, for example, a key-value pair.</span></span> <span data-ttu-id="3266a-201">L’expression suivante affiche le nom de produit d’un dataset (« Product »), compte tenu de l’identificateur de produit qui doit être mis en correspondance :</span><span class="sxs-lookup"><span data-stu-id="3266a-201">The following expression displays the product name from a dataset ("Product"), given the product identifier to match on:</span></span>  

```  
=Lookup(Fields!PID.Value, Fields!ProductID.Value, Fields!ProductName.Value, "Product")  
```  

#### <a name="lookupset"></a><span data-ttu-id="3266a-202">LookupSet</span><span class="sxs-lookup"><span data-stu-id="3266a-202">LookupSet</span></span>  

-   <span data-ttu-id="3266a-203">En spécifiant un champ clé, vous pouvez utiliser la fonction `LookupSet` pour récupérer un jeu de valeurs à partir d'un dataset pour une relation un-à-plusieurs.</span><span class="sxs-lookup"><span data-stu-id="3266a-203">By specifying a key field, you can use the `LookupSet` function to retrieve a set of values from a dataset for a one-to-many relationship.</span></span> <span data-ttu-id="3266a-204">Par exemple, une personne peut avoir plusieurs numéros de téléphone.</span><span class="sxs-lookup"><span data-stu-id="3266a-204">For example, a person can have multiple telephone numbers.</span></span> <span data-ttu-id="3266a-205">Dans l'exemple suivant, supposons que le dataset PhoneList contient un identificateur de personne et un numéro de téléphone sur chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="3266a-205">In the following example, assume the dataset PhoneList contains a person identifier and a telephone number in each row.</span></span> <span data-ttu-id="3266a-206">`LookupSet` retourne un tableau de valeurs.</span><span class="sxs-lookup"><span data-stu-id="3266a-206">`LookupSet` returns an array of values.</span></span> <span data-ttu-id="3266a-207">L'expression suivante combine les valeurs de retour dans une chaîne unique et affiche la liste des numéros de téléphone de la personne spécifiée par ContactID :</span><span class="sxs-lookup"><span data-stu-id="3266a-207">The following expression combines the return values into a single string and displays the list of telephone numbers for the person specified by ContactID:</span></span>  

```  
=Join(LookupSet(Fields!ContactID.Value, Fields!PersonID.Value, Fields!PhoneNumber.Value, "PhoneList"),",")  
```  

####  <a name="conversion-functions"></a><a name="ConversionFunctions"></a><span data-ttu-id="3266a-208">Fonctions de conversion</span><span class="sxs-lookup"><span data-stu-id="3266a-208">Conversion Functions</span></span>  
<span data-ttu-id="3266a-209">Vous pouvez utiliser des fonctions [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] pour convertir un champ en un type de données différent de celui qu'il avait au départ.</span><span class="sxs-lookup"><span data-stu-id="3266a-209">You can use [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to convert a field from the one data type to a different data type.</span></span> <span data-ttu-id="3266a-210">Les fonctions de conversion peuvent être utilisées pour convertir le type de données par défaut d'un champ en type qui sera nécessaire pour certains calculs ou pour combiner du texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-210">Conversion functions can be used to convert the default data type for a field to the data type needed for calculations or to combine text.</span></span>  

-   <span data-ttu-id="3266a-211">L’expression suivante convertit la constante 500 en type Decimal pour la comparer à un type de données money [!INCLUDE[tsql](../../includes/tsql-md.md)] dans le champ Value d’une expression de filtre.</span><span class="sxs-lookup"><span data-stu-id="3266a-211">The following expression converts the constant 500 to type Decimal in order to compare it to a [!INCLUDE[tsql](../../includes/tsql-md.md)] money data type in the Value field for a filter expression.</span></span>  

```  
=CDec(500)  
```  

-   <span data-ttu-id="3266a-212">L'expression ci-dessous affiche le nombre de valeurs sélectionnées pour le paramètre à valeurs multiples *MySelection*.</span><span class="sxs-lookup"><span data-stu-id="3266a-212">The following expression displays the number of values selected for the multivalue parameter *MySelection*.</span></span>  

```  
=CStr(Parameters!MySelection.Count)  
```  

####  <a name="decision-functions"></a><a name="DecisionFunctions"></a><span data-ttu-id="3266a-213">Fonctions de décision</span><span class="sxs-lookup"><span data-stu-id="3266a-213">Decision Functions</span></span>  

-   <span data-ttu-id="3266a-214">La fonction `Iif` retourne une valeur sur les deux possibles, laquelle dépend du fait que l'expression est vraie ou fausse.</span><span class="sxs-lookup"><span data-stu-id="3266a-214">The `Iif` function returns one of two values depending on whether the expression is true or not.</span></span> <span data-ttu-id="3266a-215">L'expression ci-dessous utilise la fonction `Iif` pour retourner la valeur booléenne `True` si la valeur de `LineTotal` est supérieure à 100.</span><span class="sxs-lookup"><span data-stu-id="3266a-215">The following expression uses the `Iif` function to return a Boolean value of `True` if the value of `LineTotal` exceeds 100.</span></span> <span data-ttu-id="3266a-216">Sinon, elle retourne `False` :</span><span class="sxs-lookup"><span data-stu-id="3266a-216">Otherwise it returns `False`:</span></span>  

```  
=IIF(Fields!LineTotal.Value > 100, True, False)  
```  

-   <span data-ttu-id="3266a-217">Vous pouvez utiliser des fonctions `IIF` (également appelées « IIF imbriqués ») pour retourner une valeur sur les trois possibles, laquelle dépend de la valeur de `PctComplete`.</span><span class="sxs-lookup"><span data-stu-id="3266a-217">Use multiple `IIF` functions (also known as "nested IIFs") to return one of three values depending on the value of `PctComplete`.</span></span> <span data-ttu-id="3266a-218">L'expression ci-dessous peut être placée dans la couleur de remplissage d'une zone de texte afin de changer la couleur d'arrière-plan selon la valeur contenue dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-218">The following expression can be placed in the fill color of a text box to change the background color depending on the value in the text box.</span></span>  

```  
=IIF(Fields!PctComplete.Value >= 10, "Green", IIF(Fields!PctComplete.Value >= 1, "Blue", "Red"))  
```  

<span data-ttu-id="3266a-219">Les valeurs supérieures ou égales à 10 s'affichent avec un arrière-plan vert, celles qui sont comprises entre 1 et 9 avec un arrière-plan bleu et les valeurs inférieures à 1 avec un arrière-plan rouge.</span><span class="sxs-lookup"><span data-stu-id="3266a-219">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, and less than 1 display with a red background.</span></span>  

-   <span data-ttu-id="3266a-220">Une autre méthode pour obtenir la même fonctionnalité consiste à utiliser la fonction `Switch`.</span><span class="sxs-lookup"><span data-stu-id="3266a-220">A different way to get the same functionality uses the `Switch` function.</span></span> <span data-ttu-id="3266a-221">La fonction `Switch` est utile lorsque vous avez au moins trois conditions à tester.</span><span class="sxs-lookup"><span data-stu-id="3266a-221">The `Switch` function is useful when you have three or more conditions to test.</span></span> <span data-ttu-id="3266a-222">La fonction `Switch` retourne la valeur associée à la première expression d'une série qui remplit la condition :</span><span class="sxs-lookup"><span data-stu-id="3266a-222">The `Switch` function returns the value associated with the first expression in a series that evaluates to true:</span></span>  

```  
=Switch(Fields!PctComplete.Value >= 10, "Green", Fields!PctComplete.Value >= 1, "Blue", Fields!PctComplete.Value = 1, "Yellow", Fields!PctComplete.Value <= 0, "Red",)  
```  

<span data-ttu-id="3266a-223">Les valeurs supérieures ou égales à 10 s'affichent avec un arrière-plan vert, celles qui sont comprises entre 1 et 9 avec un arrière-plan bleu, les valeurs égales à 1 s'affichent avec un arrière-plan jaune et celles qui sont égales ou inférieures à 0 avec un arrière-plan rouge.</span><span class="sxs-lookup"><span data-stu-id="3266a-223">Values greater than or equal to 10 display with a green background, between 1 and 9 display with a blue background, equal to 1 display with a yellow background, and 0 or less display with a red background.</span></span>  

-   <span data-ttu-id="3266a-224">L'expression ci-dessous teste la valeur du champ `ImportantDate` et retourne la valeur « Red » si elle a plus d'une semaine et la valeur « Blue » dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="3266a-224">Test the value of the `ImportantDate` field and return "Red" if it is more than a week old, and "Blue" otherwise.</span></span> <span data-ttu-id="3266a-225">Cette expression peut être utilisée pour contrôler la propriété Color d'une zone de texte dans un élément de rapport :</span><span class="sxs-lookup"><span data-stu-id="3266a-225">This expression can be used to control the Color property of a text box in a report item:</span></span>  

```  
=IIF(DateDiff("d",Fields!ImportantDate.Value, Now())>7,"Red","Blue")  
```  

-   <span data-ttu-id="3266a-226">L'expression ci-dessous teste la valeur du champ `PhoneNumber` et retourne « No Value » si la valeur est `null` (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]) ou le numéro de téléphone dans le cas contraire.</span><span class="sxs-lookup"><span data-stu-id="3266a-226">Test the value of the `PhoneNumber` field and return "No Value" if it is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]); otherwise return the phone number value.</span></span> <span data-ttu-id="3266a-227">Cette expression peut être utilisée pour contrôler la valeur d'une zone de texte dans un élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-227">This expression can be used to control the value of a text box in a report item.</span></span>  

```  
=IIF(Fields!PhoneNumber.Value Is Nothing,"No Value",Fields!PhoneNumber.Value)  
```  

-   <span data-ttu-id="3266a-228">L'expression ci-dessous teste la valeur du champ `Department` et retourne le nom d'un sous-rapport ou `null` (`Nothing` en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="3266a-228">Test the value of the `Department` field and return either a subreport name or a `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="3266a-229">Cette expression peut être utilisée pour des sous-rapports d'extraction conditionnelle.</span><span class="sxs-lookup"><span data-stu-id="3266a-229">This expression can be used for conditional drillthrough subreports.</span></span>  

```  
=IIF(Fields!Department.Value = "Development", "EmployeeReport", Nothing)  
```  

-   <span data-ttu-id="3266a-230">L'expression ci-dessous teste si la valeur d'un champ est Null.</span><span class="sxs-lookup"><span data-stu-id="3266a-230">Test if a field value is null.</span></span> <span data-ttu-id="3266a-231">Cette expression peut être utilisée pour contrôler la propriété `Hidden` d'un élément de rapport de type image.</span><span class="sxs-lookup"><span data-stu-id="3266a-231">This expression can be used to control the `Hidden` property of an image report item.</span></span> <span data-ttu-id="3266a-232">Dans l'exemple suivant, l'image spécifiée par le champ [LargePhoto] s'affiche uniquement si la valeur du champ n'est pas Null.</span><span class="sxs-lookup"><span data-stu-id="3266a-232">In the following example, the image specified by the field [LargePhoto] is displayed only if the value of the field is not null.</span></span>  

```  
=IIF(IsNothing(Fields!LargePhoto.Value),True,False)  
```  

-   <span data-ttu-id="3266a-233">La fonction `MonthName` retourne une valeur de chaîne contenant le nom du mois spécifié.</span><span class="sxs-lookup"><span data-stu-id="3266a-233">The `MonthName` function returns a string value containing the name of the specified month.</span></span> <span data-ttu-id="3266a-234">L'exemple suivant affiche NA dans le champ Mois lorsque le champ contient la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="3266a-234">The following example displays NA in the Month field when the field contains the value of 0.</span></span>  

```  
IIF(Fields!Month.Value=0,"NA",MonthName(IIF(Fields!Month.Value=0,1,Fields!Month.Value)))  

```  

###  <a name="report-functions"></a><a name="ReportFunctions"></a><span data-ttu-id="3266a-235">Fonctions de rapport</span><span class="sxs-lookup"><span data-stu-id="3266a-235">Report Functions</span></span>  
<span data-ttu-id="3266a-236">Dans une expression, vous pouvez ajouter une référence à des fonctions supplémentaires de rapport qui manipulent les données dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-236">In an expression, you can add a reference to additional report functions that manipulate data in a report.</span></span> <span data-ttu-id="3266a-237">Cette section fournit des exemples pour deux de ces fonctions.</span><span class="sxs-lookup"><span data-stu-id="3266a-237">This section provides examples for two of these functions.</span></span> <span data-ttu-id="3266a-238">Pour plus d’informations sur les fonctions et les exemples de rapport, consultez [Informations de référence sur les fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-238">For more information about report functions and examples, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md).</span></span>  

#####  <a name="sum"></a><a name="Sum"></a><span data-ttu-id="3266a-239">Checksum</span><span class="sxs-lookup"><span data-stu-id="3266a-239">Sum</span></span>  

-   <span data-ttu-id="3266a-240">La fonction `Sum` peut additionner les valeurs dans un groupe ou une région de données.</span><span class="sxs-lookup"><span data-stu-id="3266a-240">The `Sum` function can total the values in a group or data region.</span></span> <span data-ttu-id="3266a-241">Cette fonction peut être utile dans l'en-tête ou le pied de page d'un groupe.</span><span class="sxs-lookup"><span data-stu-id="3266a-241">This function can be useful in the header or footer of a group.</span></span> <span data-ttu-id="3266a-242">L'expression suivante affiche la somme des données dans la région de données ou le groupe Order :</span><span class="sxs-lookup"><span data-stu-id="3266a-242">The following expression displays the sum of data in the Order group or data region:</span></span>  

```  
=Sum(Fields!LineTotal.Value, "Order")  
```  

-   <span data-ttu-id="3266a-243">Vous pouvez également utiliser la fonction `Sum` pour effectuer des calculs d'agrégats conditionnels.</span><span class="sxs-lookup"><span data-stu-id="3266a-243">You can also use the `Sum` function for conditional aggregate calculations.</span></span> <span data-ttu-id="3266a-244">Par exemple, si un dataset contient un champ nommé State dont les valeurs possibles sont Not Started, Started et Finished, l'expression suivante, lorsqu'elle est placée dans un en-tête de groupe, calcule la somme uniquement pour la valeur Finished :</span><span class="sxs-lookup"><span data-stu-id="3266a-244">For example, if a dataset has a field that is named State with possible values Not Started, Started, Finished, the following expression, when placed in a group header, calculates the aggregate sum for only the value Finished:</span></span>  

```  
=Sum(IIF(Fields!State.Value = "Finished", 1, 0))  
```  

#####  <a name="rownumber"></a><a name="RowNumber"></a><span data-ttu-id="3266a-245">RowNumber</span><span class="sxs-lookup"><span data-stu-id="3266a-245">RowNumber</span></span>  

-   <span data-ttu-id="3266a-246">La fonction `RowNumber`, quand elle est utilisée dans une zone de texte au sein d'une région de données, affiche le numéro de ligne de chaque instance de la zone de texte dans laquelle l'expression apparaît.</span><span class="sxs-lookup"><span data-stu-id="3266a-246">The `RowNumber` function, when used in a text box within a data region, displays the row number for each instance of the text box in which the expression appears.</span></span> <span data-ttu-id="3266a-247">Cette fonction peut être utile pour numéroter les lignes dans un tableau.</span><span class="sxs-lookup"><span data-stu-id="3266a-247">This function can be useful to number rows in a table.</span></span> <span data-ttu-id="3266a-248">Elle peut également servir à l'accomplissement de tâches plus complexes, telles que l'insertion de sauts de page en fonction du nombre de lignes.</span><span class="sxs-lookup"><span data-stu-id="3266a-248">It can also be useful for more complex tasks, such as providing page breaks based on number of rows.</span></span> <span data-ttu-id="3266a-249">Pour plus d'informations, consultez [Sauts de page](#PageBreaks) , plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="3266a-249">For more information, see [Page Breaks](#PageBreaks) in this topic.</span></span>  

<span data-ttu-id="3266a-250">L'étendue que vous spécifiez pour `RowNumber` détermine quand commence la renumérotation.</span><span class="sxs-lookup"><span data-stu-id="3266a-250">The scope you specify for `RowNumber` controls when renumbering begins.</span></span> <span data-ttu-id="3266a-251">Le mot clé `Nothing` indique que la fonction démarrera à compter à la première ligne dans la région de données la plus à l'extérieur.</span><span class="sxs-lookup"><span data-stu-id="3266a-251">The `Nothing` keyword indicates that the function will start counting at the first row in the outermost data region.</span></span> <span data-ttu-id="3266a-252">Pour commencer à compter dans des régions de données imbriquées, utilisez le nom de la région de données.</span><span class="sxs-lookup"><span data-stu-id="3266a-252">To start counting within nested data regions, use the name of the data region.</span></span> <span data-ttu-id="3266a-253">Pour commencer à compter dans un groupe, utilisez le nom du groupe.</span><span class="sxs-lookup"><span data-stu-id="3266a-253">To start counting within a group, use the name of the group.</span></span>  

```  
=RowNumber(Nothing)  
```  

##  <a name="appearance-of-report-data"></a><a name="AppearanceofReportData"></a><span data-ttu-id="3266a-254">Apparence des données du rapport</span><span class="sxs-lookup"><span data-stu-id="3266a-254">Appearance of Report Data</span></span>  
<span data-ttu-id="3266a-255">Vous pouvez recourir à des expressions pour intervenir sur la façon dont les données apparaissent sur un rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-255">You can use expressions to manipulate how data appears on a report.</span></span> <span data-ttu-id="3266a-256">Par exemple, vous pouvez afficher les valeurs de deux champs dans une seule zone de texte, afficher des informations sur le rapport ou modifier la façon dont les sauts de page sont insérés dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-256">For example, you can display the values of two fields in a single text box, display information about the report, or affect how page breaks are inserted in the report.</span></span>  

###  <a name="page-headers-and-footers"></a><a name="PageHeadersandFooters"></a><span data-ttu-id="3266a-257">En-têtes et pieds de page</span><span class="sxs-lookup"><span data-stu-id="3266a-257">Page Headers and Footers</span></span>  
<span data-ttu-id="3266a-258">Lors de la conception d'un rapport, vous pouvez choisir d'afficher son nom et les numéros des pages dans le pied de page.</span><span class="sxs-lookup"><span data-stu-id="3266a-258">When designing a report, you may want to display the name of the report and page number in the report footer.</span></span> <span data-ttu-id="3266a-259">Pour ce faire, vous pouvez utiliser les expressions suivantes :</span><span class="sxs-lookup"><span data-stu-id="3266a-259">To do this, you can use the following expressions:</span></span>  

-   <span data-ttu-id="3266a-260">L'expression suivante fournit le nom du rapport ainsi que les date et heure de son exécution.</span><span class="sxs-lookup"><span data-stu-id="3266a-260">The following expression provides the name of the report and the time it was run.</span></span> <span data-ttu-id="3266a-261">Elle peut être placée dans une zone de texte du pied de page du rapport ou dans le corps du rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-261">It can be placed in a text box in the report footer or in the body of the report.</span></span> <span data-ttu-id="3266a-262">Le format des date et heure est déterminé par la chaîne de mise en forme [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] pour la date courte :</span><span class="sxs-lookup"><span data-stu-id="3266a-262">The time is formatted with the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] formatting string for short date:</span></span>  

```  
=Globals.ReportName & ", dated " & Format(Globals.ExecutionTime, "d")  
```  

-   <span data-ttu-id="3266a-263">L'expression ci-dessous, placée dans une zone de texte du pied de page d'un rapport, indique le numéro de la page actuelle ainsi que le nombre total de pages du rapport :</span><span class="sxs-lookup"><span data-stu-id="3266a-263">The following expression, placed in a text box in the footer of a report, provides page number and total pages in the report:</span></span>  

```  
=Globals.PageNumber & " of " & Globals.TotalPages  
```  

<span data-ttu-id="3266a-264">Les exemples suivants décrivent comment afficher la première et la dernière valeur d'une page dans l'en-tête de la page, comme dans le contenu d'un annuaire.</span><span class="sxs-lookup"><span data-stu-id="3266a-264">The following examples describe how to display the first and last values from a page in the page header, similar to what you might find in a directory listing.</span></span> <span data-ttu-id="3266a-265">Cet exemple suppose l'existence d'une région de données qui contient une zone de texte appelée `LastName`.</span><span class="sxs-lookup"><span data-stu-id="3266a-265">The example assumes a data region that contains a text box named `LastName`.</span></span>  

-   <span data-ttu-id="3266a-266">L'expression suivante, placée dans une zone de texte sur la partie gauche de l'en-tête de la page, fournit la première valeur de la zone de texte `LastName` sur la page :</span><span class="sxs-lookup"><span data-stu-id="3266a-266">The following expression, placed in a text box on the left side of the page header, provides the first value of the `LastName` text box on the page:</span></span>  

```  
=First(ReportItems("LastName").Value)  
```  

-   <span data-ttu-id="3266a-267">L'expression suivante, placée dans une zone de texte sur la partie droite de l'en-tête de la page, fournit la dernière valeur de la zone de texte `LastName` sur la page :</span><span class="sxs-lookup"><span data-stu-id="3266a-267">The following expression, placed in a text box on the right side of the page header, provides the last value of the `LastName` text box on the page:</span></span>  

```  
=Last(ReportItems("LastName").Value)  
```  

<span data-ttu-id="3266a-268">L'exemple suivant décrit comment afficher un total pour une page.</span><span class="sxs-lookup"><span data-stu-id="3266a-268">The following example describes how to display a page total.</span></span> <span data-ttu-id="3266a-269">Cet exemple suppose l'existence d'une région de données qui contient une zone de texte appelée `Cost`.</span><span class="sxs-lookup"><span data-stu-id="3266a-269">The example assumes a data region that contains a text box named `Cost`.</span></span>  

-   <span data-ttu-id="3266a-270">L'expression suivante, placée dans l'en-tête ou le pied de page, fournit la somme des valeurs dans la zone de texte `Cost` pour la page :</span><span class="sxs-lookup"><span data-stu-id="3266a-270">The following expression, placed in the page header or footer, provides the sum of the values in the `Cost` text box for the page:</span></span>  

```  
=Sum(ReportItems("Cost").Value)  
```  

> [!NOTE]  
>  <span data-ttu-id="3266a-271">Vous ne pouvez faire référence qu'à un seul élément de rapport par expression dans un en-tête ou un pied de page.</span><span class="sxs-lookup"><span data-stu-id="3266a-271">You can refer to only one report item per expression in a page header or footer.</span></span> <span data-ttu-id="3266a-272">Vous pouvez aussi faire référence au nom de la zone de texte, mais pas à l'expression de données elle-même, dans les expressions d'en-tête et de pied de page.</span><span class="sxs-lookup"><span data-stu-id="3266a-272">Also, you can refer to the text box name, but not the actual data expression within the text box, in page header and footer expressions.</span></span>  

###  <a name="page-breaks"></a><a name="PageBreaks"></a><span data-ttu-id="3266a-273">Sauts de page</span><span class="sxs-lookup"><span data-stu-id="3266a-273">Page Breaks</span></span>  
<span data-ttu-id="3266a-274">Dans certains rapports, vous pouvez souhaiter placer un saut de page à la fin d'un nombre spécifié de lignes à la place, ou en plus, de groupes ou d'éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-274">In some reports, you may want to place a page break at the end of a specified number of rows instead of, or in addition to, on groups or report items.</span></span> <span data-ttu-id="3266a-275">Pour ce faire, créez un groupe qui contient les groupes ou enregistrements de détails qui vous intéressent, ajoutez un saut de page au groupe, puis ajoutez une expression de groupe pour regrouper par un nombre spécifié de lignes.</span><span class="sxs-lookup"><span data-stu-id="3266a-275">To do this, create a group that contains the groups or detail records you want, add a page break to the group, and then add a group expression to group by a specified number of rows.</span></span>  

-   <span data-ttu-id="3266a-276">L'expression suivante, quand elle est placée dans l'expression de groupe, affecte un nombre à chaque ensemble de 25 lignes.</span><span class="sxs-lookup"><span data-stu-id="3266a-276">The following expression, when placed in the group expression, assigns a number to each set of 25 rows.</span></span> <span data-ttu-id="3266a-277">Quand un saut de page est défini pour le groupe, cette expression insère un saut de page toutes les 25 lignes.</span><span class="sxs-lookup"><span data-stu-id="3266a-277">When a page break is defined for the group, this expression results in a page break every 25 rows.</span></span>  

```  
=Ceiling(RowNumber(Nothing)/25)  
```  

<span data-ttu-id="3266a-278">Pour permettre à l'utilisateur de définir une valeur pour le nombre de lignes par page, créez un paramètre nommé `RowsPerPage` et basez l'expression de groupe sur le paramètre, comme le montre l'expression suivante :</span><span class="sxs-lookup"><span data-stu-id="3266a-278">To allow the user to set a value for the number of rows per page, create a parameter named `RowsPerPage` and base the group expression on the parameter, as shown in the following expression:</span></span>  

```  
=Ceiling(RowNumber(Nothing)/Parameters!RowsPerPage.Value)  
```  

<span data-ttu-id="3266a-279">Pour plus d’informations sur la définition de sauts de page pour un groupe, consultez [Ajouter un saut de page &#40;Générateur de rapports et SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-279">For more information about setting page breaks for a group, see [Add a Page Break &#40;Report Builder and SSRS&#41;](add-a-page-break-report-builder-and-ssrs.md).</span></span>  

##  <a name="properties"></a><span data-ttu-id="3266a-280">Propriétés de <a name="Properties"></a></span><span class="sxs-lookup"><span data-stu-id="3266a-280"><a name="Properties"></a> Properties</span></span>  
<span data-ttu-id="3266a-281">Les expressions ne sont pas uniquement utilisées pour afficher des données dans des zones de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-281">Expressions are not only used to display data in text boxes.</span></span> <span data-ttu-id="3266a-282">Elles peuvent également servir à modifier la manière dont les propriétés sont appliquées aux éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-282">They can also be used to change how properties are applied to report items.</span></span> <span data-ttu-id="3266a-283">Vous pouvez modifier les informations de style d'un élément de rapport ou bien modifier sa visibilité.</span><span class="sxs-lookup"><span data-stu-id="3266a-283">You can change style information for a report item, or change its visibility.</span></span>  

###  <a name="formatting"></a><a name="Formatting"></a><span data-ttu-id="3266a-284">Mise en forme</span><span class="sxs-lookup"><span data-stu-id="3266a-284">Formatting</span></span>  

-   <span data-ttu-id="3266a-285">L’expression suivante, quand elle est utilisée dans la propriété Color d’une zone de texte, modifie la couleur du texte en fonction de la valeur du champ `Profit` :</span><span class="sxs-lookup"><span data-stu-id="3266a-285">The following expression, when used in the Color property of a text box, changes the color of the text depending on the value of the `Profit` field:</span></span>  

```  
=Iif(Fields!Profit.Value < 0, "Red", "Black")  
```  

<span data-ttu-id="3266a-286">Vous pouvez également utiliser la variable objet [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]`Me`.</span><span class="sxs-lookup"><span data-stu-id="3266a-286">You can also use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] object variable `Me`.</span></span> <span data-ttu-id="3266a-287">Cette variable constitue un autre moyen de faire référence à la valeur d'une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-287">This variable is another way of referring to the value of a text box.</span></span>  

`=Iif(Me.Value < 0, "Red", "Black")`  

-   <span data-ttu-id="3266a-288">L’expression suivante, quand elle est utilisée dans la propriété BackgroundColor d’un élément de rapport dans une région de données, fait alterner la couleur d’arrière-plan de chaque ligne entre vert pâle et blanc :</span><span class="sxs-lookup"><span data-stu-id="3266a-288">The following expression, when used in the BackgroundColor property of a report item in a data region, alternates the background color of each row between pale green and white:</span></span>  

```  
=Iif(RowNumber(Nothing) Mod 2, "PaleGreen", "White")  
```  

<span data-ttu-id="3266a-289">Si vous utilisez une expression pour une étendue spécifique, vous devrez peut-être indiquer le dataset de la fonction d'agrégation :</span><span class="sxs-lookup"><span data-stu-id="3266a-289">If you are using an expression for a specified scope, you may have to indicate the dataset for the aggregate function:</span></span>  

```  
=Iif(RowNumber("Employees") Mod 2, "PaleGreen", "White")  
```  

> [!NOTE]  
>  <span data-ttu-id="3266a-290">Les couleurs disponibles proviennent de l’énumération [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor.</span><span class="sxs-lookup"><span data-stu-id="3266a-290">Available colors come from the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] KnownColor enumeration.</span></span>  

### <a name="chart-colors"></a><span data-ttu-id="3266a-291">Couleurs du graphique</span><span class="sxs-lookup"><span data-stu-id="3266a-291">Chart Colors</span></span>  
<span data-ttu-id="3266a-292">Pour spécifier les couleurs d'un graphique à base de formes, vous pouvez utiliser du code personnalisé pour contrôler l'ordre dans lequel les couleurs sont mappées aux valeurs de point de données.</span><span class="sxs-lookup"><span data-stu-id="3266a-292">To specify colors for a Shape chart, you can use custom code to control the order that colors are mapped to data point values.</span></span> <span data-ttu-id="3266a-293">Cela vous permet d'utiliser des couleurs cohérentes dans le cadre de plusieurs graphiques possédant les mêmes groupes de catégories.</span><span class="sxs-lookup"><span data-stu-id="3266a-293">This helps you use consistent colors for multiple charts that have the same category groups.</span></span> <span data-ttu-id="3266a-294">Pour plus d’informations, consultez [Spécifier des couleurs cohérentes pour plusieurs graphiques à base de formes &#40;Générateur de rapports et SSRS&#41;](charts-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-294">For more information, see [Specify Consistent Colors across Multiple Shape Charts &#40;Report Builder and SSRS&#41;](charts-report-builder-and-ssrs.md).</span></span>  

###  <a name="visibility"></a><a name="Visibility"></a><span data-ttu-id="3266a-295">Vue</span><span class="sxs-lookup"><span data-stu-id="3266a-295">Visibility</span></span>  
<span data-ttu-id="3266a-296">Vous pouvez également afficher et masquer des éléments dans un rapport en utilisant les propriétés de visibilité de l'élément de rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-296">You can show and hide items in a report using the visibility properties for the report item.</span></span> <span data-ttu-id="3266a-297">Dans une région de données comme un tableau, vous pouvez initialement masquer les lignes de détails en fonction de la valeur d'une expression.</span><span class="sxs-lookup"><span data-stu-id="3266a-297">In a data region such as a table, you can initially hide detail rows based on the value in an expression.</span></span>  

-   <span data-ttu-id="3266a-298">L'expression suivante, lorsqu'elle est utilisée pour la visibilité initiale des lignes de détails dans un groupe, affiche les lignes de détails de toutes les ventes supérieures à 90 pour cent dans le champ `PctQuota` :</span><span class="sxs-lookup"><span data-stu-id="3266a-298">The following expression, when used for initial visibility of detail rows in a group, shows the detail rows for all sales exceeding 90 percent in the `PctQuota` field:</span></span>  

```  
=Iif(Fields!PctQuota.Value>.9, False, True)  
```  

-   <span data-ttu-id="3266a-299">L’expression suivante, quand elle est définie dans la propriété Hidden d’une table, affiche la table uniquement si elle compte plus de 12 lignes :</span><span class="sxs-lookup"><span data-stu-id="3266a-299">The following expression, when set in the Hidden property of a table, shows the table only if it has more than 12 rows:</span></span>  

```  
=IIF(CountRows()>12,false,true)  
```  

-   <span data-ttu-id="3266a-300">L’expression suivante, lorsqu’elle est définie dans la `Hidden` propriété d’une colonne, affiche la colonne uniquement si le champ existe dans le DataSet du rapport après que les données ont été récupérées à partir de la source de données :</span><span class="sxs-lookup"><span data-stu-id="3266a-300">The following expression, when set in the `Hidden` property of a column, shows the column only if the field exists in the report dataset after the data is retrieved from the data source:</span></span>  

```  
=IIF(Fields!Column_1.IsMissing, true, false)  
```  

###  <a name="urls"></a><a name="Hyperlinks"></a><span data-ttu-id="3266a-301">URL</span><span class="sxs-lookup"><span data-stu-id="3266a-301">URLs</span></span>  
<span data-ttu-id="3266a-302">Vous pouvez personnaliser des URL à l'aide de données de rapport, mais aussi contrôler de manière conditionnelle si les URL sont ajoutées en tant qu'action pour une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-302">You can customize URLs by using report data and also conditionally control whether URLs are added as an action for a text box.</span></span>  

-   <span data-ttu-id="3266a-303">L'expression ci-dessous, lorsqu'elle est utilisée en tant qu'action pour une zone de texte, génère une URL personnalisée qui spécifie le champ de dataset `EmployeeID` comme un paramètre d'URL.</span><span class="sxs-lookup"><span data-stu-id="3266a-303">The following expression, when used as an action on a text box, generates a customized URL that specifies the dataset field `EmployeeID` as a URL parameter.</span></span>  

```  
="http://adventure-works/MyInfo?ID=" & Fields!EmployeeID.Value  
```  

<span data-ttu-id="3266a-304">Pour plus d’informations, consultez [Ajouter un lien hypertexte à une URL &#40;Générateur de rapports et SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-304">For more information, see [Add a Hyperlink to a URL &#40;Report Builder and SSRS&#41;](add-a-hyperlink-to-a-url-report-builder-and-ssrs.md).</span></span>  

-   <span data-ttu-id="3266a-305">L'expression ci-dessous contrôle de manière conditionnelle si une URL doit être ajoutée à une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-305">The following expression conditionally controls whether to add a URL in a text box.</span></span> <span data-ttu-id="3266a-306">Cette expression dépend d'un paramètre nommé `IncludeURLs` qui permet à un utilisateur de décider s'il faut inclure des URL actives dans un rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-306">This expression depends on a parameter named `IncludeURLs` that allows a user to decide whether to include active URLs in a report.</span></span> <span data-ttu-id="3266a-307">Cette expression est définie en tant qu'action pour une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-307">This expression is set as an action on a text box.</span></span> <span data-ttu-id="3266a-308">En affectant au paramètre la valeur False, puis en consultant le rapport, vous pouvez exporter le rapport vers Microsoft Excel sans liens hypertexte.</span><span class="sxs-lookup"><span data-stu-id="3266a-308">By setting the parameter to False and then viewing the report, you can export the report Microsoft Excel without hyperlinks.</span></span>  

```  
=IIF(Parameters!IncludeURLs.Value,"http://adventure-works.com/productcatalog",Nothing)  
```  

##  <a name="report-data"></a><a name="ReportData"></a><span data-ttu-id="3266a-309">Données du rapport</span><span class="sxs-lookup"><span data-stu-id="3266a-309">Report Data</span></span>  
<span data-ttu-id="3266a-310">Les expressions peuvent être utilisées pour manipuler les données utilisées dans les rapports.</span><span class="sxs-lookup"><span data-stu-id="3266a-310">Expressions can be used to manipulate the data that is used in the report.</span></span> <span data-ttu-id="3266a-311">Vous pouvez faire référence à des paramètres et à d'autres informations de rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-311">You can refer to parameters and other report information.</span></span> <span data-ttu-id="3266a-312">Vous pouvez même modifier la requête utilisée pour extraire les données du rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-312">You can even change the query that is used to retrieve data for the report.</span></span>  

###  <a name="parameters"></a><a name="Parameters"></a> <span data-ttu-id="3266a-313">Paramètres</span><span class="sxs-lookup"><span data-stu-id="3266a-313">Parameters</span></span>  
<span data-ttu-id="3266a-314">Vous pouvez utiliser des expressions dans un paramètre pour faire varier la valeur par défaut du paramètre.</span><span class="sxs-lookup"><span data-stu-id="3266a-314">You can use expressions in a parameter to vary the default value for the parameter.</span></span> <span data-ttu-id="3266a-315">Par exemple, vous pouvez utiliser un paramètre pour filtrer les données d'un utilisateur en particulier en fonction de l'ID utilisateur utilisé pour exécuter le rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-315">For example, you can use a parameter to filter data to a particular user based on the user ID that is used to run the report.</span></span>  

-   <span data-ttu-id="3266a-316">L'expression ci-dessous, lorsqu'elle est utilisée comme valeur par défaut pour un paramètre, collecte l'ID utilisateur de la personne exécutant le rapport :</span><span class="sxs-lookup"><span data-stu-id="3266a-316">The following expression, when used as the default value for a parameter, collects the user ID of the person running the report:</span></span>  

```  
=User!UserID  
```  

-   <span data-ttu-id="3266a-317">Pour faire référence à un paramètre dans un paramètre de requête, une expression de filtre, une zone de texte ou une autre zone du rapport, utilisez la collection globale `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="3266a-317">To refer to a parameter in a query parameter, filter expression, text box, or other area of the report, use the `Parameters` global collection.</span></span> <span data-ttu-id="3266a-318">Cet exemple suppose que le paramètre est appelé *Department*:</span><span class="sxs-lookup"><span data-stu-id="3266a-318">This example assumes that the parameter is named *Department*:</span></span>  

```  
=Parameters!Department.Value  
```  

-   <span data-ttu-id="3266a-319">Des paramètres peuvent être créés dans un rapport, mais définis comme étant masqués.</span><span class="sxs-lookup"><span data-stu-id="3266a-319">Parameters can be created in a report but set to hidden.</span></span> <span data-ttu-id="3266a-320">Lorsque le rapport s'exécute sur le serveur de rapports, le paramètre n'apparaît pas dans la barre d'outils et le lecteur du rapport ne peut pas modifier la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="3266a-320">When the report runs on the report server, the parameter does not appear in the toolbar and the report reader cannot change the default value.</span></span> <span data-ttu-id="3266a-321">Vous pouvez utiliser un paramètre masqué auquel est affectée une valeur par défaut en tant que constante personnalisée.</span><span class="sxs-lookup"><span data-stu-id="3266a-321">You can use a hidden parameter set to a default value as custom constant.</span></span> <span data-ttu-id="3266a-322">Vous pouvez utiliser cette valeur dans n'importe quelle expression, y compris une expression de champ.</span><span class="sxs-lookup"><span data-stu-id="3266a-322">You can use this value in any expression, including a field expression.</span></span> <span data-ttu-id="3266a-323">L'expression suivante identifie le champ spécifié par la valeur de paramètre par défaut pour le paramètre nommé *ParameterField*:</span><span class="sxs-lookup"><span data-stu-id="3266a-323">The following expression identifies the field specified by the default parameter value for the parameter named *ParameterField*:</span></span>  

```  
=Fields(Parameters!ParameterField.Value).Value  
```  

## <a name="custom-code"></a><a name="CustomCode"></a><span data-ttu-id="3266a-324">Code personnalisé</span><span class="sxs-lookup"><span data-stu-id="3266a-324">Custom Code</span></span>

<span data-ttu-id="3266a-325">L'usage de code personnalisé au sein d'un rapport est possible.</span><span class="sxs-lookup"><span data-stu-id="3266a-325">You can use custom code in a report.</span></span> <span data-ttu-id="3266a-326">Le code personnalisé est soit incorporé au rapport, soit stocké dans un assembly personnalisé utilisé au sein du rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-326">Custom code is either embedded in a report or stored in a custom assembly which is used in the report.</span></span> <span data-ttu-id="3266a-327">Pour plus d’informations sur le code personnalisé, consultez [Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-327">For more information about custom code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  

### <a name="using-group-variables-for-custom-aggregation"></a><span data-ttu-id="3266a-328">Utilisation de variables de groupe pour une agrégation personnalisée</span><span class="sxs-lookup"><span data-stu-id="3266a-328">Using Group Variables for Custom Aggregation</span></span>

<span data-ttu-id="3266a-329">Vous pouvez initialiser la valeur pour une variable de groupe qui est locale à une étendue de groupe particulière, puis inclure une référence à cette variable dans les expressions.</span><span class="sxs-lookup"><span data-stu-id="3266a-329">You can initialize the value for a group variable that is local to a particular group scope and then include a reference to that variable in expressions.</span></span> <span data-ttu-id="3266a-330">L'une des façons d'utiliser une variable de groupe avec du code personnalisé consiste à implémenter un agrégat personnalisé.</span><span class="sxs-lookup"><span data-stu-id="3266a-330">One of the ways that you can use a group variable with custom code is to implement a custom aggregate.</span></span> <span data-ttu-id="3266a-331">Pour plus d'informations, consultez [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714)(en anglais).</span><span class="sxs-lookup"><span data-stu-id="3266a-331">For more information, see [Using Group Variables in Reporting Services 2008 for Custom Aggregation](https://go.microsoft.com/fwlink/?LinkId=128714).</span></span>  

<span data-ttu-id="3266a-332">Pour plus d’informations sur les variables, consultez [Références à des collections de variables de rapport et de groupe &#40;Générateur de rapports et SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="3266a-332">For more information about variables, see [Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](built-in-collections-report-and-group-variables-references-report-builder.md).</span></span>  

## <a name="suppressing-null-or-zero-values-at-run-time"></a><span data-ttu-id="3266a-333">Suppression de valeurs Null ou zéro au moment de l'exécution</span><span class="sxs-lookup"><span data-stu-id="3266a-333">Suppressing Null or Zero Values at Run Time</span></span>

<span data-ttu-id="3266a-334">Certaines valeurs d'une expression peuvent prendre la valeur Null ou une valeur indéfinie au moment du traitement du rapport.</span><span class="sxs-lookup"><span data-stu-id="3266a-334">Some values in an expression can evaluate to null or undefined at report processing time.</span></span> <span data-ttu-id="3266a-335">Des erreurs d’exécution peuvent alors se produire et provoquer l’affichage de **#Erreur** au lieu de l’expression évaluée dans la zone de texte.</span><span class="sxs-lookup"><span data-stu-id="3266a-335">This can create run-time errors that result in **#Error** displaying in the text box instead of the evaluated expression.</span></span> <span data-ttu-id="3266a-336">La fonction `IIF` est particulièrement sensible à ce comportement, car, contrairement à une instruction If-Then-Else, chaque partie de l'instruction `IIF` est évaluée (y compris les appels de fonction) avant d'être passée à la routine de test `true` ou `false`.</span><span class="sxs-lookup"><span data-stu-id="3266a-336">The `IIF` function is particularly sensitive to this behavior because, unlike an If-Then-Else statement, each part of the `IIF` statement is evaluated (including function calls) before being passed to the routine that tests for `true` or `false`.</span></span> <span data-ttu-id="3266a-337">L’instruction `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` génère **#Erreur** dans le rapport rendu si `Fields!Sales.Value` a la valeur NOTHING.</span><span class="sxs-lookup"><span data-stu-id="3266a-337">The statement `=IIF(Fields!Sales.Value is NOTHING, 0, Fields!Sales.Value)` generates **#Error** in the rendered report if `Fields!Sales.Value` is NOTHING.</span></span>  

<span data-ttu-id="3266a-338">Pour éviter de vous trouver dans cette situation, utilisez l'une des stratégies qui suivent :</span><span class="sxs-lookup"><span data-stu-id="3266a-338">To avoid this condition, use one of the following strategies:</span></span>  

-   <span data-ttu-id="3266a-339">Affectez au numérateur la valeur 0 et au dénominateur la valeur 1 si la valeur du champ B est 0 ou indéfinie ; sinon, affectez au numérateur la valeur du champ A et au dénominateur celle du champ B.</span><span class="sxs-lookup"><span data-stu-id="3266a-339">Set the numerator to 0 and the denominator to 1 if the value for field B is 0 or undefined; otherwise, set the numerator to the value for field A and the denominator to the value for field B.</span></span>  

```  
=IIF(Field!B.Value=0, 0, Field!A.Value / IIF(Field!B.Value =0, 1, Field!B.Value))  
```  

-   <span data-ttu-id="3266a-340">Utilisez une fonction de code personnalisé pour retourner la valeur de l'expression.</span><span class="sxs-lookup"><span data-stu-id="3266a-340">Use a custom code function to return the value for the expression.</span></span> <span data-ttu-id="3266a-341">L'exemple ci-dessous retourne la différence, exprimée en pourcentage, entre une valeur actuelle et une valeur précédente.</span><span class="sxs-lookup"><span data-stu-id="3266a-341">The following example returns the percentage difference between a current value and a previous value.</span></span> <span data-ttu-id="3266a-342">Il peut être utilisé pour calculer la différence entre deux valeurs consécutives quelconques et gère le cas limite de la première comparaison (lorsqu'il n'y a aucune valeur précédente) et les cas où la valeur précédente ou la valeur actuelle est `null` (`Nothing` dans [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="3266a-342">This can be used to calculate the difference between any two successive values and it handles the edge case of the first comparison (when there is no previous value) and cases whether either the previous value or the current value is `null` (`Nothing` in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]).</span></span>  

```  
Public Function GetDeltaPercentage(ByVal PreviousValue, ByVal CurrentValue) As Object  
     If IsNothing(PreviousValue) OR IsNothing(CurrentValue) Then  
          Return Nothing  
     Else if PreviousValue = 0 OR CurrentValue = 0 Then  
          Return Nothing  
     Else
          Return (CurrentValue - PreviousValue) / CurrentValue  
     End If  
End Function  
```  

<span data-ttu-id="3266a-343">L’expression suivante montre comment appeler ce code personnalisé à partir d’une zone de texte, pour le conteneur « ColumnGroupByYear » (groupe ou région de données).</span><span class="sxs-lookup"><span data-stu-id="3266a-343">The following expression shows how to call this custom code from a text box, for the "ColumnGroupByYear" container (group or data region).</span></span>  

```  
=Code.GetDeltaPercentage(Previous(Sum(Fields!Sales.Value),"ColumnGroupByYear"), Sum(Fields!Sales.Value))  
```  

<span data-ttu-id="3266a-344">Cela permet d'éviter les exceptions d'exécution.</span><span class="sxs-lookup"><span data-stu-id="3266a-344">This helps to avoid run-time exceptions.</span></span> <span data-ttu-id="3266a-345">Vous pouvez maintenant utiliser une expression comme `=IIF(Me.Value < 0, "red", "black")` dans la propriété de `Color` de la zone de texte pour afficher de manière conditionnelle un texte selon que les valeurs sont supérieures ou inférieures à 0.</span><span class="sxs-lookup"><span data-stu-id="3266a-345">You can now use an expression like `=IIF(Me.Value < 0, "red", "black")` in the `Color` property of the text box to conditionally the display text based on whether the values are greater than or less than 0.</span></span>  

## <a name="see-also"></a><span data-ttu-id="3266a-346">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3266a-346">See Also</span></span>

- [<span data-ttu-id="3266a-347">Exemples d’équations de filtre &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-347">Filter Equation Examples &#40;Report Builder and SSRS&#41;</span></span>](filter-equation-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="3266a-348">Exemples d’expressions de groupe &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-348">Group Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](expression-examples-report-builder-and-ssrs.md)
- [<span data-ttu-id="3266a-349">Utilisation d’expressions dans les rapports &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-349">Expression Uses in Reports &#40;Report Builder and SSRS&#41;</span></span>](expression-uses-in-reports-report-builder-and-ssrs.md)
- [<span data-ttu-id="3266a-350">Expressions &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-350">Expressions &#40;Report Builder and SSRS&#41;</span></span>](expressions-report-builder-and-ssrs.md)
- [<span data-ttu-id="3266a-351">Filtres couramment utilisés &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="3266a-351">Commonly Used Filters &#40;Report Builder and SSRS&#41;</span></span>](commonly-used-filters-report-builder-and-ssrs.md)