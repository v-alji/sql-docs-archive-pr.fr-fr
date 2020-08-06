---
title: 'Liste de vérification : utiliser PowerShell pour vérifier PowerPivot pour SharePoint | Microsoft Docs'
ms.custom: ''
ms.date: 07/20/2020
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 73a13f05-3450-411f-95f9-4b6167cc7607
author: minewiskan
ms.author: owend
ms.openlocfilehash: 001b3fae82851b9ec08b0383bb3db9e6d011ae32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697319"
---
# <a name="checklist-use-powershell-to-verify-powerpivot-for-sharepoint"></a><span data-ttu-id="fd083-102">Liste de vérification : utiliser PowerShell pour vérifier PowerPivot pour SharePoint</span><span class="sxs-lookup"><span data-stu-id="fd083-102">CheckList: Use PowerShell to Verify PowerPivot for SharePoint</span></span>
  <span data-ttu-id="fd083-103">Aucune opération d'installation ou de récupération de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] n'est terminée sans exécuter un test de vérification complet qui confirme que les services et les données sont opérationnels.</span><span class="sxs-lookup"><span data-stu-id="fd083-103">No [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] installation or recovery operation is complete without a solid verification test pass that confirms your services and data are operational.</span></span> <span data-ttu-id="fd083-104">Dans cet article, nous vous indiquons comment effectuer ces étapes avec Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd083-104">In this article, we show you how to perform these steps using Windows PowerShell.</span></span> <span data-ttu-id="fd083-105">Nous avons consacré une section distincte à chaque étape afin que vous puissiez accéder directement aux tâches spécifiques.</span><span class="sxs-lookup"><span data-stu-id="fd083-105">We put each step into its own section so that you can go straight to specific tasks.</span></span> <span data-ttu-id="fd083-106">Par exemple, exécutez le script dans la section [Bases de données](#bkmk_databases) de cette rubrique pour vérifier le nom de l'application de service et des bases de données de contenu si vous souhaitez les planifier pour la maintenance ou la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="fd083-106">For example, run the script in the [Databases](#bkmk_databases) section of this topic to verify the name of the service application and content databases if you want to schedule them for maintenance or backup.</span></span>

|||
|-|-|
|<span data-ttu-id="fd083-107">![Contenu relatif à PowerShell](../../../reporting-services/media/rs-powershellicon.jpg "Contenu relatif à PowerShell")</span><span class="sxs-lookup"><span data-stu-id="fd083-107">![PowerShell related content](../../../reporting-services/media/rs-powershellicon.jpg "PowerShell related content")</span></span>|<span data-ttu-id="fd083-108">Un script PowerShell complet est inclus en bas de la rubrique.</span><span class="sxs-lookup"><span data-stu-id="fd083-108">A full PowerShell script is included at the bottom of the topic.</span></span> <span data-ttu-id="fd083-109">Utilisez le script dans sa totalité comme point de départ pour générer un script personnalisé afin de vérifier votre déploiement complet de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd083-109">Use the full script as a starting point to build a custom script for auditing your full [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] deployment.</span></span>|

||
|-|
|<span data-ttu-id="fd083-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]** SharePoint 2013 &#124; SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="fd083-110">**[!INCLUDE[applies](../../../includes/applies-md.md)]**  SharePoint 2013 &#124; SharePoint 2010</span></span>|

 <span data-ttu-id="fd083-111">**Dans cette rubrique**- Les lettres dans la table des matières qui suit correspondent aux zones du schéma.</span><span class="sxs-lookup"><span data-stu-id="fd083-111">**In this topic**: The lettered items in the following the TOC correspond to areas of the diagram.</span></span> <span data-ttu-id="fd083-112">Le schéma illustre les points suivants :</span><span class="sxs-lookup"><span data-stu-id="fd083-112">The diagram illustrates the</span></span>

|||
|-|-|
|[<span data-ttu-id="fd083-113">Préparer votre environnement PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd083-113">Prepare your PowerShell environment</span></span>](#bkmk_prerequisites)<br /><br /> [<span data-ttu-id="fd083-114">Symptômes et actions recommandées</span><span class="sxs-lookup"><span data-stu-id="fd083-114">Symptoms and Recommended Actions</span></span>](#bkmk_symptoms)<br /><br /> <span data-ttu-id="fd083-115">**(A)** [Service Windows Analysis Services](#bkmk_windows_service)</span><span class="sxs-lookup"><span data-stu-id="fd083-115">**(A)** [Analysis Services Windows Service](#bkmk_windows_service)</span></span><br /><br /> <span data-ttu-id="fd083-116">**(B)** [PowerPivotSystemService et PowerPivotEngineService](#bkmk_engine_and_system_service)</span><span class="sxs-lookup"><span data-stu-id="fd083-116">**(B)** [PowerPivotSystemService and PowerPivotEngineService](#bkmk_engine_and_system_service)</span></span><br /><br /> <span data-ttu-id="fd083-117">**(C)** [Application(s) et proxys du service PowerPivot](#bkmk_powerpivot_service_application)</span><span class="sxs-lookup"><span data-stu-id="fd083-117">**(C)** [PowerPivot Service Application(s) and proxies](#bkmk_powerpivot_service_application)</span></span><br /><br /> <span data-ttu-id="fd083-118">**(D)** [Bases de données](#bkmk_databases)</span><span class="sxs-lookup"><span data-stu-id="fd083-118">**(D)** [Databases](#bkmk_databases)</span></span><br /><br /> [<span data-ttu-id="fd083-119">Fonctionnalités SharePoint</span><span class="sxs-lookup"><span data-stu-id="fd083-119">SharePoint Features</span></span>](#bkmk_features)<br /><br /> [<span data-ttu-id="fd083-120">Travaux du minuteur</span><span class="sxs-lookup"><span data-stu-id="fd083-120">Timer Jobs</span></span>](#bkmk_timer_jobs)<br /><br /> [<span data-ttu-id="fd083-121">Règles d'intégrité</span><span class="sxs-lookup"><span data-stu-id="fd083-121">Health Rules</span></span>](#bkmk_health_rules)<br /><br /> <span data-ttu-id="fd083-122">**(E)** [Journaux Windows et ULS](#bkmk_logs)</span><span class="sxs-lookup"><span data-stu-id="fd083-122">**(E)** [Windows and ULS Logs](#bkmk_logs)</span></span><br /><br /> [<span data-ttu-id="fd083-123">Fournisseur MSOLAP</span><span class="sxs-lookup"><span data-stu-id="fd083-123">MSOLAP Provider</span></span>](#bkmk_msolap)<br /><br /> [<span data-ttu-id="fd083-124">Bibliothèque cliente ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="fd083-124">ADOMD.Net client Library</span></span>](#bkmk_adomd)<br /><br /> [<span data-ttu-id="fd083-125">Règles de collecte de données d'intégrité</span><span class="sxs-lookup"><span data-stu-id="fd083-125">Health Data Collection Rules</span></span>](#bkmk_health_collection)<br /><br /> [<span data-ttu-id="fd083-126">Solutions</span><span class="sxs-lookup"><span data-stu-id="fd083-126">Solutions</span></span>](#bkmk_solutions)<br /><br /> [<span data-ttu-id="fd083-127">Étapes de vérification manuelle</span><span class="sxs-lookup"><span data-stu-id="fd083-127">Manual Verification Steps</span></span>](#bkmk_manual)<br /><br /> [<span data-ttu-id="fd083-128">Plus de ressources</span><span class="sxs-lookup"><span data-stu-id="fd083-128">More Resources</span></span>](#bkmk_more_resources)<br /><br /> [<span data-ttu-id="fd083-129">Script PowerShell complet</span><span class="sxs-lookup"><span data-stu-id="fd083-129">Full PowerShell Script</span></span>](#bkmk_full_script)|<span data-ttu-id="fd083-130">![contrôle powershell pour powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "contrôle powershell pour powerpivot")</span><span class="sxs-lookup"><span data-stu-id="fd083-130">![powershell verification of powerpivot](../../../sql-server/install/media/ssas-powershell-component-verification.png "powershell verification of powerpivot")</span></span>|

##  <a name="prepare-your-powershell-environment"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="fd083-131">Préparation de votre environnement PowerShell</span><span class="sxs-lookup"><span data-stu-id="fd083-131">Prepare your PowerShell environment</span></span>
 <span data-ttu-id="fd083-132">Les étapes de cette section préparent votre environnement PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd083-132">The steps in this section prepare your PowerShell environment.</span></span> <span data-ttu-id="fd083-133">Elles peuvent ne pas être requises, selon la façon dont votre environnement de script est actuellement configuré.</span><span class="sxs-lookup"><span data-stu-id="fd083-133">The steps may not be required, depending on how your scripting environment is currently configured.</span></span>

 <span data-ttu-id="fd083-134">**Autorisations PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fd083-134">**PowerShell Permissions**</span></span>

 <span data-ttu-id="fd083-135">Ouvrez une fenêtre Powershell ou PowerShell ISE (environnement d’écriture de scripts intégré) avec des **privilèges d’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="fd083-135">Open a Powershell window or the PowerShell ISE (Integrated Scripting Environment) with **administrative privileges**.</span></span> <span data-ttu-id="fd083-136">Sans privilèges d'administrateur, lorsque vous exécuterez les commandes, vous recevrez un message d'erreur similaire au suivant :</span><span class="sxs-lookup"><span data-stu-id="fd083-136">If you do not have administrative privileges when you run commands, you will see an error message similar to the following:</span></span>

 <span data-ttu-id="fd083-137">Get-SPLogEvent : Vous devez disposer des **droits d’administrateur** de l’ordinateur pour exécuter cette applet de commande.</span><span class="sxs-lookup"><span data-stu-id="fd083-137">Get-SPLogEvent : You need to have Machine **administrator privileges** to run this cmdlet.</span></span>

 <span data-ttu-id="fd083-138">Module **SharePoint et [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="fd083-138">**SharePoint and [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)]** Module</span></span>

 <span data-ttu-id="fd083-139">Si un message d'erreur semblable au suivant s'affiche lorsque vous exécutez des applets de commande associées à SharePoint, exécutez la commande Add-PSSnapin :</span><span class="sxs-lookup"><span data-stu-id="fd083-139">If you see an error message similar to the following when you run SharePoint related cmdlets, run the Add-PSSnapin command:</span></span>

 <span data-ttu-id="fd083-140">Le terme « Get-PowerPivotSystemService » **n’est pas reconnu comme nom d’applet de commande**, fonction, fichier de script ou programme exécutable.</span><span class="sxs-lookup"><span data-stu-id="fd083-140">The term 'Get-PowerPivotSystemService' **is not recognized as the name of a cmdlet**, function, script file, or operable program.</span></span> <span data-ttu-id="fd083-141">Vérifiez l’orthographe du nom ou, si un chemin d’accès a été inclus, vérifiez que le chemin d’accès est correct et réessayez.</span><span class="sxs-lookup"><span data-stu-id="fd083-141">Check the spelling of the name, or if a path was included, verify that the path is correct and try again.</span></span>

```
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0
```

 <span data-ttu-id="fd083-142">**Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fd083-142">**Windows PowerShell**</span></span>

 <span data-ttu-id="fd083-143">Pour plus d'informations sur PowerShell ISE, consultez [Introduction à Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) et [Utiliser Windows PowerShell pour administrer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span><span class="sxs-lookup"><span data-stu-id="fd083-143">For more information on the PowerShell ISE, see [Introducing the Windows PowerShell ISE](https://technet.microsoft.com/library/dd315244.aspx) and [Use Windows PowerShell to administer SharePoint 2013](https://technet.microsoft.com/library/ee806878\(v=office.15\).aspx).</span></span>

|||
|-|-|
|<span data-ttu-id="fd083-144">![powerpivot dans l'ensemble général d'applications sharepoint](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot dans l'ensemble général d'applications sharepoint")</span><span class="sxs-lookup"><span data-stu-id="fd083-144">![powerpivot in sharepoint general application set](../../../sql-server/install/media/ssas-powerpivot-logo.png "powerpivot in sharepoint general application set")</span></span>|<span data-ttu-id="fd083-145">Vous pouvez éventuellement vérifier la plupart des composants dans l'Administration centrale, dans le tableau de bord de gestion de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd083-145">You can optionally verify a majority of the components in Central Administration, using the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] management dashboard.</span></span> <span data-ttu-id="fd083-146">Pour ouvrir le tableau de bord dans l'Administration centrale, cliquez sur **Paramètres généraux de l'application**, puis cliquez sur **Tableau de bord de gestion** dans **PowerPivot**.</span><span class="sxs-lookup"><span data-stu-id="fd083-146">To open the dashboard in Central Administration, click **General Application Settings**, and then click **Management Dashboard** in the **PowerPivot**.</span></span> <span data-ttu-id="fd083-147">Pour plus d'informations sur le tableau de bord, consultez [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-147">For more information on the dashboard, see [PowerPivot Management Dashboard and Usage Data](../../power-pivot-sharepoint/power-pivot-management-dashboard-and-usage-data.md).</span></span>|

##  <a name="symptoms-and-recommended-actions"></a><a name="bkmk_symptoms"></a><span data-ttu-id="fd083-148">Symptômes et actions recommandées</span><span class="sxs-lookup"><span data-stu-id="fd083-148">Symptoms and Recommended Actions</span></span>
 <span data-ttu-id="fd083-149">Le tableau suivant répertorie les symptômes ou les problèmes et suggère la section correspondante de cette rubrique à consulter pour vous aider à résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="fd083-149">The following table is a list of symptoms or issues and the suggested section of this topic to consult to help you resolve the issue.</span></span>

|<span data-ttu-id="fd083-150">Symptôme</span><span class="sxs-lookup"><span data-stu-id="fd083-150">Symptom</span></span>|<span data-ttu-id="fd083-151">Voir la section</span><span class="sxs-lookup"><span data-stu-id="fd083-151">See section</span></span>|
|-------------|-----------------|
|<span data-ttu-id="fd083-152">L'actualisation des données ne fonctionne pas</span><span class="sxs-lookup"><span data-stu-id="fd083-152">Data refresh is not running</span></span>|<span data-ttu-id="fd083-153">Consultez la section [Timer Jobs](#bkmk_timer_jobs) et vérifiez que le **Travail du minuteur d'actualisation des données PowerPivot** est en ligne.</span><span class="sxs-lookup"><span data-stu-id="fd083-153">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Online PowerPivot Data Refresh Timer Job** is online.</span></span>|
|<span data-ttu-id="fd083-154">Les données du tableau de bord de gestion sont obsolètes</span><span class="sxs-lookup"><span data-stu-id="fd083-154">Management dashboard data is old</span></span>|<span data-ttu-id="fd083-155">Consultez la section [Travaux du minuteur](#bkmk_timer_jobs) et vérifiez que le **Travail du minuteur pour le traitement du tableau de bord de gestion** est en ligne.</span><span class="sxs-lookup"><span data-stu-id="fd083-155">See the section [Timer Jobs](#bkmk_timer_jobs) and verify the **Management Dashboard Processing Timer Job** is online.</span></span>|
|<span data-ttu-id="fd083-156">Certaines parties du tableau de bord de gestion ne sont pas accessibles</span><span class="sxs-lookup"><span data-stu-id="fd083-156">Some portions of the Management Dashboard</span></span>|<span data-ttu-id="fd083-157">Si vous installez PowerPivot pour SharePoint dans une batterie de serveurs qui présente la topologie d'Administration centrale, sans Excel Services ou PowerPivot pour SharePoint, vous devez télécharger et installer la bibliothèque cliente Microsoft ADOMD.NET si vous voulez disposer d'un accès total aux rapports intégrés dans le tableau de bord de gestion PowerPivot.</span><span class="sxs-lookup"><span data-stu-id="fd083-157">If you install PowerPivot for SharePoint into a farm that has the topology of Central Administration, without Excel Services or PowerPivot for SharePoint, you must download and install the Microsoft ADOMD.NET client library if you want full access to the built-in reports in the PowerPivot management dashboard.</span></span> <span data-ttu-id="fd083-158">Certains rapports du tableau de bord utilisent ADOMD.NET pour accéder aux données internes qui fournissent les données de création de rapports sur le traitement des requêtes PowerPivot et l'intégrité des serveurs de la batterie.</span><span class="sxs-lookup"><span data-stu-id="fd083-158">Some reports in the dashboard use ADOMD.NET to access internal data that provides reporting data on PowerPivot query processing and server health in the farm.</span></span> <span data-ttu-id="fd083-159">Consultez la section [Bibliothèque cliente ADOMD.NET](#bkmk_adomd) et la rubrique [Installer ADOMD.NET sur des serveurs web frontaux exécutant l’Administration centrale](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-159">See the section [ADOMD.Net client Library](#bkmk_adomd) and the topic [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>|
|\<future content>||

##  <a name="analysis-services-windows-service"></a><a name="bkmk_windows_service"></a> <span data-ttu-id="fd083-160">Service Windows Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fd083-160">Analysis Services Windows Service</span></span>
 <span data-ttu-id="fd083-161">Le script de cette section vérifie l'instance d' [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd083-161">The script in this section verifies the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="fd083-162">Vérifiez que le service est **en cours d’exécution**.</span><span class="sxs-lookup"><span data-stu-id="fd083-162">Verify the service is **running**.</span></span>

```powershell
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name              DisplayName                                Status
----              -----------                                ------
MSOLAP$POWERPIVOT SQL Server Analysis Services (POWERPIVOT) Running
```

##  <a name="powerpivotsystemservice-and-powerpivotengineservice"></a><a name="bkmk_engine_and_system_service"></a><span data-ttu-id="fd083-163">PowerPivotSystemService et PowerPivotEngineService</span><span class="sxs-lookup"><span data-stu-id="fd083-163">PowerPivotSystemService and PowerPivotEngineService</span></span>
 <span data-ttu-id="fd083-164">Les scripts de cette section vérifient les services système de [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd083-164">The scripts in this section verify the [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] system services.</span></span> <span data-ttu-id="fd083-165">Il existe un seul service système pour un déploiement SharePoint 2013 et deux services pour un déploiement SharePoint 2010.</span><span class="sxs-lookup"><span data-stu-id="fd083-165">There is one system service for a SharePoint 2013 deployment and two services for a SharePoint 2010 deployment.</span></span>

 <span data-ttu-id="fd083-166">**PowerPivotSystemService**</span><span class="sxs-lookup"><span data-stu-id="fd083-166">**PowerPivotSystemService**</span></span>

 <span data-ttu-id="fd083-167">Vérifiez que l’État est **en ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-167">Verify the Status is **Online**.</span></span>

```powershell
Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                  Status Applications                             Farm
--------                                  ------ ------------                             ----
SQL Server PowerPivot Service Application Online {Default PowerPivot Service Application} SPFarm Name=SharePoint_Config_77d8ab0744a34e8aa27c806a2b8c760c
```

 <span data-ttu-id="fd083-168">**PowerPivotEngineService**</span><span class="sxs-lookup"><span data-stu-id="fd083-168">**PowerPivotEngineService**</span></span>

> [!NOTE]
>  <span data-ttu-id="fd083-169">**Ignorez ce script si** vous utilisez SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="fd083-169">**Skip this script if** you are using SharePoint 2013.</span></span> <span data-ttu-id="fd083-170">Le service PowerPivotEngineService ne fait pas partie d'un déploiement SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="fd083-170">The PowerPivotEngineService is not part of a SharePoint 2013 deployment.</span></span> <span data-ttu-id="fd083-171">Si vous exécutez l'applet de commande Get-PowerPivot**Engine**Service sur SharePoint 2013, vous verrez s'afficher un message d'erreur semblable au suivant.</span><span class="sxs-lookup"><span data-stu-id="fd083-171">If you run the Get-PowerPivot**Engine**Service cmdlet on SharePoint 2013, you will see an error message similar to the following.</span></span> <span data-ttu-id="fd083-172">Ce message d'erreur est retourné même si vous avez exécuté la commande Add-PSSnapin décrite dans la section des conditions préalables requises de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fd083-172">This error message is returned even if you have run the Add-PSSnapin command described in the prerequisites section of this topic.</span></span>
> 
>  <span data-ttu-id="fd083-173">Le terme « Get-PowerPivotEngineService » n'est pas reconnu comme nom d'une applet de commande</span><span class="sxs-lookup"><span data-stu-id="fd083-173">The term 'Get-PowerPivotEngineService' is not recognized as the name of a cmdlet</span></span>

 <span data-ttu-id="fd083-174">Dans un déploiement SharePoint 2010, vérifiez que l'état est **En ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-174">In a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName  : SQL Server Analysis Services
Status    : Online
Name      : MSOLAP$POWERPIVOT
Instances : {POWERPIVOT}
Farm      : SPFarm Name=SharePoint_Config
```

##  <a name="powerpivot-service-applications-and-proxies"></a><a name="bkmk_powerpivot_service_application"></a><span data-ttu-id="fd083-175">Application (s) et proxys du service PowerPivot</span><span class="sxs-lookup"><span data-stu-id="fd083-175">PowerPivot Service Application(s) and proxies</span></span>
 <span data-ttu-id="fd083-176">Vérifiez que l'état est **En ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-176">Verify the status is **Online**.</span></span> <span data-ttu-id="fd083-177">L'application Excel Services n'utilise pas une base de données d'application de service et par conséquent l'applet de commande ne retourne aucun nom de base de données.</span><span class="sxs-lookup"><span data-stu-id="fd083-177">The Excel Services Application does not use a service application database and therefore the cmdlet does not return a database name.</span></span> <span data-ttu-id="fd083-178">Notez la base de données utilisée par l'application de service de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] , afin de pouvoir vérifier que la base de données est en ligne dans la section traitant des bases de données plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fd083-178">Note the database used by the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] service application so you can verify the database is online in the database section later in this topic.</span></span>

 <span data-ttu-id="fd083-179">**Application(s) PowerPivot et Excel Service**</span><span class="sxs-lookup"><span data-stu-id="fd083-179">**PowerPivot and Excel Service Application(s)**</span></span>

 <span data-ttu-id="fd083-180">Pour un déploiement SharePoint 2010, vérifiez que l'état est **En ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-180">For a SharePoint 2010 deployment, verify the status is **Online**.</span></span>

```powershell
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename, DisplayName, status
```

```Output
TypeName          : PowerPivot Service Application
Name              : PowerPivotServiceApplication1
Status            : Online
UnattendedAccount : PowerPivotUnattendedAccount
ApplicationPool   : SPIisWebServiceApplicationPool Name=sqlbi_serviceapp
Farm              : SPFarm Name=SharePoint_Config
Database          : GeminiServiceDatabase Name=PowerPivotServiceApplication1_19648f3f2c944e27acdc6c20aab8487a

TypeName    : Excel Services Application Web Service Application
DisplayName : Excel Services Application
Status      : Online
```

 <span data-ttu-id="fd083-181">**Pool d’applications de service**</span><span class="sxs-lookup"><span data-stu-id="fd083-181">**Service Application Pool**</span></span>

> [!NOTE]
>  <span data-ttu-id="fd083-182">L'exemple de code suivant retourne tout d'abord la propriété applicationpool de l'application de service [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] par défaut.</span><span class="sxs-lookup"><span data-stu-id="fd083-182">The following code sample first returns the applicationpool property of the default [!INCLUDE[ssGeminiShort](../../../includes/ssgeminishort-md.md)] service application.</span></span> <span data-ttu-id="fd083-183">Le nom est analysé à partir de la chaîne et est utilisé pour obtenir l'état de l'objet de pool d'applications.</span><span class="sxs-lookup"><span data-stu-id="fd083-183">The name is parsed from the string and used to get the status of the application pool object.</span></span>
> 
>  <span data-ttu-id="fd083-184">Vérifiez que l’État est **en ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-184">Verify the Status is **Online**.</span></span> <span data-ttu-id="fd083-185">Si l’État n’est pas en ligne ou si vous voyez « erreur http » lorsque vous parcourez le [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, vérifiez que les informations d’identification de l’identité dans les pools d’applications IIS sont toujours correctes.</span><span class="sxs-lookup"><span data-stu-id="fd083-185">If the status is not Online or you see "http error" when you browse the [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] site, verify the identity credentials in the IIS application pools are still correct.</span></span> <span data-ttu-id="fd083-186">Le nom du pool d'applications IIS est la valeur de la propriété d'ID retournée par la commande Get-SPServiceApplicationPool.</span><span class="sxs-lookup"><span data-stu-id="fd083-186">The IIS pool name will is the value of the ID property returned by the Get-SPServiceApplicationPool command.</span></span>

```powershell
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)

Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                           Status ProcessAccountName Id
----                           ------ ------------------ ------- 
SharePoint Web Services System Online DOMAIN\account     89b50ec3-49e3-4de7-881a-2cec4b8b73ea
```

 ![Remarque](../../../reporting-services/media/rs-fyinote.png "remarque") Le pool d’applications peut également être vérifié sur la page Administration centrale **gérer les applications de service**. <span data-ttu-id="fd083-188">Cliquez sur le nom de l'application de service et cliquez sur **Propriétés** dans le ruban.</span><span class="sxs-lookup"><span data-stu-id="fd083-188">Click the name of the service application and then click **properties** in the ribbon.</span></span>

 <span data-ttu-id="fd083-189">**Proxys d'application PowerPivot et Excel Service**</span><span class="sxs-lookup"><span data-stu-id="fd083-189">**PowerPivot and Excel Service Application proxies**</span></span>

 <span data-ttu-id="fd083-190">Vérifiez que l’État est **en ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-190">Verify the Status is **Online**.</span></span>

```powershell
Get-SPServiceApplicationProxy | Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -Like "*powerpivot*" -Or $_.TypeName -Like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
TypeName                                                 Status UnattendedAccount           DisplayName
--------                                                 ------ -----------------           -----------
PowerPivot Service Application Proxy                     Online PowerPivotUnattendedAccount PowerPivotServiceApplication1
Excel Services Application Web Service Application Proxy Online                             Excel Services Application
```

##  <a name="databases"></a><a name="bkmk_databases"></a> <span data-ttu-id="fd083-191">Bases de données</span><span class="sxs-lookup"><span data-stu-id="fd083-191">Databases</span></span>
 <span data-ttu-id="fd083-192">Le script suivant retourne l'état des bases de données d'application de service et de toutes les bases de données de contenu.</span><span class="sxs-lookup"><span data-stu-id="fd083-192">The following script returns the status of the service application databases and all content databases.</span></span> <span data-ttu-id="fd083-193">Vérifiez que l'état est **En ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-193">Verify the status is **Online**.</span></span>

```powershell
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -Or $_.TypeName -Like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                                                                       Status Server                  TypeName 
----                                                                       ------ ------                  -------- 
DefaultPowerPivotServiceApplicationDB-38422181-2b68-4ab2-b2bb-9c00c39e5a5e Online SPServer Name=TESTSERVER Microsoft.AnalysisServices.SPAddin.GeminiServiceDatabase
DefaultWebApplicationDB-f0db1a8e-4c22-408c-b9b9-153bd74b0312               Online TESTSERVER\POWERPIVOT    Content Database 
SharePoint_Admin_3cadf0b098bf49e0bb15abd487f5c684                          Online TESTSERVER\POWERPIVOT    Content Database
```

##  <a name="sharepoint-features"></a><a name="bkmk_features"></a><span data-ttu-id="fd083-194">Fonctionnalités SharePoint</span><span class="sxs-lookup"><span data-stu-id="fd083-194">SharePoint Features</span></span>
 <span data-ttu-id="fd083-195">Vérifiez que le site Web et les fonctionnalités de la batterie sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="fd083-195">Verify the site, web, and farm features are online.</span></span>

```powershell
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
DisplayName     Status Scope Farm                         
-----------     ------ ----- ----                         
PowerPivotSite  Online  Site SPFarm Name=SharePoint_Config
PowerPivotAdmin Online   Web SPFarm Name=SharePoint_Config
PowerPivot      Online  Farm SPFarm Name=SharePoint_Config
```

##  <a name="timer-jobs"></a><a name="bkmk_timer_jobs"></a><span data-ttu-id="fd083-196">Travaux du minuteur</span><span class="sxs-lookup"><span data-stu-id="fd083-196">Timer Jobs</span></span>
 <span data-ttu-id="fd083-197">Vérifiez que les travaux du minuteur sont **En ligne**.</span><span class="sxs-lookup"><span data-stu-id="fd083-197">Verify the Time Jobs are **Online**.</span></span> <span data-ttu-id="fd083-198">Le [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService n'est pas installé sur SharePoint 2013, par conséquent le script ne répertorie pas les travaux du minuteur EngineService dans un déploiement SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="fd083-198">The [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] EngineService is not installed on SharePoint 2013, therefore the script will not list EngineService timer jobs in a SharePoint 2013 deployment.</span></span>

```powershell
Get-SPTimerJob | Where {$_.service -Like "*power*" -Or $_.service -Like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default
```

```Output
      Status DisplayName                                                                          LastRunTime          Service                             
------ -----------                                                                          -----------          -------                             
Online Health Analysis Job (Daily, SQL Server Analysis Services, All Servers)               4/9/2014 12:00:01 AM EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Hourly, SQL Server Analysis Services, All Servers)              4/9/2014 1:00:01 PM  EngineService Name=MSOLAP$POWERPIVOT
Online Health Analysis Job (Weekly, SQL Server Analysis Services, All Servers)              4/6/2014 12:00:10 AM EngineService Name=MSOLAP$POWERPIVOT
Online PowerPivot Management Dashboard Processing Timer Job                                 4/8/2014 3:45:38 AM  MidTierService
Online PowerPivot Health Statistics Collector Timer Job                                     4/9/2014 1:00:12 PM  MidTierService
Online PowerPivot Data Refresh Timer Job                                                    4/9/2014 1:09:36 PM  MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, All Servers)  4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Daily, SQL Server PowerPivot Service Application, Any Server)   4/9/2014 12:00:00 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, All Servers) 4/6/2014 12:00:03 AM MidTierService
Online Health Analysis Job (Weekly, SQL Server PowerPivot Service Application, Any Server)  4/6/2014 12:00:03 AM MidTierService
Online PowerPivot Setup Extension Timer Job                                                 4/1/2014 1:40:31 AM  MidTierService
```

##  <a name="health-rules"></a><a name="bkmk_health_rules"></a><span data-ttu-id="fd083-199">Règles d’intégrité</span><span class="sxs-lookup"><span data-stu-id="fd083-199">Health Rules</span></span>
 <span data-ttu-id="fd083-200">Il y a moins de règles dans un déploiement SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="fd083-200">There are fewer rules in a SharePoint 2013 deployment.</span></span> <span data-ttu-id="fd083-201">Pour obtenir une liste complète des règles pour chaque environnement SharePoint et une explication de l’utilisation des règles, consultez la page relative aux [règles d’intégrité PowerPivot-configurer](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-201">For a full list of rules for each SharePoint environment and an explanation of how to use the rules, see [PowerPivot Health Rules - Configure](../../power-pivot-sharepoint/configure-power-pivot-health-rules.md).</span></span>

```powershell
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                          Enabled Summary
----                          ------- -------         
SecondaryLogonHealthRule         True PowerPivot:  Secondary Logon service (seclogon) is disabled
DataRefreshTimerJobHealthRule    True PowerPivot: The PowerPivot Data Refresh timer job is disabled.
ASUsageLoadHealthRule            True PowerPivot: The ratio of load events to connections is too high.
ASMiniDumpHealthRule             True PowerPivot: One or more minidump files were found in the Logs directory, indicating a program crash
ASUsageCubeRule                  True PowerPivot: Usage data is not getting updated at the expected frequency.
ASADOMDNETHealthRule             True PowerPivot: ADOMD.NET is not installed on a standalone WFE that is configured for central admin
MidTierAcctReadPermissionRule    True PowerPivot: MidTier process account should have 'Full Read' permission on all associated SPWebApplications.
```

##  <a name="windows-and-uls-logs"></a><a name="bkmk_logs"></a><span data-ttu-id="fd083-202">Journaux Windows et ULS</span><span class="sxs-lookup"><span data-stu-id="fd083-202">Windows and ULS Logs</span></span>
 <span data-ttu-id="fd083-203">**Journal des événements Windows**</span><span class="sxs-lookup"><span data-stu-id="fd083-203">**Windows event log**</span></span>

 <span data-ttu-id="fd083-204">La commande suivante recherche le journal des événements Windows pour les événements associés à l'instance d' [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] en mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="fd083-204">The following command will search the windows event log for events related to the instance of [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] in SharePoint mode.</span></span> <span data-ttu-id="fd083-205">Pour plus d’informations sur la désactivation des événements ou la modification du niveau d’événement, consultez [configurer et afficher les fichiers journaux SharePoint et la journalisation des diagnostics &#40;PowerPivot pour SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-205">For information on disabling events or changing the event level, see [Configure and View SharePoint Log Files  and Diagnostic Logging &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/configure-and-view-sharepoint-and-diagnostic-logging.md).</span></span>

 <span data-ttu-id="fd083-206">**Nom du service :** MSOLAP$POWERPIVOT</span><span class="sxs-lookup"><span data-stu-id="fd083-206">**Service Name:** MSOLAP$POWERPIVOT</span></span>

 <span data-ttu-id="fd083-207">**Afficher le nom dans les services Windows :** SQL Server Analysis Services (POWERPIVOT)</span><span class="sxs-lookup"><span data-stu-id="fd083-207">**Display name in Windows Services:** SQL Server Analysis Services (POWERPIVOT)</span></span>

```powershell
Get-EventLog "application" | Where-Object {$_.source -Like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -property * -AutoSize | Out-Default
```

```Output
TimeGenerated           EntryType Source            Message
-------------           --------- ------            -------
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
4/16/2014 1:45:19 PM  Information MSOLAP$POWERPIVOT Service started. Microsoft SQL Server Analysis Services 64 Bit Evaluation (x64) RTM 12.0.1997.5.
4/16/2014 1:45:18 PM  Information MSOLAP$POWERPIVOT The flight recorder was started.
4/14/2014 6:45:37 PM  Information MSOLAP$POWERPIVOT Software usage metrics are disabled.
```

 <span data-ttu-id="fd083-208">**Journaux ULS SharePoint, dernières 48 heures**</span><span class="sxs-lookup"><span data-stu-id="fd083-208">**SharePoint ULS Log, last 48 hours**</span></span>

 <span data-ttu-id="fd083-209">La commande suivante retourne les messages de [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] du journal ULS créés au cours des dernières 48 heures.</span><span class="sxs-lookup"><span data-stu-id="fd083-209">The following command will return [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] messages from the ULS log that were created in the last 48 hours.</span></span> <span data-ttu-id="fd083-210">Ajustez le paramètre addhours selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="fd083-210">Adjust the addhours parameter for your need.</span></span>

```powershell
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid,level, message | Format-Table -Property * -AutoSize | Out-Default
```

 <span data-ttu-id="fd083-211">La variante suivante de la commande retourne uniquement les journaux d'événements de la catégorie **Actualisation des données** .</span><span class="sxs-lookup"><span data-stu-id="fd083-211">The following variation of the command only returns log events for the **data refresh** category.</span></span>

```powershell
Get-SPLogEvent -starttime(Get-Date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message
```

```Output
Timestamp   : 4/14/2014 7:15:01 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 43
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : The following error occurred when working with the service application, Default PowerPivot Service Application. Skipping the service application..

Timestamp   : 4/14/2014 7:15:02 PM
Area        : PowerPivot Service
Category    : Data Refresh
EventID     : 99
Level       : High
Correlation : 5755879c-7cab-e097-8f80-f27895d44a77
Message     : EXCEPTION: System.TimeoutException: The request channel timed out while waiting for a reply after 00:00:47.0625313. Increase the timeout value passed to 
              the call to Request or increase the SendTimeout value on the Binding. The time allotted to this operation may have been a portion of a longer timeout. 
              ---> System.TimeoutException: The HTTP request to 'http://localhost:32843/SecurityTokenServiceApplication/securitytoken.svc/actas' has exceeded the 
              allotted timeout of 00:00:54.5930000. The time allotted to this operation may have been a portion of a longer timeout. ---> System.Net.WebException: The 
              operation has timed out     at System.Net.HttpWebRequest.GetResponse()     at 
              System.ServiceModel.Channels.HttpChannelFactory`1.HttpRequestChannel.HttpChannelRequest.WaitForReply(TimeSpan timeout...
```

##  <a name="msolap-provider"></a><a name="bkmk_msolap"></a><span data-ttu-id="fd083-212">Fournisseur MSOLAP</span><span class="sxs-lookup"><span data-stu-id="fd083-212">MSOLAP Provider</span></span>
 <span data-ttu-id="fd083-213">Vérifiez le fournisseur MSOLAP.</span><span class="sxs-lookup"><span data-stu-id="fd083-213">Verify the provider MSOLAP provider.</span></span> [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]<span data-ttu-id="fd083-214">et [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] requièrent MSOLAP. 5.</span><span class="sxs-lookup"><span data-stu-id="fd083-214">and [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)] [!INCLUDE[ssGemini](../../../includes/ssgemini-md.md)] require MSOLAP.5.</span></span>

```powershell
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default
```

```Output
ProviderId ProviderType Description
---------- ------------ -----------
MSOLAP     Oledb        Microsoft OLE DB Provider for OLAP Services     
MSOLAP.3   Oledb        Microsoft OLE DB Provider for OLAP Services 9.0 
MSOLAP.4   Oledb        Microsoft OLE DB Provider for OLAP Services 10.0
MSOLAP.5   Oledb        Microsoft OLE DB Provider for OLAP Services 11.0
```

 <span data-ttu-id="fd083-215">Pour plus d’informations, voir [Installer le fournisseur OLE DB Analysis Services sur les serveurs SharePoint](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) et [Ajouter MSOLAP.5 en tant que fournisseur de données approuvé dans Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd083-215">For more information, see [Install the Analysis Services OLE DB Provider on SharePoint Servers](../../../sql-server/install/install-the-analysis-services-ole-db-provider-on-sharepoint-servers.md) and [Add MSOLAP.5 as a Trusted Data Provider in Excel Services](https://technet.microsoft.com/library/hh758436.aspx).</span></span>

##  <a name="adomdnet-client-library"></a><a name="bkmk_adomd"></a><span data-ttu-id="fd083-216">Bibliothèque cliente ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="fd083-216">ADOMD.Net client Library</span></span>

```powershell
Get-WMIObject -Class win32_product | Where-Object {$_.name -Like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | out-default
```

```Output
name                                                  version      vendor
----                                                  -------      ------
Microsoft SQL Server 2008 Analysis Services ADOMD.NET 10.1.2531.0  Microsoft Corporation
Microsoft SQL Server 2005 Analysis Services ADOMD.NET 9.00.1399.06 Microsoft Corporation
```

 <span data-ttu-id="fd083-217">Pour plus d’informations, consultez [Installer ADOMD.NET sur des serveurs web frontaux exécutant l’Administration centrale](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-217">For more information, see [Install ADOMD.NET on Web Front-End Servers Running Central Administration](../../../sql-server/install/install-adomd-net-on-web-front-end-servers-running-central-administration.md).</span></span>

##  <a name="health-data-collection-rules"></a><a name="bkmk_health_collection"></a><span data-ttu-id="fd083-218">Règles de collecte des données d’intégrité</span><span class="sxs-lookup"><span data-stu-id="fd083-218">Health Data Collection Rules</span></span>
 <span data-ttu-id="fd083-219">Vérifiez que l' **État** est en ligne et que la valeur **Activé** est True.</span><span class="sxs-lookup"><span data-stu-id="fd083-219">Verify the **Status** is Online and **Enabled** is True.</span></span>

```powershell
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -Like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

```Output
Name                         Status Enabled TableName                   DaysToKeepDetailedData
----                         ------ ------- ---------                   ----------------------
PowerPivot Connections       OnlineTrue AnalysisServicesConnections  14
PowerPivot Load Data Usage   Online    True AnalysisServicesLoads                           14
PowerPivot Query Usage       Online    True AnalysisServicesRequests                        14
PowerPivot Unload Data Usage Online    True AnalysisServicesUnloads                         14
```

 <span data-ttu-id="fd083-220">Pour plus d'informations, consultez [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-220">For more information, see [PowerPivot Usage Data Collection](../../power-pivot-sharepoint/power-pivot-usage-data-collection.md).</span></span>

##  <a name="solutions"></a><a name="bkmk_solutions"></a><span data-ttu-id="fd083-221">Elles</span><span class="sxs-lookup"><span data-stu-id="fd083-221">Solutions</span></span>
 <span data-ttu-id="fd083-222">Si les autres composants sont en ligne, vous pouvez ignorer la vérification des solutions.</span><span class="sxs-lookup"><span data-stu-id="fd083-222">If the other components are online then you can skip verifying the solutions.</span></span> <span data-ttu-id="fd083-223">Toutefois, si les règles d'intégrité sont absentes, vérifiez que les deux solutions existent et sont affichées, puis vérifiez que les deux solutions PowerPivot sont **En ligne** et **Déployées**.</span><span class="sxs-lookup"><span data-stu-id="fd083-223">If however the Health rules are missing, verify the two solutions exist and showed Verify the two PowerPivot solutions are **Online** and **Deployed**.</span></span>

```powershell
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -Like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
```

<span data-ttu-id="fd083-224">SharePoint 2013 :</span><span class="sxs-lookup"><span data-stu-id="fd083-224">SharePoint 2013:</span></span>

```Output
Name                                 Status Deployed        DeploymentState DeployedServers
----                                 ------ --------        --------------- ---------------
powerpivotfarm14solution.wsp         Online     True         GlobalDeployed {UETESTA00}
powerpivotfarmsolution.wsp           Online     True         GlobalDeployed {UETESTA00}
powerpivotwebapplicationsolution.wsp Online     True WebApplicationDeployed {UETESTA00}
```

<span data-ttu-id="fd083-225">SharePoint 2010 :</span><span class="sxs-lookup"><span data-stu-id="fd083-225">SharePoint 2010:</span></span>

```Output
Name                 Status Deployed        DeploymentState DeployedServers 
----                 ------ --------        --------------- --------------- 
powerpivotfarm.wsp   Online     True         GlobalDeployed {uesql11spoint2}
powerpivotwebapp.wsp Online     True WebApplicationDeployed {uesql11spoint2}
```

 <span data-ttu-id="fd083-226">Pour plus d’informations sur le déploiement des solutions SharePoint, consultez [Déployer des packages de solutions (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span><span class="sxs-lookup"><span data-stu-id="fd083-226">For more information on how to deploy SharePoint solutions, see [Deploy solution packages (SharePoint Server 2010)](https://technet.microsoft.com/library/cc262995\(v=office.14\).aspx).</span></span>

##  <a name="manual-verification-steps"></a><a name="bkmk_manual"></a> <span data-ttu-id="fd083-227">Étapes manuelles de contrôle</span><span class="sxs-lookup"><span data-stu-id="fd083-227">Manual Verification Steps</span></span>
 <span data-ttu-id="fd083-228">Cette section décrit les étapes de vérification qui ne peuvent pas être effectuées par des applets de commande PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fd083-228">This section describes verification steps that cannot be completed with PowerShell cmdlets.</span></span>

 <span data-ttu-id="fd083-229">**Actualisation de données planifiée :** configurez la planification d'actualisation d'un classeur sur **Aussi actualiser dès que possible**.</span><span class="sxs-lookup"><span data-stu-id="fd083-229">**Scheduled Data Refresh:** Configure the refresh schedule a workbook to **Also refresh as soon as possible**.</span></span>  <span data-ttu-id="fd083-230">Pour plus d’informations, consultez la section « vérifier l’actualisation des données » de planification de l' [actualisation des données et des sources de données qui ne prennent pas en charge l’authentification Windows &#40;PowerPivot pour SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fd083-230">For more information, see the "Verify Data Refresh" section of [Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication &#40;PowerPivot for SharePoint&#41;](../../power-pivot-sharepoint/schedule-data-refresh-and-data-sources-no-windows-authentication.md).</span></span>

##  <a name="more-resources"></a><a name="bkmk_more_resources"></a><span data-ttu-id="fd083-231">Plus de ressources</span><span class="sxs-lookup"><span data-stu-id="fd083-231">More Resources</span></span>
 <span data-ttu-id="fd083-232">[Applets de commande de l’administration du serveur Web (IIS) dans Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span><span class="sxs-lookup"><span data-stu-id="fd083-232">[Web Server (IIS) Administration Cmdlets in Windows PowerShell](https://technet.microsoft.com/library/ee790599.aspx).</span></span>

 <span data-ttu-id="fd083-233">[PowerShell pour activer les services, les sites IIS et l'état du pool d'applications dans SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span><span class="sxs-lookup"><span data-stu-id="fd083-233">[PowerShell to check services, IIS sites and Application Pool status in SharePoint](https://gallery.technet.microsoft.com/office/PowerShell-to-check-a6ed72a0).</span></span>

 <span data-ttu-id="fd083-234">[Référence Windows PowerShell pour SharePoint 2013](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fd083-234">[Windows PowerShell for SharePoint 2013 reference](https://technet.microsoft.com/library/ee890108\(v=office.15\).aspx)</span></span>

 <span data-ttu-id="fd083-235">[Référence Windows PowerShell pour SharePoint Foundation 2010](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fd083-235">[Windows PowerShell for SharePoint Foundation 2010 reference](https://technet.microsoft.com/library/ee890105\(v=office.14\).aspx)</span></span>

 <span data-ttu-id="fd083-236">[Gérer Excel Services avec Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fd083-236">[Manage Excel Services with Windows PowerShell (SharePoint Server 2010)](https://technet.microsoft.com/library/ff191201\(v=office.14\).aspx)</span></span>

 [<span data-ttu-id="fd083-237">Afficher et lire les fichiers journaux d'installation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="fd083-237">View and Read SQL Server Setup Log Files</span></span>](../../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md)

 [<span data-ttu-id="fd083-238">Utiliser l'applet de commande Get-EvenLog</span><span class="sxs-lookup"><span data-stu-id="fd083-238">Use the Get-EvenLog cmdlet</span></span>](https://technet.microsoft.com/library/ee176846.aspx)

##  <a name="full-powershell-script"></a><a name="bkmk_full_script"></a><span data-ttu-id="fd083-239">Script PowerShell complet</span><span class="sxs-lookup"><span data-stu-id="fd083-239">Full PowerShell Script</span></span>
 <span data-ttu-id="fd083-240">Le script suivant contient toutes les commandes des sections précédentes.</span><span class="sxs-lookup"><span data-stu-id="fd083-240">The Following script contains all of the commands from the previous sections.</span></span> <span data-ttu-id="fd083-241">Il exécute les commandes dans l'ordre dans lequel elles sont présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="fd083-241">The script runs the commands in the same order as they are presented in this topic.</span></span> <span data-ttu-id="fd083-242">Le script contient les variantes facultatives des commandes, indiquées dans cette rubrique au cas où vous auriez besoin d'un filtrage supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="fd083-242">The script contains some optional variations of the commands noted in this topic in case you need additional filtering.</span></span> <span data-ttu-id="fd083-243">Les variantes sont désactivées par un caractère de commentaire (#).</span><span class="sxs-lookup"><span data-stu-id="fd083-243">The variations are disabled with a comment character (#).</span></span> <span data-ttu-id="fd083-244">Le script inclut également des instructions pour vérifier le mode SharePoint de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fd083-244">The script also includes some statements for verifying [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode.</span></span> <span data-ttu-id="fd083-245">Les instructions [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] sont désactivées par un caractère de commentaire (#).</span><span class="sxs-lookup"><span data-stu-id="fd083-245">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] statements are disabled with a comment character (#).</span></span>

```powershell
# This script audits services related to PowerPivot for SharePoint
$starttime = Get-Date
write-host -foregroundcolor DarkGray StartTime $starttime

Write-Host  "Import the SharePoint PowerShell snappin"
Add-PSSnapin Microsoft.Sharepoint.Powershell -EA 0

Write-Host -ForegroundColor Green "Analysis Services Windows Service"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-Service | Select name, displayname, status | Where {$_.Name -eq "msolap`$powerpivot"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "PowerPivotEngineService and PowerPivotSystemService"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"

Get-PowerPivotSystemService | Select typename, status, applications, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotSystemService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

Get-PowerPivotEngineService | Select typename, status, name, instances, farm | Format-Table -property * -AutoSize | Out-Default
# If needed, you can run the following to compare job definitions specific to the service against the results of the timer job definition section
#Get-PowerPivotEngineService | select -ExpandProperty jobdefinitions | select displayname, schedule, service | format-table -property * -autosize | out-default

#Write-Host -ForegroundColor Green "Service Instances - optional if you want to associate services with the server"
#Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
#Get-SPServiceInstance | select typename, status, server, service, instance | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel*" -or $_.TypeName -like "*Analysis Services*"} | format-table -property * -autosize | out-default
#Get-PowerPivotEngineServiceInstance  | select typename, ASServername, status, server, service, instance
#Get-PowerPivotSystemServiceInstance  | select typename, ASSServerName, status, server, service, instance

Write-Host -ForegroundColor Green "PowerPivot And Excel Service Applications"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-PowerPivotServiceApplication | Select typename,name, status, unattendedaccount, applicationpool, farm, database
Get-SPExcelServiceApplication | Select typename,  DisplayName, status

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot Service Application pool"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
# the following assumes there is only 1 PowerPivot Service Application, and returns that application's pool name.  if you have more than one, use the 2nd version
$poolname = [string](Get-PowerPivotServiceApplication | Select -Property applicationpool)
$position = $poolname.lastindexof("=")
$poolname = $poolname.substring($position+1)
$poolname = $poolname.substring(0,$poolname.length-1)
Get-SPServiceApplicationPool | Select name, status, processaccountname, id | Where {$_.Name -eq $poolname} | Format-Table -Property * -AutoSize | Out-Default

#Write-Host ""
Write-Host -ForegroundColor Green "PowerPivot and Excel Service Application Proxy"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPServiceApplicationProxy |  Select typename, status, unattendedaccount, displayname | Where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*excel services*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPServiceApplicationProxy |  select typename, status, unattendedaccount, displayname | where {$_.TypeName -like "*powerpivot*" -or $_.TypeName -like "*Reporting Services*" -or $_.TypeName -like "*excel services*"} | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "DATABASES"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPDatabase | Select name, status, server, typename | Where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPDatabase | select name, status, server, typename | where {$_.TypeName -eq "content database" -or $_.TypeName -like "*Gemini*" -or $_.TypeName -like "*ReportingServices*"}

Write-Host -ForegroundColor Green "features"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPFeature | Select displayname, status, scope, farm | Where {$_.displayName -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default
#Get-SPFeature | select displayname, status, scope, farm | where {$_.displayName -like "*powerpivot*" -or $_.displayName -like "*ReportServer*"}  | format-table -property * -autosize | out-default

Write-Host -ForegroundColor Green "Timer Jobs (Job Definitions) -- list is the same as seen in the 'Review timer job definitions' section of the management dashboard"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPTimerJob | Where {$_.service -like "*power*" -or $_.service -like "*mid*"} | Select status, displayname, LastRunTime, service | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "health rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPHealthAnalysisRule | Select name, enabled, summary | Where {$_.summary -Like "*power*"}  | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "Windows Event Log data MSSQL$POWERPIVOT and "
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*"}  | Select timegenerated, entrytype , source, message | Format-Table -Property * -autosize | Out-Default
#The following is the same command but with the Inforamtion events filtered out.
#Get-EventLog "application" | Where-Object {$_.source -like "msolap`$powerpivot*" -and ($_.entrytype -match "error" -or $_.entrytype -match "critical" -or $_.entrytype -match "warning")}  |select timegenerated, entrytype , source, message | format-table -property * -autosize | out-default

#Write-Host ""
Write-Host -ForegroundColor Green "ULS Log data"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPLogEvent -StartTime(Get-Date).AddHours(-48) | Where-Object {$_.Area -eq "powerpivot service" -and $_.level -eq "high"} | Select timestamp, area, category, eventid, level, correlation, message | Format-Table -Property * -AutoSize | Out-Default
#the following example filters for the category 'data refresh'
#Get-SPLogEvent -starttime(get-date).addhours(-48) | Where-Object {$_.category -eq "data refresh" -and $_.level -eq "high"} | select timestamp, area, category, eventid, level, correlation, message

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time

Write-Host -ForegroundColor Green "MSOLAP data provider for Excel Servivces, service application"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
$excelApp = Get-SPExcelServiceApplication
Get-SPExcelDataProvider -ExcelServiceApplication $excelApp | Select providerid, providertype, description | Where {$_.providerid -like "msolap*" } | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "ADOMD.net client library"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-WMIObject -Class win32_product | Where-Object {$_.name -like "*ado*"} | Select name, version, vendor | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Usage Data Rules"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPUsageDefinition | Select name, status, enabled, tablename, DaysToKeepDetailedData | Where {$_.name -like "powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

Write-Host -ForegroundColor Green "Solutions"
Write-Host -ForegroundColor Green ">>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>"
Get-SPSolution | Select name, status, deployed, DeploymentState, DeployedServers | Where {$_.Name -like "*powerpivot*"} | Format-Table -Property * -AutoSize | Out-Default

$time = Get-Date
Write-Host -ForegroundColor DarkGray StartTime $starttime
Write-Host -ForegroundColor DarkGray EndTime $time
```
