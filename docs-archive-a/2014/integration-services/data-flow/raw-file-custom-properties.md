---
title: Propriétés personnalisées des fichiers bruts | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7e81f7e1-fac0-4b57-b145-8f1b9e4720bf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7614c03fbf44f37597e586549e306d01c28b523d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602918"
---
# <a name="raw-file-custom-properties"></a><span data-ttu-id="29e7c-102">Propriétés personnalisées des fichiers bruts</span><span class="sxs-lookup"><span data-stu-id="29e7c-102">Raw File Custom Properties</span></span>
  <span data-ttu-id="29e7c-103">**Propriétés personnalisées des sources**</span><span class="sxs-lookup"><span data-stu-id="29e7c-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="29e7c-104">La source de fichier brut comporte des propriétés personnalisées et les propriétés communes à l'ensemble des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="29e7c-104">The Raw File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="29e7c-105">Le tableau suivant décrit les propriétés personnalisées de la source de fichier brut.</span><span class="sxs-lookup"><span data-stu-id="29e7c-105">The following table describes the custom properties of the Raw File source.</span></span> <span data-ttu-id="29e7c-106">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="29e7c-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="29e7c-107">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="29e7c-107">Property name</span></span>|<span data-ttu-id="29e7c-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="29e7c-108">Data Type</span></span>|<span data-ttu-id="29e7c-109">Description</span><span class="sxs-lookup"><span data-stu-id="29e7c-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="29e7c-110">AccessMode</span><span class="sxs-lookup"><span data-stu-id="29e7c-110">AccessMode</span></span>|<span data-ttu-id="29e7c-111">Integer (énumération)</span><span class="sxs-lookup"><span data-stu-id="29e7c-111">Integer (enumeration)</span></span>|<span data-ttu-id="29e7c-112">Mode utilisé pour accéder aux données brutes.</span><span class="sxs-lookup"><span data-stu-id="29e7c-112">The mode used to access the raw data.</span></span> <span data-ttu-id="29e7c-113">Les valeurs possibles sont `File name` (0) et `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="29e7c-113">The possible values are `File name` (0) and `File name from variable` (1).</span></span> <span data-ttu-id="29e7c-114">La valeur par défaut est `File name` (0).</span><span class="sxs-lookup"><span data-stu-id="29e7c-114">The default value is `File name` (0).</span></span>|  
|<span data-ttu-id="29e7c-115">FileName</span><span class="sxs-lookup"><span data-stu-id="29e7c-115">FileName</span></span>|<span data-ttu-id="29e7c-116">String</span><span class="sxs-lookup"><span data-stu-id="29e7c-116">String</span></span>|<span data-ttu-id="29e7c-117">Chemin d'accès et nom de fichier du fichier source.</span><span class="sxs-lookup"><span data-stu-id="29e7c-117">The path and file name of the source file.</span></span>|  
  
 <span data-ttu-id="29e7c-118">La sortie et les colonnes de sortie de la source de fichier brut ne disposent pas de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="29e7c-118">The output and the output columns of the Raw File source have no custom properties.</span></span>  
  
 <span data-ttu-id="29e7c-119">Pour plus d’informations, consultez [Source de fichier brut](raw-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="29e7c-119">For more information, see [Raw File Source](raw-file-source.md).</span></span>  
  
 <span data-ttu-id="29e7c-120">**Propriétés personnalisées des destinations**</span><span class="sxs-lookup"><span data-stu-id="29e7c-120">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="29e7c-121">La destination de fichier brut comporte à la fois des propriétés personnalisées et les propriétés communes à l'ensemble des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="29e7c-121">The Raw File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="29e7c-122">Le tableau suivant décrit les propriétés personnalisées de la destination de fichier brut.</span><span class="sxs-lookup"><span data-stu-id="29e7c-122">The following table describes the custom properties of the Raw File destination.</span></span> <span data-ttu-id="29e7c-123">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="29e7c-123">All properties are read/write.</span></span>  
  
|<span data-ttu-id="29e7c-124">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="29e7c-124">Property name</span></span>|<span data-ttu-id="29e7c-125">Type de données</span><span class="sxs-lookup"><span data-stu-id="29e7c-125">Data Type</span></span>|<span data-ttu-id="29e7c-126">Description</span><span class="sxs-lookup"><span data-stu-id="29e7c-126">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="29e7c-127">AccessMode</span><span class="sxs-lookup"><span data-stu-id="29e7c-127">AccessMode</span></span>|<span data-ttu-id="29e7c-128">Integer (énumération)</span><span class="sxs-lookup"><span data-stu-id="29e7c-128">Integer (enumeration)</span></span>|<span data-ttu-id="29e7c-129">Valeur qui indique si la propriété FileName contient un nom de fichier ou le nom d’une variable qui contient un nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="29e7c-129">A value that specifies whether the FileName property contains a file name, or the name of a variable that contains a file name.</span></span> <span data-ttu-id="29e7c-130">Les options disponibles sont `File name` (0) et `File name from variable` (1).</span><span class="sxs-lookup"><span data-stu-id="29e7c-130">The options are `File name` (0) and `File name from variable` (1).</span></span>|  
|<span data-ttu-id="29e7c-131">FileName</span><span class="sxs-lookup"><span data-stu-id="29e7c-131">FileName</span></span>|<span data-ttu-id="29e7c-132">String</span><span class="sxs-lookup"><span data-stu-id="29e7c-132">String</span></span>|<span data-ttu-id="29e7c-133">Nom du fichier dans lequel la destination de fichier brut écrit.</span><span class="sxs-lookup"><span data-stu-id="29e7c-133">The name of the file to which the Raw File destination writes.</span></span>|  
|<span data-ttu-id="29e7c-134">WriteOption</span><span class="sxs-lookup"><span data-stu-id="29e7c-134">WriteOption</span></span>|<span data-ttu-id="29e7c-135">Integer (énumération)</span><span class="sxs-lookup"><span data-stu-id="29e7c-135">Integer (enumeration)</span></span>|<span data-ttu-id="29e7c-136">Valeur qui spécifie si la destination de fichier brut supprime un fichier existant qui porte le même nom.</span><span class="sxs-lookup"><span data-stu-id="29e7c-136">A value that specifies whether the Raw File destination deletes an existing file that has the same name.</span></span> <span data-ttu-id="29e7c-137">Les options disponibles sont `Create Always` (0), `Create Once` (1), `Truncate and Append` (3) et `Append` (2).</span><span class="sxs-lookup"><span data-stu-id="29e7c-137">The options are `Create Always` (0), `Create Once` (1), `Truncate and Append` (3), and `Append` (2).</span></span> <span data-ttu-id="29e7c-138">La valeur par défaut de cette propriété est `Create Always` (0).</span><span class="sxs-lookup"><span data-stu-id="29e7c-138">The default value of this property is `Create Always` (0).</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="29e7c-139">Une opération d'ajout exige que les métadonnées des données ajoutées correspondent à celles des données déjà présentes dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="29e7c-139">An append operation requires the metadata of the appended data to match the metadata of the data already present in the file.</span></span>  
  
 <span data-ttu-id="29e7c-140">L'entrée et les colonnes d'entrée de la destination de fichier brut ne disposent pas de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="29e7c-140">The input and the input columns of the Raw File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="29e7c-141">Pour plus d’informations, consultez [Destination de fichier brut](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="29e7c-141">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e7c-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29e7c-142">See Also</span></span>  
 [<span data-ttu-id="29e7c-143">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="29e7c-143">Common Properties</span></span>](../common-properties.md)  
  
  
