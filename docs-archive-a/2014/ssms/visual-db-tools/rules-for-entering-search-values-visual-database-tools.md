---
title: Règles pour l’entrée de valeurs de recherche (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- time [SQL Server], searches
- date searches
- dates [SQL Server], searches
- embedding apostrophes [SQL Server]
- logical value searches [SQL Server]
- case-sensitive search matches
- search criteria [SQL Server], rules
- text value searches [SQL Server]
- numeric value searches [SQL Server]
ms.assetid: 3c8134b7-83f4-41b4-99c8-e3949a685ff5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 907bcac93863bc5660993e910b37e25e25a129b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601248"
---
# <a name="rules-for-entering-search-values-visual-database-tools"></a><span data-ttu-id="29174-102">Règles pour l'entrée de valeurs de recherche (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="29174-102">Rules for Entering Search Values (Visual Database Tools)</span></span>
  <span data-ttu-id="29174-103">Cette rubrique décrit les conventions à utiliser lorsque vous entrez les types de valeurs littérales suivants pour une condition de recherche :</span><span class="sxs-lookup"><span data-stu-id="29174-103">This topic discusses the conventions you must use when entering the following types of literal values for a search condition:</span></span>  
  
-   <span data-ttu-id="29174-104">Valeurs texte</span><span class="sxs-lookup"><span data-stu-id="29174-104">Text values</span></span>  
  
-   <span data-ttu-id="29174-105">Valeurs numériques</span><span class="sxs-lookup"><span data-stu-id="29174-105">Numeric values</span></span>  
  
-   <span data-ttu-id="29174-106">Dates</span><span class="sxs-lookup"><span data-stu-id="29174-106">Dates</span></span>  
  
-   <span data-ttu-id="29174-107">Valeurs logiques</span><span class="sxs-lookup"><span data-stu-id="29174-107">Logical values</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29174-108">Les informations contenues dans cette rubrique sont extraites des règles relatives au langage SQL-92 standard.</span><span class="sxs-lookup"><span data-stu-id="29174-108">The information in this topic is derived from the rules for standard SQL-92.</span></span> <span data-ttu-id="29174-109">L'implémentation du langage SQL peut cependant être personnalisée dans chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="29174-109">However, each database can implement SQL in its own way.</span></span> <span data-ttu-id="29174-110">Les indications proposées ci-dessous ne sont donc pas forcément applicables dans tous les cas.</span><span class="sxs-lookup"><span data-stu-id="29174-110">Therefore, the guidelines provided here might not apply in every case.</span></span> <span data-ttu-id="29174-111">Si vous avez des questions sur l'entrée des valeurs de recherche pour une base de données particulière, consultez la documentation de la base de données utilisée.</span><span class="sxs-lookup"><span data-stu-id="29174-111">If you have questions about how to enter search values for a particular database, refer to the documentation for the database that you are using.</span></span>  
  
## <a name="searching-on-text-values"></a><span data-ttu-id="29174-112">Recherche de valeurs texte</span><span class="sxs-lookup"><span data-stu-id="29174-112">Searching on Text Values</span></span>  
 <span data-ttu-id="29174-113">Les indications suivantes s'appliquent lorsque vous entrez des valeurs texte dans les conditions de recherche :</span><span class="sxs-lookup"><span data-stu-id="29174-113">The following guidelines apply when you enter text values in search conditions:</span></span>  
  
-   <span data-ttu-id="29174-114">**Guillemets** Placez les valeurs texte entre des guillemets simples, à l’instar du nom dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-114">**Quotation marks** Enclose text values in single quotation marks, as in this example for a last name:</span></span>  
  
    ```  
    'Smith'  
    ```  
  
     <span data-ttu-id="29174-115">Si vous entrez une condition de recherche dans le [volet Critères](visual-database-tools.md), il vous suffit de taper la valeur texte : le Concepteur de requêtes et de vues insère automatiquement des guillemets simples devant et derrière.</span><span class="sxs-lookup"><span data-stu-id="29174-115">If you are entering a search condition in the [Criteria Pane](visual-database-tools.md), you can simply type the text value and the Query and View Designer will automatically put single quotation marks around it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="29174-116">Dans certaines bases de données, les termes placés entre guillemets simples sont interprétés comme des valeurs littérales et les termes placés entre guillemets doubles comme des objets de base de données, par exemple, des références de colonne ou de table.</span><span class="sxs-lookup"><span data-stu-id="29174-116">In some databases, terms in single quotation marks are interpreted as literal values, whereas terms in double quotation marks are interpreted as database objects such as column or table references.</span></span> <span data-ttu-id="29174-117">Par conséquent, même si le Concepteur de requêtes et de vues accepte les termes entre guillemets doubles, il risque de ne pas les interpréter comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="29174-117">Therefore, even though the Query and View Designer can accept terms in double quotation marks, it might interpret them differently than you expect.</span></span>  
  
-   <span data-ttu-id="29174-118">**Incorporation d’apostrophes** Si les données recherchées contiennent un guillemet unique (une apostrophe), vous pouvez entrer deux guillemets simples pour indiquer que ce guillemet est une valeur littérale, et non un délimiteur.</span><span class="sxs-lookup"><span data-stu-id="29174-118">**Embedding apostrophes** If the data you are searching for contains a single quotation mark (an apostrophe), you can enter two single quotation marks to indicate that you mean the single quotation mark as a literal value and not a delimiter.</span></span> <span data-ttu-id="29174-119">Par exemple, la condition suivante permet de rechercher la valeur « Aujourd'hui » :</span><span class="sxs-lookup"><span data-stu-id="29174-119">For example, the following condition searches for the value "Swann's Way:"</span></span>  
  
    ```  
    ='Swann''s Way'  
    ```  
  
-   <span data-ttu-id="29174-120">**Longueurs limites** Ne dépassez pas la longueur maximale de l’instruction SQL pour votre base de données quand vous entrez des chaînes longues.</span><span class="sxs-lookup"><span data-stu-id="29174-120">**Length limits** Do not exceed the maximum length of the SQL statement for your database when entering long strings.</span></span>  
  
-   <span data-ttu-id="29174-121">**Respect de la casse** Suivez les règles de respect de la casse associées à la base de données utilisée.</span><span class="sxs-lookup"><span data-stu-id="29174-121">**Case sensitivity** Follow the case sensitivity rules for the database you are using.</span></span> <span data-ttu-id="29174-122">C'est en effet la base de données utilisée qui détermine si les recherches de texte distinguent les majuscules et les minuscules.</span><span class="sxs-lookup"><span data-stu-id="29174-122">The database you are using determines whether text searches are case sensitive.</span></span> <span data-ttu-id="29174-123">Par exemple, certaines bases de données interprètent l'opérateur « = » comme une correspondance avec respect de la casse, tandis que d'autres acceptent les correspondances pour n'importe quelle combinaison de caractères majuscules et minuscules.</span><span class="sxs-lookup"><span data-stu-id="29174-123">For example, some databases interpret the operator "=" to mean an exact case-sensitive match, but others will allow matches on any combination of uppercase and lowercase characters.</span></span>  
  
     <span data-ttu-id="29174-124">Lorsque vous ignorez si la base de données utilise une recherche avec respect de la casse, vous pouvez utiliser les fonctions UPPER ou LOWER dans la condition de recherche afin de convertir la casse des données recherchées, comme illustré dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-124">If you are unsure about whether the database uses a case-sensitive search, you can use the UPPER or LOWER functions in the search condition to convert the case of the search data, as illustrated in the following example:</span></span>  
  
    ```  
    WHERE UPPER(lname) = 'SMITH'  
    ```  
  
## <a name="searching-on-numeric-values"></a><span data-ttu-id="29174-125">Recherche sur des valeurs numériques</span><span class="sxs-lookup"><span data-stu-id="29174-125">Searching on Numeric Values</span></span>  
 <span data-ttu-id="29174-126">Les indications suivantes s'appliquent lorsque vous entrez des valeurs numériques dans les conditions de recherche:</span><span class="sxs-lookup"><span data-stu-id="29174-126">The following guidelines apply when you enter numeric values in search conditions:</span></span>  
  
-   <span data-ttu-id="29174-127">**Guillemets** Ne mettez pas les nombres entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="29174-127">**Quotation marks** Do not enclose numbers in quotation marks.</span></span>  
  
-   <span data-ttu-id="29174-128">**Caractères non numériques** N’incluez pas de caractères non numériques autres que le délimiteur décimal (défini dans la boîte de dialogue **Paramètres régionaux** du Panneau de configuration Windows) et le signe négatif (-).</span><span class="sxs-lookup"><span data-stu-id="29174-128">**Non-numeric characters** Do not include non-numeric characters except the decimal separator (as defined in the **Regional Settings** dialog box of Windows Control Panel) and negative sign (-).</span></span> <span data-ttu-id="29174-129">N'incluez pas de symboles de groupement des chiffres (telle une virgule entre les milliers) ni de symboles monétaires.</span><span class="sxs-lookup"><span data-stu-id="29174-129">Do not include digit grouping symbols (such as a comma between thousands) or currency symbols.</span></span>  
  
-   <span data-ttu-id="29174-130">**Marques décimales** Si vous entrez des nombres entiers, vous pouvez inclure une marque décimale, que la valeur recherchée soit un entier ou un nombre réel.</span><span class="sxs-lookup"><span data-stu-id="29174-130">**Decimal marks** If you are entering whole numbers, you can include a decimal mark, whether the value you are searching for is an integer or a real number.</span></span>  
  
-   <span data-ttu-id="29174-131">**Notation scientifique** Vous pouvez entrer des nombres très petits ou très grands en utilisant la notation scientifique, comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-131">**Scientific notation** You can enter very large or very small numbers using scientific notation, as in this example:</span></span>  
  
    ```  
    > 1.23456e-9  
    ```  
  
## <a name="searching-on-dates"></a><span data-ttu-id="29174-132">Recherche sur des dates</span><span class="sxs-lookup"><span data-stu-id="29174-132">Searching on Dates</span></span>  
 <span data-ttu-id="29174-133">Le format utilisé pour l'entrée des dates varie selon la base de données employée et le volet du Concepteur de requêtes et de vues dans lequel vous entrez les dates.</span><span class="sxs-lookup"><span data-stu-id="29174-133">The format you use to enter dates depends on the database you are using and in what pane of the Query and View Designer you are entering the date.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="29174-134">Si vous ne connaissez pas le format utilisé par votre source de données, tapez une date dans la colonne Filtre du volet Critères dans n'importe quel format qui vous est familier.</span><span class="sxs-lookup"><span data-stu-id="29174-134">If you don't know which format your data source uses, type a date into the filter column of the Criteria pane in any format familiar to you.</span></span> <span data-ttu-id="29174-135">Le Concepteur convertira la plupart des entrées de ce type au format approprié.</span><span class="sxs-lookup"><span data-stu-id="29174-135">The designer will convert most of such entries into the appropriate format.</span></span>  
  
 <span data-ttu-id="29174-136">Le Concepteur de requêtes et de vues accepte les formats de date suivants :</span><span class="sxs-lookup"><span data-stu-id="29174-136">The Query and View Designer can work with the following date formats:</span></span>  
  
-   <span data-ttu-id="29174-137">**Données locales spécifiques** Le format spécifié pour les dates dans la boîte de dialogue **Windows Propriétés de Paramètres régionaux** .</span><span class="sxs-lookup"><span data-stu-id="29174-137">**Locale-specific** The format specified for dates in the **Windows Regional Settings Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="29174-138">**Spécifique à la base de données** N’importe quel format interprété par la base de données.</span><span class="sxs-lookup"><span data-stu-id="29174-138">**Database-specific** Any format understood by the database.</span></span>  
  
-   <span data-ttu-id="29174-139">**Date ANSI standard** Format utilisant des accolades, le marqueur 'd' pour désigner la date et une chaîne de date, comme dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-139">**ANSI standard date** A format that uses braces, the marker 'd' to designate the date, and a date string, as in the following example:</span></span>  
  
    ```  
    { d '1990-12-31' }  
    ```  
  
-   <span data-ttu-id="29174-140">**DateHeure ANSI standard** Similaire à la date ANSI standard, avec quelques différences : 'ts' est utilisé à la place de 'd' et l’heure (heures, minutes et secondes, dans un format sur 24 heures) est ajoutée à la date. L’exemple suivant indique la notation utilisée pour le 31 décembre 1990 :</span><span class="sxs-lookup"><span data-stu-id="29174-140">**ANSI standard datetime** Similar to ANSI-standard date, but uses 'ts' instead of 'd' and adds hours, minutes, and seconds to the date (using a 24-hour clock), as in this example for December 31, 1990:</span></span>  
  
    ```  
    { ts '1990-12-31 00:00:00' }  
    ```  
  
     <span data-ttu-id="29174-141">En général, le format de date ANSI standard est employé pour les bases de données qui représentent les dates avec un véritable type de données date.</span><span class="sxs-lookup"><span data-stu-id="29174-141">In general, the ANSI standard date format is used with databases that represent dates using a true date data type.</span></span> <span data-ttu-id="29174-142">En revanche, le format datetime est employé pour les bases de données qui prennent en charge un type de données datetime.</span><span class="sxs-lookup"><span data-stu-id="29174-142">In contrast, the datetime format is used with databases that support a datetime data type.</span></span>  
  
 <span data-ttu-id="29174-143">Le tableau suivant récapitule les formats de date que vous pouvez utiliser dans les différents volets du Concepteur de requêtes et de vues.</span><span class="sxs-lookup"><span data-stu-id="29174-143">The following table summarizes the date format that you can use in different panes of the Query and View Designer.</span></span>  
  
|<span data-ttu-id="29174-144">**Volet**</span><span class="sxs-lookup"><span data-stu-id="29174-144">**Pane**</span></span>|<span data-ttu-id="29174-145">**Format de date**</span><span class="sxs-lookup"><span data-stu-id="29174-145">**Date format**</span></span>|  
|--------------|---------------------|  
|<span data-ttu-id="29174-146">Critères</span><span class="sxs-lookup"><span data-stu-id="29174-146">Criteria</span></span>|<span data-ttu-id="29174-147">Données locales spécifiques, spécifiques à la base de données, ANSI standard</span><span class="sxs-lookup"><span data-stu-id="29174-147">Locale-specific Database-specific ANSI standard</span></span><br /><br /> <span data-ttu-id="29174-148">Les dates entrées dans le [volet Critères](visual-database-tools.md) sont converties dans un format compatible avec la base de données à l’intérieur du volet SQL.</span><span class="sxs-lookup"><span data-stu-id="29174-148">Dates entered in the [Criteria Pane](visual-database-tools.md) are converted to a database-compatible format in the SQL pane.</span></span>|  
|<span data-ttu-id="29174-149">SQL</span><span class="sxs-lookup"><span data-stu-id="29174-149">SQL</span></span>|<span data-ttu-id="29174-150">Données spécifique à la base de données, ANSI standard</span><span class="sxs-lookup"><span data-stu-id="29174-150">Database-specific ANSI standard</span></span>|  
|<span data-ttu-id="29174-151">Résultats</span><span class="sxs-lookup"><span data-stu-id="29174-151">Results</span></span>|<span data-ttu-id="29174-152">Données locales spécifiques</span><span class="sxs-lookup"><span data-stu-id="29174-152">Locale-specific</span></span>|  
  
## <a name="searching-on-logical-values"></a><span data-ttu-id="29174-153">Recherche sur des valeurs logiques</span><span class="sxs-lookup"><span data-stu-id="29174-153">Searching on Logical Values</span></span>  
 <span data-ttu-id="29174-154">Le format des données logiques varie d'une base de données à l'autre.</span><span class="sxs-lookup"><span data-stu-id="29174-154">The format of logical data varies from database to database.</span></span> <span data-ttu-id="29174-155">Très souvent, la valeur False est stockée en tant que zéro (0).</span><span class="sxs-lookup"><span data-stu-id="29174-155">Very frequently, a value of False is stored as zero (0).</span></span> <span data-ttu-id="29174-156">La valeur True est en général stockée en tant que 1, parfois en tant que -1.</span><span class="sxs-lookup"><span data-stu-id="29174-156">A value of True is most frequently stored as 1 and occasionally as -1.</span></span> <span data-ttu-id="29174-157">Les indications suivantes s'appliquent lorsque vous entrez des valeurs logiques dans les conditions de recherche :</span><span class="sxs-lookup"><span data-stu-id="29174-157">The following guidelines apply when you enter logical values in search conditions:</span></span>  
  
-   <span data-ttu-id="29174-158">Pour rechercher la valeur False, utilisez un zéro, comme dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-158">To search for a value of False, use a zero, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 0  
    ```  
  
-   <span data-ttu-id="29174-159">Si vous avez des doutes sur le format à utiliser pour rechercher la valeur True, essayez d'utiliser 1, comme dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-159">If you are not sure what format to use when searching for a True value, try using 1, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract = 1  
    ```  
  
-   <span data-ttu-id="29174-160">Vous pouvez également élargir la portée de la recherche en recherchant toutes les valeurs différentes de zéro, comme dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="29174-160">Alternatively, you can broaden the scope of the search by searching for any non-zero value, as in the following example:</span></span>  
  
    ```  
    SELECT * FROM authors  
    WHERE contract <> 0  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="29174-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29174-161">See Also</span></span>  
 [<span data-ttu-id="29174-162">Spécifier des critères de recherche &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="29174-162">Specify Search Criteria &#40;Visual Database Tools&#41;</span></span>](specify-search-criteria-visual-database-tools.md)  
  
  
