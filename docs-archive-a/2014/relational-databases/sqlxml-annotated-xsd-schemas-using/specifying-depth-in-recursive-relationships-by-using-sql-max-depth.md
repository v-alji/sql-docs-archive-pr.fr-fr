---
title: 'Spécification de la profondeur dans les relations récursives à l’aide de SQL : max-depth | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- max-depth annotation
- XPath queries [SQLXML], recursive relationships
- depth in recursive relationships [SQLXML]
- annotated XSD schemas, recursive relationships
- relationships [SQLXML], recursive relationships
- self joins
- recursive relationships [SQLXML]
- recursion [SQLXML]
- sql:max-depth
- recursive joins [SQLXML]
ms.assetid: 0ffdd57d-dc30-44d9-a8a0-f21cadedb327
author: rothja
ms.author: jroth
ms.openlocfilehash: 5e3ccb2de9c7b2ac8f8702b52aa990d755620e46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610999"
---
# <a name="specifying-depth-in-recursive-relationships-by-using-sqlmax-depth"></a><span data-ttu-id="c3b11-102">Spécification de la profondeur dans les relations récursives à l'aide de sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="c3b11-102">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>
  <span data-ttu-id="c3b11-103">Dans les bases de données relationnelles, lorsqu'une table est impliquée dans une relation avec elle-même, on utilise le terme de relation récursive.</span><span class="sxs-lookup"><span data-stu-id="c3b11-103">In relational databases, when a table is involved in a relationship with itself, it is called a recursive relationship.</span></span> <span data-ttu-id="c3b11-104">Par exemple, dans une relation responsable-subalterne, une table qui stocke des enregistrements d'employés est impliquée dans une relation avec elle-même.</span><span class="sxs-lookup"><span data-stu-id="c3b11-104">For example, in a supervisor-supervisee relationship, a table storing employee records is involved in a relationship with itself.</span></span> <span data-ttu-id="c3b11-105">Dans ce cas, la table d'employés joue un rôle de responsable d'un côté de la relation, et la même table joue un rôle de subalterne de l'autre côté.</span><span class="sxs-lookup"><span data-stu-id="c3b11-105">In this case, the employees table plays a role of supervisor on one side of the relationship, and the same table plays a role of supervisee on the other side.</span></span>  
  
 <span data-ttu-id="c3b11-106">Les schémas de mappage peuvent inclure des relations récursives dans lesquelles un élément et son ancêtre sont du même type.</span><span class="sxs-lookup"><span data-stu-id="c3b11-106">Mapping schemas can include recursive relationships where an element and its ancestor are of the same type.</span></span>  
  
## <a name="example-a"></a><span data-ttu-id="c3b11-107">Exemple A</span><span class="sxs-lookup"><span data-stu-id="c3b11-107">Example A</span></span>  
 <span data-ttu-id="c3b11-108">Considérez la table ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="c3b11-108">Consider the following table:</span></span>  
  
```  
Emp (EmployeeID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="c3b11-109">Dans cette table, la colonne ReportsTo stocke l'ID employé du responsable.</span><span class="sxs-lookup"><span data-stu-id="c3b11-109">In this table, the ReportsTo column stores the employee ID of the manager.</span></span>  
  
 <span data-ttu-id="c3b11-110">Supposez que vous souhaitez générer une hiérarchie XML des employés, dans laquelle l'employé responsable est en haut de la hiérarchie et les employés subalternes apparaissent dans la hiérarchie correspondante comme illustré dans le fragment d'exemple XML suivant.</span><span class="sxs-lookup"><span data-stu-id="c3b11-110">Assume that you want to generate an XML hierarchy of employees in which the manager employee is at the top of the hierarchy, and in which the employees that report to that manager appear in the corresponding hierarchy as shown in the following sample XML fragment.</span></span> <span data-ttu-id="c3b11-111">Ce fragment montre l' *arborescence récursive* pour l’employé 1.</span><span class="sxs-lookup"><span data-stu-id="c3b11-111">What this fragment shows is the *recursive tree* for employee 1.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
     <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
     <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
        <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
          <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
...  
...  
</root>  
```  
  
 <span data-ttu-id="c3b11-112">Dans ce fragment, l'employé 5 est le subalterne de l'employé 4, l'employé 4 est le subalterne de l'employé 3 et les employés 3 et 2 sont les subalternes de l'employé 1.</span><span class="sxs-lookup"><span data-stu-id="c3b11-112">In this fragment, employee 5 reports to employee 4, employee 4 reports to employee 3, and employees 3 and 2 reports to employee 1.</span></span>  
  
 <span data-ttu-id="c3b11-113">Pour produire ce résultat, vous pouvez utiliser le schéma XSD suivant et spécifier une requête XPath contre lui.</span><span class="sxs-lookup"><span data-stu-id="c3b11-113">To produce this result, you can use the following XSD schema and specify an XPath query against it.</span></span> <span data-ttu-id="c3b11-114">Le schéma décrit un **\<Emp>** élément de type EmployeeType, qui se compose d’un **\<Emp>** élément enfant du même type, EmployeeType.</span><span class="sxs-lookup"><span data-stu-id="c3b11-114">The schema describes an **\<Emp>** element of type EmployeeType, consisting of an **\<Emp>** child element of the same type, EmployeeType.</span></span> <span data-ttu-id="c3b11-115">Il s'agit d'une relation récursive (l'élément et son ancêtre sont du même type).</span><span class="sxs-lookup"><span data-stu-id="c3b11-115">This is a recursive relationship (the element and its ancestor are of the same type).</span></span> <span data-ttu-id="c3b11-116">En outre, le schéma utilise un **\<sql:relationship>** pour décrire la relation parent-enfant entre le superviseur et le superviseur.</span><span class="sxs-lookup"><span data-stu-id="c3b11-116">In addition, the schema uses a **\<sql:relationship>** to describe the parent-child relationship between the supervisor and supervisee.</span></span> <span data-ttu-id="c3b11-117">Notez que dans ce cas **\<sql:relationship>** , EMP est à la fois le parent et la table enfant.</span><span class="sxs-lookup"><span data-stu-id="c3b11-117">Note that in this **\<sql:relationship>**, Emp is both the parent and the child table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="6" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c3b11-118">La relation étant récursive, vous devez trouver un moyen de spécifier la profondeur de récursivité dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="c3b11-118">Because the relationship is recursive, you need some way to specify the depth of recursion in the schema.</span></span> <span data-ttu-id="c3b11-119">Sinon, le résultat sera une récursivité sans fin (employé subalterne à employé subalterne à employé, et ainsi de suite).</span><span class="sxs-lookup"><span data-stu-id="c3b11-119">Otherwise, the result will be an endless recursion (employee reporting to employee reporting to employee, and so on).</span></span> <span data-ttu-id="c3b11-120">L'annotation `sql:max-depth` vous permet de spécifier la profondeur de récursivité.</span><span class="sxs-lookup"><span data-stu-id="c3b11-120">The `sql:max-depth` annotation allows you to specify how deep in the recursion to go.</span></span> <span data-ttu-id="c3b11-121">Dans cet exemple particulier, pour spécifier une valeur pour `sql:max-depth`, vous devez connaître la profondeur de la hiérarchie de direction dans la société.</span><span class="sxs-lookup"><span data-stu-id="c3b11-121">In this particular example, to specify a value for `sql:max-depth`, you must know how deep the management hierarchy goes in the company.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3b11-122">Le schéma spécifie l'annotation `sql:limit-field`, mais ne spécifie pas l'annotation `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="c3b11-122">The schema specifies the `sql:limit-field` annotation, but does not specify the `sql:limit-value` annotation.</span></span> <span data-ttu-id="c3b11-123">Cela limite le nœud supérieur dans la hiérarchie résultante uniquement aux employés qui ne sont subalternes de personne.</span><span class="sxs-lookup"><span data-stu-id="c3b11-123">This limits the top node in the resulting hierarchy to only those employees who do not report to anyone.</span></span> <span data-ttu-id="c3b11-124">(Rendez-vous NULL.) Si `sql:limit-field` vous spécifiez et ne spécifiez pas `sql:limit-value` (dont la valeur par défaut est null), l’annotation effectue cette.</span><span class="sxs-lookup"><span data-stu-id="c3b11-124">(ReportsTo is NULL.) Specifying `sql:limit-field` and not specifying `sql:limit-value` (which defaults to NULL) annotation accomplishes this.</span></span> <span data-ttu-id="c3b11-125">Si vous souhaitez que le XML résultant inclue chaque arborescence de direction possible (l'arborescence de direction pour chaque employé dans la table), supprimez l'annotation `sql:limit-field` du schéma.</span><span class="sxs-lookup"><span data-stu-id="c3b11-125">If you want the resulting XML to include every possible reporting tree (the reporting tree for every employee in the table), remove the `sql:limit-field` annotation from the schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3b11-126">La procédure suivante utilise la base de données tempdb.</span><span class="sxs-lookup"><span data-stu-id="c3b11-126">The following procedure uses the tempdb database.</span></span>  
  
#### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c3b11-127">Pour tester un exemple de requête XPath sur le schéma</span><span class="sxs-lookup"><span data-stu-id="c3b11-127">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c3b11-128">Créez un exemple de table nommé Emp dans la base de données tempdb vers laquelle la racine virtuelle pointe.</span><span class="sxs-lookup"><span data-stu-id="c3b11-128">Create a sample table called Emp in the tempdb database to which the virtual root points.</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Emp (  
           EmployeeID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    ```  
  
2.  <span data-ttu-id="c3b11-129">Ajoutez les exemples de données suivants :</span><span class="sxs-lookup"><span data-stu-id="c3b11-129">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Emp values (1, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Emp values (2, 'Andrew', 'Fuller',1)  
    INSERT INTO Emp values (3, 'Janet', 'Leverling',1)  
    INSERT INTO Emp values (4, 'Margaret', 'Peacock',3)  
    INSERT INTO Emp values (5, 'Steven', 'Devolio',4)  
    INSERT INTO Emp values (6, 'Nancy', 'Buchanan',5)  
    INSERT INTO Emp values (7, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="c3b11-130">Copiez le code de schéma ci-dessus et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="c3b11-130">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c3b11-131">Enregistrez le fichier en tant que maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b11-131">Save the file as maxDepth.xml.</span></span>  
  
4.  <span data-ttu-id="c3b11-132">Copiez le modèle suivant et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="c3b11-132">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="c3b11-133">Enregistrez le fichier en tant que maxDepthT.xml dans le même répertoire où vous avez enregistré maxDepth.xml.</span><span class="sxs-lookup"><span data-stu-id="c3b11-133">Save the file as maxDepthT.xml in the same directory where you saved maxDepth.xml.</span></span> <span data-ttu-id="c3b11-134">La requête dans le modèle retourne tous les employés de la table Emp.</span><span class="sxs-lookup"><span data-stu-id="c3b11-134">The query in the template returns all the employees in the Emp table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="maxDepth.xml">  
        /Emp  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c3b11-135">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (maxDepth.xml) est relatif au répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="c3b11-135">The directory path specified for the mapping schema (maxDepth.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c3b11-136">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="c3b11-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\maxDepth.xml"  
    ```  
  
5.  <span data-ttu-id="c3b11-137">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="c3b11-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="c3b11-138">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c3b11-138">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c3b11-139">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="c3b11-139">This is the result:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
  <Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2" LastName="Fuller" />   
    <Emp FirstName="Janet" EmployeeID="3" LastName="Leverling">  
      <Emp FirstName="Margaret" EmployeeID="4" LastName="Peacock">  
        <Emp FirstName="Steven" EmployeeID="5" LastName="Devolio">  
          <Emp FirstName="Nancy" EmployeeID="6" LastName="Buchanan">  
            <Emp FirstName="Michael" EmployeeID="7" LastName="Suyama" />   
          </Emp>  
        </Emp>  
      </Emp>  
    </Emp>  
  </Emp>  
</root>  
```  
  
> [!NOTE]  
>  <span data-ttu-id="c3b11-140">Pour produire différentes profondeurs de hiérarchies dans le résultat, modifiez la valeur de l'annotation `sql:max-depth` dans le schéma et réexécutez le modèle après chaque modification.</span><span class="sxs-lookup"><span data-stu-id="c3b11-140">To produce different depths of hierarchies in the result, change the value of the `sql:max-depth` annotation in the schema and execute the template again after each change.</span></span>  
  
 <span data-ttu-id="c3b11-141">Dans le schéma précédent, tous les **\<Emp>** éléments avaient exactement le même jeu d’attributs (**EmployeeID**, **FirstName**et **LastName**).</span><span class="sxs-lookup"><span data-stu-id="c3b11-141">In the previous schema, all the **\<Emp>** elements had exactly the same set of attributes (**EmployeeID**, **FirstName**, and **LastName**).</span></span> <span data-ttu-id="c3b11-142">Le schéma suivant a été légèrement modifié pour retourner un attribut de **rendez** -vous supplémentaire pour tous les **\<Emp>** éléments signalés à un responsable.</span><span class="sxs-lookup"><span data-stu-id="c3b11-142">The following schema has been slightly modified to return an additional **ReportsTo** attribute for all the **\<Emp>** elements that report to a manager.</span></span>  
  
 <span data-ttu-id="c3b11-143">Par exemple, ce fragment XML affiche les subalternes de l'employé 1 :</span><span class="sxs-lookup"><span data-stu-id="c3b11-143">For example, this XML fragment shows the subordinates of employee 1:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<root>  
<Emp FirstName="Nancy" EmployeeID="1" LastName="Devolio">  
  <Emp FirstName="Andrew" EmployeeID="2"   
       ReportsTo="1" LastName="Fuller" />   
  <Emp FirstName="Janet" EmployeeID="3"   
       ReportsTo="1" LastName="Leverling">  
...  
...  
```  
  
 <span data-ttu-id="c3b11-144">Voici le schéma modifié :</span><span class="sxs-lookup"><span data-stu-id="c3b11-144">This is the revised schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:documentation>  
      Customer-Order-Order Details Schema  
      Copyright 2000 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"  
                  parent-key="EmployeeID"  
                  child="Emp"  
                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
                   type="EmpType"   
                   sql:relation="Emp"   
                   sql:key-fields="EmployeeID"   
                   sql:limit-field="ReportsTo" />  
  <xsd:complexType name="EmpType">  
    <xsd:sequence>  
       <xsd:element name="Emp"   
                    type="EmpType"   
                    sql:relation="Emp"   
                    sql:key-fields="EmployeeID"  
                    sql:relationship="SupervisorSupervisee"  
                    sql:max-depth="6"/>  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:int" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
    <xsd:attribute name="ReportsTo" type="xsd:int" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
## <a name="sqlmax-depth-annotation"></a><span data-ttu-id="c3b11-145">Annotation sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="c3b11-145">sql:max-depth Annotation</span></span>  
 <span data-ttu-id="c3b11-146">Dans un schéma constitué de relations récursives, la profondeur de récursivité doit être spécifiée explicitement dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="c3b11-146">In a schema consisting of recursive relationships, the depth of recursion must be explicitly specified in the schema.</span></span> <span data-ttu-id="c3b11-147">Cela est nécessaire afin de produire avec succès la requête FOR XML EXPLICIT correspondante qui retourne les résultats demandés.</span><span class="sxs-lookup"><span data-stu-id="c3b11-147">This is required to successfully produce the corresponding FOR XML EXPLICIT query that returns the requested results.</span></span>  
  
 <span data-ttu-id="c3b11-148">Utilisez l'annotation `sql:max-depth` dans le schéma pour spécifier la profondeur de récursivité dans une relation récursive décrite dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="c3b11-148">Use the `sql:max-depth` annotation in the schema to specify the depth of recursion in a recursive relationship that is described in the schema.</span></span> <span data-ttu-id="c3b11-149">La valeur de l'annotation `sql:max-depth` est un entier positif (1 à 50) qui indique le nombre de récursivités : une valeur de 1 arrête la récursivité à l'élément pour lequel l'annotation `sql:max-depth` est spécifiée ; une valeur de 2 arrête la récursivité au niveau suivant l'élément auquel `sql:max-depth` est spécifié ; et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="c3b11-149">The value of the `sql:max-depth` annotation is a positive integer (1 to 50) that indicates the number of recursions:  A value of 1 stops the recursion at the element for which the `sql:max-depth` annotation is specified; a value of 2 stops the recursion at the next level from the element at which `sql:max-depth` is specified; and so on.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3b11-150">Dans l'implémentation sous-jacente, une requête XPath spécifiée contre un schéma de mappage est convertie en requête SELECT ... FOR XML EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="c3b11-150">In the underlying implementation, an XPath query that is specified against a mapping schema is converted to a SELECT ... FOR XML EXPLICIT query.</span></span> <span data-ttu-id="c3b11-151">Cette requête nécessite que vous spécifiiez une profondeur de récursivité finie.</span><span class="sxs-lookup"><span data-stu-id="c3b11-151">This query requires you to specify a finite depth of recursion.</span></span> <span data-ttu-id="c3b11-152">Plus la valeur que vous spécifiez pour `sql:max-depth` est élevée, plus la requête FOR XML EXPLICIT générée est grande.</span><span class="sxs-lookup"><span data-stu-id="c3b11-152">The higher the value that you specify for `sql:max-depth`, the larger the FOR XML EXPLICIT query that is generated.</span></span> <span data-ttu-id="c3b11-153">Cela risque d'allonger la durée de récupération.</span><span class="sxs-lookup"><span data-stu-id="c3b11-153">This might slow the retrieval time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c3b11-154">Les codes de mise à jour (updategrams) et chargements en masse XML ignorent l'annotation max-depth.</span><span class="sxs-lookup"><span data-stu-id="c3b11-154">Updategrams and XML Bulk Load ignore the max-depth annotation.</span></span> <span data-ttu-id="c3b11-155">Cela signifie que les insertions ou mises à jour récursives ont lieu indépendamment de la valeur que vous spécifiez pour max-depth.</span><span class="sxs-lookup"><span data-stu-id="c3b11-155">This means, recursive updates or insertions will happen regardless of what value you specify for max-depth.</span></span>  
  
## <a name="specifying-sqlmax-depth-on-complex-elements"></a><span data-ttu-id="c3b11-156">Spécification de sql:max-depth sur des éléments complexes</span><span class="sxs-lookup"><span data-stu-id="c3b11-156">Specifying sql:max-depth on Complex Elements</span></span>  
 <span data-ttu-id="c3b11-157">L'annotation `sql:max-depth` peut être spécifiée sur tout élément de contenu complexe.</span><span class="sxs-lookup"><span data-stu-id="c3b11-157">The `sql:max-depth` annotation can be specified on any complex content element.</span></span>  
  
### <a name="recursive-elements"></a><span data-ttu-id="c3b11-158">Éléments récursifs</span><span class="sxs-lookup"><span data-stu-id="c3b11-158">Recursive Elements</span></span>  
 <span data-ttu-id="c3b11-159">Si `sql:max-depth` est spécifié sur l'élément parent et sur l'élément enfant dans une relation récursive, l'annotation `sql:max-depth` spécifiée sur le parent est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="c3b11-159">If `sql:max-depth` is specified on both the parent element and the child element in a recursive relationship, the `sql:max-depth` annotation specified on the parent takes precedence.</span></span> <span data-ttu-id="c3b11-160">Par exemple, dans le schéma suivant, l'annotation `sql:max-depth` est spécifiée à la fois sur les éléments employés parents et enfants.</span><span class="sxs-lookup"><span data-stu-id="c3b11-160">For example, in the following schema, the `sql:max-depth` annotation is specified on both the parent and the child employee elements.</span></span> <span data-ttu-id="c3b11-161">Dans ce cas, `sql:max-depth=4` , spécifié sur l' **\<Emp>** élément parent (jouent un rôle de superviseur), est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="c3b11-161">In this case, `sql:max-depth=4`, specified on the **\<Emp>** parent element (playing a role of supervisor), takes precedence.</span></span> <span data-ttu-id="c3b11-162">La `sql:max-depth` spécifiée sur l' **\<Emp>** élément enfant (qui jouent un rôle de superviseur) est ignorée.</span><span class="sxs-lookup"><span data-stu-id="c3b11-162">The `sql:max-depth` specified on the child **\<Emp>** element (playing a role of supervisee) is ignored.</span></span>  
  
#### <a name="example-b"></a><span data-ttu-id="c3b11-163">Exemple B</span><span class="sxs-lookup"><span data-stu-id="c3b11-163">Example B</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"  
                                  parent="Emp"  
                                  parent-key="EmployeeID"  
                                  child="Emp"  
                                  child-key="ReportsTo" />  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp" type="EmployeeType"   
                          sql:relation="Emp"   
                          sql:key-fields="EmployeeID"   
                          sql:limit-field="ReportsTo"   
                          sql:max-depth="3" />  
  <xsd:complexType name="EmployeeType">  
    <xsd:sequence>  
      <xsd:element name="Emp" type="EmployeeType"   
                              sql:relation="Emp"   
                              sql:key-fields="EmployeeID"  
                              sql:relationship="SupervisorSupervisee"  
                              sql:max-depth="2" />  
    </xsd:sequence>   
    <xsd:attribute name="EmployeeID" type="xsd:ID" />  
    <xsd:attribute name="FirstName" type="xsd:string"/>  
    <xsd:attribute name="LastName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c3b11-164">Pour tester ce schéma, suivez les étapes fournies pour l’exemple A, plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c3b11-164">To test this schema, follow the steps provided for Sample A, earlier in this topic.</span></span>  
  
### <a name="nonrecursive-elements"></a><span data-ttu-id="c3b11-165">Éléments non récursifs</span><span class="sxs-lookup"><span data-stu-id="c3b11-165">Nonrecursive Elements</span></span>  
 <span data-ttu-id="c3b11-166">Si l'annotation `sql:max-depth` est spécifiée sur un élément dans le schéma qui ne provoque pas de récursivité, elle est ignorée.</span><span class="sxs-lookup"><span data-stu-id="c3b11-166">If the `sql:max-depth` annotation is specified on an element in the schema that does not cause any recursion, it is ignored.</span></span> <span data-ttu-id="c3b11-167">Dans le schéma suivant, un **\<Emp>** élément est constitué d’un **\<Constant>** élément enfant qui, à son tour, possède un **\<Emp>** élément enfant.</span><span class="sxs-lookup"><span data-stu-id="c3b11-167">In the following schema, an **\<Emp>** element consists of a **\<Constant>** child element, which, in turn, has an **\<Emp>** child element.</span></span>  
  
 <span data-ttu-id="c3b11-168">Dans ce schéma, l' `sql:max-depth` annotation spécifiée sur l' **\<Constant>** élément est ignorée, car il n’y a pas de récursivité entre le **\<Emp>** parent et l' **\<Constant>** élément enfant.</span><span class="sxs-lookup"><span data-stu-id="c3b11-168">In this schema, the `sql:max-depth` annotation specified on the **\<Constant>** element is ignored because there is no recursion between the **\<Emp>** parent and the **\<Constant>** child element.</span></span> <span data-ttu-id="c3b11-169">Toutefois, il existe une récurrence entre l' **\<Emp>** ancêtre et l' **\<Emp>** enfant.</span><span class="sxs-lookup"><span data-stu-id="c3b11-169">But there is recursion between the **\<Emp>** ancestor and the **\<Emp>** child.</span></span> <span data-ttu-id="c3b11-170">Le schéma spécifie l'annotation `sql:max-depth` sur les deux.</span><span class="sxs-lookup"><span data-stu-id="c3b11-170">The schema specifies the `sql:max-depth` annotation on both.</span></span> <span data-ttu-id="c3b11-171">Par conséquent, l' `sql:max-depth` annotation spécifiée sur l’ancêtre ( **\<Emp>** dans le rôle superviseur) est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="c3b11-171">Therefore, the `sql:max-depth` annotation that is specified on the ancestor (**\<Emp>** in the supervisor role) takes precedence.</span></span>  
  
#### <a name="example-c"></a><span data-ttu-id="c3b11-172">Exemple C</span><span class="sxs-lookup"><span data-stu-id="c3b11-172">Example C</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
    <xsd:appinfo>  
      <sql:relationship name="SupervisorSupervisee"   
                  parent="Emp"   
                  child="Emp"   
                  parent-key="EmployeeID"   
                  child-key="ReportsTo"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="Emp"   
               sql:relation="Emp"   
               type="EmpType"  
               sql:limit-field="ReportsTo"  
               sql:max-depth="1" />  
    <xsd:complexType name="EmpType" >  
      <xsd:sequence>  
       <xsd:element name="Constant"   
                    sql:is-constant="1"   
                    sql:max-depth="20" >  
         <xsd:complexType >  
           <xsd:sequence>  
            <xsd:element name="Emp"   
                         sql:relation="Emp" type="EmpType"  
                         sql:relationship="SupervisorSupervisee"   
                         sql:max-depth="3" />  
         </xsd:sequence>  
         </xsd:complexType>  
         </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="EmployeeID" type="xsd:int" />  
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="c3b11-173">Pour tester ce schéma, suivez les étapes fournies pour l'Exemple A, plus haut dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c3b11-173">To test this schema, follow the steps provided for Example A, earlier in this topic.</span></span>  
  
## <a name="complex-types-derived-by-restriction"></a><span data-ttu-id="c3b11-174">Types complexes dérivés par restriction</span><span class="sxs-lookup"><span data-stu-id="c3b11-174">Complex Types Derived by Restriction</span></span>  
 <span data-ttu-id="c3b11-175">Si vous avez une dérivation de type complexe par **\<restriction>** , les éléments du type complexe de base correspondant ne peuvent pas spécifier l' `sql:max-depth` annotation.</span><span class="sxs-lookup"><span data-stu-id="c3b11-175">If you have a complex type derivation by **\<restriction>**, elements of the corresponding base complex type cannot specify the `sql:max-depth` annotation.</span></span> <span data-ttu-id="c3b11-176">Dans ces cas-là, l'annotation `sql:max-depth` peut être ajoutée à l'élément du type dérivé.</span><span class="sxs-lookup"><span data-stu-id="c3b11-176">In these cases, the `sql:max-depth` annotation can be added to the element of the derived type.</span></span>  
  
 <span data-ttu-id="c3b11-177">En revanche, si vous avez une dérivation de type complexe par **\<extension>** , les éléments du type complexe de base correspondant peuvent spécifier l' `sql:max-depth` annotation.</span><span class="sxs-lookup"><span data-stu-id="c3b11-177">On the other hand, if you have a complex type derivation by **\<extension>**, the elements of the corresponding base complex type can specify the `sql:max-depth` annotation.</span></span>  
  
 <span data-ttu-id="c3b11-178">Par exemple, le schéma XSD suivant génère une erreur car l'annotation `sql:max-depth` est spécifiée sur le type de base.</span><span class="sxs-lookup"><span data-stu-id="c3b11-178">For example, the following XSD schema generates an error because the `sql:max-depth` annotation is specified on the base type.</span></span> <span data-ttu-id="c3b11-179">Cette annotation n’est pas prise en charge sur un type dérivé **\<restriction>** de à partir d’un autre type.</span><span class="sxs-lookup"><span data-stu-id="c3b11-179">This annotation is not supported on a type that is derived by **\<restriction>** from another type.</span></span> <span data-ttu-id="c3b11-180">Pour résoudre ce problème, vous devez modifier le schéma et spécifier l'annotation `sql:max-depth` sur l'élément dans le type dérivé.</span><span class="sxs-lookup"><span data-stu-id="c3b11-180">To fix this problem, you must change the schema and specify the `sql:max-depth` annotation on element in the derived type.</span></span>  
  
#### <a name="example-d"></a><span data-ttu-id="c3b11-181">Exemple D</span><span class="sxs-lookup"><span data-stu-id="c3b11-181">Example D</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:complexType name="CustomerBaseType">   
    <xsd:sequence>  
       <xsd:element name="CID" msdata:field="CustomerID" />  
       <xsd:element name="CompanyName"/>  
       <xsd:element name="Customers" msdata:max-depth="3">  
         <xsd:annotation>  
           <xsd:appinfo>  
             <msdata:relationship  
                     parent="Customers"  
                     parent-key="CustomerID"  
                     child-key="CustomerID"  
                     child="Customers" />  
           </xsd:appinfo>  
         </xsd:annotation>  
       </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
  <xsd:element name="Customers" type="CustomerType"/>  
  <xsd:complexType name="CustomerType">  
    <xsd:complexContent>  
       <xsd:restriction base="CustomerBaseType">  
          <xsd:sequence>  
            <xsd:element name="CID"   
                         type="xsd:string"/>  
            <xsd:element name="CompanyName"   
                         type="xsd:string"  
                         msdata:field="CName" />  
            <xsd:element name="Customers"   
                         type="CustomerType" />  
          </xsd:sequence>  
       </xsd:restriction>  
    </xsd:complexContent>  
  </xsd:complexType>  
</xsd:schema>   
```  
  
 <span data-ttu-id="c3b11-182">Dans le schéma, `sql:max-depth` est spécifié sur un type complexe `CustomerBaseType`.</span><span class="sxs-lookup"><span data-stu-id="c3b11-182">In the schema, `sql:max-depth` is specified on a `CustomerBaseType` complex type.</span></span> <span data-ttu-id="c3b11-183">Le schéma spécifie également un **\<Customer>** élément de type `CustomerType` , dérivé de `CustomerBaseType` .</span><span class="sxs-lookup"><span data-stu-id="c3b11-183">The schema also specifies a **\<Customer>** element of type `CustomerType`, which is derived from `CustomerBaseType`.</span></span> <span data-ttu-id="c3b11-184">Une requête XPath spécifiée sur un tel schéma génère une erreur car `sql:max-depth` n'est pas pris en charge sur un élément défini dans un type de base de restriction.</span><span class="sxs-lookup"><span data-stu-id="c3b11-184">An XPath query specified on such a schema will generate an error, because `sql:max-depth` is not supported on an element that is defined in a restriction base type.</span></span>  
  
## <a name="schemas-with-a-deep-hierarchy"></a><span data-ttu-id="c3b11-185">Schémas avec une hiérarchie profonde</span><span class="sxs-lookup"><span data-stu-id="c3b11-185">Schemas with a Deep Hierarchy</span></span>  
 <span data-ttu-id="c3b11-186">Vous pouvez avoir un schéma qui inclut une hiérarchie profonde dans laquelle un élément contient un élément enfant, qui à son tour contient un autre élément enfant, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="c3b11-186">You might have a schema that includes a deep hierarchy in which an element contains a child element, which in turn contains another child element, and so on.</span></span> <span data-ttu-id="c3b11-187">Si l'annotation `sql:max-depth` spécifiée dans un tel schéma génère un document XML qui inclut une hiérarchie de plus de 500 niveaux (avec l'élément de niveau supérieur au niveau 1, son enfant au niveau 2, et ainsi de suite), une erreur est retournée.</span><span class="sxs-lookup"><span data-stu-id="c3b11-187">If the `sql:max-depth` annotation specified in such a schema generates an XML document that includes a hierarchy of more than 500 levels (with top-level element at level 1, its child at level 2, and so on), an error is returned.</span></span>  
  
  
