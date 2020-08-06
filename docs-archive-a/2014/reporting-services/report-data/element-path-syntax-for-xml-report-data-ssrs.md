---
title: Syntaxe du chemin à l’élément pour des données de rapport XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ElementPath syntax
- XML [Reporting Services], data retrieval
ms.assetid: 07bd7a4e-fd7a-4a72-9344-3258f7c286d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b7d66b39761dc278abff25a3b22ccd18ca74272b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710240"
---
# <a name="element-path-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="de60e-102">Syntaxe du chemin d'accès à l'élément pour des données de rapport XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="de60e-102">Element Path Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="de60e-103">Dans le Concepteur de rapports, vous spécifiez les données à utiliser pour un rapport à partir d'une source de données XML en définissant un chemin d'accès à l'élément qui respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="de60e-103">In Report Designer, you specify the data to use for a report from an XML data source by defining a case-sensitive element path.</span></span> <span data-ttu-id="de60e-104">Le chemin d'accès à l'élément indique comment parcourir les nœuds hiérarchiques XML et leurs attributs dans la source de données XML.</span><span class="sxs-lookup"><span data-stu-id="de60e-104">An element path indicates how to traverse the XML hierarchical nodes and their attributes in the XML data source.</span></span> <span data-ttu-id="de60e-105">Pour utiliser le chemin d'accès à l'élément par défaut, laissez la requête du dataset ou `ElementPath` XML dans `Query` XML vide.</span><span class="sxs-lookup"><span data-stu-id="de60e-105">To use the default element path, leave the dataset query or the XML `ElementPath` of the XML `Query` empty.</span></span> <span data-ttu-id="de60e-106">Lorsque les données sont extraites de la source de données XML, les nœuds d'élément possédant des valeurs de texte et des attributs de nœud d'élément deviennent des colonnes dans le jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="de60e-106">When data is retrieved from the XML data source, element nodes that have text values and element node attributes become columns in the result set.</span></span> <span data-ttu-id="de60e-107">Les valeurs des nœuds et les attributs deviennent les données de ligne lorsque vous exécutez la requête.</span><span class="sxs-lookup"><span data-stu-id="de60e-107">The values of the nodes and attributes become the row data when you run the query.</span></span> <span data-ttu-id="de60e-108">Les colonnes apparaissent sous la forme de collection de champs de dataset dans le volet des données de rapport.</span><span class="sxs-lookup"><span data-stu-id="de60e-108">The columns appear as the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="de60e-109">Cette rubrique décrit la syntaxe du chemin d'accès à l'élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-109">This topic describes the element path syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de60e-110">La syntaxe du chemin d'accès à l'élément est indépendante de l'espace de noms.</span><span class="sxs-lookup"><span data-stu-id="de60e-110">Element path syntax is namespace-independent.</span></span> <span data-ttu-id="de60e-111">Pour utiliser des espaces de noms dans un chemin d’accès à un élément, utilisez la syntaxe de requête XML qui comprend un `ElementPath` élément XML décrit dans [syntaxe de requête XML pour les données de rapport XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de60e-111">To use namespaces in an element path, use the XML query syntax that includes an XML `ElementPath` element described in [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="de60e-112">Le tableau suivant décrit les conventions utilisées pour définir un chemin d'accès à l'élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-112">The following table describes conventions used to define an element path.</span></span>  
  
|<span data-ttu-id="de60e-113">Convention</span><span class="sxs-lookup"><span data-stu-id="de60e-113">Convention</span></span>|<span data-ttu-id="de60e-114">Utilisé pour</span><span class="sxs-lookup"><span data-stu-id="de60e-114">Used for</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="de60e-115">**gras**</span><span class="sxs-lookup"><span data-stu-id="de60e-115">**bold**</span></span>|<span data-ttu-id="de60e-116">Texte devant être tapé exactement comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="de60e-116">Text that must be typed exactly as shown.</span></span>|  
|<span data-ttu-id="de60e-117">&#124; (barre verticale)</span><span class="sxs-lookup"><span data-stu-id="de60e-117">&#124; (vertical bar)</span></span>|<span data-ttu-id="de60e-118">Sépare les éléments de la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="de60e-118">Separates syntax items.</span></span> <span data-ttu-id="de60e-119">Vous ne pouvez choisir qu'un seul de ces éléments.</span><span class="sxs-lookup"><span data-stu-id="de60e-119">You can choose only one of the items.</span></span>|  
|`[ ] (brackets)`|<span data-ttu-id="de60e-120">Éléments de syntaxe facultatifs.</span><span class="sxs-lookup"><span data-stu-id="de60e-120">Optional syntax items.</span></span> <span data-ttu-id="de60e-121">Ne tapez pas les crochets.</span><span class="sxs-lookup"><span data-stu-id="de60e-121">Do not type the brackets.</span></span>|  
|<span data-ttu-id="de60e-122">**{}** (accolades)</span><span class="sxs-lookup"><span data-stu-id="de60e-122">**{ }** (braces)</span></span>|<span data-ttu-id="de60e-123">Délimitent les paramètres des éléments de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="de60e-123">Delimits parameters of syntax items.</span></span>|  
|<span data-ttu-id="de60e-124">[ **,** ...*n*]</span><span class="sxs-lookup"><span data-stu-id="de60e-124">[**,**...*n*]</span></span>|<span data-ttu-id="de60e-125">Indique que l’élément précédent peut se répéter *n* fois.</span><span class="sxs-lookup"><span data-stu-id="de60e-125">Indicates the preceding item can be repeated *n* number of times.</span></span> <span data-ttu-id="de60e-126">Les occurrences sont séparées par des virgules.</span><span class="sxs-lookup"><span data-stu-id="de60e-126">The occurrences are separated by commas.</span></span>|  
  
## <a name="syntax"></a><span data-ttu-id="de60e-127">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="de60e-127">Syntax</span></span>  
  
```  
  
Element path ::=  
    ElementNode[/Element path]  
ElementNode ::=  
    XMLName[(Encoding)][{[FieldList]}]  
XMLName ::=  
    [NamespacePrefix:]XMLLocalName  
Encoding ::=  
        HTMLEncoded | Base64Encoded  
FieldList ::=  
    Field[,FieldList]  
Field ::=  
    Attribute | Value | Element | ElementNode  
Attribute ::=  
        @XMLName[(Type)]  
Value ::=  
        @[(Type)]  
Element ::=  
    XMLName[(Type)]  
Type ::=  
        String | Integer | Boolean | Float | Decimal | Date | XML   
NamespacePrefix ::=  
    Identifier that specifies the namespace.  
XMLLocalName :: =  
    Identifier in the XML tag.   
```  
  
## <a name="remarks"></a><span data-ttu-id="de60e-128">Notes</span><span class="sxs-lookup"><span data-stu-id="de60e-128">Remarks</span></span>  
 <span data-ttu-id="de60e-129">Le tableau suivant récapitule les termes du chemin d'accès à l'élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-129">The following table summarizes element path terms.</span></span> <span data-ttu-id="de60e-130">Les exemples du tableau font référence au document XML d'exemple Customers.xml inclus dans la section Exemples de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="de60e-130">Examples in the table refer to the example XML document Customers.xml, which is included in the Examples section of this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="de60e-131">Les balises XML respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="de60e-131">XML tags are case-sensitive.</span></span> <span data-ttu-id="de60e-132">Lorsque vous spécifiez ElementNode dans le chemin d'accès à l'élément, vous devez utiliser exactement les mêmes balises XML que celles de la source de données.</span><span class="sxs-lookup"><span data-stu-id="de60e-132">When you specify an ElementNode in the element path, you must exactly match the XML tags in the data source.</span></span>  
  
|<span data-ttu-id="de60e-133">Terme</span><span class="sxs-lookup"><span data-stu-id="de60e-133">Term</span></span>|<span data-ttu-id="de60e-134">Définition</span><span class="sxs-lookup"><span data-stu-id="de60e-134">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="de60e-135">Element path</span><span class="sxs-lookup"><span data-stu-id="de60e-135">Element path</span></span>|<span data-ttu-id="de60e-136">Définit la séquence de nœuds à parcourir dans le document XML afin de récupérer les données de champ d'un dataset avec une source de données XML.</span><span class="sxs-lookup"><span data-stu-id="de60e-136">Defines the sequence of nodes to traverse within the XML document in order to retrieve field data for a dataset with an XML data source.</span></span>|  
|`ElementNode`|<span data-ttu-id="de60e-137">Nœud XML dans le document XML.</span><span class="sxs-lookup"><span data-stu-id="de60e-137">The XML node in the XML document.</span></span> <span data-ttu-id="de60e-138">Les nœuds sont désignés par des balises et existent dans une relation hiérarchique avec d'autres nœuds.</span><span class="sxs-lookup"><span data-stu-id="de60e-138">Nodes are designated by tags and exist in a hierarchical relationship with other nodes.</span></span> <span data-ttu-id="de60e-139">Par exemple, \<Customers> est le nœud d’élément racine.</span><span class="sxs-lookup"><span data-stu-id="de60e-139">For example, \<Customers> is the root element node.</span></span> <span data-ttu-id="de60e-140">\<Customer>est un sous-élément de \<Customers> .</span><span class="sxs-lookup"><span data-stu-id="de60e-140">\<Customer> is a subelement of \<Customers>.</span></span>|  
|`XMLName`|<span data-ttu-id="de60e-141">Nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="de60e-141">The name of the node.</span></span> <span data-ttu-id="de60e-142">Par exemple, le nom du nœud Customers est Customers.</span><span class="sxs-lookup"><span data-stu-id="de60e-142">For example, the name of the Customers node is Customers.</span></span> <span data-ttu-id="de60e-143">Un `XMLName` peut porter comme préfixe un identificateur d'espace de noms qui identifie de façon unique chaque nœud.</span><span class="sxs-lookup"><span data-stu-id="de60e-143">An `XMLName` can be prefixed with a namespace identifier to uniquely name every node.</span></span>|  
|`Encoding`|<span data-ttu-id="de60e-144">Indique que `Value` pour cet élément est encodé en XML et doit être décodé et inclus en tant que sous-élément de cet élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-144">Indicates that the `Value` for this element is encoded XML and needs to be decoded and included as a subelement of this element.</span></span>|  
|`FieldList`|<span data-ttu-id="de60e-145">Définit l'ensemble des éléments et des attributs à utiliser pour récupérer des données.</span><span class="sxs-lookup"><span data-stu-id="de60e-145">Defines the set of elements and attributes to use to retrieve data.</span></span><br /><br /> <span data-ttu-id="de60e-146">Si ce terme n'est pas spécifié, tous les attributs et les sous-éléments sont utilisés comme champs.</span><span class="sxs-lookup"><span data-stu-id="de60e-146">If not specified, all attributes and subelements are used as fields.</span></span> <span data-ttu-id="de60e-147">Si la liste de champs vide est spécifiée ( **{}** ), aucun champ de ce nœud n’est utilisé.</span><span class="sxs-lookup"><span data-stu-id="de60e-147">If the empty field list is specified (**{}**), no fields from this node are used.</span></span><br /><br /> <span data-ttu-id="de60e-148">`FieldList` ne peut pas contenir à la fois `Value` et `Element` ou `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="de60e-148">A `FieldList` may not contain both a `Value` and an `Element` or `ElementNode`.</span></span>|  
|`Field`|<span data-ttu-id="de60e-149">Spécifie les données qui sont extraites en tant que champ de dataset.</span><span class="sxs-lookup"><span data-stu-id="de60e-149">Specifies the data that is retrieved as a dataset field.</span></span>|  
|`Attribute`|<span data-ttu-id="de60e-150">Paire nom-valeur dans `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="de60e-150">A name-value pair within the `ElementNode`.</span></span> <span data-ttu-id="de60e-151">Par exemple, dans le nœud d’élément \<Customer ID="1"> , `ID` est un attribut et `@ID(Integer)` retourne « 1 » comme type d’entier dans le champ de données correspondant `ID` .</span><span class="sxs-lookup"><span data-stu-id="de60e-151">For example, in the element node \<Customer ID="1">, `ID` is an attribute and `@ID(Integer)` returns "1" as an integer type in the corresponding data field `ID`.</span></span>|  
|`Value`|<span data-ttu-id="de60e-152">Valeur de l'élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-152">The value of the element.</span></span> <span data-ttu-id="de60e-153">`Value` ne peut être utilisé que sur le dernier `ElementNode` dans le chemin de l'élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-153">`Value` can only be used on the last `ElementNode` in the element path.</span></span> <span data-ttu-id="de60e-154">Par exemple, étant donné que \<Return> est un nœud terminal, si vous l’incluez à la fin d’un chemin d’accès à un élément, la valeur de `Return {@}` est `Chair` .</span><span class="sxs-lookup"><span data-stu-id="de60e-154">For example, because \<Return> is a leaf node, if you include it at the end of an element path, the value of `Return {@}` is `Chair`.</span></span>|  
|`Element`|<span data-ttu-id="de60e-155">Valeur du sous-élément nommé.</span><span class="sxs-lookup"><span data-stu-id="de60e-155">The value of the named subelement.</span></span> <span data-ttu-id="de60e-156">Par exemple, Customers {}/Customer {}/LastName récupère des valeurs pour l'élément LastName uniquement.</span><span class="sxs-lookup"><span data-stu-id="de60e-156">For example, Customers {}/Customer {}/LastName retrieves values for only the LastName element.</span></span>|  
|`Type`|<span data-ttu-id="de60e-157">Type de données facultatif utilisé pour le champ créé à partir de cet élément.</span><span class="sxs-lookup"><span data-stu-id="de60e-157">The optional data type to use for the field created from this element.</span></span>|  
|`NamespacePrefix`|<span data-ttu-id="de60e-158">`NamespacePrefix` est défini dans l'élément de requête XML.</span><span class="sxs-lookup"><span data-stu-id="de60e-158">`NamespacePrefix` is defined in the XML Query element.</span></span> <span data-ttu-id="de60e-159">S'il n'existe aucun élément de requête XML, les espaces de noms dans `ElementPath` XML sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="de60e-159">If no XML Query element exists, namespaces in the XML `ElementPath` are ignored.</span></span> <span data-ttu-id="de60e-160">S'il existe un élément de requête XML, `ElementPath` XML possède un attribut `IgnoreNamespaces` facultatif.</span><span class="sxs-lookup"><span data-stu-id="de60e-160">If there is an XML Query element, the XML `ElementPath` has an optional attribute `IgnoreNamespaces`.</span></span> <span data-ttu-id="de60e-161">Si IgnoreNamespaces a `true` la la, les espaces de noms dans le XML `ElementPath` et le document XML sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="de60e-161">If IgnoreNamespaces is `true`, namespaces in the XML `ElementPath` and the XML document are ignored.</span></span> <span data-ttu-id="de60e-162">Pour plus d’informations, consultez [Syntaxe de requête XML pour les données de rapport XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="de60e-162">For more information, see [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>|  
  
## <a name="example---no-namespaces"></a><span data-ttu-id="de60e-163">Exemples - Aucun espace de noms</span><span class="sxs-lookup"><span data-stu-id="de60e-163">Example - No Namespaces</span></span>  
 <span data-ttu-id="de60e-164">Les exemples suivants utilisent le document XML Customers.xml.</span><span class="sxs-lookup"><span data-stu-id="de60e-164">The following examples use the XML document Customers.xml.</span></span> <span data-ttu-id="de60e-165">Ce tableau présente des exemples de syntaxe du chemin d'accès à l'élément et les résultats de l'utilisation du chemin d'accès à l'élément dans une requête qui définit un dataset, en fonction du document XML comme source de données.</span><span class="sxs-lookup"><span data-stu-id="de60e-165">This table shows examples of element path syntax and the results of using the element path in a query that defines a dataset, based on the XML document as a data source.</span></span>  
  
 <span data-ttu-id="de60e-166">Notez que lorsque le chemin d’accès à l’élément est vide, la requête utilise le chemin d’accès à l’élément par défaut : le premier chemin d’accès à une collection de nœuds feuille.</span><span class="sxs-lookup"><span data-stu-id="de60e-166">Note that when the element path is empty, the query uses the default element path: the first path to a leaf node collection.</span></span> <span data-ttu-id="de60e-167">Dans le premier exemple, laisser un chemin d'accès à l'élément vide équivaut à spécifier le chemin d'accès à l'élément /Customers/Customer/Orders/Order.</span><span class="sxs-lookup"><span data-stu-id="de60e-167">In the first example, leaving the element path empty is equivalent to specifying the element path /Customers/Customer/Orders/Order.</span></span> <span data-ttu-id="de60e-168">L'ensemble des attributs et des valeurs de nœud, ainsi que le chemin d'accès, sont retournés dans le jeu de résultats, et les noms de nœuds et les noms d'attributs apparaissent en tant que champs du dataset.</span><span class="sxs-lookup"><span data-stu-id="de60e-168">All node value and attributes along the path are returned in the result set, and the node names and attributes names appear as dataset fields.</span></span>  
  
-   <span data-ttu-id="de60e-169">*Vide*</span><span class="sxs-lookup"><span data-stu-id="de60e-169">*Empty*</span></span>  
  
    |<span data-ttu-id="de60e-170">JSON</span><span class="sxs-lookup"><span data-stu-id="de60e-170">Order</span></span>|<span data-ttu-id="de60e-171">Qté</span><span class="sxs-lookup"><span data-stu-id="de60e-171">Qty</span></span>|<span data-ttu-id="de60e-172">id</span><span class="sxs-lookup"><span data-stu-id="de60e-172">ID</span></span>|<span data-ttu-id="de60e-173">FirstName</span><span class="sxs-lookup"><span data-stu-id="de60e-173">FirstName</span></span>|<span data-ttu-id="de60e-174">LastName</span><span class="sxs-lookup"><span data-stu-id="de60e-174">LastName</span></span>|<span data-ttu-id="de60e-175">Customer.ID</span><span class="sxs-lookup"><span data-stu-id="de60e-175">Customer.ID</span></span>|<span data-ttu-id="de60e-176">xmlns</span><span class="sxs-lookup"><span data-stu-id="de60e-176">xmlns</span></span>|  
    |-----------|---------|--------|---------------|--------------|-----------------|-----------|  
    |<span data-ttu-id="de60e-177">Chair</span><span class="sxs-lookup"><span data-stu-id="de60e-177">Chair</span></span>|<span data-ttu-id="de60e-178">6</span><span class="sxs-lookup"><span data-stu-id="de60e-178">6</span></span>|<span data-ttu-id="de60e-179">1</span><span class="sxs-lookup"><span data-stu-id="de60e-179">1</span></span>|<span data-ttu-id="de60e-180">Bobby</span><span class="sxs-lookup"><span data-stu-id="de60e-180">Bobby</span></span>|<span data-ttu-id="de60e-181">Moore</span><span class="sxs-lookup"><span data-stu-id="de60e-181">Moore</span></span>|<span data-ttu-id="de60e-182">11</span><span class="sxs-lookup"><span data-stu-id="de60e-182">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="de60e-183">Table de charge de travail</span><span class="sxs-lookup"><span data-stu-id="de60e-183">Table</span></span>|<span data-ttu-id="de60e-184">1</span><span class="sxs-lookup"><span data-stu-id="de60e-184">1</span></span>|<span data-ttu-id="de60e-185">2</span><span class="sxs-lookup"><span data-stu-id="de60e-185">2</span></span>|<span data-ttu-id="de60e-186">Bobby</span><span class="sxs-lookup"><span data-stu-id="de60e-186">Bobby</span></span>|<span data-ttu-id="de60e-187">Moore</span><span class="sxs-lookup"><span data-stu-id="de60e-187">Moore</span></span>|<span data-ttu-id="de60e-188">11</span><span class="sxs-lookup"><span data-stu-id="de60e-188">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="de60e-189">Sofa</span><span class="sxs-lookup"><span data-stu-id="de60e-189">Sofa</span></span>|<span data-ttu-id="de60e-190">2</span><span class="sxs-lookup"><span data-stu-id="de60e-190">2</span></span>|<span data-ttu-id="de60e-191">8</span><span class="sxs-lookup"><span data-stu-id="de60e-191">8</span></span>|<span data-ttu-id="de60e-192">Crystal</span><span class="sxs-lookup"><span data-stu-id="de60e-192">Crystal</span></span>|<span data-ttu-id="de60e-193">Hu</span><span class="sxs-lookup"><span data-stu-id="de60e-193">Hu</span></span>|<span data-ttu-id="de60e-194">20</span><span class="sxs-lookup"><span data-stu-id="de60e-194">20</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="de60e-195">EndTables</span><span class="sxs-lookup"><span data-stu-id="de60e-195">EndTables</span></span>|<span data-ttu-id="de60e-196">2</span><span class="sxs-lookup"><span data-stu-id="de60e-196">2</span></span>|<span data-ttu-id="de60e-197">15</span><span class="sxs-lookup"><span data-stu-id="de60e-197">15</span></span>|<span data-ttu-id="de60e-198">Wyatt</span><span class="sxs-lookup"><span data-stu-id="de60e-198">Wyatt</span></span>|<span data-ttu-id="de60e-199">Diaz</span><span class="sxs-lookup"><span data-stu-id="de60e-199">Diaz</span></span>|<span data-ttu-id="de60e-200">33</span><span class="sxs-lookup"><span data-stu-id="de60e-200">33</span></span>|http://www.adventure-works.com|  
  
-   `Customers {}/Customer`  
  
    |<span data-ttu-id="de60e-201">FirstName</span><span class="sxs-lookup"><span data-stu-id="de60e-201">FirstName</span></span>|<span data-ttu-id="de60e-202">LastName</span><span class="sxs-lookup"><span data-stu-id="de60e-202">LastName</span></span>|<span data-ttu-id="de60e-203">id</span><span class="sxs-lookup"><span data-stu-id="de60e-203">ID</span></span>|  
    |---------------|--------------|--------|  
    |<span data-ttu-id="de60e-204">Bobby</span><span class="sxs-lookup"><span data-stu-id="de60e-204">Bobby</span></span>|<span data-ttu-id="de60e-205">Moore</span><span class="sxs-lookup"><span data-stu-id="de60e-205">Moore</span></span>|<span data-ttu-id="de60e-206">11</span><span class="sxs-lookup"><span data-stu-id="de60e-206">11</span></span>|  
    |<span data-ttu-id="de60e-207">Crystal</span><span class="sxs-lookup"><span data-stu-id="de60e-207">Crystal</span></span>|<span data-ttu-id="de60e-208">Hu</span><span class="sxs-lookup"><span data-stu-id="de60e-208">Hu</span></span>|<span data-ttu-id="de60e-209">20</span><span class="sxs-lookup"><span data-stu-id="de60e-209">20</span></span>|  
    |<span data-ttu-id="de60e-210">Wyatt</span><span class="sxs-lookup"><span data-stu-id="de60e-210">Wyatt</span></span>|<span data-ttu-id="de60e-211">Diaz</span><span class="sxs-lookup"><span data-stu-id="de60e-211">Diaz</span></span>|<span data-ttu-id="de60e-212">33</span><span class="sxs-lookup"><span data-stu-id="de60e-212">33</span></span>|  
  
-   `Customers {}/Customer {}/LastName`  
  
    |<span data-ttu-id="de60e-213">LastName</span><span class="sxs-lookup"><span data-stu-id="de60e-213">LastName</span></span>|  
    |--------------|  
    |<span data-ttu-id="de60e-214">Moore</span><span class="sxs-lookup"><span data-stu-id="de60e-214">Moore</span></span>|  
    |<span data-ttu-id="de60e-215">Hu</span><span class="sxs-lookup"><span data-stu-id="de60e-215">Hu</span></span>|  
    |<span data-ttu-id="de60e-216">Diaz</span><span class="sxs-lookup"><span data-stu-id="de60e-216">Diaz</span></span>|  
  
-   `Customers {}/Customer {}/Orders/Order {@,@Qty}`  
  
    |<span data-ttu-id="de60e-217">JSON</span><span class="sxs-lookup"><span data-stu-id="de60e-217">Order</span></span>|<span data-ttu-id="de60e-218">Qté</span><span class="sxs-lookup"><span data-stu-id="de60e-218">Qty</span></span>|  
    |-----------|---------|  
    |<span data-ttu-id="de60e-219">Chair</span><span class="sxs-lookup"><span data-stu-id="de60e-219">Chair</span></span>|<span data-ttu-id="de60e-220">6</span><span class="sxs-lookup"><span data-stu-id="de60e-220">6</span></span>|  
    |<span data-ttu-id="de60e-221">Table de charge de travail</span><span class="sxs-lookup"><span data-stu-id="de60e-221">Table</span></span>|<span data-ttu-id="de60e-222">1</span><span class="sxs-lookup"><span data-stu-id="de60e-222">1</span></span>|  
    |<span data-ttu-id="de60e-223">Sofa</span><span class="sxs-lookup"><span data-stu-id="de60e-223">Sofa</span></span>|<span data-ttu-id="de60e-224">2</span><span class="sxs-lookup"><span data-stu-id="de60e-224">2</span></span>|  
    |<span data-ttu-id="de60e-225">EndTables</span><span class="sxs-lookup"><span data-stu-id="de60e-225">EndTables</span></span>|<span data-ttu-id="de60e-226">2</span><span class="sxs-lookup"><span data-stu-id="de60e-226">2</span></span>|  
  
-   `Customers {}/Customer/Orders/Order{ @ID(Integer)}`  
  
    |<span data-ttu-id="de60e-227">Order.ID</span><span class="sxs-lookup"><span data-stu-id="de60e-227">Order.ID</span></span>|<span data-ttu-id="de60e-228">FirstName</span><span class="sxs-lookup"><span data-stu-id="de60e-228">FirstName</span></span>|<span data-ttu-id="de60e-229">LastName</span><span class="sxs-lookup"><span data-stu-id="de60e-229">LastName</span></span>|<span data-ttu-id="de60e-230">id</span><span class="sxs-lookup"><span data-stu-id="de60e-230">ID</span></span>|  
    |--------------|---------------|--------------|--------|  
    |<span data-ttu-id="de60e-231">1</span><span class="sxs-lookup"><span data-stu-id="de60e-231">1</span></span>|<span data-ttu-id="de60e-232">Bobby</span><span class="sxs-lookup"><span data-stu-id="de60e-232">Bobby</span></span>|<span data-ttu-id="de60e-233">Moore</span><span class="sxs-lookup"><span data-stu-id="de60e-233">Moore</span></span>|<span data-ttu-id="de60e-234">11</span><span class="sxs-lookup"><span data-stu-id="de60e-234">11</span></span>|  
    |<span data-ttu-id="de60e-235">2</span><span class="sxs-lookup"><span data-stu-id="de60e-235">2</span></span>|<span data-ttu-id="de60e-236">Bobby</span><span class="sxs-lookup"><span data-stu-id="de60e-236">Bobby</span></span>|<span data-ttu-id="de60e-237">Moore</span><span class="sxs-lookup"><span data-stu-id="de60e-237">Moore</span></span>|<span data-ttu-id="de60e-238">11</span><span class="sxs-lookup"><span data-stu-id="de60e-238">11</span></span>|  
    |<span data-ttu-id="de60e-239">8</span><span class="sxs-lookup"><span data-stu-id="de60e-239">8</span></span>|<span data-ttu-id="de60e-240">Crystal</span><span class="sxs-lookup"><span data-stu-id="de60e-240">Crystal</span></span>|<span data-ttu-id="de60e-241">Hu</span><span class="sxs-lookup"><span data-stu-id="de60e-241">Hu</span></span>|<span data-ttu-id="de60e-242">20</span><span class="sxs-lookup"><span data-stu-id="de60e-242">20</span></span>|  
    |<span data-ttu-id="de60e-243">15</span><span class="sxs-lookup"><span data-stu-id="de60e-243">15</span></span>|<span data-ttu-id="de60e-244">Wyatt</span><span class="sxs-lookup"><span data-stu-id="de60e-244">Wyatt</span></span>|<span data-ttu-id="de60e-245">Diaz</span><span class="sxs-lookup"><span data-stu-id="de60e-245">Diaz</span></span>|<span data-ttu-id="de60e-246">33</span><span class="sxs-lookup"><span data-stu-id="de60e-246">33</span></span>|  
  
#### <a name="xml-document-customersxml"></a><span data-ttu-id="de60e-247">Document XML : Customers.xml</span><span class="sxs-lookup"><span data-stu-id="de60e-247">XML document: Customers.xml</span></span>  
 <span data-ttu-id="de60e-248">Pour vous entraîner avec les exemples de chemin d’élément présentés dans la section précédente, vous pouvez copier ce code XML et l’enregistrer dans une URL à laquelle le Concepteur de rapports peut accéder, puis utiliser le document XML comme source de données XML : par exemple, `http://localhost/Customers.xml`.</span><span class="sxs-lookup"><span data-stu-id="de60e-248">To try out the element path examples in the previous section, you can copy this XML and save it to a URL that is accessible by Report Designer, and then use the XML document as an XML data source: for example, `http://localhost/Customers.xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<Customers xmlns="http://www.adventure-works.com">  
   <Customer ID="11">  
      <FirstName>Bobby</FirstName>  
      <LastName>Moore</LastName>  
      <Orders>  
         <Order ID="1" Qty="6">Chair</Order>  
         <Order ID="2" Qty="1">Table</Order>  
      </Orders>  
      <Returns>  
         <Return ID="1" Qty="2">Chair</Return>  
      </Returns>  
   </Customer>  
   <Customer ID="20">  
      <FirstName>Crystal</FirstName>  
      <LastName>Hu</LastName>  
      <Orders>  
         <Order ID="8" Qty="2">Sofa</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
   <Customer ID="33">  
      <FirstName>Wyatt</FirstName>  
      <LastName>Diaz</LastName>  
      <Orders>  
         <Order ID="15" Qty="2">EndTables</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
</Customers>  
```  
  
 <span data-ttu-id="de60e-249">Vous pouvez également créer une source de données XML ne possédant aucune chaîne de connexion et incorporer Customers.XML dans la requête à l'aide de la procédure suivante :</span><span class="sxs-lookup"><span data-stu-id="de60e-249">Alternatively, you can create an XML data source that has no connection string and embed Customers.XML in the query, using the following procedure:</span></span>  
  
###### <a name="to-embed-customersxml-in-a-query"></a><span data-ttu-id="de60e-250">Pour incorporer Customers.XML dans une requête</span><span class="sxs-lookup"><span data-stu-id="de60e-250">To embed Customers.XML in a query</span></span>  
  
1.  <span data-ttu-id="de60e-251">Créez une source de données XML avec une chaîne de connexion vide.</span><span class="sxs-lookup"><span data-stu-id="de60e-251">Create an XML data source with a blank connection string.</span></span>  
  
2.  <span data-ttu-id="de60e-252">Créez un dataset pour la source de données XML.</span><span class="sxs-lookup"><span data-stu-id="de60e-252">Create a new dataset for the XML data source.</span></span>  
  
3.  <span data-ttu-id="de60e-253">Dans la boîte de dialogue **Propriétés du dataset** , cliquez sur **Concepteur de requêtes**.</span><span class="sxs-lookup"><span data-stu-id="de60e-253">In the **Dataset Properties** dialog box, click **Query Designer**.</span></span> <span data-ttu-id="de60e-254">La boîte de dialogue du concepteur de requêtes textuelles s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="de60e-254">The text-based query designer dialog box opens.</span></span>  
  
4.  <span data-ttu-id="de60e-255">Dans le volet de requête, entrez les deux lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="de60e-255">In the query pane, enter the following two lines:</span></span>  
  
     `<Query>`  
  
     `<XmlData>`  
  
5.  <span data-ttu-id="de60e-256">Copiez Customers.XML et collez le texte dans le volet de requête après `<XmlData>`.</span><span class="sxs-lookup"><span data-stu-id="de60e-256">Copy Customers.XML and paste the text in the query pane after `<XmlData>`.</span></span>  
  
6.  <span data-ttu-id="de60e-257">Dans le volet de requête, supprimez la première ligne que vous avez copiée à partir de Customers.XML : `<?xml version="1.0"?>`</span><span class="sxs-lookup"><span data-stu-id="de60e-257">In the query pane, delete the first line that you copied from Customers.XML: `<?xml version="1.0"?>`</span></span>  
  
7.  <span data-ttu-id="de60e-258">À la fin de la requête, ajoutez les deux lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="de60e-258">At the end of the query, add the following two lines:</span></span>  
  
     `<XmlData>`  
  
     `<Query>`  
  
8.  <span data-ttu-id="de60e-259">Cliquez sur **Exécuter la requête** .</span><span class="sxs-lookup"><span data-stu-id="de60e-259">Click **Run Query** (!).</span></span>  
  
     <span data-ttu-id="de60e-260">Le jeu de résultats affiche 4 lignes de données avec les colonnes suivantes : `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span><span class="sxs-lookup"><span data-stu-id="de60e-260">The result set displays 4 lines of data with the following columns: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de60e-261">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de60e-261">See Also</span></span>  
 <span data-ttu-id="de60e-262">[Type de connexion XML &#40;&#41;SSRS](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de60e-262">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 <span data-ttu-id="de60e-263">[Didacticiels de Reporting Services &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="de60e-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span></span>  
 [<span data-ttu-id="de60e-264">Ajouter, modifier ou actualiser des champs dans le volet des données de rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="de60e-264">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
  
