---
title: Destination de fichier plat | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledest.f1
helpviewer_keywords:
- flat files
- Flat File destination
- text file writing [Integration Services]
- destinations [Integration Services], Flat File
ms.assetid: e0d6e356-8db4-48aa-ba66-029397f98f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a961b7528b13a4eaa3297343e91f1deaf2fa3226
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709779"
---
# <a name="flat-file-destination"></a><span data-ttu-id="61cae-102">Destination de fichier plat</span><span class="sxs-lookup"><span data-stu-id="61cae-102">Flat File Destination</span></span>
  <span data-ttu-id="61cae-103">La destination de fichier plat écrit des données dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="61cae-103">The Flat File destination writes data to a text file.</span></span> <span data-ttu-id="61cae-104">Le fichier texte peut se présenter dans un format délimité, à largeur fixe, à largeur fixe avec séparateur de ligne ou en drapeau à droite.</span><span class="sxs-lookup"><span data-stu-id="61cae-104">The text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="61cae-105">Vous pouvez configurer la destination de fichier plat de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="61cae-105">You can configure the Flat File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="61cae-106">Fournissez un bloc de texte qui est inséré dans le fichier avant l'écriture des données.</span><span class="sxs-lookup"><span data-stu-id="61cae-106">Provide a block of text that is inserted in the file before any data is written.</span></span> <span data-ttu-id="61cae-107">Le texte peut fournir des informations telles que des en-têtes de colonnes.</span><span class="sxs-lookup"><span data-stu-id="61cae-107">The text can provide information such as column headings.</span></span>  
  
-   <span data-ttu-id="61cae-108">Spécifiez s'il faut remplacer des données dans un fichier de destination qui porte le même nom.</span><span class="sxs-lookup"><span data-stu-id="61cae-108">Specify whether to overwrite a data in a destination file that has the same name.</span></span>  
  
 <span data-ttu-id="61cae-109">Cette destination utilise un gestionnaire de connexions de fichier plat pour accéder au fichier texte.</span><span class="sxs-lookup"><span data-stu-id="61cae-109">This destination uses a Flat File connection manager to access the text file.</span></span> <span data-ttu-id="61cae-110">En définissant les propriétés du gestionnaire de connexions de fichier plat utilisé par la destination de fichier plat, vous pouvez spécifier la façon dont elle met en forme et écrit le fichier texte.</span><span class="sxs-lookup"><span data-stu-id="61cae-110">By setting properties on the Flat File connection manager that the Flat File destination uses, you can specify how the Flat File destination formats and writes the text file.</span></span> <span data-ttu-id="61cae-111">Lors de la configuration du gestionnaire de connexions de fichier plat, vous spécifiez des informations sur le fichier et sur chacune de ses colonnes.</span><span class="sxs-lookup"><span data-stu-id="61cae-111">When you configure the Flat File connection manager, you specify information about the file and about each column in the file.</span></span> <span data-ttu-id="61cae-112">Par exemple, vous spécifiez les caractères qui délimitent les colonnes et les lignes du fichier, ainsi que le type de données et la longueur de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="61cae-112">For example, you specify the characters that delimit columns and rows in the file, and you specify the data type and the length of each column.</span></span> <span data-ttu-id="61cae-113">Pour plus d'informations, consultez [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="61cae-113">For more information, see [Flat File Connection Manager](../connection-manager/file-connection-manager.md).</span></span>  
  
 <span data-ttu-id="61cae-114">La destination de fichier plat inclut la propriété personnalisée Header.</span><span class="sxs-lookup"><span data-stu-id="61cae-114">The Flat File destination includes the Header custom property.</span></span> <span data-ttu-id="61cae-115">La propriété peut être mise à jour par une expression de propriété lors du chargement du package.</span><span class="sxs-lookup"><span data-stu-id="61cae-115">This property can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="61cae-116">Pour plus d’informations, consultez [Expressions Integration Services &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Expressions de propriété dans des packages](../expressions/use-property-expressions-in-packages.md) et [Propriétés personnalisées des fichiers plats](flat-file-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="61cae-116">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [Flat File Custom Properties](flat-file-custom-properties.md).</span></span>  
  
 <span data-ttu-id="61cae-117">Cette destination possède une sortie.</span><span class="sxs-lookup"><span data-stu-id="61cae-117">This destination has one output.</span></span> <span data-ttu-id="61cae-118">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="61cae-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-flat-file-destination"></a><span data-ttu-id="61cae-119">Configuration de la destination de fichier plat</span><span class="sxs-lookup"><span data-stu-id="61cae-119">Configuration of the Flat File Destination</span></span>  
 <span data-ttu-id="61cae-120">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="61cae-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="61cae-121">Pour plus d’informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de source de fichier plat**, cliquez sur l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="61cae-121">For more information about the properties that you can set in the **Flat File Source Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="61cae-122">Éditeur de destination de fichier plat &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="61cae-122">Flat File Destination Editor &#40;Connection Manager Page&#41;</span></span>](../flat-file-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="61cae-123">Éditeur de destination de fichier plat &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="61cae-123">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../flat-file-destination-editor-mappings-page.md)  
  
 <span data-ttu-id="61cae-124">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="61cae-124">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="61cae-125">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="61cae-125">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="61cae-126">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="61cae-126">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="61cae-127">Propriétés personnalisées des fichiers plats</span><span class="sxs-lookup"><span data-stu-id="61cae-127">Flat File Custom Properties</span></span>](flat-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="61cae-128">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="61cae-128">Related Tasks</span></span>  
 <span data-ttu-id="61cae-129">Pour plus d’informations sur la définition des propriétés d’un composant de flux de données, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="61cae-129">For information about how to set the properties of a data flow component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cae-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="61cae-130">See Also</span></span>  
 <span data-ttu-id="61cae-131">[Source de fichier plat](flat-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="61cae-131">[Flat File Source](flat-file-source.md) </span></span>  
 [<span data-ttu-id="61cae-132">Flux de données</span><span class="sxs-lookup"><span data-stu-id="61cae-132">Data Flow</span></span>](data-flow.md)  
  
  
