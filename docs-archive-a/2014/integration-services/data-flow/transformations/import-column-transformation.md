---
title: Importation de colonne, transformation | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.importcolumntrans.f1
helpviewer_keywords:
- Import Column transformation [Integration Services]
- columns [Integration Services], importing
- importing data, SSIS packages
- inserting data
ms.assetid: ac3b74c1-ef54-4297-8062-1734324fffcc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f4330438614cce7892e74dc9a1dcbb6680b72972
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613055"
---
# <a name="import-column-transformation"></a><span data-ttu-id="b8e5f-102">Transformation d'importation de colonne</span><span class="sxs-lookup"><span data-stu-id="b8e5f-102">Import Column Transformation</span></span>
  <span data-ttu-id="b8e5f-103">La transformation d'importation de colonne lit des données dans des fichiers puis les ajoute à des colonnes dans un flux de données.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-103">The Import Column transformation reads data from files and adds the data to columns in a data flow.</span></span> <span data-ttu-id="b8e5f-104">Grâce à cette transformation, un package peut ajouter à un flux de données du texte et des images stockés dans des fichiers distincts.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-104">Using this transformation, a package can add text and images stored in separate files to a data flow.</span></span> <span data-ttu-id="b8e5f-105">Par exemple, un flux de données qui charge des données dans une table stockant des informations sur des produits peut inclure la transformation d'importation de colonne pour importer depuis des fichiers les commentaires des clients sur chaque produit, puis ajouter ces commentaires au flux de données.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-105">For example, a data flow that loads data into a table that stores product information can include the Import Column transformation to import customer reviews of each product from files and add the reviews to the data flow.</span></span>  
  
 <span data-ttu-id="b8e5f-106">Vous pouvez configurer la transformation d'importation de colonne comme suit :</span><span class="sxs-lookup"><span data-stu-id="b8e5f-106">You can configure the Import Column transformation in the following ways:</span></span>  
  
-   <span data-ttu-id="b8e5f-107">Spécifiez les colonnes auxquelles la transformation ajoute des données.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-107">Specify the columns to which the transformation adds data.</span></span>  
  
-   <span data-ttu-id="b8e5f-108">Indiquez si la transformation attend une marque d'ordre d'octet (BOM, Byte-Order Mark).</span><span class="sxs-lookup"><span data-stu-id="b8e5f-108">Specify whether the transformation expects a byte-order mark (BOM).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b8e5f-109">Une marque d'ordre d'octet n'est attendue que si les données sont du type de données DT_NTEXT.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-109">A BOM is only expected if the data has the DT_NTEXT data type.</span></span>  
  
 <span data-ttu-id="b8e5f-110">Une colonne de l'entrée de transformation contient les noms des fichiers dans lesquels les données sont stockées.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-110">A column in the transformation input contains the names of files that hold the data.</span></span> <span data-ttu-id="b8e5f-111">Chaque ligne de l'ensemble de données peut spécifier un fichier différent.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-111">Each row in the dataset can specify a different file.</span></span> <span data-ttu-id="b8e5f-112">Lorsque la transformation d'importation de colonne traite une ligne, elle lit le nom de fichier, ouvre le fichier correspondant dans le système de fichiers et charge le contenu du fichier dans une colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-112">When the Import Column transformation processes a row, it reads the file name, opens the corresponding file in the file system, and loads the file content into an output column.</span></span> <span data-ttu-id="b8e5f-113">Le type de données de la colonne de sortie doit être DT_TEXT, DT_NTEXT ou DT_IMAGE.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-113">The data type of the output column must be DT_TEXT, DT_NTEXT, or DT_IMAGE.</span></span> <span data-ttu-id="b8e5f-114">Pour plus d’informations, consultez [Types de données Integration Services](../integration-services-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="b8e5f-114">For more information, see [Integration Services Data Types](../integration-services-data-types.md).</span></span>  
  
 <span data-ttu-id="b8e5f-115">Cette transformation a une entrée, une sortie et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-115">This transformation has one input, one output, and one error output.</span></span>  
  
## <a name="configuration-of-the-import-column-transformation"></a><span data-ttu-id="b8e5f-116">Configuration de la transformation d’importation de colonne</span><span class="sxs-lookup"><span data-stu-id="b8e5f-116">Configuration of the Import Column Transformation</span></span>  
 <span data-ttu-id="b8e5f-117">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-117">You can set properties through [!INCLUDE[ssIS](../../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="b8e5f-118">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="b8e5f-118">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="b8e5f-119">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="b8e5f-119">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="b8e5f-120">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="b8e5f-120">Common Properties</span></span>](../../common-properties.md)  
  
-   [<span data-ttu-id="b8e5f-121">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="b8e5f-121">Transformation Custom Properties</span></span>](transformation-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="b8e5f-122">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="b8e5f-122">Related Tasks</span></span>  
 <span data-ttu-id="b8e5f-123">Pour plus d’informations sur la définition des propriétés de ce composant, consultez [Définir les propriétés d’un composant de flux de données](../set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="b8e5f-123">For information about how to set properties of this component, see [Set the Properties of a Data Flow Component](../set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8e5f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b8e5f-124">See Also</span></span>  
 <span data-ttu-id="b8e5f-125">[Transformation d'exportation de colonne](export-column-transformation.md) </span><span class="sxs-lookup"><span data-stu-id="b8e5f-125">[Export Column Transformation](export-column-transformation.md) </span></span>  
 <span data-ttu-id="b8e5f-126">[Flux de données](../data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="b8e5f-126">[Data Flow](../data-flow.md) </span></span>  
 [<span data-ttu-id="b8e5f-127">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="b8e5f-127">Integration Services Transformations</span></span>](integration-services-transformations.md)  
  
  
