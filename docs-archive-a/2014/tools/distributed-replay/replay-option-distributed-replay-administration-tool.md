---
title: Option replay (outil d’administration Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: d7bce6a5-d414-488d-a3cd-50c1c62019c4
author: stevestein
ms.author: sstein
ms.openlocfilehash: a3114d7c2a2a7908e4e010fbf5d80c7d332d264c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707988"
---
# <a name="replay-option-distributed-replay-administration-tool"></a><span data-ttu-id="f869a-102">Option replay (outil d'administration Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="f869a-102">Replay Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="f869a-103">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] outil d’administration Distributed Replay, `DReplay.exe` , est un outil en ligne de commande que vous pouvez utiliser pour communiquer avec le contrôleur Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="f869a-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="f869a-104">Cette rubrique décrit l’option de ligne de commande **replay** et la syntaxe correspondante.</span><span class="sxs-lookup"><span data-stu-id="f869a-104">This topic describes the **replay** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="f869a-105">L’option **replay** initialise l’étape de relecture d’événement, dans laquelle le contrôleur distribue des données de relecture aux clients spécifiés, lance la relecture distribuée et synchronise les clients.</span><span class="sxs-lookup"><span data-stu-id="f869a-105">The **replay** option initiates the event replay stage, in which the controller dispatches replay data to the specified clients, launches the distributed replay and synchronizes the clients.</span></span> <span data-ttu-id="f869a-106">Chaque client participant à la relecture peut éventuellement enregistrer l'activité de relecture et enregistrer un fichier de trace de résultats localement.</span><span class="sxs-lookup"><span data-stu-id="f869a-106">Optionally, each client participating in the replay can record the replay activity and save a result trace file locally.</span></span>

 <span data-ttu-id="f869a-107">![Icône de lien vers une rubrique](../../database-engine/media/topic-link.gif "Icône du lien de rubrique") Pour plus d’informations sur les conventions de syntaxe utilisées par l’outil d’administration, consultez [Conventions de la syntaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f869a-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="f869a-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f869a-108">Syntax</span></span>

```

      dreplay replay [-mcontroller] -dcontroller_working_dir [-o]
    [-starget_server] -wclients [-cconfig_file]
    [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="f869a-109">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f869a-109">Parameters</span></span>
 <span data-ttu-id="f869a-110">**-m** *contrôleur* spécifie le nom d’ordinateur du contrôleur.</span><span class="sxs-lookup"><span data-stu-id="f869a-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="f869a-111">Vous pouvez utiliser «`localhost`» ou «`.`» pour désigner l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="f869a-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="f869a-112">Si le paramètre **-m** n’est pas spécifié, l’ordinateur local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="f869a-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="f869a-113">**-d** *controller_working_dir* spécifie le répertoire sur le contrôleur où le fichier intermédiaire sera stocké.</span><span class="sxs-lookup"><span data-stu-id="f869a-113">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="f869a-114">Le paramètre **-d** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="f869a-114">The **-d** parameter is required.</span></span>

 <span data-ttu-id="f869a-115">Les conditions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="f869a-115">The following requirements apply:</span></span>

-   <span data-ttu-id="f869a-116">Le répertoire doit résider sur le contrôleur.</span><span class="sxs-lookup"><span data-stu-id="f869a-116">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="f869a-117">Vous devez spécifier le chemin complet, en commençant par une lettre de lecteur (par exemple, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="f869a-117">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="f869a-118">Le chemin d'accès ne doit pas se terminer par une barre oblique inverse «`\`».</span><span class="sxs-lookup"><span data-stu-id="f869a-118">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="f869a-119">Les chemins d'accès UNC ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f869a-119">UNC paths are not supported.</span></span>

 <span data-ttu-id="f869a-120">**-o** Capture l’activité de relecture des clients et l’enregistre dans un fichier de trace de résultats dans le chemin d’accès spécifié par l' `<ResultDirectory>` élément dans le fichier de configuration client, `DReplayClient.xml` .</span><span class="sxs-lookup"><span data-stu-id="f869a-120">**-o** Captures the clients' replay activity and saves it to a result trace file in the path specified by the `<ResultDirectory>` element in the client configuration file, `DReplayClient.xml`.</span></span>

 <span data-ttu-id="f869a-121">Lorsque le paramètre **-o** n’est pas spécifié, le fichier de trace de résultats n’est pas généré.</span><span class="sxs-lookup"><span data-stu-id="f869a-121">When the **-o** parameter is not specified, the result trace file is not generated.</span></span> <span data-ttu-id="f869a-122">La sortie de console retourne les informations de résumé à la fin de la relecture, mais aucune autre statistique de relecture n'est disponible.</span><span class="sxs-lookup"><span data-stu-id="f869a-122">The console output returns summary information at the end of replay, but no other replay statistics are available.</span></span>

 <span data-ttu-id="f869a-123">**-s** *target_server* spécifie l’instance cible de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à partir de laquelle la charge de travail distribuée doit être relue.</span><span class="sxs-lookup"><span data-stu-id="f869a-123">**-s** *target_server* Specifies the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that the distributed workload should be replayed against.</span></span> <span data-ttu-id="f869a-124">Vous devez spécifier ce paramètre au format **nom_serveur[\nom_instance]** .</span><span class="sxs-lookup"><span data-stu-id="f869a-124">You must specify this parameter in the format **server_name[\instance name]**.</span></span>

 <span data-ttu-id="f869a-125">Vous ne pouvez pas utiliser «`localhost`» ou «`.`» comme serveur cible.</span><span class="sxs-lookup"><span data-stu-id="f869a-125">You cannot use "`localhost`" or "`.`" as the target server.</span></span>

 <span data-ttu-id="f869a-126">Le paramètre **-s** n’est pas obligatoire si l’élément `<Server>` est spécifié dans la section `<ReplayOptions>` du fichier de configuration de relecture `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="f869a-126">The **-s** parameter is not required if the `<Server>` element is specified in the `<ReplayOptions>` section of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="f869a-127">Si le paramètre **-s** est utilisé, l’élément `<Server>` dans la section `<ReplayOptions>` du fichier de configuration de relecture est ignoré.</span><span class="sxs-lookup"><span data-stu-id="f869a-127">If the **-s** parameter is used, the `<Server>` element in the `<ReplayOptions>` section of the replay configuration file will be ignored.</span></span>

 <span data-ttu-id="f869a-128">**-w** *clients* ce paramètre obligatoire est une liste séparée par des virgules (sans espaces) qui spécifie les noms d’ordinateur des clients qui doivent participer à la relecture distribuée.</span><span class="sxs-lookup"><span data-stu-id="f869a-128">**-w** *clients* This required parameter is a comma-separated list (without spaces) that specifies the computer names of clients that should participate in the distributed replay.</span></span> <span data-ttu-id="f869a-129">Les adresses IP ne sont pas autorisées.</span><span class="sxs-lookup"><span data-stu-id="f869a-129">IP addresses are not allowed.</span></span> <span data-ttu-id="f869a-130">Sachez que les clients doivent être déjà enregistrés avec le contrôleur.</span><span class="sxs-lookup"><span data-stu-id="f869a-130">Be aware that the clients must already be registered with the controller.</span></span>

> [!NOTE]
>  <span data-ttu-id="f869a-131">Chaque client s'inscrit avec le contrôleur spécifié dans le fichier de configuration client lors du démarrage du service client.</span><span class="sxs-lookup"><span data-stu-id="f869a-131">Each client registers with the controller that is specified in the client configuration file when the client service starts.</span></span>

 <span data-ttu-id="f869a-132">**-c** *Config_file* est le chemin d’accès complet du fichier de configuration de relecture. utilisé pour spécifier l’emplacement où il est stocké dans un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="f869a-132">**-c** *config_file* Is the full path of the replay configuration file; used to specify the location when it is stored in a different location.</span></span>

 <span data-ttu-id="f869a-133">Le paramètre **-c** n’est pas obligatoire si vous voulez utiliser les valeurs par défaut du fichier de configuration de relecture `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="f869a-133">The **-c** parameter is not required if you want to use the default values of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="f869a-134">**-f** *status_interval* spécifie la fréquence (en secondes) à laquelle afficher l’État.</span><span class="sxs-lookup"><span data-stu-id="f869a-134">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="f869a-135">Si **-f** n’est pas spécifié, l’intervalle par défaut est de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="f869a-135">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="f869a-136">Exemples</span><span class="sxs-lookup"><span data-stu-id="f869a-136">Examples</span></span>
 <span data-ttu-id="f869a-137">Dans cet exemple, la relecture distribuée tire beaucoup de son comportement d'un fichier de configuration de relecture modifié, `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="f869a-137">In this example, the distributed replay derives much of its behavior from a modified replay configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="f869a-138">Le paramètre **-m** spécifie qu’un ordinateur nommé `controller1` agit en tant que contrôleur.</span><span class="sxs-lookup"><span data-stu-id="f869a-138">The **-m** parameter specifies that a computer named `controller1` acts as the controller.</span></span> <span data-ttu-id="f869a-139">Le nom d'ordinateur doit être spécifié quand le service contrôleur s'exécute sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f869a-139">The computer name must be specified when the controller service is running on a different computer.</span></span>

-   <span data-ttu-id="f869a-140">Le paramètre **-d** spécifie l’emplacement du fichier intermédiaire sur le contrôleur, `c:\WorkingDir`.</span><span class="sxs-lookup"><span data-stu-id="f869a-140">The **-d** parameter specifies the location of the intermediate file on the controller, `c:\WorkingDir`.</span></span>

-   <span data-ttu-id="f869a-141">Le paramètre **-o** spécifie que chaque client spécifié capture l’activité de relecture et l’enregistre dans un fichier de trace de résultats.</span><span class="sxs-lookup"><span data-stu-id="f869a-141">The **-o** parameter specifies that each specified client capture the replay activity and save it to a result trace file.</span></span> <span data-ttu-id="f869a-142">Remarque : L'élément `<ResultTrace>` dans le fichier de configuration peut être utilisé pour spécifier si le nombre de lignes et le jeu de résultats doivent être enregistrés.</span><span class="sxs-lookup"><span data-stu-id="f869a-142">Note: The `<ResultTrace>` element in the configuration file can be used to specify if row count and result set be recorded.</span></span>

-   <span data-ttu-id="f869a-143">Le paramètre **-w** spécifie que les ordinateurs `client1` à `client4` participent en tant que clients à la relecture distribuée.</span><span class="sxs-lookup"><span data-stu-id="f869a-143">The **-w** parameter specifies that computers `client1` through `client4` participate as clients in the distributed replay.</span></span>

-   <span data-ttu-id="f869a-144">Le paramètre **-c** est utilisé pour pointer vers le fichier de configuration modifié `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="f869a-144">The **-c** parameter is used to point to the modified configuration file, `DReplay.exe.replay.config`.</span></span>

-   <span data-ttu-id="f869a-145">Le paramètre **-s** n’est pas obligatoire, car l’élément `<Server>` est spécifié dans l’élément `<ReplayOptions>` du fichier de configuration de relecture `DReplay.exe.replay.config`.</span><span class="sxs-lookup"><span data-stu-id="f869a-145">The **-s** parameter is not required because the `<Server>` element is specified in the `<ReplayOptions>` element of the replay configuration file, `DReplay.exe.replay.config`.</span></span>

 <span data-ttu-id="f869a-146">L'étape de relecture d'événement est initialisée avec la syntaxe suivante, lorsque l'outil d'administration est exécuté à partir d'un autre ordinateur que le contrôleur :</span><span class="sxs-lookup"><span data-stu-id="f869a-146">The event replay stage is initiated with the following syntax, when the administration tool is run from a different computer than the controller:</span></span>

```
dreplay replay -m controller1 -d c:\WorkingDir -o -w client1,client2,client3,client4 -c c:\DReplay.exe.replay.config
```

 <span data-ttu-id="f869a-147">Pour spécifier un mode de mise en séquence synchrone, l'élément `<SequencingMode>` du fichier `DReplay.exe.replay.config` est défini comme égal à la valeur `synchronization`.</span><span class="sxs-lookup"><span data-stu-id="f869a-147">To specify a synchronous sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `synchronization`.</span></span> <span data-ttu-id="f869a-148">La section `<ResultTrace>` du fichier de configuration de relecture est modifiée pour spécifier que le nombre de lignes doit être enregistré.</span><span class="sxs-lookup"><span data-stu-id="f869a-148">The `<ResultTrace>` section of the replay configuration file is modified to specify that row count be recorded.</span></span> <span data-ttu-id="f869a-149">Ces modifications sont illustrées dans l'exemple XML suivant :</span><span class="sxs-lookup"><span data-stu-id="f869a-149">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance</Server>
        <SequencingMode>synchronization</SequencingMode>
        <ConnectTimeScale></ConnectTimeScale>
        <ThinkTimeScale></ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

 <span data-ttu-id="f869a-150">Pour spécifier un mode de séquencement en simultané (stress), l'élément `<SequencingMode>` du fichier `DReplay.exe.replay.config` est défini comme égal à la valeur `stress`.</span><span class="sxs-lookup"><span data-stu-id="f869a-150">To specify a stress sequencing mode, the `<SequencingMode>` element of the `DReplay.exe.replay.config` file is set equal to the value `stress`.</span></span> <span data-ttu-id="f869a-151">Les éléments `<ConnectTimeScale>` et `<ThinkTimeScale>` ont la valeur `50` (pour spécifier 50 pour cent).</span><span class="sxs-lookup"><span data-stu-id="f869a-151">The `<ConnectTimeScale>` and `<ThinkTimeScale>` elements are set to the value `50` (to specify 50 percent).</span></span> <span data-ttu-id="f869a-152">Pour plus d'informations sur le délai de connexion et le temps de réflexion, consultez [Configure Distributed Replay](configure-distributed-replay.md).</span><span class="sxs-lookup"><span data-stu-id="f869a-152">For more information about connect time and think time, see [Configure Distributed Replay](configure-distributed-replay.md).</span></span> <span data-ttu-id="f869a-153">Ces modifications sont illustrées dans l'exemple XML suivant :</span><span class="sxs-lookup"><span data-stu-id="f869a-153">These changes are shown in the following XML example:</span></span>

```
<?xml version='1.0'?>
<Options>
    <ReplayOptions>
        <Server>server_name\replay_target_instance_name</Server>
        <SequencingMode>stress</SequencingMode>
        <ConnectTimeScale>50</ConnectTimeScale>
        <ThinkTimeScale>50</ThinkTimeScale>
        <HealthmonInterval>60</HealthmonInterval>
        <QueryTimeout>3600</QueryTimeout>
        <ThreadsPerClient></ThreadsPerClient>
    </ReplayOptions>
    <OutputOptions>
        <ResultTrace>
            <RecordRowCount>Yes</RecordRowCount>
            <RecordResultSet>No</RecordResultSet>
        </ResultTrace>
    </OutputOptions>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="f869a-154">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f869a-154">Permissions</span></span>
 <span data-ttu-id="f869a-155">Vous devez exécuter l'outil d'administration en tant qu'utilisateur interactif, comme un utilisateur local ou un compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="f869a-155">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="f869a-156">Pour utiliser un compte d'utilisateur local, l'outil d'administration et le contrôleur doivent s'exécuter sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f869a-156">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="f869a-157">Pour plus d’informations, voir [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="f869a-157">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f869a-158">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f869a-158">See Also</span></span>
 <span data-ttu-id="f869a-159">Relire les [données de trace](replay-trace-data.md) [passez en revue les résultats de relecture](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [configurer Distributed Replay](configure-distributed-replay.md) [Forum de Distributed Replay SQL Server](https://social.technet.microsoft.com/Forums/sl/sqldru/) [à l’aide de Distributed Replay pour tester la charge de votre SQL Server-partie 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [à l’aide de Distributed Replay pour effectuer un test de charge de votre SQL Server-partie 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span><span class="sxs-lookup"><span data-stu-id="f869a-159">[Replay Trace Data](replay-trace-data.md) [Review the Replay Results](review-the-replay-results.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md) [SQL Server Distributed Replay Forum](https://social.technet.microsoft.com/Forums/sl/sqldru/) [Using Distributed Replay to Load Test Your SQL Server - Part 2](https://docs.microsoft.com/archive/blogs/msdn/mspfe/using-distributed-replay-to-load-test-your-sql-serverpart-2) [Using Distributed Replay to Load Test Your SQL Server - Part 1](https://docs.microsoft.com/archive/blogs/batuhanyildiz/using-distributed-replay-to-load-test-your-sql-serverpart-1)</span></span>


