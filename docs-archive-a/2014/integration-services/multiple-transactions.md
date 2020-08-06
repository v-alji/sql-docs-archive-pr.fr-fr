---
title: Transactions multiples | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], multiple
- multiple transactions
ms.assetid: c3664a94-be89-40c0-a3a0-84b74a7fedbe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5ff909c92a23c965047edc0fcf278e17e4c76d94
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605547"
---
# <a name="multiple-transactions"></a><span data-ttu-id="9a68f-102">Transactions multiples</span><span class="sxs-lookup"><span data-stu-id="9a68f-102">Multiple Transactions</span></span>
  <span data-ttu-id="9a68f-103">Il est possible qu'un package inclue des transactions non liées entre elles dans un package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a68f-103">It is possible for a package to include unrelated transactions in an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package.</span></span> <span data-ttu-id="9a68f-104">Chaque fois qu'un conteneur, au milieu d'une hiérarchie de conteneurs imbriquée, ne prend pas en charge les transactions, les conteneurs au-dessus et au-dessous de lui dans la hiérarchie démarrent des transactions distinctes s'ils sont configurés pour prendre en charge les transactions.</span><span class="sxs-lookup"><span data-stu-id="9a68f-104">Any time a container in the middle of a nested container hierarchy does not support transactions, the containers above or below it in the hierarchy start separate transactions if they are configured to support transactions.</span></span> <span data-ttu-id="9a68f-105">Les transactions sont validées ou annulées dans l'ordre, de la tâche la plus imbriquée dans la hiérarchie de conteneurs jusqu'au package.</span><span class="sxs-lookup"><span data-stu-id="9a68f-105">The transactions commit or roll back in order from the innermost task in the nested container hierarchy to the package.</span></span> <span data-ttu-id="9a68f-106">Cependant, si une transaction interne est validée, elle n'est pas annulée si une transaction externe est abandonnée.</span><span class="sxs-lookup"><span data-stu-id="9a68f-106">However, after the inner transaction commits, it does not roll back if an outer transaction is aborted.</span></span>

## <a name="illustration-of-multiple-transactions"></a><span data-ttu-id="9a68f-107">Illustration de plusieurs transactions</span><span class="sxs-lookup"><span data-stu-id="9a68f-107">Illustration of Multiple Transactions</span></span>
 <span data-ttu-id="9a68f-108">Par exemple, un package comprend un conteneur de séquences qui contient deux conteneurs de boucles Foreach, et chaque conteneur comprend deux tâches d'exécution de requêtes SQL.</span><span class="sxs-lookup"><span data-stu-id="9a68f-108">For example, a package has a Sequence container that holds two Foreach Loop containers, and each container include two Execute SQL tasks.</span></span> <span data-ttu-id="9a68f-109">Le conteneur de séquences et les tâches d'exécution de requêtes SQL prennent en charge les transactions, contrairement aux conteneurs de boucles Foreach.</span><span class="sxs-lookup"><span data-stu-id="9a68f-109">The Sequence container supports transactions, the Foreach Loop containers do not, and the Execute SQL tasks do.</span></span> <span data-ttu-id="9a68f-110">Dans cet exemple, chaque tâche d'exécution de requêtes SQL démarre sa propre transaction et elle n'est pas annulée si la transaction de la tâche de séquence est abandonnée.</span><span class="sxs-lookup"><span data-stu-id="9a68f-110">In this example, each Execute SQL task would start its own transaction and would not roll back if the transaction on the Sequence task was aborted.</span></span>

 <span data-ttu-id="9a68f-111">Les propriétés TransactionOption du conteneur de séquences, du conteneur de boucle Foreach et des tâches d’exécution de requêtes SQL sont définies comme suit :</span><span class="sxs-lookup"><span data-stu-id="9a68f-111">The TransactionOption properties of the Sequence container, Foreach Loop container and the Execute SQL tasks are set as follows:</span></span>

-   <span data-ttu-id="9a68f-112">La propriété TransactionOption du conteneur de séquences a pour valeur **Required**.</span><span class="sxs-lookup"><span data-stu-id="9a68f-112">The TransactionOption property of the Sequence container is set to **Required**.</span></span>

-   <span data-ttu-id="9a68f-113">Les propriétés TransactionOption des conteneurs de boucles Foreach ont pour valeur **NotSupported**.</span><span class="sxs-lookup"><span data-stu-id="9a68f-113">The TransactionOption properties of the Foreach Loop containers are set to **NotSupported**.</span></span>

-   <span data-ttu-id="9a68f-114">Les propriétés TransactionOption des tâches d’exécution de requêtes SQL ont pour valeur **Required**.</span><span class="sxs-lookup"><span data-stu-id="9a68f-114">The TransactionOption properties of the Execute SQL tasks are set to **Required**.</span></span>

 <span data-ttu-id="9a68f-115">Le diagramme ci-dessous représente les cinq transactions non liées du package.</span><span class="sxs-lookup"><span data-stu-id="9a68f-115">The following diagram shows the five unrelated transactions in the package.</span></span> <span data-ttu-id="9a68f-116">Une transaction est démarrée par le conteneur de séquences et quatre transactions par les tâches d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="9a68f-116">One transaction is started by the Sequence container and four transactions are started by the Execute SQL tasks.</span></span>

 <span data-ttu-id="9a68f-117">![Implémentation de plusieurs transactions](media/mw-dts-trans2.gif "Implémentation de plusieurs transactions")</span><span class="sxs-lookup"><span data-stu-id="9a68f-117">![Implementation of multiple transactions](media/mw-dts-trans2.gif "Implementation of multiple transactions")</span></span>

## <a name="related-tasks"></a><span data-ttu-id="9a68f-118">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="9a68f-118">Related Tasks</span></span>
 [<span data-ttu-id="9a68f-119">Configurer un package pour l'utilisation de transactions</span><span class="sxs-lookup"><span data-stu-id="9a68f-119">Configure a Package to Use Transactions</span></span>](../relational-databases/native-client-ole-db-transactions/transactions.md)


