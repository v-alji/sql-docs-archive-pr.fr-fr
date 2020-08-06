---
title: Source ODBC | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.f1
ms.assetid: abcf34eb-9140-4100-82e6-b85bccd22abe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 792557839d60f34bdf944dab150959d4df7cb8cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602931"
---
# <a name="odbc-source"></a><span data-ttu-id="d4ee5-102">Source ODBC</span><span class="sxs-lookup"><span data-stu-id="d4ee5-102">ODBC Source</span></span>
  <span data-ttu-id="d4ee5-103">La source ODBC extrait les données d'une base de données compatible ODBC à l'aide d'une table de base de données, d'une vue ou d'une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-103">The ODBC source extracts data from ODBC-supported database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="d4ee5-104">La source ODBC utilise les modes d'accès aux données suivants pour extraire les données :</span><span class="sxs-lookup"><span data-stu-id="d4ee5-104">The ODBC source has the following data access modes for extracting data:</span></span>  
  
-   <span data-ttu-id="d4ee5-105">Une table ou une vue.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-105">A table or view.</span></span>  
  
-   <span data-ttu-id="d4ee5-106">Les résultats d'une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-106">The results of an SQL statement.</span></span>  
  
 <span data-ttu-id="d4ee5-107">La source utilise un gestionnaire de connexions ODBC qui spécifie le fournisseur à utiliser.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-107">The source uses an ODBC connection manager, which specifies the provider to use.</span></span>  
  
 <span data-ttu-id="d4ee5-108">Une source ODBC inclut les colonnes de sortie de données sources.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-108">An ODBC source includes the source data output columns.</span></span> <span data-ttu-id="d4ee5-109">Lorsque les colonnes de sortie sont mappées dans la destination ODBC aux colonnes de destination, des erreurs peuvent se produire si aucune colonne de sortie n'est mappée aux colonnes de destination.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-109">When output columns are mapped in the ODBC destination to the destination columns, errors may occur if no output columns are mapped to the destination columns.</span></span> <span data-ttu-id="d4ee5-110">Même si des colonnes de types différents peuvent être mappées, si les données de sortie ne sont pas compatibles pour la destination, une erreur se produit au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-110">Columns of different types can be mapped, however if the output data is not compatible for the destination then an error occurs at runtime.</span></span> <span data-ttu-id="d4ee5-111">En fonction du comportement des erreurs, l'erreur sera ignorée, entraînera un échec ou la ligne sera envoyée à la sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-111">Depending on the error behavior, setting the error will be ignored, cause a failure, or the row is sent to the error output.</span></span>  
  
 <span data-ttu-id="d4ee5-112">La source ODBC a une sortie normale et une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-112">The ODBC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="d4ee5-113">Gestion des erreurs</span><span class="sxs-lookup"><span data-stu-id="d4ee5-113">Error Handling</span></span>  
 <span data-ttu-id="d4ee5-114">La source ODBC a une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-114">The ODBC source has an error output.</span></span> <span data-ttu-id="d4ee5-115">La sortie d'erreur du composant contient les colonnes de sortie suivantes :</span><span class="sxs-lookup"><span data-stu-id="d4ee5-115">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="d4ee5-116">**Code d’erreur**: numéro qui correspond à l’erreur actuelle.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-116">**Error Code**: The number that corresponds to the current error.</span></span> <span data-ttu-id="d4ee5-117">Consultez la documentation de la base de données ODBC que vous utilisez pour obtenir une liste d'erreurs.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-117">See the documentation for the ODBC-supported database you are using for a list of errors.</span></span> <span data-ttu-id="d4ee5-118">Pour obtenir la liste des codes d'erreur SSIS, consultez le Guide de référence des erreurs et des événements SSIS.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-118">For a list of SSIS error codes, see the SSIS Error Code and Message Reference.</span></span>  
  
-   <span data-ttu-id="d4ee5-119">**Colonne d’erreur**: colonne source à l’origine de l’erreur (pour les erreurs de conversion).</span><span class="sxs-lookup"><span data-stu-id="d4ee5-119">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="d4ee5-120">Colonnes de données de sortie standard.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-120">The standard output data columns.</span></span>  
  
 <span data-ttu-id="d4ee5-121">Selon le comportement paramétré pour les erreurs, la source ODBC prend en charge les erreurs de retour (conversion de données, troncation) qui se produisent pendant le processus d'extraction dans la sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-121">Depending on the error behavior setting, the ODBC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="d4ee5-122">Pour plus d’informations, consultez [Éditeur de destination ODBC &#40;page Gestionnaire de connexions&#41;](../odbc-destination-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee5-122">For more information, see [ODBC Destination Editor &#40;Connection Manager Page&#41;](../odbc-destination-editor-connection-manager-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="d4ee5-123">Prise en charge du type de données</span><span class="sxs-lookup"><span data-stu-id="d4ee5-123">Data Type Support</span></span>  
 <span data-ttu-id="d4ee5-124">Pour plus d'informations sur les types de données pris en charge par la source ODBC, consultez le Connecteur pour Open Database Connectivity (ODBC) d'Attunity.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-124">For information about the data types supported by the ODBC source, see Connector for Open Database Connectivity (ODBC) by Attunity.</span></span>  
  
## <a name="extract-options"></a><span data-ttu-id="d4ee5-125">Options d'extraction</span><span class="sxs-lookup"><span data-stu-id="d4ee5-125">Extract Options</span></span>  
 <span data-ttu-id="d4ee5-126">La source ODBC s’exécute en mode **Lot** ou **Ligne par ligne** .</span><span class="sxs-lookup"><span data-stu-id="d4ee5-126">The ODBC source operates in either **Batch** or **Row-by-Row** mode.</span></span> <span data-ttu-id="d4ee5-127">Le mode utilisé est déterminé par la propriété **FetchMethod** .</span><span class="sxs-lookup"><span data-stu-id="d4ee5-127">The mode used is determined by the **FetchMethod** property.</span></span> <span data-ttu-id="d4ee5-128">La liste suivante décrit les différents modes.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-128">The following list describes the modes.</span></span>  
  
-   <span data-ttu-id="d4ee5-129">**Lot**: les composants tentent d’utiliser la méthode de récupération la plus efficace en fonction des capacités perçues du fournisseur ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-129">**Batch**: The component attempts to use the most efficient fetch method based on the perceived ODBC provider capabilities.</span></span> <span data-ttu-id="d4ee5-130">Pour la plupart des fournisseurs ODBC modernes, il s’agit de SQLFetchScroll avec une liaison de table (où la taille de la table est déterminée par la propriété **BatchSize** ).</span><span class="sxs-lookup"><span data-stu-id="d4ee5-130">For most modern ODBC providers, this is SQLFetchScroll with array binding (where the array size is determined by the **BatchSize** property).</span></span> <span data-ttu-id="d4ee5-131">Si vous sélectionnez **Lot** et que le fournisseur ne prend pas en charge cette méthode, la destination ODBC bascule automatiquement en mode **Ligne par ligne** .</span><span class="sxs-lookup"><span data-stu-id="d4ee5-131">If you select **Batch** and the provider does not support this method, the ODBC destination automatically switches to the **Row-by-row** mode.</span></span>  
  
-   <span data-ttu-id="d4ee5-132">**Ligne par ligne**: le composant utilise SQLFetch pour extraire les lignes une par une.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-132">**Row-by Row**: The component uses SQLFetch to retrieve the rows one at a time.</span></span>  
  
 <span data-ttu-id="d4ee5-133">Pour plus d’informations sur la propriété **FetchMethod** , consultez [Propriétés personnalisées des sources ODBC](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee5-133">For more information about the **FetchMethod** property, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="parallelism"></a><span data-ttu-id="d4ee5-134">Parallélisme</span><span class="sxs-lookup"><span data-stu-id="d4ee5-134">Parallelism</span></span>  
 <span data-ttu-id="d4ee5-135">Il n'existe aucune limitation quant au nombre de composants de source ODBC pouvant s'exécuter en parallèle sur la même table ou des tables différentes, sur le même ordinateur ou sur des ordinateurs différents (autre que les limites de session globale habituelles).</span><span class="sxs-lookup"><span data-stu-id="d4ee5-135">There is no limitation on the number of ODBC source components that can run in parallel against the same table or different tables, on the same machine or on different machines (other than normal global session limits).</span></span>  
  
 <span data-ttu-id="d4ee5-136">Toutefois, les limites du fournisseur ODBC utilisé peuvent limiter le nombre de connexions simultanées par le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-136">However, limitations of the ODBC provider being used may restrict the number of concurrent connections through the provider.</span></span> <span data-ttu-id="d4ee5-137">Ces limites restreignent le nombre d'instances parallèles prises en charge pour la source ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-137">These limitations limit the number of supported parallel instances possible for the ODBC source.</span></span> <span data-ttu-id="d4ee5-138">Le développeur SSIS doit avoir connaissance des limites de tout fournisseur ODBC utilisé et en tenir compte lors de la génération de packages SSIS.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-138">The SSIS developer must be aware of the limitations of any ODBC provider being used and take them into consideration when building SSIS packages.</span></span>  
  
## <a name="troubleshooting-the-odbc-source"></a><span data-ttu-id="d4ee5-139">Résolution des problèmes liés à la source ODBC</span><span class="sxs-lookup"><span data-stu-id="d4ee5-139">Troubleshooting the ODBC Source</span></span>  
 <span data-ttu-id="d4ee5-140">Vous pouvez consigner dans un journal les appels que la source ODBC effectue vers des fournisseurs de données externes.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-140">You can log the calls that the ODBC source makes to external data providers.</span></span> <span data-ttu-id="d4ee5-141">Cette fonctionnalité de journalisation permet de résoudre des problèmes liés au chargement de données qu'effectue la source ODBC à partir de sources de données externes.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-141">You can use this logging capability to troubleshoot the loading of data from external data sources that the ODBC source performs.</span></span> <span data-ttu-id="d4ee5-142">Pour consigner les appels effectués par la source ODBC à destination de fournisseurs de données externes, activez la trace du gestionnaire de pilotes ODBC.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-142">To log the calls that the ODBC source makes to external data providers, enable the ODBC driver manager trace.</span></span> <span data-ttu-id="d4ee5-143">Pour plus d’informations, consultez la documentation Microsoft intitulée *Génération d’une trace ODBC avec l’administrateur des source de données ODBC*.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-143">For more information, see the Microsoft documentation on *How To Generate an ODBC Trace with ODBC the Data Source Administrator.*</span></span>  
  
## <a name="configuring-the-odbc-source"></a><span data-ttu-id="d4ee5-144">Configuration de la source ODBC</span><span class="sxs-lookup"><span data-stu-id="d4ee5-144">Configuring the ODBC Source</span></span>  
 <span data-ttu-id="d4ee5-145">Vous pouvez définir la source ODBC par programmation ou par le biais du concepteur SSIS.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-145">You can configure the ODBC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="d4ee5-146">Pour plus d’informations, consultez l’une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="d4ee5-146">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="d4ee5-147">Éditeur de source ODBC &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ee5-147">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="d4ee5-148">Éditeur de source ODBC &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ee5-148">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="d4ee5-149">Éditeur de source ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ee5-149">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="d4ee5-150">La boîte de dialogue **Éditeur avancé** contient les propriétés qui peuvent être définies par programme.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-150">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="d4ee5-151">Pour ouvrir la boîte de dialogue **Éditeur avancé** :</span><span class="sxs-lookup"><span data-stu-id="d4ee5-151">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="d4ee5-152">Sur l’écran **Flux de données** de votre projet [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] , cliquez avec le bouton droit sur la source ODBC, puis sélectionnez **Afficher l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="d4ee5-152">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the ODBC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="d4ee5-153">Pour plus d’informations sur les propriétés que vous pouvez définir dans la boîte de dialogue Éditeur avancé, consultez [Propriétés personnalisées des sources ODBC](odbc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="d4ee5-153">For more information about the properties that you can set in the Advanced Editor dialog box, see [ODBC Source Custom Properties](odbc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d4ee5-154">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d4ee5-154">In This Section</span></span>  
  
-   [<span data-ttu-id="d4ee5-155">Éditeur de source ODBC &#40;page Sortie d’erreur&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ee5-155">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../odbc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="d4ee5-156">Éditeur de source ODBC &#40;page Colonnes&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ee5-156">ODBC Source Editor &#40;Columns Page&#41;</span></span>](../odbc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="d4ee5-157">Éditeur de source ODBC &#40;page Gestionnaire de connexions&#41;</span><span class="sxs-lookup"><span data-stu-id="d4ee5-157">ODBC Source Editor &#40;Connection Manager Page&#41;</span></span>](../odbc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="d4ee5-158">Extraire des données à l'aide de la source ODBC</span><span class="sxs-lookup"><span data-stu-id="d4ee5-158">Extract Data by Using the ODBC Source</span></span>](odbc-source.md)  
  
-   [<span data-ttu-id="d4ee5-159">Propriétés personnalisées des sources ODBC</span><span class="sxs-lookup"><span data-stu-id="d4ee5-159">ODBC Source Custom Properties</span></span>](odbc-source-custom-properties.md)  
  
  
