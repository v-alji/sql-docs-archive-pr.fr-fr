---
title: Informations de référence sur les fichiers d’entrée XML (Assistant Paramétrage du moteur de base de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
dev_langs:
- XML
helpviewer_keywords:
- Database Engine Tuning Advisor [SQL Server], XML input files
- input file reference [Database Engine Tuning Advisor]
- XML input files [Database Engine Tuning Advisor]
ms.assetid: 05e5e5f0-d6df-4336-b18e-e9bc2835a766
author: stevestein
ms.author: sstein
ms.openlocfilehash: 3bbd38299e4921db33cbaf318883c2f0a9041d92
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708856"
---
# <a name="xml-input-file-reference-database-engine-tuning-advisor"></a><span data-ttu-id="f6e80-102">Référence des fichiers d'entrée XML (Assistant Paramétrage du moteur de base de données)</span><span class="sxs-lookup"><span data-stu-id="f6e80-102">XML Input File Reference (Database Engine Tuning Advisor)</span></span>
  [!INCLUDE[ssDE](../../includes/ssde-md.md)] <span data-ttu-id="f6e80-103">L’Assistant Paramétrage peut utiliser un fichier d’entrée XML pour paramétrer une base de données.</span><span class="sxs-lookup"><span data-stu-id="f6e80-103">Tuning Advisor can use an XML input file to tune a database.</span></span> <span data-ttu-id="f6e80-104">Ce fichier XML désigne les bases de données, les tables, les fichiers ou tables de charge de travail et les options de paramétrage à utiliser pendant la session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="f6e80-104">This XML file designates which databases, tables, workload files or tables, and tuning options to use for the tuning session.</span></span> <span data-ttu-id="f6e80-105">Vous pouvez également utiliser ce fichier pour indiquer une configuration spécifiée par l'utilisateur afin d'effectuer une évaluation de simulation.</span><span class="sxs-lookup"><span data-stu-id="f6e80-105">You can also use this file to specify a user-specified configuration to perform "what-if" analysis.</span></span>  
  
 <span data-ttu-id="f6e80-106">Un fichier d’entrée XML de l’Assistant Paramétrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] contient une hiérarchie d’éléments XML, chaque élément XML comprenant le texte ou d’autres éléments qui spécifient les paramètres de la session de paramétrage.</span><span class="sxs-lookup"><span data-stu-id="f6e80-106">A [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file contains a hierarchy of XML elements, each containing text or other elements that specify the tuning session settings.</span></span> <span data-ttu-id="f6e80-107">Le fichier d’entrée XML de l’Assistant Paramétrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] doit être conforme aux normes pour le XML correctement formé. Tous les éléments respectent la casse.</span><span class="sxs-lookup"><span data-stu-id="f6e80-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML input file must conform to the standards for well-formed XML, so all element names are case sensitive.</span></span> <span data-ttu-id="f6e80-108">Les éléments sont spécifiés à l'aide de la casse Pascal, ce qui signifie que le premier caractère est en majuscules, tout comme la première lettre des mots concaténés suivants.</span><span class="sxs-lookup"><span data-stu-id="f6e80-108">Elements are specified using Pascal case, which means that the first character is uppercase and the first letter of any subsequent concatenated word is uppercase.</span></span>  
  
 <span data-ttu-id="f6e80-109">Toutes les valeurs d'éléments doivent respecter les conventions d'affectation de noms XML.</span><span class="sxs-lookup"><span data-stu-id="f6e80-109">All element values must conform to XML naming conventions.</span></span> <span data-ttu-id="f6e80-110">Pour plus d’informations sur ces conventions, consultez [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) (Contenu textuel XML) dans la bibliothèque MSDN.</span><span class="sxs-lookup"><span data-stu-id="f6e80-110">For more information about these conventions, see [XML Textual Content](https://go.microsoft.com/fwlink/?LinkId=7614) in the MSDN Library.</span></span>  
  
 <span data-ttu-id="f6e80-111">Notez que ce Guide de référence n'est pas complet.</span><span class="sxs-lookup"><span data-stu-id="f6e80-111">Note that this reference is not comprehensive.</span></span> <span data-ttu-id="f6e80-112">Pour plus d'informations sur tous les éléments que vous pouvez utiliser pour définir une entrée XML, reportez-vous au schéma DTASchema.xsd de l'Assistant Paramétrage du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f6e80-112">For information about all the elements you can use to define XML input, refer to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Tuning Advisor XML schema, DTASchema.xsd.</span></span>  
  
## <a name="xml-declaration"></a><span data-ttu-id="f6e80-113">Déclaration XML</span><span class="sxs-lookup"><span data-stu-id="f6e80-113">XML Declaration</span></span>  
  
-   [<span data-ttu-id="f6e80-114">Données XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-114">XML Data &#40;SQL Server&#41;</span></span>](../../relational-databases/xml/xml-data-sql-server.md)  
  
## <a name="dtaxml-root-element"></a><span data-ttu-id="f6e80-115">Élément racine DTAXML</span><span class="sxs-lookup"><span data-stu-id="f6e80-115">DTAXML Root Element</span></span>  
  
-   [<span data-ttu-id="f6e80-116">DTAXML, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-116">DTAXML Element &#40;DTA&#41;</span></span>](dtaxml-element-dta.md)  
  
## <a name="dtainput-elements"></a><span data-ttu-id="f6e80-117">Éléments DTAInput</span><span class="sxs-lookup"><span data-stu-id="f6e80-117">DTAInput Elements</span></span>  
  
-   [<span data-ttu-id="f6e80-118">DTAInput, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-118">DTAInput Element &#40;DTA&#41;</span></span>](dtainput-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-119">Server, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-119">Server Element &#40;DTA&#41;</span></span>](server-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-120">Workload, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-120">Workload Element &#40;DTA&#41;</span></span>](workload-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-121">Élément TuningOptions &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-121">TuningOptions Element &#40;DTA&#41;</span></span>](tuningoptions-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-122">Configuration, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-122">Configuration Element &#40;DTA&#41;</span></span>](configuration-element-dta.md)  
  
## <a name="server-elements"></a><span data-ttu-id="f6e80-123">Éléments de serveur</span><span class="sxs-lookup"><span data-stu-id="f6e80-123">Server Elements</span></span>  
  
-   [<span data-ttu-id="f6e80-124">Name, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-124">Name Element for Server &#40;DTA&#41;</span></span>](name-element-for-server-dta.md)  
  
-   [<span data-ttu-id="f6e80-125">Database, élément pour les serveurs &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-125">Database Element for Server &#40;DTA&#41;</span></span>](database-element-for-server-dta.md)  
  
## <a name="workload-elements"></a><span data-ttu-id="f6e80-126">Éléments de charge de travail</span><span class="sxs-lookup"><span data-stu-id="f6e80-126">Workload Elements</span></span>  
  
-   [<span data-ttu-id="f6e80-127">Élément File &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-127">File Element &#40;DTA&#41;</span></span>](file-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-128">Élément Database &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-128">Database Element for Workload &#40;DTA&#41;</span></span>](database-element-for-workload-dta.md)  
  
-   [<span data-ttu-id="f6e80-129">Élément EventString &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-129">EventString Element &#40;DTA&#41;</span></span>](eventstring-element-dta.md)  
  
## <a name="tuning-options-elements"></a><span data-ttu-id="f6e80-130">Éléments d'options de paramétrage</span><span class="sxs-lookup"><span data-stu-id="f6e80-130">Tuning Options Elements</span></span>  
  
-   [<span data-ttu-id="f6e80-131">TuningTimeInMin, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-131">TuningTimeInMin Element &#40;DTA&#41;</span></span>](tuningtimeinmin-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-132">StorageBoundInMB, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-132">StorageBoundInMB Element &#40;DTA&#41;</span></span>](storageboundinmb-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-133">TestServer, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-133">TestServer Element &#40;DTA&#41;</span></span>](testserver-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-134">FeatureSet, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-134">FeatureSet Element &#40;DTA&#41;</span></span>](featureset-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-135">Partitioning, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-135">Partitioning Element &#40;DTA&#41;</span></span>](partitioning-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-136">DropOnlyMode, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-136">DropOnlyMode Element &#40;DTA&#41;</span></span>](droponlymode-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-137">KeepExisting, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-137">KeepExisting Element &#40;DTA&#41;</span></span>](keepexisting-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-138">OnlineIndexOperation, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-138">OnlineIndexOperation Element &#40;DTA&#41;</span></span>](onlineindexoperation-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-139">DatabaseToConnect, élément &#40;DTA&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-139">DatabaseToConnect Element &#40;DTA&#41;</span></span>](databasetoconnect-element-dta.md)  
  
## <a name="configuration-elements"></a><span data-ttu-id="f6e80-140">Éléments de configuration</span><span class="sxs-lookup"><span data-stu-id="f6e80-140">Configuration Elements</span></span>  
  
-   [<span data-ttu-id="f6e80-141">Server, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-141">Server Element for Configuration &#40;DTA&#41;</span></span>](server-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="f6e80-142">Database, élément pour les configurations &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-142">Database Element for Configuration &#40;DTA&#41;</span></span>](database-element-for-configuration-dta.md)  
  
-   [<span data-ttu-id="f6e80-143">Recommendation, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-143">Recommendation Element &#40;DTA&#41;</span></span>](recommendation-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-144">Create, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-144">Create Element &#40;DTA&#41;</span></span>](create-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-145">Index, élément &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-145">Index Element &#40;DTA&#41;</span></span>](index-element-dta.md)  
  
-   [<span data-ttu-id="f6e80-146">Name, élément pour les index &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-146">Name Element for Index &#40;DTA&#41;</span></span>](name-element-for-index-dta.md)  
  
-   [<span data-ttu-id="f6e80-147">Column, élément pour les index &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-147">Column Element for Index &#40;DTA&#41;</span></span>](column-element-for-index-dta.md)  
  
-   [<span data-ttu-id="f6e80-148">Name, élément pour les colonnes &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-148">Name Element for Column &#40;DTA&#41;</span></span>](name-element-for-column-dta.md)  
  
-   [<span data-ttu-id="f6e80-149">Filegroup, élément pour les index &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-149">Filegroup Element for Index &#40;DTA&#41;</span></span>](filegroup-element-for-index-dta.md)  
  
## <a name="database-elements"></a><span data-ttu-id="f6e80-150">Éléments de base de données</span><span class="sxs-lookup"><span data-stu-id="f6e80-150">Database Elements</span></span>  
  
-   [<span data-ttu-id="f6e80-151">Name, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-151">Name Element for Database &#40;DTA&#41;</span></span>](name-element-for-database-dta.md)  
  
-   [<span data-ttu-id="f6e80-152">Schema, élément pour les bases de données &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-152">Schema Element for Database &#40;DTA&#41;</span></span>](schema-element-for-database-dta.md)  
  
-   [<span data-ttu-id="f6e80-153">Name, élément pour les schémas &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-153">Name Element for Schema &#40;DTA&#41;</span></span>](name-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="f6e80-154">Table, élément pour les schémas &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-154">Table Element for Schema &#40;DTA&#41;</span></span>](table-element-for-schema-dta.md)  
  
-   [<span data-ttu-id="f6e80-155">Name, élément pour les tables &#40;Assistant Paramétrage de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="f6e80-155">Name Element for Table &#40;DTA&#41;</span></span>](name-element-for-table-dta.md)  
  
## <a name="see-also"></a><span data-ttu-id="f6e80-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6e80-156">See Also</span></span>  
 [<span data-ttu-id="f6e80-157">Database Engine Tuning Advisor</span><span class="sxs-lookup"><span data-stu-id="f6e80-157">Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
