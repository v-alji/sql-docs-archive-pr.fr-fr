---
title: Utiliser les méthodes value() et nodes() avec OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- OpenXML method [XML in SQL Server]
- value method [XML in SQL Server]
- nodes method [XML in SQL Server]
ms.assetid: c73dbe55-d685-42eb-b0ee-9f3c5b9d97f3
author: rothja
ms.author: jroth
ms.openlocfilehash: 5dccf5a7ef626d1f1a42d011d22ba77807b34eba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706263"
---
# <a name="use-the-value-and-nodes-methods-with-openxml"></a><span data-ttu-id="e6303-102">Utiliser les méthodes value() et nodes() avec OPENXML</span><span class="sxs-lookup"><span data-stu-id="e6303-102">Use the value() and nodes() Methods with OPENXML</span></span>
  <span data-ttu-id="e6303-103">Vous pouvez utiliser plusieurs méthodes **value ()** sur le `xml` type de données dans une clause **Select** pour générer un ensemble de lignes de valeurs extraites.</span><span class="sxs-lookup"><span data-stu-id="e6303-103">You can use multiple **value()** methods on `xml` data type in a **SELECT** clause to generate a rowset of extracted values.</span></span> <span data-ttu-id="e6303-104">La méthode **nodes()** produit une référence interne pour chaque nœud sélectionné en vue d’une requête supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e6303-104">The **nodes()** method yields an internal reference for each selected node that can be used for additional query.</span></span> <span data-ttu-id="e6303-105">La combinaison des méthodes **nodes()** et **value()** peut s’avérer plus efficace pour générer l’ensemble de lignes quand il contient plusieurs colonnes et, peut-être, quand les expressions de chemin utilisées durant sa génération sont complexes.</span><span class="sxs-lookup"><span data-stu-id="e6303-105">The combination of the **nodes()** and **value()** methods can be more efficient in generating the rowset when it has several columns and, perhaps, when the path expressions used in its generation are complex.</span></span>  
  
 <span data-ttu-id="e6303-106">La méthode **Nodes ()** génère des instances d’un `xml` type de données spécial, chacune ayant son contexte défini sur un nœud sélectionné différent.</span><span class="sxs-lookup"><span data-stu-id="e6303-106">The **nodes()** method yields instances of a special `xml` data type, each of which has its context set to a different selected node.</span></span> <span data-ttu-id="e6303-107">Ce genre d’instance XML prend en charge les méthodes **query()** , **value()** , **nodes()** et **exist()** , et peut être utilisé dans les agrégations **count(\*)** .</span><span class="sxs-lookup"><span data-stu-id="e6303-107">This kind of XML instance supports **query()**, **value()**, **nodes()**, and **exist()** methods and can be used in **count(\*)** aggregations.</span></span> <span data-ttu-id="e6303-108">Tous les autres emplois génèrent une erreur.</span><span class="sxs-lookup"><span data-stu-id="e6303-108">All other uses cause an error.</span></span>  
  
## <a name="example-using-nodes"></a><span data-ttu-id="e6303-109">Exemple : Utilisation de nodes()</span><span class="sxs-lookup"><span data-stu-id="e6303-109">Example: Using nodes()</span></span>  
 <span data-ttu-id="e6303-110">Supposez que vous voulez extraire les prénoms et les noms des auteurs et que le premier prénom ne soit pas « David ».</span><span class="sxs-lookup"><span data-stu-id="e6303-110">Assume that you want to extract the first and last names of authors, and the first name is not "David".</span></span> <span data-ttu-id="e6303-111">En outre, vous voulez extraire ces informations sous forme d'un ensemble de lignes composé de deux colonnes, FirstName et LastName.</span><span class="sxs-lookup"><span data-stu-id="e6303-111">Additionally, you want to extract this information as a rowset that contains two columns, FirstName and LastName.</span></span> <span data-ttu-id="e6303-112">En utilisant les méthodes **nodes()** et **value()** , vous pouvez y parvenir en procédant ainsi :</span><span class="sxs-lookup"><span data-stu-id="e6303-112">By using **nodes()** and **value()** methods, you can accomplish this as shown in the following:</span></span>  
  
```  
SELECT nref.value('(first-name/text())[1]', 'nvarchar(50)') FirstName,  
       nref.value('(last-name/text())[1]', 'nvarchar(50)') LastName  
FROM   T CROSS APPLY xCol.nodes('//author') AS R(nref)  
WHERE  nref.exist('first-name[. != "David"]') = 1  
```  
  
 <span data-ttu-id="e6303-113">Dans cet exemple, `nodes('//author')` génère un ensemble de lignes de références aux éléments `<author>` pour chaque instance XML.</span><span class="sxs-lookup"><span data-stu-id="e6303-113">In this example, `nodes('//author')` yields a rowset of references to `<author>` elements for each XML instance.</span></span> <span data-ttu-id="e6303-114">Les prénoms et noms des auteurs sont obtenus en évaluant les méthodes **value()** relatives à ces références.</span><span class="sxs-lookup"><span data-stu-id="e6303-114">The first and last names of authors are obtained by evaluating **value()** methods relative to those references.</span></span>  
  
 <span data-ttu-id="e6303-115">Avec SQL Server 2000, vous avez la possibilité de générer un ensemble de lignes à partir d’une instance XML en utilisant **OpenXml()** .</span><span class="sxs-lookup"><span data-stu-id="e6303-115">SQL Server 2000 provides the capability for generating a rowset from an XML instance by using **OpenXml()**.</span></span> <span data-ttu-id="e6303-116">Vous pouvez spécifier le schéma relationnel pour l'ensemble de lignes et la façon de mapper les valeurs de l'instance XML avec les colonnes de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="e6303-116">You can specify the relational schema for the rowset and how values inside the XML instance map to columns in the rowset.</span></span>  
  
## <a name="example-using-openxml-on-the-xml-data-type"></a><span data-ttu-id="e6303-117">Exemple : Utilisation de OpenXml() sur le type de données xml</span><span class="sxs-lookup"><span data-stu-id="e6303-117">Example: Using OpenXml() on the xml Data Type</span></span>  
 <span data-ttu-id="e6303-118">La requête peut être réécrite d’après l’exemple précédent en utilisant **OpenXml()** , comme le montre l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="e6303-118">The query can be rewritten from the previous example by using **OpenXml()** as shown in the following.</span></span> <span data-ttu-id="e6303-119">Vous devez pour cela créer un curseur qui lit chaque instance XML dans une variable XML, et y applique ensuite OpenXML :</span><span class="sxs-lookup"><span data-stu-id="e6303-119">This is done by creating a cursor that reads each XML instance into an XML variable and then applies OpenXML to it:</span></span>  
  
```  
DECLARE name_cursor CURSOR  
FOR  
   SELECT xCol   
   FROM   T  
OPEN name_cursor  
DECLARE @xmlVal XML  
DECLARE @idoc int  
FETCH NEXT FROM name_cursor INTO @xmlVal  
  
WHILE (@@FETCH_STATUS = 0)  
BEGIN  
   EXEC sp_xml_preparedocument @idoc OUTPUT, @xmlVal  
   SELECT   *  
   FROM   OPENXML (@idoc, '//author')  
          WITH (FirstName  varchar(50) 'first-name',  
                LastName   varchar(50) 'last-name') R  
   WHERE  R.FirstName != 'David'  
  
   EXEC sp_xml_removedocument @idoc  
   FETCH NEXT FROM name_cursor INTO @xmlVal  
END  
CLOSE name_cursor  
DEALLOCATE name_cursor   
```  
  
 <span data-ttu-id="e6303-120">La fonction**OpenXml()** crée une représentation en mémoire et utilise les tables de travail plutôt que le processeur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="e6303-120">**OpenXml()** creates an in-memory representation and uses work tables instead of the query processor.</span></span> <span data-ttu-id="e6303-121">Elle s'appuie ensuite sur le processeur XPath version 1.0 de MSXML version 3.0 au lieu du moteur XQuery.</span><span class="sxs-lookup"><span data-stu-id="e6303-121">It relies on the XPath version 1.0 processor of MSXML version 3.0 instead of the XQuery engine.</span></span> <span data-ttu-id="e6303-122">Les tables de travail ne sont plus partagées entre plusieurs appels à **OpenXml()** , même s’il s’agit de la même instance XML.</span><span class="sxs-lookup"><span data-stu-id="e6303-122">The work tables are not shared among multiple calls to **OpenXml()**, even on the same XML instance.</span></span> <span data-ttu-id="e6303-123">L'évolutivité est ainsi limitée.</span><span class="sxs-lookup"><span data-stu-id="e6303-123">This limits its scalability.</span></span> <span data-ttu-id="e6303-124">La fonction**OpenXml()** vous permet d’accéder à un format de table edge pour les données XML quand la clause WITH n’est pas spécifiée.</span><span class="sxs-lookup"><span data-stu-id="e6303-124">**OpenXml()** allows you to access an edge table format for the XML data when the WITH clause is not specified.</span></span> <span data-ttu-id="e6303-125">De plus, vous pouvez utiliser la valeur XML restante dans une colonne distincte réservée aux données en excès.</span><span class="sxs-lookup"><span data-stu-id="e6303-125">Also, it allows you to use the remaining XML value in a separate, "overflow" column.</span></span>  
  
 <span data-ttu-id="e6303-126">La combinaison des fonctions **nodes()** et **value()** tire pleinement parti des index XML.</span><span class="sxs-lookup"><span data-stu-id="e6303-126">The combination of **nodes()** and **value()** functions uses XML indexes effectively.</span></span> <span data-ttu-id="e6303-127">Cette combinaison montre donc une plus grande capacité d'évolution que **OpenXml**.</span><span class="sxs-lookup"><span data-stu-id="e6303-127">As a result, this combination can exhibit more scalability than **OpenXml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6303-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6303-128">See Also</span></span>  
 [<span data-ttu-id="e6303-129">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e6303-129">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
