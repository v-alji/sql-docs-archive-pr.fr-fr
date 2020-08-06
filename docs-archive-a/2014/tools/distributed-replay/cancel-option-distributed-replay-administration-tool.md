---
title: Option cancel (outil d’administration Distributed Replay) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
ms.assetid: fea376de-307a-4b45-b7e2-37df88f3681a
author: stevestein
ms.author: sstein
ms.openlocfilehash: d132fbf5ce541a2bdab82e44dc55e6fc92df536d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610912"
---
# <a name="cancel-option-distributed-replay-administration-tool"></a><span data-ttu-id="5df96-102">Option cancel (outil d'administration Distributed Replay)</span><span class="sxs-lookup"><span data-stu-id="5df96-102">Cancel Option (Distributed Replay Administration Tool)</span></span>
  <span data-ttu-id="5df96-103">L' [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] outil d’administration Distributed Replay, `DReplay.exe` , est un outil en ligne de commande que vous pouvez utiliser pour communiquer avec le contrôleur Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="5df96-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay administration tool, `DReplay.exe`, is a command-line tool that you can use to communicate with the distributed replay controller.</span></span> <span data-ttu-id="5df96-104">Cette rubrique décrit l’option de ligne de commande **cancel** et la syntaxe correspondante.</span><span class="sxs-lookup"><span data-stu-id="5df96-104">This topic describes the **cancel** command-line option and corresponding syntax.</span></span>

 <span data-ttu-id="5df96-105">L’option **cancel** annule l’opération en cours d’exécution sur le contrôleur.</span><span class="sxs-lookup"><span data-stu-id="5df96-105">The **cancel** option cancels the current operation that is running on the controller.</span></span>

 <span data-ttu-id="5df96-106">![Icône de lien vers une rubrique](../../database-engine/media/topic-link.gif "Icône du lien de rubrique") Pour plus d’informations sur les conventions de syntaxe utilisées par l’outil d’administration, consultez [Conventions de la syntaxe Transact-SQL &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="5df96-106">![Topic link icon](../../database-engine/media/topic-link.gif "Topic link icon") For more information about the syntax conventions that are used with the administration tool syntax, see [Transact-SQL Syntax Conventions &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/transact-sql-syntax-conventions-transact-sql).</span></span>

## <a name="syntax"></a><span data-ttu-id="5df96-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5df96-107">Syntax</span></span>

```

dreplay cancel [-mcontroller] [-q] 
```

#### <a name="parameters"></a><span data-ttu-id="5df96-108">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5df96-108">Parameters</span></span>
 <span data-ttu-id="5df96-109">**-m** *contrôleur* nom d’ordinateur du contrôleur.</span><span class="sxs-lookup"><span data-stu-id="5df96-109">**-m** *controller* The computer name of the controller.</span></span> <span data-ttu-id="5df96-110">Vous pouvez utiliser «`localhost`» ou «`.`» pour désigner l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="5df96-110">You can use "`localhost`" or "`.`" to refer to the local computer.</span></span>

 <span data-ttu-id="5df96-111">Si le paramètre **-m** n’est pas spécifié, l’ordinateur local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="5df96-111">If the **-m** parameter is not specified, the local computer is used.</span></span>

 <span data-ttu-id="5df96-112">**-q** Mode silencieux.</span><span class="sxs-lookup"><span data-stu-id="5df96-112">**-q** Quiet mode.</span></span> <span data-ttu-id="5df96-113">N'invite à aucune confirmation.</span><span class="sxs-lookup"><span data-stu-id="5df96-113">Does not prompt for confirmation.</span></span>

 <span data-ttu-id="5df96-114">Le paramètre **-q** est facultatif.</span><span class="sxs-lookup"><span data-stu-id="5df96-114">The **-q** parameter is optional.</span></span>

## <a name="examples"></a><span data-ttu-id="5df96-115">Exemples</span><span class="sxs-lookup"><span data-stu-id="5df96-115">Examples</span></span>
 <span data-ttu-id="5df96-116">Dans l'exemple suivant, une demande d'annulation est soumise en mode silencieux.</span><span class="sxs-lookup"><span data-stu-id="5df96-116">In the following example, a cancel request is submitted in quiet mode.</span></span> <span data-ttu-id="5df96-117">La valeur `localhost` indique que le service contrôleur s'exécute sur le même ordinateur que l'outil d'administration.</span><span class="sxs-lookup"><span data-stu-id="5df96-117">The value `localhost` indicates that the controller service is running on the same computer as the administration tool.</span></span>

```
dreplay cancel -m localhost -q
```

## <a name="permissions"></a><span data-ttu-id="5df96-118">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5df96-118">Permissions</span></span>
 <span data-ttu-id="5df96-119">Vous devez exécuter l'outil d'administration en tant qu'utilisateur interactif, comme un utilisateur local ou un compte d'utilisateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="5df96-119">You must run the administration tool as an interactive user, as either a local user or a domain user account.</span></span> <span data-ttu-id="5df96-120">Pour utiliser un compte d'utilisateur local, l'outil d'administration et le contrôleur doivent s'exécuter sur le même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5df96-120">To use a local user account, the administration tool and controller must be running on the same computer.</span></span>

 <span data-ttu-id="5df96-121">Pour plus d’informations, voir [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="5df96-121">For more information, see [Distributed Replay Security](distributed-replay-security.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5df96-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5df96-122">See Also</span></span>
 [<span data-ttu-id="5df96-123">SQL Server Distributed Replay</span><span class="sxs-lookup"><span data-stu-id="5df96-123">SQL Server Distributed Replay</span></span>](sql-server-distributed-replay.md)


