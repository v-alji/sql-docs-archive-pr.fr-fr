---
title: Fonction LookupSet (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7685acfd-1c8d-420c-993c-903236fbe1ff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4edc7a17f2aa3813e8aa73e538594b5df3aeabc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605162"
---
# <a name="lookupset-function-report-builder-and-ssrs"></a><span data-ttu-id="58f95-102">Fonction LookupSet (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="58f95-102">LookupSet Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="58f95-103">Retourne le jeu de valeurs correspondantes pour le nom spécifié d'un dataset contenant des paires nom/valeur.</span><span class="sxs-lookup"><span data-stu-id="58f95-103">Returns the set of matching values for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="58f95-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="58f95-104">Syntax</span></span>  
  
```  
  
LookupSet(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58f95-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="58f95-105">Parameters</span></span>  
 <span data-ttu-id="58f95-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="58f95-106">*source_expression*</span></span>  
 <span data-ttu-id="58f95-107">(`Variant`) Expression évaluée dans l'étendue actuelle et qui spécifie le nom ou la clé à rechercher.</span><span class="sxs-lookup"><span data-stu-id="58f95-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="58f95-108">Par exemple : `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="58f95-108">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="58f95-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="58f95-109">*destination_expression*</span></span>  
 <span data-ttu-id="58f95-110">(`Variant`) Expression évaluée pour chaque ligne d'un dataset et qui spécifie le nom ou la clé de correspondance.</span><span class="sxs-lookup"><span data-stu-id="58f95-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="58f95-111">Par exemple : `=Fields!CustomerID.Value`.</span><span class="sxs-lookup"><span data-stu-id="58f95-111">For example, `=Fields!CustomerID.Value`.</span></span>  
  
 <span data-ttu-id="58f95-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="58f95-112">*result_expression*</span></span>  
 <span data-ttu-id="58f95-113">( `Variant` ) Expression évaluée pour la ligne du DataSet où *source_expression*  =  *destination_expression*, et qui spécifie la valeur à récupérer.</span><span class="sxs-lookup"><span data-stu-id="58f95-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="58f95-114">Par exemple : `=Fields!PhoneNumber.Value`.</span><span class="sxs-lookup"><span data-stu-id="58f95-114">For example, `=Fields!PhoneNumber.Value`.</span></span>  
  
 <span data-ttu-id="58f95-115">*dataset*</span><span class="sxs-lookup"><span data-stu-id="58f95-115">*dataset*</span></span>  
 <span data-ttu-id="58f95-116">Constante qui spécifie le nom d'un dataset dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="58f95-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="58f95-117">Par exemple, « ContactInformation ».</span><span class="sxs-lookup"><span data-stu-id="58f95-117">For example, "ContactInformation".</span></span>  
  
## <a name="return"></a><span data-ttu-id="58f95-118">Renvoie</span><span class="sxs-lookup"><span data-stu-id="58f95-118">Return</span></span>  
 <span data-ttu-id="58f95-119">Retourne une valeur `VariantArray`, ou `Nothing` si aucune correspondance n'est trouvée.</span><span class="sxs-lookup"><span data-stu-id="58f95-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58f95-120">Notes</span><span class="sxs-lookup"><span data-stu-id="58f95-120">Remarks</span></span>  
 <span data-ttu-id="58f95-121">Utilisez `LookupSet` pour récupérer un jeu de valeurs du dataset spécifié pour une paire nom-valeur lorsqu'il existe une relation un à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="58f95-121">Use `LookupSet` to retrieve a set of values from the specified dataset for a name/value pair where there is a 1-to-many relationship.</span></span> <span data-ttu-id="58f95-122">Par exemple, pour un identificateur de client dans une table, vous pouvez utiliser `LookupSet` pour récupérer tous les numéros de téléphone associés à ce client à partir d'un dataset qui n'est pas lié à la région de données.</span><span class="sxs-lookup"><span data-stu-id="58f95-122">For example, for a customer identifier in a table, you can use `LookupSet` to retrieve all the associated phone numbers for that customer from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="58f95-123">La fonction `LookupSet` effectue les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="58f95-123">`LookupSet` does the following:</span></span>  
  
-   <span data-ttu-id="58f95-124">Évalue l'expression source dans l'étendue actuelle.</span><span class="sxs-lookup"><span data-stu-id="58f95-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="58f95-125">Évalue l'expression de destination pour chaque ligne du dataset spécifié après avoir appliqué les filtres, en fonction du classement du dataset spécifié.</span><span class="sxs-lookup"><span data-stu-id="58f95-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="58f95-126">Pour chaque correspondance des expressions source et de destination, évalue l'expression de résultat pour cette ligne dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="58f95-126">For each match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="58f95-127">Retourne le jeu de valeurs d'expressions de résultat.</span><span class="sxs-lookup"><span data-stu-id="58f95-127">Returns the set of result expression values.</span></span>  
  
 <span data-ttu-id="58f95-128">Pour récupérer une valeur unique dans un dataset avec les paires nom-valeur d’un nom spécifique, lorsqu’il existe une relation un-à-un, utilisez la [Fonction Lookup &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="58f95-128">To retrieve a single value from a dataset with name/value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="58f95-129">Pour appeler `Lookup` pour un ensemble de valeurs, utilisez la [fonction multilookup &#40;générateur de rapports et SSRS&#41;](report-builder-functions-multilookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="58f95-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-multilookup-function.md).</span></span>  
  
 <span data-ttu-id="58f95-130">Les restrictions suivantes s’appliquent :</span><span class="sxs-lookup"><span data-stu-id="58f95-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="58f95-131">`LookupSet`est évalué après que toutes les expressions de filtre ont été appliquées.</span><span class="sxs-lookup"><span data-stu-id="58f95-131">`LookupSet` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="58f95-132">Un seul niveau de recherche est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="58f95-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="58f95-133">Une expression source, destination ou de résultat ne peut pas inclure de référence à une fonction de recherche.</span><span class="sxs-lookup"><span data-stu-id="58f95-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="58f95-134">Les expressions source et de destination doivent correspondre au même type de données.</span><span class="sxs-lookup"><span data-stu-id="58f95-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="58f95-135">Les expressions source, de destination et de résultat ne peuvent pas inclure de références à des variables de groupe ou de rapport.</span><span class="sxs-lookup"><span data-stu-id="58f95-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="58f95-136">`LookupSet` ne peut pas être utilisé comme expression pour les éléments de rapport suivants :</span><span class="sxs-lookup"><span data-stu-id="58f95-136">`LookupSet` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="58f95-137">des chaînes de connexion dynamiques pour une source de données ;</span><span class="sxs-lookup"><span data-stu-id="58f95-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="58f95-138">des champs calculés dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="58f95-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="58f95-139">des paramètres de requête dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="58f95-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="58f95-140">des filtres dans un dataset ;</span><span class="sxs-lookup"><span data-stu-id="58f95-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="58f95-141">des paramètres de rapport ;</span><span class="sxs-lookup"><span data-stu-id="58f95-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="58f95-142">la propriété Report.Language.</span><span class="sxs-lookup"><span data-stu-id="58f95-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="58f95-143">Pour plus d’informations, consultez [Référence aux fonctions d’agrégation &#40;Générateur de rapports et SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) et [Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="58f95-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58f95-144">Exemple</span><span class="sxs-lookup"><span data-stu-id="58f95-144">Example</span></span>  
 <span data-ttu-id="58f95-145">Dans l'exemple suivant, supposons que la table est liée à un dataset qui inclut un identificateur de secteur de vente TerritoryGroupID.</span><span class="sxs-lookup"><span data-stu-id="58f95-145">In the following example, assume the table is bound to a dataset that includes a sales territory identifier TerritoryGroupID.</span></span> <span data-ttu-id="58f95-146">Un dataset séparé appelé « Magasins » contient la liste de tous les magasins dans un secteur et inclut l'identificateur du secteur ID et le nom du magasin NomMagasin.</span><span class="sxs-lookup"><span data-stu-id="58f95-146">A separate dataset called "Stores" contains the list of all stores in a territory and includes the territory identifier ID and the name of the store StoreName.</span></span>  
  
 <span data-ttu-id="58f95-147">Dans l'expression suivante, `LookupSet` compare la valeur TerritoryGroupID à la valeur ID pour chaque ligne du dataset appelé « Stores ».</span><span class="sxs-lookup"><span data-stu-id="58f95-147">In the following expression, `LookupSet` compares the value TerritoryGroupID to ID for each row in the dataset called "Stores".</span></span> <span data-ttu-id="58f95-148">Pour chaque correspondance, la valeur du champ StoreName pour cette ligne est ajoutée au jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="58f95-148">For each match, the value of the StoreName field for that row is added to the result set.</span></span>  
  
```  
=LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores")  
```  
  
## <a name="example"></a><span data-ttu-id="58f95-149">Exemple</span><span class="sxs-lookup"><span data-stu-id="58f95-149">Example</span></span>  
 <span data-ttu-id="58f95-150">Étant donné que `LookupSet` retourne une collection d'objets, vous ne pouvez pas afficher directement l'expression de résultat dans une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="58f95-150">Because `LookupSet` returns a collection of objects, you cannot display the result expression directly in a text box.</span></span> <span data-ttu-id="58f95-151">Vous pouvez concaténer la valeur de chaque objet dans la collection en tant que chaîne.</span><span class="sxs-lookup"><span data-stu-id="58f95-151">You can concatenate the value of each object in the collection as a string.</span></span>  
  
 <span data-ttu-id="58f95-152">Utilisez la fonction [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]`Join` pour créer une chaîne délimitée à partir d'un jeu d'objets.</span><span class="sxs-lookup"><span data-stu-id="58f95-152">Use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] function `Join` create a delimited string from a set of objects.</span></span> <span data-ttu-id="58f95-153">Utilisez une virgule comme séparateur pour combiner les objets en une ligne unique.</span><span class="sxs-lookup"><span data-stu-id="58f95-153">Use a comma as a separator to combine the objects in a single line.</span></span> <span data-ttu-id="58f95-154">Dans certains convertisseurs, vous pouvez utiliser un saut de ligne [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] (`vbCrLF`) comme séparateur pour répertorier chaque valeur sur une nouvelle ligne.</span><span class="sxs-lookup"><span data-stu-id="58f95-154">In some renderers, you might use a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] line feed (`vbCrLF`) as a separator to list each value on a new line.</span></span>  
  
 <span data-ttu-id="58f95-155">L’expression suivante, lorsqu’elle est utilisée comme propriété de valeur d’une zone de texte, utilise `Join` pour créer une liste.</span><span class="sxs-lookup"><span data-stu-id="58f95-155">The following expression, when it is used as the Value property for a text box, uses `Join` to create a list.</span></span>  
  
```  
=Join(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"),",")  
```  
  
## <a name="example"></a><span data-ttu-id="58f95-156">Exemple</span><span class="sxs-lookup"><span data-stu-id="58f95-156">Example</span></span>  
 <span data-ttu-id="58f95-157">Pour les zones de texte qui seront uniquement restituées quelques fois, vous pouvez choisir d'ajouter un code personnalisé pour générer un code HTML permettant d'afficher des valeurs dans une zone de texte.</span><span class="sxs-lookup"><span data-stu-id="58f95-157">For text boxes that only render a few times, you might choose to add custom code to generate HTML to display values in a text box.</span></span> <span data-ttu-id="58f95-158">Le code HTML dans une zone de texte requiert un traitement supplémentaire et ne serait donc pas un bon choix pour une zone de texte restituée des milliers de fois.</span><span class="sxs-lookup"><span data-stu-id="58f95-158">HTML in a text box requires extra processing, so this would not be a good choice for a text box that is rendered thousands of times.</span></span>  
  
 <span data-ttu-id="58f95-159">Copiez les fonctions [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] suivantes dans un bloc Code de définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="58f95-159">Copy the following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to a Code block in a report definition.</span></span> <span data-ttu-id="58f95-160">**MakeList** utilise le tableau d’objets retourné dans *result_expression* pour générer une liste non ordonnée à l’aide de balises HTML.</span><span class="sxs-lookup"><span data-stu-id="58f95-160">**MakeList** takes the object array that is returned in *result_expression* and builds an unordered list by using HTML tags.</span></span> <span data-ttu-id="58f95-161">**Length** retourne le nombre d'éléments dans le tableau d'objets.</span><span class="sxs-lookup"><span data-stu-id="58f95-161">**Length** returns the number of items in the object array.</span></span>  
  
```  
Function MakeList(ByVal items As Object()) As String  
   If items Is Nothing Then  
      Return Nothing  
   End If  
  
   Dim builder As System.Text.StringBuilder =   
      New System.Text.StringBuilder()  
   builder.Append("<ul>")  
  
   For Each item As Object In items  
      builder.Append("<li>")  
      builder.Append(item)  
   Next  
   builder.Append("</ul>")  
  
   Return builder.ToString()  
End Function  
  
Function Length(ByVal items as Object()) as Integer  
   If items is Nothing Then  
      Return 0  
   End If  
   Return items.Length  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="58f95-162">Exemple</span><span class="sxs-lookup"><span data-stu-id="58f95-162">Example</span></span>  
 <span data-ttu-id="58f95-163">Pour générer le code HTML, vous devez appeler la fonction.</span><span class="sxs-lookup"><span data-stu-id="58f95-163">To generate the HTML, you must call the function.</span></span> <span data-ttu-id="58f95-164">Collez l’expression suivante dans la propriété Value de la zone de texte et définissez le type de balise de texte sur HTML.</span><span class="sxs-lookup"><span data-stu-id="58f95-164">Paste the following expression in the Value property for the text box and set the markup type for text to HTML.</span></span> <span data-ttu-id="58f95-165">Pour plus d’informations, consultez [Ajouter du code HTML à un rapport &#40;Générateur de rapports et SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="58f95-165">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
```  
=Code.MakeList(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="58f95-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58f95-166">See Also</span></span>  
 <span data-ttu-id="58f95-167">[Utilisation d’expressions dans les rapports &#40;Générateur de rapport et SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="58f95-167">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="58f95-168">[Exemples d’expressions &#40;Générateur de rapports et SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="58f95-168">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="58f95-169">[Types de données dans les expressions &#40;Générateur de rapports et SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="58f95-169">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="58f95-170">Étendue des expressions pour les totaux, les agrégats et les collections intégrées &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="58f95-170">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
