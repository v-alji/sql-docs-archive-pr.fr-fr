---
title: Source de fichier plat | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Flat File
- text file reading [Integration Services]
- flat files
- Flat File source
ms.assetid: 4a64f7f3-f25d-4db0-93b3-a29496030e58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b1ca0f38c457256b3f2ed2ddb81bfbd0dc06b6c0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709776"
---
# <a name="flat-file-source"></a><span data-ttu-id="ab60a-102">Source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="ab60a-102">Flat File Source</span></span>
  <span data-ttu-id="ab60a-103">La source de fichier plat lit des données figurant dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="ab60a-103">The Flat File source reads data from a text file.</span></span> <span data-ttu-id="ab60a-104">Le fichier texte peut être d'un format délimité, à largeur fixe ou mixte.</span><span class="sxs-lookup"><span data-stu-id="ab60a-104">The text file can be in delimited, fixed width, or mixed format.</span></span>  
  
-   <span data-ttu-id="ab60a-105">Le format délimité utilise des séparateurs de colonnes et de lignes pour définir les colonnes et les lignes.</span><span class="sxs-lookup"><span data-stu-id="ab60a-105">Delimited format uses column and row delimiters to define columns and rows.</span></span>  
  
-   <span data-ttu-id="ab60a-106">Le format de largeur fixe utilise la largeur pour définir les colonnes et les lignes.</span><span class="sxs-lookup"><span data-stu-id="ab60a-106">Fixed width format uses width to define columns and rows.</span></span> <span data-ttu-id="ab60a-107">Ce format comprend également un caractère qui permet de remplir les champs dans la limite de leur largeur maximale.</span><span class="sxs-lookup"><span data-stu-id="ab60a-107">This format also includes a character for padding fields to their maximum width.</span></span>  
  
-   <span data-ttu-id="ab60a-108">Le format non justifié à droite utilise la largeur pour définir toutes les colonnes, à l'exception de la dernière colonne, qui est délimitée par le séparateur de lignes.</span><span class="sxs-lookup"><span data-stu-id="ab60a-108">Ragged right format uses width to define all columns, except for the last column, which is delimited by the row delimiter.</span></span>  
  
 <span data-ttu-id="ab60a-109">Vous pouvez configurer la source de fichier plat comme suit :</span><span class="sxs-lookup"><span data-stu-id="ab60a-109">You can configure the Flat File source in the following ways:</span></span>  
  
-   <span data-ttu-id="ab60a-110">Ajoutez une colonne à la sortie de transformation qui contient le nom du fichier texte dont la source de fichier plat extrait les données.</span><span class="sxs-lookup"><span data-stu-id="ab60a-110">Add a column to the transformation output that contains the name of the text file from which the Flat File source extracts data.</span></span>  
  
-   <span data-ttu-id="ab60a-111">Spécifiez si la source de fichier plat interprète les chaînes nulles dans les colonnes en tant que valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="ab60a-111">Specify whether the Flat File source interprets zero-length strings in columns as null values.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ab60a-112">Le gestionnaire de connexions de fichiers plats utilisé par la source de fichier plat doit être configuré de manière à utiliser un format délimité, afin qu'il puisse interpréter les chaînes de longueur nulle en tant que valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="ab60a-112">The Flat File connection manager that the Flat File source uses must be configured to use a delimited format to interpret zero-length strings as nulls.</span></span> <span data-ttu-id="ab60a-113">Si le gestionnaire de connexions utilise le format à largeur fixe ou non justifié à droite, les données composées d'espaces ne peuvent pas être interprétées comme des valeurs NULL.</span><span class="sxs-lookup"><span data-stu-id="ab60a-113">If the connection manager uses the fixed width or ragged right formats, data that consists of spaces cannot be interpreted as null values.</span></span>  
  
 <span data-ttu-id="ab60a-114">Les colonnes de sortie dans la sortie de la source de fichier plat comportent la propriété FastParse.</span><span class="sxs-lookup"><span data-stu-id="ab60a-114">The output columns in the output of the Flat File source include the FastParse property.</span></span> <span data-ttu-id="ab60a-115">FastParse indique si la colonne utilise les routines d’analyse de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui sont rapides, mais ne tiennent pas compte des paramètres régionaux, ou les routines d’analyse standard qui tiennent compte des paramètres régionaux.</span><span class="sxs-lookup"><span data-stu-id="ab60a-115">FastParse indicates whether the column uses the quicker, but locale-insensitive, fast parsing routines that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides or the locale-sensitive standard parsing routines.</span></span> <span data-ttu-id="ab60a-116">Pour plus d'informations, consultez [Fast Parse](../fast-parse.md) et [Standard Parse](../standard-parse.md).</span><span class="sxs-lookup"><span data-stu-id="ab60a-116">For more information, see [Fast Parse](../fast-parse.md) and [Standard Parse](../standard-parse.md).</span></span>  
  
 <span data-ttu-id="ab60a-117">Les colonnes de sortie incluent également la propriété UseBinaryFormat.</span><span class="sxs-lookup"><span data-stu-id="ab60a-117">Output columns also include the UseBinaryFormat property.</span></span> <span data-ttu-id="ab60a-118">Cette propriété vous permet d'implémenter la prise en charge de données binaires, par exemple des données au format décimal compressé, dans des fichiers.</span><span class="sxs-lookup"><span data-stu-id="ab60a-118">You use this property to implement support for binary data, such as data with the packed decimal format, in files.</span></span> <span data-ttu-id="ab60a-119">Par défaut, UseBinaryFormat a la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="ab60a-119">By default UseBinaryFormat is set to `false`.</span></span> <span data-ttu-id="ab60a-120">Si vous souhaitez utiliser un format binaire, affectez à UseBinaryFormat `true` la valeur et au type de données de la colonne de sortie la valeur `DT_BYTES` .</span><span class="sxs-lookup"><span data-stu-id="ab60a-120">If you want to use a binary format, set UseBinaryFormat to `true` and the data type on the output column to `DT_BYTES`.</span></span> <span data-ttu-id="ab60a-121">De cette manière, la source de fichier plat ignore la conversion des données et passe les données telles quelles à la colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="ab60a-121">When you do this, the Flat File source skips the data conversion and passes the data to the output column as is.</span></span> <span data-ttu-id="ab60a-122">Vous pouvez ensuite utiliser une transformation, telle que la conversion de données ou de colonne dérivée pour convertir les données `DT_BYTES` en un type de données différent, ou vous pouvez écrire un script personnalisé dans une transformation de script pour interpréter les données.</span><span class="sxs-lookup"><span data-stu-id="ab60a-122">You can then use a transformation such as the Derived Column or Data Conversion to cast the `DT_BYTES` data to a different data type, or you can write custom script in a Script transformation to interpret the data.</span></span> <span data-ttu-id="ab60a-123">Vous pouvez également écrire un composant de flux de données personnalisé pour interpréter les données.</span><span class="sxs-lookup"><span data-stu-id="ab60a-123">You can also write a custom data flow component to interpret the data.</span></span> <span data-ttu-id="ab60a-124">Pour plus d’informations sur les types de données vers lesquels vous pouvez effectuer un cast `DT_BYTES` , consultez [Cast &#40;Expression SSIS&#41;](../expressions/cast-ssis-expression.md).</span><span class="sxs-lookup"><span data-stu-id="ab60a-124">For more information about which data types you can cast `DT_BYTES` to, see [Cast &#40;SSIS Expression&#41;](../expressions/cast-ssis-expression.md).</span></span>  
  
 <span data-ttu-id="ab60a-125">Cette source utilise un gestionnaire de connexions de fichiers plats pour accéder au fichier texte.</span><span class="sxs-lookup"><span data-stu-id="ab60a-125">This source uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="ab60a-126">À l'aide des propriétés du gestionnaire de connexions de fichiers plats, vous pouvez indiquer des informations relatives au fichier et à chacune de ses colonnes, ainsi que définir la façon dont la source du fichier plat doit gérer les données figurant dans le fichier texte.</span><span class="sxs-lookup"><span data-stu-id="ab60a-126">By setting properties on the Flat File connection manager, you can provide information about the file and each column in it, and specify how the Flat File source should handle the data in the text file.</span></span> <span data-ttu-id="ab60a-127">Par exemple, vous pouvez spécifier les caractères qui séparent les colonnes et les lignes du fichier, ainsi que le type de données et la longueur de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="ab60a-127">For example, you can specify the characters that delimit columns and rows in the file, and the data type and the length of each column.</span></span> <span data-ttu-id="ab60a-128">Pour plus d'informations, consultez [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ab60a-128">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="ab60a-129">Cette source comporte une sortie et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="ab60a-129">This source has one output and one error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-source"></a><span data-ttu-id="ab60a-130">Configuration de la source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="ab60a-130">Configuration of the Flat File Source</span></span>  
 <span data-ttu-id="ab60a-131">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="ab60a-131">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ab60a-132">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de source de fichier plat**, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ab60a-132">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ab60a-133">Éditeur de source de fichier plat &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="ab60a-133">Flat File Source Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="ab60a-134">Éditeur de source de fichier plat &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="ab60a-134">Flat File Source Editor &#40;Columns Page&#41;</span></span>](../flat-file-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="ab60a-135">Éditeur de source de fichier plat &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="ab60a-135">Flat File Source Editor &#40;Error Output Page&#41;</span></span>](../flat-file-source-editor-error-output-page.md)  
  
 <span data-ttu-id="ab60a-136">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="ab60a-136">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="ab60a-137">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="ab60a-137">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ab60a-138">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="ab60a-138">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="ab60a-139">Propriétés personnalisées des fichiers plats</span><span class="sxs-lookup"><span data-stu-id="ab60a-139">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="ab60a-140">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="ab60a-140">Related Tasks</span></span>  
 <span data-ttu-id="ab60a-141">Pour plus d’informations sur la définition des propriétés d’un composant de flux de données, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="ab60a-141">For details about how to set properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab60a-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab60a-142">See Also</span></span>  
 <span data-ttu-id="ab60a-143">[Destination de fichier plat](flat-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="ab60a-143">[Flat File Destination](flat-file-destination.md) </span></span>  
 [<span data-ttu-id="ab60a-144">Flux de données</span><span class="sxs-lookup"><span data-stu-id="ab60a-144">Data Flow</span></span>](data-flow.md)  
  
  
