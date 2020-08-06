---
title: 'Spécification de l’attribut SQL : inverse sur SQL : Relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- bulk load [SQLXML]
- inverse attribute
- relationships [SQLXML], inverse orders
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- updategrams [SQLXML], relationships
- sql:inverse
ms.assetid: 08904cbd-9c86-493d-90c3-f5e1d13ce59d
author: rothja
ms.author: jroth
ms.openlocfilehash: 5b0781102371b98cced72a5a0edee70c9567c372
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605349"
---
# <a name="specifying-the-sqlinverse-attribute-on-sqlrelationship-sqlxml-40"></a><span data-ttu-id="f1a0f-102">Spécification de l'attribut sql:inverse sur sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f1a0f-102">Specifying the sql:inverse Attribute on sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="f1a0f-103">L'attribut `sql:inverse` est utile uniquement lorsque le schéma XSD est utilisé pour le chargement en masse ou par un code de mise à jour (updategram).</span><span class="sxs-lookup"><span data-stu-id="f1a0f-103">The `sql:inverse` attribute is useful only when the XSD schema is used for either bulk load or by an updategram.</span></span> <span data-ttu-id="f1a0f-104">L' `sql:inverse` attribut peut être spécifié sur l' **\<sql:relationship>** élément.</span><span class="sxs-lookup"><span data-stu-id="f1a0f-104">The `sql:inverse` attribute can be specified on the **\<sql:relationship>** element.</span></span> <span data-ttu-id="f1a0f-105">Dans les codes de mise à jour, la logique de code de mise à jour interprète le schéma pour déterminer les tables et colonnes mises à jour par l'opération de code de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f1a0f-105">In updategrams, the updategram logic interprets the schema in determining the tables and columns that are updated by the updategram operation.</span></span> <span data-ttu-id="f1a0f-106">Les relations parent-enfant spécifiées dans le schéma déterminent l'ordre dans lequel les enregistrements sont modifiés (insérés ou supprimés).</span><span class="sxs-lookup"><span data-stu-id="f1a0f-106">The parent-child relationships that are specified in the schema determine the order in which the records are modified (inserted or deleted).</span></span>  
  
 <span data-ttu-id="f1a0f-107">Si vous avez un schéma XSD dans lequel la relation parent-enfant est spécifiée dans l'ordre inverse de la relation clé primaire/clé étrangère entre les colonnes de base de données correspondantes, l'opération d'insertion ou de suppression du code de mise à jour échouera à cause de la violation de clé primaire/clé étrangère.</span><span class="sxs-lookup"><span data-stu-id="f1a0f-107">If you have an XSD schema in which the parent-child relationship is specified in the inverse order of the primary-key/foreign-key relationship between the corresponding database columns, the insert or delete updategram operation will fail because of the primary-key/foreign-key violation.</span></span> <span data-ttu-id="f1a0f-108">Dans ce cas, l' `sql:inverse` attribut est spécifié ( `sql:inverse="true"` ) dans l' **\<sql:relationship>** élément, et la logique mise à jour inverse son interprétation de la relation parent-enfant spécifiée dans le schéma.</span><span class="sxs-lookup"><span data-stu-id="f1a0f-108">In such cases, the `sql:inverse` attribute is specified (`sql:inverse="true"`) in the **\<sql:relationship>** element, and the updategram logic inverses its interpretation of the parent-child relationship specified in the schema.</span></span>  
  
 <span data-ttu-id="f1a0f-109">L'attribut `sql:inverse` prend une valeur booléenne (0=faux, 1=vrai).</span><span class="sxs-lookup"><span data-stu-id="f1a0f-109">The `sql:inverse` attribute takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="f1a0f-110">Les valeurs acceptables sont 0, 1, true et false.</span><span class="sxs-lookup"><span data-stu-id="f1a0f-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="f1a0f-111">Pour obtenir un exemple fonctionnel à l’aide de l' `sql:inverse` annotation, consultez [spécification d’un schéma de mappage annoté dans un mise à jour](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="f1a0f-111">For a working sample using the `sql:inverse` annotation, see [Specifying an Annotated Mapping Schema in an Updategram](../sqlxml-annotated-xsd-schemas-xpath-queries/updategrams/specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a0f-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f1a0f-112">See Also</span></span>  
 [<span data-ttu-id="f1a0f-113">Spécification de relations à l’aide de SQL : Relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f1a0f-113">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
  
  
