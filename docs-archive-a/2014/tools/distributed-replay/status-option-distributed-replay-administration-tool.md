---
title: Option status (outil d’administration Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: ea89386e-1598-4412-8b37-680d14b2a5b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 6ce3d07bc357c5f3788fb6f995a43399021b3553
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695040"
---
# <a name="status-option-distributed-replay-administration-tool"></a><span data-ttu-id="a7a10-102">Option status (outil d'administration Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="a7a10-102">Status Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="a7a10-103">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] outil d’administration Distributed Replay, `DReplay.exe` , est un outil en ligne de commande que vous pouvez utiliser pour communiquer avec le contrôleur Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="a7a10-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="a7a10-104">Cette rubrique décrit l’option de ligne de commande **status** et la syntaxe correspondante.</span><span class="sxs-lookup"><span data-stu-id="a7a10-104">This topic describes the **status** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="a7a10-105">L'option **status** interroge le contrôleur et affiche l'état en cours.</span><span class="sxs-lookup"><span data-stu-id="a7a10-105">The **status** option queries the controller and displays the current status.</span></span>

 <span data-ttu-id="a7a10-106">![Icône de lien vers une rubrique](../../database-engine/media/topic-link.gif "Icône du lien de rubrique") Pour plus d’informations sur les conventions de syntaxe utilisées par l’outil d’administration, consultez [Conventions de la syntaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="a7a10-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="a7a10-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="a7a10-107">Syntax</span></span>

```

dreplay status [-mcontroller] [-fstatus_interval]
```

#### <a name="parameters"></a><span data-ttu-id="a7a10-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="a7a10-108">Parameters</span></span>
 <span data-ttu-id="a7a10-109">**-m** *contrôleur* spécifie le nom d’ordinateur du contrôleur.</span><span class="sxs-lookup"><span data-stu-id="a7a10-109">**-m** *controller* Specifies the computer name of the controller.</span></span> <span data-ttu-id="a7a10-110">Vous pouvez utiliser «`localhost`» ou «`.`» pour désigner l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="a7a10-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="a7a10-111">Si le paramètre **-m** n’est pas spécifié, l’ordinateur local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="a7a10-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="a7a10-112">**-f** *status_interval* spécifie la fréquence (en secondes) à laquelle afficher l’État.</span><span class="sxs-lookup"><span data-stu-id="a7a10-112">**-f** *status_interval* Specifies the frequency (in seconds) at which to display the status.</span></span>

 <span data-ttu-id="a7a10-113">Si le paramètre **-f** n’est pas spécifié, l’intervalle par défaut est de 30 secondes.</span><span class="sxs-lookup"><span data-stu-id="a7a10-113">If the **-f** parameter is not specified, the default interval is 30 seconds.</span></span>

## <a name="examples"></a><span data-ttu-id="a7a10-114">Exemples</span><span class="sxs-lookup"><span data-stu-id="a7a10-114">Examples</span></span>
 <span data-ttu-id="a7a10-115">Dans l'exemple suivant, l'état en cours est affiché toutes les 60 secondes.</span><span class="sxs-lookup"><span data-stu-id="a7a10-115">In the following example, the current status is displayed every 60 seconds.</span></span> <span data-ttu-id="a7a10-116">La valeur `localhost` indique que le service contrôleur s'exécute sur le même ordinateur que l'outil d'administration.</span><span class="sxs-lookup"><span data-stu-id="a7a10-116">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay status -m localhost -f 60
```

## <a name="permissions"></a><span data-ttu-id="a7a10-117">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a7a10-117">Permissions</span></span>
 <span data-ttu-id="a7a10-118">Vous devez exécuter l'outil d'administration en tant qu'utilisateur interactif, comme un utilisateur local ou un compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="a7a10-118">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="a7a10-119">Pour utiliser un compte d'utilisateur local, l'outil d'administration et le contrôleur doivent s'exécuter sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="a7a10-119">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="a7a10-120">Pour plus d’informations, voir [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="a7a10-120">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7a10-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7a10-121">See Also</span></span>
 <span data-ttu-id="a7a10-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [débogueur Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md)</span><span class="sxs-lookup"><span data-stu-id="a7a10-122">[SQL Server Distributed Replay](sql-server-distributed-replay.md) [Transact-SQL Debugger](../../relational-databases/scripting/transact-sql-debugger.md)</span></span>


