---
title: Propriétés personnalisées des fichiers plats | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7f2caeab-784c-4b0c-9b3e-6a88d1ccdbf9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b906e9268bf3a74ffcf5661953397ad7a24b77a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709780"
---
# <a name="flat-file-custom-properties"></a><span data-ttu-id="03ff9-102">Propriétés personnalisées des fichiers plats</span><span class="sxs-lookup"><span data-stu-id="03ff9-102">Flat File Custom Properties</span></span>
  <span data-ttu-id="03ff9-103">**Propriétés personnalisées des sources**</span><span class="sxs-lookup"><span data-stu-id="03ff9-103">**Source Custom Properties**</span></span>  
  
 <span data-ttu-id="03ff9-104">La source de fichier plat comporte des propriétés personnalisées et les propriétés communes à l'ensemble des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="03ff9-104">The Flat File source has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="03ff9-105">Le tableau suivant décrit les propriétés personnalisées de la source de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="03ff9-105">The following table describes the custom properties of the Flat File source.</span></span> <span data-ttu-id="03ff9-106">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="03ff9-106">All properties are read/write.</span></span>  
  
|<span data-ttu-id="03ff9-107">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="03ff9-107">Property name</span></span>|<span data-ttu-id="03ff9-108">Type de données</span><span class="sxs-lookup"><span data-stu-id="03ff9-108">Data Type</span></span>|<span data-ttu-id="03ff9-109">Description</span><span class="sxs-lookup"><span data-stu-id="03ff9-109">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="03ff9-110">FileNameColumnName</span><span class="sxs-lookup"><span data-stu-id="03ff9-110">FileNameColumnName</span></span>|<span data-ttu-id="03ff9-111">String</span><span class="sxs-lookup"><span data-stu-id="03ff9-111">String</span></span>|<span data-ttu-id="03ff9-112">Nom d'une colonne de sortie qui contient le nom de fichier.</span><span class="sxs-lookup"><span data-stu-id="03ff9-112">The name of an output column that contains the file name.</span></span> <span data-ttu-id="03ff9-113">Si le nom n'est pas spécifié, aucune colonne de sortie contenant le nom de fichier ne sera générée.</span><span class="sxs-lookup"><span data-stu-id="03ff9-113">If no name is specified, no output column containing the file name will be generated.</span></span><br /><br /> <span data-ttu-id="03ff9-114">Remarque : cette propriété n’est pas disponible dans **l’Éditeur de source de fichier plat**, mais elle peut être définie à l’aide de **l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="03ff9-114">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
|<span data-ttu-id="03ff9-115">RetainNulls</span><span class="sxs-lookup"><span data-stu-id="03ff9-115">RetainNulls</span></span>|<span data-ttu-id="03ff9-116">Boolean</span><span class="sxs-lookup"><span data-stu-id="03ff9-116">Boolean</span></span>|<span data-ttu-id="03ff9-117">Valeur qui spécifie si les valeurs NULL du fichier source doivent être conservées comme valeurs NULL lorsque les données sont traitées par le moteur du pipeline de transformation des données.</span><span class="sxs-lookup"><span data-stu-id="03ff9-117">A value that specifies whether to retain Null values from the source file as Null values when the data is processed by the Data Transformation Pipeline engine.</span></span> <span data-ttu-id="03ff9-118">La valeur par défaut de cette propriété est `False`.</span><span class="sxs-lookup"><span data-stu-id="03ff9-118">The default value of this property is `False`.</span></span>|  
  
 <span data-ttu-id="03ff9-119">La sortie de la source de fichier plat n'est pas dotée de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="03ff9-119">The output of the Flat File source has no custom properties.</span></span>  
  
 <span data-ttu-id="03ff9-120">Le tableau suivant décrit les propriétés personnalisées des colonnes de sortie de la source de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="03ff9-120">The following table describes the custom properties of the output columns of the Flat File source.</span></span> <span data-ttu-id="03ff9-121">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="03ff9-121">All properties are read/write.</span></span>  
  
|<span data-ttu-id="03ff9-122">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="03ff9-122">Property name</span></span>|<span data-ttu-id="03ff9-123">Type de données</span><span class="sxs-lookup"><span data-stu-id="03ff9-123">Data Type</span></span>|<span data-ttu-id="03ff9-124">Description</span><span class="sxs-lookup"><span data-stu-id="03ff9-124">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="03ff9-125">FastParse</span><span class="sxs-lookup"><span data-stu-id="03ff9-125">FastParse</span></span>|<span data-ttu-id="03ff9-126">Boolean</span><span class="sxs-lookup"><span data-stu-id="03ff9-126">Boolean</span></span>|<span data-ttu-id="03ff9-127">Valeur qui indique si la colonne utilise les routines d'analyse fournies par DTS (routines plus rapides mais qui ne tiennent pas compte des paramètres régionaux) ou les routines d'analyse standard qui tiennent compte des paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="03ff9-127">A value that indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that DTS provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="03ff9-128">Pour plus d'informations, consultez [Fast Parse](../fast-parse.md) et [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="03ff9-128">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span> <span data-ttu-id="03ff9-129">La valeur par défaut de cette propriété est `False`.</span><span class="sxs-lookup"><span data-stu-id="03ff9-129">The default value of this property is `False`.</span></span><br /><br /> <span data-ttu-id="03ff9-130">Remarque : cette propriété n’est pas disponible dans **l’Éditeur de source de fichier plat**, mais elle peut être définie à l’aide de **l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="03ff9-130">Note: This property is not available in the **Flat File Source Editor**, but can be set by using the **Advanced Editor**.</span></span>|  
  
 <span data-ttu-id="03ff9-131">Pour plus d'informations, consultez [Flat File Source](flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="03ff9-131">For more information, see [Flat File Source](flat-file-source.md).</span></span>  
  
 <span data-ttu-id="03ff9-132">**Propriétés personnalisées des destinations**</span><span class="sxs-lookup"><span data-stu-id="03ff9-132">**Destination Custom Properties**</span></span>  
  
 <span data-ttu-id="03ff9-133">La destination de fichier plat comporte à la fois des propriétés personnalisées et les propriétés communes à l'ensemble des composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="03ff9-133">The Flat File destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="03ff9-134">Le tableau suivant décrit les propriétés personnalisées de la destination de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="03ff9-134">The following table describes the custom properties of the Flat File destination.</span></span> <span data-ttu-id="03ff9-135">Toutes les propriétés sont en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="03ff9-135">All properties are read/write.</span></span>  
  
|<span data-ttu-id="03ff9-136">Nom de la propriété</span><span class="sxs-lookup"><span data-stu-id="03ff9-136">Property name</span></span>|<span data-ttu-id="03ff9-137">Type de données</span><span class="sxs-lookup"><span data-stu-id="03ff9-137">Data Type</span></span>|<span data-ttu-id="03ff9-138">Description</span><span class="sxs-lookup"><span data-stu-id="03ff9-138">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="03ff9-139">En-tête</span><span class="sxs-lookup"><span data-stu-id="03ff9-139">Header</span></span>|<span data-ttu-id="03ff9-140">String</span><span class="sxs-lookup"><span data-stu-id="03ff9-140">String</span></span>|<span data-ttu-id="03ff9-141">Bloc de texte inséré dans le fichier avant l'écriture des données.</span><span class="sxs-lookup"><span data-stu-id="03ff9-141">A block of text that is inserted in the file before any data is written.</span></span><br /><br /> <span data-ttu-id="03ff9-142">Il est possible de spécifier la valeur de cette propriété en utilisant l'expression d'une propriété.</span><span class="sxs-lookup"><span data-stu-id="03ff9-142">The value of this property can be specified by using a property expression.</span></span>|  
|<span data-ttu-id="03ff9-143">Remplacer</span><span class="sxs-lookup"><span data-stu-id="03ff9-143">Overwrite</span></span>|<span data-ttu-id="03ff9-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="03ff9-144">Boolean</span></span>|<span data-ttu-id="03ff9-145">Valeur qui spécifie s'il faut remplacer un fichier de destination existant qui porte le même nom ou lui ajouter des données.</span><span class="sxs-lookup"><span data-stu-id="03ff9-145">A value that specifies whether to overwrite or append to an existing destination file that has the same name.</span></span> <span data-ttu-id="03ff9-146">La valeur par défaut de cette propriété est `True`.</span><span class="sxs-lookup"><span data-stu-id="03ff9-146">The default value of this property is `True`.</span></span>|  
  
 <span data-ttu-id="03ff9-147">L'entrée et les colonnes d'entrée de la destination de fichier plat ne disposent pas de propriétés personnalisées.</span><span class="sxs-lookup"><span data-stu-id="03ff9-147">The input and the input columns of the Flat File destination have no custom properties.</span></span>  
  
 <span data-ttu-id="03ff9-148">Pour plus d'informations, consultez [Flat File Destination](flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="03ff9-148">For more information, see [Flat File Destination](flat-file-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ff9-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="03ff9-149">See Also</span></span>  
 [<span data-ttu-id="03ff9-150">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="03ff9-150">Common Properties</span></span>](../common-properties.md)  
  
  
