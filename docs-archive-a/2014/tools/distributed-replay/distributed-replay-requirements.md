---
title: Configuration requise pour la Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 6fffee7d-891f-4d9d-b2c3-dd19855a1c2c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 66be93534756360e722fcccaf405815e14ffa7ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604774"
---
# <a name="distributed-replay-requirements"></a><span data-ttu-id="10a19-102">Distributed Replay Requirements</span><span class="sxs-lookup"><span data-stu-id="10a19-102">Distributed Replay Requirements</span></span>
  <span data-ttu-id="10a19-103">Avant d’utiliser la fonctionnalité [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay, prenez connaissance des spécifications du produit présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="10a19-103">Before using the [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay feature, consider the product requirements that are outlined in this topic.</span></span>  
  
## <a name="input-trace-requirements"></a><span data-ttu-id="10a19-104">Spécifications des données de trace d'entrée</span><span class="sxs-lookup"><span data-stu-id="10a19-104">Input Trace Requirements</span></span>  
 <span data-ttu-id="10a19-105">Pour que les données de trace puissent être correctement relues, elles doivent répondre à des spécifications de version et de format et contenir des événements et des colonnes obligatoires.</span><span class="sxs-lookup"><span data-stu-id="10a19-105">To successfully replay trace data, it must meet the requirements for version and format, and contain the required events and columns.</span></span>  
  
### <a name="input-trace-versions"></a><span data-ttu-id="10a19-106">Versions de trace d'entrée</span><span class="sxs-lookup"><span data-stu-id="10a19-106">Input Trace Versions</span></span>  
 <span data-ttu-id="10a19-107">Distributed Replay prend en charge les données de trace d'entrée recueillies dans les versions suivantes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="10a19-107">Distributed Replay supports input trace data that is collected on the following versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
-   [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]  
  
-   [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]  
  
-   [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]  
  
-   [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]  
  
### <a name="input-trace-formats"></a><span data-ttu-id="10a19-108">Formats de trace d'entrée</span><span class="sxs-lookup"><span data-stu-id="10a19-108">Input Trace Formats</span></span>  
 <span data-ttu-id="10a19-109">Les données de trace d'entrée peuvent se présenter sous l'un des formats suivants :</span><span class="sxs-lookup"><span data-stu-id="10a19-109">The input trace data can be in any of the following formats:</span></span>  
  
-   <span data-ttu-id="10a19-110">Un fichier de trace unique ayant l'extension `.trc` .</span><span class="sxs-lookup"><span data-stu-id="10a19-110">A single trace file that has the `.trc` extension.</span></span>  
  
-   <span data-ttu-id="10a19-111">Un jeu de fichiers de trace de substitution qui suivent la convention d’affectation des noms de substitution de fichier, par exemple : `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="10a19-111">A set of rollover trace files that follow the file rollover naming convention, for example: `<TraceFile>.trc`, `<TraceFile>_1.trc`, `<TraceFile>_2.trc`, `<TraceFile>_3.trc`, ... `<TraceFile>_n.trc`.</span></span>  
  
### <a name="input-trace-events-and-columns"></a><span data-ttu-id="10a19-112">Événements et colonnes de trace d'entrée</span><span class="sxs-lookup"><span data-stu-id="10a19-112">Input Trace Events and Columns</span></span>  
 <span data-ttu-id="10a19-113">Les données de trace d'entrée doivent contenir des événements et des colonnes spécifiques pour pouvoir être relues par Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="10a19-113">The input trace data must contain specific events and columns to be replayed by Distributed Replay.</span></span> <span data-ttu-id="10a19-114">Le modèle **TSQL_Replay** , dans [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] , contient tous les événements et toutes les colonnes obligatoires, ainsi que des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="10a19-114">The **TSQL_Replay** template in [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] contains all of the required events and columns, in addition to extra information.</span></span> <span data-ttu-id="10a19-115">Pour plus d’informations sur ce modèle, consultez [Conditions préalables à la relecture](../sql-server-profiler/replay-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a19-115">For more information about that template, see [Replay Requirements](../sql-server-profiler/replay-requirements.md).</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="10a19-116">Si vous n’utilisez pas le modèle **TSQL_Replay** pour capturer les données de trace d’entrée, ou si les conditions d’entrée de trace ne sont pas satisfaites, vous pouvez recevoir des résultats de relecture inattendus.</span><span class="sxs-lookup"><span data-stu-id="10a19-116">If you do not use the **TSQL_Replay** template to capture the input trace data, or if the input trace requirements are not satisfied, you may receive unexpected replay results.</span></span>  
  
 <span data-ttu-id="10a19-117">Vous pouvez également créer un modèle de trace personnalisé et l'utiliser pour relire des événements avec Distributed Replay, à condition que ce modèle contienne les événements suivants :</span><span class="sxs-lookup"><span data-stu-id="10a19-117">You can also create a custom trace template and use it to replay events with Distributed Replay, as long as it contains the following events:</span></span>  
  
-   <span data-ttu-id="10a19-118">Audit Login</span><span class="sxs-lookup"><span data-stu-id="10a19-118">Audit Login</span></span>  
  
-   <span data-ttu-id="10a19-119">Audit Logout</span><span class="sxs-lookup"><span data-stu-id="10a19-119">Audit Logout</span></span>  
  
-   <span data-ttu-id="10a19-120">ExistingConnection</span><span class="sxs-lookup"><span data-stu-id="10a19-120">ExistingConnection</span></span>  
  
-   <span data-ttu-id="10a19-121">RPC Output Parameter</span><span class="sxs-lookup"><span data-stu-id="10a19-121">RPC Output Parameter</span></span>  
  
-   <span data-ttu-id="10a19-122">RPC:Completed</span><span class="sxs-lookup"><span data-stu-id="10a19-122">RPC:Completed</span></span>  
  
-   <span data-ttu-id="10a19-123">RPC:Starting</span><span class="sxs-lookup"><span data-stu-id="10a19-123">RPC:Starting</span></span>  
  
-   <span data-ttu-id="10a19-124">SQL:BatchCompleted</span><span class="sxs-lookup"><span data-stu-id="10a19-124">SQL:BatchCompleted</span></span>  
  
-   <span data-ttu-id="10a19-125">SQL:BatchStarting</span><span class="sxs-lookup"><span data-stu-id="10a19-125">SQL:BatchStarting</span></span>  
  
 <span data-ttu-id="10a19-126">Si vous relisez des curseurs côté serveur, les événements suivants sont également obligatoires :</span><span class="sxs-lookup"><span data-stu-id="10a19-126">If you are replaying server-side cursors, the following events are also required:</span></span>  
  
-   <span data-ttu-id="10a19-127">CursorClose</span><span class="sxs-lookup"><span data-stu-id="10a19-127">CursorClose</span></span>  
  
-   <span data-ttu-id="10a19-128">CursorExecute</span><span class="sxs-lookup"><span data-stu-id="10a19-128">CursorExecute</span></span>  
  
-   <span data-ttu-id="10a19-129">CursorOpen</span><span class="sxs-lookup"><span data-stu-id="10a19-129">CursorOpen</span></span>  
  
-   <span data-ttu-id="10a19-130">CursorPrepare</span><span class="sxs-lookup"><span data-stu-id="10a19-130">CursorPrepare</span></span>  
  
-   <span data-ttu-id="10a19-131">CursorUnprepare</span><span class="sxs-lookup"><span data-stu-id="10a19-131">CursorUnprepare</span></span>  
  
 <span data-ttu-id="10a19-132">Si vous relisez des instructions SQL préparées côté serveur, les événements suivants sont également obligatoires :</span><span class="sxs-lookup"><span data-stu-id="10a19-132">If you are replaying server-side prepared SQL statements, the following events are also required:</span></span>  
  
-   <span data-ttu-id="10a19-133">Exec Prepared SQL</span><span class="sxs-lookup"><span data-stu-id="10a19-133">Exec Prepared SQL</span></span>  
  
-   <span data-ttu-id="10a19-134">Prepare SQL</span><span class="sxs-lookup"><span data-stu-id="10a19-134">Prepare SQL</span></span>  
  
 <span data-ttu-id="10a19-135">Toutes les données de trace d'entrée doivent contenir les colonnes suivantes :</span><span class="sxs-lookup"><span data-stu-id="10a19-135">All input trace data must contain the following columns:</span></span>  
  
-   <span data-ttu-id="10a19-136">Classe d'événements</span><span class="sxs-lookup"><span data-stu-id="10a19-136">Event Class</span></span>  
  
-   <span data-ttu-id="10a19-137">EventSequence</span><span class="sxs-lookup"><span data-stu-id="10a19-137">EventSequence</span></span>  
  
-   <span data-ttu-id="10a19-138">TextData</span><span class="sxs-lookup"><span data-stu-id="10a19-138">TextData</span></span>  
  
-   <span data-ttu-id="10a19-139">Nom de l’application</span><span class="sxs-lookup"><span data-stu-id="10a19-139">Application Name</span></span>  
  
-   <span data-ttu-id="10a19-140">LoginName</span><span class="sxs-lookup"><span data-stu-id="10a19-140">LoginName</span></span>  
  
-   <span data-ttu-id="10a19-141">nom_base_de_données</span><span class="sxs-lookup"><span data-stu-id="10a19-141">DatabaseName</span></span>  
  
-   <span data-ttu-id="10a19-142">ID de base de données</span><span class="sxs-lookup"><span data-stu-id="10a19-142">Database ID</span></span>  
  
-   <span data-ttu-id="10a19-143">HostName</span><span class="sxs-lookup"><span data-stu-id="10a19-143">HostName</span></span>  
  
-   <span data-ttu-id="10a19-144">Binary Data</span><span class="sxs-lookup"><span data-stu-id="10a19-144">Binary Data</span></span>  
  
-   <span data-ttu-id="10a19-145">SPID</span><span class="sxs-lookup"><span data-stu-id="10a19-145">SPID</span></span>  
  
-   <span data-ttu-id="10a19-146">Heure de Début</span><span class="sxs-lookup"><span data-stu-id="10a19-146">Start Time</span></span>  
  
-   <span data-ttu-id="10a19-147">EndTime</span><span class="sxs-lookup"><span data-stu-id="10a19-147">EndTime</span></span>  
  
-   <span data-ttu-id="10a19-148">IsSystem</span><span class="sxs-lookup"><span data-stu-id="10a19-148">IsSystem</span></span>  
  
## <a name="supported-input-trace-and-target-server-combinations"></a><span data-ttu-id="10a19-149">Combinaisons de traces d'entrée et de serveurs cibles prises en charge</span><span class="sxs-lookup"><span data-stu-id="10a19-149">Supported Input Trace and Target Server Combinations</span></span>  
 <span data-ttu-id="10a19-150">Le tableau suivant répertorie les versions de données de trace prises en charge et, pour chacune d'entre elles, les versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prises en charge avec lesquelles les données peuvent être relues.</span><span class="sxs-lookup"><span data-stu-id="10a19-150">The following table lists the supported versions of trace data, and for each, the supported versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that data can be replayed against.</span></span>  
  
|<span data-ttu-id="10a19-151">Version de données de trace d'entrée</span><span class="sxs-lookup"><span data-stu-id="10a19-151">Version of Input Trace Data</span></span>|<span data-ttu-id="10a19-152">Versions de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prises en charge pour l'instance de serveur cible</span><span class="sxs-lookup"><span data-stu-id="10a19-152">Supported Versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the Target Server Instance</span></span>|  
|---------------------------------|------------------------------------------------------------------------------------|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="10a19-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a19-153">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]<span data-ttu-id="10a19-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a19-154">, [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="10a19-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a19-155">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]<span data-ttu-id="10a19-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a19-156">, [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|[!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]|  
  
## <a name="operating-system-requirements"></a><span data-ttu-id="10a19-157">Systèmes d'exploitation requis</span><span class="sxs-lookup"><span data-stu-id="10a19-157">Operating System Requirements</span></span>  
 <span data-ttu-id="10a19-158">Les systèmes d'exploitation pris en charge pour exécuter l'outil d'administration et les services contrôleur et clients sont les mêmes que dans votre instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="10a19-158">Supported operating systems for running the administration tool and the controller and client services is the same as your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="10a19-159">Pour plus d’informations sur les systèmes d’exploitation pris en charge pour votre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, consultez [configurations matérielle et logicielle requises pour l’installation de SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="10a19-159">For more information about which operating systems are supported for your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance, see [Hardware and Software Requirements for Installing SQL Server 2014](../../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).</span></span>  
  
 <span data-ttu-id="10a19-160">Les fonctionnalités Distributed Replay sont prises en charge à la fois sur les systèmes d'exploitation basés sur des processeurs x86 et ceux basés sur des processeurs x64.</span><span class="sxs-lookup"><span data-stu-id="10a19-160">Distributed Replay features are supported on both x86-based and x64-based operating systems.</span></span> <span data-ttu-id="10a19-161">Pour les systèmes d'exploitation basés sur des processeurs x64, seul le mode Windows on Windows (WOW) est pris en charge.</span><span class="sxs-lookup"><span data-stu-id="10a19-161">For x64-based operating systems, only Windows on Windows (WOW) mode is supported.</span></span>  
  
## <a name="installation-limitations"></a><span data-ttu-id="10a19-162">Limitations d'installation</span><span class="sxs-lookup"><span data-stu-id="10a19-162">Installation Limitations</span></span>  
 <span data-ttu-id="10a19-163">Un ordinateur ne peut avoir qu'une seule instance de chaque fonctionnalité Distributed Replay installée.</span><span class="sxs-lookup"><span data-stu-id="10a19-163">Any one computer can only have a single instance of each Distributed Replay feature installed.</span></span> <span data-ttu-id="10a19-164">Le tableau suivant indique le nombre d'installations autorisées pour chaque fonctionnalité dans un même environnement Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="10a19-164">The following table lists how many installations of each feature are allowed in a single Distributed Replay environment.</span></span>  
  
|<span data-ttu-id="10a19-165">Fonctionnalité de Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="10a19-165">Distributed Replay Feature</span></span>|<span data-ttu-id="10a19-166">Nombre maximal d'installations par environnement de relecture</span><span class="sxs-lookup"><span data-stu-id="10a19-166">Maximum Installations Per Replay Environment</span></span>|  
|--------------------------------|--------------------------------------------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="10a19-167">Service Distributed Replay Controller</span><span class="sxs-lookup"><span data-stu-id="10a19-167">Distributed Replay controller service</span></span>|<span data-ttu-id="10a19-168">1</span><span class="sxs-lookup"><span data-stu-id="10a19-168">1</span></span>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="10a19-169">Service Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="10a19-169">Distributed Replay client service</span></span>|<span data-ttu-id="10a19-170">16 (ordinateurs physiques ou virtuels)</span><span class="sxs-lookup"><span data-stu-id="10a19-170">16 (physical or virtual computers)</span></span>|  
|<span data-ttu-id="10a19-171">Outil d'administration</span><span class="sxs-lookup"><span data-stu-id="10a19-171">Administration tool</span></span>|<span data-ttu-id="10a19-172">Illimité</span><span class="sxs-lookup"><span data-stu-id="10a19-172">Unlimited</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="10a19-173">Bien qu'une seule instance de l'outil d'administration puisse être installée sur un même ordinateur, vous pouvez en démarrer plusieurs instances.</span><span class="sxs-lookup"><span data-stu-id="10a19-173">Although only one instance of the administration tool can be installed on a single computer, you can start multiple instances of the administration tool.</span></span> <span data-ttu-id="10a19-174">Les commandes émises depuis plusieurs outils d'administration sont résolues dans l'ordre de leur réception.</span><span class="sxs-lookup"><span data-stu-id="10a19-174">Commands issued from multiple administration tools are resolved in the order in which they are received.</span></span>  
  
## <a name="data-access-provider"></a><span data-ttu-id="10a19-175">Fournisseur d'accès aux données</span><span class="sxs-lookup"><span data-stu-id="10a19-175">Data Access Provider</span></span>  
 <span data-ttu-id="10a19-176">Distributed Replay ne prend en charge que le fournisseur d'accès aux données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="10a19-176">Distributed Replay only supports the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC data access provider.</span></span>  
  
## <a name="target-server-preparation-requirements"></a><span data-ttu-id="10a19-177">Spécifications requises pour la préparation du serveur cible</span><span class="sxs-lookup"><span data-stu-id="10a19-177">Target Server Preparation Requirements</span></span>  
 <span data-ttu-id="10a19-178">Nous conseillons de placer le serveur cible dans un environnement de test.</span><span class="sxs-lookup"><span data-stu-id="10a19-178">We recommend that the target server be located in a test environment.</span></span> <span data-ttu-id="10a19-179">Pour relire les données de trace avec une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] différente de celle qui a servi à les enregistrer, assurez-vous que les opérations suivantes ont été effectuées sur le serveur cible :</span><span class="sxs-lookup"><span data-stu-id="10a19-179">To replay trace data against a different instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] than it was originally recorded, make sure that the following has been done to the target server:</span></span>  
  
-   <span data-ttu-id="10a19-180">Toutes les connexions et tous les utilisateurs contenus dans les données de trace doivent être présents dans la même base de données sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="10a19-180">All logins and users that are contained in the trace data must be present in the same database on the target server.</span></span>  
  
-   <span data-ttu-id="10a19-181">Toutes les connexions et tous les utilisateurs présents sur le serveur cible doivent avoir les mêmes autorisations que sur le serveur d'origine.</span><span class="sxs-lookup"><span data-stu-id="10a19-181">All logins and users on the target server must have the same permissions they had on the original server.</span></span>  
  
-   <span data-ttu-id="10a19-182">Les ID de base de données sur la cible doivent idéalement être identiques à ceux qui sont sur la source.</span><span class="sxs-lookup"><span data-stu-id="10a19-182">The database IDs on the target ideally should be the same as those on the source.</span></span> <span data-ttu-id="10a19-183">Si ce n’est pas le cas, la mise en correspondance peut être effectuée sur la base du **DatabaseName** s’il est présent dans la trace.</span><span class="sxs-lookup"><span data-stu-id="10a19-183">However, if they are not the same, matching can be performed based on **DatabaseName** if it is present in the trace.</span></span>  
  
-   <span data-ttu-id="10a19-184">La base de données par défaut de chaque connexion contenue dans les données de trace doit être définie (sur le serveur cible) en tant que base de données cible relative à la connexion.</span><span class="sxs-lookup"><span data-stu-id="10a19-184">The default database for each login that is contained in the trace data must be set (on the target server) to the respective target database of the login.</span></span> <span data-ttu-id="10a19-185">Par exemple, les données de trace à relire contiennent les activités de la connexion **Fred**dans la base de données **Fred_Db** située sur l’instance d’origine de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10a19-185">For example, the trace data to be replayed contains activity for the login, **Fred**, in the database **Fred_Db** on the original instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="10a19-186">Par conséquent, sur le serveur cible, la base de données par défaut de la connexion **Fred**doit être la base de données correspondant à **Fred_Db** (même si le nom de la base de données est différent).</span><span class="sxs-lookup"><span data-stu-id="10a19-186">Therefore, on the target server, the default database for the login, **Fred**, must be set to the database that matches **Fred_Db** (even if the database name is different).</span></span> <span data-ttu-id="10a19-187">Pour définir la base de données par défaut de la connexion, utilisez la procédure stockée système `sp_defaultdb` .</span><span class="sxs-lookup"><span data-stu-id="10a19-187">To set the default database of the login, use the `sp_defaultdb` system stored procedure.</span></span>  
  
 <span data-ttu-id="10a19-188">La relecture d'événements associés à des connexions manquantes ou incorrectes va entraîner des erreurs de relecture, mais l'opération de relecture va se poursuivre.</span><span class="sxs-lookup"><span data-stu-id="10a19-188">Replaying events associated with missing or incorrect logins results in replay errors, but the replay operation continues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10a19-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10a19-189">See Also</span></span>  
 <span data-ttu-id="10a19-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span><span class="sxs-lookup"><span data-stu-id="10a19-190">[SQL Server Distributed Replay](sql-server-distributed-replay.md) </span></span>  
 <span data-ttu-id="10a19-191">[Sécurité Distributed Replay](distributed-replay-security.md) </span><span class="sxs-lookup"><span data-stu-id="10a19-191">[Distributed Replay Security](distributed-replay-security.md) </span></span>  
 [<span data-ttu-id="10a19-192">Installer Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="10a19-192">Install Distributed Replay</span></span>](install-distributed-replay-overview.md)  
  
  
