---
title: Destination Excel | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.exceldest.f1
helpviewer_keywords:
- destinations [Integration Services], Excel
- Excel [Integration Services]
ms.assetid: 37c07446-1264-4814-b4f5-9c66d333bb24
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 3e959f14e52fc045cb0cbc2ba0255d20bd0356d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709804"
---
# <a name="excel-destination"></a><span data-ttu-id="26c41-102">Destination Excel</span><span class="sxs-lookup"><span data-stu-id="26c41-102">Excel Destination</span></span>
  <span data-ttu-id="26c41-103">La destination Excel charge les données dans des feuilles de calcul ou des plages au sein de classeurs [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel.</span><span class="sxs-lookup"><span data-stu-id="26c41-103">The Excel destination loads data into worksheets or ranges in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel workbooks.</span></span>  
  
## <a name="access-modes"></a><span data-ttu-id="26c41-104">Modes d'accès</span><span class="sxs-lookup"><span data-stu-id="26c41-104">Access Modes</span></span>  
 <span data-ttu-id="26c41-105">La destination Excel propose trois modes d'accès différents pour charger les données :</span><span class="sxs-lookup"><span data-stu-id="26c41-105">The Excel destination provides three different data access modes for loading data:</span></span>  
  
-   <span data-ttu-id="26c41-106">Une table ou une vue.</span><span class="sxs-lookup"><span data-stu-id="26c41-106">A table or view.</span></span>  
  
-   <span data-ttu-id="26c41-107">Une table ou une vue spécifiée dans une variable.</span><span class="sxs-lookup"><span data-stu-id="26c41-107">A table or view specified in a variable.</span></span>  
  
-   <span data-ttu-id="26c41-108">Les résultats d'une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="26c41-108">The results of an SQL statement.</span></span> <span data-ttu-id="26c41-109">La requête peut être une requête paramétrable.</span><span class="sxs-lookup"><span data-stu-id="26c41-109">The query can be a parameterized query.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="26c41-110">Dans Excel, une feuille de calcul ou une plage sont l'équivalent d'une table ou d'une vue.</span><span class="sxs-lookup"><span data-stu-id="26c41-110">In Excel, a worksheet or range is the equivalent of a table or view.</span></span> <span data-ttu-id="26c41-111">Les listes de tables disponibles dans l'Éditeur de source Excel et l'Éditeur de destination Excel contiennent uniquement les feuilles de calcul (identifiées par le signe $ qui est ajouté au nom de la feuille de calcul, comme dans Feuille1$) et plages nommées (identifiées par l'absence de signe $, comme dans MaPlage) existantes.</span><span class="sxs-lookup"><span data-stu-id="26c41-111">The lists of available tables in the Excel Source and Destination editors display only existing worksheets (identified by the $ sign appended to the worksheet name, such as Sheet1$) and named ranges (identified by the absence of the $ sign, such as MyRange).</span></span>  
  
## <a name="usage-considerations"></a><span data-ttu-id="26c41-112">Considérations sur l'utilisation</span><span class="sxs-lookup"><span data-stu-id="26c41-112">Usage Considerations</span></span>  
 <span data-ttu-id="26c41-113">Le gestionnaire de connexions Excel utilise le fournisseur [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB pour Jet version 4.0 et son pilote de prise en charge Excel ISAM (Indexed Sequential Access Method) pour se connecter puis lire et écrire les données dans les sources de données Excel.</span><span class="sxs-lookup"><span data-stu-id="26c41-113">The Excel Connection Manager uses the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for Jet 4.0 and its supporting Excel ISAM (Indexed Sequential Access Method) driver to connect and read and write data to Excel data sources.</span></span>  
  
 <span data-ttu-id="26c41-114">De nombreux articles disponibles dans la Base de connaissances [!INCLUDE[msCoName](../../includes/msconame-md.md)] documentent le comportement de ce fournisseur et de ce pilote et, bien que ces articles ne soient pas spécifiques à [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ou à son prédécesseur DTS (Data Transformation Services), vous pouvez souhaiter vous informer sur certains comportements susceptibles de produire des résultats inattendus.</span><span class="sxs-lookup"><span data-stu-id="26c41-114">Many existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] Knowledge Base articles document the behavior of this provider and driver, and although these articles are not specific to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] or its predecessor Data Transformation Services, you may want to know about certain behaviors that can lead to unexpected results.</span></span> <span data-ttu-id="26c41-115">Pour obtenir des informations générales sur l'utilisation et le comportement du pilote Excel, consultez [COMMENT FAIRE : Utiliser ADO avec des données Excel à partir de Visual Basic ou de VBA](https://support.microsoft.com/kb/257819).</span><span class="sxs-lookup"><span data-stu-id="26c41-115">For general information on the use and behavior of the Excel driver, see [HOWTO: Use ADO with Excel Data from Visual Basic or VBA](https://support.microsoft.com/kb/257819).</span></span>  
  
 <span data-ttu-id="26c41-116">Les comportements suivants du fournisseur Jet inclus avec le pilote Excel peuvent provoquer des résultats inattendus lors de l'enregistrement des données vers une destination Excel.</span><span class="sxs-lookup"><span data-stu-id="26c41-116">The following behaviors of the Jet provider that is included with the Excel driver can lead to unexpected results when saving data to an Excel destination.</span></span>  
  
-   <span data-ttu-id="26c41-117">**Enregistrement des données texte**.</span><span class="sxs-lookup"><span data-stu-id="26c41-117">**Saving text data**.</span></span> <span data-ttu-id="26c41-118">Lorsque le pilote Excel enregistre des valeurs de données texte vers une destination Excel, le pilote fait précéder le texte contenu dans chaque cellule de l'apostrophe (') pour que les valeurs enregistrées soient bien interprétées comme des valeurs texte.</span><span class="sxs-lookup"><span data-stu-id="26c41-118">When the Excel driver saves text data values to an Excel destination, the driver precedes the text in each cell with the single quote character (') to ensure that the saved values will be interpreted as text values.</span></span> <span data-ttu-id="26c41-119">Si vous possédez ou développez des applications qui lisent ou traitent les données enregistrées, peut-être serez-vous amené, dans ce cas précis, à inclure un traitement spécial pour l'apostrophe.</span><span class="sxs-lookup"><span data-stu-id="26c41-119">If you have or develop other applications that read or process the saved data, you may need to include special handling for the single quote character that precedes each text value.</span></span>  
  
     <span data-ttu-id="26c41-120">Pour plus d'informations sur la façon d'inclure l'apostrophe, consultez le billet de blog, [Une apostrophe est ajoutée à toutes les chaînes quand des données sont transformées dans excel lors de l'utilisation d'un composant de flux de données de destination Excel dans un package SSIS](https://go.microsoft.com/fwlink/?LinkId=400876), sur msdn.com.</span><span class="sxs-lookup"><span data-stu-id="26c41-120">For information on how to avoid including the single quote, see this blog post, [Single quote is appended to all strings when data is transformed to excel when using Excel destination data flow component in SSIS package](https://go.microsoft.com/fwlink/?LinkId=400876), on msdn.com.</span></span>  
  
-   <span data-ttu-id="26c41-121">**Enregistrement des données mémo (ntext)**.</span><span class="sxs-lookup"><span data-stu-id="26c41-121">**Saving memo (ntext) da**ta.</span></span> <span data-ttu-id="26c41-122">Avant de pouvoir enregistrer des chaînes dépassant 255 caractères dans une colonne Excel, le pilote doit reconnaître le type de données de la colonne de destination comme **mémo** et non comme **chaîne**.</span><span class="sxs-lookup"><span data-stu-id="26c41-122">Before you can successfully save strings longer than 255 characters to an Excel column, the driver must recognize the data type of the destination column as **memo** and not **string**.</span></span> <span data-ttu-id="26c41-123">Si la table de destination contient déjà des lignes de données, les premières lignes échantillonnées par le pilote doivent contenir au moins une instance d'une valeur dépassant 255 caractères dans la colonne mémo.</span><span class="sxs-lookup"><span data-stu-id="26c41-123">If the destination table already contains rows of data, then the first few rows that are sampled by the driver must contain at least one instance of a value longer than 255 characters in the memo column.</span></span> <span data-ttu-id="26c41-124">Si la table de destination est créée pendant la conception du package ou au moment de l’exécution, l’instruction CREATE TABLE doit utiliser LONGTEXT (ou l’un de ses synonymes) comme type de données de la colonne MEMO.</span><span class="sxs-lookup"><span data-stu-id="26c41-124">If the destination table is created during package design or at run time, then the CREATE TABLE statement must use LONGTEXT (or one of its synonyms) as the data type of the memo column.</span></span>  
  
-   <span data-ttu-id="26c41-125">**Types de données**.</span><span class="sxs-lookup"><span data-stu-id="26c41-125">**Data types**.</span></span> <span data-ttu-id="26c41-126">Le pilote Excel ne reconnaît qu'un ensemble limité de types de données.</span><span class="sxs-lookup"><span data-stu-id="26c41-126">The Excel driver recognizes only a limited set of data types.</span></span> <span data-ttu-id="26c41-127">Par exemple, toutes les colonnes numériques sont interprétées comme doubles (DT_R8) et toutes les colonnes de type chaîne (autres que les colonnes mémo) comme des chaînes Unicode de 255 caractères (DT_WSTR).</span><span class="sxs-lookup"><span data-stu-id="26c41-127">For example, all numeric columns are interpreted as doubles (DT_R8), and all string columns (other than memo columns) are interpreted as 255-character Unicode strings (DT_WSTR).</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="26c41-128">mappe les types de données Excel de la façon suivante :</span><span class="sxs-lookup"><span data-stu-id="26c41-128">maps the Excel data types as follows:</span></span>  
  
    -   <span data-ttu-id="26c41-129">Numérique    virgule flottante double précision (DT_R8)</span><span class="sxs-lookup"><span data-stu-id="26c41-129">Numeric    double-precision float (DT_R8)</span></span>  
  
    -   <span data-ttu-id="26c41-130">Devise     devise (DT_CY)</span><span class="sxs-lookup"><span data-stu-id="26c41-130">Currency     currency (DT_CY)</span></span>  
  
    -   <span data-ttu-id="26c41-131">Booléen     booléen (DT_BOOL)</span><span class="sxs-lookup"><span data-stu-id="26c41-131">Boolean     Boolean (DT_BOOL)</span></span>  
  
    -   <span data-ttu-id="26c41-132">Date/heure `datetime` (DT_DATE)</span><span class="sxs-lookup"><span data-stu-id="26c41-132">Date/time     `datetime` (DT_DATE)</span></span>  
  
    -   <span data-ttu-id="26c41-133">Chaîne     chaîne Unicode, longueur 255 (DT_WSTR)</span><span class="sxs-lookup"><span data-stu-id="26c41-133">String     Unicode string, length 255 (DT_WSTR)</span></span>  
  
    -   <span data-ttu-id="26c41-134">Mémo     flux de texte Unicode (DT_NTEXT)</span><span class="sxs-lookup"><span data-stu-id="26c41-134">Memo     Unicode text stream (DT_NTEXT)</span></span>  
  
-   <span data-ttu-id="26c41-135">**Conversions de type et de longueur de données**.</span><span class="sxs-lookup"><span data-stu-id="26c41-135">**Data type and length conversions**.</span></span> [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="26c41-136">ne convertit pas implicitement les types de données.</span><span class="sxs-lookup"><span data-stu-id="26c41-136">does not implicitly convert data types.</span></span> <span data-ttu-id="26c41-137">Par conséquent, peut-être devrez-vous utiliser les transformations de conversion de données et de colonne dérivée pour convertir explicitement des données Excel avant chargement dans une destination non-Excel ou pour convertir des données non-Excel avant chargement dans une destination Excel.</span><span class="sxs-lookup"><span data-stu-id="26c41-137">As a result, you may need to use the Derived Column or Data Conversion transformations to convert Excel data explicitly before loading it into a non-Excel destination, or to convert non-Excel data before loading it into an Excel destination.</span></span> <span data-ttu-id="26c41-138">Dans ce cas, il peut être utile de créer le package initial à l'aide de l'Assistant Importation et Exportation, qui configure les conversions nécessaires automatiquement.</span><span class="sxs-lookup"><span data-stu-id="26c41-138">In this case, it may be useful to create the initial package by using the Import and Export Wizard, which configures the necessary conversions for you.</span></span> <span data-ttu-id="26c41-139">Des exemples de conversions pouvant être requises sont présentées ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="26c41-139">Some examples of the conversions that may be required include the following:</span></span>  
  
    -   <span data-ttu-id="26c41-140">conversion entre des colonnes Unicode Excel de type chaîne et des colonnes non-Unicode de type chaîne avec des pages de codes spécifiques ;</span><span class="sxs-lookup"><span data-stu-id="26c41-140">Conversion between Unicode Excel string columns and non-Unicode string columns with specific codepages.</span></span>  
  
    -   <span data-ttu-id="26c41-141">conversion entre des colonnes Excel de type chaîne de 255 caractères et des colonnes de type chaîne de longueurs différentes ;</span><span class="sxs-lookup"><span data-stu-id="26c41-141">Conversion between 255-character Excel string columns and string columns of different lengths.</span></span>  
  
    -   <span data-ttu-id="26c41-142">conversion entre des colonnes numériques Excel à double précision et des colonnes numériques d'autres types.</span><span class="sxs-lookup"><span data-stu-id="26c41-142">Conversion between double-precision Excel numeric columns and numeric columns of other types.</span></span>  
  
## <a name="configuration-of-the-excel-destination"></a><span data-ttu-id="26c41-143">Configuration de la destination Excel</span><span class="sxs-lookup"><span data-stu-id="26c41-143">Configuration of the Excel Destination</span></span>  
 <span data-ttu-id="26c41-144">La destination Excel utilise un gestionnaire de connexions Excel pour se connecter à une source de données et le gestionnaire de connexions indique le fichier de feuille de calcul à utiliser.</span><span class="sxs-lookup"><span data-stu-id="26c41-144">The Excel destination uses an Excel connection manager to connect to a data source, and the connection manager specifies the workbook file to use.</span></span> <span data-ttu-id="26c41-145">Pour plus d'informations, consultez [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="26c41-145">For more information, see [Excel Connection Manager](../connection-manager/excel-connection-manager.md).</span></span>  
  
 <span data-ttu-id="26c41-146">La destination Excel comporte une entrée normale et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="26c41-146">The Excel destination has one regular input and one error output.</span></span>  
  
 <span data-ttu-id="26c41-147">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="26c41-147">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="26c41-148">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur de destination Excel** , cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="26c41-148">For more information about the properties that you can set in the **Excel Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="26c41-149">Éditeur de destination Excel &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="26c41-149">Excel Destination Editor &#40;Connection Manager Page&#41;</span></span>](../excel-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="26c41-150">Éditeur de destination Excel &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="26c41-150">Excel Destination Editor &#40;Mappings Page&#41;</span></span>](../excel-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="26c41-151">Éditeur de destination Excel &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="26c41-151">Excel Destination Editor &#40;Error Output Page&#41;</span></span>](../excel-destination-editor-error-output-page.md)  
  
 <span data-ttu-id="26c41-152">La boîte de dialogue **Éditeur avancé** reflète toutes les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="26c41-152">The **Advanced Editor** dialog box reflects all the properties that can be set programmatically.</span></span> <span data-ttu-id="26c41-153">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="26c41-153">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="26c41-154">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="26c41-154">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="26c41-155">Propriétés personnalisées d'Excel</span><span class="sxs-lookup"><span data-stu-id="26c41-155">Excel Custom Properties</span></span>](excel-custom-properties.md)  
  
 <span data-ttu-id="26c41-156">Pour plus d’informations sur la façon de définir les propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="26c41-156">For more information about how to set properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="26c41-157">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="26c41-157">Related Tasks</span></span>  
  
-   [<span data-ttu-id="26c41-158">Importer des données à partir d’Excel ou exporter des données vers Excel avec SQL Server Integration Services (SSIS)</span><span class="sxs-lookup"><span data-stu-id="26c41-158">Import data from Excel or export data to Excel with SQL Server Integration Services (SSIS)</span></span>](../load-data-to-from-excel-with-ssis.md)  
  
-   [<span data-ttu-id="26c41-159">Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach</span><span class="sxs-lookup"><span data-stu-id="26c41-159">Loop through Excel Files and Tables by Using a Foreach Loop Container</span></span>](../control-flow/foreach-loop-container.md)  
  
-   [<span data-ttu-id="26c41-160">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="26c41-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="see-also"></a><span data-ttu-id="26c41-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26c41-161">See Also</span></span>  
 <span data-ttu-id="26c41-162">[Source Excel](excel-source.md) </span><span class="sxs-lookup"><span data-stu-id="26c41-162">[Excel Source](excel-source.md) </span></span>  
 <span data-ttu-id="26c41-163">[Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="26c41-163">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="26c41-164">[Flux de données](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="26c41-164">[Data Flow](data-flow.md) </span></span>  
 [<span data-ttu-id="26c41-165">Utilisation de fichiers Excel avec la tâche de script</span><span class="sxs-lookup"><span data-stu-id="26c41-165">Working with Excel Files with the Script Task</span></span>](../extending-packages-scripting-task-examples/working-with-excel-files-with-the-script-task.md)  
  
  
