---
title: Éditeur de source XML (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.xmlsourceadapter.connectionmanager.f1
helpviewer_keywords:
- XML Source Editor
ms.assetid: e6507403-a3ce-4b6f-91fc-a7de9f7b6283
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0e40ca6ef2d8fbcd10b756a2ce15f33730c367d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614160"
---
# <a name="xml-source-editor-connection-manager-page"></a><span data-ttu-id="c3260-102">Éditeur de source XML (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="c3260-102">XML Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="c3260-103">Utilisez la page **Gestionnaire de connexions** de l' **Éditeur de source XML** pour spécifier un fichier XML et le schéma XSD qui transforme les données XML.</span><span class="sxs-lookup"><span data-stu-id="c3260-103">Use the **Connection Manager** page of the **XML Source Editor** to specify an XML file and the XSD that transforms the XML data.</span></span>  
  
 <span data-ttu-id="c3260-104">Pour plus d'informations sur la source XML, consultez [XML Source](data-flow/xml-source.md).</span><span class="sxs-lookup"><span data-stu-id="c3260-104">For more information about the XML source, see [XML Source](data-flow/xml-source.md).</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="c3260-105">Options statiques</span><span class="sxs-lookup"><span data-stu-id="c3260-105">Static Options</span></span>  
 <span data-ttu-id="c3260-106">**Mode d'accès aux données**</span><span class="sxs-lookup"><span data-stu-id="c3260-106">**Data access mode**</span></span>  
 <span data-ttu-id="c3260-107">Spécifiez la méthode de sélection des données dans la source.</span><span class="sxs-lookup"><span data-stu-id="c3260-107">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="c3260-108">Valeur</span><span class="sxs-lookup"><span data-stu-id="c3260-108">Value</span></span>|<span data-ttu-id="c3260-109">Description</span><span class="sxs-lookup"><span data-stu-id="c3260-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c3260-110">Emplacement du fichier XML</span><span class="sxs-lookup"><span data-stu-id="c3260-110">XML file location</span></span>|<span data-ttu-id="c3260-111">Récupère des données dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="c3260-111">Retrieve data from an XML file.</span></span>|  
|<span data-ttu-id="c3260-112">Fichier XML à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="c3260-112">XML file from variable</span></span>|<span data-ttu-id="c3260-113">Spécifiez le nom de fichier XML dans une variable.</span><span class="sxs-lookup"><span data-stu-id="c3260-113">Specify the XML file name in a variable.</span></span><br /><br /> <span data-ttu-id="c3260-114">**Informations connexes** : [Utiliser des variables dans des packages](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="c3260-114">**Related information**: [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="c3260-115">Données XML à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="c3260-115">XML data from variable</span></span>|<span data-ttu-id="c3260-116">Récupère des données XML à partir d'une variable.</span><span class="sxs-lookup"><span data-stu-id="c3260-116">Retrieve XML data from a variable.</span></span>|  
  
 <span data-ttu-id="c3260-117">**Utiliser le schéma inclus**</span><span class="sxs-lookup"><span data-stu-id="c3260-117">**Use inline schema**</span></span>  
 <span data-ttu-id="c3260-118">Indique si les données de la source XML contiennent le schéma XSD définissant et validant sa structure et ses données.</span><span class="sxs-lookup"><span data-stu-id="c3260-118">Specify whether the XML source data itself contains the XSD schema that defines and validates its structure and data.</span></span>  
  
 <span data-ttu-id="c3260-119">**Emplacement XSD**</span><span class="sxs-lookup"><span data-stu-id="c3260-119">**XSD location**</span></span>  
 <span data-ttu-id="c3260-120">Tapez le chemin et le nom de fichier du schéma XSD, ou recherchez le fichier en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="c3260-120">Type the path and file name of the XSD schema file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="c3260-121">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="c3260-121">**Browse**</span></span>  
 <span data-ttu-id="c3260-122">Dans la boîte de dialogue **Ouvrir** , recherchez le fichier de schéma XSD.</span><span class="sxs-lookup"><span data-stu-id="c3260-122">Use the **Open** dialog box to locate the XSD schema file.</span></span>  
  
 <span data-ttu-id="c3260-123">**Créer XSD**</span><span class="sxs-lookup"><span data-stu-id="c3260-123">**Generate XSD**</span></span>  
 <span data-ttu-id="c3260-124">Utilisez la boîte de dialogue **Enregistrer sous** pour sélectionner l’emplacement du fichier de schéma XSD généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="c3260-124">Use the **Save As** dialog box to select a location for the auto-generated XSD schema file.</span></span> <span data-ttu-id="c3260-125">L'éditeur détermine le schéma en fonction de la structure des données XML.</span><span class="sxs-lookup"><span data-stu-id="c3260-125">The editor infers the schema from the structure of the XML data.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="c3260-126">Options dynamiques du mode d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="c3260-126">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--xml-file-location"></a><span data-ttu-id="c3260-127">Mode d'accès aux données = emplacement du fichier XML</span><span class="sxs-lookup"><span data-stu-id="c3260-127">Data access mode = XML file location</span></span>  
 <span data-ttu-id="c3260-128">**Emplacement XML**</span><span class="sxs-lookup"><span data-stu-id="c3260-128">**XML location**</span></span>  
 <span data-ttu-id="c3260-129">Tapez le chemin et le nom du fichier de données XML, ou recherchez le fichier en cliquant sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="c3260-129">Type the path and file name of the XML data file, or locate the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="c3260-130">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="c3260-130">**Browse**</span></span>  
 <span data-ttu-id="c3260-131">Dans la boîte de dialogue **Ouvrir** , recherchez le fichier de données XML.</span><span class="sxs-lookup"><span data-stu-id="c3260-131">Use the **Open** dialog box to locate the XML data file.</span></span>  
  
### <a name="data-access-mode--xml-file-from-variable"></a><span data-ttu-id="c3260-132">Mode d'accès aux données = fichier XML à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="c3260-132">Data access mode = XML file from variable</span></span>  
 <span data-ttu-id="c3260-133">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="c3260-133">**Variable name**</span></span>  
 <span data-ttu-id="c3260-134">Sélectionnez la variable contenant le chemin d'accès et le nom du fichier XML.</span><span class="sxs-lookup"><span data-stu-id="c3260-134">Select the variable that contains the path and file name of the XML file.</span></span>  
  
### <a name="data-access-mode--xml-data-from-variable"></a><span data-ttu-id="c3260-135">Mode d'accès aux données = données XML à partir d'une variable</span><span class="sxs-lookup"><span data-stu-id="c3260-135">Data access mode = XML data from variable</span></span>  
 <span data-ttu-id="c3260-136">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="c3260-136">**Variable name**</span></span>  
 <span data-ttu-id="c3260-137">Sélectionnez la variable qui contient les données XML.</span><span class="sxs-lookup"><span data-stu-id="c3260-137">Select the variable that contains the XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3260-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3260-138">See Also</span></span>  
 <span data-ttu-id="c3260-139">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="c3260-139">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="c3260-140">[Éditeur de source XML &#40;page colonnes&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c3260-140">[XML Source Editor &#40;Columns Page&#41;](../../2014/integration-services/xml-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="c3260-141">[Éditeur de source XML &#40;page sortie d’erreur&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c3260-141">[XML Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/xml-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c3260-142">Extraire des données à l'aide de la source XML</span><span class="sxs-lookup"><span data-stu-id="c3260-142">Extract Data by Using the XML Source</span></span>](data-flow/extract-data-by-using-the-xml-source.md)  
  
  
