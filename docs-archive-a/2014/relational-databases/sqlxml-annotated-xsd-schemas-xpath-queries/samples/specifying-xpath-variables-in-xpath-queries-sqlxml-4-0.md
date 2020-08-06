---
title: Spécification de variables XPath dans les requêtes XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], XPath variables
- XPath variables [SQLXML]
ms.assetid: c11ab816-11b8-4131-8b77-c03fe500fa10
author: rothja
ms.author: jroth
ms.openlocfilehash: 5045831f627722f7dbb9a9189be5c48d830f2add
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600725"
---
# <a name="specifying-xpath-variables-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="9ac22-102">Spécification de variables XPath dans les requêtes XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="9ac22-102">Specifying XPath Variables in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="9ac22-103">Les exemples suivants expliquent comment des variables XPath sont passées dans des requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="9ac22-103">The following examples show how XPath variables are passed in XPath queries.</span></span> <span data-ttu-id="9ac22-104">Les requêtes XPath de ces exemples sont spécifiées par rapport au schéma de mappage contenu dans SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="9ac22-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="9ac22-105">Pour plus d’informations sur cet exemple de schéma, consultez [exemple de schéma XSD annoté pour les exemples XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="9ac22-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9ac22-106">Exemples</span><span class="sxs-lookup"><span data-stu-id="9ac22-106">Examples</span></span>  
  
### <a name="a-use-the-xpath-variables"></a><span data-ttu-id="9ac22-107">R.</span><span class="sxs-lookup"><span data-stu-id="9ac22-107">A.</span></span> <span data-ttu-id="9ac22-108">Utilisation des variables XPath</span><span class="sxs-lookup"><span data-stu-id="9ac22-108">Use the XPath variables</span></span>  
 <span data-ttu-id="9ac22-109">Un exemple de modèle se compose de deux requêtes XPath.</span><span class="sxs-lookup"><span data-stu-id="9ac22-109">A sample template consists of two XPath queries.</span></span> <span data-ttu-id="9ac22-110">Chacune des requêtes XPath accepte un paramètre.</span><span class="sxs-lookup"><span data-stu-id="9ac22-110">Each of the XPath queries takes one parameter.</span></span> <span data-ttu-id="9ac22-111">Le modèle spécifie également les valeurs par défaut de ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="9ac22-111">The template also specifies default values for these parameters.</span></span> <span data-ttu-id="9ac22-112">Les valeurs par défaut sont utilisées si les valeurs des paramètres ne sont pas spécifiées.</span><span class="sxs-lookup"><span data-stu-id="9ac22-112">The default values are used if parameter values are not specified.</span></span> <span data-ttu-id="9ac22-113">Deux paramètres avec des valeurs par défaut sont spécifiés dans **\<sql:header>** .</span><span class="sxs-lookup"><span data-stu-id="9ac22-113">Two parameters with default values are specified in **\<sql:header>**.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:header>  
     <sql:param name='CustomerID'>1</sql:param>  
     <sql:param name='ContactID'>1</sql:param>   
  </sql:header>  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
    Customer[@CustomerID=$CustomerID]   
  </sql:xpath-query >  
  <sql:xpath-query mapping-schema="SampleSchema1.xml">  
   Contact[@ContactID=$ContactID]   
  </sql:xpath-query>  
</ROOT>  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="9ac22-114">Pour tester la requête XPath par rapport au schéma de mappage</span><span class="sxs-lookup"><span data-stu-id="9ac22-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="9ac22-115">Copiez l' [exemple de code de schéma](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) et collez-le dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="9ac22-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="9ac22-116">Enregistrez ce fichier sous le nom SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="9ac22-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="9ac22-117">Créez le modèle suivant (XPathVariables.xml) et enregistrez-le dans le répertoire où :</span><span class="sxs-lookup"><span data-stu-id="9ac22-117">Create the following template (XPathVariables.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:header>  
         <sql:param name='CustomerID'>1</sql:param>  
         <sql:param name='ContactID'>1</sql:param>   
      </sql:header>  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[@CustomerID=$CustomerID]   
      </sql:xpath-query >  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
       Contact[@ContactID=$ContactID]   
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="9ac22-118">Le chemin d'accès au répertoire spécifié pour le schéma de mappage (SampleSchema1.xml) varie en fonction du répertoire où le modèle est enregistré.</span><span class="sxs-lookup"><span data-stu-id="9ac22-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="9ac22-119">Vous pouvez également spécifier un chemin d'accès absolu, par exemple :</span><span class="sxs-lookup"><span data-stu-id="9ac22-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="9ac22-120">Créez et utilisez le script de test SQLXML 4.0 (Sqlxml4test.vbs) pour exécuter le modèle.</span><span class="sxs-lookup"><span data-stu-id="9ac22-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="9ac22-121">Pour plus d’informations, consultez [utilisation d’ADO pour exécuter des requêtes SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9ac22-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9ac22-122">Dans cet exemple, aucun paramètre n'est passé.</span><span class="sxs-lookup"><span data-stu-id="9ac22-122">In this example, no parameters are passed.</span></span> <span data-ttu-id="9ac22-123">Ce sont donc les valeurs de paramètre par défaut qui sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="9ac22-123">Therefore, the default parameter values are used.</span></span>  
  
  
