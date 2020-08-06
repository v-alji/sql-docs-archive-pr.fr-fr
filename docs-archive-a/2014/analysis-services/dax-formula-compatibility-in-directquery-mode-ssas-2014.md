---
title: Compatibilité des formules DAX en mode DirectQuery (SSAS 2014) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: de83cfa9-9ffe-4e24-9c74-96a3876cb4bd
author: minewiskan
ms.author: owend
ms.openlocfilehash: acaac82d6930787a45281c0e942def8df764f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604268"
---
# <a name="dax-formula-compatibility-in-directquery-mode-ssas-2014"></a><span data-ttu-id="25651-102">Compatibilité des formules DAX en mode DirectQuery (SSAS 2014)</span><span class="sxs-lookup"><span data-stu-id="25651-102">DAX Formula Compatibility in DirectQuery Mode (SSAS 2014)</span></span>
<span data-ttu-id="25651-103">Le langage DAX (Data Analysis expression) peut être utilisé pour créer des mesures et d’autres formules personnalisées à utiliser dans des modèles tabulaires Analysis Services, des [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] modèles de données dans des classeurs Excel et des modèles de données Power bi Desktop.</span><span class="sxs-lookup"><span data-stu-id="25651-103">The Data Analysis Expression language (DAX) can be used to create measures and other custom formulas for use in Analysis Services Tabular models, [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] data models in Excel workbooks, and Power BI Desktop data models.</span></span> <span data-ttu-id="25651-104">Dans la plupart des aspects, les modèles que vous créez dans ces environnements sont identiques et vous pouvez utiliser les mêmes mesures, relations et indicateurs de performance clés, etc. Toutefois, si vous créez un modèle tabulaire Analysis Services et que vous le déployez en mode DirectQuery, certaines restrictions s’appliquent aux formules que vous pouvez utiliser.</span><span class="sxs-lookup"><span data-stu-id="25651-104">In most respects, the models you create in these environments are identical, and you can use the same measures, relationships, and KPIs, etc. However, if you author an Analysis Services Tabular model and deploy it in DirectQuery mode, there are some restrictions on the formulas that you can use.</span></span> <span data-ttu-id="25651-105">Cette rubrique fournit une vue d’ensemble de ces différences, répertorie les fonctions qui ne sont pas prises en charge dans le modèle SQL Server 2014 Analysis Services tabulaires au niveau de compatibilité 1100 ou 1103 et en mode DirectQuery, et répertorie les fonctions prises en charge, mais qui peuvent retourner des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="25651-105">This topic provides an overview of those differences, lists the functions that are not supported in SQL Server 2014 Analysis Services tabulars model at compatibility level 1100 or 1103 and in DirectQuery mode, and lists the functions that are supported but might return different results.</span></span>  
  
<span data-ttu-id="25651-106">Dans cette rubrique, nous utilisons le terme *modèle en mémoire* pour faire référence aux modèles tabulaires, qui sont des données en mémoire cache entièrement hébergées sur un serveur Analysis Services s’exécutant en mode tabulaire.</span><span class="sxs-lookup"><span data-stu-id="25651-106">Within this topic, we use the term *in-memory model* to refer to  Tabular models, which are fully hosted in-memory cached data on an Analysis Services server running in Tabular mode.</span></span> <span data-ttu-id="25651-107">Nous utilisons les *modèles DirectQuery* pour faire référence aux modèles tabulaires qui ont été créés et/ou déployés en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-107">We use *DirectQuery models* to refer to Tabular models that have been authored and/or deployed in DirectQuery mode.</span></span> <span data-ttu-id="25651-108">Pour plus d’informations sur le mode DirectQuery, consultez [mode DirectQuery (SSAS tabulaire)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span><span class="sxs-lookup"><span data-stu-id="25651-108">For information about DirectQuery mode, see [DirectQuery Mode (SSAS Tabular)](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5).</span></span>  
  
  
## <a name="differences-between-in-memory-and-directquery-mode"></a><a name="bkmk_SemanticDifferences"></a><span data-ttu-id="25651-109">Différences entre le mode en mémoire et le mode DirectQuery</span><span class="sxs-lookup"><span data-stu-id="25651-109">Differences between in-memory and DirectQuery mode</span></span>  
<span data-ttu-id="25651-110">Les requêtes sur un modèle déployé en mode DirectQuery peuvent retourner des résultats différents de ceux du même modèle déployé en mode en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-110">Queries on a model deployed in DirectQuery mode can return different results than the same model deployed in in-memory mode.</span></span> <span data-ttu-id="25651-111">En effet, avec DirectQuery, les données sont interrogées directement à partir d’une banque de données relationnelle et les agrégations requises par les formules sont effectuées à l’aide du moteur relationnel approprié, au lieu d’utiliser le moteur d’analyse en mémoire xVelocity (VertiPaq) pour le stockage et le calcul.</span><span class="sxs-lookup"><span data-stu-id="25651-111">This is because with DirectQuery, data is queried directly from a relational data store and aggregations required by formulas are performed using the relevant relational engine, rather than using the xVelocity in-memory analytics engine (VertiPaq) for storage and calculation.</span></span>  
  
<span data-ttu-id="25651-112">Par exemple, il existe des différences dans la façon dont certaines banques de données relationnelles gèrent les valeurs numériques, les dates, les valeurs Null, etc.</span><span class="sxs-lookup"><span data-stu-id="25651-112">For example, there are differences in the way that certain relational data stores handle numeric values, dates, nulls, and so forth.</span></span>  
  
<span data-ttu-id="25651-113">En revanche, le langage DAX est prévu pour émuler le mieux possible le comportement des fonctions dans Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="25651-113">In contrast, the DAX language is intended to emulate as closely as possible the behavior of functions in Microsoft Excel.</span></span> <span data-ttu-id="25651-114">Par exemple, lorsque vous gérez des valeurs Null, des chaînes vides et des valeurs zéro, Excel tente de fournir la meilleure réponse quel que soit le type de données exact, et par conséquent le moteur xVelocity en fait de même.</span><span class="sxs-lookup"><span data-stu-id="25651-114">For example, when handling nulls, empty strings and zero values, Excel attempts to provide the best answer regardless of the precise data type, and therefore the xVelocity engine does the same.</span></span> <span data-ttu-id="25651-115">Toutefois, lorsqu'un modèle tabulaire est déployé en mode DirectQuery et transmet des formules à une source de données relationnelle pour l'évaluation, les données doivent être traitées selon la sémantique de la source de données relationnelle, qui nécessite généralement une gestion distincte des chaînes vides et des valeurs Null.</span><span class="sxs-lookup"><span data-stu-id="25651-115">However, when a tabular model is deployed in DirectQuery mode and passes formulas to a relational data source for evaluation, the data must be handled according to the semantics of the relational data source, which typically require distinct handling of empty strings vs. nulls.</span></span> <span data-ttu-id="25651-116">Pour cette raison, la même formule peut retourner un résultat différent une fois évaluée sur des données en mémoire cache et sur des données extraites seulement de la banque de données relationnelle.</span><span class="sxs-lookup"><span data-stu-id="25651-116">For this reason, the same formula might return a different result when evaluated against cached data and against data returned solely from the relational store.</span></span>  
  
<span data-ttu-id="25651-117">En outre, certaines fonctions ne peuvent pas être utilisées du tout en mode DirectQuery, car le calcul exige que les données du contexte actuel soient envoyées à la source de données relationnelle en tant que paramètre.</span><span class="sxs-lookup"><span data-stu-id="25651-117">Additionally, some functions cannot be used at all in DirectQuery mode because the calculation would require the data in the current context be sent to the relational data source as a parameter.</span></span> <span data-ttu-id="25651-118">Par exemple, les mesures d’un [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] classeur utilisent souvent des fonctions d’intelligence temporelle qui font référence à des plages de dates disponibles dans le classeur.</span><span class="sxs-lookup"><span data-stu-id="25651-118">For example, measures in a [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] workbook often use time-intelligence functions that reference date ranges available within the workbook.</span></span> <span data-ttu-id="25651-119">En général, ces formules ne peuvent pas être utilisées en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-119">Such formulas generally cannot be used in DirectQuery mode.</span></span>  
  
## <a name="semantic-differences"></a><span data-ttu-id="25651-120">Différences sémantiques</span><span class="sxs-lookup"><span data-stu-id="25651-120">Semantic differences</span></span>  
<span data-ttu-id="25651-121">Cette section répertorie les types de différences sémantiques que vous pouvez attendre, et décrit toutes les limitations qui peuvent s'appliquer à l'utilisation des fonctions ou aux résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="25651-121">This section lists the types of semantic differences that you can expect, and describes any limitations that might apply to the usage of functions or to query results.</span></span>  
  
### <a name="comparisons"></a><a name="bkmk_Comparisons"></a><span data-ttu-id="25651-122">Comparaisons</span><span class="sxs-lookup"><span data-stu-id="25651-122">Comparisons</span></span>  
<span data-ttu-id="25651-123">Dans les modèles en mémoire, DAX prend en charge les comparaisons de deux expressions qui se résolvent en valeurs scalaires de types de données différents.</span><span class="sxs-lookup"><span data-stu-id="25651-123">DAX in in-memory models support comparisons of two expressions that resolve to scalar values of different data types.</span></span> <span data-ttu-id="25651-124">Toutefois, les modèles qui sont déployés en mode DirectQuery utilisent les types de données et les opérateurs de comparaison du moteur relationnel, et peuvent donc retourner des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="25651-124">However, models that are deployed in DirectQuery mode use the data types and comparison operators of the relational engine, and therefore might return different results.</span></span>  
  
<span data-ttu-id="25651-125">Les comparaisons suivantes retournent toujours une erreur quand elles sont utilisées dans un calcul sur une source de données de DirectQuery :</span><span class="sxs-lookup"><span data-stu-id="25651-125">The following comparisons will always return an error when used in a calculation on a DirectQuery data source:</span></span>  
  
-   <span data-ttu-id="25651-126">Type de données numérique comparé à tout type de données string</span><span class="sxs-lookup"><span data-stu-id="25651-126">Numeric data type compared to any string data type</span></span>  
  
-   <span data-ttu-id="25651-127">Type de données numérique comparé à une valeur booléenne</span><span class="sxs-lookup"><span data-stu-id="25651-127">Numeric data type compared to a Boolean value</span></span>  
  
-   <span data-ttu-id="25651-128">Tout type de données string comparé à une valeur booléenne</span><span class="sxs-lookup"><span data-stu-id="25651-128">Any string data type compared to a Boolean value</span></span>  
  
<span data-ttu-id="25651-129">DAX est généralement plus indulgent avec les incompatibilités de type de données dans les modèles en mémoire, et tente d’effectuer une conversion de type implicite des valeurs jusqu’à deux fois, comme le décrit cette section.</span><span class="sxs-lookup"><span data-stu-id="25651-129">In general, DAX is more forgiving of data type mismatches in in-memory models and will attempt an implicit cast of values up to two times, as described in this section.</span></span> <span data-ttu-id="25651-130">Toutefois, les formules envoyées à une banque de données relationnelle en mode DirectQuery sont évaluées plus strictement, selon les règles du moteur relationnel, et sont plus susceptibles d'échouer.</span><span class="sxs-lookup"><span data-stu-id="25651-130">However, formulas sent to a relational data store in DirectQuery mode are evaluated more strictly, following the rules of the relational engine, and are more likely to fail.</span></span>  
  
<span data-ttu-id="25651-131">**Comparaisons de chaînes et de nombres**</span><span class="sxs-lookup"><span data-stu-id="25651-131">**Comparisons of strings and numbers**</span></span>  
<span data-ttu-id="25651-132">EXEMPLE : `"2" < 3`</span><span class="sxs-lookup"><span data-stu-id="25651-132">EXAMPLE: `"2" < 3`</span></span>  
  
<span data-ttu-id="25651-133">La formule compare une chaîne de texte à un nombre.</span><span class="sxs-lookup"><span data-stu-id="25651-133">The formula compares a text string to a number.</span></span> <span data-ttu-id="25651-134">L’expression est **true** en mode DirectQuery et dans les modèles en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-134">The expression is **true** in both DirectQuery mode and in-memory models.</span></span>  
  
<span data-ttu-id="25651-135">Dans un modèle en mémoire, le résultat est **true** car les nombres sous forme de chaînes sont implicitement convertis en type de données numérique pour les comparaisons avec d’autres nombres.</span><span class="sxs-lookup"><span data-stu-id="25651-135">In an in-memory model, the result is **true** because numbers as strings are implicitly cast to a numerical data type for comparisons with other numbers.</span></span> <span data-ttu-id="25651-136">SQL effectue aussi un cast implicite des nombres sous forme de texte en nombres afin de les comparer aux types de données numériques.</span><span class="sxs-lookup"><span data-stu-id="25651-136">SQL also implicitly casts text numbers as numbers for comparison to numerical data types.</span></span>  
  
<span data-ttu-id="25651-137">Notez que cela représente un changement de comportement de la première version de [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , qui retourne la **valeur false**, car le texte « 2 » est toujours considéré comme supérieur à n’importe quel nombre.</span><span class="sxs-lookup"><span data-stu-id="25651-137">Note that this represents a change in behavior from the first version of [!INCLUDE[ssGemini](../includes/ssgemini-md.md)], which would return **false**, because the text "2" would always be considered larger than any number.</span></span>  
  
<span data-ttu-id="25651-138">**Comparaison de texte avec une valeur booléenne**</span><span class="sxs-lookup"><span data-stu-id="25651-138">**Comparison of text with Boolean**</span></span>  
<span data-ttu-id="25651-139">EXEMPLE : `"VERDADERO" = TRUE`</span><span class="sxs-lookup"><span data-stu-id="25651-139">EXAMPLE: `"VERDADERO" = TRUE`</span></span>  
  
<span data-ttu-id="25651-140">Cette expression compare une chaîne de texte avec une valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="25651-140">This expression compares a text string with a Boolean value.</span></span> <span data-ttu-id="25651-141">En général, pour les modèles DirectQuery ou en mémoire, la comparaison d'une valeur de chaîne avec une valeur booléenne provoque une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-141">In general, for DirectQuery or In-Memory models, comparing a string value to a Boolean value results in an error.</span></span> <span data-ttu-id="25651-142">Les seules exceptions à cette règle sont quand la chaîne contient le mot **true** ou le mot **false**; si la chaîne contient une de ces valeurs, une conversion en valeur booléenne est effectuée et la comparaison a lieu, donnant le résultat logique.</span><span class="sxs-lookup"><span data-stu-id="25651-142">The only exceptions to the rule are when the string contains the word **true** or the word **false**; if the string contains any of true or false values, a conversion to Boolean is made and the comparison takes place giving the logical result.</span></span>  
  
<span data-ttu-id="25651-143">**Comparaison de valeurs Null**</span><span class="sxs-lookup"><span data-stu-id="25651-143">**Comparison of nulls**</span></span>  
<span data-ttu-id="25651-144">EXEMPLE : `EVALUATE ROW("X", BLANK() = BLANK())`</span><span class="sxs-lookup"><span data-stu-id="25651-144">EXAMPLE: `EVALUATE ROW("X", BLANK() = BLANK())`</span></span>  
  
<span data-ttu-id="25651-145">Cette formule compare l'équivalent SQL d'une valeur Null avec une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="25651-145">This formula compares the SQL equivalent of a null to a null.</span></span> <span data-ttu-id="25651-146">Elle retourne **true** dans les modèles en mémoire et DirectQuery ; un approvisionnement est effectué dans le modèle DirectQuery pour assurer un comportement similaire au modèle en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-146">It returns **true** in in-memory and DirectQuery models; a provision is made in DirectQuery model to guarantee similar behavior to in-memory model.</span></span>  
  
<span data-ttu-id="25651-147">Notez que dans Transact-SQL une valeur Null n'est jamais égale à une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="25651-147">Note that in Transact-SQL, a null is never equal to a null.</span></span> <span data-ttu-id="25651-148">Toutefois, dans DAX, un espace est égal à un autre espace.</span><span class="sxs-lookup"><span data-stu-id="25651-148">However, in DAX, a blank is equal to another blank.</span></span> <span data-ttu-id="25651-149">Ce comportement est le même pour tous les modèles en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-149">This behavior is the same for all in-memory models.</span></span> <span data-ttu-id="25651-150">Il est important de noter que le mode DirectQuery utilise la plupart de la sémantique SQL Server ; mais, dans ce cas il s'en sépare en lui donnant un nouveau comportement dans les comparaisons NULL.</span><span class="sxs-lookup"><span data-stu-id="25651-150">It is important to note that DirectQuery mode uses, most of, the semantics of SQL Server; but, in this case it separates from it giving a new behavior to NULL comparisons.</span></span>  
  
### <a name="casts"></a><a name="bkmk_Casts"></a><span data-ttu-id="25651-151">Casts</span><span class="sxs-lookup"><span data-stu-id="25651-151">Casts</span></span>  
  
<span data-ttu-id="25651-152">Il n'existe aucune fonction cast telle que dans DAX, mais les casts implicites sont effectués dans nombre de comparaisons et d'opérations arithmétiques.</span><span class="sxs-lookup"><span data-stu-id="25651-152">There is no cast function as such in DAX, but implicit casts are performed in many comparison and arithmetic operations.</span></span> <span data-ttu-id="25651-153">La comparaison ou l'opération arithmétique détermine le type de données du résultat.</span><span class="sxs-lookup"><span data-stu-id="25651-153">It is the comparison or arithmetic operation that determines the data type of the result.</span></span> <span data-ttu-id="25651-154">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="25651-154">For example,</span></span>  
  
-   <span data-ttu-id="25651-155">Les valeurs booléennes sont traitées en tant que valeurs numériques dans les opérations arithmétiques, telles que TRUE + 1, ou la fonction MIN appliquée à une colonne de valeurs booléennes.</span><span class="sxs-lookup"><span data-stu-id="25651-155">Boolean values are treated as numeric in arithmetic operations, such as TRUE + 1, or the function MIN applied to a column of Boolean values.</span></span> <span data-ttu-id="25651-156">Une opération NOT retourne également une valeur numérique.</span><span class="sxs-lookup"><span data-stu-id="25651-156">A NOT operation also returns a numeric value.</span></span>  
  
-   <span data-ttu-id="25651-157">Les valeurs booléennes sont toujours traitées comme des valeurs logiques dans les comparaisons et quand elles sont utilisées avec EXACT, AND, OR, &amp;&amp;||.</span><span class="sxs-lookup"><span data-stu-id="25651-157">Boolean values are always treated as logical values in comparisons and when used with EXACT, AND, OR, &amp;&amp;, or ||.</span></span>  
  
<span data-ttu-id="25651-158">**Conversion d'une chaîne en valeur booléenne**</span><span class="sxs-lookup"><span data-stu-id="25651-158">**Cast from string to Boolean**</span></span>  
<span data-ttu-id="25651-159">Dans les modèles en mémoire et DirectQuery, les casts sont autorisés aux valeurs booléennes de ces chaînes uniquement : **""** (chaîne vide), **"true"**, **"false"**; où une chaîne vide est convertie en valeur false.</span><span class="sxs-lookup"><span data-stu-id="25651-159">In in-memory and DirectQuery models, casts are permitted to Boolean values from these strings only: **""** (empty string), **"true"**, **"false"**; where an empty string casts to false value.</span></span>  
  
<span data-ttu-id="25651-160">Les conversions en type de données booléen d'une autre chaîne génèrent une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-160">Casts to the Boolean data type of any other string results in an error.</span></span>  
  
<span data-ttu-id="25651-161">**Conversion d'une chaîne en date/heure**</span><span class="sxs-lookup"><span data-stu-id="25651-161">**Cast from string to date/time**</span></span>  
<span data-ttu-id="25651-162">En mode DirectQuery, les conversions des représentations sous forme de chaîne des dates et heures en valeurs **datetime** réelles se comportent de la même façon que dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25651-162">In DirectQuery mode, casts from string representations of dates and times to actual **datetime** values behave the same way as they do in SQL Server.</span></span>  
  
<span data-ttu-id="25651-163">Pour plus d’informations sur les règles régissant les casts de types de données String en **DateTime** dans [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] les modèles, consultez la [référence de syntaxe DAX](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="25651-163">For information about the rules governing casts from string to **datetime** data types in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, see the [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="25651-164">Les modèles qui utilisent la banque de données en mémoire utilisent une plage plus limitée de formats de texte pour les dates que les formats de chaîne pour les dates prises en charge par SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25651-164">Models that use the in-memory data store support a more limited range of text formats for dates than the string formats for dates that are supported by SQL Server.</span></span> <span data-ttu-id="25651-165">Toutefois, DAX prend en charge les formats de date et d'heure personnalisés.</span><span class="sxs-lookup"><span data-stu-id="25651-165">However, DAX supports custom date and time formats.</span></span>  
  
<span data-ttu-id="25651-166">**Conversion d'une chaîne en d'autres valeurs non booléennes**</span><span class="sxs-lookup"><span data-stu-id="25651-166">**Cast from string to other non Boolean values**</span></span>  
<span data-ttu-id="25651-167">Lors de la conversion de chaînes en valeurs non booléennes, le mode DirectQuery se comporte de la même manière que SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25651-167">When casting from strings to non-Boolean values, DirectQuery mode behaves the same as SQL Server.</span></span> <span data-ttu-id="25651-168">Pour plus d’informations, consultez [CAST et CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span><span class="sxs-lookup"><span data-stu-id="25651-168">For more information, see [CAST and CONVERT (Transact-SQL)](https://msdn.microsoft.com/a87d0850-c670-4720-9ad5-6f5a22343ea8).</span></span>  
  
<span data-ttu-id="25651-169">**Conversion de nombres en chaîne non autorisée**</span><span class="sxs-lookup"><span data-stu-id="25651-169">**Cast from numbers to string not allowed**</span></span>  
<span data-ttu-id="25651-170">EXEMPLE : `CONCATENATE(102,",345")`</span><span class="sxs-lookup"><span data-stu-id="25651-170">EXAMPLE: `CONCATENATE(102,",345")`</span></span>  
  
<span data-ttu-id="25651-171">La conversion de nombres en chaînes n'est pas autorisée dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25651-171">Casting from numbers to strings is not allowed in SQL Server.</span></span>  
  
<span data-ttu-id="25651-172">Cette formule retourne une erreur dans les modèles tabulaires et en mode DirectQuery. Cependant, la formule produit un résultat dans [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25651-172">This formula returns an error in tabular models and in DirectQuery mode; however, the formula produces a result in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)].</span></span>  
  
<span data-ttu-id="25651-173">**Aucune prise en charge de deux tentatives de conversion dans DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="25651-173">**No support for two-try casts in DirectQuery**</span></span>  
<span data-ttu-id="25651-174">Les modèles en mémoire tentent souvent une deuxième conversion lorsque la première échoue.</span><span class="sxs-lookup"><span data-stu-id="25651-174">In-memory models often attempt a second cast when the first one fails.</span></span> <span data-ttu-id="25651-175">Cela ne se produit jamais en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-175">This never happens in DirectQuery mode.</span></span>  
  
<span data-ttu-id="25651-176">EXEMPLE : `TODAY() + "13:14:15"`</span><span class="sxs-lookup"><span data-stu-id="25651-176">EXAMPLE: `TODAY() + "13:14:15"`</span></span>  
  
<span data-ttu-id="25651-177">Dans cette expression, le premier paramètre est de type **datetime** et le deuxième paramètre est de type **string**.</span><span class="sxs-lookup"><span data-stu-id="25651-177">In this expression, the first parameter has type **datetime** and second parameter has type **string**.</span></span> <span data-ttu-id="25651-178">Toutefois, les conversions en combinant les opérandes sont gérées différemment.</span><span class="sxs-lookup"><span data-stu-id="25651-178">However, the casts when combining the operands are handled differently.</span></span> <span data-ttu-id="25651-179">DAX effectue une conversion de type implicite de **string** en **double**.</span><span class="sxs-lookup"><span data-stu-id="25651-179">DAX will perform an implicit cast from **string** to **double**.</span></span> <span data-ttu-id="25651-180">Dans les modèles en mémoire, le moteur de formule tente de convertir le type directement en **double**et, si cette tentative échoue, il essaie de convertir la chaîne en **datetime**.</span><span class="sxs-lookup"><span data-stu-id="25651-180">In in-memory models, the formula engine attempts to cast directly to **double**, and if that fails, it will try to cast the string to **datetime**.</span></span>  
  
<span data-ttu-id="25651-181">En mode DirectQuery, seule la conversion directe de **string** en **double** est appliquée.</span><span class="sxs-lookup"><span data-stu-id="25651-181">In DirectQuery mode, only the direct cast from **string** to **double** will be applied.</span></span> <span data-ttu-id="25651-182">Si cette conversion échoue, la formule retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-182">If this cast fails, the formula will return an error.</span></span>  
  
### <a name="math-functions-and-arithmetic-operations"></a><a name="bkmk_Math"></a><span data-ttu-id="25651-183">Fonctions mathématiques et opérations arithmétiques</span><span class="sxs-lookup"><span data-stu-id="25651-183">Math functions and arithmetic operations</span></span>  
<span data-ttu-id="25651-184">Certaines fonctions mathématiques retournent des résultats différents en mode DirectQuery, en raison de différences dans le type de données sous-jacent ou des conversions qui peuvent être appliquées dans les opérations.</span><span class="sxs-lookup"><span data-stu-id="25651-184">Some mathematical functions will return different results in DirectQuery mode because of differences in the underlying data type or the casts that can be applied in operations.</span></span> <span data-ttu-id="25651-185">En outre, les restrictions décrites ci-dessus relatives à la plage de valeurs autorisée peuvent affecter les résultats des opérations arithmétiques.</span><span class="sxs-lookup"><span data-stu-id="25651-185">Also, the restrictions described above on the allowed range of values might affect the outcome of arithmetic operations.</span></span>  
  
<span data-ttu-id="25651-186">**Ordre d'ajout**</span><span class="sxs-lookup"><span data-stu-id="25651-186">**Order of addition**</span></span>  
<span data-ttu-id="25651-187">Lorsque vous créez une formule qui ajoute une série de nombres, un modèle en mémoire peut traiter les nombres dans un ordre différent de celui d'un modèle DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-187">When you create a formula that adds a series of numbers, an in-memory model might process the numbers in a different order than a DirectQuery model.</span></span>  <span data-ttu-id="25651-188">Par conséquent, lorsque vous avez de très grands nombres positifs et de très grands nombres négatifs, vous pouvez obtenir une erreur dans une opération et des résultats dans une autre opération.</span><span class="sxs-lookup"><span data-stu-id="25651-188">Therefore, when you have many very large positive numbers and very large negative numbers, you may get an error in one operation and results in another operation.</span></span>  
  
<span data-ttu-id="25651-189">**Utilisation de la fonction POWER**</span><span class="sxs-lookup"><span data-stu-id="25651-189">**Use of the POWER function**</span></span>  
<span data-ttu-id="25651-190">EXEMPLE : `POWER(-64, 1/3)`</span><span class="sxs-lookup"><span data-stu-id="25651-190">EXAMPLE: `POWER(-64, 1/3)`</span></span>  
  
<span data-ttu-id="25651-191">En mode DirectQuery, la fonction POWER ne peut pas utiliser de valeurs négatives comme base une fois élevée à un exposant fractionnaire.</span><span class="sxs-lookup"><span data-stu-id="25651-191">In DirectQuery mode, the POWER function cannot use negative values as the base when raised to a fractional exponent.</span></span> <span data-ttu-id="25651-192">Il s'agit du comportement attendu dans SQL Server.</span><span class="sxs-lookup"><span data-stu-id="25651-192">This is the expected behavior in SQL Server.</span></span>  
  
<span data-ttu-id="25651-193">Dans un modèle en mémoire, la formule retourne -4.</span><span class="sxs-lookup"><span data-stu-id="25651-193">In an in-memory model, the formula returns -4.</span></span>  
  
<span data-ttu-id="25651-194">**Opérations numériques de dépassement de capacité**</span><span class="sxs-lookup"><span data-stu-id="25651-194">**Numerical overflow operations**</span></span>  
<span data-ttu-id="25651-195">Dans Transact-SQL, les opérations qui génèrent un dépassement de capacité numérique génèrent une erreur de dépassement de capacité ; par conséquent, les formules qui génèrent un dépassement de capacité génèrent également une erreur en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-195">In Transact-SQL, operations that result in a numerical overflow return an overflow error; therefore, formulas that result in an overflow also raise an error in DirectQuery mode.</span></span>  
  
<span data-ttu-id="25651-196">Toutefois, la même formule utilisée dans un modèle en mémoire retourne un entier sur huit octets.</span><span class="sxs-lookup"><span data-stu-id="25651-196">However, the same formula when used in an in-memory model returns an eight-byte integer.</span></span> <span data-ttu-id="25651-197">Cela est dû au fait que le moteur de formule ne recherche pas les dépassements de capacité numériques.</span><span class="sxs-lookup"><span data-stu-id="25651-197">That is because the formula engine does not perform checks for numerical overflows.</span></span>  
  
<span data-ttu-id="25651-198">**Les fonctions LOG avec des espaces retournent des résultats différents**</span><span class="sxs-lookup"><span data-stu-id="25651-198">**LOG functions with blanks return different results**</span></span>  
<span data-ttu-id="25651-199">SQL Server gère les valeurs Null et les espaces différemment du moteur xVelocity.</span><span class="sxs-lookup"><span data-stu-id="25651-199">SQL Server handles nulls and blanks differently than the xVelocity engine.</span></span> <span data-ttu-id="25651-200">Par conséquent, la formule suivante retourne une erreur en mode DirectQuery, mais retourne Infinity (-INF) en mode in-Memory.</span><span class="sxs-lookup"><span data-stu-id="25651-200">As a result, the following formula returns an error in DirectQuery mode, but return infinity (-inf) in in-memory mode.</span></span>  
  
`EXAMPLE: LOG(blank())`  
  
<span data-ttu-id="25651-201">Les mêmes limitations s'appliquent aux autres fonctions logarithmiques : LOG10 et LN.</span><span class="sxs-lookup"><span data-stu-id="25651-201">The same limitations apply to the other logarithmic functions: LOG10 and LN.</span></span>  
  
<span data-ttu-id="25651-202">Pour plus d’informations sur le type de données **blank** dans DAX, consultez [Spécification de syntaxe DAX pour PowerPivot](/dax/dax-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="25651-202">For more information about the **blank** data type in DAX, see [DAX Syntax Reference](/dax/dax-syntax-reference).</span></span>
  
<span data-ttu-id="25651-203">**Division par 0 et division par un espace**</span><span class="sxs-lookup"><span data-stu-id="25651-203">**Division by 0 and division by Blank**</span></span>  
<span data-ttu-id="25651-204">En mode DirectQuery, la division par zéro (0) ou la division par BLANK aura toujours pour résultat une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-204">In DirectQuery mode, division by zero (0) or division by BLANK will always result in an error.</span></span> <span data-ttu-id="25651-205">SQL Server ne prend pas en charge la notion d'infini, et comme le résultat naturel de toute division par 0 est l'infini, le résultat est une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-205">SQL Server does not support the notion of infinity, and because the natural result of any division by 0 is infinity, the result is an error.</span></span> <span data-ttu-id="25651-206">Toutefois, SQL Server prend en charge la division par des valeurs Null, et le résultat doit toujours être égal à une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="25651-206">However, SQL Server supports division by nulls, and the result must always equal null.</span></span>  
  
<span data-ttu-id="25651-207">Plutôt que de retourner des résultats différents pour ces opérations, en mode DirectQuery, les deux types d'opérations (division par zéro et division par une valeur Null) retournent une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-207">Rather than return different results for these operations, in DirectQuery mode, both types of operations (division by zero and division by null) return an error.</span></span>  
  
<span data-ttu-id="25651-208">Notez que dans Excel et dans les modèles [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] , la division par zéro retourne également une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-208">Note that, in Excel and in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] models, division by zero also returns an error.</span></span> <span data-ttu-id="25651-209">La division par un espace retourne un espace.</span><span class="sxs-lookup"><span data-stu-id="25651-209">Division by a blank returns a blank.</span></span>  
  
<span data-ttu-id="25651-210">Les expressions suivantes sont toutes valides dans les modèles en mémoire, mais échouent en mode DirectQuery :</span><span class="sxs-lookup"><span data-stu-id="25651-210">The following expressions are all valid in in-memory models, but will fail in DirectQuery mode:</span></span>  
  
`1/BLANK`  
  
`1/0`  
  
`0.0/BLANK`  
  
`0/0`  
  
<span data-ttu-id="25651-211">L'expression `BLANK/BLANK` est un cas spécial qui retourne `BLANK` dans les modèles en mémoire et en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-211">The expression `BLANK/BLANK` is a special case that returns `BLANK` in both for in-memory models, and in DirectQuery mode.</span></span>  
  
### <a name="supported-numeric-and-date-time-ranges"></a><a name="bkmk_Ranges"></a><span data-ttu-id="25651-212">Plages numériques et de date/heure prises en charge</span><span class="sxs-lookup"><span data-stu-id="25651-212">Supported numeric and date-time ranges</span></span>  
<span data-ttu-id="25651-213">Les formules dans [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] les modèles tabulaires et en mémoire sont soumises aux mêmes limitations qu’Excel en ce qui concerne les valeurs maximales autorisées pour les nombres réels et les dates.</span><span class="sxs-lookup"><span data-stu-id="25651-213">Formulas in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and tabular models in-memory are subject to the same limitations as Excel with regard to maximum allowed values for real numbers and dates.</span></span> <span data-ttu-id="25651-214">Toutefois, des différences peuvent survenir lorsque la valeur maximale est retournée à partir d'un calcul ou d'une requête, ou lorsque les valeurs sont converties, castées, arrondies ou tronquées.</span><span class="sxs-lookup"><span data-stu-id="25651-214">However, differences can arise when the maximum value is returned from a calculation or query, or when values are converted, cast, rounded, or truncated.</span></span>  
  
-   <span data-ttu-id="25651-215">Si des valeurs des types **Currency** et **Real** sont multipliées, et que le résultat est supérieur à la valeur maximale possible, en mode DirectQuery, aucune erreur n’est générée et une valeur Null est retournée.</span><span class="sxs-lookup"><span data-stu-id="25651-215">If values of types **Currency** and **Real** are multiplied, and the result is larger than the maximum possible value, in DirectQuery mode, no error is raised, and a null is returned.</span></span>  
  
-   <span data-ttu-id="25651-216">Dans les modèles en mémoire, aucune erreur n'est générée, mais la valeur maximale est retournée.</span><span class="sxs-lookup"><span data-stu-id="25651-216">In in-memory models, no error is raised, but the maximum value is returned.</span></span>  
  
<span data-ttu-id="25651-217">En général, étant donné que les plages de dates acceptées sont différentes pour Excel et SQL Server, les résultats peuvent être garantis pour correspondre uniquement lorsque les dates sont dans la plage de dates commune, qui compris les dates suivantes :</span><span class="sxs-lookup"><span data-stu-id="25651-217">In general, because the accepted date ranges are different for Excel and SQL Server, results can be guaranteed to match only when dates are within the common date range, which is inclusive of the following dates:</span></span>  
  
-   <span data-ttu-id="25651-218">Première date : 1er mars 1990</span><span class="sxs-lookup"><span data-stu-id="25651-218">Earliest date: March 1, 1990</span></span>  
  
-   <span data-ttu-id="25651-219">Dernière date : 31 décembre 9999</span><span class="sxs-lookup"><span data-stu-id="25651-219">Latest date: December 31, 9999</span></span>  
  
<span data-ttu-id="25651-220">Si les dates utilisées dans les formules n'appartiennent pas à cette plage, la formule génère une erreur ou les résultats ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="25651-220">If any dates used in formulas fall outside this range, either the formula will result in an error, or the results will not match.</span></span>  
  
<span data-ttu-id="25651-221">**Valeurs à virgule flottante prises en charge par CEILING**</span><span class="sxs-lookup"><span data-stu-id="25651-221">**Floating point values supported by CEILING**</span></span>  
<span data-ttu-id="25651-222">EXEMPLE : `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span><span class="sxs-lookup"><span data-stu-id="25651-222">EXAMPLE: `EVALUATE ROW("x", CEILING(-4.398488E+30, 1))`</span></span>  
  
<span data-ttu-id="25651-223">L'équivalent Transact-SQL de la fonction DAX CEILING prend uniquement en charge les valeurs avec une grandeur de 10^19 ou inférieure.</span><span class="sxs-lookup"><span data-stu-id="25651-223">The Transact-SQL equivalent of the DAX CEILING function only supports values with magnitude of 10^19 or less.</span></span> <span data-ttu-id="25651-224">Une règle empirique consiste à utiliser des valeurs en virgule flottante pour le type **bigint**.</span><span class="sxs-lookup"><span data-stu-id="25651-224">A rule of thumb is that floating point values should be able to fit into **bigint**.</span></span>  
  
<span data-ttu-id="25651-225">**Datepart fonctionne avec des dates qui sont hors limites**</span><span class="sxs-lookup"><span data-stu-id="25651-225">**Datepart functions with dates that are out of range**</span></span>  
<span data-ttu-id="25651-226">Les résultats en mode DirectQuery sont garantis pour correspondre à ceux des modèles en mémoire uniquement lorsque la date utilisée comme argument se trouve dans la plage de dates valide.</span><span class="sxs-lookup"><span data-stu-id="25651-226">Results in DirectQuery mode are guaranteed to match those in in-memory models only when the date used as the argument is in the valid date range.</span></span> <span data-ttu-id="25651-227">Si ces conditions ne sont pas satisfaites, une erreur est générée, ou la formule retourne des résultats différents dans DirectQuery et dans le mode en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-227">If these conditions are not satisfied, either an error will be raised, or the formula will return different results in DirectQuery than in in-memory mode.</span></span>  
  
<span data-ttu-id="25651-228">EXEMPLE : `MONTH(0)` ou `YEAR(0)`</span><span class="sxs-lookup"><span data-stu-id="25651-228">EXAMPLE: `MONTH(0)` or `YEAR(0)`</span></span>  
  
<span data-ttu-id="25651-229">En mode DirectQuery, les expressions retournent 12 et 1899, respectivement.</span><span class="sxs-lookup"><span data-stu-id="25651-229">In DirectQuery mode, the expressions return 12 and 1899, respectively.</span></span>  
  
<span data-ttu-id="25651-230">Dans les modèles en mémoire, les expressions retournent 1 et 1900, respectivement.</span><span class="sxs-lookup"><span data-stu-id="25651-230">In in-memory models, the expressions return 1 and 1900, respectively.</span></span>  
  
<span data-ttu-id="25651-231">EXEMPLE :  `EOMONTH(0.0001, 1)`</span><span class="sxs-lookup"><span data-stu-id="25651-231">EXAMPLE:  `EOMONTH(0.0001, 1)`</span></span>  
  
<span data-ttu-id="25651-232">Les résultats de cette expression ne correspondent que lorsque les données fournies comme paramètre se trouvent dans la plage de dates valide.</span><span class="sxs-lookup"><span data-stu-id="25651-232">The results of this expression will match only when the data supplied as a parameter is within the valid date range.</span></span>  
  
<span data-ttu-id="25651-233">EXEMPLE : `EOMONTH(blank(), blank())` ou `EDATE(blank(), blank())`</span><span class="sxs-lookup"><span data-stu-id="25651-233">EXAMPLE: `EOMONTH(blank(), blank())` or `EDATE(blank(), blank())`</span></span>  
  
<span data-ttu-id="25651-234">Les résultats de cette expression doivent être identiques en mode DirectQuery et en mode en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-234">The results of this expression should be the same in DirectQuery mode and in-memory mode.</span></span>  
  
<span data-ttu-id="25651-235">**Troncation des valeurs d'heure**</span><span class="sxs-lookup"><span data-stu-id="25651-235">**Truncation of time values**</span></span>  
<span data-ttu-id="25651-236">EXEMPLE : `SECOND(1231.04097222222)`</span><span class="sxs-lookup"><span data-stu-id="25651-236">EXAMPLE: `SECOND(1231.04097222222)`</span></span>  
  
<span data-ttu-id="25651-237">En mode DirectQuery, le résultat est tronqué, selon les règles de SQL Server, et l'expression renvoie la valeur 59.</span><span class="sxs-lookup"><span data-stu-id="25651-237">In DirectQuery mode, the result is truncated, following the rules of SQL Server, and the expression evaluates to 59.</span></span>  
  
<span data-ttu-id="25651-238">Dans les modèles en mémoire, les résultats de chaque opération temporaire sont arrondis ; par conséquent, l'expression renvoie la valeur 0.</span><span class="sxs-lookup"><span data-stu-id="25651-238">In in-memory models, the results of each interim operation are rounded; therefore, the expression evaluates to 0.</span></span>  
  
<span data-ttu-id="25651-239">L'exemple suivant montre comment cette valeur est calculée :</span><span class="sxs-lookup"><span data-stu-id="25651-239">The following example demonstrates how this value is calculated:</span></span>  
  
1.  <span data-ttu-id="25651-240">La fraction de l'entrée (0,04097222222) est multipliée par 24.</span><span class="sxs-lookup"><span data-stu-id="25651-240">The fraction of the input (0.04097222222) is multiplied by 24.</span></span>  
  
2.  <span data-ttu-id="25651-241">La valeur d'heure obtenue (0,98333333328) est multipliée par 60.</span><span class="sxs-lookup"><span data-stu-id="25651-241">The resulting hour value (0.98333333328) is multiplied by 60.</span></span>  
  
3.  <span data-ttu-id="25651-242">La valeur de minute obtenue est 58,9999999968.</span><span class="sxs-lookup"><span data-stu-id="25651-242">The resulting minute value is 58.9999999968.</span></span>  
  
4.  <span data-ttu-id="25651-243">La fraction de la valeur de minute (0,9999999968) est multipliée par 60.</span><span class="sxs-lookup"><span data-stu-id="25651-243">The fraction of the minute value (0.9999999968) is multiplied by 60.</span></span>  
  
5.  <span data-ttu-id="25651-244">La valeur de seconde obtenue (59,999999808) est arrondie au chiffre supérieur (60).</span><span class="sxs-lookup"><span data-stu-id="25651-244">The resulting second value (59.999999808) rounds up to 60.</span></span>  
  
6.  <span data-ttu-id="25651-245">60 correspond à 0.</span><span class="sxs-lookup"><span data-stu-id="25651-245">60 is equivalent to 0.</span></span>  
  
<span data-ttu-id="25651-246">**Type de données d'heure SQL non pris en charge**</span><span class="sxs-lookup"><span data-stu-id="25651-246">**SQL Time data type not supported**</span></span>  
<span data-ttu-id="25651-247">Les modèles en mémoire ne prennent pas en charge l’utilisation du nouveau type de données SQL **Time** .</span><span class="sxs-lookup"><span data-stu-id="25651-247">In-memory models do not support use of the new SQL **Time** data type.</span></span> <span data-ttu-id="25651-248">En mode DirectQuery, les formules qui référencent les colonnes de ce type de données retournent une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-248">In DirectQuery mode, formulas that reference columns with this data type will return an error.</span></span> <span data-ttu-id="25651-249">Les colonnes de données d'heure ne peuvent pas être importées dans un modèle en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-249">Time data columns cannot be imported into an in-memory model.</span></span>  
  
<span data-ttu-id="25651-250">Toutefois, dans [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] et dans les modèles mis en cache, parfois le moteur convertit la valeur d’heure en un type de données acceptable, et la formule retourne un résultat.</span><span class="sxs-lookup"><span data-stu-id="25651-250">However, in [!INCLUDE[ssGemini](../includes/ssgemini-md.md)] and in cached models, sometimes the engine casts the time value to an acceptable data type, and the formula returns a result.</span></span>  
  
<span data-ttu-id="25651-251">Ce comportement affecte toutes les fonctions qui utilisent une colonne de date comme paramètre.</span><span class="sxs-lookup"><span data-stu-id="25651-251">This behavior affects all functions that use a date column as a parameter.</span></span>  
  
### <a name="currency"></a><a name="bkmk_Currency"></a><span data-ttu-id="25651-252">Accès</span><span class="sxs-lookup"><span data-stu-id="25651-252">Currency</span></span>  
<span data-ttu-id="25651-253">En mode DirectQuery, si le résultat d’une opération arithmétique est de type **Currency**, la valeur doit être dans la plage suivante :</span><span class="sxs-lookup"><span data-stu-id="25651-253">In DirectQuery mode, if the result of an arithmetic operation has the type **Currency**, the value must be within the following range:</span></span>  
  
-   <span data-ttu-id="25651-254">Minimum : -922337203685477,5808</span><span class="sxs-lookup"><span data-stu-id="25651-254">Minimum: -922337203685477.5808</span></span>  
  
-   <span data-ttu-id="25651-255">Maximum : 922337203685477,5807</span><span class="sxs-lookup"><span data-stu-id="25651-255">Maximum: 922337203685477.5807</span></span>  
  
<span data-ttu-id="25651-256">**Combinaison de types de données Currency et REAL**</span><span class="sxs-lookup"><span data-stu-id="25651-256">**Combining currency and REAL data types**</span></span>  
<span data-ttu-id="25651-257">EXEMPLE : `Currency sample 1`</span><span class="sxs-lookup"><span data-stu-id="25651-257">EXAMPLE: `Currency sample 1`</span></span>  
  
<span data-ttu-id="25651-258">Si des types **Currency** et **Real** sont multipliés et que le résultat est supérieur à 9223372036854774784 (0x7ffffffffffffc00), le mode DirectQuery ne génère pas d’erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-258">If **Currency** and **Real** types are multiplied, and the result is larger than 9223372036854774784 (0x7ffffffffffffc00), DirectQuery mode will not raise an error.</span></span>  
  
<span data-ttu-id="25651-259">Dans un modèle en mémoire, une erreur est générée si la valeur absolue du résultat est supérieure à 922337203685477,4784.</span><span class="sxs-lookup"><span data-stu-id="25651-259">In an in-memory model, an error is raised if the absolute value of the result is larger than 922337203685477.4784.</span></span>  
  
<span data-ttu-id="25651-260">**L'opération génère une valeur hors limites**</span><span class="sxs-lookup"><span data-stu-id="25651-260">**Operation results in an out-of-range value**</span></span>  
<span data-ttu-id="25651-261">EXEMPLE : `Currency sample 2`</span><span class="sxs-lookup"><span data-stu-id="25651-261">EXAMPLE: `Currency sample 2`</span></span>  
  
<span data-ttu-id="25651-262">Si des opérations sur deux valeurs monétaires quelconques génèrent une valeur qui est en dehors de la plage spécifiée, une erreur est générée dans les modèles en mémoire, mais pas dans les modèles DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-262">If operations on any two currency values result in a value that is outside the specified range, an error is raised in in-memory models, but not in DirectQuery models.</span></span>  
  
<span data-ttu-id="25651-263">**Combinaison du type de données Currency avec d'autres types de données**</span><span class="sxs-lookup"><span data-stu-id="25651-263">**Combining currency with other data types**</span></span>  
<span data-ttu-id="25651-264">La division de valeurs monétaires par des valeurs d'autres types numériques peut entraîner des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="25651-264">Division of currency values by values of other numeric types can result in different results.</span></span>  
  
### <a name="aggregation-functions"></a><a name="bkmk_Aggregations"></a><span data-ttu-id="25651-265">Fonctions d’agrégation</span><span class="sxs-lookup"><span data-stu-id="25651-265">Aggregation functions</span></span>  
<span data-ttu-id="25651-266">Les fonctions statistiques sur une table avec une ligne retournent des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="25651-266">Statistical functions on a table with one row return different results.</span></span> <span data-ttu-id="25651-267">Les fonctions d'agrégation sur les tables vides se comportent différemment dans les modèles en mémoire et en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-267">Aggregation functions over empty tables also behave differently in in-memory models than they do in DirectQuery mode.</span></span>  
  
<span data-ttu-id="25651-268">**Fonctions statistiques sur une table avec une seule ligne**</span><span class="sxs-lookup"><span data-stu-id="25651-268">**Statistical functions over a table with a single row**</span></span>  
<span data-ttu-id="25651-269">Si la table utilisée comme argument contient une seule ligne, en mode DirectQuery, les fonctions statistiques telles STDEV et VAR retournent une valeur Null.</span><span class="sxs-lookup"><span data-stu-id="25651-269">If the table that is used as argument contains a single row, in DirectQuery mode, statistical functions such as STDEV and VAR return null.</span></span>  
  
<span data-ttu-id="25651-270">Dans un modèle en mémoire, une formule qui utilise STDEV ou VAR sur une table avec une seule ligne retourne une erreur de division par zéro.</span><span class="sxs-lookup"><span data-stu-id="25651-270">In an in-memory model, a formula that uses STDEV or VAR over a table with a single row returns a division by zero error.</span></span>  
  
### <a name="text-functions"></a><a name="bkmk_Text"></a><span data-ttu-id="25651-271">Fonctions de texte</span><span class="sxs-lookup"><span data-stu-id="25651-271">Text functions</span></span>  
<span data-ttu-id="25651-272">Étant donné que les banques de données relationnelles fournissent différents types de données texte par rapport à Excel, vous pouvez voir des résultats différents lors de la recherche de chaînes ou lorsque vous utilisez des sous-chaînes.</span><span class="sxs-lookup"><span data-stu-id="25651-272">Because relational data stores provide different text data types than does Excel, you may see different results when searching strings or working with substrings.</span></span> <span data-ttu-id="25651-273">La longueur des chaînes peut également être différente.</span><span class="sxs-lookup"><span data-stu-id="25651-273">The length of strings also can be different.</span></span>  
  
<span data-ttu-id="25651-274">En général toutes les fonctions de manipulation de chaînes qui utilisent des colonnes de taille fixe comme arguments peuvent avoir des résultats différents.</span><span class="sxs-lookup"><span data-stu-id="25651-274">In general, any string manipulation functions that use fixed-size columns as arguments can have different results.</span></span>  
  
<span data-ttu-id="25651-275">De plus, dans SQL Server, certaines fonctions de texte prennent en charge des arguments supplémentaires qui ne sont pas fournis dans Excel.</span><span class="sxs-lookup"><span data-stu-id="25651-275">Additionally, in SQL Server, some text functions support additional arguments that are not provided in Excel.</span></span> <span data-ttu-id="25651-276">Si la formule requiert l'argument manquant vous pouvez obtenir des résultats différents ou des erreurs dans le modèle en mémoire.</span><span class="sxs-lookup"><span data-stu-id="25651-276">If the formula requires the missing argument you can get different results or errors in the in-memory model.</span></span>  
  
<span data-ttu-id="25651-277">**Les opérations qui retournent un caractère en utilisant LEFT, RIGHT, etc., peuvent retourner le caractère correct mais avec une casse différente, ou aucun résultat**</span><span class="sxs-lookup"><span data-stu-id="25651-277">**Operations that return a character using LEFT, RIGHT, etc. may return the correct character but in a different case, or no results**</span></span>  
<span data-ttu-id="25651-278">EXEMPLE : `LEFT(["text"], 2)`</span><span class="sxs-lookup"><span data-stu-id="25651-278">EXAMPLE: `LEFT(["text"], 2)`</span></span>  
  
<span data-ttu-id="25651-279">En mode DirectQuery, la casse du caractère qui est retourné est toujours exactement la même que celle de la lettre stockée dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="25651-279">In DirectQuery mode, the case of the character that is returned is always exactly the same as the letter that is stored in the database.</span></span> <span data-ttu-id="25651-280">Toutefois, le moteur xVelocity utilise un algorithme différent pour la compression et l'indexation des valeurs, afin d'améliorer les performances.</span><span class="sxs-lookup"><span data-stu-id="25651-280">However, the xVelocity engine uses a different algorithm for compression and indexing of values, to improve performance.</span></span>  
  
<span data-ttu-id="25651-281">Par défaut, le classement Latin1_General est utilisé, qui ne respecte pas la casse mais les accents.</span><span class="sxs-lookup"><span data-stu-id="25651-281">By default, the Latin1_General collation is used, which is case-insensitive but accent-sensitive.</span></span> <span data-ttu-id="25651-282">Par conséquent, s'il existe plusieurs instances d'une chaîne de texte en minuscules, majuscules, ou casse mixte, toutes les instances sont considérées comme la même chaîne, et seule la première instance de la chaîne est stockée dans l'index.</span><span class="sxs-lookup"><span data-stu-id="25651-282">Therefore, if there are multiple instances of a text string in lower case, upper case, or mixed case, all instances are considered the same string, and only the first instance of the string is stored in the index.</span></span> <span data-ttu-id="25651-283">Toutes les fonctions de texte exécutées sur les chaînes stockées récupèrent la partie spécifiée du formulaire indexé.</span><span class="sxs-lookup"><span data-stu-id="25651-283">All text functions that operate on stored strings will retrieve the specified portion of the indexed form.</span></span> <span data-ttu-id="25651-284">Par conséquent, l'exemple de formule retourne la même valeur pour la colonne entière, à l'aide de la première instance comme entrée.</span><span class="sxs-lookup"><span data-stu-id="25651-284">Therefore, the example formula would return the same value for the entire column, using the first instance as the input.</span></span>  
  
[<span data-ttu-id="25651-285">Stockage de chaîne et classement dans les modèles tabulaires</span><span class="sxs-lookup"><span data-stu-id="25651-285">String Storage and Collation in Tabular Models</span></span>](https://msdn.microsoft.com/8516f0ad-32ee-4688-a304-e705143642ca)  
  
<span data-ttu-id="25651-286">Ce comportement s'applique également aux autres fonctions de texte, notamment RIGHT, MID, etc.</span><span class="sxs-lookup"><span data-stu-id="25651-286">This behavior also applies to other text functions, including RIGHT, MID, and so forth.</span></span>  
  
<span data-ttu-id="25651-287">**La longueur de chaîne affecte les résultats**</span><span class="sxs-lookup"><span data-stu-id="25651-287">**String length affects results**</span></span>  
<span data-ttu-id="25651-288">EXEMPLE : `SEARCH("within string", "sample target  text", 1, 1)`</span><span class="sxs-lookup"><span data-stu-id="25651-288">EXAMPLE: `SEARCH("within string", "sample target  text", 1, 1)`</span></span>  
  
<span data-ttu-id="25651-289">Si vous recherchez une chaîne à l'aide de la fonction SEARCH, et la chaîne cible est plus longue que la chaîne, le mode DirectQuery génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="25651-289">If you search for a string using the SEARCH function, and the target string is longer than the within string, DirectQuery mode raises an error.</span></span>  
  
<span data-ttu-id="25651-290">Dans un modèle en mémoire, la chaîne recherchée est retournée, mais sa longueur est tronquée à la longueur du &lt;texte où se fait la recherche&gt;.</span><span class="sxs-lookup"><span data-stu-id="25651-290">In an in-memory model, the searched string is returned, but with its length truncated to the length of &lt;within text&gt;.</span></span>  
  
<span data-ttu-id="25651-291">EXEMPLE : `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span><span class="sxs-lookup"><span data-stu-id="25651-291">EXAMPLE: `EVALUATE ROW("X", REPLACE("CA", 3, 2, "California") )`</span></span>  
  
<span data-ttu-id="25651-292">Si la longueur de la chaîne de remplacement est supérieure à la longueur de la chaîne d'origine, en mode DirectQuery, la formule retourne la valeur Null.</span><span class="sxs-lookup"><span data-stu-id="25651-292">If the length of the replacement string is greater than the length of the original string, in DirectQuery mode, the formula returns null.</span></span>  
  
<span data-ttu-id="25651-293">Dans les modèles en mémoire, la formule suit le comportement d'Excel, qui concatène la chaîne source et la chaîne de remplacement, qui retourne CACalifornia.</span><span class="sxs-lookup"><span data-stu-id="25651-293">In in-memory models, the formula follows the behavior of Excel, which concatenates the source string and the replacement string, which returns CACalifornia.</span></span>  
  
<span data-ttu-id="25651-294">**TRIM implicite au milieu de chaînes**</span><span class="sxs-lookup"><span data-stu-id="25651-294">**Implicit TRIM in the middle of strings**</span></span>  
<span data-ttu-id="25651-295">EXEMPLE : `TRIM(" A sample sentence with leading white space")`</span><span class="sxs-lookup"><span data-stu-id="25651-295">EXAMPLE: `TRIM(" A sample sentence with leading white space")`</span></span>  
  
<span data-ttu-id="25651-296">Le mode DirectQuery convertit la fonction DAX TRIM en instruction SQL `LTRIM(RTRIM(<column>))`.</span><span class="sxs-lookup"><span data-stu-id="25651-296">DirectQuery mode translates the DAX TRIM function to the SQL statement `LTRIM(RTRIM(<column>))`.</span></span> <span data-ttu-id="25651-297">Par conséquent, seuls les espaces de début et de fin sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="25651-297">As a result, only leading and trailing white space is removed.</span></span>  
  
<span data-ttu-id="25651-298">En revanche, la même formule dans un modèle en mémoire supprime les espaces dans la chaîne, d'après le comportement d'Excel.</span><span class="sxs-lookup"><span data-stu-id="25651-298">In contrast, the same formula in an in-memory model removes spaces within the string, following the behavior of Excel.</span></span>  
  
<span data-ttu-id="25651-299">**RTRIM implicite avec l'utilisation de la fonction LEN**</span><span class="sxs-lookup"><span data-stu-id="25651-299">**Implicit RTRIM with use of LEN function**</span></span>  
<span data-ttu-id="25651-300">EXEMPLE : `LEN('string_column')`</span><span class="sxs-lookup"><span data-stu-id="25651-300">EXAMPLE: `LEN('string_column')`</span></span>  
  
<span data-ttu-id="25651-301">Comme SQL Server, le mode DirectQuery supprime automatiquement les espaces de fin des colonnes de chaîne : autrement dit, il effectue un RTRIM implicite.</span><span class="sxs-lookup"><span data-stu-id="25651-301">Like SQL Server, DirectQuery mode automatically removes white space from the end of string columns: that is, it performs an implicit RTRIM.</span></span> <span data-ttu-id="25651-302">Par conséquent, les formules qui utilisent la fonction LEN peuvent retourner des valeurs différentes si la chaîne possède des espaces de fin.</span><span class="sxs-lookup"><span data-stu-id="25651-302">Therefore, formulas that use the LEN function can return different values if the string has trailing spaces.</span></span>  
  
<span data-ttu-id="25651-303">**Le mode en mémoire prend en charge des paramètres supplémentaires pour SUBSTITUTE**</span><span class="sxs-lookup"><span data-stu-id="25651-303">**In-memory supports additional parameters for SUBSTITUTE**</span></span>  
<span data-ttu-id="25651-304">EXEMPLE : `SUBSTITUTE([Title],"Doctor","Dr.")`</span><span class="sxs-lookup"><span data-stu-id="25651-304">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.")`</span></span>  
  
<span data-ttu-id="25651-305">EXEMPLE : `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span><span class="sxs-lookup"><span data-stu-id="25651-305">EXAMPLE: `SUBSTITUTE([Title],"Doctor","Dr.", 2)`</span></span>  
  
<span data-ttu-id="25651-306">En mode DirectQuery, vous pouvez utiliser uniquement la version de cette fonction qui a trois (3) paramètres : une référence à une colonne, l'ancien texte et le nouveau texte.</span><span class="sxs-lookup"><span data-stu-id="25651-306">In DirectQuery mode, you can use only the version of this function that has three (3) parameters: a reference to a column, the old text, and the new text.</span></span> <span data-ttu-id="25651-307">Si vous utilisez la deuxième formule, une erreur est générée.</span><span class="sxs-lookup"><span data-stu-id="25651-307">If you use the second formula, an error is raised.</span></span>  
  
<span data-ttu-id="25651-308">Dans les modèles en mémoire, vous pouvez utiliser un quatrième paramètre facultatif pour spécifier le nombre d'instances de la chaîne à remplacer.</span><span class="sxs-lookup"><span data-stu-id="25651-308">In in-memory models, you can use an optional fourth parameter to specify the instance number of the string to replace.</span></span> <span data-ttu-id="25651-309">Par exemple, vous pouvez remplacer uniquement la deuxième instance, etc.</span><span class="sxs-lookup"><span data-stu-id="25651-309">For example, you can replace only the second instance, etc.</span></span>  
  
<span data-ttu-id="25651-310">**Restrictions relatives aux longueurs de chaîne pour les opérations REPT**</span><span class="sxs-lookup"><span data-stu-id="25651-310">**Restrictions on string lengths for REPT operations**</span></span>  
<span data-ttu-id="25651-311">Dans les modèles en mémoire, la longueur d'une chaîne résultant d'une opération en utilisant REPT doit être inférieure à 32 767 caractères.</span><span class="sxs-lookup"><span data-stu-id="25651-311">In in-memory models, the length of a string resulting from an operation using REPT must be less than 32,767 characters.</span></span>  
  
<span data-ttu-id="25651-312">Cette restriction ne s'applique pas en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-312">This limitation does not apply in DirectQuery mode.</span></span>  
  
<span data-ttu-id="25651-313">**Les opérations de sous-chaîne retournent des résultats différents selon le type de caractère**</span><span class="sxs-lookup"><span data-stu-id="25651-313">**Substring operations return different results depending on character type**</span></span>  
<span data-ttu-id="25651-314">EXEMPLE : `MID([col], 2, 5)`</span><span class="sxs-lookup"><span data-stu-id="25651-314">EXAMPLE: `MID([col], 2, 5)`</span></span>  
  
<span data-ttu-id="25651-315">Si le texte d **varchar** ou **nvarchar**, le résultat de la formule est toujours identique.</span><span class="sxs-lookup"><span data-stu-id="25651-315">If the input text is **varchar** or **nvarchar**, the result of the formula is always the same.</span></span>  
  
<span data-ttu-id="25651-316">Toutefois, si le texte est un caractère de longueur fixe et que la valeur de \* &lt; num_chars &gt; \* est supérieure à la longueur de la chaîne cible, en mode DirectQuery, un espace est ajouté à la fin de la chaîne de résultat.</span><span class="sxs-lookup"><span data-stu-id="25651-316">However, if the text is a fixed-length character and the value for *&lt;num_chars&gt;* is greater than the length of the target string, in DirectQuery mode, a blank is added at the end of the result string.</span></span>  
  
<span data-ttu-id="25651-317">Dans un modèle en mémoire, le résultat se termine au dernier caractère de chaîne, sans remplissage.</span><span class="sxs-lookup"><span data-stu-id="25651-317">In an in-memory model, the result terminates at the last string character, with no padding.</span></span>  
  
## <a name="functions-supported-in-directquery-mode"></a><a name="bkmk_SupportedFunc"></a><span data-ttu-id="25651-318">Fonctions prises en charge en mode DirectQuery</span><span class="sxs-lookup"><span data-stu-id="25651-318">Functions supported in DirectQuery mode</span></span>  
<span data-ttu-id="25651-319">Les fonctions DAX suivantes peuvent être utilisées en mode DirectQuery, mais avec les qualifications comme décrit dans la section précédente.</span><span class="sxs-lookup"><span data-stu-id="25651-319">The following DAX functions can be used in DirectQuery mode, but with the qualifications as described in the preceding section.</span></span>  
  
<span data-ttu-id="25651-320">**Fonctions de texte**</span><span class="sxs-lookup"><span data-stu-id="25651-320">**Text functions**</span></span>  
  
<span data-ttu-id="25651-321">CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="25651-321">CONCATENATE</span></span>  
  
<span data-ttu-id="25651-322">FIND</span><span class="sxs-lookup"><span data-stu-id="25651-322">FIND</span></span>  
  
<span data-ttu-id="25651-323">LEFT</span><span class="sxs-lookup"><span data-stu-id="25651-323">LEFT</span></span>  
  
<span data-ttu-id="25651-324">LEN</span><span class="sxs-lookup"><span data-stu-id="25651-324">LEN</span></span>  
  
<span data-ttu-id="25651-325">MID</span><span class="sxs-lookup"><span data-stu-id="25651-325">MID</span></span>  
  
<span data-ttu-id="25651-326">REPLACE</span><span class="sxs-lookup"><span data-stu-id="25651-326">REPLACE</span></span>  
  
<span data-ttu-id="25651-327">REPT</span><span class="sxs-lookup"><span data-stu-id="25651-327">REPT</span></span>  
  
<span data-ttu-id="25651-328">RIGHT</span><span class="sxs-lookup"><span data-stu-id="25651-328">RIGHT</span></span>  
  
<span data-ttu-id="25651-329">SUBSTITUTE</span><span class="sxs-lookup"><span data-stu-id="25651-329">SUBSTITUTE</span></span>  
  
<span data-ttu-id="25651-330">TRIM</span><span class="sxs-lookup"><span data-stu-id="25651-330">TRIM</span></span>  
  
<span data-ttu-id="25651-331">**Fonctions statistiques**</span><span class="sxs-lookup"><span data-stu-id="25651-331">**Statistical functions**</span></span>  
  
<span data-ttu-id="25651-332">COUNT</span><span class="sxs-lookup"><span data-stu-id="25651-332">COUNT</span></span>  
  
<span data-ttu-id="25651-333">STDEV.P</span><span class="sxs-lookup"><span data-stu-id="25651-333">STDEV.P</span></span>  
  
<span data-ttu-id="25651-334">STDEV.S</span><span class="sxs-lookup"><span data-stu-id="25651-334">STDEV.S</span></span>  
  
<span data-ttu-id="25651-335">STDEVX.P</span><span class="sxs-lookup"><span data-stu-id="25651-335">STDEVX.P</span></span>  
  
<span data-ttu-id="25651-336">STDEVX.S</span><span class="sxs-lookup"><span data-stu-id="25651-336">STDEVX.S</span></span>  
  
<span data-ttu-id="25651-337">VAR.P</span><span class="sxs-lookup"><span data-stu-id="25651-337">VAR.P</span></span>  
  
<span data-ttu-id="25651-338">VAR.S</span><span class="sxs-lookup"><span data-stu-id="25651-338">VAR.S</span></span>  
  
<span data-ttu-id="25651-339">VARX.P</span><span class="sxs-lookup"><span data-stu-id="25651-339">VARX.P</span></span>  
  
<span data-ttu-id="25651-340">VARX.S</span><span class="sxs-lookup"><span data-stu-id="25651-340">VARX.S</span></span>  
  
<span data-ttu-id="25651-341">**Fonctions de date/heure**</span><span class="sxs-lookup"><span data-stu-id="25651-341">**Date/time functions**</span></span>  
  
<span data-ttu-id="25651-342">DATE</span><span class="sxs-lookup"><span data-stu-id="25651-342">DATE</span></span>  
  
<span data-ttu-id="25651-343">EDATE</span><span class="sxs-lookup"><span data-stu-id="25651-343">EDATE</span></span>  
  
<span data-ttu-id="25651-344">EOMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-344">EOMONTH</span></span>  
  
<span data-ttu-id="25651-345">DATE</span><span class="sxs-lookup"><span data-stu-id="25651-345">DATE</span></span>  
  
<span data-ttu-id="25651-346">TEMPS</span><span class="sxs-lookup"><span data-stu-id="25651-346">TIME</span></span>  
  
<span data-ttu-id="25651-347">SECOND</span><span class="sxs-lookup"><span data-stu-id="25651-347">SECOND</span></span>  
  
<span data-ttu-id="25651-348">**Fonctions mathématiques et numériques**</span><span class="sxs-lookup"><span data-stu-id="25651-348">**Math and number functions**</span></span>  
  
<span data-ttu-id="25651-349">CEILING</span><span class="sxs-lookup"><span data-stu-id="25651-349">CEILING</span></span>  
  
<span data-ttu-id="25651-350">LN</span><span class="sxs-lookup"><span data-stu-id="25651-350">LN</span></span>  
  
<span data-ttu-id="25651-351">LOG</span><span class="sxs-lookup"><span data-stu-id="25651-351">LOG</span></span>  
  
<span data-ttu-id="25651-352">LOG10</span><span class="sxs-lookup"><span data-stu-id="25651-352">LOG10</span></span>  
  
<span data-ttu-id="25651-353">POWER</span><span class="sxs-lookup"><span data-stu-id="25651-353">POWER</span></span>  
  
<span data-ttu-id="25651-354">**Requêtes de table DAX**</span><span class="sxs-lookup"><span data-stu-id="25651-354">**DAX Table queries**</span></span>  
  
<span data-ttu-id="25651-355">Il existe des limitations lorsque vous calculez des formules par rapport à un modèle DirectQuery à l'aide de requêtes de table DAX.</span><span class="sxs-lookup"><span data-stu-id="25651-355">There are some limitations when you evaluate formulas against a DirectQuery model by using DAX Table queries.</span></span> <span data-ttu-id="25651-356">DirectQuery ne prend pas en charge les références à la même colonne deux fois dans une clause ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="25651-356">DirectQuery does not support referring to the same column twice in an ORDER BY clause.</span></span> <span data-ttu-id="25651-357">L'instruction Transact-SQL équivalente ne peut pas être créée et la requête échoue.</span><span class="sxs-lookup"><span data-stu-id="25651-357">The equivalent Transact-SQL statement cannot be created and the query fails.</span></span>  
  
<span data-ttu-id="25651-358">Dans un modèle en mémoire, la répétition de la clause ORDER BY n'a aucun effet sur les résultats.</span><span class="sxs-lookup"><span data-stu-id="25651-358">In an in-memory model, repeating the ORDER by clause has no effect on the results.</span></span>  
  
## <a name="functions-not-supported-in-directquery-mode"></a><a name="bkmk_NotSupportedFunc"></a><span data-ttu-id="25651-359">Fonctions non prises en charge en mode DirectQuery</span><span class="sxs-lookup"><span data-stu-id="25651-359">Functions not supported in DirectQuery Mode</span></span>  
<span data-ttu-id="25651-360">Certaines fonctions DAX ne sont pas prises en charge dans les modèles qui sont déployés en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-360">Some DAX functions are not supported in models that are deployed in DirectQuery mode.</span></span> <span data-ttu-id="25651-361">Les raisons pour lesquelles une fonction particulière n'est pas prise en charge peuvent notamment inclure une ou plusieurs de celles indiquées ci-après :</span><span class="sxs-lookup"><span data-stu-id="25651-361">The reasons that a particular function is not supported can include any or a combination of these reasons:</span></span>  
  
-   <span data-ttu-id="25651-362">Le moteur relationnel sous-jacent ne peut pas effectuer des calculs identiques à ceux effectués par le moteur xVelocity.</span><span class="sxs-lookup"><span data-stu-id="25651-362">The underlying relational engine cannot perform calculations equivalent to those performed by the xVelocity engine.</span></span>  
  
-   <span data-ttu-id="25651-363">La formule ne peut pas être convertie en une expression SQL équivalente.</span><span class="sxs-lookup"><span data-stu-id="25651-363">The formula cannot be converted to en equivalent SQL expression.</span></span>  
  
-   <span data-ttu-id="25651-364">Les performances de l'expression convertie et les calculs résultants sont inacceptables.</span><span class="sxs-lookup"><span data-stu-id="25651-364">The performance of the converted expression and the resulting calculations would be unacceptable.</span></span>  
  
<span data-ttu-id="25651-365">Les fonctions DAX suivantes ne peuvent pas être utilisées dans les modèles DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="25651-365">The following DAX functions cannot be used in DirectQuery models.</span></span>  
  
<span data-ttu-id="25651-366">**Fonctions PATH**</span><span class="sxs-lookup"><span data-stu-id="25651-366">**Path functions**</span></span>  
  
<span data-ttu-id="25651-367">PATH</span><span class="sxs-lookup"><span data-stu-id="25651-367">PATH</span></span>  
  
<span data-ttu-id="25651-368">PATHCONTAINS</span><span class="sxs-lookup"><span data-stu-id="25651-368">PATHCONTAINS</span></span>  
  
<span data-ttu-id="25651-369">PATHITEM</span><span class="sxs-lookup"><span data-stu-id="25651-369">PATHITEM</span></span>  
  
<span data-ttu-id="25651-370">PATHITEMREVERSE</span><span class="sxs-lookup"><span data-stu-id="25651-370">PATHITEMREVERSE</span></span>  
  
<span data-ttu-id="25651-371">PATHLENGTH</span><span class="sxs-lookup"><span data-stu-id="25651-371">PATHLENGTH</span></span>  
  
<span data-ttu-id="25651-372">**Fonctions diverses**</span><span class="sxs-lookup"><span data-stu-id="25651-372">**Misc functions**</span></span>  
  
<span data-ttu-id="25651-373">COUNTBLANK</span><span class="sxs-lookup"><span data-stu-id="25651-373">COUNTBLANK</span></span>  
  
<span data-ttu-id="25651-374">FIXED</span><span class="sxs-lookup"><span data-stu-id="25651-374">FIXED</span></span>  
  
<span data-ttu-id="25651-375">FORMAT</span><span class="sxs-lookup"><span data-stu-id="25651-375">FORMAT</span></span>  
  
<span data-ttu-id="25651-376">RAND</span><span class="sxs-lookup"><span data-stu-id="25651-376">RAND</span></span>  
  
<span data-ttu-id="25651-377">RANDBETWEEN</span><span class="sxs-lookup"><span data-stu-id="25651-377">RANDBETWEEN</span></span>  
  
<span data-ttu-id="25651-378">**Fonctions Time Intelligence : dates de début et de fin**</span><span class="sxs-lookup"><span data-stu-id="25651-378">**Time intelligence functions: Start and end dates**</span></span>  
  
<span data-ttu-id="25651-379">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="25651-379">DATESQTD</span></span>  
  
<span data-ttu-id="25651-380">DATESYTD</span><span class="sxs-lookup"><span data-stu-id="25651-380">DATESYTD</span></span>  
  
<span data-ttu-id="25651-381">DATESMTD</span><span class="sxs-lookup"><span data-stu-id="25651-381">DATESMTD</span></span>  
  
<span data-ttu-id="25651-382">DATESQTD</span><span class="sxs-lookup"><span data-stu-id="25651-382">DATESQTD</span></span>  
  
<span data-ttu-id="25651-383">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="25651-383">DATESINPERIOD</span></span>  
  
<span data-ttu-id="25651-384">TOTALMTD</span><span class="sxs-lookup"><span data-stu-id="25651-384">TOTALMTD</span></span>  
  
<span data-ttu-id="25651-385">TOTALQTD</span><span class="sxs-lookup"><span data-stu-id="25651-385">TOTALQTD</span></span>  
  
<span data-ttu-id="25651-386">TOTALYTD</span><span class="sxs-lookup"><span data-stu-id="25651-386">TOTALYTD</span></span>  
  
<span data-ttu-id="25651-387">DATESINPERIOD</span><span class="sxs-lookup"><span data-stu-id="25651-387">DATESINPERIOD</span></span>  
  
<span data-ttu-id="25651-388">SAMEPERIODLASTYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-388">SAMEPERIODLASTYEAR</span></span>  
  
<span data-ttu-id="25651-389">PARALLELPERIOD</span><span class="sxs-lookup"><span data-stu-id="25651-389">PARALLELPERIOD</span></span>  
  
<span data-ttu-id="25651-390">**Fonctions Time Intelligence : soldes**</span><span class="sxs-lookup"><span data-stu-id="25651-390">**Time-intelligence functions: Balances**</span></span>  
  
<span data-ttu-id="25651-391">OPENINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-391">OPENINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="25651-392">OPENINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="25651-392">OPENINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="25651-393">OPENINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-393">OPENINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="25651-394">CLOSINGBALANCEMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-394">CLOSINGBALANCEMONTH</span></span>  
  
<span data-ttu-id="25651-395">CLOSINGBALANCEQUARTER</span><span class="sxs-lookup"><span data-stu-id="25651-395">CLOSINGBALANCEQUARTER</span></span>  
  
<span data-ttu-id="25651-396">CLOSINGBALANCEYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-396">CLOSINGBALANCEYEAR</span></span>  
  
<span data-ttu-id="25651-397">**Fonctions Time Intelligence : périodes précédente et suivante**</span><span class="sxs-lookup"><span data-stu-id="25651-397">**Time intelligence functions: Previous and next periods**</span></span>  
  
<span data-ttu-id="25651-398">PREVIOUSDAY</span><span class="sxs-lookup"><span data-stu-id="25651-398">PREVIOUSDAY</span></span>  
  
<span data-ttu-id="25651-399">PREVIOUSMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-399">PREVIOUSMONTH</span></span>  
  
<span data-ttu-id="25651-400">PREVIOUSQUARTER</span><span class="sxs-lookup"><span data-stu-id="25651-400">PREVIOUSQUARTER</span></span>  
  
<span data-ttu-id="25651-401">PREVIOUSYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-401">PREVIOUSYEAR</span></span>  
  
<span data-ttu-id="25651-402">NEXTDAY</span><span class="sxs-lookup"><span data-stu-id="25651-402">NEXTDAY</span></span>  
  
<span data-ttu-id="25651-403">NEXTMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-403">NEXTMONTH</span></span>  
  
<span data-ttu-id="25651-404">NEXTQUARTER</span><span class="sxs-lookup"><span data-stu-id="25651-404">NEXTQUARTER</span></span>  
  
<span data-ttu-id="25651-405">NEXTYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-405">NEXTYEAR</span></span>  
  
<span data-ttu-id="25651-406">**Fonctions Time Intelligence : périodes et calculs sur les périodes**</span><span class="sxs-lookup"><span data-stu-id="25651-406">**Time intelligence functions: Periods and calculations over periods**</span></span>  
  
<span data-ttu-id="25651-407">STARTOFMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-407">STARTOFMONTH</span></span>  
  
<span data-ttu-id="25651-408">STARTOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="25651-408">STARTOFQUARTER</span></span>  
  
<span data-ttu-id="25651-409">STARTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-409">STARTOFYEAR</span></span>  
  
<span data-ttu-id="25651-410">ENDOFMONTH</span><span class="sxs-lookup"><span data-stu-id="25651-410">ENDOFMONTH</span></span>  
  
<span data-ttu-id="25651-411">ENDOFQUARTER</span><span class="sxs-lookup"><span data-stu-id="25651-411">ENDOFQUARTER</span></span>  
  
<span data-ttu-id="25651-412">ENDOFYEAR</span><span class="sxs-lookup"><span data-stu-id="25651-412">ENDOFYEAR</span></span>  
  
<span data-ttu-id="25651-413">FIRSTDATE</span><span class="sxs-lookup"><span data-stu-id="25651-413">FIRSTDATE</span></span>  
  
<span data-ttu-id="25651-414">LASTDATE</span><span class="sxs-lookup"><span data-stu-id="25651-414">LASTDATE</span></span>  
  
<span data-ttu-id="25651-415">DATEADD</span><span class="sxs-lookup"><span data-stu-id="25651-415">DATEADD</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25651-416">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25651-416">See also</span></span>  
[<span data-ttu-id="25651-417">Mode DirectQuery (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="25651-417">DirectQuery Mode (SSAS Tabular)</span></span>](https://msdn.microsoft.com/45ad2965-05ec-4fb1-a164-d8060b562ea5)  
  

