---
title: Fichier de configuration ReportingServicesService | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- traces [Reporting Services]
- Report Server Windows service, ReportingServicesService configuration file
- ReportingServicesService configuration file
ms.assetid: 40f4a401-cb61-4c42-b1ec-01acdacdacd1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5124631db9635211827dd3b1abbff7116101a61d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610442"
---
# <a name="reportingservicesservice-configuration-file"></a><span data-ttu-id="b91fe-102">fichier de configuration ReportingServicesService</span><span class="sxs-lookup"><span data-stu-id="b91fe-102">ReportingServicesService Configuration File</span></span>
  <span data-ttu-id="b91fe-103">Le fichier ReportingServicesService.exe.config contient les paramètres de configuration de la trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-103">The ReportingServicesService.exe.config file includes settings that configure tracing.</span></span>  
  
## <a name="file-location"></a><span data-ttu-id="b91fe-104">Emplacement du fichier</span><span class="sxs-lookup"><span data-stu-id="b91fe-104">File Location</span></span>  
 <span data-ttu-id="b91fe-105">Ce fichier est situé dans le dossier \Reporting Services\Report Server\Bin.</span><span class="sxs-lookup"><span data-stu-id="b91fe-105">This file is located in the \Reporting Services\Report Server\Bin folder.</span></span>  
  
## <a name="editing-guidelines"></a><span data-ttu-id="b91fe-106">Instructions de modification</span><span class="sxs-lookup"><span data-stu-id="b91fe-106">Editing Guidelines</span></span>  
 <span data-ttu-id="b91fe-107">Vous pouvez modifier ce fichier pour renommer le fichier journal ou pour augmenter ou réduire les niveaux de trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-107">You can modify this file to rename the log file or to increase or decrease trace levels.</span></span> <span data-ttu-id="b91fe-108">Ne modifiez aucun autre paramètre.</span><span class="sxs-lookup"><span data-stu-id="b91fe-108">Do not modify any of the other settings.</span></span> <span data-ttu-id="b91fe-109">Pour obtenir des instructions, consultez [Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="b91fe-109">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="b91fe-110">Pour plus d’informations sur les journaux des traces, consultez [Journal des traces du service Report Server](report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="b91fe-110">For more information about trace logs, see [Report Server Service Trace Log](report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="b91fe-111">Exemple de configuration</span><span class="sxs-lookup"><span data-stu-id="b91fe-111">Example Configuration</span></span>  
 <span data-ttu-id="b91fe-112">L'exemple suivant illustre les paramètres et valeurs par défaut du fichier ReportingServicesService.exe.config.</span><span class="sxs-lookup"><span data-stu-id="b91fe-112">The following example shows the settings and default values found in the ReportingServicesService.exe.config file.</span></span>  
  
```  
<configSections>  
      <section name="RStrace" type="Microsoft.ReportingServices.Diagnostics.RSTraceSectionHandler,Microsoft.ReportingServices.Diagnostics" />  
</configSections>  
<system.diagnostics>  
      <switches>  
          <add name="DefaultTraceSwitch" value="3" />  
      </switches>  
</system.diagnostics>  
<RStrace>  
      <add name="FileName" value="ReportServerService_" />  
      <add name="FileSizeLimitMb" value="32" />  
      <add name="KeepFilesForDays" value="14" />  
      <add name="Prefix" value="tid, time" />  
      <add name="TraceListeners" value="debugwindow, file" />  
      <add name="TraceFileMode" value="unique" />  
      <add name="Components" value="all" />  
</RStrace>  
<runtime>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
             <dependentAssembly>  
                    <assemblyIdentity name="Microsoft.ReportingServices.Interfaces"  
                        publicKeyToken="89845dcd8080cc91"  
                        culture="neutral" />  
                    <bindingRedirect oldVersion="8.0.242.0"  
                                     newVersion="10.0.0.0"/>  
                    <bindingRedirect oldVersion="9.0.242.0"  
                                     newVersion="10.0.0.0"/>  
             </dependentAssembly>  
      </assemblyBinding>  
      <gcServer enabled="true" />  
</runtime>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="b91fe-113">Paramètres de configuration</span><span class="sxs-lookup"><span data-stu-id="b91fe-113">Configuration Settings</span></span>  
 <span data-ttu-id="b91fe-114">Le tableau suivant contient des informations sur des paramètres spécifiques.</span><span class="sxs-lookup"><span data-stu-id="b91fe-114">The following table provides information about specific settings.</span></span> <span data-ttu-id="b91fe-115">Les paramètres sont présentés dans l'ordre dans lequel ils apparaissent dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="b91fe-115">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="b91fe-116">Paramètre</span><span class="sxs-lookup"><span data-stu-id="b91fe-116">Setting</span></span>|<span data-ttu-id="b91fe-117">Description</span><span class="sxs-lookup"><span data-stu-id="b91fe-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b91fe-118">**RStrace**</span><span class="sxs-lookup"><span data-stu-id="b91fe-118">**RStrace**</span></span>|<span data-ttu-id="b91fe-119">Spécifie les espaces de noms utilisés pour les erreurs et la trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-119">Specifies namespaces used for errors and tracing.</span></span>|  
|<span data-ttu-id="b91fe-120">**DefaultTraceSwitch**</span><span class="sxs-lookup"><span data-stu-id="b91fe-120">**DefaultTraceSwitch**</span></span>|<span data-ttu-id="b91fe-121">Spécifie le niveau des informations consignées dans le journal de trace de ReportServerService.</span><span class="sxs-lookup"><span data-stu-id="b91fe-121">Specifies the level of information that is reported to the ReportServerService trace log.</span></span> <span data-ttu-id="b91fe-122">Chaque niveau comprend les informations signalées par tous les niveaux inférieurs.</span><span class="sxs-lookup"><span data-stu-id="b91fe-122">Each level includes the information reported by all lower-numbered levels.</span></span> <span data-ttu-id="b91fe-123">La désactivation de la trace n'est pas recommandée.</span><span class="sxs-lookup"><span data-stu-id="b91fe-123">Disabling tracing is not recommended.</span></span> <span data-ttu-id="b91fe-124">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b91fe-124">Valid values include:</span></span><br /><br /> <span data-ttu-id="b91fe-125">0= Trace désactivée</span><span class="sxs-lookup"><span data-stu-id="b91fe-125">0= Disables tracing</span></span><br /><br /> <span data-ttu-id="b91fe-126">1= Exceptions et redémarrages</span><span class="sxs-lookup"><span data-stu-id="b91fe-126">1= Exceptions and restarts</span></span><br /><br /> <span data-ttu-id="b91fe-127">2= Exceptions, redémarrages, avertissements</span><span class="sxs-lookup"><span data-stu-id="b91fe-127">2= Exceptions, restarts, warnings</span></span><br /><br /> <span data-ttu-id="b91fe-128">3= Exceptions, redémarrages, avertissements, messages d'état (par défaut)</span><span class="sxs-lookup"><span data-stu-id="b91fe-128">3= Exceptions, restarts, warnings, status messages (default)</span></span><br /><br /> <span data-ttu-id="b91fe-129">4= Mode commenté</span><span class="sxs-lookup"><span data-stu-id="b91fe-129">4= Verbose mode</span></span>|  
|<span data-ttu-id="b91fe-130">**FileName**</span><span class="sxs-lookup"><span data-stu-id="b91fe-130">**FileName**</span></span>|<span data-ttu-id="b91fe-131">Spécifie la première partie du nom du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="b91fe-131">Specifies the first portion of the log file name.</span></span> <span data-ttu-id="b91fe-132">La valeur spécifiée par `Prefix` complète le reste du nom.</span><span class="sxs-lookup"><span data-stu-id="b91fe-132">The value specified by `Prefix` completes the rest of the name.</span></span> <span data-ttu-id="b91fe-133">Le nom est ReportServerService_ par défaut.</span><span class="sxs-lookup"><span data-stu-id="b91fe-133">By default, the name is ReportServerService_.</span></span>|  
|<span data-ttu-id="b91fe-134">**FileSizeLimitMb**</span><span class="sxs-lookup"><span data-stu-id="b91fe-134">**FileSizeLimitMb**</span></span>|<span data-ttu-id="b91fe-135">Spécifie une taille maximale pour le journal de trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-135">Specifies an upper limit on trace log size.</span></span> <span data-ttu-id="b91fe-136">La taille du fichier est exprimée en mégaoctets.</span><span class="sxs-lookup"><span data-stu-id="b91fe-136">The file is measured in megabytes.</span></span> <span data-ttu-id="b91fe-137">Les valeurs valides vont de 0 à un entier maximal.</span><span class="sxs-lookup"><span data-stu-id="b91fe-137">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="b91fe-138">La valeur par défaut est 32.</span><span class="sxs-lookup"><span data-stu-id="b91fe-138">The default value is 32.</span></span>|  
|<span data-ttu-id="b91fe-139">**KeepFilesForDays**</span><span class="sxs-lookup"><span data-stu-id="b91fe-139">**KeepFilesForDays**</span></span>|<span data-ttu-id="b91fe-140">Spécifie le nombre de jours après lequel supprimer un journal de trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-140">Specifies the number of days after which a trace log file will be deleted.</span></span> <span data-ttu-id="b91fe-141">Les valeurs valides vont de 0 à un entier maximal.</span><span class="sxs-lookup"><span data-stu-id="b91fe-141">Valid values are 0 to a maximum integer.</span></span> <span data-ttu-id="b91fe-142">La valeur par défaut est 14.</span><span class="sxs-lookup"><span data-stu-id="b91fe-142">The default value is 14.</span></span>|  
|`Prefix`|<span data-ttu-id="b91fe-143">Spécifie une valeur générée qui distingue une instance de journal d'une autre.</span><span class="sxs-lookup"><span data-stu-id="b91fe-143">Specifies a generated value that distinguishes one log instance from another.</span></span> <span data-ttu-id="b91fe-144">Par défaut, des valeurs d'horodatage sont ajoutées aux noms des journaux de trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-144">By default, timestamp values are appended to trace log file names.</span></span> <span data-ttu-id="b91fe-145">Cette valeur est définie sur « tid, time ».</span><span class="sxs-lookup"><span data-stu-id="b91fe-145">This value is set to " tid, time ".</span></span> <span data-ttu-id="b91fe-146">Ne modifiez pas ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="b91fe-146">Do not modify this setting.</span></span>|  
|<span data-ttu-id="b91fe-147">**TraceListeners**</span><span class="sxs-lookup"><span data-stu-id="b91fe-147">**TraceListeners**</span></span>|<span data-ttu-id="b91fe-148">Spécifie une cible de sortie du contenu du journal de trace.</span><span class="sxs-lookup"><span data-stu-id="b91fe-148">Specifies a target for outputting trace log content.</span></span> <span data-ttu-id="b91fe-149">Vous pouvez spécifier plusieurs cibles ; dans ce cas, utilisez la virgule comme séparateur.</span><span class="sxs-lookup"><span data-stu-id="b91fe-149">You can specify multiple targets using a comma to separate each one.</span></span> <span data-ttu-id="b91fe-150">Les valeurs valides sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="b91fe-150">Valid values include:</span></span><br /><br /> <span data-ttu-id="b91fe-151">DebugWindow (par défaut)</span><span class="sxs-lookup"><span data-stu-id="b91fe-151">DebugWindow (default)</span></span><br /><br /> <span data-ttu-id="b91fe-152">File (par défaut)</span><span class="sxs-lookup"><span data-stu-id="b91fe-152">File (default)</span></span><br /><br /> <span data-ttu-id="b91fe-153">StdOut</span><span class="sxs-lookup"><span data-stu-id="b91fe-153">StdOut</span></span>|  
|<span data-ttu-id="b91fe-154">**TraceFileMode**</span><span class="sxs-lookup"><span data-stu-id="b91fe-154">**TraceFileMode**</span></span>|<span data-ttu-id="b91fe-155">Spécifie si les journaux de trace contiennent des données pour une période de 24 heures.</span><span class="sxs-lookup"><span data-stu-id="b91fe-155">Specifies whether trace logs contain data for a 24-hour period.</span></span> <span data-ttu-id="b91fe-156">Un seul journal de trace doit exister par composant et par jour.</span><span class="sxs-lookup"><span data-stu-id="b91fe-156">You should have one unique trace log for each component on each day.</span></span> <span data-ttu-id="b91fe-157">Cette valeur est définie sur « Unique » (par défaut).</span><span class="sxs-lookup"><span data-stu-id="b91fe-157">This value is set to "Unique (default)".</span></span> <span data-ttu-id="b91fe-158">Ne modifiez pas cette valeur.</span><span class="sxs-lookup"><span data-stu-id="b91fe-158">Do not modify this value.</span></span>|  
|<span data-ttu-id="b91fe-159">**Composants**</span><span class="sxs-lookup"><span data-stu-id="b91fe-159">**Components**</span></span>|<span data-ttu-id="b91fe-160">Spécifie les composants pour lesquels des journaux de trace sont créés.</span><span class="sxs-lookup"><span data-stu-id="b91fe-160">Specifies the components for which trace logs are created.</span></span> <span data-ttu-id="b91fe-161">La valeur par défaut est `all`.</span><span class="sxs-lookup"><span data-stu-id="b91fe-161">The default value is `all`.</span></span> <span data-ttu-id="b91fe-162">Ce paramètre accepte aussi comme valeur les noms de composants internes.</span><span class="sxs-lookup"><span data-stu-id="b91fe-162">Other valid values for this setting include the names of internal components.</span></span> <span data-ttu-id="b91fe-163">Ne modifiez pas cette valeur.</span><span class="sxs-lookup"><span data-stu-id="b91fe-163">Do not modify this value.</span></span>|  
|<span data-ttu-id="b91fe-164">**Language**</span><span class="sxs-lookup"><span data-stu-id="b91fe-164">**Runtime**</span></span>|<span data-ttu-id="b91fe-165">Spécifie les paramètres de configuration qui prennent en charge la compatibilité descendante avec la version précédente.</span><span class="sxs-lookup"><span data-stu-id="b91fe-165">Specifies configuration settings that support backward compatibility with the previous version.</span></span> <span data-ttu-id="b91fe-166">Des paramètres d'exécution sont utilisés pour rediriger vers la nouvelle version les demandes qui ciblent la version précédente de Microsoft.ReportingServices.Interfaces.</span><span class="sxs-lookup"><span data-stu-id="b91fe-166">Runtime settings are used to redirect requests that target the previous version of Microsoft.ReportingServices.Interfaces to the new version.</span></span><br /><br /> <span data-ttu-id="b91fe-167">Tous les paramètres de configuration de cette section sont décrits dans la documentation de produit du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b91fe-167">All of the configuration settings in this section are described in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] product documentation.</span></span> <span data-ttu-id="b91fe-168">Pour plus d'informations, recherchez « Runtime Schema Settings » (en anglais) sur le site Web MSDN ou dans la documentation du [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b91fe-168">For more information, search for "Runtime Schema Settings" on the MSDN Web site or in the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b91fe-169">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b91fe-169">See Also</span></span>  
 <span data-ttu-id="b91fe-170">[Fichiers de configuration de Reporting Services](reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="b91fe-170">[Reporting Services Configuration Files](reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="b91fe-171">Report Server Service Trace Log</span><span class="sxs-lookup"><span data-stu-id="b91fe-171">Report Server Service Trace Log</span></span>](report-server-service-trace-log.md)  
  
  
