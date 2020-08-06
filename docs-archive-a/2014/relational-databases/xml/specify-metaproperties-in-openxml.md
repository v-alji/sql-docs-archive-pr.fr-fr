---
title: Spécifier des métapropriétés dans OPENXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- overflow in XML document [SQL Server]
- metaproperties [XML in SQL Server]
- unconsumed data
- extracting information of XML nodes [SQL Server]
- OPENXML statement, metaproperties
ms.assetid: 29bfd1c6-3f9a-43c4-924a-53d438e442f4
author: rothja
ms.author: jroth
ms.openlocfilehash: c52d1162aa495deff8a0fde314fdcde0735d9c2f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703975"
---
# <a name="specify-metaproperties-in-openxml"></a><span data-ttu-id="6b7d7-102">Spécifier des métapropriétés dans OPENXML</span><span class="sxs-lookup"><span data-stu-id="6b7d7-102">Specify Metaproperties in OPENXML</span></span>
  <span data-ttu-id="6b7d7-103">Les attributs de métapropriétés dans un document XML décrivent les propriétés d'un élément XML (élément, attribut ou tout autre nœud DOM).</span><span class="sxs-lookup"><span data-stu-id="6b7d7-103">Metaproperty attributes in an XML document are attributes that describe the properties of an XML item, such as element, attribute, or any other DOM node.</span></span> <span data-ttu-id="6b7d7-104">Ces attributs n'existent pas physiquement dans le texte du document XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-104">These attributes do not physically exist in the XML document text.</span></span> <span data-ttu-id="6b7d7-105">Toutefois, OPENXML fournit ces métapropriétés pour tous les éléments XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-105">However, OPENXML provides these metaproperties for all the XML items.</span></span> <span data-ttu-id="6b7d7-106">Ces métapropriétés vous permettent d'extraire des informations (par exemple des informations de positionnement local et d'espace de noms) sur les nœuds XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-106">These metaproperties allow you to extract information, such as local positioning and namespace information, of XML nodes.</span></span> <span data-ttu-id="6b7d7-107">Ces informations vous procurent davantage de détails que ceux apparents dans la représentation textuelle.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-107">This information provides you with more details than are apparent in the textual representation.</span></span>  
  
 <span data-ttu-id="6b7d7-108">Vous pouvez mapper ces métapropriétés aux colonnes de l’ensemble de lignes dans une instruction OPENXML à l’aide du paramètre *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="6b7d7-108">You can map these metaproperties to the rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span> <span data-ttu-id="6b7d7-109">Les colonnes contiendront les valeurs des métapropriétés avec lesquelles elles sont mappées.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-109">The columns will contain the values of the metaproperties to which they are mapped.</span></span> <span data-ttu-id="6b7d7-110">Pour plus d’informations sur la syntaxe d’OPENXML, consultez [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6b7d7-110">For more information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span>  
  
 <span data-ttu-id="6b7d7-111">Pour accéder aux attributs de métapropriétés, un espace de noms spécifique à SQL Server est fourni.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-111">To access the metaproperty attributes, a namespace that is specific to SQL Server is provided.</span></span> <span data-ttu-id="6b7d7-112">Cet espace de noms, **urn:schemas-microsoft-com:xml-metaprop** , permet à l’utilisateur d’accéder aux attributs de métapropriétés.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-112">This namespace, **urn:schemas-microsoft-com:xml-metaprop** allows the user to access the metaproperty attributes.</span></span> <span data-ttu-id="6b7d7-113">Si le résultat d’une requête OPENXML est retourné sous un format de table du bord, celle-ci contient une colonne par attribut de métapropriété (sauf la métapropriété **xmltext** ).</span><span class="sxs-lookup"><span data-stu-id="6b7d7-113">If the result of an OPENXML query is returned in an edge table format, the edge table contains one column for each metaproperty attribute, except the **xmltext** metaproperty.</span></span>  
  
 <span data-ttu-id="6b7d7-114">Certains attributs de métapropriétés sont utilisés à des fins de traitement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-114">Some of the metaproperty attributes are used for processing purposes.</span></span> <span data-ttu-id="6b7d7-115">Par exemple, l’attribut de métapropriété **xmltext** permet de gérer les dépassements.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-115">For example, the **xmltext** metaproperty attribute is used for overflow handling.</span></span> <span data-ttu-id="6b7d7-116">Cette gestion concerne les données du document non consommées ou non traitées.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-116">Overflow handling refers to the unconsumed, unprocessed data in the document.</span></span> <span data-ttu-id="6b7d7-117">L'une des colonnes de l'ensemble de lignes qui est généré par OPENXML peut être identifiée comme colonne de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-117">One of the columns in the rowset that is generated by OPENXML can be identified as the overflow column.</span></span> <span data-ttu-id="6b7d7-118">Pour cela, vous devez la mapper à la métapropriété **xmltext** à l’aide du paramètre *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="6b7d7-118">You do this by mapping it to the **xmltext** metaproperty by using the *ColPattern* parameter.</span></span> <span data-ttu-id="6b7d7-119">La colonne reçoit ensuite les données de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-119">The column then receives the overflow data.</span></span> <span data-ttu-id="6b7d7-120">Le paramètre *flags* détermine si la colonne contient tout ou uniquement les données non consommées.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-120">The *flags* parameter determines whether the column contains everything or only the unconsumed data.</span></span>  
  
 <span data-ttu-id="6b7d7-121">Le tableau suivant répertorie les attributs de métapropriétés détenus par chaque élément XML analysé.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-121">The following table lists the metaproperty attributes that each parsed XML element possesses.</span></span> <span data-ttu-id="6b7d7-122">Ces attributs de métapropriétés sont accessibles par le biais de l’espace de noms **urn:schemas-microsoft-com:xml-metaprop**.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-122">These metaproperty attributes can be accessed by using the namespace **urn:schemas-microsoft-com:xml-metaprop**.</span></span> <span data-ttu-id="6b7d7-123">Toute valeur définie directement par l'utilisateur dans le document XML à l'aide de ces métapropriétés est ignorée.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-123">Any value that the user sets directly in the XML document by using these metaproperties is ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6b7d7-124">Aucune navigation XPath ne vous permet de faire référence à ces métapropriétés.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-124">You cannot reference these metaproperties in any XPath navigation.</span></span>  
  
|<span data-ttu-id="6b7d7-125">Attribut de métapropriété</span><span class="sxs-lookup"><span data-stu-id="6b7d7-125">Metaproperty attribute</span></span>|<span data-ttu-id="6b7d7-126">Description</span><span class="sxs-lookup"><span data-stu-id="6b7d7-126">Description</span></span>|  
|----------------------------|-----------------|  
|<span data-ttu-id="6b7d7-127">**\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-127">**\@mp:id**</span></span>|<span data-ttu-id="6b7d7-128">Fournit l'identificateur du nœud DOM. Cet identificateur est généré par le système et couvre l'ensemble du document.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-128">Provides a system-generated, document-wide identifier of the DOM node.</span></span> <span data-ttu-id="6b7d7-129">Tant que le document n'est pas réanalysé, cet ID fait référence au même nœud XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-129">As long as the document is not reparsed, this ID refers to the same XML node.</span></span><br /><br /> <span data-ttu-id="6b7d7-130">Un ID XML de valeur **0** indique que l’élément est un élément racine.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-130">An XML ID of **0** indicates that the element is a root element.</span></span> <span data-ttu-id="6b7d7-131">Son ID XML parent vaut NULL.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-131">Its parent XML ID is NULL.</span></span>|  
|<span data-ttu-id="6b7d7-132">**\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-132">**\@mp:localname**</span></span>|<span data-ttu-id="6b7d7-133">Stocke la partie locale du nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-133">Stores the local part of the name of the node.</span></span> <span data-ttu-id="6b7d7-134">Utilisé avec un préfixe et un URI d'espace de noms, il permet de nommer les nœuds d'éléments ou d'attributs.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-134">It is used with a prefix and a namespace URI to name element or attribute nodes.</span></span>|  
|<span data-ttu-id="6b7d7-135">**\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-135">**\@mp:namespaceuri**</span></span>|<span data-ttu-id="6b7d7-136">Fournit l'URI de l'espace de noms de l'élément actuel.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-136">Provides the namespace URI of the current element.</span></span> <span data-ttu-id="6b7d7-137">Si la valeur de cet attribut est NULL, aucun espace de noms n'est présent.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-137">If the value of this attribute is NULL, no namespace is present</span></span>|  
|<span data-ttu-id="6b7d7-138">**\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-138">**\@mp:prefix**</span></span>|<span data-ttu-id="6b7d7-139">Stocke le préfixe d'espace de noms de l'élément actuel.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-139">Stores the namespace prefix of the current element name.</span></span><br /><br /> <span data-ttu-id="6b7d7-140">Si aucun préfixe n'est présent (NULL) et qu'un URI est fourni, l'espace de noms spécifié est l'espace de noms par défaut.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-140">If no prefix is present (NULL) and a URI is given, it indicates that the specified namespace is the default namespace.</span></span> <span data-ttu-id="6b7d7-141">Si aucun URI n'est fourni, aucun espace de noms n'est attaché.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-141">If no URI is given, no namespace is attached.</span></span>|  
|<span data-ttu-id="6b7d7-142">**\@mp:prev**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-142">**\@mp:prev**</span></span>|<span data-ttu-id="6b7d7-143">Stocke le frère précédent relatif à un nœud.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-143">Stores the previous sibling relative to a node.</span></span> <span data-ttu-id="6b7d7-144">Fournit des informations sur l'ordre des éléments dans le document.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-144">This provides information about the ordering of elements in the document.</span></span><br /><br /> <span data-ttu-id="6b7d7-145">**\@mp:prev** contient l’ID XML du frère précédent possédant le même élément parent.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-145">**\@mp:prev** contains the XML ID of the previous sibling that has the same parent element.</span></span> <span data-ttu-id="6b7d7-146">Si un élément figure au début de la liste des frères, **\@mp:prev** a pour valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-146">If an element is at the front of the sibling list, **\@mp:prev** is NULL.</span></span>|  
|<span data-ttu-id="6b7d7-147">**\@mp:xmltext**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-147">**\@mp:xmltext**</span></span>|<span data-ttu-id="6b7d7-148">Utilisé à des fins de traitement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-148">Used for processing purposes.</span></span> <span data-ttu-id="6b7d7-149">Représente la sérialisation textuelle de l'élément, ainsi que de ses attributs et sous-éléments, utilisée dans la gestion de dépassement d'OPENXML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-149">It is the textual serialization of the element and its attributes, and also the subelements, as used in the overflow handling of OPENXML.</span></span>|  
  
 <span data-ttu-id="6b7d7-150">Ce tableau présente les propriétés parentes supplémentaires qui vous permettent d'extraire des informations sur la hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-150">This table shows the additional parent properties that are provided and which allow you to retrieve information about the hierarchy.</span></span>  
  
|<span data-ttu-id="6b7d7-151">Attribut de métapropriété parent</span><span class="sxs-lookup"><span data-stu-id="6b7d7-151">Parent metaproperty attribute</span></span>|<span data-ttu-id="6b7d7-152">Description</span><span class="sxs-lookup"><span data-stu-id="6b7d7-152">Description</span></span>|  
|-----------------------------------|-----------------|  
|<span data-ttu-id="6b7d7-153">**\@mp:parentid**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-153">**\@mp:parentid**</span></span>|<span data-ttu-id="6b7d7-154">Correspond à **../\@mp:id**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-154">Corresponds to **../\@mp:id**</span></span>|  
|<span data-ttu-id="6b7d7-155">**\@mp:parentlocalname**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-155">**\@mp:parentlocalname**</span></span>|<span data-ttu-id="6b7d7-156">Correspond à **../\@mp:localname**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-156">Corresponds to **../\@mp:localname**</span></span>|  
|<span data-ttu-id="6b7d7-157">**\@mp:parentnamespacerui**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-157">**\@mp:parentnamespacerui**</span></span>|<span data-ttu-id="6b7d7-158">Correspond à **../\@mp:namespaceuri**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-158">Corresponds to **../\@mp:namespaceuri**</span></span>|  
|<span data-ttu-id="6b7d7-159">**\@mp:parentprefix**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-159">**\@mp:parentprefix**</span></span>|<span data-ttu-id="6b7d7-160">Correspond à **../\@mp:prefix**</span><span class="sxs-lookup"><span data-stu-id="6b7d7-160">Corresponds to **../\@mp:prefix**</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="6b7d7-161">Exemples</span><span class="sxs-lookup"><span data-stu-id="6b7d7-161">Examples</span></span>  
 <span data-ttu-id="6b7d7-162">Les exemples suivants illustrent l'utilisation d'OPENXML pour créer différentes vues d'ensembles de lignes.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-162">The following examples illustrate how OPENXML is used to create different rowset views.</span></span>  
  
### <a name="a-mapping-the-openxml-rowset-columns-to-the-metaproperties"></a><span data-ttu-id="6b7d7-163">R.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-163">A.</span></span> <span data-ttu-id="6b7d7-164">Mappage des colonnes de l'ensemble de lignes OPENXML aux métapropriétés</span><span class="sxs-lookup"><span data-stu-id="6b7d7-164">Mapping the OPENXML rowset columns to the metaproperties</span></span>  
 <span data-ttu-id="6b7d7-165">Cet exemple utilise OPENXML pour créer une vue d'ensemble de lignes de l'exemple de document XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-165">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="6b7d7-166">Plus spécifiquement, il montre comment différents attributs de métapropriétés peuvent être mappés à des colonnes d’ensembles de lignes dans une instruction OPENXML à l’aide du paramètre *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="6b7d7-166">Specifically, it shows how the various metaproperty attributes can be mapped to rowset columns in an OPENXML statement by using the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="6b7d7-167">L'instruction OPENXML contient les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6b7d7-167">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="6b7d7-168">La colonne **id** est mappée à l’attribut de métapropriété **\@mp:id**, ce qui indique qu’elle contient l’ID XML unique généré par le système de l’élément.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-168">The **id** column is mapped to the **\@mp:id** metaproperty attribute and indicates that the column contains the system-generated unique XML ID of the element.</span></span>  
  
-   <span data-ttu-id="6b7d7-169">La colonne **parent** est mappée à **\@mp:parentid**, ce qui indique qu’elle contient l’ID XML du parent de l’élément.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-169">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent of the element.</span></span>  
  
-   <span data-ttu-id="6b7d7-170">La colonne **parentLocalName** est mappée à **\@mp:parentlocalname**, ce qui indique qu’elle contient le nom local du parent.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-170">The **parentLocalName** column is mapped to **\@mp:parentlocalname** and indicates that the column contains the local name of the parent.</span></span>  
  
 <span data-ttu-id="6b7d7-171">L'instruction SELECT retourne ensuite l'ensemble de lignes fourni par OPENXML :</span><span class="sxs-lookup"><span data-stu-id="6b7d7-171">The SELECT statement then returns the rowset that is provided by OPENXML:</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- Sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (id int '@mp:id',   
            oid char(5),   
            date datetime,   
            amount real,   
            parentIDNo int '@mp:parentid',   
            parentLocalName varchar(40) '@mp:parentlocalname')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="6b7d7-172">Voici le résultat obtenu :</span><span class="sxs-lookup"><span data-stu-id="6b7d7-172">This is the result:</span></span>  
  
```  
id   oid         date                amount    parentIDNo  parentLocalName    
--- ------- ---------------------- ---------- ------------ ---------------  
6    O1    1996-01-20 00:00:00.000     3.5         2        Customer  
10   O2    1997-04-30 00:00:00.000     13.4        2        Customer  
19   O3    1999-07-14 00:00:00.000     100.0       15       Customer  
25   O4    1996-01-20 00:00:00.000     10000.0     15       Customer  
```  
  
### <a name="b-retrieving-the-whole-xml-document"></a><span data-ttu-id="6b7d7-173">B.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-173">B.</span></span> <span data-ttu-id="6b7d7-174">Récupération du document XML en entier</span><span class="sxs-lookup"><span data-stu-id="6b7d7-174">Retrieving the whole XML document</span></span>  
 <span data-ttu-id="6b7d7-175">Dans cet exemple, OPENXML est utilisé pour créer une vue d'ensemble de lignes contenant une seule colonne à partir de l'exemple de document XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-175">In this example, OPENXML is used to create a one-column rowset view of the sample XML document.</span></span> <span data-ttu-id="6b7d7-176">Cette colonne, **Col1**, est mappée à la métapropriété **xmltext** et devient une colonne de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-176">This column, **Col1**, is mapped to the **xmltext** metaproperty and becomes an overflow column.</span></span> <span data-ttu-id="6b7d7-177">En conséquence, elle reçoit les données non consommées.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-177">As a result, the column receives the unconsumed data.</span></span> <span data-ttu-id="6b7d7-178">Dans ce cas, il s'agit du document en entier.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-178">In this case, it is the whole document.</span></span>  
  
 <span data-ttu-id="6b7d7-179">L'instruction SELECT retourne ensuite l'intégralité de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-179">The SELECT statement then returns the complete rowset.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
SET @doc = N'<?xml version="1.0"?>  
<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
     <MyTag>Testing to see if all the subelements are returned</MyTag>  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/')  
   WITH (Col1 ntext '@mp:xmltext')  
```  
  
 <span data-ttu-id="6b7d7-180">Pour extraire l'intégralité du document sans déclaration XML, vous pouvez spécifier la requête comme suit :</span><span class="sxs-lookup"><span data-stu-id="6b7d7-180">To retrieve the whole document without the XML declaration, the query can be specified as shown in the following:</span></span>  
  
```  
SELECT *  
FROM OPENXML (@idoc, '/root')  
   WITH (Col1 ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="6b7d7-181">La requête retourne l'élément racine ayant la racine du nom et les données contenues dans l'élément racine.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-181">The query returns the root element that has the name root and the data that is contained by the root element</span></span>  
  
### <a name="c-specifying-the-xmltext-metaproperty-to-retrieve-the-unconsumed-data-in-a-column"></a><span data-ttu-id="6b7d7-182">C.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-182">C.</span></span> <span data-ttu-id="6b7d7-183">Spécification de la métapropriété xmltext pour récupérer les données non consommées d'une colonne</span><span class="sxs-lookup"><span data-stu-id="6b7d7-183">Specifying the xmltext metaproperty to retrieve the unconsumed data in a column</span></span>  
 <span data-ttu-id="6b7d7-184">Cet exemple utilise OPENXML pour créer une vue d'ensemble de lignes de l'exemple de document XML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-184">This example uses OPENXML to create a rowset view of the sample XML document.</span></span> <span data-ttu-id="6b7d7-185">Il montre comment récupérer des données XML non consommées en mappant l’attribut de métapropriété **xmltext** à une colonne d’ensemble de lignes dans OPENXML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-185">The example shows how to retrieve unconsumed XML data by mapping the **xmltext** metaproperty attribute to a rowset column in OPENXML.</span></span>  
  
 <span data-ttu-id="6b7d7-186">La colonne **comment** est mappée à la métapropriété **\@mp:xmltext**, ce qui l’identifie comme colonne de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-186">The **comment** column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span> <span data-ttu-id="6b7d7-187">Le paramètre *flags* a la valeur **9** (XML_ATTRIBUTE et XML_NOCOPY).</span><span class="sxs-lookup"><span data-stu-id="6b7d7-187">The *flags* parameter is set to **9** (XML_ATTRIBUTE and XML_NOCOPY).</span></span> <span data-ttu-id="6b7d7-188">Cela indique un mappage **centré sur l’attribut** et signifie que seules les données non consommées doivent être copiées dans la colonne de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-188">This indicates **attribute-centric** mapping and indicates that only the unconsumed data should be copied to the overflow column.</span></span>  
  
 <span data-ttu-id="6b7d7-189">L'instruction SELECT retourne ensuite l'ensemble de lignes fourni par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-189">The SELECT statement then returns the rowset provided by OPENXML.</span></span>  
  
 <span data-ttu-id="6b7d7-190">Dans cet exemple, la métapropriété **\@mp:parentlocalname** est définie pour une colonne (**ParentLocalName**) de l’ensemble de lignes généré par OPENXML.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-190">In this example, the **\@mp:parentlocalname** metaproperty is set for a column, **ParentLocalName**, in the rowset generated by OPENXML.</span></span> <span data-ttu-id="6b7d7-191">Par conséquent, cette colonne contient le nom local de l'élément parent.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-191">As a result, this column contains the local name of the parent element.</span></span>  
  
 <span data-ttu-id="6b7d7-192">Deux autres colonnes sont spécifiées dans l’ensemble de lignes ( **parent** et **comment**).</span><span class="sxs-lookup"><span data-stu-id="6b7d7-192">Two additional columns are specified in the rowset, **parent** and **comment**.</span></span> <span data-ttu-id="6b7d7-193">La colonne **parent** est mappée à **\@mp:parentid**, ce qui indique qu’elle contient l’ID XML de l’élément parent de l’élément.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-193">The **parent** column is mapped to **\@mp:parentid** and indicates that the column contains the XML ID of the parent element of the element.</span></span> <span data-ttu-id="6b7d7-194">La colonne comment est mappée à la métapropriété **\@mp:xmltext**, ce qui l’identifie comme colonne de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-194">The comment column is identified as the overflow column by mapping it to the **\@mp:xmltext** metaproperty.</span></span>  
  
```  
DECLARE @idoc int  
DECLARE @doc nvarchar(1000)  
-- sample XML document  
SET @doc = N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>  
'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @idoc OUTPUT, @doc  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@idoc, '/root/Customer/Order', 9)  
      WITH (oid char(5),   
            date datetime,  
            comment ntext '@mp:xmltext')  
EXEC sp_xml_removedocument @idoc  
```  
  
 <span data-ttu-id="6b7d7-195">Voici l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-195">This is the result.</span></span> <span data-ttu-id="6b7d7-196">Les données oid et date étant déjà consommées, elles n'apparaissent pas dans la colonne de dépassement.</span><span class="sxs-lookup"><span data-stu-id="6b7d7-196">Because the oid columns and date columns are already consumed, they do not appear in the overflow column.</span></span>  
  
```  
oid   date                        comment                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            
----- --------------------------- ----------------------------------------  
O1    1996-01-20 00:00:00.000     <Order amount="3.5"/>  
O2    1997-04-30 00:00:00.000     <Order amount="13.4">Customer was very   
                                   satisfied</Order>  
O3    1999-07-14 00:00:00.000     <Order amount="100" note="Wrap it blue   
                                   white red"><Urgency>   
                                   Important</Urgency></Order>  
O4    1996-01-20 00:00:00.000     <Order amount="10000"/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6b7d7-197">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6b7d7-197">See Also</span></span>  
 <span data-ttu-id="6b7d7-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6b7d7-198">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="6b7d7-199">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6b7d7-199">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
