---
title: Présentation de codes (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
ms.openlocfilehash: eb2f29d7f5d86d28254dacb9c55cceb9b4c72d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700859"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a><span data-ttu-id="da8d3-102">Présentation des codes de mise à jour (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="da8d3-102">Introduction to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="da8d3-103">Vous pouvez modifier (insérer, mettre à jour ou supprimer) une base de données dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à partir d’un document XML existant à l’aide d’un mise à jour ou de la [!INCLUDE[tsql](../../../includes/tsql-md.md)] fonction OpenXml.</span><span class="sxs-lookup"><span data-stu-id="da8d3-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="da8d3-104">La fonction OPENXML modifie une base de données en fragmentant le document XML existant et en fournissant un ensemble de lignes qui peut être passé à une instruction INSERT, UPDATE ou DELETE.</span><span class="sxs-lookup"><span data-stu-id="da8d3-104">The OPENXML function modifies a database by shredding the existing XML document and providing a rowset that can be passed to an INSERT, UPDATE, or DELETE statement.</span></span> <span data-ttu-id="da8d3-105">Avec OPENXML, les opérations sont effectuées directement sur les tables de base de données.</span><span class="sxs-lookup"><span data-stu-id="da8d3-105">With OPENXML, operations are performed directly against the database tables.</span></span> <span data-ttu-id="da8d3-106">Par conséquent, OPENXML est particulièrement approprié partout où les fournisseurs d'ensembles de lignes, tels qu'une table, peuvent apparaître comme source.</span><span class="sxs-lookup"><span data-stu-id="da8d3-106">Therefore, OPENXML is most appropriate wherever rowset providers, such as a table, can appear as a source.</span></span>  
  
 <span data-ttu-id="da8d3-107">Comme OPENXML, un code de mise à jour vous permet d'insérer, de mettre à jour ou de supprimer des données dans la base de données ; toutefois, un code de mise à jour fonctionne sur les vues XML fournies par le schéma XSD annoté (ou un XDR) ; par exemple, les mises à jour sont appliquées à la vue XML fournie par le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="da8d3-107">Like OPENXML, an updategram allows you to insert, update, or delete data in the database; however, an updategram works against the XML views provided by the annotated XSD (or an XDR) schema; for example, the updates are applied to the XML view provided by the mapping schema.</span></span> <span data-ttu-id="da8d3-108">Le schéma de mappage, à son tour, possède les informations nécessaires pour mapper des éléments et des attributs XML aux tables et colonnes de base de données correspondantes.</span><span class="sxs-lookup"><span data-stu-id="da8d3-108">The mapping schema, in turn, has the necessary information to map XML elements and attributes to the corresponding database tables and columns.</span></span> <span data-ttu-id="da8d3-109">Le code de mise à jour utilise ces informations de mappage pour mettre à jour les tables et colonnes de base de données.</span><span class="sxs-lookup"><span data-stu-id="da8d3-109">The updategram uses this mapping information to update the database tables and columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da8d3-110">Cette documentation suppose une connaissance suffisante des modèles et de la prise en charge des schémas de mappage dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da8d3-110">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="da8d3-111">Pour plus d’informations, consultez [Introduction aux schémas XSD Annotés &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="da8d3-111">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="da8d3-112">Pour les applications héritées qui utilisent XDR, consultez [schémas XDR Annotés &#40;dépréciés dans SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="da8d3-112">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="required-namespaces-in-the-updategram"></a><span data-ttu-id="da8d3-113">Espace de noms requis dans le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="da8d3-113">Required Namespaces in the Updategram</span></span>  
 <span data-ttu-id="da8d3-114">Les mots clés dans un mise à jour, tels que **\<sync>** , **\<before>** et **\<after>** , existent dans l' `urn:schemas-microsoft-com:xml-updategram` espace de noms.</span><span class="sxs-lookup"><span data-stu-id="da8d3-114">The keywords in an updategram, such as **\<sync>**, **\<before>**, and **\<after>**, exist in the `urn:schemas-microsoft-com:xml-updategram` namespace.</span></span> <span data-ttu-id="da8d3-115">Le préfixe d'espace de noms employé est arbitraire.</span><span class="sxs-lookup"><span data-stu-id="da8d3-115">The namespace prefix that you use is arbitrary.</span></span> <span data-ttu-id="da8d3-116">Dans cette documentation, le préfixe `updg` dénote l'espace de noms `updategram`.</span><span class="sxs-lookup"><span data-stu-id="da8d3-116">In this documentation, the `updg` prefix denotes the `updategram` namespace.</span></span>  
  
## <a name="reviewing-syntax"></a><span data-ttu-id="da8d3-117">Vérification de la syntaxe</span><span class="sxs-lookup"><span data-stu-id="da8d3-117">Reviewing Syntax</span></span>  
 <span data-ttu-id="da8d3-118">Un mise à jour est un modèle avec **\<sync>** des **\<before>** blocs, et **\<after>** qui forment la syntaxe du mise à jour.</span><span class="sxs-lookup"><span data-stu-id="da8d3-118">An updategram is a template with **\<sync>**, **\<before>**, and **\<after>** blocks that form the syntax of the updategram.</span></span> <span data-ttu-id="da8d3-119">Le code ci-dessous illustre cette syntaxe dans sa forme la plus simple :</span><span class="sxs-lookup"><span data-stu-id="da8d3-119">The following code shows this syntax in its simplest form:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="da8d3-120">Les définitions ci-dessous décrivent le rôle de chacun de ces blocs :</span><span class="sxs-lookup"><span data-stu-id="da8d3-120">The following definitions describe the role of each of these blocks:</span></span>  
  
 **\<before>**  
 <span data-ttu-id="da8d3-121">Identifie l'état existant (également appelé « état before ») de l'instance de l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="da8d3-121">Identifies the existing state (also called "the before state") of the record instance.</span></span>  
  
 **\<after>**  
 <span data-ttu-id="da8d3-122">Identifie le nouvel état qu'auront les données après modification.</span><span class="sxs-lookup"><span data-stu-id="da8d3-122">Identifies the new state to which data is to be changed.</span></span>  
  
 **\<sync>**  
 <span data-ttu-id="da8d3-123">Contient les **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="da8d3-123">Contains the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="da8d3-124">Un **\<sync>** bloc peut contenir plusieurs jeux de **\<before>** **\<after>** blocs et.</span><span class="sxs-lookup"><span data-stu-id="da8d3-124">A **\<sync>** block can contain more than one set of **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="da8d3-125">S’il y a plus d’un ensemble **\<before>** de **\<after>** blocs et, ces blocs (même s’ils sont vides) doivent être spécifiés en tant que paires.</span><span class="sxs-lookup"><span data-stu-id="da8d3-125">If there is more than one set of **\<before>** and **\<after>** blocks, these blocks (even if they are empty) must be specified as pairs.</span></span> <span data-ttu-id="da8d3-126">En outre, un mise à jour peut avoir plusieurs **\<sync>** blocs.</span><span class="sxs-lookup"><span data-stu-id="da8d3-126">Furthermore, an updategram can have more than one **\<sync>** block.</span></span> <span data-ttu-id="da8d3-127">Chaque **\<sync>** bloc est une unité de transaction (ce qui signifie que tous les éléments du **\<sync>** bloc sont exécutés ou que rien n’est fait).</span><span class="sxs-lookup"><span data-stu-id="da8d3-127">Each **\<sync>** block is one unit of transaction (which means that either everything in the **\<sync>** block is done or nothing is done).</span></span> <span data-ttu-id="da8d3-128">Si vous spécifiez plusieurs **\<sync>** blocs dans un mise à jour, la défaillance d’un **\<sync>** bloc n’affecte pas les autres **\<sync>** blocs.</span><span class="sxs-lookup"><span data-stu-id="da8d3-128">If you specify multiple **\<sync>** blocks in an updategram, the failure of one **\<sync>** block does not affect the other **\<sync>** blocks.</span></span>  
  
 <span data-ttu-id="da8d3-129">Le fait qu’un mise à jour supprime, insère ou met à jour une instance d’enregistrement dépend du contenu des **\<before>** **\<after>** blocs et :</span><span class="sxs-lookup"><span data-stu-id="da8d3-129">Whether an updategram deletes, inserts, or updates a record instance depends on the contents of the **\<before>** and **\<after>** blocks:</span></span>  
  
-   <span data-ttu-id="da8d3-130">Si une instance d’enregistrement apparaît uniquement dans le **\<before>** bloc sans instance correspondante dans le **\<after>** bloc, mise à jour effectue une opération de suppression.</span><span class="sxs-lookup"><span data-stu-id="da8d3-130">If a record instance appears only in the **\<before>** block with no corresponding instance in the **\<after>** block, the updategram performs a delete operation.</span></span>  
  
-   <span data-ttu-id="da8d3-131">Si une instance d’enregistrement apparaît uniquement dans le **\<after>** bloc sans instance correspondante dans le **\<before>** bloc, il s’agit d’une opération d’insertion.</span><span class="sxs-lookup"><span data-stu-id="da8d3-131">If a record instance appears only in the **\<after>** block with no corresponding instance in the **\<before>** block, it is an insert operation.</span></span>  
  
-   <span data-ttu-id="da8d3-132">Si une instance d’enregistrement apparaît dans le **\<before>** bloc et a une instance correspondante dans le **\<after>** bloc, il s’agit d’une opération de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="da8d3-132">If a record instance appears in the **\<before>** block and has a corresponding instance in the **\<after>** block, it is an update operation.</span></span> <span data-ttu-id="da8d3-133">Dans ce cas, mise à jour met à jour l’instance d’enregistrement avec les valeurs spécifiées dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="da8d3-133">In this case, the updategram updates the record instance to the values that are specified in the **\<after>** block.</span></span>  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a><span data-ttu-id="da8d3-134">Spécification d'un schéma de mappage dans le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="da8d3-134">Specifying a Mapping Schema in the Updategram</span></span>  
 <span data-ttu-id="da8d3-135">Dans un code de mise à jour, l'abstraction XML fournie par un schéma de mappage (les schémas XSD et XDR sont pris en charge) peut être implicite ou explicite (autrement dit, un code de mise à jour peut fonctionner avec ou sans schéma de mappage spécifié).</span><span class="sxs-lookup"><span data-stu-id="da8d3-135">In an updategram, the XML abstraction that is provided by a mapping schema (both XSD and XDR schemas are supported) can be implicit or explicit (that is, an updategram can work with or without a specified mapping schema).</span></span> <span data-ttu-id="da8d3-136">Si vous ne spécifiez pas de schéma de mappage, le mise à jour suppose un mappage implicite (le mappage par défaut), où chaque élément du **\<before>** bloc ou bloc **\<after>** est mappé à une table et l’élément enfant ou l’attribut enfant de chaque élément est mappé à une colonne de la base de données.</span><span class="sxs-lookup"><span data-stu-id="da8d3-136">If you do not specify a mapping schema, the updategram assumes an implicit mapping (the default mapping), where each element in the **\<before>** block or **\<after>** block maps to a table and each element's child element or attribute maps to a column in the database.</span></span> <span data-ttu-id="da8d3-137">Si vous spécifiez explicitement un schéma de mappage, les éléments et les attributs dans le code de mise à jour doivent correspondre aux éléments et aux attributs dans le schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="da8d3-137">If you explicitly specify a mapping schema, the elements and attributes in the updategram must match the elements and attributes in the mapping schema.</span></span>  
  
### <a name="implicit-default-mapping"></a><span data-ttu-id="da8d3-138">Mappage implicite (par défaut)</span><span class="sxs-lookup"><span data-stu-id="da8d3-138">Implicit (default) Mapping</span></span>  
 <span data-ttu-id="da8d3-139">Dans la plupart des cas, un code de mise à jour qui effectue des mises à jour simples peut ne pas requérir de schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="da8d3-139">In most cases, an updategram that performs simple updates might not require a mapping schema.</span></span> <span data-ttu-id="da8d3-140">Dans ce cas, le code de mise à jour compte sur le schéma de mappage par défaut.</span><span class="sxs-lookup"><span data-stu-id="da8d3-140">In this case, the updategram relies on the default mapping schema.</span></span>  
  
 <span data-ttu-id="da8d3-141">Le code de mise à jour ci-dessous illustre un mappage implicite.</span><span class="sxs-lookup"><span data-stu-id="da8d3-141">The following updategram demonstrates implicit mapping.</span></span> <span data-ttu-id="da8d3-142">Dans cet exemple, le code de mise à jour insère un nouveau client dans la table Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="da8d3-142">In this example, the updategram inserts a new customer in the Sales.Customer table.</span></span> <span data-ttu-id="da8d3-143">Étant donné que ce mise à jour utilise le mappage implicite, l' \<Sales.Customer> élément est mappé à la table Sales. Customer, et les attributs CustomerID et SalesPersonID sont mappés aux colonnes correspondantes de la table Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="da8d3-143">Because this updategram uses implicit mapping, the \<Sales.Customer> element maps to the Sales.Customer table, and the CustomerID and SalesPersonID attributes map to the corresponding columns in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a><span data-ttu-id="da8d3-144">Mappage explicite</span><span class="sxs-lookup"><span data-stu-id="da8d3-144">Explicit Mapping</span></span>  
 <span data-ttu-id="da8d3-145">Si vous spécifiez un schéma de mappage (XSD ou XDR), le code de mise à jour utilise le schéma pour déterminer les tables et colonnes de base de données qui seront mises à jour.</span><span class="sxs-lookup"><span data-stu-id="da8d3-145">If you specify a mapping schema (either XSD or XDR), the updategram uses the schema to determine the database tables and columns that are to be updated.</span></span>  
  
 <span data-ttu-id="da8d3-146">Si le code de mise à jour effectue une mise à jour complexe (par exemple, l'insertion d'enregistrements dans plusieurs tables sur la base de la relation parent-enfant spécifiée dans le schéma de mappage), vous devez fournir explicitement le schéma de mappage en utilisant l'attribut `mapping-schema` sur lequel le code de mise à jour s'exécute.</span><span class="sxs-lookup"><span data-stu-id="da8d3-146">If the updategram performs a complex update (for example, inserting records in multiple tables on the basis of the parent-child relationship that is specified in the mapping schema), you must explicitly provide the mapping schema by using the `mapping-schema` attribute against which the updategram executes.</span></span>  
  
 <span data-ttu-id="da8d3-147">Comme un code de mise à jour est un modèle, le chemin d'accès spécifié pour le schéma de mappage dans le code de mise à jour est relatif à l'emplacement du fichier modèle (relatif à l'emplacement où le code de mise à jour est stocké).</span><span class="sxs-lookup"><span data-stu-id="da8d3-147">Because an updategram is a template, the path specified for the mapping schema in the updategram is relative to the location of the template file (relative to where the updategram is stored).</span></span> <span data-ttu-id="da8d3-148">Pour plus d’informations, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="da8d3-148">For more information, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a><span data-ttu-id="da8d3-149">Mappage centré sur les éléments et mappage centré sur les attributs dans les codes de mise à jour</span><span class="sxs-lookup"><span data-stu-id="da8d3-149">Element-centric and Attribute-centric Mapping in Updategrams</span></span>  
 <span data-ttu-id="da8d3-150">Avec le mappage par défaut (lorsque le schéma de mappage n'est pas spécifié dans le code de mise à jour), les éléments de code de mise à jour sont mappés à des tables et les éléments enfants (dans le cas du mappage centré sur les éléments) et les attributs (dans le cas du mappage centré sur les attributs) sont mappés à des colonnes.</span><span class="sxs-lookup"><span data-stu-id="da8d3-150">With default mapping (when the mapping schema is not specified in the updategram), the updategram elements map to tables and the  child elements (in the case of element-centric mapping) and the attributes (in the case of attribute-centric mapping) map to columns.</span></span>  
  
### <a name="element-centric-mapping"></a><span data-ttu-id="da8d3-151">Mappage centré sur les éléments</span><span class="sxs-lookup"><span data-stu-id="da8d3-151">Element-centric Mapping</span></span>  
 <span data-ttu-id="da8d3-152">Dans un code de mise à jour centré sur les éléments, un élément contient des éléments enfants qui désignent les propriétés de l'élément.</span><span class="sxs-lookup"><span data-stu-id="da8d3-152">In an element-centric updategram, an element contains child elements that denote the properties of the element.</span></span> <span data-ttu-id="da8d3-153">Pour bénéficier d'un exemple, reportez-vous au code de mise à jour ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="da8d3-153">As an example, refer to the following updategram.</span></span> <span data-ttu-id="da8d3-154">L' **\<Person.Contact>** élément contient les **\<FirstName>** **\<LastName>** éléments enfants et.</span><span class="sxs-lookup"><span data-stu-id="da8d3-154">The **\<Person.Contact>** element contains the **\<FirstName>** and **\<LastName>** child elements.</span></span> <span data-ttu-id="da8d3-155">Ces éléments enfants sont des propriétés de l' **\<Person.Contact>** élément.</span><span class="sxs-lookup"><span data-stu-id="da8d3-155">These child elements are properties of the **\<Person.Contact>** element.</span></span>  
  
 <span data-ttu-id="da8d3-156">Étant donné que ce mise à jour ne spécifie pas de schéma de mappage, mise à jour utilise le mappage implicite, où l' **\<Person.Contact>** élément est mappé à la table Person. contact et ses éléments enfants sont mappés aux colonnes FirstName et LastName.</span><span class="sxs-lookup"><span data-stu-id="da8d3-156">Because this updategram does not specify a mapping schema, the updategram uses implicit mapping, where the **\<Person.Contact>** element maps to the Person.Contact table and its child elements map to the FirstName and LastName columns.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a><span data-ttu-id="da8d3-157">mappage centré sur les attributs</span><span class="sxs-lookup"><span data-stu-id="da8d3-157">Attribute-centric Mapping</span></span>  
 <span data-ttu-id="da8d3-158">Dans un mappage centré sur les attributs, les éléments ont des attributs.</span><span class="sxs-lookup"><span data-stu-id="da8d3-158">In an attribute-centric mapping, the elements have attributes.</span></span> <span data-ttu-id="da8d3-159">Le code de mise à jour ci-dessous utilise le mappage centré sur les attributs.</span><span class="sxs-lookup"><span data-stu-id="da8d3-159">The following updategram uses attribute-centric mapping.</span></span> <span data-ttu-id="da8d3-160">Dans cet exemple, l' **\<Person.Contact>** élément se compose des attributs **FirstName** et **LastName** .</span><span class="sxs-lookup"><span data-stu-id="da8d3-160">In this example, the **\<Person.Contact>** element consists of the **FirstName** and **LastName** attributes.</span></span> <span data-ttu-id="da8d3-161">Ces attributs sont les propriétés de l' **\<Person.Contact>** élément.</span><span class="sxs-lookup"><span data-stu-id="da8d3-161">These attributes are the properties of the **\<Person.Contact>** element.</span></span> <span data-ttu-id="da8d3-162">Comme dans l’exemple précédent, ce mise à jour ne spécifie aucun schéma de mappage. il s’appuie donc sur le mappage implicite pour mapper l' **\<Person.Contact>** élément à la table Person. contact et les attributs de l’élément aux colonnes respectives dans la table.</span><span class="sxs-lookup"><span data-stu-id="da8d3-162">As in the previous example, this updategram specifies no mapping schema, so it relies on implicit mapping to map the **\<Person.Contact>** element to the Person.Contact table and the element's attributes to the respective columns in the table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a><span data-ttu-id="da8d3-163">Utilisation du mappage centré sur les éléments et du mappage centré sur les attributs</span><span class="sxs-lookup"><span data-stu-id="da8d3-163">Using Both Element-centric and Attribute-centric Mapping</span></span>  
 <span data-ttu-id="da8d3-164">Vous pouvez spécifier une association du mappage centré sur les éléments et du mappage centré sur les attributs, comme l'illustre le code de mise à jour ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="da8d3-164">You can specify a mix of element-centric and attribute-centric mapping, as shown in the following updategram.</span></span> <span data-ttu-id="da8d3-165">Notez que l' **\<Person.Contact>** élément contient à la fois un attribut et un élément enfant.</span><span class="sxs-lookup"><span data-stu-id="da8d3-165">Notice that the **\<Person.Contact>** element contains both an attribute and a child element.</span></span> <span data-ttu-id="da8d3-166">Également, ce code de mise à jour s'appuie sur un mappage implicite.</span><span class="sxs-lookup"><span data-stu-id="da8d3-166">Also, this updategram relies on implicit mapping.</span></span> <span data-ttu-id="da8d3-167">Ainsi, l’attribut **FirstName** et l' **\<LastName>** élément enfant sont mappés aux colonnes correspondantes de la table Person. contact.</span><span class="sxs-lookup"><span data-stu-id="da8d3-167">Thus, the **FirstName** attribute and the **\<LastName>** child element map to corresponding columns in the Person.Contact table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a><span data-ttu-id="da8d3-168">Utilisation des caractères valides dans SQL Server mais non valides dans XML</span><span class="sxs-lookup"><span data-stu-id="da8d3-168">Working with Characters Valid in SQL Server but Not Valid in XML</span></span>  
 <span data-ttu-id="da8d3-169">Dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], les noms des tables peuvent inclure un espace.</span><span class="sxs-lookup"><span data-stu-id="da8d3-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space.</span></span> <span data-ttu-id="da8d3-170">Toutefois, ce type de nom de table n'est pas valide dans XML.</span><span class="sxs-lookup"><span data-stu-id="da8d3-170">However, this type of table name is not valid in XML.</span></span>  
  
 <span data-ttu-id="da8d3-171">Pour encoder des caractères qui sont des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificateurs valides, mais qui ne sont pas des identificateurs XML valides, utilisez' __xHHHH \_ \_ 'comme valeur d’encodage, où HHHH représente le code UCS-2 hexadécimal à quatre chiffres du caractère dans l’ordre binaire le plus significatif.</span><span class="sxs-lookup"><span data-stu-id="da8d3-171">To encode characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but are not valid XML identifiers, use '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="da8d3-172">À l’aide de ce schéma d’encodage, un espace est remplacé par x0020 (le code hexadécimal à quatre chiffres pour un espace); ainsi, le nom de la table [Order Details] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est _x005B_Order_x0020_Details_x005D \_ en XML.</span><span class="sxs-lookup"><span data-stu-id="da8d3-172">Using this encoding scheme, a space character gets replaced with x0020 (the four-digit hexadecimal code for a space character); thus, the table name [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] becomes _x005B_Order_x0020_Details_x005D\_ in XML.</span></span>  
  
 <span data-ttu-id="da8d3-173">De même, vous devrez peut-être spécifier des noms d’éléments en trois parties, tels que \<[database].[owner].[table]> .</span><span class="sxs-lookup"><span data-stu-id="da8d3-173">Similarly, you might need to specify three-part element names, such as \<[database].[owner].[table]>.</span></span> <span data-ttu-id="da8d3-174">Étant donné que les crochets ([et]) ne sont pas valides en XML, vous devez spécifier ce \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_> qui correspond à, où _x005B \_ est l’encodage du crochet gauche ([) et _x005D \_ est l’encodage du crochet droit (]).</span><span class="sxs-lookup"><span data-stu-id="da8d3-174">Because the bracket characters ([ and ]) are not valid in XML, you must specify this as \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_>, where _x005B\_ is the encoding for the left bracket ([) and _x005D\_ is the encoding for the right bracket (]).</span></span>  
  
## <a name="executing-updategrams"></a><span data-ttu-id="da8d3-175">Exécution de codes de mise à jour</span><span class="sxs-lookup"><span data-stu-id="da8d3-175">Executing Updategrams</span></span>  
 <span data-ttu-id="da8d3-176">Comme un code de mise à jour est un modèle, tous les mécanismes de traitement d'un modèle s'appliquent aux codes de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="da8d3-176">Because an updategram is a template, all the processing mechanisms of a template apply to the updategram.</span></span> <span data-ttu-id="da8d3-177">Pour SQLXML 4.0, vous pouvez exécuter un code de mise à jour d'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="da8d3-177">For SQLXML 4.0, you can execute an updategram in either of the following ways:</span></span>  
  
-   <span data-ttu-id="da8d3-178">En le soumettant dans une commande ADO.</span><span class="sxs-lookup"><span data-stu-id="da8d3-178">By submitting it in an ADO command.</span></span>  
  
-   <span data-ttu-id="da8d3-179">En le soumettant sous la forme d'une commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="da8d3-179">By submitting it as an OLE DB command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da8d3-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da8d3-180">See Also</span></span>  
 [<span data-ttu-id="da8d3-181">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="da8d3-181">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
