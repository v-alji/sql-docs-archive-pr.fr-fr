---
title: Créer des index XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- indexes [XML in SQL Server]
- XML indexes [SQL Server], creating
ms.assetid: 6ecac598-355d-4408-baf7-1b2e8d4cf7c1
author: rothja
ms.author: jroth
ms.openlocfilehash: 9e7800193222b8c9060fee1b247cc5585654cde4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706283"
---
# <a name="create-xml-indexes"></a><span data-ttu-id="19357-102">Créer des index XML</span><span class="sxs-lookup"><span data-stu-id="19357-102">Create XML Indexes</span></span>
  <span data-ttu-id="19357-103">Cette rubrique décrit comment créer des index XML primaires et secondaires.</span><span class="sxs-lookup"><span data-stu-id="19357-103">This topic describes how to create primary and secondary XML indexes.</span></span>  
  
## <a name="creating-a-primary-xml-index"></a><span data-ttu-id="19357-104">Création d'un index XML primaire</span><span class="sxs-lookup"><span data-stu-id="19357-104">Creating a Primary XML Index</span></span>  
 <span data-ttu-id="19357-105">Pour créer un index XML primaire, utilisez l’instruction DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19357-105">To create a primary XML index, use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement.</span></span> <span data-ttu-id="19357-106">Les options disponibles pour les index non XML ne sont pas toutes prises en charge pour les index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-106">Not all options available for non-XML indexes are supported on XML indexes.</span></span>  
  
 <span data-ttu-id="19357-107">Lorsque vous créez un index XML, prenez les points suivants en considération :</span><span class="sxs-lookup"><span data-stu-id="19357-107">Note the following when you are creating an XML index:</span></span>  
  
-   <span data-ttu-id="19357-108">Pour créer un index XML primaire, la table contenant la colonne XML en cours d'indexation, appelée table de base, doit posséder un index cluster portant sur la clé primaire.</span><span class="sxs-lookup"><span data-stu-id="19357-108">To create a primary XML index, the table that contains the XML column being indexed, called the base table, must have a clustered index on the primary key.</span></span> <span data-ttu-id="19357-109">Ceci permet de s'assurer que, si la table de base est partitionnée, l'index XML primaire peut être partitionné grâce au même schéma de partitionnement et à la même fonction de partitionnement.</span><span class="sxs-lookup"><span data-stu-id="19357-109">This makes sure that if the base table is partitioned, the primary XML index can be partitioned by using the same partitioning scheme and partitioning function.</span></span>  
  
-   <span data-ttu-id="19357-110">Si un index XML existe, la clé primaire mise en cluster de la table ne peut alors pas être modifiée.</span><span class="sxs-lookup"><span data-stu-id="19357-110">If an XML index exists, the clustered, primary key of the table cannot be modified.</span></span> <span data-ttu-id="19357-111">Vous devez dans ce cas supprimer tous les index XML de la table avant de pouvoir modifier la clé primaire.</span><span class="sxs-lookup"><span data-stu-id="19357-111">You will have to drop all XML indexes on the table before modifying the primary key.</span></span>  
  
-   <span data-ttu-id="19357-112">Un index XML primaire portant sur une seule colonne de type `xml` peut être créé.</span><span class="sxs-lookup"><span data-stu-id="19357-112">A primary XML index can be created on a single `xml` type column.</span></span> <span data-ttu-id="19357-113">Aucun autre type d'index relatif à la colonne de type XML ne peut être créé en tant que colonne clé.</span><span class="sxs-lookup"><span data-stu-id="19357-113">You cannot create any other type of index with the XML type column as a key column.</span></span> <span data-ttu-id="19357-114">Vous pouvez cependant inclure la colonne de type `xml` dans un index non XML.</span><span class="sxs-lookup"><span data-stu-id="19357-114">However, you can include the `xml` L type column in a non-XML index.</span></span> <span data-ttu-id="19357-115">Chaque colonne de type `xml` d'une table peut présenter son propre index XML primaire.</span><span class="sxs-lookup"><span data-stu-id="19357-115">Each `xml` type column in a table can have its own primary XML index.</span></span> <span data-ttu-id="19357-116">Ceci dit, un seul index XML primaire est autorisé par colonne de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="19357-116">However, only one primary XML index per `xml` type column is permitted.</span></span>  
  
-   <span data-ttu-id="19357-117">Les index XML existent dans le même espace de noms que les index non XML.</span><span class="sxs-lookup"><span data-stu-id="19357-117">XML indexes exist in the same namespace as non-XML indexes.</span></span> <span data-ttu-id="19357-118">Vous ne pouvez par conséquent pas avoir un index XML et un index non XML portant tous deux le même nom pour une même table.</span><span class="sxs-lookup"><span data-stu-id="19357-118">Therefore, you cannot have an XML index and a non-XML index on the same table with the same name.</span></span>  
  
-   <span data-ttu-id="19357-119">Les options IGNORE_DUP_KEY et ONLINE sont toujours définies sur OFF (c'est-à-dire désactivées) pour les index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-119">IGNORE_DUP_KEY and ONLINE options of are always set to OFF for XML indexes.</span></span> <span data-ttu-id="19357-120">Vous pouvez indiquer la valeur OFF pour ces options.</span><span class="sxs-lookup"><span data-stu-id="19357-120">You can specify these options with a value of OFF.</span></span>  
  
-   <span data-ttu-id="19357-121">Les informations de groupes de fichiers ou de partitionnement de la table utilisateur s'appliquent à l'index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-121">The filegroup or partitioning information of the user table is applied to the XML index.</span></span> <span data-ttu-id="19357-122">Les utilisateurs ne peuvent pas indiquer ces informations séparément pour un index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-122">Users cannot specify these separately on an XML index.</span></span>  
  
-   <span data-ttu-id="19357-123">L'option d'index DROP_EXISTING peut supprimer un index XML primaire et en recréer un, ou supprimer un index XML secondaire et en recréer un.</span><span class="sxs-lookup"><span data-stu-id="19357-123">The DROP_EXISTING index option can drop a primary XML index and create a new primary XML index, or drop a secondary XML index and create a new secondary XML index.</span></span> <span data-ttu-id="19357-124">Elle ne peut cependant pas entraîner la suppression d'index XML secondaire pour créer un index XML primaire ou vice versa.</span><span class="sxs-lookup"><span data-stu-id="19357-124">However, this option cannot drop a secondary XML index to create a new primary XML index or vice versa.</span></span>  
  
-   <span data-ttu-id="19357-125">Les noms s'appliquant aux index XML primaires sont soumis aux mêmes restrictions que les noms de vues.</span><span class="sxs-lookup"><span data-stu-id="19357-125">Primary XML index names have the same restrictions as view names.</span></span>  
  
 <span data-ttu-id="19357-126">Vous ne pouvez pas créer d’index XML sur une `xml` colonne de type dans une vue, sur une variable **table** avec des colonnes de type `xml` , ou sur des variables de `xml` type.</span><span class="sxs-lookup"><span data-stu-id="19357-126">You cannot create an XML index on an `xml` type column in a view, on a **table** valued variable with `xml` type columns, or `xml` type variables.</span></span>  
  
-   <span data-ttu-id="19357-127">Pour modifier une colonne de type `xml` non typé en XML typé ou vice versa par le biais de l'option ALTER TABLE ALTER COLUMN, assurez-vous qu'aucun index XML portant sur la colonne n'existe.</span><span class="sxs-lookup"><span data-stu-id="19357-127">To change an `xml` type column from untyped to typed XML, or vice versa, by using the ALTER TABLE ALTER COLUMN option, no XML index on the column should exist.</span></span> <span data-ttu-id="19357-128">Si c'est le cas, il doit être supprimé avant de pouvoir tenter de modifier le type de colonne.</span><span class="sxs-lookup"><span data-stu-id="19357-128">If one does exist, it must be dropped before the column type change is tried.</span></span>  
  
-   <span data-ttu-id="19357-129">L'option ARITHABORT doit être activée (c'est-à-dire définie sur ON) lors de la création d'un index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-129">The option ARITHABORT must be set to ON when an XML index is created.</span></span> <span data-ttu-id="19357-130">Pour pouvoir interroger, insérer, supprimer ou mettre à jour des valeurs de la colonne XML par le biais des méthodes portant sur des données de type XML, cette même option doit être définie sur la connexion aux données.</span><span class="sxs-lookup"><span data-stu-id="19357-130">To query, insert, delete, or update values in the XML column using XML data type methods, the same option must be set on the connection.</span></span> <span data-ttu-id="19357-131">Dans le cas contraire, les méthodes portant sur les données de type XML échouent.</span><span class="sxs-lookup"><span data-stu-id="19357-131">If it is not, the XML data type methods will fail.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19357-132">Des informations à propos d'un index XML donné sont répertoriées dans les affichages catalogue.</span><span class="sxs-lookup"><span data-stu-id="19357-132">Information about an XML index can be found in catalog views.</span></span> <span data-ttu-id="19357-133">La procédure **sp_helpindex** n’est cependant pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="19357-133">However, **sp_helpindex** is not supported.</span></span> <span data-ttu-id="19357-134">Des exemples fournis plus loin dans cette rubrique illustrent comment lancer une requête sur les affichages catalogue afin de retrouver les informations propres aux index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-134">Examples provided later in this topic show how to query the catalog views to find XML index information.</span></span>  
  
 <span data-ttu-id="19357-135">Lors de la création ou de la recréation d’un index XML primaire sur une colonne de type de données XML qui contient des valeurs des types de schémas XML **xs:date** ou **xs:dateTime** (ou tout sous-type de ces types) dont l’année est inférieure à 1, la création de l’index échoue dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] et les versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="19357-135">When creating or recreating a primary XML index on an XML data type column that contains values of the XML Schema types **xs:date** or **xs:dateTime** (or any subtypes of these types) that have a year of less than 1, the index creation will fail in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] and later versions.</span></span> [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="19357-136">Ces valeurs étaient autorisées, ce problème peut donc se produire lors de la création d’index dans une base de données générée dans [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="19357-136">allowed these values, so this problem can occur when creating indexes in a database generated in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="19357-137">Pour plus d’informations, consultez [Comparer du XML typé et du XML non typé](../xml/compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="19357-137">For more information, see [Compare Typed XML to Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md).</span></span>  
  
### <a name="example-creating-a-primary-xml-index"></a><span data-ttu-id="19357-138">Exemple : Création d'un index XML primaire</span><span class="sxs-lookup"><span data-stu-id="19357-138">Example: Creating a Primary XML Index</span></span>  
 <span data-ttu-id="19357-139">La table T (pk INT PRIMARY KEY, xCol XML) avec une colonne XML non typée est utilisée dans la plupart des exemples.</span><span class="sxs-lookup"><span data-stu-id="19357-139">Table T (pk INT PRIMARY KEY, xCol XML) with an untyped XML column is used in most of the examples.</span></span> <span data-ttu-id="19357-140">Cette syntaxe peut très aisément s'adapter à du code XML typé.</span><span class="sxs-lookup"><span data-stu-id="19357-140">These can be extended to typed XML in a straightforward way.</span></span> <span data-ttu-id="19357-141">Par souci de clarté, les requêtes sont décrites pour des instances de données XML, comme le montre l'exemple qui suit :</span><span class="sxs-lookup"><span data-stu-id="19357-141">For simplicity, queries are described for XML data instances as shown in the following:</span></span>  
  
```  
<book genre="security" publicationdate="2002" ISBN="0-7356-1588-2">  
   <title>Writing Secure Code</title>  
   <author>  
      <first-name>Michael</first-name>  
      <last-name>Howard</last-name>  
   </author>  
   <author>  
      <first-name>David</first-name>  
      <last-name>LeBlanc</last-name>  
   </author>  
   <price>39.99</price>  
</book>  
```  
  
 <span data-ttu-id="19357-142">L'instruction suivante crée un index XML, appelé idx_xCol, sur la colonne XML xCol de la table T :</span><span class="sxs-lookup"><span data-stu-id="19357-142">The following statement creates an XML index, called idx_xCol, on the XML column xCol of table T:</span></span>  
  
```  
CREATE PRIMARY XML INDEX idx_xCol on T (xCol)  
```  
  
## <a name="creating-a-secondary-xml-index"></a><span data-ttu-id="19357-143">Création d'un index XML secondaire</span><span class="sxs-lookup"><span data-stu-id="19357-143">Creating a Secondary XML Index</span></span>  
 <span data-ttu-id="19357-144">Utilisez l’instruction DDL [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] pour créer des index XML secondaires et préciser leur type.</span><span class="sxs-lookup"><span data-stu-id="19357-144">Use the [CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql)[!INCLUDE[tsql](../../includes/tsql-md.md)] DDL statement to create secondary XML indexes and specify the type of the secondary XML index that you want.</span></span>  
  
 <span data-ttu-id="19357-145">Lorsque vous créez un index XML secondaire, prenez les points suivants en considération :</span><span class="sxs-lookup"><span data-stu-id="19357-145">Note the following when you are creating secondary XML indexes:</span></span>  
  
-   <span data-ttu-id="19357-146">Toutes les options d'indexation qui s'appliquent à un index non-cluster, hormis les options IGNORE_DUP_KEY et ONLINE, sont autorisées sur les index XML secondaires.</span><span class="sxs-lookup"><span data-stu-id="19357-146">All indexing options that apply to a nonclustered index, except IGNORE_DUP_KEY and ONLINE, are permitted on secondary XML indexes.</span></span> <span data-ttu-id="19357-147">Ces deux options doivent toujours être définies sur OFF dans le cas d'index XML secondaires.</span><span class="sxs-lookup"><span data-stu-id="19357-147">The two options must always be set to OFF for secondary XML indexes.</span></span>  
  
-   <span data-ttu-id="19357-148">Les index secondaires sont partitionnés de la même manière que l'index XML primaire.</span><span class="sxs-lookup"><span data-stu-id="19357-148">The secondary indexes are partitioned just like the primary XML index.</span></span>  
  
-   <span data-ttu-id="19357-149">DROP_EXISTING permet de supprimer un index secondaire sur la table utilisateur pour en recréer un.</span><span class="sxs-lookup"><span data-stu-id="19357-149">DROP_EXISTING can drop a secondary index on the user table and create another secondary index on the user table.</span></span>  
  
 <span data-ttu-id="19357-150">Vous pouvez passer par une requête sur l’affichage catalogue **sys.xml_indexes** afin d’extraire les informations relatives aux index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-150">You can query the **sys.xml_indexes** catalog view to retrieve XML index information.</span></span> <span data-ttu-id="19357-151">Il reste à noter que la colonne **secondary_type_desc** se trouvant dans l’affichage catalogue **sys.xml_indexes** fournit le type d’index secondaire :</span><span class="sxs-lookup"><span data-stu-id="19357-151">Note that the **secondary_type_desc** column in the **sys.xml_indexes** catalog view provides the type of secondary index:</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="19357-152">Les valeurs retournées dans la colonne **secondary_type_desc** peuvent être NULL, PATH, VALUE ou PROPERTY.</span><span class="sxs-lookup"><span data-stu-id="19357-152">The values returned in the **secondary_type_desc** column can be NULL, PATH, VALUE, or PROPERTY.</span></span> <span data-ttu-id="19357-153">Pour l'index XML primaire, la valeur renvoyée correspond à NULL.</span><span class="sxs-lookup"><span data-stu-id="19357-153">For the primary XML index, the value returned is NULL.</span></span>  
  
### <a name="example-creating-secondary-xml-indexes"></a><span data-ttu-id="19357-154">Exemple : Création d’index XML secondaires</span><span class="sxs-lookup"><span data-stu-id="19357-154">Example: Creating Secondary XML Indexes</span></span>  
 <span data-ttu-id="19357-155">L'exemple suivant illustre le mode de création d'index XML secondaires.</span><span class="sxs-lookup"><span data-stu-id="19357-155">The following example illustrates how secondary XML indexes are created.</span></span> <span data-ttu-id="19357-156">Il montre également les informations relatives aux index XML que vous avez créés.</span><span class="sxs-lookup"><span data-stu-id="19357-156">The example also shows information about the XML indexes that you created.</span></span>  
  
```  
CREATE TABLE T (Col1 INT PRIMARY KEY, XmlCol XML);  
GO  
-- Create primary index.  
CREATE PRIMARY XML INDEX PIdx_T_XmlCol   
ON T(XmlCol);  
GO  
-- Create secondary indexes (PATH, VALUE, PROPERTY).  
CREATE XML INDEX PIdx_T_XmlCol_PATH ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PATH;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_VALUE ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR VALUE;  
GO  
CREATE XML INDEX PIdx_T_XmlCol_PROPERTY ON T(XmlCol)  
USING XML INDEX PIdx_T_XmlCol  
FOR PROPERTY;  
GO  
```  
  
 <span data-ttu-id="19357-157">Vous pouvez interroger le `sys.xml_indexes` afin d'extraire des informations relatives aux index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-157">You can query the `sys.xml_indexes` to retrieve XML indexes information.</span></span> <span data-ttu-id="19357-158">La colonne `secondary_type_desc` fournit le type d'index secondaire.</span><span class="sxs-lookup"><span data-stu-id="19357-158">The `secondary_type_desc` column provides the secondary index type.</span></span>  
  
```  
SELECT  *   
FROM    sys.xml_indexes;  
```  
  
 <span data-ttu-id="19357-159">Vous pouvez également interroger l'affichage catalogue pour obtenir les informations sur l'index.</span><span class="sxs-lookup"><span data-stu-id="19357-159">You can also query the catalog view for index information.</span></span>  
  
```  
SELECT *  
FROM sys.xml_indexes  
WHERE object_id = object_id('T');  
```  
  
 <span data-ttu-id="19357-160">Vous pouvez ajouter des exemples de données puis passer en revue les informations de l'index XML.</span><span class="sxs-lookup"><span data-stu-id="19357-160">You can add sample data and then review the XML index information.</span></span>  
  
```  
INSERT INTO T VALUES (1,  
'<doc id="123">  
<sections>  
<section num="2">  
<heading>Background</heading>  
</section>  
<section num="3">  
<heading>Sort</heading>  
</section>  
<section num="4">  
<heading>Search</heading>  
</section>  
</sections>  
</doc>');  
GO  
-- Check XML index information.  
SELECT *  
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, NULL, 'DETAILED');  
GO  
-- Space usage of primary XML index  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id  
FROM    sys.xml_indexes i   
WHERE   i.name = 'PIdx_T_XmlCol' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
--- Space usage of secondary XML index (for example PATH secondary index)  PIdx_T_XmlCol_PATH  
DECLARE @index_id int;  
SELECT  @index_id = i.index_id   
FROM    sys.xml_indexes i   
WHERE  i.name = 'PIdx_T_XmlCol_PATH' and object_name(i.object_id) = 'T';  
  
SELECT *  
FROM sys.dm_db_index_physical_stats (db_id(), object_id('T') , @index_id, DEFAULT, 'DETAILED');  
go  
  
-- Space usage of all secondary XML indexes for a particular table  
SELECT i.name, object_name(i.object_id), stats.*   
FROM   sys.dm_db_index_physical_stats (db_id(), object_id('T'), NULL, DEFAULT, 'DETAILED') stats  
JOIN sys.xml_indexes i ON (stats.object_id = i.object_id and stats.index_id = i.index_id)  
WHERE secondary_type is not null;  
-- Drop secondary indexes.  
DROP INDEX PIdx_T_XmlCol_PATH ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_VALUE ON T;  
GO  
DROP INDEX PIdx_T_XmlCol_PROPERTY ON T;  
GO  
-- Drop primary index.  
DROP INDEX PIdx_T_XmlCol ON T;  
-- Drop table T.  
DROP TABLE T;  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="19357-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19357-161">See Also</span></span>  
 <span data-ttu-id="19357-162">[Index XML &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="19357-162">[XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md) </span></span>  
 [<span data-ttu-id="19357-163">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="19357-163">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
