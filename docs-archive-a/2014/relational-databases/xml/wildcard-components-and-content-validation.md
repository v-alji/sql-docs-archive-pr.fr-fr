---
title: Composants génériques et validation de contenu | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- wildcard components [XML]
- content validation [XML]
ms.assetid: ffa7d974-3645-446c-8425-f0b22b6b060a
author: rothja
ms.author: jroth
ms.openlocfilehash: 76ff2b48efb8cff0b98827fe8522405682c294e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602001"
---
# <a name="wildcard-components-and-content-validation"></a><span data-ttu-id="506e6-102">Composants génériques et validation de contenu</span><span class="sxs-lookup"><span data-stu-id="506e6-102">Wildcard Components and Content Validation</span></span>
  <span data-ttu-id="506e6-103">Les composants génériques sont utilisés pour accroître la flexibilité en termes d'éléments pouvant apparaître dans un modèle de contenu.</span><span class="sxs-lookup"><span data-stu-id="506e6-103">Wildcard components are used to increase flexibility in what is allowed to appear in a content model.</span></span> <span data-ttu-id="506e6-104">Ils sont pris en charge comme suit dans le langage XSD :</span><span class="sxs-lookup"><span data-stu-id="506e6-104">These components are supported in the XSD language in the following ways:</span></span>  
  
-   <span data-ttu-id="506e6-105">Composants génériques éléments.</span><span class="sxs-lookup"><span data-stu-id="506e6-105">Element wildcard components.</span></span> <span data-ttu-id="506e6-106">Ils sont représentés par l'élément **\<xsd:any>** .</span><span class="sxs-lookup"><span data-stu-id="506e6-106">These are represented by the **\<xsd:any>** element.</span></span>  
  
-   <span data-ttu-id="506e6-107">Composants génériques attributs.</span><span class="sxs-lookup"><span data-stu-id="506e6-107">Attribute wildcard components.</span></span> <span data-ttu-id="506e6-108">Ils sont représentés par l'élément **\<xsd:anyAttribute>** .</span><span class="sxs-lookup"><span data-stu-id="506e6-108">These are represented by the **\<xsd:anyAttribute>** element.</span></span>  
  
 <span data-ttu-id="506e6-109">Ces deux types de caractères génériques, **\<xsd:any>** et **\<xsd:anyAttribute>** , prennent en charge l'emploi d'un attribut **processContents**.</span><span class="sxs-lookup"><span data-stu-id="506e6-109">Both wildcard character elements, **\<xsd:any>** and **\<xsd:anyAttribute>**, support the use of a **processContents** attribute.</span></span> <span data-ttu-id="506e6-110">Grâce à lui, vous pouvez préciser une valeur indiquant comment les applications XML vont gérer la validation du contenu des documents associé à ces éléments de caractères génériques.</span><span class="sxs-lookup"><span data-stu-id="506e6-110">This lets you specify a value that indicates how XML applications handle the validation of document content associated with these wildcard character elements.</span></span> <span data-ttu-id="506e6-111">Les valeurs possibles et leurs effets sont décrits ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="506e6-111">These are the different values and their effect:</span></span>  
  
-   <span data-ttu-id="506e6-112">La valeur **strict** indique que le contenu est entièrement validé.</span><span class="sxs-lookup"><span data-stu-id="506e6-112">The **strict** value specifies that the contents are fully validated.</span></span>  
  
-   <span data-ttu-id="506e6-113">La valeur **skip** indique que le contenu n'est pas validé.</span><span class="sxs-lookup"><span data-stu-id="506e6-113">The **skip** value specifies that the contents are not validated.</span></span>  
  
-   <span data-ttu-id="506e6-114">La valeur **lax** indique que sont validés uniquement les éléments et les attributs pour lesquels des définitions de schéma sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="506e6-114">The **lax** value specifies that only elements and attributes for which schema definitions are available are validated.</span></span>  
  
## <a name="lax-validation-and-xsanytype-elements"></a><span data-ttu-id="506e6-115">Validation de type lax et éléments xs:anyType</span><span class="sxs-lookup"><span data-stu-id="506e6-115">Lax Validation and xs:anyType Elements</span></span>  
 <span data-ttu-id="506e6-116">La spécification de schéma XML utilise la validation de type **lax** pour les éléments du type **anyType** .</span><span class="sxs-lookup"><span data-stu-id="506e6-116">The XML Schema specification uses **lax** validation for elements of the **anyType** type.</span></span> <span data-ttu-id="506e6-117">Étant donné que [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] ne prenait pas en charge la validation de type lax, la validation de type strict était appliquée aux éléments de type **anyType**.</span><span class="sxs-lookup"><span data-stu-id="506e6-117">Because [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] did not support lax validation, strict validation was applied for elements of the **anyType**.</span></span> <span data-ttu-id="506e6-118">À compter de [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], la validation de type lax est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="506e6-118">Beginning with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], lax validation is supported.</span></span> <span data-ttu-id="506e6-119">Le contenu des éléments de type **anyType** sera validé à l'aide de la validation de type lax.</span><span class="sxs-lookup"><span data-stu-id="506e6-119">Content of elements of type **anyType** will be validated using lax validation.</span></span>  
  
 <span data-ttu-id="506e6-120">L'exemple suivant illustre la validation de type lax.</span><span class="sxs-lookup"><span data-stu-id="506e6-120">The following example illustrates the lax validation.</span></span> <span data-ttu-id="506e6-121">L'élément de schéma `e` est de type **anyType** .</span><span class="sxs-lookup"><span data-stu-id="506e6-121">The schema element `e` is of the **anyType** type.</span></span> <span data-ttu-id="506e6-122">L'exemple crée des variables **xml** typées et illustre la validation de type lax de l'élément de type **anyType** .</span><span class="sxs-lookup"><span data-stu-id="506e6-122">The example creates typed **xml** variables and illustrates the lax validation of the element of the **anyType** type.</span></span>  
  
```  
CREATE XML SCHEMA COLLECTION SC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema"   
        targetNamespace="http://ns">  
   <element name="e" type="anyType"/>  
   <element name="a" type="byte"/>  
   <element name="b" type="string"/>  
 </schema>'  
GO  
```  
  
 <span data-ttu-id="506e6-123">L'exemple ci-dessous aboutit, car la validation de `<e>` réussit.</span><span class="sxs-lookup"><span data-stu-id="506e6-123">The following example succeeds, because the validation of `<e>` is successful:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="506e6-124">L'exemple ci-dessous aboutit.</span><span class="sxs-lookup"><span data-stu-id="506e6-124">The following example succeeds.</span></span> <span data-ttu-id="506e6-125">L'instance est acceptée, bien qu'aucun élément `<c>` ne soit défini dans le schéma :</span><span class="sxs-lookup"><span data-stu-id="506e6-125">The instance is accepted, even though no element `<c>` is defined in the schema:</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>1</a><c>Wrong</c><b>data</b></e>'  
GO  
```  
  
 <span data-ttu-id="506e6-126">L'instance XML dans l'exemple suivant est rejetée car la définition de l'élément `<a>` n'autorise pas de valeur de chaîne.</span><span class="sxs-lookup"><span data-stu-id="506e6-126">The XML instance in the following example is rejected, because the definition of the `<a>` element does not allow a string value.</span></span>  
  
```  
DECLARE @var XML(SC)  
SET @var = '<e xmlns="http://ns"><a>Wrong</a><b>data</b></e>'  
SELECT @var  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="506e6-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="506e6-127">See Also</span></span>  
 [<span data-ttu-id="506e6-128">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="506e6-128">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
