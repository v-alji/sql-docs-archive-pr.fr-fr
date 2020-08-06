---
title: Propriétés du journal | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- QueryLogFileSize property
- QueryLogTableName property
- TraceBackgroundDistributionPeriod property
- TraceMaxRowsetSize property
- NullKeyConvertedToUnknown property
- CrashReportsFolder property
- TraceDefinitionFile property
- SQLDumperFlagsOn property
- KeyErrorLimit property
- SnapshotDefinitionFile property
- MinidumpErrorList property
- ErrorLogFileName property
- KeyDuplicate property
- IgnoreDataTruncation property
- logs [Analysis Services]
- Enabled property
- FileSizeMB property
- TraceFileWriteTrailerPeriod property
- TraceQueryResponseTextChunkSize property
- File property
- FileBufferSize property
- TraceRowsetBackgroundFlushPeriod property
- ErrorLogFileSize property
- TraceRequestParameters property
- KeyErrorLimitAction property
- CreateQueryLogTable property
- LogDir property
- TraceBackgroundFlushPeriod property
- TraceFileBufferSize property
- SQLDumperFlagsOff property
- QueryLogConnectionString property
- KeyNotFound property
- KeyErrorLogFile property
- TraceReportFQDN property
- KeyErrorAction property
- QueryLogFileName property
- MessageLogs property
- MiniDumpFlagsOn property
- SnapshotFrequencySec property
- QueryLogSampling property
- CreateAndSendCrashReports property
- LogDurationSec property
ms.assetid: 33fd90ee-cead-48f0-8ff9-9b458994c766
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3761ce3dca232db8968a2a7cba083dcc5554d792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710847"
---
# <a name="log-properties"></a><span data-ttu-id="e9b19-102">Propriétés du journal</span><span class="sxs-lookup"><span data-stu-id="e9b19-102">Log Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="e9b19-103">prend en charge les propriétés de serveur de journal répertoriées dans les tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="e9b19-103">supports the log server properties listed in the following tables.</span></span> <span data-ttu-id="e9b19-104">Pour plus d'informations sur les autres propriétés de serveur et la façon de les configurer, consultez [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9b19-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
## <a name="general"></a><span data-ttu-id="e9b19-105">Général</span><span class="sxs-lookup"><span data-stu-id="e9b19-105">General</span></span>  
 `File`  
 <span data-ttu-id="e9b19-106">Propriété de type chaîne qui spécifie le nom du fichier journal du serveur.</span><span class="sxs-lookup"><span data-stu-id="e9b19-106">A string property that identifies the name of the server log file.</span></span> <span data-ttu-id="e9b19-107">Cette propriété s'applique uniquement si vous utilisez un fichier sur disque pour l'enregistrement, au lieu d'une table de base de données (comportement par défaut).</span><span class="sxs-lookup"><span data-stu-id="e9b19-107">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="e9b19-108">La valeur par défaut de cette propriété est msmdsrv.log.</span><span class="sxs-lookup"><span data-stu-id="e9b19-108">The default value for this property is msmdsrv.log.</span></span>  
  
 `FileBufferSize`  
 <span data-ttu-id="e9b19-109">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MessageLogs`  
 <span data-ttu-id="e9b19-110">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="error-log"></a><span data-ttu-id="e9b19-111">Journal des erreurs de SQL Server</span><span class="sxs-lookup"><span data-stu-id="e9b19-111">Error Log</span></span>  
 <span data-ttu-id="e9b19-112">Vous pouvez définir ces propriétés au niveau de l'instance du serveur pour modifier les valeurs par défaut de la configuration d'erreur qui s'affichent dans d'autres outils et concepteurs.</span><span class="sxs-lookup"><span data-stu-id="e9b19-112">You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers.</span></span> <span data-ttu-id="e9b19-113">Pour plus d’informations [, consultez Configuration d’erreur pour le traitement des cubes, des partitions et des dimensions &#40;SSAS-multidimensionnel&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="e9b19-113">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.</span></span>  
  
 <span data-ttu-id="e9b19-114">**ErrorLog\ErrorLogFileName**</span><span class="sxs-lookup"><span data-stu-id="e9b19-114">**ErrorLog\ErrorLogFileName**</span></span>  
 <span data-ttu-id="e9b19-115">Propriété utilisée comme valeur par défaut durant une opération de traitement effectuée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="e9b19-115">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="e9b19-116">**ErrorLog\ErrorLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="e9b19-116">**ErrorLog\ErrorLogFileSize**</span></span>  
 <span data-ttu-id="e9b19-117">Propriété utilisée comme valeur par défaut durant une opération de traitement effectuée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="e9b19-117">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="e9b19-118">**ErrorLog\KeyErrorAction**</span><span class="sxs-lookup"><span data-stu-id="e9b19-118">**ErrorLog\KeyErrorAction**</span></span>  
 <span data-ttu-id="e9b19-119">Spécifie l'action que doit entreprendre le serveur en cas d'erreur `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="e9b19-119">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="e9b19-120">Les réponses valides à cette erreur sont :</span><span class="sxs-lookup"><span data-stu-id="e9b19-120">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="e9b19-121">`ConvertToUnknown` indique au serveur d'allouer la valeur de clé d'erreur au membre inconnu.</span><span class="sxs-lookup"><span data-stu-id="e9b19-121">`ConvertToUnknown` tells the server to allocate the error key value to the unknown member.</span></span>  
  
-   <span data-ttu-id="e9b19-122">`DiscardRecord` indique au serveur d'exclure l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e9b19-122">`DiscardRecord` tells the server to exclude the record.</span></span>  
  
 <span data-ttu-id="e9b19-123">**ErrorLog\KeyErrorLogFile**</span><span class="sxs-lookup"><span data-stu-id="e9b19-123">**ErrorLog\KeyErrorLogFile**</span></span>  
 <span data-ttu-id="e9b19-124">Il s'agit d'un nom de fichier défini par l'utilisateur qui doit avoir une extension de fichier .log, situé dans un dossier sur lequel le compte de services dispose des autorisations d'accès en lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="e9b19-124">This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions.</span></span> <span data-ttu-id="e9b19-125">Ce fichier journal contient uniquement les erreurs générées lors du traitement.</span><span class="sxs-lookup"><span data-stu-id="e9b19-125">This log file will only contain errors generated during processing.</span></span> <span data-ttu-id="e9b19-126">Utilisez la Boîte noire si vous avez besoin de plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="e9b19-126">Use the Flight Recorder if you require more detailed information.</span></span>  
  
 <span data-ttu-id="e9b19-127">**ErrorLog\KeyErrorLimit**</span><span class="sxs-lookup"><span data-stu-id="e9b19-127">**ErrorLog\KeyErrorLimit**</span></span>  
 <span data-ttu-id="e9b19-128">Il s'agit du nombre maximal d'erreurs d'intégrité des données que le serveur autorise avant que le traitement échoue.</span><span class="sxs-lookup"><span data-stu-id="e9b19-128">This is the maximum number of data integrity errors that the server will allow before failing the processing.</span></span> <span data-ttu-id="e9b19-129">Une valeur égale à -1 indique un nombre illimité.</span><span class="sxs-lookup"><span data-stu-id="e9b19-129">A value of -1 indicates that there is no limit.</span></span> <span data-ttu-id="e9b19-130">La valeur par défaut est 0, ce qui signifie que le traitement s'arrête après la première erreur.</span><span class="sxs-lookup"><span data-stu-id="e9b19-130">The default is 0, which means processing stops after the first error occurs.</span></span> <span data-ttu-id="e9b19-131">Vous pouvez également définir un nombre entier.</span><span class="sxs-lookup"><span data-stu-id="e9b19-131">You can also set it to a whole number.</span></span>  
  
 <span data-ttu-id="e9b19-132">**ErrorLog\KeyErrorLimitAction**</span><span class="sxs-lookup"><span data-stu-id="e9b19-132">**ErrorLog\KeyErrorLimitAction**</span></span>  
 <span data-ttu-id="e9b19-133">Spécifie l'action entreprise par le serveur lorsque le nombre maximal d'erreurs de clé est atteint.</span><span class="sxs-lookup"><span data-stu-id="e9b19-133">Specifies the action taken by the server when the number of key errors has reached the upper limit.</span></span> <span data-ttu-id="e9b19-134">Les réponses valides à cette action sont :</span><span class="sxs-lookup"><span data-stu-id="e9b19-134">Valid responses to this action include:</span></span>  
  
-   <span data-ttu-id="e9b19-135">`StopProcessing` indique au serveur d'arrêter le traitement lorsque le nombre maximal d'erreurs est atteint.</span><span class="sxs-lookup"><span data-stu-id="e9b19-135">`StopProcessing` tells the server to stop processing when the error limit is reached.</span></span>  
  
-   <span data-ttu-id="e9b19-136">`StopLogging` indique au serveur d'arrêter l'enregistrement des erreurs lorsque le nombre maximal d'erreurs est atteint, mais d'autoriser la poursuite du traitement.</span><span class="sxs-lookup"><span data-stu-id="e9b19-136">`StopLogging` tells the server to stop logging errors when the error limit is reached, but allow processing to continue.</span></span>  
  
 <span data-ttu-id="e9b19-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span><span class="sxs-lookup"><span data-stu-id="e9b19-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span></span>  
 <span data-ttu-id="e9b19-138">Spécifie l'action que doit entreprendre le serveur en cas d'erreur `KeyNotFound`.</span><span class="sxs-lookup"><span data-stu-id="e9b19-138">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="e9b19-139">Les réponses valides à cette erreur sont :</span><span class="sxs-lookup"><span data-stu-id="e9b19-139">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="e9b19-140">`IgnoreError` indique au serveur de poursuivre le traitement sans enregistrer l'erreur ou la compter dans le nombre maximal d'erreurs de clé.</span><span class="sxs-lookup"><span data-stu-id="e9b19-140">`IgnoreError` tells the server to continue processing without logging the error or counting it towards the key error limit.</span></span> <span data-ttu-id="e9b19-141">Lorsque vous ignorez l'erreur, vous permettez au traitement de continuer sans ajouter l'erreur au nombre d'erreurs ou l'enregistrer à l'écran ou dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="e9b19-141">By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file.</span></span> <span data-ttu-id="e9b19-142">L'enregistrement en question rencontre un problème d'intégrité des données et ne peut pas être ajouté à la base de données.</span><span class="sxs-lookup"><span data-stu-id="e9b19-142">The record in question has a data integrity problem and cannot be added to the database.</span></span> <span data-ttu-id="e9b19-143">L'enregistrement est ignoré ou agrégé à un membre inconnu, tel que le détermine la propriété `KeyErrorAction`.</span><span class="sxs-lookup"><span data-stu-id="e9b19-143">The record will either be discarded or aggregated to Unknown Member, as determined by the `KeyErrorAction` property.</span></span>  
  
-   <span data-ttu-id="e9b19-144">`ReportAndContinue` indique au serveur d'enregistrer l'erreur, de la compter dans le nombre maximal d'erreurs de clé et de continuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="e9b19-144">`ReportAndContinue` tells the server to log the error, count it towards the key error limit, and continue processing.</span></span> <span data-ttu-id="e9b19-145">L'enregistrement déclenchant l'erreur est ignoré ou converti en membre inconnu.</span><span class="sxs-lookup"><span data-stu-id="e9b19-145">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
-   <span data-ttu-id="e9b19-146">`ReportAndStop` indique au serveur d'enregistrer l'erreur et d'arrêter le traitement immédiatement, quel que soit le nombre maximal d'erreurs de clé.</span><span class="sxs-lookup"><span data-stu-id="e9b19-146">`ReportAndStop` tells the server to log the error and stop processing immediately, regardless of the key error limit.</span></span> <span data-ttu-id="e9b19-147">L'enregistrement déclenchant l'erreur est ignoré ou converti en membre inconnu.</span><span class="sxs-lookup"><span data-stu-id="e9b19-147">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
 <span data-ttu-id="e9b19-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span><span class="sxs-lookup"><span data-stu-id="e9b19-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span></span>  
 <span data-ttu-id="e9b19-149">Spécifie l'action entreprise par le serveur lorsqu'une clé dupliquée est détectée.</span><span class="sxs-lookup"><span data-stu-id="e9b19-149">Specifies the action taken by the server when a duplicate key is found.</span></span> <span data-ttu-id="e9b19-150">Les valeurs valides sont `IgnoreError` pour continuer le traitement comme si l'erreur ne s'était pas produite, `ReportAndContinue` pour enregistrer l'erreur et continuer le traitement et `ReportAndStop` pour enregistrer l'erreur et arrêter le traitement immédiatement, même si le nombre d'erreurs est inférieur au nombre maximal.</span><span class="sxs-lookup"><span data-stu-id="e9b19-150">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="e9b19-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span><span class="sxs-lookup"><span data-stu-id="e9b19-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span></span>  
 <span data-ttu-id="e9b19-152">Spécifie l'action entreprise par le serveur lorsqu'une clé NULL a été convertie en membre inconnu.</span><span class="sxs-lookup"><span data-stu-id="e9b19-152">Specifies the action taken by the server when a null key has been converted to Unknown Member.</span></span> <span data-ttu-id="e9b19-153">Les valeurs valides sont `IgnoreError` pour continuer le traitement comme si l'erreur ne s'était pas produite, `ReportAndContinue` pour enregistrer l'erreur et continuer le traitement et `ReportAndStop` pour enregistrer l'erreur et arrêter le traitement immédiatement, même si le nombre d'erreurs est inférieur au nombre maximal.</span><span class="sxs-lookup"><span data-stu-id="e9b19-153">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="e9b19-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span><span class="sxs-lookup"><span data-stu-id="e9b19-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span></span>  
 <span data-ttu-id="e9b19-155">Spécifie l'action entreprise par le serveur lorsque `NullProcessing` a la valeur `Error` pour un attribut de dimension.</span><span class="sxs-lookup"><span data-stu-id="e9b19-155">Specifies the action taken by the server when `NullProcessing` is set to `Error` for a dimension attribute.</span></span> <span data-ttu-id="e9b19-156">Une erreur est générée lorsqu'une valeur NULL n'est pas autorisée dans un attribut donné.</span><span class="sxs-lookup"><span data-stu-id="e9b19-156">An error is generated when a null value is not allowed in a given attribute.</span></span> <span data-ttu-id="e9b19-157">Cette propriété de configuration d'erreur informe l'étape suivante, qui consiste à créer un rapport d'erreurs et poursuivre le traitement tant que le nombre maximal d'erreurs n'est pas atteint.</span><span class="sxs-lookup"><span data-stu-id="e9b19-157">This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached.</span></span> <span data-ttu-id="e9b19-158">Les valeurs valides sont `IgnoreError` pour continuer le traitement comme si l'erreur ne s'était pas produite, `ReportAndContinue` pour enregistrer l'erreur et continuer le traitement et `ReportAndStop` pour enregistrer l'erreur et arrêter le traitement immédiatement, même si le nombre d'erreurs est inférieur au nombre maximal.</span><span class="sxs-lookup"><span data-stu-id="e9b19-158">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="e9b19-159">**ErrorLog\ LogErrorTypes\CalculationError**</span><span class="sxs-lookup"><span data-stu-id="e9b19-159">**ErrorLog\ LogErrorTypes\CalculationError**</span></span>  
 <span data-ttu-id="e9b19-160">Propriété utilisée comme valeur par défaut durant une opération de traitement effectuée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="e9b19-160">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="e9b19-161">**ErrorLog\IgnoreDataTruncation**</span><span class="sxs-lookup"><span data-stu-id="e9b19-161">**ErrorLog\IgnoreDataTruncation**</span></span>  
 <span data-ttu-id="e9b19-162">Propriété utilisée comme valeur par défaut durant une opération de traitement effectuée par le serveur.</span><span class="sxs-lookup"><span data-stu-id="e9b19-162">A property used as a default during processing operation performed by the server.</span></span>  
  
## <a name="exception"></a><span data-ttu-id="e9b19-163">Exception</span><span class="sxs-lookup"><span data-stu-id="e9b19-163">Exception</span></span>  
 <span data-ttu-id="e9b19-164">**Exception\CreateAndSendCrashReports**</span><span class="sxs-lookup"><span data-stu-id="e9b19-164">**Exception\CreateAndSendCrashReports**</span></span>  
 <span data-ttu-id="e9b19-165">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-165">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-166">**Exception\CrashReportsFolder**</span><span class="sxs-lookup"><span data-stu-id="e9b19-166">**Exception\CrashReportsFolder**</span></span>  
 <span data-ttu-id="e9b19-167">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-167">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-168">**Exception\SQLDumperFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="e9b19-168">**Exception\SQLDumperFlagsOn**</span></span>  
 <span data-ttu-id="e9b19-169">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-170">**Exception\SQLDumperFlagsOff**</span><span class="sxs-lookup"><span data-stu-id="e9b19-170">**Exception\SQLDumperFlagsOff**</span></span>  
 <span data-ttu-id="e9b19-171">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-172">**Exception\MiniDumpFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="e9b19-172">**Exception\MiniDumpFlagsOn**</span></span>  
 <span data-ttu-id="e9b19-173">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-173">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-174">**Exception\MinidumpErrorList**</span><span class="sxs-lookup"><span data-stu-id="e9b19-174">**Exception\MinidumpErrorList**</span></span>  
 <span data-ttu-id="e9b19-175">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-175">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="flight-recorder"></a><span data-ttu-id="e9b19-176">Boîte noire SQL</span><span class="sxs-lookup"><span data-stu-id="e9b19-176">Flight Recorder</span></span>  
 <span data-ttu-id="e9b19-177">**FlightRecorder\Enabled**</span><span class="sxs-lookup"><span data-stu-id="e9b19-177">**FlightRecorder\Enabled**</span></span>  
 <span data-ttu-id="e9b19-178">Propriété booléenne qui indique si la fonctionnalité de boîte noire SQL est activée.</span><span class="sxs-lookup"><span data-stu-id="e9b19-178">A Boolean property that indicates whether the flight recorder feature is enabled.</span></span>  
  
 <span data-ttu-id="e9b19-179">**FlightRecorder\FileSizeMB**</span><span class="sxs-lookup"><span data-stu-id="e9b19-179">**FlightRecorder\FileSizeMB**</span></span>  
 <span data-ttu-id="e9b19-180">Propriété dont la valeur est un entier 32 bits signé qui définit la taille du fichier sur disque de la boîte noire SQL, exprimée en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="e9b19-180">A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.</span></span>  
  
 <span data-ttu-id="e9b19-181">**FlightRecorder\LogDurationSec**</span><span class="sxs-lookup"><span data-stu-id="e9b19-181">**FlightRecorder\LogDurationSec**</span></span>  
 <span data-ttu-id="e9b19-182">Propriété dont la valeur est un entier 32 bits signé qui définit la fréquence en secondes selon laquelle l'enregistrement reprend au début dans la boîte noire SQL.</span><span class="sxs-lookup"><span data-stu-id="e9b19-182">A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.</span></span>  
  
 <span data-ttu-id="e9b19-183">**FlightRecorder\SnapshotDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="e9b19-183">**FlightRecorder\SnapshotDefinitionFile**</span></span>  
 <span data-ttu-id="e9b19-184">Propriété de type chaîne qui spécifie le nom du fichier de définition d'instantané, qui contient les commandes de découverte envoyées au serveur lorsqu'un instantané est réalisé.</span><span class="sxs-lookup"><span data-stu-id="e9b19-184">A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.</span></span>  
  
 <span data-ttu-id="e9b19-185">La valeur par défaut de cette propriété est vide, ce qui correspond au nom de fichier par défaut FlightRecorderSnapshotDef.txt.</span><span class="sxs-lookup"><span data-stu-id="e9b19-185">The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.</span></span>  
  
 <span data-ttu-id="e9b19-186">**FlightRecorder\SnapshotFrequencySec**</span><span class="sxs-lookup"><span data-stu-id="e9b19-186">**FlightRecorder\SnapshotFrequencySec**</span></span>  
 <span data-ttu-id="e9b19-187">Propriété dont la valeur est un entier 32 bits signé qui définit la fréquence en secondes des instantanés.</span><span class="sxs-lookup"><span data-stu-id="e9b19-187">A signed 32-bit integer property that defines the snapshot frequency, in seconds.</span></span>  
  
 <span data-ttu-id="e9b19-188">**FlightRecorder\TraceDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="e9b19-188">**FlightRecorder\TraceDefinitionFile**</span></span>  
 <span data-ttu-id="e9b19-189">Propriété de type chaîne qui spécifie le nom du fichier de définition de trace de la boîte noire SQL.</span><span class="sxs-lookup"><span data-stu-id="e9b19-189">A string property that specifies the name of the flight recorder trace definition file.</span></span>  
  
 <span data-ttu-id="e9b19-190">La valeur par défaut de cette propriété est vide, ce qui correspond au nom de fichier par défaut FlightRecorderTraceDef.txt.</span><span class="sxs-lookup"><span data-stu-id="e9b19-190">The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml.</span></span>  
  
## <a name="query-log"></a><span data-ttu-id="e9b19-191">Journal des requêtes</span><span class="sxs-lookup"><span data-stu-id="e9b19-191">Query Log</span></span>  
 <span data-ttu-id="e9b19-192">**S’applique à :** Mode serveur multidimensionnel uniquement</span><span class="sxs-lookup"><span data-stu-id="e9b19-192">**Applies to:** Multidimensional server mode only</span></span>  
  
 <span data-ttu-id="e9b19-193">**QueryLog\QueryLogFileName**</span><span class="sxs-lookup"><span data-stu-id="e9b19-193">**QueryLog\QueryLogFileName**</span></span>  
 <span data-ttu-id="e9b19-194">Propriété de type chaîne qui spécifie le nom du fichier journal des requêtes.</span><span class="sxs-lookup"><span data-stu-id="e9b19-194">A string property that specifies the name of the query log file.</span></span> <span data-ttu-id="e9b19-195">Cette propriété s'applique uniquement si vous utilisez un fichier sur disque pour l'enregistrement, au lieu d'une table de base de données (comportement par défaut).</span><span class="sxs-lookup"><span data-stu-id="e9b19-195">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="e9b19-196">**QueryLog\QueryLogSampling**</span><span class="sxs-lookup"><span data-stu-id="e9b19-196">**QueryLog\QueryLogSampling**</span></span>  
 <span data-ttu-id="e9b19-197">Propriété dont la valeur est un entier 32 bits signé qui spécifie le taux d'échantillonnage du journal des requêtes.</span><span class="sxs-lookup"><span data-stu-id="e9b19-197">A signed 32-bit integer property that specifies the query log sampling rate.</span></span>  
  
 <span data-ttu-id="e9b19-198">La valeur par défaut de cette propriété, 10, signifie qu'une requête sur 10 est enregistrée.</span><span class="sxs-lookup"><span data-stu-id="e9b19-198">The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.</span></span>  
  
 <span data-ttu-id="e9b19-199">**QueryLog\QueryLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="e9b19-199">**QueryLog\QueryLogFileSize**</span></span>  
 <span data-ttu-id="e9b19-200">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-200">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-201">**QueryLog\QueryLogConnectionString**</span><span class="sxs-lookup"><span data-stu-id="e9b19-201">**QueryLog\QueryLogConnectionString**</span></span>  
 <span data-ttu-id="e9b19-202">Propriété de type chaîne qui spécifie la connexion à la base de données du journal des requêtes.</span><span class="sxs-lookup"><span data-stu-id="e9b19-202">A string property that specifies the connection to the query log database.</span></span>  
  
 <span data-ttu-id="e9b19-203">**QueryLog\QueryLogTableName**</span><span class="sxs-lookup"><span data-stu-id="e9b19-203">**QueryLog\QueryLogTableName**</span></span>  
 <span data-ttu-id="e9b19-204">Propriété de type chaîne qui spécifie le nom de la table du journal des requêtes.</span><span class="sxs-lookup"><span data-stu-id="e9b19-204">A string property that specifies the name of the query log table.</span></span>  
  
 <span data-ttu-id="e9b19-205">La valeur par défaut de cette propriété est OlapQueryLog.</span><span class="sxs-lookup"><span data-stu-id="e9b19-205">The default value for this property is OlapQueryLog.</span></span>  
  
 <span data-ttu-id="e9b19-206">**QueryLog\CreateQueryLogTable**</span><span class="sxs-lookup"><span data-stu-id="e9b19-206">**QueryLog\CreateQueryLogTable**</span></span>  
 <span data-ttu-id="e9b19-207">Propriété booléenne qui spécifie si la table du journal des requêtes doit être créée.</span><span class="sxs-lookup"><span data-stu-id="e9b19-207">A Boolean property that specifies whether to create the query log table.</span></span>  
  
 <span data-ttu-id="e9b19-208">La valeur par défaut de cette propriété, False, indique que ne serveur ne crée pas automatiquement la table du journal et n'enregistre pas d'événements de requête.</span><span class="sxs-lookup"><span data-stu-id="e9b19-208">The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e9b19-209">Pour plus d’informations sur la configuration du journal des requêtes, consultez [opérations de journalisation dans Analysis Services](../instances/log-operations-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e9b19-209">For more information about configuring the query log, see [Log operations in Analysis Services](../instances/log-operations-in-analysis-services.md).</span></span>  
  
## <a name="trace"></a><span data-ttu-id="e9b19-210">Trace</span><span class="sxs-lookup"><span data-stu-id="e9b19-210">Trace</span></span>  
 <span data-ttu-id="e9b19-211">**Trace\TraceBackgroundDistributionPeriod**</span><span class="sxs-lookup"><span data-stu-id="e9b19-211">**Trace\TraceBackgroundDistributionPeriod**</span></span>  
 <span data-ttu-id="e9b19-212">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-212">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-213">**Trace\TraceBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="e9b19-213">**Trace\TraceBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="e9b19-214">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-215">**Trace\TraceFileBufferSize**</span><span class="sxs-lookup"><span data-stu-id="e9b19-215">**Trace\TraceFileBufferSize**</span></span>  
 <span data-ttu-id="e9b19-216">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-216">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-217">**Trace\TraceFileWriteTrailerPeriod**</span><span class="sxs-lookup"><span data-stu-id="e9b19-217">**Trace\TraceFileWriteTrailerPeriod**</span></span>  
 <span data-ttu-id="e9b19-218">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-219">**Trace\TraceMaxRowsetSize**</span><span class="sxs-lookup"><span data-stu-id="e9b19-219">**Trace\TraceMaxRowsetSize**</span></span>  
 <span data-ttu-id="e9b19-220">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-221">**Trace\TraceProtocolTraffic**</span><span class="sxs-lookup"><span data-stu-id="e9b19-221">**Trace\TraceProtocolTraffic**</span></span>  
 <span data-ttu-id="e9b19-222">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-222">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-223">**Trace\TraceQueryResponseTextChunkSize**</span><span class="sxs-lookup"><span data-stu-id="e9b19-223">**Trace\TraceQueryResponseTextChunkSize**</span></span>  
 <span data-ttu-id="e9b19-224">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-225">**Trace\TraceReportFQDN**</span><span class="sxs-lookup"><span data-stu-id="e9b19-225">**Trace\TraceReportFQDN**</span></span>  
 <span data-ttu-id="e9b19-226">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-226">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-227">**Trace\TraceRequestParameters**</span><span class="sxs-lookup"><span data-stu-id="e9b19-227">**Trace\TraceRequestParameters**</span></span>  
 <span data-ttu-id="e9b19-228">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="e9b19-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="e9b19-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="e9b19-230">Propriété avancée que vous ne devez pas modifier, sauf si vous bénéficiez de l'assistance du support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e9b19-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b19-231">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9b19-231">See Also</span></span>  
 <span data-ttu-id="e9b19-232">[Configurer les propriétés du serveur dans Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e9b19-232">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="e9b19-233">Déterminer le mode serveur d'une instance Analysis Services</span><span class="sxs-lookup"><span data-stu-id="e9b19-233">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
