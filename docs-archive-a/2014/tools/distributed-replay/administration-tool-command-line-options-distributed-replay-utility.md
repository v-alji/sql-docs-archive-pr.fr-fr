---
title: Options de ligne de commande de l’outil d’administration (Distributed Replay Utility) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: c01b0ed3-67e4-4561-92d2-a8fbb086aca8
author: stevestein
ms.author: sstein
ms.openlocfilehash: 506be071f44937d82902585e5a0621212083dfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610913"
---
# <a name="administration-tool-command-line-options-distributed-replay-utility"></a><span data-ttu-id="25ddf-102">Options de ligne de commande de l'outil d'administration (Distributed Replay Utility)</span><span class="sxs-lookup"><span data-stu-id="25ddf-102">Administration Tool Command-line Options (Distributed Replay Utility)</span></span>
  <span data-ttu-id="25ddf-103">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] outil d’administration Distributed Replay, `DReplay.exe` , est un outil en ligne de commande que vous pouvez utiliser pour communiquer avec le contrôleur Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="25ddf-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="25ddf-104">Utilisez l’outil d’administration pour initier, surveiller et annuler des opérations sur le contrôleur.</span><span class="sxs-lookup"><span data-stu-id="25ddf-104">Use the administration tool to initiate, monitor, and cancel operations on the controller.</span></span>  
  
 <span data-ttu-id="25ddf-105">![Icône de lien vers une rubrique](../../database-engine/media/topic-link.gif "Icône du lien de rubrique") Pour plus d’informations sur les conventions de syntaxe utilisées par l’outil d’administration, consultez [Conventions de la syntaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="25ddf-105">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25ddf-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="25ddf-106">Syntax</span></span>  
  
```  
  
      dreplay {preprocess|replay|status|cancel} [options] [-?]}  
  
Usage:  
  
  dreplay preprocess [-mcontroller] -iinput_trace_file  
    -dcontroller_working_dir [-cconfig_file] [-fstatus_interval]  
  
  dreplay replay [-mcontroller] -dcontroller_working_dir [-o]  
    [-starget_server] -wclients [-cconfig_file]  
    [-fstatus_interval]  
  
  dreplay status [-mcontroller] [-fstatus_interval]  
  
  dreplay cancel [-mcontroller] [-q]   
```  
  
## <a name="remarks"></a><span data-ttu-id="25ddf-107">Notes</span><span class="sxs-lookup"><span data-stu-id="25ddf-107">Remarks</span></span>  
 <span data-ttu-id="25ddf-108">Vous pouvez émettre les options de ligne de commande suivantes avec `DReplay.exe` :</span><span class="sxs-lookup"><span data-stu-id="25ddf-108">You can issue the following command-line options with `DReplay.exe`:</span></span>  
  
 <span data-ttu-id="25ddf-109">**preprocess**</span><span class="sxs-lookup"><span data-stu-id="25ddf-109">**preprocess**</span></span>  
 <span data-ttu-id="25ddf-110">Initialise l'étape de prétraitement.</span><span class="sxs-lookup"><span data-stu-id="25ddf-110">Initiates the preprocess stage.</span></span> <span data-ttu-id="25ddf-111">Le contrôleur prépare les données de trace d'entrée, que vous avez capturées dans l'environnement de production, pour la relecture sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="25ddf-111">The controller prepares the input trace data, which you captured from the production environment, for replay against the target server.</span></span>  
  
 <span data-ttu-id="25ddf-112">**relecture**</span><span class="sxs-lookup"><span data-stu-id="25ddf-112">**replay**</span></span>  
 <span data-ttu-id="25ddf-113">Initialise l'étape de relecture d'événement.</span><span class="sxs-lookup"><span data-stu-id="25ddf-113">Initiates the event replay stage.</span></span> <span data-ttu-id="25ddf-114">Le contrôleur distribue des données de relecture aux clients spécifiés, lance la relecture distribuée et synchronise les clients.</span><span class="sxs-lookup"><span data-stu-id="25ddf-114">The controller dispatches replay data to the specified clients, launches the distributed replay, and synchronizes the clients.</span></span> <span data-ttu-id="25ddf-115">Éventuellement, chaque client sélectionné enregistre l'activité de relecture et enregistre des fichiers de trace de résultats localement.</span><span class="sxs-lookup"><span data-stu-id="25ddf-115">Optionally, each client that was selected records the replay activity and saves result trace files locally.</span></span>  
  
 <span data-ttu-id="25ddf-116">**statut**</span><span class="sxs-lookup"><span data-stu-id="25ddf-116">**status**</span></span>  
 <span data-ttu-id="25ddf-117">Interroge le contrôleur et affiche l'état en cours.</span><span class="sxs-lookup"><span data-stu-id="25ddf-117">Queries the controller and displays the current status.</span></span>  
  
 <span data-ttu-id="25ddf-118">**cancel**</span><span class="sxs-lookup"><span data-stu-id="25ddf-118">**cancel**</span></span>  
 <span data-ttu-id="25ddf-119">Annule l'opération actuelle qui s'exécute sur le contrôleur.</span><span class="sxs-lookup"><span data-stu-id="25ddf-119">Cancels the current operation that is running on the controller.</span></span>  
  
 <span data-ttu-id="25ddf-120">Pour obtenir des informations détaillées sur la syntaxe contenant les arguments de commande et des exemples, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="25ddf-120">For detailed syntax information that includes the command arguments and examples, see the following topics:</span></span>  
  
-   [<span data-ttu-id="25ddf-121">Option preprocess &#40;outil d’administration Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="25ddf-121">Preprocess Option &#40;Distributed Replay Administration Tool&#41;</span></span>](preprocess-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="25ddf-122">Option replay &#40;outil d’administration Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="25ddf-122">Replay Option &#40;Distributed Replay Administration Tool&#41;</span></span>](replay-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="25ddf-123">Option status &#40;outil d’administration Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="25ddf-123">Status Option &#40;Distributed Replay Administration Tool&#41;</span></span>](status-option-distributed-replay-administration-tool.md)  
  
-   [<span data-ttu-id="25ddf-124">Option cancel &#40;outil d’administration Distributed Replay&#41;</span><span class="sxs-lookup"><span data-stu-id="25ddf-124">Cancel Option &#40;Distributed Replay Administration Tool&#41;</span></span>](cancel-option-distributed-replay-administration-tool.md)  
  
 <span data-ttu-id="25ddf-125">Les appels de procédure distante (RPC) sont rediffusés en tant que RPC et non comme événements de langage.</span><span class="sxs-lookup"><span data-stu-id="25ddf-125">RPCs are replayed as RPCs and not as language events.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="25ddf-126">Autorisations</span><span class="sxs-lookup"><span data-stu-id="25ddf-126">Permissions</span></span>  
 <span data-ttu-id="25ddf-127">Vous devez exécuter l'outil d'administration en tant qu'utilisateur interactif, comme un utilisateur local ou un compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="25ddf-127">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="25ddf-128">Pour utiliser un compte d'utilisateur local, l'outil d'administration et le contrôleur doivent s'exécuter sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="25ddf-128">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>  
  
 <span data-ttu-id="25ddf-129">Pour plus d’informations, voir [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="25ddf-129">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ddf-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="25ddf-130">See Also</span></span>  
 [<span data-ttu-id="25ddf-131">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="25ddf-131">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)  
  
  
