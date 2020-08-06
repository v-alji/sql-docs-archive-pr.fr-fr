---
title: Source de fichier brut | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Raw File
- raw data [Integration Services]
- Raw File source
ms.assetid: 5b4daea5-7f76-4674-aa77-0a79f9f97f7d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbc5800c4fb2b90b74e66b6ff161118b2b550f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602911"
---
# <a name="raw-file-source"></a><span data-ttu-id="173d5-102">source de fichier brut</span><span class="sxs-lookup"><span data-stu-id="173d5-102">Raw File Source</span></span>
  <span data-ttu-id="173d5-103">La source de fichier brut lit des données brutes dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="173d5-103">The Raw File source reads raw data from a file.</span></span> <span data-ttu-id="173d5-104">La représentation des données étant native pour la source, celles-ci ne nécessitent aucune traduction et pratiquement aucune analyse.</span><span class="sxs-lookup"><span data-stu-id="173d5-104">Because the representation of the data is native to the source, the data requires no translation and almost no parsing.</span></span> <span data-ttu-id="173d5-105">Par conséquent, la source de fichier brut peut lire les données plus rapidement que les autres sources telles que la source du fichier plat et la source OLE DB.</span><span class="sxs-lookup"><span data-stu-id="173d5-105">This means that the Raw File source can read data more quickly than other sources such as the Flat File and the OLE DB sources.</span></span>  
  
 <span data-ttu-id="173d5-106">La source de fichier brut permet d'extraire des données brutes précédemment écrites par la destination de fichier brut.</span><span class="sxs-lookup"><span data-stu-id="173d5-106">The Raw File source is used to retrieve raw data that was previously written by the Raw File destination.</span></span> <span data-ttu-id="173d5-107">Vous pouvez également faire pointer la source de fichier brut vers un fichier brut vide qui contient uniquement les colonnes (fichier réservé aux métadonnées).</span><span class="sxs-lookup"><span data-stu-id="173d5-107">You can also point the Raw File source to an empty raw file that contains only the columns (metadata-only file).</span></span> <span data-ttu-id="173d5-108">Utilisez la destination de fichier brut pour générer le fichier réservé aux métadonnées sans avoir à exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="173d5-108">You use the Raw File destination to generate the metadata-only file without having to run the package.</span></span> <span data-ttu-id="173d5-109">Pour plus d’informations, consultez [Destination de fichier brut](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="173d5-109">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
 <span data-ttu-id="173d5-110">Le format de fichier brut contient les informations de tri.</span><span class="sxs-lookup"><span data-stu-id="173d5-110">The raw file format contains sort information.</span></span> <span data-ttu-id="173d5-111">La destination de fichier brut enregistre toutes les informations de tri, y compris les indicateurs de comparaison des colonnes de chaîne.</span><span class="sxs-lookup"><span data-stu-id="173d5-111">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="173d5-112">La source de fichier brut lit et applique les informations de tri.</span><span class="sxs-lookup"><span data-stu-id="173d5-112">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="173d5-113">Vous avez la possibilité de configurer la source de fichier brut pour ignorer les indicateurs de tri du fichier, à l'aide de l'éditeur avancé.</span><span class="sxs-lookup"><span data-stu-id="173d5-113">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="173d5-114">Pour plus d’informations sur les indicateurs de comparaison, consultez [Comparaison de données de type chaîne](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="173d5-114">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="173d5-115">Pour configurer le fichier brut, vous spécifiez le nom du fichier lu par la source de fichier brut.</span><span class="sxs-lookup"><span data-stu-id="173d5-115">You configure the Raw File by specifying the name of the name of the file that the Raw File source reads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="173d5-116">Cette source n'utilise pas de gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="173d5-116">This source does not use a connection manager.</span></span>  
  
 <span data-ttu-id="173d5-117">Cette source a une sortie.</span><span class="sxs-lookup"><span data-stu-id="173d5-117">This source has one output.</span></span> <span data-ttu-id="173d5-118">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="173d5-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-raw-file-source"></a><span data-ttu-id="173d5-119">Configuration de la source de fichier brut</span><span class="sxs-lookup"><span data-stu-id="173d5-119">Configuration of the Raw File Source</span></span>  
 <span data-ttu-id="173d5-120">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="173d5-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="173d5-121">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="173d5-121">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="173d5-122">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="173d5-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="173d5-123">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="173d5-123">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="173d5-124">Propriétés personnalisées des fichiers bruts</span><span class="sxs-lookup"><span data-stu-id="173d5-124">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="173d5-125">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="173d5-125">Related Tasks</span></span>  
 <span data-ttu-id="173d5-126">Pour plus d’informations sur la définition des propriétés du composant, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="173d5-126">For information about how to set the properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="173d5-127">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="173d5-127">Related Content</span></span>  
  
-   <span data-ttu-id="173d5-128">Entrée de blog, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), sur sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="173d5-128">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173d5-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="173d5-129">See Also</span></span>  
 <span data-ttu-id="173d5-130">[Destination de fichier brut](raw-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="173d5-130">[Raw File Destination](raw-file-destination.md) </span></span>  
 [<span data-ttu-id="173d5-131">Flux de données</span><span class="sxs-lookup"><span data-stu-id="173d5-131">Data Flow</span></span>](data-flow.md)  
  
  
