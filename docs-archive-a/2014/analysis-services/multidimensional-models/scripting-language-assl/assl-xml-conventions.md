---
title: Conventions XML ASSL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- whitespace [Analysis Services Scripting Language]
- trailing whitespace
- XSD data types [Analysis Services Scripting Language]
- inheritance [Analysis Services Scripting Language]
- cardinality [Analysis Services Scripting Language]
- white space [Analysis Services Scripting Language]
- ASSL, XML conventions
- defaults [Analysis Services Scripting Language]
- leading whitespace
- Analysis Services Scripting Language, XML conventions
- XML [Analysis Services Scripting Language]
- hierarchies [Analysis Services Scripting Language]
- inherited defaults [Analysis Services Scripting Language]
ms.assetid: bce4edad-4420-41ce-9672-8c00c5c0dec6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9b70742b07fd6450b01cf205147a05f40c4b6121
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705556"
---
# <a name="assl-xml-conventions"></a><span data-ttu-id="57802-102">Conventions ASSL XML</span><span class="sxs-lookup"><span data-stu-id="57802-102">ASSL XML Conventions</span></span>
  <span data-ttu-id="57802-103">Le langage de script ASSL (Analysis Services Scripting Language) représente la hiérarchie d'objets comme un ensemble de types d'élément, chacun d'entre eux définissant les éléments enfants qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="57802-103">Analysis Services Scripting Language (ASSL) represents the hierarchy of objects as a set of element types, each of which defines the child elements they can contain.</span></span>  
  
 <span data-ttu-id="57802-104">Pour représenter la hiérarchie d'objets, ASSL utilise les conventions XML suivantes :</span><span class="sxs-lookup"><span data-stu-id="57802-104">To represent the object hierarchy, ASSL uses the following XML conventions:</span></span>  
  
-   <span data-ttu-id="57802-105">Tous les objets et propriétés sont représentés en tant qu’éléments, à l’exception des attributs XML standard tels que « XML : lang ».</span><span class="sxs-lookup"><span data-stu-id="57802-105">All objects and properties are represented as elements, except for standard XML attributes such as 'xml:lang'.</span></span>  
  
-   <span data-ttu-id="57802-106">Les noms d'élément et les valeurs d'énumération suivent la convention d'affectation de noms Microsoft .NET Framework, à savoir, une casse Pascal sans traits de soulignement.</span><span class="sxs-lookup"><span data-stu-id="57802-106">Both element names and enumeration values follow the Microsoft .NET Framework naming convention of Pascal casing with no underscores.</span></span>  
  
-   <span data-ttu-id="57802-107">La casse de toutes les valeurs est préservée.</span><span class="sxs-lookup"><span data-stu-id="57802-107">The case of all values is preserved.</span></span> <span data-ttu-id="57802-108">Les valeurs des énumérations respectent également la casse.</span><span class="sxs-lookup"><span data-stu-id="57802-108">Values for enumerations are also case-sensitive.</span></span>  
  
 <span data-ttu-id="57802-109">En plus de cette liste de conventions, Analysis Services suit également certaines conventions en matière de cardinalité, d'héritage, d'espaces, de types de données et de valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="57802-109">In addition to this list of conventions, Analysis Services also follows certain conventions regarding cardinality, inheritance, whitespace, data types, and default values.</span></span>  
  
## <a name="cardinality"></a><span data-ttu-id="57802-110">Cardinalité</span><span class="sxs-lookup"><span data-stu-id="57802-110">Cardinality</span></span>  
 <span data-ttu-id="57802-111">Lorsque la cardinalité d'un élément est supérieure à 1, cela signifie qu'il existe une collection d'éléments XML qui englobe cet élément.</span><span class="sxs-lookup"><span data-stu-id="57802-111">When an element has a cardinality that is greater than 1, there is an XML element collection that encapsulates this element.</span></span> <span data-ttu-id="57802-112">Le nom de la collection correspond à la forme plurielle des éléments contenus dans la collection.</span><span class="sxs-lookup"><span data-stu-id="57802-112">The name of collection uses the plural form of the elements contained in the collection.</span></span> <span data-ttu-id="57802-113">Par exemple, le fragment XML suivant représente la collection `Dimensions` au sein d'un élément `Database` :</span><span class="sxs-lookup"><span data-stu-id="57802-113">For example, the following XML fragment represents the `Dimensions` collection within a `Database` element:</span></span>  
  
 `<Database>`  
  
 `...`  
  
 `<Dimensions>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `...`  
  
 `</Dimension>`  
  
 `</Dimensions>`  
  
 `</Database>`  
  
 ``  
  
 <span data-ttu-id="57802-114">L'ordre d'apparition des éléments n'a pas d'importance.</span><span class="sxs-lookup"><span data-stu-id="57802-114">The order in which elements appear is unimportant.</span></span>  
  
## <a name="inheritance"></a><span data-ttu-id="57802-115">Héritage</span><span class="sxs-lookup"><span data-stu-id="57802-115">Inheritance</span></span>  
 <span data-ttu-id="57802-116">L'héritage est utilisé lorsqu'il existe des objets distincts dont les ensembles de propriétés se chevauchent en dépit de leur différence très marquée.</span><span class="sxs-lookup"><span data-stu-id="57802-116">Inheritance is used when there are distinct objects that have overlapping but significantly different sets of properties.</span></span> <span data-ttu-id="57802-117">Les cubes virtuels, les cubes liés et les cubes réguliers sont des exemples d'objets qui se chevauchent malgré leurs différences.</span><span class="sxs-lookup"><span data-stu-id="57802-117">Examples of such overlapping but distinct objects are virtual cubes, linked cubes, and regular cubes.</span></span> <span data-ttu-id="57802-118">Pour les objets distincts qui se chevauchent, Analysis Services fait appel à l'attribut `type` standard de l'espace de noms d'instances XML pour indiquer l'héritage.</span><span class="sxs-lookup"><span data-stu-id="57802-118">For overlapping but distinct object, Analysis Services uses the standard `type` attribute from the XML Instance Namespace to indicate the inheritance.</span></span> <span data-ttu-id="57802-119">Par exemple, le fragment XML suivant indique comment l'attribut `type` détermine si un élément `Cube` hérite d'un cube régulier ou d'un cube virtuel :</span><span class="sxs-lookup"><span data-stu-id="57802-119">For example, the following XML fragment shows how the `type` attribute identifies whether a `Cube` element inherits from a regular cube or from a virtual cube:</span></span>  
  
 `<Cubes>`  
  
 `<Cube xsi:type="RegularCube">`  
  
 `<Name>Sales</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `<Cube xsi:type="VirtualCube">`  
  
 `<Name>SalesAndInventory</Name>`  
  
 `...`  
  
 `</Cube>`  
  
 `</Cubes>`  
  
 ``  
  
 <span data-ttu-id="57802-120">En règle générale, l'héritage n'est pas utilisé lorsque plusieurs types partagent un même nom de propriété.</span><span class="sxs-lookup"><span data-stu-id="57802-120">Inheritance is generally not used when multiple types have a property of the same name.</span></span> <span data-ttu-id="57802-121">Par exemple, les propriétés `Name` et `ID` apparaissent dans de nombreux éléments, mais ces propriétés n'ont pas été promues en type abstrait.</span><span class="sxs-lookup"><span data-stu-id="57802-121">For example, the `Name` and `ID` properties appear on many elements, but these properties have not been promoted to an abstract type.</span></span>  
  
## <a name="whitespace"></a><span data-ttu-id="57802-122">Espaces</span><span class="sxs-lookup"><span data-stu-id="57802-122">Whitespace</span></span>  
 <span data-ttu-id="57802-123">Les espaces contenus dans la valeur d'un élément sont conservés.</span><span class="sxs-lookup"><span data-stu-id="57802-123">Whitespace within an element value is preserved.</span></span> <span data-ttu-id="57802-124">Toutefois, les espaces de début et de fin sont toujours supprimés.</span><span class="sxs-lookup"><span data-stu-id="57802-124">However, leading and trailing whitespace is always trimmed.</span></span> <span data-ttu-id="57802-125">Par exemple, les éléments suivants comportent le même texte, mais le nombre d'espaces contenus dans le texte varie d'un élément à un autre, si bien que leurs valeurs sont considérées comme étant différentes :</span><span class="sxs-lookup"><span data-stu-id="57802-125">For example, the following elements have the same text but differing amounts of whitespace within that text, and are therefore treated as if they have different values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>My  text<Description>`  
  
 ``  
  
 <span data-ttu-id="57802-126">Toutefois, les éléments suivants ne se distinguent qu'au niveau des espaces de début et de fin. Ils sont donc considérés comme des valeurs équivalentes :</span><span class="sxs-lookup"><span data-stu-id="57802-126">However, the following elements vary only in leading and trailing whitespace, and are therefore treated as if they have equivalent values:</span></span>  
  
 `<Description>My text<Description>`  
  
 `<Description>  My text  <Description>`  
  
 ``  
  
## <a name="data-types"></a><span data-ttu-id="57802-127">Types de données</span><span class="sxs-lookup"><span data-stu-id="57802-127">Data Types</span></span>  
 <span data-ttu-id="57802-128">Analysis Services utilise les types de données XSD (XML Schema definition language) standard suivants :</span><span class="sxs-lookup"><span data-stu-id="57802-128">Analysis Services uses the following standard XML Schema definition language (XSD) data types:</span></span>  
  
 `Int`  
 <span data-ttu-id="57802-129">Valeur entière comprise entre-231 et 231-1.</span><span class="sxs-lookup"><span data-stu-id="57802-129">An integer value in the range of -231 to 231 - 1.</span></span>  
  
 `Long`  
 <span data-ttu-id="57802-130">Valeur entière comprise entre-263 et 263-1.</span><span class="sxs-lookup"><span data-stu-id="57802-130">An integer value in range of -263 to 263 - 1.</span></span>  
  
 `String`  
 <span data-ttu-id="57802-131">Valeur de chaîne conforme aux règles globales suivantes :</span><span class="sxs-lookup"><span data-stu-id="57802-131">A string value that conforms to the following global rules:</span></span>  
  
-   <span data-ttu-id="57802-132">les caractères de contrôle sont supprimés ;</span><span class="sxs-lookup"><span data-stu-id="57802-132">Control characters are stripped out.</span></span>  
  
-   <span data-ttu-id="57802-133">les espaces de début et de fin sont supprimés ;</span><span class="sxs-lookup"><span data-stu-id="57802-133">Leading and trailing white space is trimmed.</span></span>  
  
-   <span data-ttu-id="57802-134">les espaces internes sont conservés.</span><span class="sxs-lookup"><span data-stu-id="57802-134">Internal white space is preserved.</span></span>  
  
 <span data-ttu-id="57802-135">Les propriétés `Name` et `ID` imposent des limitations spéciales en matière de validité des caractères dans les éléments de chaîne.</span><span class="sxs-lookup"><span data-stu-id="57802-135">`Name` and `ID` properties have special limitations on valid characters in string elements.</span></span> <span data-ttu-id="57802-136">Pour plus d’informations sur `Name` les `ID` conventions et, consultez [objets ASSL et caractéristiques](assl-objects-and-object-characteristics.md)de l’objet.</span><span class="sxs-lookup"><span data-stu-id="57802-136">For additional information about `Name` and `ID` conventions, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
 `DateTime`  
 <span data-ttu-id="57802-137">`DateTime`Structure de l' .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="57802-137">A `DateTime` structure from the .NET Framework.</span></span> <span data-ttu-id="57802-138">Une valeur `DateTime` ne peut pas être NULL.</span><span class="sxs-lookup"><span data-stu-id="57802-138">A `DateTime` value cannot be NULL.</span></span> <span data-ttu-id="57802-139">La date la plus reculée prise en charge par le type de données `DataTime` est le 1er janvier 1601, qui est accessible aux programmeurs via `DateTime.MinValue`.</span><span class="sxs-lookup"><span data-stu-id="57802-139">The lowest date supported by the `DataTime` data type is January 1, 1601, which is available to programmers as `DateTime.MinValue`.</span></span> <span data-ttu-id="57802-140">La présence de cette date indique qu'il manque une valeur `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="57802-140">The lowest supported date indicates that a `DateTime` value is missing.</span></span>  
  
 `Boolean`  
 <span data-ttu-id="57802-141">Énumération constituée de seulement deux valeurs, telles que {true, false} ou {0, 1}.</span><span class="sxs-lookup"><span data-stu-id="57802-141">An enumeration with only two values, such as {true, false} or {0, 1}.</span></span>  
  
## <a name="default-values"></a><span data-ttu-id="57802-142">Valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="57802-142">Default Values</span></span>  
 <span data-ttu-id="57802-143">Analysis Services prend en charge les valeurs par défaut répertoriées dans la table suivante :</span><span class="sxs-lookup"><span data-stu-id="57802-143">Analysis Services uses the defaults listed in the following table.</span></span>  
  
|<span data-ttu-id="57802-144">Type de données XML</span><span class="sxs-lookup"><span data-stu-id="57802-144">XML data type</span></span>|<span data-ttu-id="57802-145">Valeur par défaut</span><span class="sxs-lookup"><span data-stu-id="57802-145">Default value</span></span>|  
|-------------------|-------------------|  
|`Boolean`|<span data-ttu-id="57802-146">False</span><span class="sxs-lookup"><span data-stu-id="57802-146">False</span></span>|  
|`String`|<span data-ttu-id="57802-147">"" (chaîne vide)</span><span class="sxs-lookup"><span data-stu-id="57802-147">"" (empty string)</span></span>|  
|<span data-ttu-id="57802-148">`Integer` ou `Long`</span><span class="sxs-lookup"><span data-stu-id="57802-148">`Integer` or `Long`</span></span>|<span data-ttu-id="57802-149">0 (zéro)</span><span class="sxs-lookup"><span data-stu-id="57802-149">0 (zero)</span></span>|  
|`Timestamp`|<span data-ttu-id="57802-150">12:00:00 AM, 1/1/0001 (correspondant à un .NET Framework `System.DateTime` avec 0 graduations)</span><span class="sxs-lookup"><span data-stu-id="57802-150">12:00:00 AM, 1/1/0001 (corresponding to a the .NET Frameworks `System.DateTime` with 0 ticks)</span></span>|  
  
 <span data-ttu-id="57802-151">Un élément qui est présent mais vide est considéré comme ayant une valeur de chaîne null, et non la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="57802-151">An element that is present but empty is interpreted as having a value of a null string, not the default value.</span></span>  
  
### <a name="inherited-defaults"></a><span data-ttu-id="57802-152">Valeurs par défaut héritées</span><span class="sxs-lookup"><span data-stu-id="57802-152">Inherited Defaults</span></span>  
 <span data-ttu-id="57802-153">Certaines propriétés définies au niveau d'un objet fournissent les valeurs par défaut des mêmes propriétés au niveau des objets enfants ou descendants.</span><span class="sxs-lookup"><span data-stu-id="57802-153">Some properties that are specified on an object provide default values for the same property on child or descendant objects.</span></span> <span data-ttu-id="57802-154">Par exemple, `Cube.StorageMode` fournit la valeur par défaut de `Partition.StorageMode`.</span><span class="sxs-lookup"><span data-stu-id="57802-154">For example, `Cube.StorageMode` provides the default value for `Partition.StorageMode`.</span></span> <span data-ttu-id="57802-155">Les règles qu'Analysis Services applique pour les valeurs par défaut héritées sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="57802-155">The rules that Analysis Services applies for inherited default values are as follows:</span></span>  
  
-   <span data-ttu-id="57802-156">Lorsque la propriété de l'objet enfant a la valeur NULL dans l'élément XML, sa valeur par défaut est la valeur héritée.</span><span class="sxs-lookup"><span data-stu-id="57802-156">When the property for the child object is null in the XML, its value defaults to the inherited value.</span></span> <span data-ttu-id="57802-157">Toutefois, si vous interrogez le serveur à propos de la valeur, le serveur renvoie la valeur NULL de l'élément XML.</span><span class="sxs-lookup"><span data-stu-id="57802-157">However, if you query the value from the server, the server returns the null value of the XML element.</span></span>  
  
-   <span data-ttu-id="57802-158">Il n'est pas possible de déterminer par programme si la propriété d'un objet enfant a été définie directement sur l'objet enfant ou héritée.</span><span class="sxs-lookup"><span data-stu-id="57802-158">It is not possible to determine programmatically whether the property of a child object has been set directly on the child object or inherited.</span></span>  
  
 <span data-ttu-id="57802-159">Certains éléments possèdent des valeurs par défaut définies qui s'appliquent lorsque ces éléments sont manquants.</span><span class="sxs-lookup"><span data-stu-id="57802-159">Some elements have defined defaults that apply when the element is missing.</span></span> <span data-ttu-id="57802-160">Par exemple, dans le fragment XML suivant, les éléments `Dimension` sont équivalents bien qu'un élément `Dimension` contienne un élément `Visible` mais que l'autre élément `Dimension` n'en contient pas.</span><span class="sxs-lookup"><span data-stu-id="57802-160">For example, the `Dimension` elements in the following XML fragment are equivalent even though one `Dimension` element contains a `Visible` element, but the other `Dimension` element does not.</span></span>  
  
 `<Dimension>`  
  
 `<Name>Product</Name>`  
  
 `</Dimension>`  
  
 `<Dimension>`  
  
 `<Name>Product</ Name>`  
  
 `<Visible>true</Visible>`  
  
 `</Dimension>`  
  
 <span data-ttu-id="57802-161">Pour plus d’informations sur les valeurs par défaut héritées, consultez [objets ASSL et caractéristiques](assl-objects-and-object-characteristics.md)de l’objet.</span><span class="sxs-lookup"><span data-stu-id="57802-161">For more information on inherited defaults, see [ASSL Objects and Object Characteristics](assl-objects-and-object-characteristics.md).</span></span>  
  
  
