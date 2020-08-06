---
title: Option preprocess (outil d’administration Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: 9b5012fd-233e-4a25-a2e1-585c63b70502
author: stevestein
ms.author: sstein
ms.openlocfilehash: e7f168d45b03473d958e202bd75116f4519d2fc4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603180"
---
# <a name="preprocess-option-distributed-replay-administration-tool"></a><span data-ttu-id="5f382-102">Option preprocess (outil d'administration Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="5f382-102">Preprocess Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="5f382-103">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] outil d’administration Distributed Replay, `DReplay.exe` , est un outil en ligne de commande que vous pouvez utiliser pour communiquer avec le contrôleur Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="5f382-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="5f382-104">Cette rubrique décrit l’option de ligne de commande **preprocess** et la syntaxe correspondante.</span><span class="sxs-lookup"><span data-stu-id="5f382-104">This topic describes the **preprocess** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="5f382-105">L’option **preprocess** initialise l’étape de prétraitement.</span><span class="sxs-lookup"><span data-stu-id="5f382-105">The **preprocess** option initiates the preprocess stage.</span></span> <span data-ttu-id="5f382-106">Lors de cette étape, le contrôleur prépare les données de trace d'entrée pour la relecture sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="5f382-106">During this stage, the controller prepares the input trace data for replay against the target server.</span></span>

 <span data-ttu-id="5f382-107">![Icône de lien vers une rubrique](../../database-engine/media/topic-link.gif "Icône du lien de rubrique") Pour plus d’informations sur les conventions de syntaxe utilisées par l’outil d’administration, consultez [Conventions de la syntaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5f382-107">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="5f382-108">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5f382-108">Syntax</span></span>

```

      dreplay preprocess [-mcontroller] -iinput_trace_file
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="5f382-109">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5f382-109">Parameters</span></span>
 <span data-ttu-id="5f382-110">**-m** *contrôleur* spécifie le nom d’ordinateur du contrôleur.</span><span class="sxs-lookup"><span data-stu-id="5f382-110">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="5f382-111">Vous pouvez utiliser «`localhost`» ou «`.`» pour désigner l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="5f382-111">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="5f382-112">Si le paramètre **-m** n’est pas spécifié, l’ordinateur local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5f382-112">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="5f382-113">**-i** *input_trace_file* spécifie le chemin d’accès complet du fichier de trace d’entrée sur le contrôleur, tel que `D:\Mytrace.trc` .</span><span class="sxs-lookup"><span data-stu-id="5f382-113">**-i** *input_trace_file* Specifies the full path of the input trace file on the controller, such as `D:\Mytrace.trc`.</span></span> <span data-ttu-id="5f382-114">Le paramètre **-i** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="5f382-114">The **-i** parameter is required.</span></span>

 <span data-ttu-id="5f382-115">Si des fichiers de substitution se trouvent dans le même répertoire, ils seront chargés et utilisés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="5f382-115">If there are rollover files in the same directory, they will be loaded and used automatically.</span></span> <span data-ttu-id="5f382-116">Les fichiers doivent suivre la convention d’affectation des noms de substitution de fichier, par exemple : `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span><span class="sxs-lookup"><span data-stu-id="5f382-116">The files must follow the file rollover naming convention, for example: `Mytrace.trc`, `Mytrace_1.trc`, `Mytrace_2.trc`, `Mytrace_3.trc`, ... `Mytrace_n.trc`.</span></span>

> [!NOTE]
>  <span data-ttu-id="5f382-117">Si vous utilisez l'outil d'administration sur un autre ordinateur que le contrôleur, vous devrez copier les fichiers de trace d'entrée vers le contrôleur afin qu'un chemin d'accès local puisse être utilisé pour ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="5f382-117">If you are using the administration tool on a different computer than the controller, you will need to copy the input trace files to the controller so that a local path can be used for this parameter.</span></span>

 <span data-ttu-id="5f382-118">**-d** *controller_working_dir* spécifie le répertoire sur le contrôleur où le fichier intermédiaire sera stocké.</span><span class="sxs-lookup"><span data-stu-id="5f382-118">**-d** *controller_working_dir* Specifies the directory on the controller where the intermediate file will be stored.</span></span> <span data-ttu-id="5f382-119">Le paramètre **-d** est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="5f382-119">The **-d** parameter is required.</span></span>

 <span data-ttu-id="5f382-120">Les conditions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="5f382-120">The following requirements apply:</span></span>

-   <span data-ttu-id="5f382-121">Le répertoire doit résider sur le contrôleur.</span><span class="sxs-lookup"><span data-stu-id="5f382-121">The directory must reside on the controller.</span></span>

-   <span data-ttu-id="5f382-122">Vous devez spécifier le chemin complet, en commençant par une lettre de lecteur (par exemple, `c:\WorkingDir`).</span><span class="sxs-lookup"><span data-stu-id="5f382-122">You must specify the full path, starting with a drive letter (for example, `c:\WorkingDir`).</span></span>

-   <span data-ttu-id="5f382-123">Le chemin d'accès ne doit pas se terminer par une barre oblique inverse «`\`».</span><span class="sxs-lookup"><span data-stu-id="5f382-123">The path must not end with a backslash "`\`".</span></span>

-   <span data-ttu-id="5f382-124">Les chemins d'accès UNC ne sont pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="5f382-124">UNC paths are not supported.</span></span>

 <span data-ttu-id="5f382-125">**-c** *Config_file* est le chemin d’accès complet du fichier de configuration de prétraitement ; utilisé pour spécifier l’emplacement du fichier de configuration de prétraitement lorsqu’il est stocké à un autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="5f382-125">**-c** *config_file* Is the full path of the preprocess configuration file; used to specify the location of the preprocess configuration file when stored in a different location.</span></span> <span data-ttu-id="5f382-126">Ce paramètre peut être un chemin d'accès UNC, ou peut résider localement sur l'ordinateur où vous exécutez l'outil d'administration.</span><span class="sxs-lookup"><span data-stu-id="5f382-126">This parameter can be a UNC path, or can reside locally on the computer where you run the administration tool.</span></span>

 <span data-ttu-id="5f382-127">Le paramètre **-c** n’est pas obligatoire si aucun filtrage n’est exigé, ou si vous ne voulez pas modifier la durée d’inactivité maximale.</span><span class="sxs-lookup"><span data-stu-id="5f382-127">The **-c** parameter is not required if no filtering is needed, or if you do not want to modify the maximum idle time.</span></span>

 <span data-ttu-id="5f382-128">Sans le paramètre **-c** , le fichier de configuration de prétraitement par défaut `DReplay.exe.preprocess.config`est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5f382-128">Without the **-c** parameter, the default preprocess configuration file, `DReplay.exe.preprocess.config`, is used.</span></span>

 <span data-ttu-id="5f382-129">**-f** *status_interval* spécifie la fréquence (en secondes) d’affichage des messages d’État.</span><span class="sxs-lookup"><span data-stu-id="5f382-129">**-f** *status_interval* Specifies the frequency (in seconds) at which to display status messages.</span></span>

 <span data-ttu-id="5f382-130">Si **-f** n’est pas spécifié, l’intervalle par défaut est de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="5f382-130">If **-f** is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="5f382-131">Exemples</span><span class="sxs-lookup"><span data-stu-id="5f382-131">Examples</span></span>
 <span data-ttu-id="5f382-132">Dans cet exemple, l'étape de prétraitement est initialisée avec tous les paramètres par défaut.</span><span class="sxs-lookup"><span data-stu-id="5f382-132">In this example, the preprocess stage is initiated with all of the default settings.</span></span> <span data-ttu-id="5f382-133">La valeur `localhost` indique que le service contrôleur s'exécute sur le même ordinateur que l'outil d'administration.</span><span class="sxs-lookup"><span data-stu-id="5f382-133">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span> <span data-ttu-id="5f382-134">Le paramètre *input_trace_file* spécifie l’emplacement des données de trace d’entrée ( `c:\mytrace.trc`).</span><span class="sxs-lookup"><span data-stu-id="5f382-134">The *input_trace_file* parameter specifies the location of the input trace data, `c:\mytrace.trc`.</span></span> <span data-ttu-id="5f382-135">Étant donné qu’aucun filtre de fichier de trace n’est impliqué, le paramètre **-c** doit être spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f382-135">Because there is no trace file filtering involved, the **-c** parameter does have to be specified.</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir
```

 <span data-ttu-id="5f382-136">Dans cet exemple, l'étape de prétraitement est initialisée et un fichier de configuration de prétraitement modifié est spécifié.</span><span class="sxs-lookup"><span data-stu-id="5f382-136">In this example, the preprocess stage is initiated and a modified preprocess configuration file is specified.</span></span> <span data-ttu-id="5f382-137">Contrairement à l’exemple précédent, le paramètre **-c** est utilisé pour pointer sur le fichier de configuration modifié, si vous l’avez stocké dans un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="5f382-137">Unlike the previous example, the **-c** parameter is used to point to the modified configuration file, if you have stored it in a different location.</span></span> <span data-ttu-id="5f382-138">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5f382-138">For example:</span></span>

```
dreplay preprocess -m localhost -i c:\mytrace.trc -d c:\WorkingDir -c c:\DReplay.exe.preprocess.config
```

 <span data-ttu-id="5f382-139">Dans le fichier de configuration de prétraitement modifié, une condition de filtre est ajoutée qui exclut les sessions système pendant la relecture distribuée.</span><span class="sxs-lookup"><span data-stu-id="5f382-139">In the modified preprocess configuration file, a filter condition is added that filters out system sessions during distributed replay.</span></span> <span data-ttu-id="5f382-140">Le filtre est ajouté en modifiant l'élément `<PreprocessModifiers>` dans le fichier de configuration de prétraitement, `DReplay.exe.preprocess.config`.</span><span class="sxs-lookup"><span data-stu-id="5f382-140">The filter is added by modifying the `<PreprocessModifiers>` element in the preprocess configuration file, `DReplay.exe.preprocess.config`.</span></span>

 <span data-ttu-id="5f382-141">L'exemple suivant montre le fichier de configuration modifié :</span><span class="sxs-lookup"><span data-stu-id="5f382-141">The following shows an example of the modified configuration file:</span></span>

```
<?xml version='1.0'?>
<Options>
    <PreprocessModifiers>
        <IncSystemSession>No</IncSystemSession>
        <MaxIdleTime>-1</MaxIdleTime>
    </PreprocessModifiers>
</Options>
```

## <a name="permissions"></a><span data-ttu-id="5f382-142">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5f382-142">Permissions</span></span>
 <span data-ttu-id="5f382-143">Vous devez exécuter l'outil d'administration en tant qu'utilisateur interactif, comme un utilisateur local ou un compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="5f382-143">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="5f382-144">Pour utiliser un compte d'utilisateur local, l'outil d'administration et le contrôleur doivent s'exécuter sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5f382-144">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="5f382-145">Pour plus d’informations, voir [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="5f382-145">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f382-146">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5f382-146">See Also</span></span>
 <span data-ttu-id="5f382-147">[Préparez les données de trace d’entrée](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [configurer Distributed Replay](configure-distributed-replay.md)</span><span class="sxs-lookup"><span data-stu-id="5f382-147">[Prepare the Input Trace Data](prepare-the-input-trace-data.md) [SQL Server Distributed Replay](sql-server-distributed-replay.md) [Configure Distributed Replay](configure-distributed-replay.md)</span></span>


