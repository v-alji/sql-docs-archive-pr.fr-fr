---
title: Utiliser le mode RAW avec FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML RAW mode
- XMLSCHEMA option
- FOR XML clause, RAW mode
- RAW FOR XML mode
- ELEMENTS directive
- RAW mode
- XMLDATA option
ms.assetid: 02c1bc0b-760c-4589-9ab1-6927c6d9c734
author: rothja
ms.author: jroth
ms.openlocfilehash: b2908a98336ec8a6e12029ad471f22a33d7a4dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706287"
---
# <a name="use-raw-mode-with-for-xml"></a><span data-ttu-id="bdf8e-102">Utiliser le mode RAW avec FOR XML</span><span class="sxs-lookup"><span data-stu-id="bdf8e-102">Use RAW Mode with FOR XML</span></span>
  <span data-ttu-id="bdf8e-103">Le mode RAW transforme chaque ligne du jeu de résultats de la requête en un élément XML contenant l’identificateur générique \<row> ou le nom d’élément éventuellement fourni.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-103">RAW mode transforms each row in the query result set into an XML element that has the generic identifier \<row>, or the optionally provided element name.</span></span> <span data-ttu-id="bdf8e-104">Par défaut, chaque valeur de colonne dans l’ensemble de lignes qui n’est pas NULL est mappée à un attribut de l’élément \<row>.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-104">By default, each column value in the rowset that is not NULL is mapped to an attribute of the \<row> element.</span></span> <span data-ttu-id="bdf8e-105">Si la directive ELEMENTS est ajoutée à la clause FOR XML, chaque valeur de colonne est mappée à un sous-élément de l’élément \<row>.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-105">If the ELEMENTS directive is added to the FOR XML clause, each column value is mapped to a subelement of the \<row> element.</span></span> <span data-ttu-id="bdf8e-106">Avec la directive ELEMENTS, vous pouvez éventuellement spécifier l'option XSINIL pour mapper les valeurs de colonnes NULL dans le jeu de résultats à un élément qui possède l'attribut xsi:nil=`"`true`"`.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-106">Together with the ELEMENTS directive, you can optionally specify the XSINIL option to map NULL column values in the result set to an element that has the attribute, xsi:nil=`"`true`"`.</span></span>  
  
 <span data-ttu-id="bdf8e-107">Vous pouvez demander un schéma pour les données XML résultantes.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-107">You can request a schema for the resulting XML.</span></span> <span data-ttu-id="bdf8e-108">Spécifier l'option XMLDATA permet de retourner un schéma XDR en ligne.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-108">Specifying the XMLDATA option returns an in-line XDR schema.</span></span> <span data-ttu-id="bdf8e-109">Spécifier l'option XMLSCHEMA permet de retourner un schéma XSD en ligne.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-109">Specifying the XMLSCHEMA option returns an in-line XSD schema.</span></span> <span data-ttu-id="bdf8e-110">Le schéma apparaît au début des données.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-110">The schema appears at the start of the data.</span></span> <span data-ttu-id="bdf8e-111">Dans le résultat, la référence à l'espace de noms du schéma est répétée pour chaque élément de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-111">In the result, the schema namespace reference is repeated for every top-level element.</span></span>  
  
 <span data-ttu-id="bdf8e-112">L'option BINARY BASE64 doit être spécifiée dans la clause FOR XML pour retourner les données binaires dans un format encodé en base 64.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-112">The BINARY BASE64 option must be specified in the FOR XML clause to return the binary data in base64-encoded format.</span></span> <span data-ttu-id="bdf8e-113">En mode RAW, la récupération de données binaires sans spécification de l'option BINARY BASE64 génère une erreur.</span><span class="sxs-lookup"><span data-stu-id="bdf8e-113">In RAW mode, retrieving binary data without specifying the BINARY BASE64 option will result in an error.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bdf8e-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="bdf8e-114">In This Section</span></span>  
 <span data-ttu-id="bdf8e-115">Cette section contient les exemples suivants :</span><span class="sxs-lookup"><span data-stu-id="bdf8e-115">This section contains the following examples:</span></span>  
  
-   [<span data-ttu-id="bdf8e-116">Exemple : Récupération des informations de modèle de produit au format XML</span><span class="sxs-lookup"><span data-stu-id="bdf8e-116">Example: Retrieving Product Model Information as XML</span></span>](example-retrieving-product-model-information-as-xml.md)  
  
-   [<span data-ttu-id="bdf8e-117">Exemple : Spécification de XSINIL avec la directive ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="bdf8e-117">Example: Specifying XSINIL with the ELEMENTS Directive</span></span>](example-specifying-xsinil-with-the-elements-directive.md)  
  
-   [<span data-ttu-id="bdf8e-118">Exemple : demande de schémas comme résultats à l'aide des options XMLDATA et XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="bdf8e-118">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>](example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options.md)  
  
-   [<span data-ttu-id="bdf8e-119">Exemple : Récupération de données binaires</span><span class="sxs-lookup"><span data-stu-id="bdf8e-119">Example: Retrieving Binary Data</span></span>](example-retrieving-binary-data.md)  
  
-   [<span data-ttu-id="bdf8e-120">Exemple : Renommage de l’élément &#60;row&#62;</span><span class="sxs-lookup"><span data-stu-id="bdf8e-120">Example: Renaming the &#60;row&#62; Element</span></span>](example-renaming-the-row-element.md)  
  
-   [<span data-ttu-id="bdf8e-121">Exemple : Spécification d’un élément racine pour les données XML générées par FOR XML</span><span class="sxs-lookup"><span data-stu-id="bdf8e-121">Example: Specifying a Root Element for the XML Generated by FOR XML</span></span>](example-specifying-a-root-element-for-the-xml-generated-by-for-xml.md)  
  
-   [<span data-ttu-id="bdf8e-122">Exemple : Interrogation de colonnes de type XML</span><span class="sxs-lookup"><span data-stu-id="bdf8e-122">Example: Querying XMLType Columns</span></span>](example-querying-xmltype-columns.md)  
  
## <a name="see-also"></a><span data-ttu-id="bdf8e-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bdf8e-123">See Also</span></span>  
 <span data-ttu-id="bdf8e-124">[Ajouter des espaces de noms aux requêtes avec WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span><span class="sxs-lookup"><span data-stu-id="bdf8e-124">[Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md) </span></span>  
 <span data-ttu-id="bdf8e-125">[UTiliser le mode AUTO avec FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="bdf8e-125">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="bdf8e-126">[Utiliser le mode EXPLICIT avec FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="bdf8e-126">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="bdf8e-127">[Utiliser le mode PATH avec FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="bdf8e-127">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="bdf8e-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="bdf8e-128">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="bdf8e-129">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bdf8e-129">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
