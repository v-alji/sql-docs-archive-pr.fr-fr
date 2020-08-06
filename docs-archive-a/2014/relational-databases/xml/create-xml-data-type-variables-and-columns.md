---
title: Créer des variables et des colonnes de type de données XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- xml data type [SQL Server], columns
ms.assetid: 8994ab6e-5519-4ba2-97a1-fac8af6f72db
author: rothja
ms.author: jroth
ms.openlocfilehash: 08b79888eb47634deaccc910b2ea3c93800b7c78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706291"
---
# <a name="create-xml-data-type-variables-and-columns"></a><span data-ttu-id="2e972-102">Créer des variables et des colonnes de type de données XML</span><span class="sxs-lookup"><span data-stu-id="2e972-102">Create XML Data Type Variables and Columns</span></span>
  <span data-ttu-id="2e972-103">Le type de données `xml` est un type de données intégré à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], quelque peu similaire aux autres types intégrés, tels que `int` et `varchar`.</span><span class="sxs-lookup"><span data-stu-id="2e972-103">The `xml` data type is a built-in data type in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and is somewhat similar to other built-in types such as `int` and `varchar`.</span></span> <span data-ttu-id="2e972-104">Comme avec les autres types intégrés, vous pouvez utiliser le `xml` type de données comme type de colonne lorsque vous créez une table en tant que type de variable, type de paramètre, type de retour de fonction ou en [Cast et Convert](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2e972-104">As with other built-in types, you can use the `xml` data type as a column type when you create a table as a variable type, a parameter type, a function-return type, or in [CAST and CONVERT](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
## <a name="creating-columns-and-variables"></a><span data-ttu-id="2e972-105">Création de variables et de colonnes</span><span class="sxs-lookup"><span data-stu-id="2e972-105">Creating Columns and Variables</span></span>  
 <span data-ttu-id="2e972-106">Pour créer une colonne de type `xml` dans le cadre d’une table, utilisez une instruction `CREATE TABLE` , comme illustré dans l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="2e972-106">To create an `xml` type column as part of a table, use a `CREATE TABLE` statement, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T1(Col1 int primary key, Col2 xml)   
```  
  
 <span data-ttu-id="2e972-107">Vous pouvez utiliser une `DECLARE statement` pour créer une variable de type `xml` , comme le montre l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2e972-107">You can use a `DECLARE statement` to create a variable of `xml` type, as the following example shows.</span></span>  
  
```  
DECLARE @x xml   
```  
  
 <span data-ttu-id="2e972-108">Créez une variable `xml` typée en spécifiant une collection de schémas XML, comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2e972-108">Create a typed `xml` variable by specifying an XML schema collection, as shown in the following example.</span></span>  
  
```  
DECLARE @x xml (Sales.StoreSurveySchemaCollection)  
```  
  
 <span data-ttu-id="2e972-109">Pour passer un paramètre de type `xml` à une procédure stockée, utilisez une instruction `CREATE PROCEDURE` , comme illustré dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2e972-109">To pass an `xml` type parameter to a stored procedure, use a `CREATE PROCEDURE` statement, as shown in the following example.</span></span>  
  
```  
CREATE PROCEDURE SampleProc(@XmlDoc xml) AS ...   
```  
  
 <span data-ttu-id="2e972-110">Vous pouvez utiliser XQuery pour interroger des instances XML stockées dans des colonnes, paramètres ou variables.</span><span class="sxs-lookup"><span data-stu-id="2e972-110">You can use XQuery to query XML instances stored in columns, parameters, or variables.</span></span> <span data-ttu-id="2e972-111">Vous pouvez également utiliser le langage de manipulation de données XML pour appliquer des mises à jour aux instances XML.</span><span class="sxs-lookup"><span data-stu-id="2e972-111">You can also use the XML Data Manipulation Language (XML DML) to apply updates to the XML instances.</span></span> <span data-ttu-id="2e972-112">Le développement du standard XQuery n’ayant pas donné lieu à la définition d’une syntaxe DML XQuery, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduit des extensions [DML XML (XML Data Modification Language)](/sql/t-sql/xml/xml-data-modification-language-xml-dml) dans XQuery.</span><span class="sxs-lookup"><span data-stu-id="2e972-112">Because the XQuery standard did not define XQuery DML at the time of development, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] introduces [XML Data Modification Language](/sql/t-sql/xml/xml-data-modification-language-xml-dml) extensions to XQuery.</span></span> <span data-ttu-id="2e972-113">Ces extensions vous permettent de réaliser des opérations d'insertion, de mise à jour et de suppression.</span><span class="sxs-lookup"><span data-stu-id="2e972-113">These extensions allow you to perform insert, update, and delete operations.</span></span>  
  
## <a name="assigning-defaults"></a><span data-ttu-id="2e972-114">Affectation de valeurs par défaut</span><span class="sxs-lookup"><span data-stu-id="2e972-114">Assigning Defaults</span></span>  
 <span data-ttu-id="2e972-115">Dans une table, vous pouvez affecter une instance XML par défaut à une colonne de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="2e972-115">In a table, you can assign a default XML instance to a column of `xml` type.</span></span> <span data-ttu-id="2e972-116">Vous pouvez fournir le XML par défaut de deux manières : en utilisant une constante XML ou en utilisant un cast explicite au type `xml`.</span><span class="sxs-lookup"><span data-stu-id="2e972-116">You can provide the default XML in one of two ways: by using an XML constant, or by using an explicit cast to the `xml` type.</span></span>  
  
 <span data-ttu-id="2e972-117">Pour fournir le XML par défaut en tant que constante XML, utilisez la syntaxe comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2e972-117">To provide the default XML as an XML constant, use syntax as shown in the following example.</span></span> <span data-ttu-id="2e972-118">Notez que la chaîne est convertie implicitement au type `xml`.</span><span class="sxs-lookup"><span data-stu-id="2e972-118">Note that the string is implicitly CAST to `xml` type.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml default N'<element1/><element2/>')  
```  
  
 <span data-ttu-id="2e972-119">Pour fournir le XML par défaut en tant que `CAST` explicite au type `xml`, utilisez la syntaxe comme illustré dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="2e972-119">To provide the default XML as an explicit `CAST` to `xml`, use syntax as shown in the following example.</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml   
                  default CAST(N'<element1/><element2/>' AS xml))  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2e972-120">prend également en charge les contraintes NULL et NOT NULL sur des colonnes de type `xml`.</span><span class="sxs-lookup"><span data-stu-id="2e972-120">also supports NULL and NOT NULL constraints on columns of `xml` type.</span></span> <span data-ttu-id="2e972-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="2e972-121">For example:</span></span>  
  
```  
CREATE TABLE T (XmlColumn xml NOT NULL)  
```  
  
## <a name="specifying-constraints"></a><span data-ttu-id="2e972-122">Spécification de contraintes</span><span class="sxs-lookup"><span data-stu-id="2e972-122">Specifying Constraints</span></span>  
 <span data-ttu-id="2e972-123">Lorsque vous créez des colonnes de type `xml`, vous pouvez définir des contraintes de niveau colonne ou de niveau table.</span><span class="sxs-lookup"><span data-stu-id="2e972-123">When you create columns of `xml` type, you can define column-level or table-level constraints.</span></span> <span data-ttu-id="2e972-124">Utilisez les contraintes dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="2e972-124">Use constraints in the following situations:</span></span>  
  
-   <span data-ttu-id="2e972-125">Vos règles d'entreprise ne peuvent pas être exprimées dans les schémas XML.</span><span class="sxs-lookup"><span data-stu-id="2e972-125">Your business rules cannot be expressed in XML schemas.</span></span> <span data-ttu-id="2e972-126">Par exemple, l'adresse de livraison d'un fleuriste doit se trouver à 80 km du magasin.</span><span class="sxs-lookup"><span data-stu-id="2e972-126">For example, the delivery address of a flower shop must be within 50 miles of its business location.</span></span> <span data-ttu-id="2e972-127">Cela peut faire l'objet d'une contrainte dans la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="2e972-127">This can be written as a constraint on the XML column.</span></span> <span data-ttu-id="2e972-128">La contrainte peut impliquer des méthodes de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="2e972-128">The constraint may involve `xml` data type methods.</span></span>  
  
-   <span data-ttu-id="2e972-129">Votre contrainte implique d'autres colonnes XML ou non XML de la table.</span><span class="sxs-lookup"><span data-stu-id="2e972-129">Your constraint involves other XML or non-XML columns in the table.</span></span> <span data-ttu-id="2e972-130">Vous pourriez, par exemple, vouloir absolument que l'ID d'un client (`/Customer/@CustId`) figurant dans une instance XML corresponde à la valeur d'une colonne relationnelle CustomerID.</span><span class="sxs-lookup"><span data-stu-id="2e972-130">An example is the enforcement of the ID of a Customer (`/Customer/@CustId`) found in an XML instance to match the value in a relational CustomerID column.</span></span>  
  
 <span data-ttu-id="2e972-131">Vous pouvez spécifier des contraintes pour les colonnes de type de données `xml` typées ou non typées.</span><span class="sxs-lookup"><span data-stu-id="2e972-131">You can specify constraints for typed or untyped `xml` data type columns.</span></span> <span data-ttu-id="2e972-132">Toutefois, vous ne pouvez pas utiliser les [méthodes de type de données xm](/sql/t-sql/xml/xml-data-type-methods) lorsque vous spécifiez des contraintes.</span><span class="sxs-lookup"><span data-stu-id="2e972-132">However, you cannot use the [XML data type methods](/sql/t-sql/xml/xml-data-type-methods) when you specify constraints.</span></span> <span data-ttu-id="2e972-133">Notez également que le type de données `xml` ne prend pas en charge les contraintes de colonne et de table suivantes :</span><span class="sxs-lookup"><span data-stu-id="2e972-133">Also, note that the `xml` data type does not support the following column and table constraints:</span></span>  
  
-   <span data-ttu-id="2e972-134">PRIMARY KEY/ FOREIGN KEY</span><span class="sxs-lookup"><span data-stu-id="2e972-134">PRIMARY KEY/ FOREIGN KEY</span></span>  
  
-   <span data-ttu-id="2e972-135">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="2e972-135">UNIQUE</span></span>  
  
-   <span data-ttu-id="2e972-136">COLLATE</span><span class="sxs-lookup"><span data-stu-id="2e972-136">COLLATE</span></span>  
  
     <span data-ttu-id="2e972-137">XML fournit son propre encodage.</span><span class="sxs-lookup"><span data-stu-id="2e972-137">XML provides its own encoding.</span></span> <span data-ttu-id="2e972-138">Les classements ne s'appliquent qu'aux types chaîne.</span><span class="sxs-lookup"><span data-stu-id="2e972-138">Collations apply to string types only.</span></span> <span data-ttu-id="2e972-139">Le type de données `xml` n'est pas un type chaîne.</span><span class="sxs-lookup"><span data-stu-id="2e972-139">The `xml` data type is not a string type.</span></span> <span data-ttu-id="2e972-140">Toutefois, il possède une représentation chaîne et permet la conversion en provenance et en direction des types de données chaîne.</span><span class="sxs-lookup"><span data-stu-id="2e972-140">However, it does have string representation and allows casting to and from string data types.</span></span>  
  
-   <span data-ttu-id="2e972-141">RULE</span><span class="sxs-lookup"><span data-stu-id="2e972-141">RULE</span></span>  
  
 <span data-ttu-id="2e972-142">Une alternative à l'utilisation de contraintes consiste à créer une fonction wrapper définie par l'utilisateur permettant d'inclure la méthode de type de données `xml` et à spécifier cette fonction dans la contrainte de validation, comme le montre l'exemple ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="2e972-142">An alternative to using constraints is to create a wrapper, user-defined function to wrap the `xml` data type method and specify user-defined function in the check constraint as shown in the following example.</span></span>  
  
 <span data-ttu-id="2e972-143">Dans l'exemple suivant, la contrainte sur `Col2` spécifie que chaque instance XML stockée dans cette colonne doit posséder un élément `<ProductDescription>` doté d'un attribut `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="2e972-143">In the following example, the constraint on `Col2` specifies that each XML instance stored in this column must have a `<ProductDescription>` element that contains a `ProductID` attribute.</span></span> <span data-ttu-id="2e972-144">Cette contrainte est appliquée par cette fonction définie par l'utilisateur :</span><span class="sxs-lookup"><span data-stu-id="2e972-144">This constraint is enforced by this user-defined function:</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns bit  
AS BEGIN   
RETURN @var.exist('/ProductDescription/@ProductID')  
END  
GO  
```  
  
 <span data-ttu-id="2e972-145">La méthode `exist()` du type de données `xml` renvoie `1` si l'élément `<ProductDescription>` de l'instance contient l'attribut `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="2e972-145">Note that the `exist()` method of the `xml` data type returns `1` if the `<ProductDescription>` element in the instance contains the `ProductID` attribute.</span></span> <span data-ttu-id="2e972-146">Sinon, `0`est retourné.</span><span class="sxs-lookup"><span data-stu-id="2e972-146">Otherwise, it returns `0`.</span></span>  
  
 <span data-ttu-id="2e972-147">Maintenant, vous pouvez créer une table dotée d'une contrainte de niveau colonne, comme suit :</span><span class="sxs-lookup"><span data-stu-id="2e972-147">Now, you can create a table with a column-level constraint as follows:</span></span>  
  
```  
CREATE TABLE T (  
    Col1 int primary key,   
    Col2 xml check(dbo.my_udf(Col2)=1))  
GO  
```  
  
 <span data-ttu-id="2e972-148">L'insertion suivante réussit :</span><span class="sxs-lookup"><span data-stu-id="2e972-148">The following insert succeeds:</span></span>  
  
```  
INSERT INTO T values(1,'<ProductDescription ProductID="1" />')  
```  
  
 <span data-ttu-id="2e972-149">La contrainte fait échouer l'insertion suivante :</span><span class="sxs-lookup"><span data-stu-id="2e972-149">Because of the constraint, the following insert fails:</span></span>  
  
```  
INSERT INTO T values(1,'<Product />')  
```  
  
## <a name="same-or-different-table"></a><span data-ttu-id="2e972-150">Table identique ou différente</span><span class="sxs-lookup"><span data-stu-id="2e972-150">Same or Different Table</span></span>  
 <span data-ttu-id="2e972-151">Une `xml` colonne de type de données peut être créée dans une table qui contient d’autres colonnes relationnelles ou dans une table distincte avec une relation de clé étrangère avec une table principale.</span><span class="sxs-lookup"><span data-stu-id="2e972-151">An `xml` data type column can be created in a table that contains other relational columns, or in a separate table with a foreign key relationship to a main table.</span></span>  
  
 <span data-ttu-id="2e972-152">Créez une `xml` colonne de type de données dans la même table lorsque l’une des conditions suivantes est remplie :</span><span class="sxs-lookup"><span data-stu-id="2e972-152">Create an `xml` data type column in the same table when one of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="2e972-153">Votre application récupère les données dans la colonne XML sans exiger qu'un index XML existe dans la colonne XML.</span><span class="sxs-lookup"><span data-stu-id="2e972-153">Your application performs data retrieval on the XML column and does not require an XML index on the XML column.</span></span>  
  
-   <span data-ttu-id="2e972-154">Vous voulez créer un index XML sur la colonne de type `xml` et la clé primaire de la table principale est identique à sa clé de clustering.</span><span class="sxs-lookup"><span data-stu-id="2e972-154">You want to build an XML index on the `xml` data type column and the primary key of the main table is the same as its clustering key.</span></span> <span data-ttu-id="2e972-155">Pour plus d’informations, consultez [Index XML &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="2e972-155">For more information, see [XML Indexes &#40;SQL Server&#41;](xml-indexes-sql-server.md).</span></span>  
  
 <span data-ttu-id="2e972-156">Créez la colonne de type `xml` dans une table distincte si les conditions suivantes sont remplies :</span><span class="sxs-lookup"><span data-stu-id="2e972-156">Create the `xml` data type column in a separate table if the following conditions are true:</span></span>  
  
-   <span data-ttu-id="2e972-157">Vous voulez créer un index XML sur la colonne de type `xml`, mais la clé primaire de la table principale est différente de sa clé de clustering, ou la table principale n'a pas de clé primaire, ou la table principale est un segment (sans clé de clustering).</span><span class="sxs-lookup"><span data-stu-id="2e972-157">You want to build an XML index on the `xml` data type column, but the primary key of the main table is different from its clustering key, or the main table does not have a primary key, or the main table is a heap (no clustering key).</span></span> <span data-ttu-id="2e972-158">Cela peut se produire si la table principale existe déjà.</span><span class="sxs-lookup"><span data-stu-id="2e972-158">This may be true if the main table already exists.</span></span>  
  
-   <span data-ttu-id="2e972-159">Vous ne voulez pas voir les analyses de la table ralentir suite à la présence d'une colonne XML dans la table.</span><span class="sxs-lookup"><span data-stu-id="2e972-159">You do not want table scans to slow down because of the presence of the XML column in the table.</span></span> <span data-ttu-id="2e972-160">La quantité d'espace utilisée varie selon que le stockage se fait en ligne ou hors ligne.</span><span class="sxs-lookup"><span data-stu-id="2e972-160">This uses space whether it is stored in-row or out-of-row.</span></span>  
  
  
