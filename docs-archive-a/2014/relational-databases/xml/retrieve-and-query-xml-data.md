---
title: Récupérer et interroger des données XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XML data [SQL Server], retrieving
- XML instance retrieval
ms.assetid: 24a28760-1225-42b3-9c89-c9c0332d9c51
author: rothja
ms.author: jroth
ms.openlocfilehash: d387d1b96a57dcc7100368779f8ec6078fad5c7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697591"
---
# <a name="retrieve-and-query-xml-data"></a><span data-ttu-id="a86ed-102">Récupérer et interroger des données XML</span><span class="sxs-lookup"><span data-stu-id="a86ed-102">Retrieve and Query XML Data</span></span>
  <span data-ttu-id="a86ed-103">Cette rubrique décrit les options de requête que vous devez spécifier pour interroger les données XML.</span><span class="sxs-lookup"><span data-stu-id="a86ed-103">This topic describes the query options that you have to specify to query XML data.</span></span> <span data-ttu-id="a86ed-104">Elle décrit aussi les parties des instances XML qui ne sont pas conservées lorsqu'elles sont stockées dans des bases de données.</span><span class="sxs-lookup"><span data-stu-id="a86ed-104">It also describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>  
  
##  <a name="features-of-an-xml-instance-that-are-not-preserved"></a><a name="features"></a> <span data-ttu-id="a86ed-105">Fonctionnalités d'une instance XML qui ne sont pas conservées</span><span class="sxs-lookup"><span data-stu-id="a86ed-105">Features of an XML Instance That Are Not Preserved</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a86ed-106">conserve le contenu de l’instance XML, mais ne conserve pas les aspects de l’instance XML qui ne sont pas considérés significatifs dans le modèle de données XML.</span><span class="sxs-lookup"><span data-stu-id="a86ed-106">preserves the content of the XML instance, but does not preserve aspects of the XML instance that are not considered to be significant in the XML data model.</span></span> <span data-ttu-id="a86ed-107">Cela signifie qu'une instance XML extraite peut ne pas être identique à l'instance stockée sur le serveur, mais contiendra les mêmes informations.</span><span class="sxs-lookup"><span data-stu-id="a86ed-107">This means that a retrieved XML instance might not be identical to the instance that was stored in the server, but will contain the same information.</span></span>  
  
### <a name="xml-declaration"></a><span data-ttu-id="a86ed-108">Déclaration XML</span><span class="sxs-lookup"><span data-stu-id="a86ed-108">XML Declaration</span></span>  
 <span data-ttu-id="a86ed-109">La déclaration XML d'une instance n'est pas conservée lors du stockage de l'instance dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="a86ed-109">The XML declaration in an instance is not preserved when the instance is stored in the database.</span></span> <span data-ttu-id="a86ed-110">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a86ed-110">For example:</span></span>  
  
```  
CREATE TABLE T1 (Col1 int primary key, Col2 xml)  
GO  
INSERT INTO T1 values (1, '<?xml version="1.0" encoding="windows-1252" ?><doc></doc>')  
GO  
SELECT Col2  
FROM T1  
```  
  
 <span data-ttu-id="a86ed-111">Le résultat est `<doc/>`.</span><span class="sxs-lookup"><span data-stu-id="a86ed-111">The result is `<doc/>`.</span></span>  
  
 <span data-ttu-id="a86ed-112">La déclaration XML, telle que `<?xml version='1.0'?>`, n'est pas conservée en cas de stockage des données XML dans une instance de type de données `xml`.</span><span class="sxs-lookup"><span data-stu-id="a86ed-112">The XML declaration, such as `<?xml version='1.0'?>`, is not preserved when storing XML data in an `xml` data type instance.</span></span> <span data-ttu-id="a86ed-113">C'est la procédure normale.</span><span class="sxs-lookup"><span data-stu-id="a86ed-113">This is by design.</span></span> <span data-ttu-id="a86ed-114">La déclaration XML () et ses attributs (version/Encoding/stand-alone) sont perdus une fois les données converties en type `xml` .</span><span class="sxs-lookup"><span data-stu-id="a86ed-114">The XML declaration () and its attributes (version/encoding/stand-alone) are lost after data is converted to type `xml`.</span></span> <span data-ttu-id="a86ed-115">La déclaration XML est traitée comme une directive de l'analyseur XML.</span><span class="sxs-lookup"><span data-stu-id="a86ed-115">The XML declaration is treated as a directive to the XML parser.</span></span> <span data-ttu-id="a86ed-116">Les données XML sont stockées en interne au format ucs-2.</span><span class="sxs-lookup"><span data-stu-id="a86ed-116">The XML data is stored internally as ucs-2.</span></span> <span data-ttu-id="a86ed-117">Toutes les autres instructions de traitement dans l'instance XML sont conservées.</span><span class="sxs-lookup"><span data-stu-id="a86ed-117">All other PIs in the XML instance are preserved.</span></span>  
  
  
### <a name="order-of-attributes"></a><span data-ttu-id="a86ed-118">Ordre des attributs</span><span class="sxs-lookup"><span data-stu-id="a86ed-118">Order of Attributes</span></span>  
 <span data-ttu-id="a86ed-119">L'ordre des attributs d'une instance XML n'est pas conservé.</span><span class="sxs-lookup"><span data-stu-id="a86ed-119">The order of attributes in an XML instance is not preserved.</span></span> <span data-ttu-id="a86ed-120">Lorsque vous interrogez l'instance XML stockée dans la colonne de type `xml`, l'ordre des attributs du code XML résultant peut différer de l'ordre utilisé dans l'instance XML d'origine.</span><span class="sxs-lookup"><span data-stu-id="a86ed-120">When you query the XML instance stored in the `xml` type column, the order of attributes in the resulting XML may be different from the original XML instance.</span></span>  
  
  
### <a name="quotation-marks-around-attribute-values"></a><span data-ttu-id="a86ed-121">Guillemets autour des valeurs d'attributs</span><span class="sxs-lookup"><span data-stu-id="a86ed-121">Quotation Marks Around Attribute Values</span></span>  
 <span data-ttu-id="a86ed-122">Les guillemets et les guillemets simples qui encadrent les valeurs des attributs ne sont pas conservés.</span><span class="sxs-lookup"><span data-stu-id="a86ed-122">Single quotation marks and double quotations marks around attribute values are not preserved.</span></span> <span data-ttu-id="a86ed-123">Les valeurs des attributs sont stockées sous forme de paire nom et valeur.</span><span class="sxs-lookup"><span data-stu-id="a86ed-123">The attribute values are stored in the database as a name and value pair.</span></span> <span data-ttu-id="a86ed-124">Les guillemets ne sont pas stockés.</span><span class="sxs-lookup"><span data-stu-id="a86ed-124">The quotation marks are not stored.</span></span> <span data-ttu-id="a86ed-125">En cas d'exécution d'une requête XQuery sur une instance XML, le code XML résultant est sérialisé, et les valeurs des attributs figurent entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="a86ed-125">When an XQuery is executed against an XML instance, the resulting XML is serialized with double quotation marks around the attribute values.</span></span>  
  
```  
DECLARE @x xml  
-- Use double quotation marks.  
SET @x = '<root a="1" />'  
SELECT @x  
GO  
DECLARE @x xml  
-- Use single quotation marks.  
SET @x = '<root a=''1'' />'  
SELECT @x  
GO  
```  
  
 <span data-ttu-id="a86ed-126">Les deux requêtes retournent = `<root a="1" />`.</span><span class="sxs-lookup"><span data-stu-id="a86ed-126">Both queries return = `<root a="1" />`.</span></span>  
  
  
### <a name="namespace-prefixes"></a><span data-ttu-id="a86ed-127">Préfixes d'espace de noms</span><span class="sxs-lookup"><span data-stu-id="a86ed-127">Namespace Prefixes</span></span>  
 <span data-ttu-id="a86ed-128">Les préfixes d'espace de noms ne sont pas conservés.</span><span class="sxs-lookup"><span data-stu-id="a86ed-128">Namespace prefixes are not preserved.</span></span> <span data-ttu-id="a86ed-129">Lorsque vous définissez une requête XQuery sur une colonne de type `xml`, le code XML sérialisé qui en découle peut renvoyer des préfixes d'espace de noms différents.</span><span class="sxs-lookup"><span data-stu-id="a86ed-129">When you specify XQuery against an `xml` type column, the serialized XML result may return different namespace prefixes.</span></span>  
  
```  
DECLARE @x xml  
SET @x = '<ns1:root xmlns:ns1="abc" xmlns:ns2="abc">  
            <ns2:SomeElement/>  
          </ns1:root>'  
SELECT @x  
SELECT @x.query('/*')  
GO  
```  
  
 <span data-ttu-id="a86ed-130">Le préfixe d'espace de noms peut avoir une valeur différente dans le résultat.</span><span class="sxs-lookup"><span data-stu-id="a86ed-130">The namespace prefix in the result may be different.</span></span> <span data-ttu-id="a86ed-131">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a86ed-131">For example:</span></span>  
  
```  
<p1:root xmlns:p1="abc"><p1:SomeElement/></p1:root>  
```  
  
  
##  <a name="setting-required-query-options"></a><a name="query"></a> <span data-ttu-id="a86ed-132">Définition des options requises de requête</span><span class="sxs-lookup"><span data-stu-id="a86ed-132">Setting Required Query Options</span></span>  
 <span data-ttu-id="a86ed-133">Lors de l’interrogation de `xml` colonnes de type ou de variables à l’aide de `xml` méthodes de type de données, les options suivantes doivent être définies comme indiqué.</span><span class="sxs-lookup"><span data-stu-id="a86ed-133">When querying `xml` type columns or variables using `xml` data type methods, the following options must be set as shown.</span></span>  
  
|<span data-ttu-id="a86ed-134">Options SET</span><span class="sxs-lookup"><span data-stu-id="a86ed-134">SET Options</span></span>|<span data-ttu-id="a86ed-135">Valeurs requises</span><span class="sxs-lookup"><span data-stu-id="a86ed-135">Required Values</span></span>|  
|-----------------|---------------------|  
|<span data-ttu-id="a86ed-136">ANSI_NULLS</span><span class="sxs-lookup"><span data-stu-id="a86ed-136">ANSI_NULLS</span></span>|<span data-ttu-id="a86ed-137">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="a86ed-137">ON</span></span>|  
|<span data-ttu-id="a86ed-138">ANSI_PADDING</span><span class="sxs-lookup"><span data-stu-id="a86ed-138">ANSI_PADDING</span></span>|<span data-ttu-id="a86ed-139">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="a86ed-139">ON</span></span>|  
|<span data-ttu-id="a86ed-140">ANSI_WARNINGS</span><span class="sxs-lookup"><span data-stu-id="a86ed-140">ANSI_WARNINGS</span></span>|<span data-ttu-id="a86ed-141">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="a86ed-141">ON</span></span>|  
|<span data-ttu-id="a86ed-142">ARITHABORT</span><span class="sxs-lookup"><span data-stu-id="a86ed-142">ARITHABORT</span></span>|<span data-ttu-id="a86ed-143">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="a86ed-143">ON</span></span>|  
|<span data-ttu-id="a86ed-144">CONCAT_NULL_YIELDS_NULL</span><span class="sxs-lookup"><span data-stu-id="a86ed-144">CONCAT_NULL_YIELDS_NULL</span></span>|<span data-ttu-id="a86ed-145">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="a86ed-145">ON</span></span>|  
|<span data-ttu-id="a86ed-146">NUMERIC_ROUNDABORT</span><span class="sxs-lookup"><span data-stu-id="a86ed-146">NUMERIC_ROUNDABORT</span></span>|<span data-ttu-id="a86ed-147">OFF</span><span class="sxs-lookup"><span data-stu-id="a86ed-147">OFF</span></span>|  
|<span data-ttu-id="a86ed-148">QUOTED_IDENTIFIER</span><span class="sxs-lookup"><span data-stu-id="a86ed-148">QUOTED_IDENTIFIER</span></span>|<span data-ttu-id="a86ed-149">ACTIVÉ</span><span class="sxs-lookup"><span data-stu-id="a86ed-149">ON</span></span>|  
  
 <span data-ttu-id="a86ed-150">Si les options ne sont pas définies comme indiqué, les requêtes et les modifications sur les `xml` méthodes de type de données échouent.</span><span class="sxs-lookup"><span data-stu-id="a86ed-150">If the options are not set as shown, queries and modifications on `xml` data type methods will fail.</span></span>  
  
  
## <a name="see-also"></a><span data-ttu-id="a86ed-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a86ed-151">See Also</span></span>  
 [<span data-ttu-id="a86ed-152">Créer des instances de données XML</span><span class="sxs-lookup"><span data-stu-id="a86ed-152">Create Instances of XML Data</span></span>](create-instances-of-xml-data.md)  
  
  
