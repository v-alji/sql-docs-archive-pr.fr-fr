---
title: Source CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.f1
ms.assetid: 99775608-e177-44ed-bb44-aaccb0f4f327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 064c25b129364dfcd813d71a462586303dd4ff60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613577"
---
# <a name="cdc-source"></a><span data-ttu-id="96a0e-102">Source CDC</span><span class="sxs-lookup"><span data-stu-id="96a0e-102">CDC Source</span></span>
  <span data-ttu-id="96a0e-103">La source CDC lit une plage de données modifiées dans les tables de modifications de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] et apporte les modifications en aval aux autres composants SSIS.</span><span class="sxs-lookup"><span data-stu-id="96a0e-103">The CDC source reads a range of change data from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables and delivers the changes downstream to other SSIS components.</span></span>  
  
 <span data-ttu-id="96a0e-104">La plage de données modifiées lue par la source CDC est appelée « plage de traitement de capture de données modifiées » et est déterminée par la tâche de contrôle de capture de données modifiées exécutée avant le démarrage du flux de données actuel.</span><span class="sxs-lookup"><span data-stu-id="96a0e-104">The range of change data read by the CDC source is called the CDC Processing Range and is determine by the CDC Control task that is executed before the current data flow starts.</span></span> <span data-ttu-id="96a0e-105">La plage de traitement de capture de données modifiées est dérivée de la valeur d'une variable de package qui gère l'état du traitement de capture de données modifiées pour un groupe de tables.</span><span class="sxs-lookup"><span data-stu-id="96a0e-105">The CDC Processing Range is derived from the value of a package variable that maintains the state of the CDC processing for a group of tables.</span></span>  
  
 <span data-ttu-id="96a0e-106">La source CDC extrait les données d’une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à l’aide d’une table de base de données, d’une vue ou d’une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="96a0e-106">The CDC source extracts data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="96a0e-107">La source CDC utilise les configurations suivantes :</span><span class="sxs-lookup"><span data-stu-id="96a0e-107">The CDC source uses the following configurations:</span></span>  
  
-   <span data-ttu-id="96a0e-108">Un gestionnaire de connexions ADO.NET [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour accéder à la base de données CDC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="96a0e-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET connection manager to access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database.</span></span> <span data-ttu-id="96a0e-109">Pour plus d’informations sur la configuration de la connexion à la source CDC, consultez [Éditeur de source CDC &#40;page Gestionnaire de connexions&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="96a0e-109">For more information about configuring the CDC source connection, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
-   <span data-ttu-id="96a0e-110">Une table pour laquelle la capture de données modifiées est activée.</span><span class="sxs-lookup"><span data-stu-id="96a0e-110">A table enabled for CDC.</span></span>  
  
-   <span data-ttu-id="96a0e-111">Le nom de l'instance de capture de la table sélectionnée (s'il en existe plusieurs).</span><span class="sxs-lookup"><span data-stu-id="96a0e-111">The name of the capture instance of the selected table (if more-than-one exists).</span></span>  
  
-   <span data-ttu-id="96a0e-112">Le mode de traitement des modifications.</span><span class="sxs-lookup"><span data-stu-id="96a0e-112">The change processing mode.</span></span>  
  
-   <span data-ttu-id="96a0e-113">Le nom de la variable de package d'état de capture de données modifiées à partir de laquelle la plage de traitement de capture de données modifiées est déterminée.</span><span class="sxs-lookup"><span data-stu-id="96a0e-113">The name of the CDC state package variable based on which the CDC Processing range is determined.</span></span> <span data-ttu-id="96a0e-114">La source CDC ne modifie pas cette variable.</span><span class="sxs-lookup"><span data-stu-id="96a0e-114">The CDC source does not modify that variable.</span></span>  
  
 <span data-ttu-id="96a0e-115">Les données retournées par la source CDC sont les mêmes que celles retournées par les fonctions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** ou **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (si disponibles).</span><span class="sxs-lookup"><span data-stu-id="96a0e-115">The data returned by the CDC Source is the same as that returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC functions **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** or **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (when available).</span></span> <span data-ttu-id="96a0e-116">Le seul ajout facultatif est la colonne **__$initial_processing** qui indique si la plage de traitement actuelle peut chevaucher une charge initiale de la table.</span><span class="sxs-lookup"><span data-stu-id="96a0e-116">The only optional addition is the column, **__$initial_processing** that indicates whether the current processing range can overlap with an initial load of the table.</span></span> <span data-ttu-id="96a0e-117">Pour plus d’informations sur la traitement initial, consultez [Tâche de contrôle de capture de données modifiées](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="96a0e-117">For more information about initial processing, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="96a0e-118">La source CDC a une sortie normale et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="96a0e-118">The CDC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="96a0e-119">Gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="96a0e-119">Error Handling</span></span>  
 <span data-ttu-id="96a0e-120">la source CDC a une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="96a0e-120">The CDC source has an error output.</span></span> <span data-ttu-id="96a0e-121">La sortie d'erreur du composant contient les colonnes de sortie suivantes :</span><span class="sxs-lookup"><span data-stu-id="96a0e-121">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="96a0e-122">**Code d’erreur**: la valeur est toujours -1.</span><span class="sxs-lookup"><span data-stu-id="96a0e-122">**Error Code**: The value is always -1.</span></span>  
  
-   <span data-ttu-id="96a0e-123">**Colonne d’erreur**: colonne source à l’origine de l’erreur (pour les erreurs de conversion).</span><span class="sxs-lookup"><span data-stu-id="96a0e-123">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="96a0e-124">**Colonnes de ligne d’erreur**: données d’enregistrement à l’origine de l’erreur.</span><span class="sxs-lookup"><span data-stu-id="96a0e-124">**Error Row Columns**: The record data that causes the error.</span></span>  
  
 <span data-ttu-id="96a0e-125">Selon le comportement paramétré pour les erreurs, la source CDC prend en charge les erreurs de retour (conversion de données, troncation) qui se produisent pendant le processus d'extraction dans la sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="96a0e-125">Depending on the error behavior setting, the CDC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="96a0e-126">Pour plus d’informations, consultez [Éditeur de source CDC &#40;page Sortie d’erreur&#41;](../cdc-source-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="96a0e-126">For more information, see [CDC Source Editor &#40;Error Output Page&#41;](../cdc-source-editor-error-output-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="96a0e-127">Prise en charge du type de données</span><span class="sxs-lookup"><span data-stu-id="96a0e-127">Data Type Support</span></span>  
 <span data-ttu-id="96a0e-128">Le composant source CDC pour Microsoft prend en charge tous les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui sont mappés à des types de données SSIS appropriés.</span><span class="sxs-lookup"><span data-stu-id="96a0e-128">The CDC source component for Microsoft supports all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, which are mapped to the correct SSIS data types.</span></span>  
  
## <a name="troubleshooting-the-cdc-source"></a><span data-ttu-id="96a0e-129">Résolution des problèmes liés à la source CDC</span><span class="sxs-lookup"><span data-stu-id="96a0e-129">Troubleshooting the CDC Source</span></span>  
 <span data-ttu-id="96a0e-130">Les éléments suivants contiennent des informations utiles à la résolution des problèmes liés à la source CDC.</span><span class="sxs-lookup"><span data-stu-id="96a0e-130">The following contains information on troubleshooting the CDC source.</span></span>  
  
### <a name="use-this-script-to-isolate-problems-and-reproduce-them-in-sql-server-management-studio"></a><span data-ttu-id="96a0e-131">Utilisez ce script pour isoler les problèmes et les reproduire dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96a0e-131">Use this script to isolate problems and reproduce them in SQL Server Management Studio</span></span>  
 <span data-ttu-id="96a0e-132">L'opération de la source CDC est régie par l'opération de la tâche de contrôle de capture de données modifiées exécutée avant d'appeler la source CDC.</span><span class="sxs-lookup"><span data-stu-id="96a0e-132">The CDC source operation is governed by the operation of the CDC Control task executed before invoking the CDC source.</span></span> <span data-ttu-id="96a0e-133">La tâche de contrôle de capture de données modifiées prépare la valeur de la variable de package d'état de capture de données modifiées de sorte qu'elle contienne le NSE de début et le NSE de fin.</span><span class="sxs-lookup"><span data-stu-id="96a0e-133">The CDC Control task prepares the value of the CDC state package variable to contain the start and end LSNs.</span></span> <span data-ttu-id="96a0e-134">Elle exécute une fonction équivalente au script suivant :</span><span class="sxs-lookup"><span data-stu-id="96a0e-134">It performs function equivalent to the following script:</span></span>  
  
```  
use <cdc-enabled-database-name>  
               declare @start_lsn binary(10), @end_lsn binary(10)  
               set @start_lsn = sys.fn_cdc_increment_lsn(  
                       convert(binary(10),'0x' + '<value-from-state-cs>', 1))  
               set @end_lsn =   
                       convert(binary(10),'0x' + '<value-from-state-ce>', 1)  
               select * from cdc.fn_cdc_get_net_changes_dbo_Table1(@start_lsn,  
@end_lsn, '<mode>')  
```  
  
 <span data-ttu-id="96a0e-135">où :</span><span class="sxs-lookup"><span data-stu-id="96a0e-135">where:</span></span>  
  
-   <span data-ttu-id="96a0e-136">\<cdc-enabled-database-name> est le nom de la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contenant les tables de modifications.</span><span class="sxs-lookup"><span data-stu-id="96a0e-136">\<cdc-enabled-database-name> is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database containing the change tables.</span></span>  
  
-   <span data-ttu-id="96a0e-137">\<value-from-state-cs> est la valeur affichée dans la variable d’état de capture des changements de données sous la forme CS/\<value-from-state-cs>/ (CS correspond à Current-processing-range-Start, début de la plage de traitement actuelle).</span><span class="sxs-lookup"><span data-stu-id="96a0e-137">\<value-from-state-cs> is the value that appears in the CDC state variable as CS/\<value-from-state-cs>/ (CS stands for Current-processing-range-Start).</span></span>  
  
-   <span data-ttu-id="96a0e-138">\<value-from-state-ce> est la valeur affichée dans la variable d’état de capture des changements de données sous la forme CE/\<value-from-state-cs>/ (CE correspond à Current-processing-range-End, fin de la plage de traitement actuelle).</span><span class="sxs-lookup"><span data-stu-id="96a0e-138">\<value-from-state-ce> is the value that appears in the CDC state variable as CE/\<value-from-state-cs>/ (CE stands for Current-processing-range-End).</span></span>  
  
-   <span data-ttu-id="96a0e-139">\<mode> correspond aux modes de traitement de capture des changements de données.</span><span class="sxs-lookup"><span data-stu-id="96a0e-139">\<mode> are the CDC processing modes.</span></span> <span data-ttu-id="96a0e-140">Les modes de traitement ont l’une des valeurs suivantes : **Tout**, **Tout avec les anciennes valeurs**, **NET**, **Net avec masque de mise à jour**et **Net avec fusion**.</span><span class="sxs-lookup"><span data-stu-id="96a0e-140">The processing modes have one of the following values **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span></span>  
  
 <span data-ttu-id="96a0e-141">Ce script aide à isoler les problèmes en les reproduisant dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], où il est facile de reproduire et d'identifier des erreurs.</span><span class="sxs-lookup"><span data-stu-id="96a0e-141">This script helps isolate problems by reproducing them in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], where it is easy to reproduce and identify errors.</span></span>  
  
#### <a name="sql-server-error-message"></a><span data-ttu-id="96a0e-142">Message d'erreur SQL Server</span><span class="sxs-lookup"><span data-stu-id="96a0e-142">SQL Server Error Message</span></span>  
 <span data-ttu-id="96a0e-143">Le message suivant peut être retourné par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="96a0e-143">The following message may be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="96a0e-144">**Nombre d’arguments fournis insuffisant pour la procédure ou la fonction cdc.fn_cdc_get_net_changes_\<..>.**</span><span class="sxs-lookup"><span data-stu-id="96a0e-144">**An insufficient number of arguments were supplied for the procedure or function cdc.fn_cdc_get_net_changes_\<..>.**</span></span>  
  
 <span data-ttu-id="96a0e-145">Cette erreur n'indique pas qu'un argument est manquant.</span><span class="sxs-lookup"><span data-stu-id="96a0e-145">This error does not indicate that an argument is missing.</span></span> <span data-ttu-id="96a0e-146">Elle signifie que les valeurs du NSE de début ou du NSE de fin dans la variable d'état de capture de données modifiées ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="96a0e-146">It means that the start or end LSN values in the CDC state variable are invalid.</span></span>  
  
## <a name="configuring-the-cdc-source"></a><span data-ttu-id="96a0e-147">Configuration de la source CDC</span><span class="sxs-lookup"><span data-stu-id="96a0e-147">Configuring the CDC Source</span></span>  
 <span data-ttu-id="96a0e-148">Vous pouvez configurer la source CDC par programme ou par le biais du concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="96a0e-148">You can configure the CDC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="96a0e-149">Pour plus d’informations, consultez l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="96a0e-149">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="96a0e-150">Éditeur de source CDC &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="96a0e-150">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="96a0e-151">Éditeur de source CDC &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="96a0e-151">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="96a0e-152">Éditeur de source CDC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="96a0e-152">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="96a0e-153">La boîte de dialogue **Éditeur avancé** contient les propriétés qui peuvent être définies par programme.</span><span class="sxs-lookup"><span data-stu-id="96a0e-153">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="96a0e-154">Pour ouvrir la boîte de dialogue **Éditeur avancé** :</span><span class="sxs-lookup"><span data-stu-id="96a0e-154">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="96a0e-155">Dans l’écran **Flux de données** de votre projet [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , cliquez avec le bouton droit sur la source CDC, puis sélectionnez **Afficher l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="96a0e-155">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="96a0e-156">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue **Éditeur avancé** , consultez [Propriétés personnalisées des sources CDC](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="96a0e-156">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96a0e-157">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="96a0e-157">In This Section</span></span>  
  
-   [<span data-ttu-id="96a0e-158">Éditeur de source CDC &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="96a0e-158">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="96a0e-159">Éditeur de source CDC &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="96a0e-159">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="96a0e-160">Éditeur de source CDC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="96a0e-160">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="96a0e-161">Propriétés personnalisées des sources CDC</span><span class="sxs-lookup"><span data-stu-id="96a0e-161">CDC Source Custom Properties</span></span>](cdc-source-custom-properties.md)  
  
-   [<span data-ttu-id="96a0e-162">Extraire des données modifiées à l’aide de la source de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="96a0e-162">Extract Change Data Using the CDC Source</span></span>](cdc-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="96a0e-163">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="96a0e-163">Related Content</span></span>  
  
-   <span data-ttu-id="96a0e-164">Entrée de blog, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/)(Modes de traitement pour la source CDC), sur mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="96a0e-164">Blog entry, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), on mattmasson.com.</span></span>  
  
  
