---
title: Charger des données XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], loading
- loading XML data
ms.assetid: d1741e8d-f44e-49ec-9f14-10208b5468a7
author: rothja
ms.author: jroth
ms.openlocfilehash: c48d1d6feccb7df9fec9801ee56abcab99884754
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702504"
---
# <a name="load-xml-data"></a><span data-ttu-id="9f5f9-102">Charger des données XML</span><span class="sxs-lookup"><span data-stu-id="9f5f9-102">Load XML Data</span></span>
  <span data-ttu-id="9f5f9-103">Vous pouvez transférer des données XML dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] de plusieurs manières.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-103">You can transfer XML data into [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in several ways.</span></span> <span data-ttu-id="9f5f9-104">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9f5f9-104">For example:</span></span>  
  
-   <span data-ttu-id="9f5f9-105">Si vos données figurent dans une colonne de type [n]text ou image, dans une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous pouvez importer la table par le biais de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9f5f9-105">If you have your data in an [n]text or image column in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, you can import the table by using [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="9f5f9-106">Modifiez ensuite le type de colonne en XML à l'aide de l'instruction ALTER TABLE.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-106">Change the column type to XML by using the ALTER TABLE statement.</span></span>  
  
-   <span data-ttu-id="9f5f9-107">Vous pouvez copier vos données en bloc à partir d’une autre base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide de bcp out, puis les insérer en bloc dans la base de données de version ultérieure à l’aide de bcp in.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-107">You can bulk copy your data from another [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using bcp out, and then bulk insert the data into the later version database by using bcp in.</span></span>  
  
-   <span data-ttu-id="9f5f9-108">Si vous avez des données dans des colonnes relationnelles d'une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , créez une table avec une colonne [n]text et, éventuellement, une colonne de clé primaire pour un identificateur de ligne.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-108">If you have data in relational columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, create a new table with an [n]text column and, optionally, a primary key column for a row identifier.</span></span> <span data-ttu-id="9f5f9-109">Utilisez la programmation côté client pour récupérer les données XML générées sur le serveur par la clause FOR XML et placez-les dans la colonne `[n]text`.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-109">Use client-side programming to retrieve the XML that is generated at the server with FOR XML and write it into the `[n]text` column.</span></span> <span data-ttu-id="9f5f9-110">Ensuite, utilisez les techniques citées précédemment pour transférer les données vers une base de données de version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-110">Then, use the previously mentioned techniques to transfer data to a later version database.</span></span> <span data-ttu-id="9f5f9-111">Vous pouvez choisir d’écrire directement le code XML dans une colonne XML de la base de données de version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-111">You can choose to write the XML into an XML column in the later version database directly.</span></span>  
  
## <a name="bulk-loading-xml-data"></a><span data-ttu-id="9f5f9-112">Chargement en masse de données XML</span><span class="sxs-lookup"><span data-stu-id="9f5f9-112">Bulk loading XML data</span></span>  
 <span data-ttu-id="9f5f9-113">Vous pouvez charger en masse des données XML sur le serveur en utilisant les fonctions de chargement en masse de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], comme bcp.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-113">You can bulk load XML data into the server by using the bulk loading capabilities of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as bcp.</span></span> <span data-ttu-id="9f5f9-114">OPENROWSET vous permet de charger des données dans une colonne XML à partir de fichiers.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-114">OPENROWSET allows you to load data into an XML column from files.</span></span> <span data-ttu-id="9f5f9-115">L'exemple suivant illustre ce comportement :</span><span class="sxs-lookup"><span data-stu-id="9f5f9-115">The following example illustrates this point.</span></span>  
  
##### <a name="example-loading-xml-from-files"></a><span data-ttu-id="9f5f9-116">Exemple : Chargement de données XML à partir de fichiers</span><span class="sxs-lookup"><span data-stu-id="9f5f9-116">Example: Loading XML from Files</span></span>  
 <span data-ttu-id="9f5f9-117">Cet exemple montre comment insérer une ligne dans la table T. La valeur de la colonne XML est chargée à partir du fichier C:\MyFile\xmlfile.xml en tant que CLOB, et la colonne integer prend la valeur 10.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-117">This example shows how to insert a row in table T. The value of the XML column is loaded from file C:\MyFile\xmlfile.xml as CLOB, and the integer column is supplied the value 10.</span></span>  
  
```  
INSERT INTO T  
SELECT 10, xCol  
FROM    (SELECT *      
    FROM OPENROWSET (BULK 'C:\MyFile\xmlfile.xml', SINGLE_CLOB)   
 AS xCol) AS R(xCol)  
```  
  
## <a name="text-encoding"></a><span data-ttu-id="9f5f9-118">Encodage de texte</span><span class="sxs-lookup"><span data-stu-id="9f5f9-118">Text Encoding</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="9f5f9-119">stocke les données XML au format Unicode (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="9f5f9-119">stores XML data in Unicode (UTF-16).</span></span> <span data-ttu-id="9f5f9-120">Les données XML extraites du serveur se présentent au format UTF-16.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-120">XML data retrieved from the server comes out in UTF-16 encoding.</span></span> <span data-ttu-id="9f5f9-121">Si vous souhaitez un encodage différent, vous devez convertir les données extraites au format voulu.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-121">If you want a different encoding, you have to perform the required conversion on the retrieved data.</span></span> <span data-ttu-id="9f5f9-122">Il arrive que les données XML soient encodées différemment.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-122">Sometimes, the XML data may be in a different encoding.</span></span> <span data-ttu-id="9f5f9-123">Si tel est le cas, vous devez prêter une attention particulière au chargement des données.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-123">If it is, you have to use care during data loading.</span></span> <span data-ttu-id="9f5f9-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9f5f9-124">For example:</span></span>  
  
-   <span data-ttu-id="9f5f9-125">Si votre texte XML est en Unicode (UCS-2, UTF-16), vous pouvez l'affecter à une colonne, une variable ou un paramètre XML sans aucun problème.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-125">If your text XML is in Unicode (UCS-2, UTF-16), you can assign it to an XML column, variable, or parameter  without any problems.</span></span>  
  
-   <span data-ttu-id="9f5f9-126">Si l'encodage ne se fait pas en Unicode et qu'il est implicite, du fait d'une page de codes source, la page de codes de la chaîne dans la base de données doit être identique (ou du moins compatible) aux points de code que vous souhaitez charger.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-126">If the encoding is not Unicode and is implicit, because of the source code page, the string code page in the database should be the same as or compatible with the code points that you want to load.</span></span> <span data-ttu-id="9f5f9-127">Si nécessaire, utilisez COLLATE.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-127">If required, use COLLATE.</span></span> <span data-ttu-id="9f5f9-128">Si aucune page de codes serveur de la sorte n'existe, vous devez ajouter une déclaration XML explicite mentionnant l'encodage correct.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-128">If no such server code page exists, you have to add an explicit XML declaration with the correct encoding.</span></span>  
  
-   <span data-ttu-id="9f5f9-129">Pour utiliser un encodage explicite, utilisez le type `varbinary()`, qui n'a aucune interaction avec les pages de codes, ou utilisez un type chaîne de la page de codes appropriée.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-129">To use an explicit encoding, use either the `varbinary()` type, which has no interaction with code pages, or use a string type of the appropriate code page.</span></span> <span data-ttu-id="9f5f9-130">Ensuite, assignez les données à une colonne, une variable ou un paramètre XML.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-130">Then, assign the data to an XML column, variable, or parameter.</span></span>  
  
### <a name="example-explicitly-specifying-an-encoding"></a><span data-ttu-id="9f5f9-131">Exemple : Spécification implicite d’un encodage</span><span class="sxs-lookup"><span data-stu-id="9f5f9-131">Example: Explicitly Specifying an Encoding</span></span>  
 <span data-ttu-id="9f5f9-132">Supposez que vous avez un document XML, vcdoc, stocké au format `varchar(max)`, qui ne comporte aucune déclaration XML explicite.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-132">Assume that you have an XML document, vcdoc, stored as `varchar(max)` that does not have an explicit XML declaration.</span></span> <span data-ttu-id="9f5f9-133">L'instruction ci-dessous permet d'ajouter une déclaration XML mentionnant l'encodage « iso8859-1 », de concaténer le document XML, de convertir le résultat au format `varbinary(max)` de façon à conserver la représentation en octets, puis enfin de le convertir au format XML.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-133">The following statement adds an XML declaration with the encoding "iso8859-1", concatenates the XML document, casts the result to `varbinary(max)` so that the byte representation is preserved, and then finally casts it to XML.</span></span> <span data-ttu-id="9f5f9-134">Ainsi, le processeur XML peut analyser les données conformément à l'encodage spécifié « iso8859-1 » et générer la représentation UTF-16 correspondante pour les valeurs de chaîne.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-134">This enables the XML processor to parse the data according to the specified encoding "iso8859-1" and generate the corresponding UTF-16 representation for string values.</span></span>  
  
```  
SELECT CAST(   
CAST (('<?xml version="1.0" encoding="iso8859-1"?>'+ vcdoc) AS VARBINARY (MAX))   
 AS XML)  
```  
  
### <a name="string-encoding-incompatibilities"></a><span data-ttu-id="9f5f9-135">Incompatibilités d'encodage de chaîne</span><span class="sxs-lookup"><span data-stu-id="9f5f9-135">String Encoding Incompatibilities</span></span>  
 <span data-ttu-id="9f5f9-136">Si vous copiez et collez du code XML sous forme de littéral chaîne dans la fenêtre d'éditeur de requête de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], vous risquez de rencontrer des incompatibilités d'encodage de la chaîne [N]VARCHAR.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-136">If you copy and paste XML as a string literal into the Query Editor window in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], you might experience [N]VARCHAR string encoding incompatibilities.</span></span> <span data-ttu-id="9f5f9-137">Tout dépendra de l'encodage de votre instance XML.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-137">This will depend on the encoding of your XML instance.</span></span> <span data-ttu-id="9f5f9-138">Dans bien des cas, vous serez amené à supprimer la déclaration XML.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-138">In many cases, you may want to remove the XML declaration.</span></span> <span data-ttu-id="9f5f9-139">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9f5f9-139">For example:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8"?>  
  <xsd:schema ...  
```  
  
 <span data-ttu-id="9f5f9-140">Vous devez ensuite inclure un N pour transformer l'instance XML en une instance Unicode.</span><span class="sxs-lookup"><span data-stu-id="9f5f9-140">You should then include an N to make the XML instance an instance of Unicode.</span></span> <span data-ttu-id="9f5f9-141">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="9f5f9-141">For example:</span></span>  
  
```  
-- Assign XML instance to a variable.  
DECLARE @X XML  
SET @X = N'...'  
-- Insert XML instance into an xml type column.  
INSERT INTO T VALUES (N'...')  
-- Create an XML schema collection  
CREATE XML SCHEMA COLLECTION XMLCOLL1 AS N'<xsd:schema ... '  
```  
  
## <a name="see-also"></a><span data-ttu-id="9f5f9-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9f5f9-142">See Also</span></span>  
 [<span data-ttu-id="9f5f9-143">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9f5f9-143">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
