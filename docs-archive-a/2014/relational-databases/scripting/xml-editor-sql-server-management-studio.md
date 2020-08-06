---
title: Éditeur XML
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.editorxml.f1
- sql12.swb.xmleditor.f1
- vs.xmleditor
- sql12.swb.editor.xml.f1
helpviewer_keywords:
- XML Designer [SQL Server Management Studio]
ms.assetid: 0824a5ce-e67b-4b53-98d9-d371faf2d23c
author: rothja
ms.author: jroth
ms.openlocfilehash: b7c3bbbda4f5a31c4d83b559c1aa623ca2aff89f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613405"
---
# <a name="xml-editor-sql-server-management-studio"></a><span data-ttu-id="abfb0-102">Éditeur XML (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="abfb0-102">XML Editor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="abfb0-103">Fournit un ensemble d'outils visuels pour utiliser des schémas XML, des groupes de données ADO.NET et des documents XML.</span><span class="sxs-lookup"><span data-stu-id="abfb0-103">Provides a set of visual tools for working with XML Schemas, ADO.NET datasets, and XML documents.</span></span> <span data-ttu-id="abfb0-104">Le Concepteur XML prend en charge le langage de définition de schéma XML (XSD, XML Schema Definition) défini par le World Wide Web Consortium (WC3),</span><span class="sxs-lookup"><span data-stu-id="abfb0-104">The XML Designer supports the XML Schema Definition (XSD) language defined by the World Wide Web Consortium (WC3).</span></span> <span data-ttu-id="abfb0-105">mais pas les définitions de type de document (DTD) ni les autres langages de schéma XML, tel XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="abfb0-105">The designer does not support DTDs (document type definitions) or other XML schema languages, such as XDR (XML-Data Reduced).</span></span>  
  
 <span data-ttu-id="abfb0-106">Pour afficher le concepteur, ajoutez un groupe de données, un schéma XML ou un fichier XML à votre projet ou ouvrez l'un des types de fichiers énumérés dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="abfb0-106">To display the designer, add a dataset, XML Schema, or XML file to your project or open any of the file types listed in the table below.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="abfb0-107">La commande **Annuler** n'est pas disponible lorsque vous travaillez en mode Schéma.</span><span class="sxs-lookup"><span data-stu-id="abfb0-107">There is no **Undo** command when working in Schema view.</span></span> <span data-ttu-id="abfb0-108">Planifiez soigneusement votre travail et enregistrez souvent vos fichiers.</span><span class="sxs-lookup"><span data-stu-id="abfb0-108">Plan your work carefully and save your files often.</span></span>  
  
 <span data-ttu-id="abfb0-109">Le concepteur propose trois vues (ou modes) pour travailler sur les fichiers XML, les schémas XML et les groupes de données :</span><span class="sxs-lookup"><span data-stu-id="abfb0-109">The designer provides the following three views (or modes) to work on XML files, XML Schemas, and datasets:</span></span>  
  
|<span data-ttu-id="abfb0-110">Affichage</span><span class="sxs-lookup"><span data-stu-id="abfb0-110">View</span></span>|<span data-ttu-id="abfb0-111">Description</span><span class="sxs-lookup"><span data-stu-id="abfb0-111">Description</span></span>|<span data-ttu-id="abfb0-112">Types de fichiers pris en charge</span><span class="sxs-lookup"><span data-stu-id="abfb0-112">File types supported</span></span>|  
|----------|-----------------|--------------------------|  
|<span data-ttu-id="abfb0-113">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="abfb0-113">**Schema**</span></span>|<span data-ttu-id="abfb0-114">Pour créer et modifier visuellement des schémas XML et des groupes de données ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="abfb0-114">For visually creating and modifying XML Schemas and ADO.NET datasets.</span></span>|<span data-ttu-id="abfb0-115">.xsd</span><span class="sxs-lookup"><span data-stu-id="abfb0-115">.xsd</span></span>|  
|<span data-ttu-id="abfb0-116">**Données**</span><span class="sxs-lookup"><span data-stu-id="abfb0-116">**Data**</span></span>|<span data-ttu-id="abfb0-117">Pour modifier visuellement des fichiers de données XML dans une grille de données structurée.</span><span class="sxs-lookup"><span data-stu-id="abfb0-117">For visually modifying XML data files in a structured data grid.</span></span>|<span data-ttu-id="abfb0-118">.xml</span><span class="sxs-lookup"><span data-stu-id="abfb0-118">.xml</span></span>|  
|<span data-ttu-id="abfb0-119">**XML**</span><span class="sxs-lookup"><span data-stu-id="abfb0-119">**XML**</span></span>|<span data-ttu-id="abfb0-120">Pour modifier XML ; l'éditeur de code source fournit un codage en couleurs et IntelliSense, y compris Compléter le mot et Liste des membres.</span><span class="sxs-lookup"><span data-stu-id="abfb0-120">For editing XML; the source editor provides color-coding and IntelliSense, including Complete Word and List Members.</span></span>|<span data-ttu-id="abfb0-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span><span class="sxs-lookup"><span data-stu-id="abfb0-121">.xml .xsd .xslt .wsdl.web.resx.tdl.wsf.hta.disco.vsdisco.config</span></span>|  
|<span data-ttu-id="abfb0-122">**ShowPlan**</span><span class="sxs-lookup"><span data-stu-id="abfb0-122">**ShowPlan**</span></span>|<span data-ttu-id="abfb0-123">Affiche les plans de requête XML créés à l'aide de l'option SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="abfb0-123">Displays xml query plans created using the SET SHOWPLAN_XML ON option.</span></span>|<span data-ttu-id="abfb0-124">.showplan</span><span class="sxs-lookup"><span data-stu-id="abfb0-124">.showplan</span></span>|  
  
## <a name="schema-view"></a><span data-ttu-id="abfb0-125">Mode Schéma</span><span class="sxs-lookup"><span data-stu-id="abfb0-125">Schema View</span></span>  
 <span data-ttu-id="abfb0-126">Le mode Schéma fournit une représentation visuelle des éléments, attributs, types, etc., qui constituent les schémas XML et les groupes de données ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="abfb0-126">Schema view provides a visual representation of the elements, attributes, types, and so on, that make up XML Schemas and ADO.NET datasets.</span></span>  
  
 <span data-ttu-id="abfb0-127">Le mode Schéma vous permet de construire des schémas et des groupes de données en déplaçant des éléments sur l'aire de conception soit à partir de l'onglet Schéma XML de la Boîte à outils, soit à partir de l'Explorateur de serveurs.</span><span class="sxs-lookup"><span data-stu-id="abfb0-127">In Schema view you can construct schemas and datasets by dropping elements on the design surface from either the XML Schema tab of the Toolbox or from Server Explorer.</span></span> <span data-ttu-id="abfb0-128">Vous pouvez également ajouter des éléments au concepteur en cliquant avec le bouton droit sur l'aire de conception et en sélectionnant Ajouter dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="abfb0-128">Additionally, you can add elements to the designer by right-clicking the design surface and selecting Add from the shortcut menu.</span></span>  
  
 <span data-ttu-id="abfb0-129">En mode Schéma, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="abfb0-129">In Schema view you can:</span></span>  
  
-   <span data-ttu-id="abfb0-130">construire et modifier des schémas XML et des groupes de données ADO.NET ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-130">Construct and modify existing XML Schemas and ADO.NET datasets</span></span>  
  
-   <span data-ttu-id="abfb0-131">créer et modifier des relations entre les tables ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-131">Create and edit relationships between tables</span></span>  
  
-   <span data-ttu-id="abfb0-132">créer et modifier des clés ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-132">Create and edit keys</span></span>  
  
-   <span data-ttu-id="abfb0-133">générer des groupes de données ADO.NET à partir de schémas XML.</span><span class="sxs-lookup"><span data-stu-id="abfb0-133">Generate ADO.NET datasets from XML Schemas</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abfb0-134">La disposition des éléments en mode Schéma est stockée dans le fichier .xsx, que vous pouvez afficher en cliquant sur **Afficher tous les fichiers** dans la barre d'outils de l'Explorateur de solutions, puis en développant le fichier .xsd.</span><span class="sxs-lookup"><span data-stu-id="abfb0-134">The layout of elements in Schema view is stored in the .xsx file, which can be seen by clicking **Show All Files** in the Solution Explorer toolbar, and then expanding the .xsd file.</span></span> <span data-ttu-id="abfb0-135">Si aucun fichier .xsx n'est présent, cela signifie que le fichier .xsd n'a jamais été ouvert dans le Concepteur XML.</span><span class="sxs-lookup"><span data-stu-id="abfb0-135">If there is no .xsx file present, it means the .xsd file has never been opened in the XML Designer.</span></span>  
  
### <a name="customizing-schema-view"></a><span data-ttu-id="abfb0-136">Personnalisation du mode Schéma</span><span class="sxs-lookup"><span data-stu-id="abfb0-136">Customizing Schema View</span></span>  
 <span data-ttu-id="abfb0-137">Les fonctionnalités suivantes permettent de modifier la présentation visuelle des éléments en mode Schéma :</span><span class="sxs-lookup"><span data-stu-id="abfb0-137">The following features modify the visual layout of elements in Schema view:</span></span>  
  
-   <span data-ttu-id="abfb0-138">zoom ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-138">Zooming</span></span>  
  
-   <span data-ttu-id="abfb0-139">développement et réduction des éléments imbriqués ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-139">Expanding or collapsing of nested elements</span></span>  
  
-   <span data-ttu-id="abfb0-140">réorganisation automatique de la disposition des éléments ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-140">Automatically arranging layout of elements</span></span>  
  
-   <span data-ttu-id="abfb0-141">rétablissement de l'état par défaut des éléments réduits.</span><span class="sxs-lookup"><span data-stu-id="abfb0-141">Resetting default state of collapsed elements</span></span>  
  
##### <a name="to-expand-hidden-nested-elements"></a><span data-ttu-id="abfb0-142">Pour développer les éléments imbriqués masqués</span><span class="sxs-lookup"><span data-stu-id="abfb0-142">To expand hidden nested elements</span></span>  
  
-   <span data-ttu-id="abfb0-143">Cliquez sur l'icône plus (+) en bas de l'élément.</span><span class="sxs-lookup"><span data-stu-id="abfb0-143">Click the plus icon on the bottom of the element.</span></span>  
  
##### <a name="to-collapse-nested-elements"></a><span data-ttu-id="abfb0-144">Pour réduire les éléments imbriqués</span><span class="sxs-lookup"><span data-stu-id="abfb0-144">To collapse nested elements</span></span>  
  
-   <span data-ttu-id="abfb0-145">Cliquez sur l'icône moins (-) de l'élément le plus bas que vous souhaitez afficher dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="abfb0-145">Click the minus icon on the bottom-most element that you want to appear on the designer.</span></span>  
  
## <a name="data-view"></a><span data-ttu-id="abfb0-146">Vue de données</span><span class="sxs-lookup"><span data-stu-id="abfb0-146">Data View</span></span>  
 <span data-ttu-id="abfb0-147">Le mode Données affiche une grille de données dont vous pouvez vous servir pour modifier les fichiers .xml.</span><span class="sxs-lookup"><span data-stu-id="abfb0-147">Data view provides a data grid that can be used to modify .xml files.</span></span> <span data-ttu-id="abfb0-148">Seul le contenu d'un fichier XML (pas les balises ni la structure) peut être modifié en mode Données.</span><span class="sxs-lookup"><span data-stu-id="abfb0-148">Only the content (but not the tags and structure) in an XML file can be edited in Data view.</span></span>  
  
 <span data-ttu-id="abfb0-149">Il y a deux zones séparées en mode Données : **Tables de données** et **Données**.</span><span class="sxs-lookup"><span data-stu-id="abfb0-149">There are two separate areas in Data view: **Data Tables** and **Data**.</span></span> <span data-ttu-id="abfb0-150">La zone **Tables de données** est une liste des relations définies à l’intérieur du fichier XML, dans l’ordre de leur imbrication (en allant de l’extérieur vers l’intérieur).</span><span class="sxs-lookup"><span data-stu-id="abfb0-150">The **Data Tables** area is a list of relations defined in the XML file, in the order of its nesting (from the outermost to the innermost).</span></span> <span data-ttu-id="abfb0-151">La zone **Données** est une grille de données qui affiche les données en fonction de la sélection effectuée dans la zone Tables de données.</span><span class="sxs-lookup"><span data-stu-id="abfb0-151">The **Data** area is a data grid that displays data based on the selection in the Data Tables area.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="abfb0-152">Les fichiers XML nouvellement créés ne contiennent pas de données et ne peuvent donc pas être affichés en mode Données.</span><span class="sxs-lookup"><span data-stu-id="abfb0-152">Newly created XML files contain no data and therefore cannot be displayed in Data view.</span></span> <span data-ttu-id="abfb0-153">Il existe également certaines instances de documents XML où il est impossible d'appeler le mode Données.</span><span class="sxs-lookup"><span data-stu-id="abfb0-153">There are also some instances of XML documents where data view cannot be invoked at all.</span></span> <span data-ttu-id="abfb0-154">Même si le document XML est considéré comme correct, si les données essayant de passer en mode Données ne sont pas structurées, le message suivant s'affiche : « Bien que ce document soit correctement construit, il contient une structure impossible à afficher en mode Données. »</span><span class="sxs-lookup"><span data-stu-id="abfb0-154">Although the XML would be considered well formed, if it is not structured data trying to switch to Data view will generate the following message: "Although this document is well formed, it contains structure that Data View cannot display."</span></span>  
  
 <span data-ttu-id="abfb0-155">En mode Données, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="abfb0-155">In Data view you can:</span></span>  
  
-   <span data-ttu-id="abfb0-156">remplir les tables de données manuellement ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-156">Manually populate data tables</span></span>  
  
-   <span data-ttu-id="abfb0-157">modifier les tables de données existantes ;</span><span class="sxs-lookup"><span data-stu-id="abfb0-157">Edit existing data tables</span></span>  
  
-   <span data-ttu-id="abfb0-158">générer un schéma XML à partir d'un document XML.</span><span class="sxs-lookup"><span data-stu-id="abfb0-158">Generate an XML Schema from an XML document</span></span>  
  
## <a name="xml-view"></a><span data-ttu-id="abfb0-159">Mode XML</span><span class="sxs-lookup"><span data-stu-id="abfb0-159">XML View</span></span>  
 <span data-ttu-id="abfb0-160">Le mode XML fournit un éditeur pour modifier le XML brut, IntelliSense et un codage en couleurs.</span><span class="sxs-lookup"><span data-stu-id="abfb0-160">XML view provides an editor for editing raw XML and provides IntelliSense and color coding.</span></span> <span data-ttu-id="abfb0-161">La saisie semi-automatique des instructions est disponible lorsque vous travaillez sur des fichiers .xsd et .xml auxquels est associé un schéma.</span><span class="sxs-lookup"><span data-stu-id="abfb0-161">Statement completion is available when working on .xsd files and .xml files that have an associated schema.</span></span> <span data-ttu-id="abfb0-162">Tapez \< pour initialiser une étiquette. une liste d’éléments valides à cet emplacement s’affiche.</span><span class="sxs-lookup"><span data-stu-id="abfb0-162">Type \< to initiate a tag and you will be presented with a list of elements that are valid at that location.</span></span> <span data-ttu-id="abfb0-163">Après avoir tapé le nom de l'élément et appuyé sur la barre d'espace, la liste des attributs pris en charge par l'élément s'affiche.</span><span class="sxs-lookup"><span data-stu-id="abfb0-163">After you type the element name and press the SPACEBAR, you will be presented with a list of attributes that the element supports.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="abfb0-164">IntelliSense ne sont pas disponibles sur la barre d'outils.</span><span class="sxs-lookup"><span data-stu-id="abfb0-164">IntelliSense options are not available on the toolbar.</span></span> <span data-ttu-id="abfb0-165">Pour accéder à ces options lorsque vous êtes dans l'Éditeur XML, dans le menu **Edition** , cliquez sur **IntelliSense**.</span><span class="sxs-lookup"><span data-stu-id="abfb0-165">When in the XML Editor, to access the options, on the **Edit** menu, click **IntelliSense**.</span></span>  
  
## <a name="showplan-view"></a><span data-ttu-id="abfb0-166">Mode SHOWPLAN</span><span class="sxs-lookup"><span data-stu-id="abfb0-166">SHOWPLAN view</span></span>  
 <span data-ttu-id="abfb0-167">Les plans de requête peuvent être enregistrés au format XML lorsqu'ils sont créés à l'aide de l'option SET SHOWPLAN_XML ON.</span><span class="sxs-lookup"><span data-stu-id="abfb0-167">Query plans can be saved in XML format when created using SET SHOWPLAN_XML ON option.</span></span> <span data-ttu-id="abfb0-168">Double-cliquez sur un fichier se terminant par l'extension .showplan pour ouvrir le plan de requête.</span><span class="sxs-lookup"><span data-stu-id="abfb0-168">Double-click a file with the .showplan extension to open the query plan.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abfb0-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="abfb0-169">See Also</span></span>  
 [<span data-ttu-id="abfb0-170">Enregistrer un plan d’exécution au format XML</span><span class="sxs-lookup"><span data-stu-id="abfb0-170">Save an Execution Plan in XML Format</span></span>](../performance/save-an-execution-plan-in-xml-format.md)  
  
  
