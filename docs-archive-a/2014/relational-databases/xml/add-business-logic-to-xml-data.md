---
title: Ajouter la logique métier aux données XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
author: rothja
ms.author: jroth
ms.openlocfilehash: 5bf8e9edc36e9c420faa92f2db1a92c311194e99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603325"
---
# <a name="add-business-logic-to-xml-data"></a><span data-ttu-id="6fcda-102">Ajouter la logique métier aux données XML</span><span class="sxs-lookup"><span data-stu-id="6fcda-102">Add Business Logic to XML Data</span></span>
  <span data-ttu-id="6fcda-103">Votre logique métier peut être ajoutée aux données XML de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="6fcda-103">Your business logic can be added to XML data in several ways:</span></span>  
  
-   <span data-ttu-id="6fcda-104">Vous pouvez écrire des contraintes sur les lignes ou les colonnes de façon à imposer des contraintes propres à un domaine lors de l'insertion et de la modification des données XML.</span><span class="sxs-lookup"><span data-stu-id="6fcda-104">You can write row or column constraints to enforce domain-specific constraints during insertion and modification of XML data.</span></span>  
  
-   <span data-ttu-id="6fcda-105">Vous pouvez écrire un déclencheur sur la colonne XML qui est activé lors de l'insertion ou de la mise à jour de valeurs dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="6fcda-105">You can write a trigger on the XML column that fires when you insert or update values in the column.</span></span> <span data-ttu-id="6fcda-106">Le déclencheur peut contenir des règles de validation propres au domaine ou remplir les tables de propriétés.</span><span class="sxs-lookup"><span data-stu-id="6fcda-106">The trigger can contain domain-specific validation rules or populate property tables.</span></span>  
  
-   <span data-ttu-id="6fcda-107">Le moteur de base de données permet l'exécution de code managé.</span><span class="sxs-lookup"><span data-stu-id="6fcda-107">The Database Engine includes the ability execute managed code.</span></span> <span data-ttu-id="6fcda-108">Vous pouvez utiliser cette intégration au CLR (Common Language Runtime) pour écrire des fonctions dans le code managé auxquelles vous transmettez des valeurs XML et utiliser les capacités de traitement fournies par l’espace de noms System.Xml.</span><span class="sxs-lookup"><span data-stu-id="6fcda-108">You can use this common language runtime (CLR) integration to write functions in managed code to which you pass XML values, and use XML processing capabilities provided by the System.Xml namespace.</span></span> <span data-ttu-id="6fcda-109">Vous pouvez, par exemple, appliquer une transformation XSL aux données XML.</span><span class="sxs-lookup"><span data-stu-id="6fcda-109">An example is to apply XSL transformation to XML data.</span></span> <span data-ttu-id="6fcda-110">Vous pouvez également désérialiser le code XML en une ou plusieurs classes managées et travailler sur ces classes à l'aide de code managé.</span><span class="sxs-lookup"><span data-stu-id="6fcda-110">Alternatively, you can deserialize the XML into one or more managed classes and operate on them by using managed code.</span></span>  
  
-   <span data-ttu-id="6fcda-111">Vous pouvez écrire des procédures stockées et des fonctions Transact-SQL pour lancer le traitement sur la colonne XML en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6fcda-111">You can write Transact-SQL stored procedures and functions that start the processing on the XML column for your business needs.</span></span>  
  
## <a name="example-applying-xsl-transformation"></a><span data-ttu-id="6fcda-112">Exemple : Application d’une transformation XSL</span><span class="sxs-lookup"><span data-stu-id="6fcda-112">Example: Applying XSL Transformation</span></span>  
 <span data-ttu-id="6fcda-113">Prenons l’exemple d’une fonction CLR **TransformXML ()** qui accepte une `xml` instance de type de données et d’une transformation XSL stockée dans un fichier, applique la transformation aux données XML, puis retourne les données XML transformées dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="6fcda-113">Consider a CLR function **TransformXml()** that accepts an `xml` data type instance and an XSL transformation stored in a file, applies the transformation to the XML data, and then returns the transformed XML in the result.</span></span> <span data-ttu-id="6fcda-114">Le code suivant est un squelette de fonction écrit en C# :</span><span class="sxs-lookup"><span data-stu-id="6fcda-114">Following is a skeleton function that is written in C#:</span></span>  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 <span data-ttu-id="6fcda-115">Après l’enregistrement de l’assembly et la création d’une fonction [!INCLUDE[tsql](../../includes/tsql-md.md)] définie par l’utilisateur, **SqlXslTransform()** correspondant à **TransformXml()** , la fonction peut être appelée à partir de Transact-SQL, comme le montre la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="6fcda-115">After the assembly is registered and a user-defined [!INCLUDE[tsql](../../includes/tsql-md.md)] function is created, **SqlXslTransform()** corresponding to **TransformXml()**, the function can be invoked from Transact-SQL as shown in the following query:</span></span>  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 <span data-ttu-id="6fcda-116">Le résultat de la requête contient un ensemble de lignes pour le code XML transformé.</span><span class="sxs-lookup"><span data-stu-id="6fcda-116">The query result contains a rowset of the transformed XML.</span></span>  
  
 <span data-ttu-id="6fcda-117">L’intégration CLR dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] étend les possibilités de décomposition des données XML en tables ou en promotion de propriétés, et d’interrogation des données XML en utilisant les classes managées de l’espace de noms System.Xml.</span><span class="sxs-lookup"><span data-stu-id="6fcda-117">The CLR integration into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expands the possibilities for decomposing XML data into tables or property promotion, and querying XML data by using managed classes in the System.Xml namespace.</span></span> <span data-ttu-id="6fcda-118">Pour plus d’informations, consultez [Données XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="6fcda-118">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
  
