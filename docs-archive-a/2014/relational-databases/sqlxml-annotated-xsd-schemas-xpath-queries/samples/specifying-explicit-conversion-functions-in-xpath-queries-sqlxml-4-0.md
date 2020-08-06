---
title: Spécification de fonctions de conversion explicite dans les requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit conversion functions [SQLXML]
- string function
- number function
- XPath queries [SQLXML], explicit conversion functions
ms.assetid: 1111cb5d-2bd9-4bdb-8de2-dc0e47452dd6
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b4b9bd5f5665c8cb86cb74c1397e2bd06e113fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600732"
---
# <a name="specifying-explicit-conversion-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="5889a-102">Spécification de fonctions de conversion explicite dans les requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5889a-102">Specifying Explicit Conversion Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="5889a-103">Les exemples suivants montrent comment les fonctions de conversion explicite sont spécifiées dans les requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="5889a-103">The following examples show how explicit conversion functions are specified in XPath queries.</span></span> <span data-ttu-id="5889a-104">Les requêtes XPath de ces exemples sont spécifiées par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="5889a-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="5889a-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5889a-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5889a-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="5889a-106">Examples</span></span>  
  
### <a name="a-use-the-number-explicit-conversion-function"></a><span data-ttu-id="5889a-107">R.</span><span class="sxs-lookup"><span data-stu-id="5889a-107">A.</span></span> <span data-ttu-id="5889a-108">Utiliser la fonction de conversion explicite number()</span><span class="sxs-lookup"><span data-stu-id="5889a-108">Use the number() explicit conversion function</span></span>  
 <span data-ttu-id="5889a-109">La fonction `number()` convertit un argument en un nombre.</span><span class="sxs-lookup"><span data-stu-id="5889a-109">The `number()` function converts an argument to a number.</span></span>  
  
 <span data-ttu-id="5889a-110">En supposant que la valeur de **ContactID** n’est pas numérique, la requête suivante convertit **ContactID** en nombre et le compare à la valeur 4.</span><span class="sxs-lookup"><span data-stu-id="5889a-110">Assuming the value of **ContactID** is nonnumeric, the following query converts **ContactID** to a number and compares it with the value 4.</span></span> <span data-ttu-id="5889a-111">La requête retourne ensuite tous les **\<Employee>** éléments enfants du nœud de contexte avec l’attribut **ContactID** qui a une valeur numérique de 4 :</span><span class="sxs-lookup"><span data-stu-id="5889a-111">The query then returns all **\<Employee>** element children of the context node with the **ContactID** attribute that has a numeric value of 4:</span></span>  
  
```  
/child::Contact[number(attribute::ContactID)= 4]  
```  
  
 <span data-ttu-id="5889a-112">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et comme l'axe `child` est la valeur par défaut, il peut être absent de la requête :</span><span class="sxs-lookup"><span data-stu-id="5889a-112">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[number(@ContactID) = 4]  
```  
  
 <span data-ttu-id="5889a-113">En termes relationnels, la requête retourne un employé avec un **ContactID** de 4.</span><span class="sxs-lookup"><span data-stu-id="5889a-113">In relational terms, the query returns an employee with a **ContactID** of 4.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="5889a-114">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="5889a-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="5889a-115">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5889a-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="5889a-116">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="5889a-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="5889a-117">Créez le modèle suivant (ExplicitConversionA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="5889a-117">Create the following template (ExplicitConversionA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact[number(@ContactID)=4]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="5889a-118">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="5889a-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="5889a-119">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="5889a-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="5889a-120">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="5889a-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="5889a-121">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5889a-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="5889a-122">Le jeu de résultats pour cette exécution de modèle est :</span><span class="sxs-lookup"><span data-stu-id="5889a-122">The result set for this template execution is:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
### <a name="b-use-the-string-explicit-conversion-function"></a><span data-ttu-id="5889a-123">B.</span><span class="sxs-lookup"><span data-stu-id="5889a-123">B.</span></span> <span data-ttu-id="5889a-124">Utiliser la fonction de conversion explicite string()</span><span class="sxs-lookup"><span data-stu-id="5889a-124">Use the string() explicit conversion function</span></span>  
 <span data-ttu-id="5889a-125">La fonction `string()` convertit un argument en une chaîne.</span><span class="sxs-lookup"><span data-stu-id="5889a-125">The `string()` function converts an argument to a string.</span></span>  
  
 <span data-ttu-id="5889a-126">La requête suivante convertit **ContactID** en une chaîne et le compare à la valeur de chaîne « 4 ».</span><span class="sxs-lookup"><span data-stu-id="5889a-126">The following query converts **ContactID** to a string and compares it with the string value "4".</span></span> <span data-ttu-id="5889a-127">La requête retourne tous les **\<Employee>** éléments enfants du nœud de contexte avec un **ContactID** avec une valeur de chaîne de « 4 » :</span><span class="sxs-lookup"><span data-stu-id="5889a-127">The query returns all **\<Employee>** element children of the context node with a **ContactID** with a string value of "4":</span></span>  
  
```  
/child::Contact[string(attribute::ContactID)="4"]  
```  
  
 <span data-ttu-id="5889a-128">Il est possible de spécifier un raccourci vers l'axe `attribute` (@), et comme l'axe `child` est la valeur par défaut, il peut être absent de la requête :</span><span class="sxs-lookup"><span data-stu-id="5889a-128">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Contact[string(@ContactID)="4"]  
```  
  
 <span data-ttu-id="5889a-129">Fonctionnellement, cette requête retourne les mêmes résultats que l'exemple de requête précédent, bien que l'évaluation soit effectuée contre une valeur de chaîne et non la valeur numérique (autrement dit, le nombre 4).</span><span class="sxs-lookup"><span data-stu-id="5889a-129">Functionally, this query returns the same results as the previous example query, though the evaluation is done against a string value and not the numeric value (that is, the number 4).</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="5889a-130">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="5889a-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="5889a-131">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5889a-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="5889a-132">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="5889a-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="5889a-133">Créez le modèle suivant (ExplicitConversionB.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="5889a-133">Create the following template (ExplicitConversionB.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Contact[string(@ContactID)="4"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="5889a-134">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="5889a-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="5889a-135">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="5889a-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="5889a-136">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="5889a-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="5889a-137">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5889a-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="5889a-138">Voici le jeu de résultats de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="5889a-138">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />   
</ROOT>  
```  
  
  
