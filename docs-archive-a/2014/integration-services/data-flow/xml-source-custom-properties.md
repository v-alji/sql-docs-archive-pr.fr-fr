---
title: Propriétés personnalisées des sources XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eb29b28c-3159-41ec-b3d7-fce5b2f2be55
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5e152b23b4f59ca46cb8272ca677dc1161b3efec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613026"
---
# <a name="xml-source-custom-properties"></a><span data-ttu-id="434e3-102">Propriétés personnalisées des sources XML</span><span class="sxs-lookup"><span data-stu-id="434e3-102">XML Source Custom Properties</span></span>
  <span data-ttu-id="434e3-103">La source XML comporte des propriétés personnalisées et les propriétés communes à l'ensemble des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="434e3-103">The XML source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="434e3-104">Le tableau suivant décrit les propriétés personnalisées de la source XML.</span><span class="sxs-lookup"><span data-stu-id="434e3-104">The following table describes the custom properties of the XML source.</span></span> <span data-ttu-id="434e3-105">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="434e3-105">All properties are read/write.</span></span>  
  
|<span data-ttu-id="434e3-106">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="434e3-106">Property name</span></span>|<span data-ttu-id="434e3-107">Type de données</span><span class="sxs-lookup"><span data-stu-id="434e3-107">Data Type</span></span>|<span data-ttu-id="434e3-108">Description</span><span class="sxs-lookup"><span data-stu-id="434e3-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="434e3-109">AccessMode</span><span class="sxs-lookup"><span data-stu-id="434e3-109">AccessMode</span></span>|<span data-ttu-id="434e3-110">Integer</span><span class="sxs-lookup"><span data-stu-id="434e3-110">Integer</span></span>|<span data-ttu-id="434e3-111">Mode utilisé pour accéder aux données XML.</span><span class="sxs-lookup"><span data-stu-id="434e3-111">The mode used to access the XML data.</span></span>|  
|<span data-ttu-id="434e3-112">UseInlineSchema</span><span class="sxs-lookup"><span data-stu-id="434e3-112">UseInlineSchema</span></span>|<span data-ttu-id="434e3-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="434e3-113">Boolean</span></span>|<span data-ttu-id="434e3-114">Valeur qui indique si une définition de schéma inséré doit être utilisée dans la source XML.</span><span class="sxs-lookup"><span data-stu-id="434e3-114">A value that indicates whether to use an inline schema definition within the XML source.</span></span> <span data-ttu-id="434e3-115">La valeur par défaut de cette propriété est `False`.</span><span class="sxs-lookup"><span data-stu-id="434e3-115">The default value of this property is `False`.</span></span>|  
|<span data-ttu-id="434e3-116">XMLData</span><span class="sxs-lookup"><span data-stu-id="434e3-116">XMLData</span></span>|<span data-ttu-id="434e3-117">String</span><span class="sxs-lookup"><span data-stu-id="434e3-117">String</span></span>|<span data-ttu-id="434e3-118">Fichier ou variables à partir desquels les données XML sont extraites.</span><span class="sxs-lookup"><span data-stu-id="434e3-118">The file or variables from which to retrieve the XML data.</span></span><br /><br /> <span data-ttu-id="434e3-119">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="434e3-119">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="434e3-120">XMLSchemaDefinition</span><span class="sxs-lookup"><span data-stu-id="434e3-120">XMLSchemaDefinition</span></span>|<span data-ttu-id="434e3-121">String</span><span class="sxs-lookup"><span data-stu-id="434e3-121">String</span></span>|<span data-ttu-id="434e3-122">Chemin d'accès et nom de fichier du fichier de définition de schéma (.xsd).</span><span class="sxs-lookup"><span data-stu-id="434e3-122">The path and file name of the schema definition file (.xsd).</span></span><br /><br /> <span data-ttu-id="434e3-123">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="434e3-123">The value of this property can be specified by using a property expression.</span></span>|  
  
 <span data-ttu-id="434e3-124">Le tableau suivant décrit les propriétés personnalisées de la sortie de la source XML.</span><span class="sxs-lookup"><span data-stu-id="434e3-124">The following table describes the custom properties of the output of the XML source.</span></span> <span data-ttu-id="434e3-125">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="434e3-125">All properties are read/write.</span></span>  
  
|<span data-ttu-id="434e3-126">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="434e3-126">Property name</span></span>|<span data-ttu-id="434e3-127">Type de données</span><span class="sxs-lookup"><span data-stu-id="434e3-127">Data Type</span></span>|<span data-ttu-id="434e3-128">Description</span><span class="sxs-lookup"><span data-stu-id="434e3-128">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="434e3-129">RowsetID</span><span class="sxs-lookup"><span data-stu-id="434e3-129">RowsetID</span></span>|<span data-ttu-id="434e3-130">String</span><span class="sxs-lookup"><span data-stu-id="434e3-130">String</span></span>|<span data-ttu-id="434e3-131">Valeur qui identifie l'ensemble de lignes associé à la sortie.</span><span class="sxs-lookup"><span data-stu-id="434e3-131">A value that identifies the rowset associated with the output.</span></span>|  
  
 <span data-ttu-id="434e3-132">Les colonnes de sortie de la source XML ne possèdent pas de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="434e3-132">The output columns of the XML source have no custom properties.</span></span>  
  
 <span data-ttu-id="434e3-133">Pour plus d'informations, consultez [XML Source](xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="434e3-133">For more information, see [XML Source](xml-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="434e3-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="434e3-134">See Also</span></span>  
 [<span data-ttu-id="434e3-135">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="434e3-135">Common Properties</span></span>](../common-properties.md)  
  
  
