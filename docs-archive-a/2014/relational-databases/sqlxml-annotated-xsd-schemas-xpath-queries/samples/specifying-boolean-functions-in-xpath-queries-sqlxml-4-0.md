---
title: Spécification de fonctions booléennes dans des requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], Boolean functions
- false function
- not function [SQLXML]
- true function
- Boolean functions
ms.assetid: c72cd333-9294-4d41-84f2-1748bf20e3eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d230c7cd8792066732085b9ce501c0794687d17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600737"
---
# <a name="specifying-boolean-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="63013-102">Spécification de fonctions booléennes dans des requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="63013-102">Specifying Boolean Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="63013-103">Les exemples suivants montrent comment spécifier des fonctions booléennes dans des requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="63013-103">The following examples show how Boolean functions are specified in XPath queries.</span></span> <span data-ttu-id="63013-104">Les requêtes XPath de ces exemples sont spécifiées par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="63013-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="63013-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="63013-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="63013-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="63013-106">Examples</span></span>  
  
## <a name="a-specify-the-not-boolean-function"></a><span data-ttu-id="63013-107">R.</span><span class="sxs-lookup"><span data-stu-id="63013-107">A.</span></span> <span data-ttu-id="63013-108">Spécifier la fonction booléenne not()</span><span class="sxs-lookup"><span data-stu-id="63013-108">Specify the not() Boolean function</span></span>  
 <span data-ttu-id="63013-109">Cette requête retourne tous les **\<Customer>** éléments enfants du nœud de contexte qui n’ont pas d' **\<Order>** éléments enfants :</span><span class="sxs-lookup"><span data-stu-id="63013-109">This query returns all the **\<Customer>** child elements of the context node that do not have **\<Order>** child elements:</span></span>  
  
```  
/child::Customer[not(child::Order)]  
```  
  
 <span data-ttu-id="63013-110">L'axe `child` est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="63013-110">The `child` axis is the default.</span></span> <span data-ttu-id="63013-111">Par conséquent, la requête peut être spécifiée sous la forme :</span><span class="sxs-lookup"><span data-stu-id="63013-111">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="63013-112">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="63013-112">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="63013-113">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="63013-113">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="63013-114">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="63013-114">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="63013-115">Créez le modèle ci-dessous (BooleanFunctionsA.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="63013-115">Create the following template (BooleanFunctionsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[not(Order)]  
    </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="63013-116">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="63013-116">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="63013-117">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="63013-117">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="63013-118">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="63013-118">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="63013-119">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="63013-119">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="63013-120">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="63013-120">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
## <a name="b-specify-the-true-and-false-boolean-functions"></a><span data-ttu-id="63013-121">B.</span><span class="sxs-lookup"><span data-stu-id="63013-121">B.</span></span> <span data-ttu-id="63013-122">Spécifier les fonctions booléennes true() et false()</span><span class="sxs-lookup"><span data-stu-id="63013-122">Specify the true() and false() Boolean functions</span></span>  
 <span data-ttu-id="63013-123">Cette requête retourne tous les éléments **\<Customer>** enfants du nœud de contexte qui n’ont pas d' **\<Order>** éléments enfants.</span><span class="sxs-lookup"><span data-stu-id="63013-123">This query returns all **\<Customer>** element children of the context node that do not have **\<Order>** child elements.</span></span> <span data-ttu-id="63013-124">En termes relationnels, cette requête retourne tous les clients qui n'ont pas passé de commandes.</span><span class="sxs-lookup"><span data-stu-id="63013-124">In relational terms, this query returns all customers who have not placed any orders.</span></span>  
  
```  
/child::Customer[child::Order=false()]  
```  
  
 <span data-ttu-id="63013-125">L'axe `child` est la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="63013-125">The `child` axis is the default.</span></span> <span data-ttu-id="63013-126">Par conséquent, la requête peut être spécifiée sous la forme :</span><span class="sxs-lookup"><span data-stu-id="63013-126">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order=false()]  
```  
  
 <span data-ttu-id="63013-127">Cette requête est équivalente à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="63013-127">This query is equivalent to the following:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
 <span data-ttu-id="63013-128">La requête ci-dessous retourne tous les clients qui ont passé au moins une commande :</span><span class="sxs-lookup"><span data-stu-id="63013-128">The following query returns all the customers who have placed at least one order:</span></span>  
  
```  
/Customer[Order=true()]  
```  
  
 <span data-ttu-id="63013-129">Cette requête est équivalente à la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="63013-129">This query is equivalent to this one:</span></span>  
  
```  
/Customer[Order]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="63013-130">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="63013-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="63013-131">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="63013-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="63013-132">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="63013-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="63013-133">Créez le modèle ci-dessous (BooleanFunctionsB.xml) et enregistrez-le dans le même répertoire que SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="63013-133">Create the following template (BooleanFunctionsB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order=false()]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="63013-134">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="63013-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="63013-135">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="63013-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="63013-136">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="63013-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="63013-137">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="63013-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="63013-138">Voici le jeu de résultats partiel de l'exécution du modèle :</span><span class="sxs-lookup"><span data-stu-id="63013-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
  
