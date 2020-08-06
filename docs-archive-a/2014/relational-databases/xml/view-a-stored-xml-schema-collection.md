---
title: Afficher une collection de schémas XML stockée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- schema collections [SQL Server], viewing
- XML schemas [SQL Server], viewing
- CREATE XML SCHEMA COLLECTION statement
- xml_schema_namespace function
- XML schema collections [SQL Server], viewing
- displaying XML schema collections
- viewing XML schema collections
ms.assetid: e38031af-22df-4cd9-a14e-e316b822f91b
author: rothja
ms.author: jroth
ms.openlocfilehash: 6383fb17183a991d2f83325044663cc9671e9442
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601998"
---
# <a name="view-a-stored-xml-schema-collection"></a><span data-ttu-id="57df2-102">Afficher une collection de schémas XML stockée</span><span class="sxs-lookup"><span data-stu-id="57df2-102">View a Stored XML Schema Collection</span></span>
  <span data-ttu-id="57df2-103">Après l’importation d’une collection de schémas XML à l’aide de l’instruction [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), les composants du schéma sont stockés dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="57df2-103">After you import an XML schema collection by using [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), the schema components are stored in the metadata.</span></span> <span data-ttu-id="57df2-104">Vous pouvez utiliser la fonction intrinsèque [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)pour reconstruire la collection de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="57df2-104">You can use the [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)intrinsic function to reconstruct the XML schema collection.</span></span> <span data-ttu-id="57df2-105">Cette fonction renvoie une instance de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="57df2-105">This function returns an `xml` data type instance.</span></span>  
  
 <span data-ttu-id="57df2-106">Par exemple, la requête suivante reprend une collection de schémas XML (à savoir`ProductDescriptionSchemaCollection`) à partir du schéma relationnel de production se trouvant dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57df2-106">For example, the following query retrieves an XML schema collection (`ProductDescriptionSchemaCollection`) from the production relational schema in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection')  
GO  
```  
  
 <span data-ttu-id="57df2-107">Si vous ne voulez consulter qu'un seul schéma de la collection de schémas XML, vous pouvez spécifier une requête XQuery portant sur le résultat de type `xml` renvoyé par la fonction `xml_schema_namespace`.</span><span class="sxs-lookup"><span data-stu-id="57df2-107">If you want to see only one schema from the XML schema collection, you can specify XQuery against the `xml` type result that is returned by `xml_schema_namespace`.</span></span>  
  
```  
SELECT xml_schema_namespace(N'RelationalSchemaName',N'XmlSchemaCollectionName').query('  
/xs:schema[@targetNamespace="TargetNameSpace"]  
')  
GO  
```  
  
 <span data-ttu-id="57df2-108">Par exemple, la requête suivante extrait les informations du schéma XML traitant des garanties et de l'entretien des produits à partir de la collection de schémas XML nommée `ProductDescriptionSchemaCollection` .</span><span class="sxs-lookup"><span data-stu-id="57df2-108">For example, the following query retrieves product warranty and maintenance XML schema information from the `ProductDescriptionSchemaCollection` XML schema collection.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection').query('  
/xs:schema[@targetNamespace="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"]  
')  
GO  
```  
  
 <span data-ttu-id="57df2-109">Vous pouvez également transmettre l'espace de noms cible facultatif en tant que troisième paramètre à la fonction `xml_schema_namespace` pour extraire un schéma spécifique de la collection, comme illustré dans la requête suivante :</span><span class="sxs-lookup"><span data-stu-id="57df2-109">You can also pass the optional target namespace as the third parameter to the `xml_schema_namespace` function to retrieve specific schema from the collection, as shown in the following query:</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection', N'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain')  
GO  
```  
  
 <span data-ttu-id="57df2-110">Lors de la création d'une collection de schémas XML par le biais de l'instruction CREATE XML SCHEMA COLLECTION dans la base de données, l'instruction stocke les composants du schéma dans les métadonnées.</span><span class="sxs-lookup"><span data-stu-id="57df2-110">When you create an XML schema collection by using CREATE XML SCHEMA COLLECTION in the database, the statement stores the schema components in the metadata.</span></span> <span data-ttu-id="57df2-111">Notez que seuls les composants de schéma que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comprend sont stockés.</span><span class="sxs-lookup"><span data-stu-id="57df2-111">Note that only the schema components that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] understands are stored.</span></span> <span data-ttu-id="57df2-112">Les commentaires, les annotations et les attributs non XSD ne sont pas stockés.</span><span class="sxs-lookup"><span data-stu-id="57df2-112">Any comments, annotations, or non-XSD attributes are not stored.</span></span> <span data-ttu-id="57df2-113">Le schéma ainsi reconstruit par **xml_schema_namespace** est donc équivalent au schéma d’origine d’un point de vue fonctionnel, mais ne lui ressemble pas nécessairement.</span><span class="sxs-lookup"><span data-stu-id="57df2-113">Therefore, the schema reconstructed by **xml_schema_namespace** is functionally equivalent to the original schema, but it will not necessarily look the same.</span></span> <span data-ttu-id="57df2-114">Par exemple, vous n'y verrez pas les mêmes préfixes que dans le schéma d'origine.</span><span class="sxs-lookup"><span data-stu-id="57df2-114">For example, you will not see the same prefixes you had in the original schema.</span></span> <span data-ttu-id="57df2-115">Le schéma renvoyé par la fonction **xml_schema_namespace** utilise **t** comme préfixe pour l’espace de noms cible et **ns1**, **ns2**, etc., pour les autres espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="57df2-115">The schema returned by **xml_schema_namespace** uses **t** as the prefix for the target namespace and **ns1**, **ns2**, and so on, for other namespaces.</span></span>  
  
 <span data-ttu-id="57df2-116">Pour conserver une copie identique des schémas XML, vous devez sauvegarder ces derniers dans des fichiers ou dans des colonnes de type `xml` d'une table tirée d'une base de données.</span><span class="sxs-lookup"><span data-stu-id="57df2-116">If you want to retain an identical copy of the XML schemas, you should save your XML schema in a file or in a database table in an `xml` type column.</span></span>  
  
 <span data-ttu-id="57df2-117">La vue de catalogue [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) retourne également des informations concernant les collections de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="57df2-117">The [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) catalog view also returns information about XML schema collections.</span></span> <span data-ttu-id="57df2-118">Ces informations comprennent le nom de la collection, la date de création et le propriétaire de la	collection.</span><span class="sxs-lookup"><span data-stu-id="57df2-118">This information includes the name of the collection, the creation date, and the owner of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57df2-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57df2-119">See Also</span></span>  
 [<span data-ttu-id="57df2-120">Collections de schémas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="57df2-120">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
