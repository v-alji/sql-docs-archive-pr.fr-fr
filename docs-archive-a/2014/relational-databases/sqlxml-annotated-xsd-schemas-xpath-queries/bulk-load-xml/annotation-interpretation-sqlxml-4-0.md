---
title: Interprétation des annotations (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, XML Bulk Load
- XML Bulk Load [SQLXML], annotation intepretations
- annotations [SQLXML]
- bulk load [SQLXML], annotation interpretations
- annotated XDR schemas, XML Bulk Load
ms.assetid: 1c46bdb6-2812-4a13-b60b-7101c04b299f
author: rothja
ms.author: jroth
ms.openlocfilehash: c31d56f7dd577b4b5a5b582eb0e3b1db312109a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611709"
---
# <a name="annotation-interpretation-sqlxml-40"></a><span data-ttu-id="ac734-102">Interprétation d'annotation (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="ac734-102">Annotation Interpretation (SQLXML 4.0)</span></span>
  <span data-ttu-id="ac734-103">Les rubriques de cette section décrivent comment le chargement en masse XML interprète les annotations dans le schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="ac734-103">The topics in this section describe how XML Bulk Load interprets annotations in the XSD schema.</span></span> <span data-ttu-id="ac734-104">Le comportement décrit ici s'applique également aux annotations dans le schéma XDR.</span><span class="sxs-lookup"><span data-stu-id="ac734-104">The behavior described here also applies to the annotations in the XDR schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ac734-105">Les informations fournies dans ces rubriques décrivent uniquement les annotations utilisées par le chargement en masse XML lors de son traitement.</span><span class="sxs-lookup"><span data-stu-id="ac734-105">The information in these topics describes only the annotations used by XML Bulk Load in its processing.</span></span> <span data-ttu-id="ac734-106">Pour obtenir la liste complète des annotations pour le schéma XSD prises en charge par SQLXML 4,0, consultez [utilisation des annotations dans les schémas xsd &#40;sqlxml 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ac734-106">For a complete list of annotations for the XSD schema that are supported by SQLXML 4.0, see [Using Annotations in XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/using-annotations-in-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="ac734-107">Pour obtenir la liste des annotations prises en charge pour les schémas XDR, consultez [schémas XDR Annotés &#40;dépréciés dans SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="ac734-107">For a list of supported annotations for XDR schemas, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ac734-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="ac734-108">In This Section</span></span>  
 [<span data-ttu-id="ac734-109">SQL : Relationship et la règle de classement des clés &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ac734-109">sql:relationship and the Key Ordering Rule &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-relationship-and-key-ordering-rule.md)  
 <span data-ttu-id="ac734-110">Décrit comment l'annotation `sql:relationship` est interprétée dans le chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="ac734-110">Describes how the `sql:relationship` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ac734-111">SQL : mappé &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ac734-111">sql:mapped &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-mapped.md)  
 <span data-ttu-id="ac734-112">Décrit comment l'annotation `sql:mapped` est interprétée dans le chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="ac734-112">Describes how the `sql:mapped` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ac734-113">SQL : Limit-Field et SQL : limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ac734-113">sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="ac734-114">Décrit comment les annotations `sql:limit-field` et `sql:limit-value` sont interprétées dans le chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="ac734-114">Describes how the `sql:limit-field` and `sql:limit-value` annotations are interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ac734-115">SQL : overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ac734-115">sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="ac734-116">Décrit comment l'annotation `sql:overflow` est interprétée dans le chargement en masse XML.</span><span class="sxs-lookup"><span data-stu-id="ac734-116">Describes how the `sql:overflow` annotation is interpreted in XML Bulk Load.</span></span>  
  
 [<span data-ttu-id="ac734-117">Autres annotations &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="ac734-117">Other Annotations &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-other-annotations.md)  
 <span data-ttu-id="ac734-118">Décrit comment les annotations suivantes sont interprétées dans le chargement en masse XML :  `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="ac734-118">Describes how the following annotations are interpreted in XML Bulk Load: `sql:id-prefix`, `sql:use-cdata`, `sql:url-encode`, `sql:is-mapping-schema`, `sql:key-fields`.</span></span>  
  
  
