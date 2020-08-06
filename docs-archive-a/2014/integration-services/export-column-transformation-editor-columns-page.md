---
title: Éditeur de transformation d’exportation de colonne (page colonnes) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fileextractortransformation.columns.f1
helpviewer_keywords:
- Export Column Transformation Editor
ms.assetid: b659a5c2-5509-4b5b-9c82-136c971d5c7f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 404b404e2328228049ae46fb1c3089b0b4089f0a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603571"
---
# <a name="export-column-transformation-editor-columns-page"></a><span data-ttu-id="4bf90-102">Éditeur de transformation d'exportation de colonne (page Colonnes)</span><span class="sxs-lookup"><span data-stu-id="4bf90-102">Export Column Transformation Editor (Columns Page)</span></span>
  <span data-ttu-id="4bf90-103">Utilisez la page **Colonnes** de la boîte de dialogue **Éditeur de transformation d'exportation de colonne** pour spécifier les colonnes du flux de données à extraire dans des fichiers.</span><span class="sxs-lookup"><span data-stu-id="4bf90-103">Use the **Columns** page of the **Export Column Transformation Editor** dialog box to specify columns in the data flow to extract to files.</span></span> <span data-ttu-id="4bf90-104">Vous pouvez préciser si la transformation d'exportation de colonne ajoute des données à la fin d'un fichier ou écrase le fichier existant.</span><span class="sxs-lookup"><span data-stu-id="4bf90-104">You can specify whether the Export Column transformation appends data to a file or overwrites an existing file.</span></span>  
  
 <span data-ttu-id="4bf90-105">Pour en savoir plus sur la transformation d'exportation de colonne, consultez [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4bf90-105">To learn more about the Export Column transformation, see [Export Column Transformation](data-flow/transformations/export-column-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4bf90-106">Options</span><span class="sxs-lookup"><span data-stu-id="4bf90-106">Options</span></span>  
 <span data-ttu-id="4bf90-107">**Colonne d'extraction**</span><span class="sxs-lookup"><span data-stu-id="4bf90-107">**Extract Column**</span></span>  
 <span data-ttu-id="4bf90-108">Permet de sélectionner à partir de la liste d'entrée des colonnes contenant des données texte ou image.</span><span class="sxs-lookup"><span data-stu-id="4bf90-108">Select from the list of input columns that contain text or image data.</span></span> <span data-ttu-id="4bf90-109">Toutes les lignes doivent avoir des définitions pour les options **Colonne d'extraction** et **Colonne du chemin d'accès**.</span><span class="sxs-lookup"><span data-stu-id="4bf90-109">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="4bf90-110">**Colonne du chemin d'accès**</span><span class="sxs-lookup"><span data-stu-id="4bf90-110">**File Path Column**</span></span>  
 <span data-ttu-id="4bf90-111">Permet de sélectionner à partir de la liste d'entrée des colonnes contenant les chemins d'accès aux fichiers ainsi que les noms de fichiers.</span><span class="sxs-lookup"><span data-stu-id="4bf90-111">Select from the list of input columns that contain file paths and file names.</span></span> <span data-ttu-id="4bf90-112">Toutes les lignes doivent avoir des définitions pour les options **Colonne d'extraction** et **Colonne du chemin d'accès**.</span><span class="sxs-lookup"><span data-stu-id="4bf90-112">All rows should have definitions for **Extract Column** and **File Path Column**.</span></span>  
  
 <span data-ttu-id="4bf90-113">**Autoriser l'ajout**</span><span class="sxs-lookup"><span data-stu-id="4bf90-113">**Allow Append**</span></span>  
 <span data-ttu-id="4bf90-114">Permet de préciser si la transformation ajoute ou non des données à la fin des fichiers existants.</span><span class="sxs-lookup"><span data-stu-id="4bf90-114">Specify whether the transformation appends data to existing files.</span></span> <span data-ttu-id="4bf90-115">Par défaut, il s’agit de `false`.</span><span class="sxs-lookup"><span data-stu-id="4bf90-115">The default is `false`.</span></span>  
  
 <span data-ttu-id="4bf90-116">**Forcer la troncation**</span><span class="sxs-lookup"><span data-stu-id="4bf90-116">**Force Truncate**</span></span>  
 <span data-ttu-id="4bf90-117">Permet de préciser si la transformation supprime le contenu des fichiers existants avant d'écrire des données.</span><span class="sxs-lookup"><span data-stu-id="4bf90-117">Specify whether the transformation deletes the contents of existing files before writing data.</span></span> <span data-ttu-id="4bf90-118">Par défaut, il s’agit de `false`.</span><span class="sxs-lookup"><span data-stu-id="4bf90-118">The default is `false`.</span></span>  
  
 <span data-ttu-id="4bf90-119">**Écrire la marque d'ordre d'octet**</span><span class="sxs-lookup"><span data-stu-id="4bf90-119">**Write BOM**</span></span>  
 <span data-ttu-id="4bf90-120">Indique s'il est nécessaire d'écrire une marque d'ordre d'octet (BOM, Byte-Order Mark) dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="4bf90-120">Specify whether to write a byte-order mark (BOM) to the file.</span></span> <span data-ttu-id="4bf90-121">Une BOM n'est inscrite que dans les cas où les données sont de type `DT_NTEXT` ou DT_WSTR et qu'elles ne sont pas ajoutées à la fin d'un fichier de données existant.</span><span class="sxs-lookup"><span data-stu-id="4bf90-121">A BOM is only written if the data has the `DT_NTEXT` or DT_WSTR data type and is not appended to an existing data file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bf90-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4bf90-122">See Also</span></span>  
 <span data-ttu-id="4bf90-123">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="4bf90-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="4bf90-124">Éditeur de transformation d’exportation de colonne &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="4bf90-124">Export Column Transformation Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/export-column-transformation-editor-error-output-page.md)  
  
  
