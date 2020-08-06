---
title: Générer du code XML à partir d’ensembles de lignes avec FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, generating XML from rowsets
ms.assetid: d061c0f1-3de9-4ad1-bbca-ce45d064b6c8
author: rothja
ms.author: jroth
ms.openlocfilehash: dcf9feb4dab9ad1149ab433c9d9b4999c96c1cdd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710419"
---
# <a name="generate-xml-from-rowsets-with-for-xml"></a><span data-ttu-id="77efb-102">Générer du code XML à partir d'ensembles de lignes avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="77efb-102">Generate XML from Rowsets with FOR XML</span></span>
  <span data-ttu-id="77efb-103">Vous pouvez générer une `xml` instance de type de données à partir d’un ensemble de lignes en utilisant for XML avec la nouvelle directive de **type** .</span><span class="sxs-lookup"><span data-stu-id="77efb-103">You can generate an `xml` data type instance from a rowset by using FOR XML with the new **TYPE** directive.</span></span>  
  
 <span data-ttu-id="77efb-104">Le résultat peut être assigné à une `xml` colonne, une variable ou un paramètre de type de données.</span><span class="sxs-lookup"><span data-stu-id="77efb-104">The result can be assigned to an `xml` data type column, variable, or parameter.</span></span> <span data-ttu-id="77efb-105">De plus, il est possible d'imbriquer des clauses FOR XML pour générer une structure hiérarchique.</span><span class="sxs-lookup"><span data-stu-id="77efb-105">Also, FOR XML can be nested to generate any hierarchical structure.</span></span> <span data-ttu-id="77efb-106">Les clauses FOR XML imbriquées sont plus faciles à écrire que la clause FOR XML EXPLICIT, mais elles ne s'avèrent pas aussi performantes pour les hiérarchies profondes.</span><span class="sxs-lookup"><span data-stu-id="77efb-106">This makes nested FOR XML much more convenient to write than FOR XML EXPLICIT, but it may not perform as well for deep hierarchies.</span></span> <span data-ttu-id="77efb-107">FOR XML introduit aussi un nouveau mode PATH</span><span class="sxs-lookup"><span data-stu-id="77efb-107">FOR XML also introduces a new PATH mode.</span></span> <span data-ttu-id="77efb-108">qui spécifie le chemin de l'arborescence XML où apparaît la valeur d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="77efb-108">This new mode specifies the path in the XML tree where a column's value appears.</span></span>  
  
 <span data-ttu-id="77efb-109">La nouvelle directive **FOR XML TYPE** permet de créer, avec une syntaxe SQL, des vues XML en lecture seule des données relationnelles.</span><span class="sxs-lookup"><span data-stu-id="77efb-109">The new **FOR XML TYPE** directive can be used to define read-only XML views over relational data with SQL syntax.</span></span> <span data-ttu-id="77efb-110">La vue peut être interrogée par des instructions SQL et le langage XQuery intégré, comme le montre l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="77efb-110">The view can be queried with SQL statements and embedded XQuery, as shown in the following example.</span></span> <span data-ttu-id="77efb-111">Vous pouvez également faire référence à ces vues SQL dans les procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="77efb-111">You can also refer to these SQL views in stored procedures.</span></span>  
  
## <a name="example-sql-view-returning-generated-xml-data-type"></a><span data-ttu-id="77efb-112">Exemple : Vue SQL retournant un type de données XML généré</span><span class="sxs-lookup"><span data-stu-id="77efb-112">Example: SQL View Returning Generated xml Data Type</span></span>  
 <span data-ttu-id="77efb-113">La définition de la vue SQL suivante crée une vue XML d'une colonne relationnelle, pk, et extrait les auteurs des livres d'une colonne XML :</span><span class="sxs-lookup"><span data-stu-id="77efb-113">The following SQL view definition creates an XML view over a relational column, pk, and book authors retrieved from an XML column:</span></span>  
  
```  
CREATE VIEW V (xmlVal) AS  
SELECT pk, xCol.query('/book/author')  
FROM   T  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="77efb-114">La vue V contient une seule ligne avec une seule colonne columnxmlVal de type XML `.` . elle peut être interrogée comme une `xml` instance de type de données normale.</span><span class="sxs-lookup"><span data-stu-id="77efb-114">The V view contains a single row with a single columnxmlVal of XML type`.` It can be queried like a regular `xml` data type instance.</span></span> <span data-ttu-id="77efb-115">Par exemple, la requête suivante renvoie l'auteur dont le prénom est « David » :</span><span class="sxs-lookup"><span data-stu-id="77efb-115">For example, the following query returns the author whose first name is "David":</span></span>  
  
```  
SELECT xmlVal.query('//author[first-name = "David"]')  
FROM   V  
```  
  
 <span data-ttu-id="77efb-116">Les définitions de vue SQL s'apparentent un peu aux vues XML créées à l'aide des schémas annotés,</span><span class="sxs-lookup"><span data-stu-id="77efb-116">SQL view definitions are somewhat similar to XML views that are created by using annotated schemas.</span></span> <span data-ttu-id="77efb-117">bien qu'il y ait des différences de taille.</span><span class="sxs-lookup"><span data-stu-id="77efb-117">However, there are important differences.</span></span> <span data-ttu-id="77efb-118">La définition d'une vue SQL est en lecture seule et doit être manipulée avec le langage XQuery intégré.</span><span class="sxs-lookup"><span data-stu-id="77efb-118">The SQL view definition is read-only and must be manipulated with embedded XQuery.</span></span> <span data-ttu-id="77efb-119">Les vues XML sont créées à l'aide d'un schéma annoté.</span><span class="sxs-lookup"><span data-stu-id="77efb-119">The XML views are created by using annotated schema.</span></span> <span data-ttu-id="77efb-120">De plus, la vue SQL matérialise le résultat XML avant l'application de l'expression XQuery tandis que les requêtes XPath sur les vues XML évaluent les requêtes SQL portant sur les tables sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="77efb-120">Additionally, the SQL view materializes the XML result before applying the XQuery expression, while the XPath queries on XML views evaluate SQL queries on the underlying tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77efb-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77efb-121">See Also</span></span>  
 [<span data-ttu-id="77efb-122">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="77efb-122">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
