---
title: Transactions héritées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], inherited
- child packages
- inherited transactions [Integration Services]
ms.assetid: 90db5564-d41e-4cfe-8c9e-4e68d41eff1c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ecb480420fe9f2492c29fad37ee3cc6e6501e3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605642"
---
# <a name="inherited-transactions"></a><span data-ttu-id="e3c02-102">Transactions héritées</span><span class="sxs-lookup"><span data-stu-id="e3c02-102">Inherited Transactions</span></span>
  <span data-ttu-id="e3c02-103">Un package peut en exécuter un autre à l'aide de la tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="e3c02-103">A package can run another package by using the Execute Package task.</span></span> <span data-ttu-id="e3c02-104">Le package enfant, qui est celui exécuté par la tâche d'exécution de package, peut créer sa propre transaction sur package, ou hériter de celle du package parent.</span><span class="sxs-lookup"><span data-stu-id="e3c02-104">The child package, which is the package run by the Execute Package task, may create its own package transaction, or it may inherit the parent package transaction.</span></span>  
  
 <span data-ttu-id="e3c02-105">Un package enfant hérite de la transaction sur package parent si les deux conditions suivantes sont réunies :</span><span class="sxs-lookup"><span data-stu-id="e3c02-105">A child package inherits the parent package transaction if both of the following are true:</span></span>  
  
-   <span data-ttu-id="e3c02-106">Le package est appelé par une tâche d'exécution de package.</span><span class="sxs-lookup"><span data-stu-id="e3c02-106">The package is invoked by an Execute Package task.</span></span>  
  
-   <span data-ttu-id="e3c02-107">La tâche d'exécution de package qui a appelé le package a également joint la transaction sur package parent.</span><span class="sxs-lookup"><span data-stu-id="e3c02-107">The Execute Package task that invoked the package also joined the parent package transaction.</span></span>  
  
 <span data-ttu-id="e3c02-108">Les conteneurs et les tâches dans le package enfant ne peuvent pas être joints à la transaction de package parent, à moins que le package enfant lui-même soit joint à la transaction.</span><span class="sxs-lookup"><span data-stu-id="e3c02-108">Containers and tasks in the child package cannot join the parent package transaction unless the child package itself joins the transaction.</span></span>  
  
## <a name="illustration-of-package-transactions"></a><span data-ttu-id="e3c02-109">Illustration de transactions de packages</span><span class="sxs-lookup"><span data-stu-id="e3c02-109">Illustration of Package Transactions</span></span>  
 <span data-ttu-id="e3c02-110">Le diagramme suivant présente trois packages utilisant tous des transactions.</span><span class="sxs-lookup"><span data-stu-id="e3c02-110">In the following diagram, there are three packages that all use transactions.</span></span> <span data-ttu-id="e3c02-111">Chaque package comprend plusieurs tâches.</span><span class="sxs-lookup"><span data-stu-id="e3c02-111">Each package contains multiple tasks.</span></span> <span data-ttu-id="e3c02-112">Afin de mettre en évidence le comportement des transactions, seules les tâches d'exécution de package sont indiquées.</span><span class="sxs-lookup"><span data-stu-id="e3c02-112">To emphasize the behavior of the transactions, only the Execute Package tasks are shown.</span></span> <span data-ttu-id="e3c02-113">Le package A exécute les packages B et C. Le package B exécute à son tour les packages D et E, et le package C exécute le package F.</span><span class="sxs-lookup"><span data-stu-id="e3c02-113">Package A runs packages B and C. In turn, package B runs packages D and E, and package C runs package F.</span></span>  
  
 <span data-ttu-id="e3c02-114">Les packages et les tâches ont les attributs de transaction suivants :</span><span class="sxs-lookup"><span data-stu-id="e3c02-114">Packages and tasks have the following transaction attributes:</span></span>  
  
-   <span data-ttu-id="e3c02-115">**TransactionOption** a pour valeur **Required** sur les packages A et C.</span><span class="sxs-lookup"><span data-stu-id="e3c02-115">**TransactionOption** is set to **Required** on packages A and C</span></span>  
  
-   <span data-ttu-id="e3c02-116">**TransactionOption** a pour valeur **Supported** sur les packages B et D, et sur les tâches d’exécution des packages B, D et F.</span><span class="sxs-lookup"><span data-stu-id="e3c02-116">**TransactionOption** is set to **Supported** on packages B and D, and on the tasks Execute Package B, Execute Package D, and Execute Package F.</span></span>  
  
-   <span data-ttu-id="e3c02-117">**TransactionOption** a pour valeur **NotSupported** sur le package E, et sur les tâches d’exécution des packages C et E.</span><span class="sxs-lookup"><span data-stu-id="e3c02-117">**TransactionOption** is set to **NotSupported** on package E, and on the tasks Execute Package C and Execute Package E.</span></span>  
  
 <span data-ttu-id="e3c02-118">![Flux de transactions héritées](media/mw-dts-executepack.gif "Flux de transactions héritées")</span><span class="sxs-lookup"><span data-stu-id="e3c02-118">![Flow of inherited transactions](media/mw-dts-executepack.gif "Flow of inherited transactions")</span></span>  
  
 <span data-ttu-id="e3c02-119">Seuls les packages B, D et F peuvent hériter des transactions de leurs packages parents.</span><span class="sxs-lookup"><span data-stu-id="e3c02-119">Only packages B, D, and F can inherit transactions from their parent packages.</span></span>  
  
 <span data-ttu-id="e3c02-120">Les packages B et D héritent de la transaction démarrée par le package A.</span><span class="sxs-lookup"><span data-stu-id="e3c02-120">Packages B and D inherit the transaction that was started by package A.</span></span>  
  
 <span data-ttu-id="e3c02-121">Les package F hérite de la transaction démarrée par le package C.</span><span class="sxs-lookup"><span data-stu-id="e3c02-121">Package F inherits the transaction that was started by package C.</span></span>  
  
 <span data-ttu-id="e3c02-122">Les packages A et C contrôlent leurs propres transactions.</span><span class="sxs-lookup"><span data-stu-id="e3c02-122">Packages A and C control their own transactions.</span></span>  
  
 <span data-ttu-id="e3c02-123">Le package E n'utilise pas de transactions.</span><span class="sxs-lookup"><span data-stu-id="e3c02-123">Package E does not use transactions.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="e3c02-124">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="e3c02-124">Related Tasks</span></span>  
 [<span data-ttu-id="e3c02-125">Configurer un package pour l'utilisation de transactions</span><span class="sxs-lookup"><span data-stu-id="e3c02-125">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)  
  
  
