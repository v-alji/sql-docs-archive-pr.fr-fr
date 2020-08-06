---
title: Configurer un package pour utiliser des transactions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- transactions [Integration Services], configuring packages to use
ms.assetid: 8bf14957-27b4-456b-81d9-e1a0e0ca94b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f469c2439deb2d16ac9046a1628e82c34e39b31d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697080"
---
# <a name="configure-a-package-to-use-transactions"></a><span data-ttu-id="ef9fd-102">Configurer un package pour l'utilisation de transactions</span><span class="sxs-lookup"><span data-stu-id="ef9fd-102">Configure a Package to Use Transactions</span></span>
  <span data-ttu-id="ef9fd-103">Lorsque vous configurez un package pour l'utilisation de transactions, vous avez le choix entre deux options :</span><span class="sxs-lookup"><span data-stu-id="ef9fd-103">When you configure a package to use transactions, you have two options:</span></span>  
  
-   <span data-ttu-id="ef9fd-104">Avoir une transaction unique pour le package.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-104">Have a single transaction for the package.</span></span> <span data-ttu-id="ef9fd-105">Dans ce cas, le package *lance* lui-même cette transaction, alors que les tâches et les conteneurs individuels dans le package participent à cette transaction unique.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-105">In this case, it is the package itself that *initiates* this transaction, whereas individual tasks and containers in the package participate in this single transaction.</span></span>  
  
-   <span data-ttu-id="ef9fd-106">Avoir plusieurs transactions dans le package.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-106">Have multiple transactions in the package.</span></span> <span data-ttu-id="ef9fd-107">Dans ce cas, le package prend en charge des transactions, mais les tâches et les conteneurs individuels dans le package lancent en réalité les transactions.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-107">In this case, the package supports transactions, but individual tasks and containers in the package actually initiate the transactions.</span></span>  
  
 <span data-ttu-id="ef9fd-108">Les procédures ci-dessous montrent comment configurer ces deux options.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-108">The following procedures describe how to configure both options.</span></span>  
  
## <a name="configuring-a-single-transaction"></a><span data-ttu-id="ef9fd-109">Configuration d'une transaction unique</span><span class="sxs-lookup"><span data-stu-id="ef9fd-109">Configuring a Single Transaction</span></span>  
 <span data-ttu-id="ef9fd-110">Dans cette option, le package lui-même lance une transaction unique.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-110">In this option, the package itself initiates a single transaction.</span></span> <span data-ttu-id="ef9fd-111">Vous configurez le package pour lancer cette transaction en affectant à la propriété TransactionOption du package la valeur `Required` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-111">You configure the package to initiate this transaction by setting the TransactionOption property of the package to `Required`.</span></span>  
  
 <span data-ttu-id="ef9fd-112">Ensuite, vous inscrivez des tâches et des conteneurs spécifiques dans cette transaction unique.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-112">Next, you enlist specific tasks and containers in this single transaction.</span></span> <span data-ttu-id="ef9fd-113">Pour inscrire une tâche ou un conteneur dans une transaction, vous affectez à la propriété TransactionOption de cette tâche ou de ce conteneur la valeur `Supported` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-113">To enlist a task or container in a transaction, you set the TransactionOption property of that task or container to `Supported`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-a-single-transaction"></a><span data-ttu-id="ef9fd-114">Pour configurer un package de façon à utiliser une transaction unique</span><span class="sxs-lookup"><span data-stu-id="ef9fd-114">To configure a package to use a single transaction</span></span>  
  
1.  <span data-ttu-id="ef9fd-115">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package à configurer pour utiliser une transaction.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-115">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use a transaction.</span></span>  
  
2.  <span data-ttu-id="ef9fd-116">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-116">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ef9fd-117">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-117">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ef9fd-118">Cliquez avec le bouton droit n’importe où dans l’arrière-plan de la surface de dessin du flux de contrôle, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-118">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ef9fd-119">Dans la fenêtre **Propriétés** , affectez à la propriété TransactionOption la valeur `Required` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-119">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
6.  <span data-ttu-id="ef9fd-120">Sur la surface de dessin de l’onglet **Flux de contrôle** , cliquez avec le bouton droit sur la tâche ou le conteneur que vous souhaitez inscrire dans la transaction, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-120">On the design surface of the **ControlFlow** tab, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="ef9fd-121">Dans la fenêtre **Propriétés** , affectez à la propriété TransactionOption la valeur `Supported` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-121">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef9fd-122">Pour inscrire une connexion dans une transaction, inscrivez les tâches qui utilisent la connexion dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-122">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="ef9fd-123">Pour plus d’informations, consultez [Connexions Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="ef9fd-123">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
8.  <span data-ttu-id="ef9fd-124">Répétez les étapes 6 et 7 pour chaque tâche et conteneur que vous voulez inscrire dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-124">Repeat steps 6 and 7 for each task and container that you want to enroll in the transaction.</span></span>  
  
## <a name="configuring-multiple-transactions"></a><span data-ttu-id="ef9fd-125">Configuration de plusieurs transactions</span><span class="sxs-lookup"><span data-stu-id="ef9fd-125">Configuring Multiple Transactions</span></span>  
 <span data-ttu-id="ef9fd-126">Dans cette option, le package lui-même prend en charge les transactions mais ne démarre pas une transaction.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-126">In this option, the package itself supports transactions but does not start a transaction.</span></span> <span data-ttu-id="ef9fd-127">Vous configurez le package pour prendre en charge les transactions en affectant à la propriété TransactionOption du package la valeur `Supported` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-127">You configure the package to support transactions by setting the TransactionOption property of the package to `Supported`.</span></span>  
  
 <span data-ttu-id="ef9fd-128">Ensuite, vous configurez les tâches et les conteneurs de votre choix au sein du package pour lancer des transactions ou y participer.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-128">Next, you configure the desired tasks and containers inside the package to initiate or participate in transactions.</span></span> <span data-ttu-id="ef9fd-129">Pour configurer une tâche ou un conteneur pour lancer une transaction, vous affectez à la propriété TransactionOption de cette tâche ou de ce conteneur la valeur `Required` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-129">To configure a task or container to initiate a transaction, you set the TransactionOption property of that task or container to `Required`.</span></span>  
  
#### <a name="to-configure-a-package-to-use-multiple-transactions"></a><span data-ttu-id="ef9fd-130">Pour configurer un package de façon à utiliser plusieurs transactions</span><span class="sxs-lookup"><span data-stu-id="ef9fd-130">To configure a package to use multiple transactions</span></span>  
  
1.  <span data-ttu-id="ef9fd-131">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le package que vous voulez configurer de façon à utiliser des transactions.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-131">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure to use transaction.s</span></span>  
  
2.  <span data-ttu-id="ef9fd-132">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-132">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="ef9fd-133">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-133">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="ef9fd-134">Cliquez avec le bouton droit n’importe où dans l’arrière-plan de la surface de dessin du flux de contrôle, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-134">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="ef9fd-135">Dans la fenêtre **Propriétés** , affectez à la propriété TransactionOption la valeur `Supported` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-135">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef9fd-136">Le package prend en charge les transactions, mais les transactions sont démarrées par la tâche ou des conteneurs dans le package.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-136">The package supports transactions, but the transactions are started by task or containers in the package.</span></span>  
  
6.  <span data-ttu-id="ef9fd-137">Sur la surface de dessin de l’onglet **Flux de contrôle** , cliquez avec le bouton droit sur la tâche ou le conteneur du package pour lequel vous souhaitez commencer une transaction, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-137">On the design surface of the **ControlFlow** tab, right-click the task or the container in the package for which you want to start a transaction, and then click **Properties**.</span></span>  
  
7.  <span data-ttu-id="ef9fd-138">Dans la fenêtre **Propriétés** , affectez à la propriété TransactionOption la valeur `Required` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-138">In the **Properties** window, set the TransactionOption property to `Required`.</span></span>  
  
8.  <span data-ttu-id="ef9fd-139">Si une transaction est commencée par un conteneur, cliquez avec le bouton droit sur la tâche ou le conteneur que vous souhaitez inscrire dans la transaction, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-139">If a transaction is started by a container, right-click the task or the container that you want to enroll in the transaction, and then click **Properties**.</span></span>  
  
9. <span data-ttu-id="ef9fd-140">Dans la fenêtre **Propriétés** , affectez à la propriété TransactionOption la valeur `Supported` .</span><span class="sxs-lookup"><span data-stu-id="ef9fd-140">In the **Properties** window, set the TransactionOption property to `Supported`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef9fd-141">Pour inscrire une connexion dans une transaction, inscrivez les tâches qui utilisent la connexion dans la transaction.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-141">To enlist a connection in a transaction, enroll the tasks that use the connection in the transaction.</span></span> <span data-ttu-id="ef9fd-142">Pour plus d’informations, consultez [Connexions Integration Services &#40;SSIS&#41;](connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="ef9fd-142">For more information, see [Integration Services &#40;SSIS&#41; Connections](connection-manager/integration-services-ssis-connections.md).</span></span>  
  
10. <span data-ttu-id="ef9fd-143">Répétez les étapes 6 à 9 pour chaque tâche et conteneur qui démarre une transaction.</span><span class="sxs-lookup"><span data-stu-id="ef9fd-143">Repeat steps 6 through 9 for each task and container that starts a transaction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9fd-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef9fd-144">See Also</span></span>  
 [<span data-ttu-id="ef9fd-145">Transactions Integration Services</span><span class="sxs-lookup"><span data-stu-id="ef9fd-145">Integration Services Transactions</span></span>](integration-services-transactions.md)  
  
  
