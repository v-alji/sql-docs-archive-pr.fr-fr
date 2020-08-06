---
title: Insertion de données à l’aide de codes XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- xsi:nil attribute
- unique values
- <after> block
- id attribute
- data insertions [SQLXML]
- nil attribute
- <before> block
- updg:guid attribute
- multiple record insertions
- returnid attribute
- updategrams [SQLXML], inserting data
- updg:at-identity attribute
- invalid characters [SQLXML]
- updg:returnid attribute
- updg:id attribute
- namespaces [SQLXML], updategrams
- IDENTITY-type column
- guid attribute
- record insertion [SQLXML]
- null values [SQLXML]
- at-identity attribute
- xml data type [SQL Server], SQLXML
ms.assetid: 4dc48762-bc12-43fb-b356-ea1b9c1e287e
author: rothja
ms.author: jroth
ms.openlocfilehash: a80f2cb157e59f30ebcbff5c14abba1003de9e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700860"
---
# <a name="inserting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="a046e-102">Insertion de données à l'aide de codes de mise à jour (updategrams) XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a046e-102">Inserting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="a046e-103">Un mise à jour indique une opération d’insertion lorsqu’une instance d’enregistrement apparaît dans le **\<after>** bloc mais pas dans le **\<before>** bloc correspondant.</span><span class="sxs-lookup"><span data-stu-id="a046e-103">An updategram indicates an insert operation when a record instance appears in the **\<after>** block but not in the corresponding **\<before>** block.</span></span> <span data-ttu-id="a046e-104">Dans ce cas, le mise à jour insère l’enregistrement dans le **\<after>** bloc dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a046e-104">In this case, the updategram inserts the record in the **\<after>** block into the database.</span></span>  
  
 <span data-ttu-id="a046e-105">Voici le format du code de mise à jour pour une opération d'insertion :</span><span class="sxs-lookup"><span data-stu-id="a046e-105">This is the updategram format for an insert operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   [<updg:before>  
   </updg:before>]  
    <updg:after [updg:returnid="x y ...] >  
       <ElementName [updg:id="value"]   
                   [updg:at-identity="x"]   
                   [updg:guid="y"]  
                   attribute="value"   
                   attribute="value"  
                   ...  
       />  
      [<ElementName .../>... ]  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
## <a name="before-block"></a><span data-ttu-id="a046e-106">\<before>Plage</span><span class="sxs-lookup"><span data-stu-id="a046e-106">\<before> Block</span></span>  
 <span data-ttu-id="a046e-107">Le **\<before>** bloc peut être omis pour une opération d’insertion.</span><span class="sxs-lookup"><span data-stu-id="a046e-107">The **\<before>** block can be omitted for an insert operation.</span></span> <span data-ttu-id="a046e-108">Si l' `mapping-schema` attribut facultatif n’est pas spécifié, le **\<ElementName>** spécifié dans le mise à jour est mappé à une table de base de données et les éléments ou attributs enfants sont mappés aux colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="a046e-108">If the optional `mapping-schema` attribute is not specified, the **\<ElementName>** that is specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
## <a name="after-block"></a><span data-ttu-id="a046e-109">\<after>Plage</span><span class="sxs-lookup"><span data-stu-id="a046e-109">\<after> Block</span></span>  
 <span data-ttu-id="a046e-110">Vous pouvez spécifier un ou plusieurs enregistrements dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="a046e-110">You can specify one or more records in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="a046e-111">Si le **\<after>** bloc ne fournit pas de valeur pour une colonne particulière, mise à jour utilise la valeur par défaut spécifiée dans le schéma annoté (si un schéma a été spécifié).</span><span class="sxs-lookup"><span data-stu-id="a046e-111">If the **\<after>** block does not supply a value for a particular column, the updategram uses the default value that is specified in the annotated schema (if a schema has been specified).</span></span> <span data-ttu-id="a046e-112">Si le schéma ne spécifie pas de valeur par défaut pour la colonne, mise à jour ne spécifie pas de valeur explicite pour cette colonne et, à la place, affecte la [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] valeur par défaut (si elle est spécifiée) à cette colonne.</span><span class="sxs-lookup"><span data-stu-id="a046e-112">If the schema does not specify a default value for the column, the updategram does not specify any explicit value to this column and, instead, assigns the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value (if specified) to this column.</span></span> <span data-ttu-id="a046e-113">S'il n'y a aucune valeur par défaut [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et que la colonne accepte une valeur NULL, le code de mise à jour attribue la valeur NULL à la colonne.</span><span class="sxs-lookup"><span data-stu-id="a046e-113">If there is no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value and the column accepts a NULL value, the updategram sets the column value to NULL.</span></span> <span data-ttu-id="a046e-114">Si la colonne ne possède pas de valeur par défaut et qu'elle n'accepte pas de valeur NULL, la commande échoue et le code de mise à jour retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="a046e-114">If the column neither has a default value nor accepts a NULL value, the command fails and the updategram returns an error.</span></span> <span data-ttu-id="a046e-115">L'attribut `updg:returnid` facultatif est utilisé pour retourner la valeur d'identité générée par le système lorsqu'un enregistrement est ajouté dans une table avec une colonne de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="a046e-115">The optional `updg:returnid` attribute is used to return the identity value that is generated by the system when a record is added in a table with an IDENTITY-type column.</span></span>  
  
## <a name="updgid-attribute"></a><span data-ttu-id="a046e-116">Attribut updg:id</span><span class="sxs-lookup"><span data-stu-id="a046e-116">updg:id Attribute</span></span>  
 <span data-ttu-id="a046e-117">Si le code de mise à jour insère uniquement des enregistrements, le code de mise à jour ne requiert pas l'attribut `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="a046e-117">If the updategram is inserting only records, the updategram does not require the `updg:id` attribute.</span></span> <span data-ttu-id="a046e-118">Pour plus d’informations sur `updg:id` , consultez [mise à jour des données à l’aide de XML codes &#40;SQLXML 4,0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-118">For more information about `updg:id`, see [Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="updgat-identity-attribute"></a><span data-ttu-id="a046e-119">Attribut updg:at-identity</span><span class="sxs-lookup"><span data-stu-id="a046e-119">updg:at-identity Attribute</span></span>  
 <span data-ttu-id="a046e-120">Lorsqu'un code de mise à jour insère un enregistrement dans une table possédant une colonne de type IDENTITY, le code de mise à jour peut capturer la valeur attribuée au système à l'aide de l'attribut `updg:at-identity` facultatif.</span><span class="sxs-lookup"><span data-stu-id="a046e-120">When an updategram inserts a record in a table that has an IDENTITY-type column, the updategram can capture the system assigned value by using the optional `updg:at-identity` attribute.</span></span> <span data-ttu-id="a046e-121">Le code de mise à jour peut utiliser ensuite cette valeur dans les opérations suivantes.</span><span class="sxs-lookup"><span data-stu-id="a046e-121">The updategram can then use this value in subsequent operations.</span></span> <span data-ttu-id="a046e-122">Après l'exécution du code de mise à jour, vous pouvez retourner la valeur d'identité générée en spécifiant l'attribut `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="a046e-122">Upon execution of the updategram, you can return the identity value that is generated by specifying the `updg:returnid` attribute.</span></span>  
  
## <a name="updgguid-attribute"></a><span data-ttu-id="a046e-123">Attribut updg:guid</span><span class="sxs-lookup"><span data-stu-id="a046e-123">updg:guid Attribute</span></span>  
 <span data-ttu-id="a046e-124">L'attribut `updg:guid` est un attribut facultatif qui génère un identificateur global unique.</span><span class="sxs-lookup"><span data-stu-id="a046e-124">The `updg:guid` attribute is an optional attribute that generates a globally unique identifier.</span></span> <span data-ttu-id="a046e-125">Cette valeur reste dans la portée pour le **\<sync>** bloc entier dans lequel elle est spécifiée.</span><span class="sxs-lookup"><span data-stu-id="a046e-125">This value remains in scope for the entire **\<sync>** block in which it is specified.</span></span> <span data-ttu-id="a046e-126">Vous pouvez utiliser cette valeur n’importe où dans le **\<sync>** bloc.</span><span class="sxs-lookup"><span data-stu-id="a046e-126">You can use this value anywhere in the **\<sync>** block.</span></span> <span data-ttu-id="a046e-127">L’attribut appelle la `NEWGUID()` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fonction pour générer l’identificateur unique.</span><span class="sxs-lookup"><span data-stu-id="a046e-127">The attribute calls the `NEWGUID()`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] function to generate the unique identifier.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a046e-128">Exemples</span><span class="sxs-lookup"><span data-stu-id="a046e-128">Examples</span></span>  
 <span data-ttu-id="a046e-129">Pour créer des exemples fonctionnels à l’aide des exemples suivants, vous devez respecter les exigences spécifiées dans la [Configuration requise pour l’exécution d’exemples SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-129">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="a046e-130">Avant d'utiliser les exemples de code de mise à jour, notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="a046e-130">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="a046e-131">La plupart des exemples utilisent le mappage par défaut (en d'autres termes, aucun schéma de mappage n'est spécifié dans le code de mise à jour (updategram)).</span><span class="sxs-lookup"><span data-stu-id="a046e-131">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="a046e-132">Pour obtenir plus d’exemples de codes qui utilisent des schémas de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-132">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="a046e-133">La plupart des exemples sont basés sur l'exemple de base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a046e-133">Most of the examples use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="a046e-134">Toutes les mises à jour sont appliquées aux tables de cette base de données.</span><span class="sxs-lookup"><span data-stu-id="a046e-134">All the updates are applied to the tables in this database.</span></span>  
  
### <a name="a-inserting-a-record-by-using-an-updategram"></a><span data-ttu-id="a046e-135">R.</span><span class="sxs-lookup"><span data-stu-id="a046e-135">A.</span></span> <span data-ttu-id="a046e-136">Insertion d'un enregistrement à l'aide d'un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-136">Inserting a record by using an updategram</span></span>  
 <span data-ttu-id="a046e-137">Ce code de mise à jour centré sur les attributs insère un enregistrement dans la table HumanResources.Employee dans la base de données [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a046e-137">This attribute-centric updategram inserts a record in the HumanResources.Employee table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="a046e-138">Dans cet exemple, le code de mise à jour ne spécifie pas de schéma de mappage.</span><span class="sxs-lookup"><span data-stu-id="a046e-138">In this example, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="a046e-139">Par conséquent, le code de mise à jour utilise le mappage par défaut, dans lequel le nom d'élément est mappé à un nom de table et les attributs ou éléments enfants sont mappés aux colonnes dans cette table.</span><span class="sxs-lookup"><span data-stu-id="a046e-139">Therefore, the updategram uses default mapping, in which the element name maps to a table name and the attributes or child elements map to columns in that table.</span></span>  
  
 <span data-ttu-id="a046e-140">Le schéma [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] pour la table HumanResources.Department impose une restriction NOT NULL sur toutes les colonnes sauf OrganizationNode et OrganizationLevel.</span><span class="sxs-lookup"><span data-stu-id="a046e-140">The [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] schema for the HumanResources.Department table imposes a 'not null' restriction on all columns.</span></span> <span data-ttu-id="a046e-141">Par conséquent, le code de mise à jour doit inclure des valeurs spécifiées pour toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="a046e-141">Therefore, the updategram must include values specified for all columns.</span></span> <span data-ttu-id="a046e-142">DepartmentID est une colonne de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="a046e-142">The DepartmentID is an IDENTITY-type column.</span></span> <span data-ttu-id="a046e-143">Par conséquent, aucune valeur n'est spécifiée pour cette colonne.</span><span class="sxs-lookup"><span data-stu-id="a046e-143">Therefore, no values are specified for it.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name="New Product Research"   
            GroupName="Research and Development"   
            ModifiedDate="2010-08-31"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="a046e-144">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="a046e-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="a046e-145">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-145">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-146">Enregistrez le fichier sous le nom MyUpdategram.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-146">Save the file as MyUpdategram.xml.</span></span>  
  
2.  <span data-ttu-id="a046e-147">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="a046e-147">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a046e-148">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-148">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a046e-149">Dans un mappage centré sur l'élément, le code de mise à jour ressemble à ceci :</span><span class="sxs-lookup"><span data-stu-id="a046e-149">In an element-centric mapping, the updategram looks like this:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department>  
            <Name> New Product Research </Name>  
            <GroupName> Research and Development </GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-150">Dans un code de mise à jour en mode mixte (centré sur l'élément et centré sur l'attribut), un élément peut avoir des attributs et des sous-éléments, comme indiqué dans ce code de mise à jour :</span><span class="sxs-lookup"><span data-stu-id="a046e-150">In a mixed-mode (element-centric and attribute-centric) updategram, an element can have both attributes and subelements, as shown in this updategram:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name=" New Product Research "   
            <GroupName>Research and Development</GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="b-inserting-multiple-records-by-using-an-updategram"></a><span data-ttu-id="a046e-151">B.</span><span class="sxs-lookup"><span data-stu-id="a046e-151">B.</span></span> <span data-ttu-id="a046e-152">Insertion de plusieurs enregistrements à l'aide d'un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-152">Inserting multiple records by using an updategram</span></span>  
 <span data-ttu-id="a046e-153">Ce code de mise à jour ajoute deux nouveaux enregistrements de décalage à la table HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="a046e-153">This updategram adds two new shift records to the HumanResources.Shift table.</span></span> <span data-ttu-id="a046e-154">Mise à jour ne spécifie pas le **\<before>** bloc facultatif.</span><span class="sxs-lookup"><span data-stu-id="a046e-154">The updategram does not specify the optional **\<before>** block.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="a046e-155">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="a046e-155">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="a046e-156">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-156">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-157">Enregistrez le fichier sous le nom Updategram-AddShifts.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-157">Save the file as Updategram-AddShifts.xml.</span></span>  
  
2.  <span data-ttu-id="a046e-158">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="a046e-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a046e-159">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a046e-160">Une autre version de cet exemple est un mise à jour qui utilise deux **\<after>** blocs séparés au lieu d’un bloc pour insérer les deux employés.</span><span class="sxs-lookup"><span data-stu-id="a046e-160">Another version of this example is an updategram that uses two separate **\<after>** blocks instead of one block to insert the two employees.</span></span> <span data-ttu-id="a046e-161">Cette opération est valide et peut être encodée comme suit :</span><span class="sxs-lookup"><span data-stu-id="a046e-161">This is valid and can be encoded as follows:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after >  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="c-working-with-valid-sql-server-characters-that-are-not-valid-in-xml"></a><span data-ttu-id="a046e-162">C.</span><span class="sxs-lookup"><span data-stu-id="a046e-162">C.</span></span> <span data-ttu-id="a046e-163">Utilisation de caractères SQL Server valides qui ne sont pas valides en XML</span><span class="sxs-lookup"><span data-stu-id="a046e-163">Working with valid SQL Server characters that are not valid in XML</span></span>  
 <span data-ttu-id="a046e-164">Dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], les noms de table peuvent inclure un espace, comme la table Order Details dans la base de données Northwind.</span><span class="sxs-lookup"><span data-stu-id="a046e-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space, such as the Order Details table in the Northwind database.</span></span> <span data-ttu-id="a046e-165">Toutefois, cela n’est pas valide dans les caractères XML qui sont des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificateurs valides, mais les identificateurs XML non valides peuvent être encodés à l’aide de' __xHHHH \_ \_ 'comme valeur d’encodage, où HHHH représente le code UCS-2 hexadécimal à quatre chiffres du caractère dans l’ordre binaire le plus significatif.</span><span class="sxs-lookup"><span data-stu-id="a046e-165">However, this is not valid in XML characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but not valid XML identifiers can be encoded using '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a046e-166">Cet exemple utilise l'exemple de base de données Northwind.</span><span class="sxs-lookup"><span data-stu-id="a046e-166">This example uses the Northwind database.</span></span> <span data-ttu-id="a046e-167">Vous pouvez installer la base de données Northwind à l’aide d’un script SQL disponible en téléchargement à partir de ce [site Web Microsoft](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="a046e-167">You can install the Northwind database by using an SQL script available for download from this [Microsoft Web site](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>  
  
 <span data-ttu-id="a046e-168">Par ailleurs, le nom d'élément doit être mis entre crochets ([ ]).</span><span class="sxs-lookup"><span data-stu-id="a046e-168">Also, the element name must be enclosed within brackets ([ ]).</span></span> <span data-ttu-id="a046e-169">Étant donné que les caractères [et] ne sont pas valides en XML, vous devez les encoder en tant que _x005B \_ et _x005D \_ , respectivement.</span><span class="sxs-lookup"><span data-stu-id="a046e-169">Because the characters [and] are not valid in XML, you must encode them as _x005B\_ and _x005D\_, respectively.</span></span> <span data-ttu-id="a046e-170">(Si vous utilisez un schéma de mappage, vous pouvez fournir des noms d'élément qui ne contiennent pas de caractères non valides, tels que des espaces blancs.</span><span class="sxs-lookup"><span data-stu-id="a046e-170">(If you use a mapping schema, you can provide element names that do not contain characters that are not valid, such as white spaces.</span></span> <span data-ttu-id="a046e-171">Le schéma de mappage effectue le mappage nécessaire ; par conséquent, il est inutile d'encoder ces caractères).</span><span class="sxs-lookup"><span data-stu-id="a046e-171">The mapping schema does the necessary mapping; therefore, you do not need to encode for these characters).</span></span>  
  
 <span data-ttu-id="a046e-172">Ce code de mise à jour ajoute un enregistrement à la table Order Details dans la base de données Northwind :</span><span class="sxs-lookup"><span data-stu-id="a046e-172">This updategram adds a record to the Order Details table in the Northwind database:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <_x005B_Order_x0020_Details_x005D_ OrderID="1"  
            ProductID="11"  
            UnitPrice="$1.0"  
            Quantity="1"  
            Discount="0.0" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-173">La colonne UnitPrice dans la table Order Details est du type `money`.</span><span class="sxs-lookup"><span data-stu-id="a046e-173">The UnitPrice column in the Order Details table is of the `money` type.</span></span> <span data-ttu-id="a046e-174">Pour appliquer la conversion de type appropriée (d'un type `string` en type `money`), le caractère $ doit être ajouté à la valeur.</span><span class="sxs-lookup"><span data-stu-id="a046e-174">To apply the appropriate type conversion (from a `string` type to a `money` type), the dollar sign character ($) must be added as part of the value.</span></span> <span data-ttu-id="a046e-175">Si le code de mise à jour ne spécifie pas de schéma de mappage, le premier caractère de la valeur `string` est évalué.</span><span class="sxs-lookup"><span data-stu-id="a046e-175">If the updategram does not specify a mapping schema, the first character of the `string` value is evaluated.</span></span> <span data-ttu-id="a046e-176">Si le premier caractère est le signe $, la conversion appropriée est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a046e-176">If the first character is a dollar sign ($), the appropriate conversion is applied.</span></span>  
  
 <span data-ttu-id="a046e-177">Si le code de mise à jour est spécifié sur un schéma de mappage où la colonne est marquée de façon appropriée en tant que `dt:type="fixed.14.4"` ou `sql:datatype="money"`, le signe $ n'est pas requis et la conversion est contrôlée par le mappage.</span><span class="sxs-lookup"><span data-stu-id="a046e-177">If the updategram is specified against a mapping schema where the column is appropriately marked as either `dt:type="fixed.14.4"` or `sql:datatype="money"`, the dollar sign ($) is not required and the conversion is handled by the mapping.</span></span> <span data-ttu-id="a046e-178">Il s'agit de la méthode recommandée pour garantir que la conversion de type appropriée a lieu.</span><span class="sxs-lookup"><span data-stu-id="a046e-178">This is the recommended way to ensure that the appropriate type conversion occurs.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="a046e-179">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="a046e-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="a046e-180">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-180">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-181">Enregistrez le fichier sous le nom UpdategramSpacesInTableName.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-181">Save the file as UpdategramSpacesInTableName.xml.</span></span>  
  
2.  <span data-ttu-id="a046e-182">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="a046e-182">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a046e-183">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-183">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-using-the-at-identity-attribute-to-retrieve-the-value-that-has-been-inserted-in-the-identity-type-column"></a><span data-ttu-id="a046e-184">D.</span><span class="sxs-lookup"><span data-stu-id="a046e-184">D.</span></span> <span data-ttu-id="a046e-185">Utilisation de l'attribut at-identity pour récupérer la valeur ayant été insérée dans la colonne de type IDENTITY</span><span class="sxs-lookup"><span data-stu-id="a046e-185">Using the at-identity attribute to retrieve the value that has been inserted in the IDENTITY-type column</span></span>  
 <span data-ttu-id="a046e-186">Le code de mise à jour suivant insère deux enregistrements : un dans la table Sales.SalesOrderHeader et un autre dans la table Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="a046e-186">The following updategram inserts two records: one in the Sales.SalesOrderHeader table and another in the Sales.SalesOrderDetail table.</span></span>  
  
 <span data-ttu-id="a046e-187">En premier lieu, le code de mise à jour ajoute un enregistrement à la table Sales.SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="a046e-187">First, the updategram adds a record to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="a046e-188">Dans cette table, la colonne SalesOrderID est une colonne de type IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="a046e-188">In this table, the SalesOrderID column is an IDENTITY-type column.</span></span> <span data-ttu-id="a046e-189">Par conséquent, lorsque vous ajoutez cet enregistrement à la table, le code de mise à jour utilise l'attribut `at-identity` pour capturer la valeur SalesOrderID attribuée en tant que « x » (valeur d'espace réservé).</span><span class="sxs-lookup"><span data-stu-id="a046e-189">Therefore, when you add this record to the table, the updategram uses the `at-identity` attribute to capture the assigned SalesOrderID value as "x" (a placeholder value).</span></span> <span data-ttu-id="a046e-190">Le code spécifie ensuite cette `at-identity` variable en tant que valeur de l’attribut SalesOrderID dans l' \<Sales.SalesOrderDetail> élément.</span><span class="sxs-lookup"><span data-stu-id="a046e-190">The updategam then specifies this `at-identity` variable as the value of SalesOrderID attribute in the \<Sales.SalesOrderDetail> element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
   <Sales.SalesOrderHeader updg:at-identity="x"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00001111-2222-3333-4444-556677889900"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
      <Sales.SalesOrderDetail SalesOrderID="x"  
                LineNumber="1"  
                OrderQty="1"  
                ProductID="776"  
                SpecialOfferID="1"  
                UnitPrice="2429.9928"  
                UnitPriceDiscount="0.00"  
                rowguid="aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"  
                ModifiedDate="2001-07-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-191">Si vous souhaitez retourner la valeur d'identité générée par l'attribut `updg:at-identity`, vous pouvez utiliser l'attribut `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="a046e-191">If you want to return the identity value that is generated by the `updg:at-identity` attribute, you can use the `updg:returnid` attribute.</span></span> <span data-ttu-id="a046e-192">Le code de mise à jour modifié suivant retourne cette valeur d'identité.</span><span class="sxs-lookup"><span data-stu-id="a046e-192">The following is a revised updategram that returns this identity value.</span></span> <span data-ttu-id="a046e-193">(Ce code de mise à jour ajoute deux enregistrements de commande et deux enregistrements de détail de commande pour rendre l'exemple un peu plus complexe.)</span><span class="sxs-lookup"><span data-stu-id="a046e-193">(This updategram adds two order records and two order detail records, just to make the example a little more complex.)</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync>  
  <updg:before>  
  </updg:before>  
  <updg:after updg:returnid="x y" >  
       <HumanResources.Shift updg:at-identity="x" Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift updg:at-identity="y" Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:after>  
 </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-194">Lorsque le code de mise à jour est exécuté, il retourne des résultats semblables aux suivants, qui comprennent notamment la valeur d'identité (valeur générée de la colonne ShiftID utilisée pour l'identité de table) ayant été générée :</span><span class="sxs-lookup"><span data-stu-id="a046e-194">When the updategram is executed, it returns results similar to the following, which includes the identity value (the generated value of the ShiftID column used for table identity) that was generated:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">   
  <returnid>   
    <x>4</x>   
    <y>5</y>   
  </returnid>   
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="a046e-195">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="a046e-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="a046e-196">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-196">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-197">Enregistrez le fichier sous le nom Updategram-returnId.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-197">Save the file as Updategram-returnId.xml.</span></span>  
  
2.  <span data-ttu-id="a046e-198">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="a046e-198">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a046e-199">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-199">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-the-updgguid-attribute-to-generate-a-unique-value"></a><span data-ttu-id="a046e-200">E.</span><span class="sxs-lookup"><span data-stu-id="a046e-200">E.</span></span> <span data-ttu-id="a046e-201">Utilisation de l'attribut updg:guid pour générer une valeur unique</span><span class="sxs-lookup"><span data-stu-id="a046e-201">Using the updg:guid attribute to generate a unique value</span></span>  
 <span data-ttu-id="a046e-202">Dans cet exemple, le code de mise à jour insère un enregistrement dans les tables Cust et CustOrder.</span><span class="sxs-lookup"><span data-stu-id="a046e-202">In this example, the updategram inserts a record in the Cust and CustOrder tables.</span></span> <span data-ttu-id="a046e-203">Par ailleurs, le code de mise à jour génère une valeur unique pour l'attribut CustomerID à l'aide de l'attribut `updg:guid`.</span><span class="sxs-lookup"><span data-stu-id="a046e-203">Also, the updategram generates a unique value for the CustomerID attribute by using the `updg:guid` attribute.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after updg:returnid="x" >  
      <Cust updg:guid="x" >  
         <CustID>x</CustID>  
         <LastName>Fuller</LastName>  
      </Cust>  
      <CustOrder>  
         <CustID>x</CustID>  
         <OrderID>1</OrderID>  
      </CustOrder>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-204">Le code de mise à jour spécifie l'attribut `returnid`.</span><span class="sxs-lookup"><span data-stu-id="a046e-204">The updategram specifies the `returnid` attribute.</span></span> <span data-ttu-id="a046e-205">En conséquence, le GUID généré est retourné :</span><span class="sxs-lookup"><span data-stu-id="a046e-205">As a result, the GUID that is generated is returned:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <returnid>  
    <x>7111BD1A-7F0B-4CEE-B411-260DADFEFA2A</x>   
  </returnid>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a046e-206">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a046e-207">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-207">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-208">Enregistrez le fichier sous le nom Updategram-GenerateGuid.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-208">Save the file as Updategram-GenerateGuid.xml.</span></span>  
  
2.  <span data-ttu-id="a046e-209">Créez les tables suivantes :</span><span class="sxs-lookup"><span data-stu-id="a046e-209">Create these tables:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust (CustID uniqueidentifier, LastName varchar(20))  
    CREATE TABLE CustOrder (CustID uniqueidentifier, OrderID int)  
    ```  
  
3.  <span data-ttu-id="a046e-210">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="a046e-210">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a046e-211">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-211">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="f-specifying-a-schema-in-an-updategram"></a><span data-ttu-id="a046e-212">F.</span><span class="sxs-lookup"><span data-stu-id="a046e-212">F.</span></span> <span data-ttu-id="a046e-213">Spécification d'un schéma dans un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-213">Specifying a schema in an updategram</span></span>  
 <span data-ttu-id="a046e-214">Le code de mise à jour dans cet exemple insère un enregistrement dans la table suivante :</span><span class="sxs-lookup"><span data-stu-id="a046e-214">The updategram in this example inserts a record into the following table:</span></span>  
  
```  
CustOrder(OrderID, EmployeeID, OrderType)  
```  
  
 <span data-ttu-id="a046e-215">Un schéma XSD est spécifié dans ce code de mise à jour (autrement dit, il n'y a aucun mappage par défaut des éléments et des attributs du code de mise à jour).</span><span class="sxs-lookup"><span data-stu-id="a046e-215">An XSD schema is specified in this updategram (that is, there is no default mapping of updategram elements and attributes).</span></span> <span data-ttu-id="a046e-216">Le schéma fournit le mappage nécessaire des éléments et des attributs aux tables et aux colonnes de base de données.</span><span class="sxs-lookup"><span data-stu-id="a046e-216">The schema provides the necessary mapping of the elements and attributes to the database tables and columns.</span></span>  
  
 <span data-ttu-id="a046e-217">Le schéma suivant (CustOrderSchema.xml) décrit un **\<CustOrder>** élément qui se compose des attributs **OrderID** et **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="a046e-217">The following schema (CustOrderSchema.xml) describes a **\<CustOrder>** element that consists of the **OrderID** and **EmployeeID** attributes.</span></span> <span data-ttu-id="a046e-218">Pour rendre le schéma plus intéressant, une valeur par défaut est assignée à l’attribut **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="a046e-218">To make the schema more interesting, a default value is assigned to the **EmployeeID** attribute.</span></span> <span data-ttu-id="a046e-219">Un code de mise à jour utilise uniquement la valeur par défaut d'un attribut pour les opérations d'insertion, puis uniquement si le code de mise à jour ne spécifie pas cet attribut.</span><span class="sxs-lookup"><span data-stu-id="a046e-219">An updategram uses an attribute's default value only for insert operations, and then only if the updategram does not specify that attribute.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="CustOrder" >  
   <xsd:complexType>  
        <xsd:attribute name="OrderID"     type="xsd:integer" />   
        <xsd:attribute name="EmployeeID"  type="xsd:integer" />  
        <xsd:attribute name="OrderType  " type="xsd:integer" default="1"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="a046e-220">Ce code de mise à jour insère un enregistrement dans la table CustOrder.</span><span class="sxs-lookup"><span data-stu-id="a046e-220">This updategram inserts a record into the CustOrder table.</span></span> <span data-ttu-id="a046e-221">Le code de mise à jour spécifie uniquement les valeurs des attributs OrderID et EmployeeID.</span><span class="sxs-lookup"><span data-stu-id="a046e-221">The updategram specifies only the OrderID and EmployeeID attribute values.</span></span> <span data-ttu-id="a046e-222">Il ne spécifie pas la valeur de l'attribut OrderType.</span><span class="sxs-lookup"><span data-stu-id="a046e-222">It does not specify the OrderType attribute value.</span></span> <span data-ttu-id="a046e-223">Par conséquent, le code de mise à jour utilise la valeur par défaut de l'attribut EmployeeID spécifié dans le schéma précédent.</span><span class="sxs-lookup"><span data-stu-id="a046e-223">Therefore, the updategram uses the default value of the EmployeeID attribute that is specified in the preceding schema.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
             xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync mapping-schema='CustOrderSchema.xml'>  
<updg:after>  
       <CustOrder OrderID="98000" EmployeeID="1" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-224">Pour obtenir plus d’exemples de codes qui spécifient un schéma de mappage, consultez [spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-224">For more examples of updategrams that specify a mapping schema, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a046e-225">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-225">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a046e-226">Créez cette table dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="a046e-226">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE CustOrder(  
                     OrderID int,   
                     EmployeeID int,   
                     OrderType int)  
    ```  
  
2.  <span data-ttu-id="a046e-227">Copiez le schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-227">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="a046e-228">Enregistrez le fichier sous le nom CustOrderSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-228">Save the file as CustOrderSchema.xml.</span></span>  
  
3.  <span data-ttu-id="a046e-229">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-229">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-230">Enregistrez le fichier sous le nom CustOrderUpdategram.xml dans le même dossier qu'à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a046e-230">Save the file as CustOrderUpdategram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="a046e-231">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="a046e-231">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="a046e-232">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-232">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a046e-233">Voici le schéma XDR équivalent :</span><span class="sxs-lookup"><span data-stu-id="a046e-233">This is the equivalent XDR schema:</span></span>  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
 <ElementType name="CustOrder" >  
    <AttributeType name="OrderID" />  
    <AttributeType name="EmployeeID" />  
    <AttributeType name="OrderType" default="1" />  
    <attribute type="OrderID"  />  
    <attribute type="EmployeeID" />  
    <attribute type="OrderType" />  
  </ElementType>  
</Schema>  
```  
  
### <a name="g-using-the-xsinil-attribute-to-insert-null-values-in-a-column"></a><span data-ttu-id="a046e-234">G.</span><span class="sxs-lookup"><span data-stu-id="a046e-234">G.</span></span> <span data-ttu-id="a046e-235">Utilisation de l'attribut xsi:nil pour insérer des valeurs Null dans une colonne</span><span class="sxs-lookup"><span data-stu-id="a046e-235">Using the xsi:nil attribute to insert null values in a column</span></span>  
 <span data-ttu-id="a046e-236">Si vous souhaitez insérer une valeur NULL dans la colonne correspondante dans la table, vous pouvez spécifier l'attribut `xsi:nil` sur un élément dans un code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a046e-236">If you want to insert a null value in the corresponding column in the table, you can specify the `xsi:nil` attribute on an element in an updategram.</span></span> <span data-ttu-id="a046e-237">Dans le schéma XSD correspondant, l'attribut `nillable` XSD doit également être spécifié.</span><span class="sxs-lookup"><span data-stu-id="a046e-237">In the corresponding XSD schema, the XSD `nillable` attribute also must be specified.</span></span>  
  
 <span data-ttu-id="a046e-238">Considérons par exemple ce schéma XSD :</span><span class="sxs-lookup"><span data-stu-id="a046e-238">For example, consider this XSD schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="Student" sql:relation="Students">  
  <xsd:complexType>  
    <xsd:all>  
      <xsd:element name="fname" sql:field="first_name"   
                                type="xsd:string"   
                                 nillable="true"/>  
    </xsd:all>  
    <xsd:attribute name="SID"   
                        sql:field="StudentID"  
                        type="xsd:ID"/>      
    <xsd:attribute name="lname"       
                        sql:field="last_name"  
                        type="xsd:string"/>  
    <xsd:attribute name="minitial"    
                        sql:field="middle_initial"   
                        type="xsd:string"/>  
    <xsd:attribute name="years"       
                         sql:field="no_of_years"  
                         type="xsd:integer"/>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="a046e-239">Le schéma XSD spécifie **nillable = "true"** pour l' **\<fname>** élément.</span><span class="sxs-lookup"><span data-stu-id="a046e-239">The XSD schema specifies **nillable="true"** for the **\<fname>** element.</span></span> <span data-ttu-id="a046e-240">Le code de mise à jour suivant utilise ce schéma :</span><span class="sxs-lookup"><span data-stu-id="a046e-240">The following updategram uses this schema:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
      xmlns:updg="urn:schemas-microsoft-com:xml-updategram"  
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  
<updg:sync mapping-schema='StudentSchema.xml'>  
  <updg:before/>  
  <updg:after>  
    <Student SID="S00004" lname="Elmaci" minitial="" years="2">  
      <fname xsi:nil="true">  
    </fname>  
    </Student>  
  </updg:after>  
</updg:sync>  
  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-241">Mise à jour spécifie `xsi:nil` pour l' **\<fname>** élément dans le **\<after>** bloc.</span><span class="sxs-lookup"><span data-stu-id="a046e-241">The updategram specifies `xsi:nil` for the **\<fname>** element in the **\<after>** block.</span></span> <span data-ttu-id="a046e-242">Par conséquent, lorsque ce code de mise à jour est exécuté, une valeur NULL est insérée pour la colonne first_name dans la table.</span><span class="sxs-lookup"><span data-stu-id="a046e-242">Therefore, when this updategram is executed, a value of NULL is inserted for the first_name column in the table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a046e-243">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-243">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a046e-244">Créez la table suivante dans la base de données **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="a046e-244">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Students (  
       StudentID char(6)NOT NULL ,  
       first_name varchar(50),  
       last_name varchar(50),  
       middle_initial char(1),  
       no_of_years int NULL)  
    GO  
    ```  
  
2.  <span data-ttu-id="a046e-245">Copiez le schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-245">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="a046e-246">Enregistrez ce fichier sous le nom StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-246">Save the file as StudentSchema.xml.</span></span>  
  
3.  <span data-ttu-id="a046e-247">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-247">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-248">Enregistrez le fichier sous le nom StudentUpdategram.xml dans le même dossier qu'à l'étape précédente pour enregistrer StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-248">Save the file as StudentUpdategram.xml in the same folder used in previous step to save StudentSchema.xml.</span></span>  
  
4.  <span data-ttu-id="a046e-249">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="a046e-249">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="a046e-250">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-250">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="h-specifying-namespaces-in-an-updategram"></a><span data-ttu-id="a046e-251">H.</span><span class="sxs-lookup"><span data-stu-id="a046e-251">H.</span></span> <span data-ttu-id="a046e-252">Spécification d'espaces de noms dans un code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-252">Specifying namespaces in an updategram</span></span>  
 <span data-ttu-id="a046e-253">Dans un code de mise à jour, vous pouvez avoir des éléments qui appartiennent à un espace de noms déclaré dans le même élément dans le code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a046e-253">In an updategram you can have elements that belong to a namespace declared in the same element in the updategram.</span></span> <span data-ttu-id="a046e-254">Dans ce cas, le schéma correspondant doit également déclarer le même espace de noms et l'élément doit appartenir à cet espace de noms cible.</span><span class="sxs-lookup"><span data-stu-id="a046e-254">In this case, the corresponding schema must also declare the same namespace and the element must belong to that target namespace.</span></span>  
  
 <span data-ttu-id="a046e-255">Par exemple, dans le mise à jour (UpdateGram-ElementHavingNamespace.xml) suivant, l' **\<Order>** élément appartient à un espace de noms déclaré dans l’élément.</span><span class="sxs-lookup"><span data-stu-id="a046e-255">For example, in the following updategram (UpdateGram-ElementHavingNamespace.xml), the **\<Order>** element belongs to a namespace declared in the element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema='XSD-ElementHavingNameSpace.xml'>  
    <updg:after>  
       <x:Order  xmlns:x="http://server/xyz/schemas/"  
             updg:at-identity="SalesOrderID"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00009999-8888-7777-6666-554433221100"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-256">Dans ce cas, le schéma doit également déclarer l'espace de noms comme montré dans ce schéma :</span><span class="sxs-lookup"><span data-stu-id="a046e-256">In this case, the schema must also declare the namespace as shown in this schema:</span></span>  
  
 <span data-ttu-id="a046e-257">Le schéma suivant (XSD-ElementHavingNamespace.xml) montre comment l'élément et les attributs correspondants doivent être déclarés.</span><span class="sxs-lookup"><span data-stu-id="a046e-257">The following schema (XSD-ElementHavingNamespace.xml) shows how the corresponding element and attributes must be declared.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns:dt="urn:schemas-microsoft-com:datatypes"   
     xmlns:sql="urn:schemas-microsoft-com:mapping-schema"    
     xmlns:x="http://server/xyz/schemas/"   
     targetNamespace="http://server/xyz/schemas/" >  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="x:Order_type"/>  
  <xsd:complexType name="Order_type">  
    <xsd:attribute name="SalesOrderID"  type="xsd:ID"/>  
    <xsd:attribute name="RevisionNumber" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OrderDate" type="xsd:dateTime"/>  
    <xsd:attribute name="DueDate" type="xsd:dateTime"/>  
    <xsd:attribute name="ShipDate" type="xsd:dateTime"/>  
    <xsd:attribute name="Status" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OnlineOrderFlag" type="xsd:boolean"/>  
    <xsd:attribute name="SalesOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="PurchaseOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="AccountNumber" type="xsd:string"/>  
    <xsd:attribute name="CustomerID" type="xsd:int"/>  
    <xsd:attribute name="ContactID" type="xsd:int"/>  
    <xsd:attribute name="SalesPersonID" type="xsd:int"/>  
    <xsd:attribute name="TerritoryID" type="xsd:int"/>  
    <xsd:attribute name="BillToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipMethodID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardApprovalCode" type="xsd:string"/>  
    <xsd:attribute name="CurrencyRateID" type="xsd:int"/>  
    <xsd:attribute name="SubTotal" type="xsd:decimal"/>  
    <xsd:attribute name="TaxAmt" type="xsd:decimal"/>  
    <xsd:attribute name="Freight" type="xsd:decimal"/>  
    <xsd:attribute name="TotalDue" type="xsd:decimal"/>  
    <xsd:attribute name="Comment" type="xsd:string"/>  
    <xsd:attribute name="rowguid" type="xsd:string"/>  
    <xsd:attribute name="ModifiedDate" type="xsd:dateTime"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a046e-258">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-258">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a046e-259">Copiez le schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-259">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="a046e-260">Enregistrez le fichier sous le nom XSD-ElementHavingNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-260">Save the file as XSD-ElementHavingNamespace.xml.</span></span>  
  
2.  <span data-ttu-id="a046e-261">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-261">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-262">Enregistrez le fichier sous le nom Updategram-ElementHavingNamespace.xml dans le même dossier que celui utilisé pour enregistrer XSD-ElementHavingnamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-262">Save the file as Updategram-ElementHavingNamespace.xml in the same folder used to save XSD-ElementHavingnamespace.xml.</span></span>  
  
3.  <span data-ttu-id="a046e-263">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="a046e-263">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="a046e-264">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-264">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="i-inserting-data-into-an-xml-data-type-column"></a><span data-ttu-id="a046e-265">I.</span><span class="sxs-lookup"><span data-stu-id="a046e-265">I.</span></span> <span data-ttu-id="a046e-266">Insertion de données dans une colonne de type de données XML</span><span class="sxs-lookup"><span data-stu-id="a046e-266">Inserting data into an XML data type column</span></span>  
 <span data-ttu-id="a046e-267">Le type de données `xml` a été introduit dans [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a046e-267">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="a046e-268">Vous pouvez utiliser des codes de mise à jour pour insérer et mettre à jour des données stockées dans des colonnes de type de données `xml` avec les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a046e-268">You can use updategrams to insert and update data stored in `xml` data type columns with the following provisions:</span></span>  
  
-   <span data-ttu-id="a046e-269">La colonne `xml` ne peut pas être utilisée pour identifier une ligne existante.</span><span class="sxs-lookup"><span data-stu-id="a046e-269">The `xml` column cannot be used for identifying an existing row.</span></span> <span data-ttu-id="a046e-270">Par conséquent, elle ne peut pas être incluse dans la section `updg:before` d'un code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="a046e-270">Therefore, it cannot be included in the `updg:before` section of an updategram.</span></span>  
  
-   <span data-ttu-id="a046e-271">Les espaces de noms qui figurent dans la portée du fragment XML inséré dans la colonne `xml` sont conservés et leurs déclarations d'espace de noms sont ajoutées à l'élément du plus haut niveau du fragment inséré.</span><span class="sxs-lookup"><span data-stu-id="a046e-271">Namespaces that are in scope of the XML fragment inserted into the `xml` column will be preserved and their namespace declarations are added to the top element of the inserted fragment.</span></span>  
  
 <span data-ttu-id="a046e-272">Par exemple, dans le mise à jour (SampleUpdateGram.xml) suivant, l' **\<Desc>** élément met à jour la colonne ProductDescription de la table ProductModel de Production>de l' [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] exemple de base de données.</span><span class="sxs-lookup"><span data-stu-id="a046e-272">For example, in the following updategram (SampleUpdateGram.xml), the **\<Desc>** element updates the ProductDescription column in the Production>productModel table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="a046e-273">Le résultat de cette mise à jour est que le contenu XML de la colonne ProductDescription est mis à jour avec le contenu XML de l' **\<Desc>** élément.</span><span class="sxs-lookup"><span data-stu-id="a046e-273">The result of this updategram is that the XML contents of the ProductDescription column are update with the XML contents of the **\<Desc>** element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
       <updg:before>  
<ProductModel ProductModelID="19">  
   <Name>Mountain-100</Name>  
</ProductModel>  
    </updg:before>  
    <updg:after>  
 <ProductModel>  
    <Name>Mountain-100</Name>  
    <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
        <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
              xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
              xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
              xmlns:html="http://www.w3.org/1999/xhtml"   
              xmlns="">  
  <p1:Summary>  
     <html:p>Insert Example</html:p>  
  </p1:Summary>  
  <p1:Manufacturer>  
    <p1:Name>AdventureWorks</p1:Name>  
    <p1:Copyright>2002</p1:Copyright>  
    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
  </p1:Manufacturer>  
  <p1:Features>These are the product highlights.   
    <wm:Warranty>  
       <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
       <wm:Description>parts and labor</wm:Description>  
    </wm:Warranty>  
    <wm:Maintenance>  
       <wm:NoOfYears>10 years</wm:NoOfYears>  
       <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
    </wm:Maintenance>  
    <wf:wheel>High performance wheels.</wf:wheel>  
    <wf:saddle>  
      <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle>  
    <wf:pedal>  
       <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal>  
    <wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter and wall-thickness required of a premium mountain frame. The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame>  
    <wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset>  
   </p1:Features>  
   <p1:Picture>  
      <p1:Angle>front</p1:Angle>  
      <p1:Size>small</p1:Size>  
      <p1:ProductPhotoID>118</p1:ProductPhotoID>  
   </p1:Picture>  
   <p1:Specifications> These are the product specifications.  
     <Material>Almuminum Alloy</Material>  
     <Color>Available in most colors</Color>  
     <ProductLine>Mountain bike</ProductLine>  
     <Style>Unisex</Style>  
     <RiderExperience>Advanced to Professional riders</RiderExperience>  
   </p1:Specifications>  
  </p1:ProductDescription>  
 </Desc>  
      </ProductModel>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="a046e-274">Le code de mise à jour fait référence au schéma XSD annoté suivant (SampleSchema.xml).</span><span class="sxs-lookup"><span data-stu-id="a046e-274">The updategram refers to the following annotated XSD schema (SampleSchema.xml).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
     <xsd:complexType>  
       <xsd:sequence>  
          <xsd:element name="Name" type="xsd:string"></xsd:element>  
          <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
           <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="ProductDescription">  
                 <xsd:complexType>  
                   <xsd:sequence>  
                     <xsd:element name="Summary" type="xsd:anyType">  
                     </xsd:element>  
                   </xsd:sequence>  
                 </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>   
       </xsd:sequence>  
       <xsd:attribute name="ProductModelID" sql:field="ProductModelID"/>  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="a046e-275">Pour tester le code de mise à jour</span><span class="sxs-lookup"><span data-stu-id="a046e-275">To test the updategram</span></span>  
  
1.  <span data-ttu-id="a046e-276">Copiez le schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-276">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="a046e-277">Enregistrez le fichier sous le nom XSD-SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-277">Save the file as XSD-SampleSchema.xml.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a046e-278">Étant donné que les codes de mise à jour prennent en charge le mappage par défaut, il est impossible d'identifier le début et la fin du type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="a046e-278">Because updategrams support default mapping, there is no way to identify the beginning and ending of the `xml` data type.</span></span> <span data-ttu-id="a046e-279">Cela signifie qu'un schéma de mappage est requis lors de l'insertion ou de la mise à jour de tables avec des colonnes de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="a046e-279">This effectively means that a mapping schema is required when inserting or updating tables with `xml` data type columns.</span></span> <span data-ttu-id="a046e-280">Lorsqu'un schéma n'est pas fourni, SQLXML retourne une erreur indiquant que l'une des colonnes est absente de la table.</span><span class="sxs-lookup"><span data-stu-id="a046e-280">When a schema is not provided, SQLXML returns an error indicating that one of the columns is missing from the table.</span></span>  
  
2.  <span data-ttu-id="a046e-281">Copiez le code de mise à jour ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="a046e-281">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="a046e-282">Enregistrez le fichier sous le nom SampleUpdategram.xml dans le même dossier que celui utilisé pour enregistrer SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="a046e-282">Save the file as SampleUpdategram.xml in the same folder used to save SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="a046e-283">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="a046e-283">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="a046e-284">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a046e-284">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a046e-285">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a046e-285">See Also</span></span>  
 [<span data-ttu-id="a046e-286">Considérations sur la sécurité mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="a046e-286">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
