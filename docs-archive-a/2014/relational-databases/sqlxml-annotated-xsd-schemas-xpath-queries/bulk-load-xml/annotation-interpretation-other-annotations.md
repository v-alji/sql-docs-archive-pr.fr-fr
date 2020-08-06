---
title: Autres annotations (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- url-encode annotation
- sql:key-fields
- use-cdata annotation
- sql:is-mapping-schema
- sql:url-encode
- sql:id-prefix
- sql:use-cdata
- key-fields annotation
- id-prefix annotation [SQLXML]
- is-mapping-schema annotation
ms.assetid: f7b4d37b-d6d3-4ac3-b2fd-a0b534a924e4
author: rothja
ms.author: jroth
ms.openlocfilehash: b654568c93df0a0c3e08cf6eaa615b7026a9c18a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605337"
---
# <a name="other-annotations-sqlxml-40"></a><span data-ttu-id="e7495-102">Autres annotations (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e7495-102">Other Annotations (SQLXML 4.0)</span></span>
  <span data-ttu-id="e7495-103">Outre les annotations présentées dans les rubriques précédentes de cette section, le chargement en masse XML interprète les annotations suivantes, comme suit :</span><span class="sxs-lookup"><span data-stu-id="e7495-103">In addition to the annotations discussed in the previous topics in this section, XML Bulk Load interprets these other annotations, as follows:</span></span>  
  
 `sql:id-prefix`  
 <span data-ttu-id="e7495-104">Si conformément au schéma, des préfixes sont ajoutés aux données XML, le chargement en masse XML supprime ces préfixes avant d'envoyer les données à Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7495-104">If the schema specifies prefixes to the XML data, XML Bulk Load removes the prefixes before sending the data to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:use-cdata`  
 <span data-ttu-id="e7495-105">Le chargement en masse XML lit le texte qui est stocké dans les sections CDATA et l'envoie à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e7495-105">XML Bulk Load reads the text that is stored in the CDATA sections and sends it to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 `sql:url-encode`  
 <span data-ttu-id="e7495-106">Le chargement en masse XML ne prend pas en charge cette annotation.</span><span class="sxs-lookup"><span data-stu-id="e7495-106">XML Bulk Load does not support this annotation.</span></span> <span data-ttu-id="e7495-107">Par exemple, vous ne pouvez pas spécifier une URL dans l'entrée de données XML et vous attendre à ce que le chargement en masse XML lise les données à cet emplacement et les stocke dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="e7495-107">For example, you cannot specify a URL in the XML data input and expect XML Bulk Load to read data from that location to store it in the database.</span></span>  
  
 `sql:is-mapping-schema`  
 <span data-ttu-id="e7495-108">Le chargement en masse XML ne prend pas en charge cette annotation, ni `sql:id`.</span><span class="sxs-lookup"><span data-stu-id="e7495-108">XML Bulk Load does not support this annotation, nor does it support `sql:id`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e7495-109">Le chargement en masse XML ne prend pas en charge les schémas de mappage insérés.</span><span class="sxs-lookup"><span data-stu-id="e7495-109">XML Bulk Load does not support inline mapping schemas.</span></span>  
  
 `sql:key-fields`  
 <span data-ttu-id="e7495-110">Le chargement en masse XML ignore toujours cette annotation.</span><span class="sxs-lookup"><span data-stu-id="e7495-110">XML Bulk Load always ignores this annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7495-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e7495-111">See Also</span></span>  
 [<span data-ttu-id="e7495-112">Interprétation des annotations &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e7495-112">Annotation Interpretation &#40;SQLXML 4.0&#41;</span></span>](annotation-interpretation-sqlxml-4-0.md)  
  
  
