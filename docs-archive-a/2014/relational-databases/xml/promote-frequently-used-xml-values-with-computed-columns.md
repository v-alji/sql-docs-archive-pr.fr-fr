---
title: Promouvoir les valeurs XML les plus fréquentes à l’aide de colonnes calculées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- promoting properties [XML in SQL Server]
- property promotion [XML in SQL Server]
ms.assetid: f5111896-c2fd-4209-b500-f2baa45489ad
author: rothja
ms.author: jroth
ms.openlocfilehash: bfb83b7772ffd92eab7087db11e4c3ffd96afa47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702503"
---
# <a name="promote-frequently-used-xml-values-with-computed-columns"></a><span data-ttu-id="a5196-102">Promouvoir les valeurs XML les plus fréquentes à l'aide de colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="a5196-102">Promote Frequently Used XML Values with Computed Columns</span></span>
  <span data-ttu-id="a5196-103">Si les requêtes portent essentiellement sur un petit nombre de valeurs d'élément et d'attribut, vous pouvez promouvoir ces quantités dans les colonnes relationnelles.</span><span class="sxs-lookup"><span data-stu-id="a5196-103">If queries are made principally on a small number of element and attribute values, you may want to promote those quantities into relational columns.</span></span> <span data-ttu-id="a5196-104">Cela peut s'avérer utile lorsque les requêtes sont émises sur une petite partie des données XML et que l'ensemble de l'instance XML est récupéré.</span><span class="sxs-lookup"><span data-stu-id="a5196-104">This is helpful when queries are issued on a small part of the XML data while the whole XML instance is retrieved.</span></span> <span data-ttu-id="a5196-105">Il n'est pas nécessaire de créer un index XML sur la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-105">Creating an XML index on the XML column is not required.</span></span> <span data-ttu-id="a5196-106">En revanche, la colonne promue peut être indexée.</span><span class="sxs-lookup"><span data-stu-id="a5196-106">Instead, the promoted column can be indexed.</span></span> <span data-ttu-id="a5196-107">Les requêtes doivent être écrites en vue de l'utilisation de la colonne promue</span><span class="sxs-lookup"><span data-stu-id="a5196-107">Queries must be written to use the promoted column.</span></span> <span data-ttu-id="a5196-108">afin que l'optimiseur de requête ne redirige plus les requêtes de la colonne XML vers la colonne promue.</span><span class="sxs-lookup"><span data-stu-id="a5196-108">That is, the query optimizer does not target again the queries on the XML column to the promoted column.</span></span>  
  
 <span data-ttu-id="a5196-109">La colonne promue peut être une colonne calculée de la même table ou une colonne distincte, gérée par l'utilisateur, d'une autre table.</span><span class="sxs-lookup"><span data-stu-id="a5196-109">The promoted column can be a computed column in the same table or it can be a separate, user-maintained column in a table.</span></span> <span data-ttu-id="a5196-110">Cela suffit lorsque des valeurs singleton sont promues à partir de chaque instance XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-110">This is sufficient when singleton values are promoted from each XML instance.</span></span> <span data-ttu-id="a5196-111">Toutefois, en cas de propriétés à valeurs multiples, vous devez créer une table distincte pour la propriété, comme l'explique la section suivante.</span><span class="sxs-lookup"><span data-stu-id="a5196-111">However, for multi-valued properties, you have to create a separate table for the property, as described in the following section.</span></span>  
  
## <a name="computed-column-based-on-the-xml-data-type"></a><span data-ttu-id="a5196-112">Colonne calculée basée sur le type de données xml</span><span class="sxs-lookup"><span data-stu-id="a5196-112">Computed Column Based on the xml Data Type</span></span>  
 <span data-ttu-id="a5196-113">Une colonne calculée peut être créée à l’aide d’une fonction définie par l’utilisateur qui appelle des `xml` méthodes de type de données.</span><span class="sxs-lookup"><span data-stu-id="a5196-113">A computed column can be created by using a user-defined function that invokes `xml` data type methods.</span></span> <span data-ttu-id="a5196-114">Le type de la colonne calculée peut être n'importe quel type SQL, y compris XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-114">The type of the computed column can be any SQL type, including XML.</span></span> <span data-ttu-id="a5196-115">L'exemple suivant illustre ce concept.</span><span class="sxs-lookup"><span data-stu-id="a5196-115">This is illustrated in the following example.</span></span>  
  
### <a name="example-computed-column-based-on-the-xml-data-type-method"></a><span data-ttu-id="a5196-116">Exemple : Colonne calculée basée sur la méthode du type de données xml</span><span class="sxs-lookup"><span data-stu-id="a5196-116">Example: Computed Column Based on the xml Data Type Method</span></span>  
 <span data-ttu-id="a5196-117">Créez la fonction définie par l'utilisateur pour extraire le numéro ISBN d'un livre :</span><span class="sxs-lookup"><span data-stu-id="a5196-117">Create the user-defined function for a book ISBN number:</span></span>  
  
```  
CREATE FUNCTION udf_get_book_ISBN (@xData xml)  
RETURNS varchar(20)  
BEGIN  
   DECLARE @ISBN   varchar(20)  
   SELECT @ISBN = @xData.value('/book[1]/@ISBN', 'varchar(20)')  
   RETURN @ISBN   
END  
```  
  
 <span data-ttu-id="a5196-118">Ajoutez une colonne calculée à la table pour le numéro ISBN :</span><span class="sxs-lookup"><span data-stu-id="a5196-118">Add a computed column to the table for the ISBN:</span></span>  
  
```  
ALTER TABLE      T  
ADD   ISBN AS dbo.udf_get_book_ISBN(xCol)  
```  
  
 <span data-ttu-id="a5196-119">La colonne calculée peut être indexée de manière habituelle.</span><span class="sxs-lookup"><span data-stu-id="a5196-119">The computed column can be indexed in the usual way.</span></span>  
  
### <a name="example-queries-on-a-computed-column-based-on-xml-data-type-methods"></a><span data-ttu-id="a5196-120">Exemple : Requêtes sur une colonne calculée basée sur les méthodes du type de données xml</span><span class="sxs-lookup"><span data-stu-id="a5196-120">Example: Queries on a Computed Column Based on xml Data Type Methods</span></span>  
 <span data-ttu-id="a5196-121">Pour obtenir l'élément <`book`> portant le numéro ISBN 0-7356-1588-2 :</span><span class="sxs-lookup"><span data-stu-id="a5196-121">To obtain the <`book`> whose ISBN is 0-7356-1588-2:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  xCol.exist('/book/@ISBN[. = "0-7356-1588-2"]') = 1  
```  
  
 <span data-ttu-id="a5196-122">La requête portant sur la colonne XML peut être réécrite de façon à utiliser directement la colonne calculée comme suit :</span><span class="sxs-lookup"><span data-stu-id="a5196-122">The query on the XML column can be rewritten to use the computed column as follows:</span></span>  
  
```  
SELECT xCol  
FROM   T  
WHERE  ISBN = '0-7356-1588-2'  
```  
  
 <span data-ttu-id="a5196-123">Vous pouvez créer une fonction définie par l’utilisateur pour retourner le `xml` type de données et une colonne calculée à l’aide de la fonction définie par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a5196-123">You can create a user-defined function to return the `xml` data type and a computed column by using the user-defined function.</span></span> <span data-ttu-id="a5196-124">Toutefois, vous ne pouvez pas créer d'index XML sur la colonne XML calculée.</span><span class="sxs-lookup"><span data-stu-id="a5196-124">However, you cannot create an XML index on the computed, XML column.</span></span>  
  
## <a name="creating-property-tables"></a><span data-ttu-id="a5196-125">Création de tables de propriétés</span><span class="sxs-lookup"><span data-stu-id="a5196-125">Creating Property Tables</span></span>  
 <span data-ttu-id="a5196-126">Vous pouvez promouvoir certaines des propriétés à valeurs multiples de vos données XML dans une ou plusieurs tables, placer des index sur ces tables et modifier la cible de vos requêtes de façon à les utiliser.</span><span class="sxs-lookup"><span data-stu-id="a5196-126">You may want to promote some of the multivalued properties from your XML data into one or more tables, create indexes on those tables, and target again your queries to use them.</span></span> <span data-ttu-id="a5196-127">C'est généralement l'attitude à adopter lorsqu'un petit nombre de propriétés couvre la plupart de la charge des requêtes.</span><span class="sxs-lookup"><span data-stu-id="a5196-127">A typical scenario is one in which a small number of properties covers most of your query workload.</span></span> <span data-ttu-id="a5196-128">Vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5196-128">You can do the following:</span></span>  
  
-   <span data-ttu-id="a5196-129">Créez une ou plusieurs tables pour enregistrer les propriétés à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="a5196-129">Create one or more tables to hold the multivalued properties.</span></span> <span data-ttu-id="a5196-130">Vous trouverez plus judicieux de stocker une propriété par table et de dupliquer la clé primaire de la table de base dans les tables de propriétés pour conserver la jointure avec la table de base.</span><span class="sxs-lookup"><span data-stu-id="a5196-130">You may find it convenient to store one property per table and duplicate the primary key of the base table in the property tables for back joining with the base table.</span></span>  
  
-   <span data-ttu-id="a5196-131">Si vous voulez conserver l'ordre relatif des propriétés, vous devez introduire une colonne distincte pour l'ordre relatif.</span><span class="sxs-lookup"><span data-stu-id="a5196-131">If you want to maintain the relative order of the properties, you have to introduce a separate column for the relative order.</span></span>  
  
-   <span data-ttu-id="a5196-132">Créez des déclencheurs sur la colonne XML pour assurer la maintenance des tables de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5196-132">Create triggers on the XML column to maintain the property tables.</span></span> <span data-ttu-id="a5196-133">Dans les déclencheurs, procédez ainsi :</span><span class="sxs-lookup"><span data-stu-id="a5196-133">Within the triggers, do one of the following:</span></span>  
  
    -   <span data-ttu-id="a5196-134">Utilisez `xml` des méthodes de type de données, telles que **Nodes ()** et **value ()**, pour insérer et supprimer des lignes dans les tables de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5196-134">Use `xml` data type methods, such as **nodes()** and **value()**, to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="a5196-135">Créez des fonctions table multidiffusion dans CLR (Common Language Runtime) pour insérer et supprimer des lignes dans les tables de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5196-135">Create streaming table-valued functions in the common language runtime (CLR) to insert and delete rows of the property tables.</span></span>  
  
    -   <span data-ttu-id="a5196-136">Écrivez des requêtes qui accèdent par SQL aux tables de propriétés et par XML à la colonne XML de la table de base, et prévoyez des jointures entre les tables à l'aide de leur clé primaire.</span><span class="sxs-lookup"><span data-stu-id="a5196-136">Write queries for SQL access to the property tables and for XML access to the XML column in the base table, with joins between the tables by using their primary key.</span></span>  
  
### <a name="example-create-a-property-table"></a><span data-ttu-id="a5196-137">Exemple : Création d’une table de propriétés</span><span class="sxs-lookup"><span data-stu-id="a5196-137">Example: Create a Property Table</span></span>  
 <span data-ttu-id="a5196-138">Supposons, dans cet exemple, que vous voulez promouvoir le prénom des auteurs.</span><span class="sxs-lookup"><span data-stu-id="a5196-138">For illustration, assume that you want to promote the first name of the authors.</span></span> <span data-ttu-id="a5196-139">Dans la mesure où les livres peuvent avoir un ou plusieurs auteurs, le prénom est une propriété à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="a5196-139">Books have one or more authors, so that first name is a multivalued property.</span></span> <span data-ttu-id="a5196-140">Chaque prénom est stocké dans une ligne distincte d'une table de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5196-140">Each first name is stored in a separate row of a property table.</span></span> <span data-ttu-id="a5196-141">La clé primaire de la table de base est dupliquée dans la table de propriétés pour la jointure en retour avec la table de base.</span><span class="sxs-lookup"><span data-stu-id="a5196-141">The primary key of the base table is duplicated in the property table for back join.</span></span>  
  
```  
create table tblPropAuthor (propPK int, propAuthor varchar(max))  
```  
  
### <a name="example-create-a-user-defined-function-to-generate-a-rowset-from-an-xml-instance"></a><span data-ttu-id="a5196-142">Exemple : Création d’une fonction définie par l’utilisateur pour générer un ensemble de lignes à partir d’une instance XML</span><span class="sxs-lookup"><span data-stu-id="a5196-142">Example: Create a User-defined Function to Generate a Rowset from an XML Instance</span></span>  
 <span data-ttu-id="a5196-143">La fonction table suivante, udf_XML2Table, accepte une valeur de clé primaire et une instance XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-143">The following table-valued function, udf_XML2Table, accepts a primary key value and an XML instance.</span></span> <span data-ttu-id="a5196-144">Elle récupère le prénom de tous les auteurs des éléments <`book`> et renvoie un ensemble de lignes pour les paires clé primaire/prénom.</span><span class="sxs-lookup"><span data-stu-id="a5196-144">It retrieves the first name of all authors of the <`book`> elements and returns a rowset of primary key, first name pairs.</span></span>  
  
```  
create function udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (propPK int, propAuthor varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
      select @pk, nref.value('.', 'varchar(max)')  
      from   @xCol.nodes('/book/author/first-name') R(nref)  
      return  
end  
```  
  
### <a name="example-create-triggers-to-populate-a-property-table"></a><span data-ttu-id="a5196-145">Exemple : Création de déclencheurs pour remplir une table de propriétés</span><span class="sxs-lookup"><span data-stu-id="a5196-145">Example: Create Triggers to Populate a Property Table</span></span>  
 <span data-ttu-id="a5196-146">Le déclencheur insert insère des lignes dans la table de propriétés :</span><span class="sxs-lookup"><span data-stu-id="a5196-146">The insert trigger inserts rows into the property table:</span></span>  
  
```  
create trigger trg_docs_INS on T for insert  
as  
      declare @wantedXML xml  
      declare @FK int  
      select @wantedXML = xCol from inserted  
      select @FK = PK from inserted  
  
   insert into tblPropAuthor  
   select * from dbo.udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="a5196-147">Le déclencheur delete supprime des lignes dans la table de propriétés en fonction de la valeur de la clé primaire des lignes supprimées :</span><span class="sxs-lookup"><span data-stu-id="a5196-147">The delete trigger deletes the rows from the property table based on the primary key value of the deleted rows:</span></span>  
  
```  
create trigger trg_docs_DEL on T for delete  
as  
   declare @FK int  
   select @FK = PK from deleted  
   delete tblPropAuthor where propPK = @FK  
```  
  
 <span data-ttu-id="a5196-148">Le déclencheur update supprime les lignes existant dans la table de propriétés qui correspondent à l'instance XML mise à jour et insère les nouvelles à la place :</span><span class="sxs-lookup"><span data-stu-id="a5196-148">The update trigger deletes the existing rows in the property table corresponding to the updated XML instance and inserts new rows into the property table:</span></span>  
  
```  
create trigger trg_docs_UPD  
on T  
for update  
as  
if update(xCol) or update(pk)  
begin  
      declare @FK int  
      declare @wantedXML xml  
      select @FK = PK from deleted  
      delete tblPropAuthor where propPK = @FK  
  
   select @wantedXML = xCol from inserted  
   select @FK = pk from inserted  
  
   insert into tblPropAuthor   
      select * from dbo.udf_XML2Table(@FK, @wantedXML)  
end  
```  
  
### <a name="example-find-xml-instances-whose-authors-have-the-same-first-name"></a><span data-ttu-id="a5196-149">Exemple : Recherche des instances XML dont les auteurs portent le même prénom</span><span class="sxs-lookup"><span data-stu-id="a5196-149">Example: Find XML Instances Whose Authors Have the Same First Name</span></span>  
 <span data-ttu-id="a5196-150">La requête peut être formée sur la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-150">The query can be formed on the XML column.</span></span> <span data-ttu-id="a5196-151">Une autre possibilité consiste à rechercher le prénom « David » dans la table de propriétés et à faire une jointure en retour avec la table de base pour renvoyer l'instance XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-151">Alternatively, it can search the property table for first name "David" and perform a back join with the base table to return the XML instance.</span></span> <span data-ttu-id="a5196-152">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a5196-152">For example:</span></span>  
  
```  
SELECT xCol   
FROM     T JOIN tblPropAuthor ON T.pk = tblPropAuthor.propPK  
WHERE    tblPropAuthor.propAuthor = 'David'  
```  
  
### <a name="example-solution-using-the-clr-streaming-table-valued-function"></a><span data-ttu-id="a5196-153">Exemple : Solution utilisant la fonction table de streaming CLR</span><span class="sxs-lookup"><span data-stu-id="a5196-153">Example: Solution Using the CLR Streaming Table-valued Function</span></span>  
 <span data-ttu-id="a5196-154">La solution se compose des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="a5196-154">This solution is made up of the following steps:</span></span>  
  
1.  <span data-ttu-id="a5196-155">Définissez une classe CLR, SqlReaderBase, qui met en œuvre ISqlReader et génère une sortie table multidiffusion par application d'une expression de chemin sur une instance XML.</span><span class="sxs-lookup"><span data-stu-id="a5196-155">Define a CLR class, SqlReaderBase, that implements ISqlReader and generates a streaming, table-valued output by applying a path expression on an XML instance.</span></span>  
  
2.  <span data-ttu-id="a5196-156">Créez un assembly et une fonction Transact-SQL définie par l'utilisateur pour démarrer la classe CLR.</span><span class="sxs-lookup"><span data-stu-id="a5196-156">Create an assembly and a Transact-SQL user-defined function to start the CLR class.</span></span>  
  
3.  <span data-ttu-id="a5196-157">Définissez les déclencheurs insert, update et delete à l'aide de la fonction définie par l'utilisateur pour assurer la maintenance de la table de propriétés.</span><span class="sxs-lookup"><span data-stu-id="a5196-157">Define the insert, update, and delete triggers by using the user-defined function to maintain a property tables.</span></span>  
  
 <span data-ttu-id="a5196-158">Pour cela, vous devez commencer par créer la fonction multidiffusion dans CLR.</span><span class="sxs-lookup"><span data-stu-id="a5196-158">To do this, you first create the streaming CLR function.</span></span> <span data-ttu-id="a5196-159">Le `xml` type de données est exposé en tant que classe managée SQLXML dans ADO.net et prend en charge la méthode **CreateReader ()** qui retourne un XmlReader.</span><span class="sxs-lookup"><span data-stu-id="a5196-159">The `xml` data type is exposed as a managed class SqlXml in ADO.NET and supports the **CreateReader()** method that returns an XmlReader.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a5196-160">L'exemple de code de cette section utilise XPathDocument et XPathNavigator,</span><span class="sxs-lookup"><span data-stu-id="a5196-160">The example code in this section uses XPathDocument and XPathNavigator.</span></span> <span data-ttu-id="a5196-161">ce qui vous oblige à charger tous les documents XML en mémoire.</span><span class="sxs-lookup"><span data-stu-id="a5196-161">These force you to load all the XML documents into memory.</span></span> <span data-ttu-id="a5196-162">Si vous utilisez un code similaire dans votre application pour traiter plusieurs documents XML volumineux, ce code n'est pas évolutif.</span><span class="sxs-lookup"><span data-stu-id="a5196-162">If you are using similar code in your application to process several large XML documents, this code is not scalable.</span></span> <span data-ttu-id="a5196-163">Au lieu de cela, laissez les allocations de mémoire petites et utilisez les interfaces multidiffusion chaque fois que possible.</span><span class="sxs-lookup"><span data-stu-id="a5196-163">Instead, keep memory allocations small and use streaming interfaces whenever possible.</span></span> <span data-ttu-id="a5196-164">Pour plus d’informations sur les performances, consultez [Architecture d’intégration du CLR](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span><span class="sxs-lookup"><span data-stu-id="a5196-164">For more information about performance, see [Architecture of CLR Integration](../../database-engine/dev-guide/architecture-of-clr-integration.md).</span></span>  
  
```  
public class c_streaming_xml_tvf {  
   public static ISqlReader streaming_xml_tvf   
(SqlXml xmlDoc, string pathExpression) {  
      return (new TestSqlReaderBase (xmlDoc, pathExpression));  
   }  
}  
  
// Class that implements ISqlReader  
public class TestSqlReaderBase : ISqlReader {  
XPathNodeIterator m_iterator;           
   public SqlChars FirstName;  
// Metadata for current resultset  
private SqlMetaData[] m_rgSqlMetaData;        
  
   public TestSqlReaderBase (SqlXml xmlDoc, string pathExpression) {     
      // Variables for XPath navigation  
      XPathDocument xDoc;  
      XPathNavigator xNav;  
      XPathExpression xPath;  
  
      // Set sql metadata  
      m_rgSqlMetaData = new SqlMetaData[1];  
      m_rgSqlMetaData[0] = new SqlMetaData ("FirstName",    
SqlDbType.NVarChar,50);     
  
      //Set up the Navigator  
      if (!xmlDoc.IsNull)  
          xDoc = new XPathDocument (xmlDoc.CreateReader());  
      else  
          xDoc = new XPathDocument ();  
      xNav = xDoc.CreateNavigator();  
      xPath = xNav.Compile (pathExpression);  
      m_iterator = xNav.Select(xPath);  
   }  
   public bool Read() {  
      bool moreRows = true;  
      if (moreRows = m_iterator.MoveNext())  
         FirstName = new SqlChars (m_iterator.Current.Value);  
      return moreRows;  
   }  
}  
```  
  
 <span data-ttu-id="a5196-165">Ensuite, créez un assembly et une fonction [!INCLUDE[tsql](../../includes/tsql-md.md)] définie par l'utilisateur SQL_streaming_xml_tvf (non présentée), correspondant à la fonction CLR streaming_xml_tvf.</span><span class="sxs-lookup"><span data-stu-id="a5196-165">Next, create an assembly and a [!INCLUDE[tsql](../../includes/tsql-md.md)] user-defined function, SQL_streaming_xml_tvf (not shown), that corresponds to the CLR function, streaming_xml_tvf.</span></span> <span data-ttu-id="a5196-166">La fonction définie par l'utilisateur sert à définir la fonction table, CLR_udf_XML2Table, pour la génération de l'ensemble de lignes :</span><span class="sxs-lookup"><span data-stu-id="a5196-166">The user-defined function is used to define the table-valued function, CLR_udf_XML2Table, for rowset generation:</span></span>  
  
```  
create function CLR_udf_XML2Table (@pk int, @xCol xml)  
returns @ret_Table table (FK int, FirstName varchar(max))  
with schemabinding  
as  
begin  
      insert into @ret_Table   
   select @pk, FirstName   
   FROM   SQL_streaming_xml_tvf (@xCol, '/book/author/first-name')  
      return  
end  
```  
  
 <span data-ttu-id="a5196-167">Pour finir, définissez les déclencheurs en suivant l'exemple « Création de déclencheurs pour remplir une table de propriétés », mais remplacez udf_XML2Table par la fonction CLR_udf_XML2Table.</span><span class="sxs-lookup"><span data-stu-id="a5196-167">Finally, define triggers as shown in the example, "Create triggers to populate a property table", but replace udf_XML2Table with the CLR_udf_XML2Table function.</span></span> <span data-ttu-id="a5196-168">Le déclencheur insert est présenté dans l'exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="a5196-168">The insert trigger is shown in the following example:</span></span>  
  
```  
create trigger CLR_trg_docs_INS on T for insert  
as  
   declare @wantedXML xml  
   declare @FK int  
   select @wantedXML = xCol from inserted  
   select @FK = PK from inserted  
  
   insert into tblPropAuthor  
      select *  
   from    dbo.CLR_udf_XML2Table(@FK, @wantedXML)  
```  
  
 <span data-ttu-id="a5196-169">Le déclencheur delete est identique à celui utilisé dans la version non CLR.</span><span class="sxs-lookup"><span data-stu-id="a5196-169">The delete trigger is identical to the non-CLR version.</span></span> <span data-ttu-id="a5196-170">Le déclencheur update, quant à lui, remplace simplement la fonction udf_XML2Table() par CLR_udf_XML2Table().</span><span class="sxs-lookup"><span data-stu-id="a5196-170">However, the update trigger just replaces the function udf_XML2Table() with CLR_udf_XML2Table().</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5196-171">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a5196-171">See Also</span></span>  
 [<span data-ttu-id="a5196-172">Utiliser des données XML dans les colonnes calculées</span><span class="sxs-lookup"><span data-stu-id="a5196-172">Use XML in Computed Columns</span></span>](use-xml-in-computed-columns.md)  
  
  
