---
title: Utilisation d’annotations dans les schémas XSD (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, about annotated XSD schemas
- annotations [SQLXML]
- relationships [SQLXML]
- relationships [SQLXML], hierarchical relationships
- hierarchical relationships [SQLXML]
- mapping schema [SQLXML], scenarios for using
ms.assetid: 78f318a4-7a36-473b-9852-a4bae6940ce5
author: rothja
ms.author: jroth
ms.openlocfilehash: e2be94aa5815593d7a5a2e0c00bcd8849e81484e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605346"
---
# <a name="using-annotations-in-xsd-schemas-sqlxml-40"></a><span data-ttu-id="dd988-102">Utilisation des annotations dans les schémas XSD (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="dd988-102">Using Annotations in XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="dd988-103">Dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, le langage de schéma XSD prend en charge les annotations d'une manière similaire aux annotations introduites avec le langage de schéma XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="dd988-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports annotations in a manner similar to the annotations introduced in the XML-Data Reduced (XDR) schema language.</span></span> <span data-ttu-id="dd988-104">Des annotations supplémentaires ont été introduites dans XSD qui ne sont pas prises en charge dans XDR.</span><span class="sxs-lookup"><span data-stu-id="dd988-104">There are additional annotations introduced in XSD that are not supported in XDR.</span></span>  
  
 <span data-ttu-id="dd988-105">Ces annotations peuvent être utilisées dans le schéma XSD pour spécifier le mappage des données XML et des données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="dd988-105">These annotations can be used within the XSD schema to specify XML-to-relational mapping.</span></span> <span data-ttu-id="dd988-106">Est inclus le mappage entre les éléments et les attributs du schéma XSD avec les tables (vues) et les colonnes des bases de données.</span><span class="sxs-lookup"><span data-stu-id="dd988-106">This includes mapping between elements and attributes in the XSD schema to tables (views) and columns in the databases.</span></span>  
  
 <span data-ttu-id="dd988-107">Si vous ne spécifiez pas les annotations, le mappage par défaut a lieu.</span><span class="sxs-lookup"><span data-stu-id="dd988-107">If you do not specify the annotations, default mapping takes place.</span></span> <span data-ttu-id="dd988-108">Par défaut, un élément XSD avec un type complexe est mappé avec un nom de table (vue) de la base de données spécifiée, et un élément ou attribut avec un type simple est mappé avec la colonne du même nom en tant qu'élément ou attribut.</span><span class="sxs-lookup"><span data-stu-id="dd988-108">By default, an XSD element with a complex type maps to a table (view) name in the specified database, and an element or attribute with a simple type maps to the column with the same name as the element or attribute.</span></span>  
  
 <span data-ttu-id="dd988-109">Ces annotations peuvent également être utilisées pour spécifier les relations hiérarchiques dans XML, représentant ainsi les relations dans la base de données, car un schéma XSD est simplement une vue XML de données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="dd988-109">These annotations can also be used to specify the hierarchical relationships in XML-thus representing the relationships in the database, because an XSD schema is simply an XML view of relational data.</span></span>  
  
 <span data-ttu-id="dd988-110">Cette section fournit les descriptions des annotations que vous pouvez utiliser avec les schémas XSD, ainsi que des exemples d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="dd988-110">This section provides descriptions of the annotations you can use with XSD schemas and examples of their usage.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd988-111">Tous les exemples de cette section spécifient des requêtes XPath simples sur le schéma XSD annoté décrit dans chaque exemple.</span><span class="sxs-lookup"><span data-stu-id="dd988-111">All the examples in this section specify simple XPath queries against the annotated XSD schema described in each example.</span></span> <span data-ttu-id="dd988-112">Ces exemples présument que vous connaissiez le langage XPath.</span><span class="sxs-lookup"><span data-stu-id="dd988-112">Familiarity with the XPath language is assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd988-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="dd988-113">In This Section</span></span>  
 [<span data-ttu-id="dd988-114">Annotations XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-114">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](xsd-annotations-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-115">Répertorie les annotations que vous pouvez utiliser avec les schémas XSD, leurs descriptions et les annotations équivalentes pour XDR.</span><span class="sxs-lookup"><span data-stu-id="dd988-115">Lists the annotations you can use with XSD schemas, their descriptions, and the equivalent annotations for XDR.</span></span>  
  
 [<span data-ttu-id="dd988-116">Mappage par défaut d’éléments et d’attributs XSD à des tables et des colonnes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-116">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-117">Explique le mappage par défaut et fournit des exemples de tâches en rapport avec le mappage par défaut.</span><span class="sxs-lookup"><span data-stu-id="dd988-117">Explains default mapping and provides examples of tasks related to default mapping.</span></span>  
  
 [<span data-ttu-id="dd988-118">Mappage explicite d’éléments et d’attributs XSD à des tables et des colonnes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-118">Explicit Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](explicit-mapping-xsd-elements-and-attributes-to-tables-and-columns.md)  
 <span data-ttu-id="dd988-119">Explique le mappage explicite avec les annotations `sql:relation` et `sql:field` et fournit des exemples.</span><span class="sxs-lookup"><span data-stu-id="dd988-119">Explains explicit mapping with the `sql:relation` and `sql:field` annotations, and provides examples.</span></span>  
  
 [<span data-ttu-id="dd988-120">Spécification de relations à l’aide de SQL : Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-120">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-121">Décrit et fournit des exemples de l'annotation `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="dd988-121">Describes and provides examples of the `sql:relationship` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-122">Spécification de l’attribut SQL : inverse sur SQL : Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-122">Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-123">Décrit l'annotation `sql:inverse`.</span><span class="sxs-lookup"><span data-stu-id="dd988-123">Describes the `sql:inverse` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-124">Création d’éléments constants à l’aide de SQL : is-constant &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-124">Creating Constant Elements Using sql:is-constant &#40;SQLXML 4.0&#41;</span></span>](creating-constant-elements-using-sql-is-constant-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-125">Décrit et fournit des exemples de l'annotation `sql:is-constant`.</span><span class="sxs-lookup"><span data-stu-id="dd988-125">Describes and provides examples of the `sql:is-constant` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-126">Exclusion d’éléments de schéma du document XML obtenu à l’aide de SQL : mapped &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-126">Excluding Schema Elements from the Resulting XML Document Using sql:mapped &#40;SQLXML 4.0&#41;</span></span>](excluding-schema-elements-from-the-xml-document-using-sql-mapped.md)  
 <span data-ttu-id="dd988-127">Décrit et fournit des exemples de l'annotation `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="dd988-127">Describes and provides examples of the `sql:mapped` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-128">Filtrage des valeurs à l’aide de SQL : Limit-Field et SQL : limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-128">Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="dd988-129">Décrit et fournit des exemples des annotations `sql:limit-field` et `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="dd988-129">Describes and provides examples of the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 [<span data-ttu-id="dd988-130">Identification des colonnes clés à l’aide de SQL : key-fields &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-130">Identifying Key Columns Using sql:key-fields &#40;SQLXML 4.0&#41;</span></span>](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-131">Décrit et fournit des exemples de l'annotation `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="dd988-131">Describes and provides examples of the `sql:key-fields` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-132">Spécification d’un espace de noms cible à l’aide de l’attribut targetNamespace &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-132">Specifying a Target Namespace Using the targetNamespace Attribute &#40;SQLXML 4.0&#41;</span></span>](specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-133">Décrit et fournit des exemples de l’attribut **targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="dd988-133">Describes and provides examples of the **targetNamespace** attribute.</span></span>  
  
 [<span data-ttu-id="dd988-134">Création d’attributs de type ID, IDREF et IDREFS valides à l’aide de SQL : prefix &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-134">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix &#40;SQLXML 4.0&#41;</span></span>](creating-valid-id-idref-and-idrefs-type-attributes-using-sql-prefix-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-135">Décrit et fournit des exemples de l'annotation `sql:prefix`.</span><span class="sxs-lookup"><span data-stu-id="dd988-135">Describes and provides examples of the `sql:prefix` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-136">Les contraintes de type de données et l’annotation sql : DataType &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-136">Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;</span></span>](data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-137">Décrit et fournit des exemples de l'annotation `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="dd988-137">Describes and provides examples of the `sql:datatype` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-138">Mappage de types de données XSD à des types de données XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-138">Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-139">Fournit une table qui compare les types de données XSD, XDR et Xpath, et répertorie les conversions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] appropriées.</span><span class="sxs-lookup"><span data-stu-id="dd988-139">Provides a table that compares XSD, XDR, and XPath datatypes and lists the relevant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conversions.</span></span>  
  
 [<span data-ttu-id="dd988-140">Création de sections CDATA à l’aide de SQL : use-cdata &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-140">Creating CDATA Sections Using sql:use-cdata &#40;SQLXML 4.0&#41;</span></span>](creating-cdata-sections-using-sql-use-cdata-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-141">Décrit et fournit des exemples de l'annotation `sql:use-data`.</span><span class="sxs-lookup"><span data-stu-id="dd988-141">Describes and provides examples of the `sql:use-data` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-142">Demande de références URL à des données BLOB à l’aide de SQL : encode &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-142">Requesting URL References to BLOB Data Using sql:encode &#40;SQLXML 4.0&#41;</span></span>](requesting-url-references-to-blob-data-using-sql-encode-sqlxml-4-0.md)  
 <span data-ttu-id="dd988-143">Décrit et fournit des exemples de l'annotation `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="dd988-143">Describes and provides examples of the `sql:encode` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-144">Récupération de données non consommées à l’aide de SQL : overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-144">Retrieving Unconsumed Data Using the sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="dd988-145">Décrit et fournit des exemples de l'annotation `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="dd988-145">Describes and provides examples of the `sql:overflow-field` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-146">Masquage d'éléments et d'attributs à l'aide de sql:hide</span><span class="sxs-lookup"><span data-stu-id="dd988-146">Hiding Elements and Attributes by Using sql:hide</span></span>](hiding-elements-and-attributes-by-using-sql-hide.md)  
 <span data-ttu-id="dd988-147">Décrit et fournit des exemples de l'annotation `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="dd988-147">Describes and provides examples of the `sql:hide` annotation.</span></span>  
  
 [<span data-ttu-id="dd988-148">Utilisation des annotations sql:identity et sql:guid</span><span class="sxs-lookup"><span data-stu-id="dd988-148">Using the sql:identity and sql:guid Annotations</span></span>](using-the-sql-identity-and-sql-guid-annotations.md)  
 <span data-ttu-id="dd988-149">Décrit et fournit des exemples des annotations `sql:identity` et `sql:guid`.</span><span class="sxs-lookup"><span data-stu-id="dd988-149">Describes and provides examples of the `sql:identity` and `sql:guid` annotations.</span></span>  
  
 [<span data-ttu-id="dd988-150">Spécification de la profondeur dans les relations récursives à l'aide de sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="dd988-150">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>](specifying-depth-in-recursive-relationships-by-using-sql-max-depth.md)  
 <span data-ttu-id="dd988-151">Décrit et fournit des exemples de l'annotation `sql:max-depth`.</span><span class="sxs-lookup"><span data-stu-id="dd988-151">Describes and provides examples of the `sql:max-depth` annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd988-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dd988-152">See Also</span></span>  
 [<span data-ttu-id="dd988-153">Considérations sur la sécurité des schémas annotés &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="dd988-153">Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md)  
  
  
