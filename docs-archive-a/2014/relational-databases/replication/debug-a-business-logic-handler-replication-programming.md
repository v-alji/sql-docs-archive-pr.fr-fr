---
title: Déboguer un gestionnaire de logique métier | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- merge replication business logic handlers [SQL Server replication]
- business logic handlers [SQL Server replication]
- BusinessLogicModule class
ms.assetid: edd0d17a-0e9c-4c28-8395-a7d47e8ce3d6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7b255407783b1e52a376e562ec910f8b123e42c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601390"
---
# <a name="debug-a-business-logic-handler-replication-programming"></a><span data-ttu-id="2b05c-102">Déboguer un gestionnaire de logique métier (programmation de la réplication)</span><span class="sxs-lookup"><span data-stu-id="2b05c-102">Debug a Business Logic Handler (Replication Programming)</span></span>
  <span data-ttu-id="2b05c-103">Utilisez un gestionnaire de logique métier pour appeler une logique métier personnalisée lorsqu'un abonnement de fusion est synchronisé.</span><span class="sxs-lookup"><span data-stu-id="2b05c-103">Use a business logic handler to invoke custom business logic when a merge subscription is synchronized.</span></span> <span data-ttu-id="2b05c-104">Pour plus d’informations, consultez [Exécuter la logique métier lors de la synchronisation de fusion](merge/execute-business-logic-during-merge-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="2b05c-104">For more information, see [Execute Business Logic During Merge Synchronization](merge/execute-business-logic-during-merge-synchronization.md).</span></span>  
  
 <span data-ttu-id="2b05c-105">Le réconciliateur de réplication de fusion (replrec.dll) appelle l'assembly de code managé qui contient la logique métier.</span><span class="sxs-lookup"><span data-stu-id="2b05c-105">The Merge Replication Reconciler (replrec.dll) calls the managed code assembly containing the business logic.</span></span> <span data-ttu-id="2b05c-106">Dans la plupart des cas, replrec.dll et la logique métier personnalisée sont exécutés sur l'ordinateur où s'exécute l'Agent de fusion (sur l'Abonné pour un abonnement par extraction ou sur le serveur de distribution pour un abonnement par émission de données).</span><span class="sxs-lookup"><span data-stu-id="2b05c-106">In most cases, replrec.dll and the custom business logic is executed on the computer where the Merge Agent runs (at the Subscriber for a pull subscription or at the Distributor for a push subscription).</span></span> <span data-ttu-id="2b05c-107">Dans le cas de la synchronisation Web ou dans le cas d'un Abonné [!INCLUDE[ssEW](../../includes/ssew-md.md)] , le réconciliateur et la logique métier personnalisée sont exécutés sur le serveur Web.</span><span class="sxs-lookup"><span data-stu-id="2b05c-107">In the case of Web synchronization, or in the case of a [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscriber, the reconciler and the custom business logic is executed on the Web server.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-local-computer"></a><span data-ttu-id="2b05c-108">Pour déboguer un gestionnaire de logique métier sur un ordinateur local</span><span class="sxs-lookup"><span data-stu-id="2b05c-108">To debug a business logic handler on a local computer</span></span>  
  
1.  <span data-ttu-id="2b05c-109">Configurez la publication et la distribution, créez une publication et créez un abonnement à la publication.</span><span class="sxs-lookup"><span data-stu-id="2b05c-109">Configure publishing and distribution, create a publication, and create a subscription to the publication.</span></span> <span data-ttu-id="2b05c-110">Pour plus d’informations, consultez [Configurer la publication et la distribution](configure-publishing-and-distribution.md) et [Créer une Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="2b05c-110">For more information, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [Create a Publication](publish/create-a-publication.md).</span></span>  
  
2.  <span data-ttu-id="2b05c-111">Créez et inscrivez un gestionnaire de logique métier.</span><span class="sxs-lookup"><span data-stu-id="2b05c-111">Create and register a business logic handler.</span></span> <span data-ttu-id="2b05c-112">Pour plus d’informations, voir [Implémenter un gestionnaire de logique métier pour un article de fusion](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="2b05c-112">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="2b05c-113">Créez un projet Replication Management Objects dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio qui démarre par programme l'Agent de fusion de façon synchrone.</span><span class="sxs-lookup"><span data-stu-id="2b05c-113">Create a Replication Management Objects (RMO) project in [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Studio that programmatically starts the Merge Agent synchronously.</span></span> <span data-ttu-id="2b05c-114">Pour plus d’informations, consultez [Synchroniser un abonnement par extraction (pull)](synchronize-a-pull-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="2b05c-114">For more information, see [Synchronize a Pull Subscription](synchronize-a-pull-subscription.md).</span></span>  
  
4.  <span data-ttu-id="2b05c-115">Définissez un point d'arrêt dans le code du gestionnaire de logique métier, soit dans la méthode en cours de débogage, soit dans le constructeur de classe.</span><span class="sxs-lookup"><span data-stu-id="2b05c-115">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="2b05c-116">Pour plus d'informations sur les méthodes qui peuvent être implémentées dans un gestionnaire de logique métier, consultez la rubrique sur les méthodes <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="2b05c-116">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
5.  <span data-ttu-id="2b05c-117">Construisez le gestionnaire de logique métier en mode débogage et déployez l'assembly et le fichier de symboles de débogage (.pdb) dans l'emplacement inscrit à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="2b05c-117">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b05c-118">Pour simplifier le débogage, créez une solution Visual Studio .NET unique qui contient à la fois le projet de gestionnaire de logique métier et le projet qui synchronise l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="2b05c-118">To simplify debugging, create a single Visual Studio .NET solution that contains both the business logic handler project and the project that synchronizes the subscription.</span></span> <span data-ttu-id="2b05c-119">Dans ce cas, définissez le projet de synchronisation comme projet de démarrage et configurez l'environnement de génération pour déployer l'assembly de logique métier dans l'emplacement inscrit à l'étape 1 au cours du débogage.</span><span class="sxs-lookup"><span data-stu-id="2b05c-119">In this case, set the synchronization project as the startup project, and configure the build environment to deploy the business logic assembly to the location registered in step 1 during debugging.</span></span>  
  
6.  <span data-ttu-id="2b05c-120">Exécutez des commandes d'insertion, de mise à jour ou de suppression sur la base de données d'abonnement ou de publication.</span><span class="sxs-lookup"><span data-stu-id="2b05c-120">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="2b05c-121">L'emplacement de commande et d'exécution dépend de la méthode faisant l'objet du débogage.</span><span class="sxs-lookup"><span data-stu-id="2b05c-121">The command and execution location depends on the method being debugged.</span></span>  
  
7.  <span data-ttu-id="2b05c-122">Démarrez le projet créé à l'étape 3 en mode débogage pour synchroniser l'abonnement.</span><span class="sxs-lookup"><span data-stu-id="2b05c-122">Start the project from step 3 in debug mode to synchronize the subscription.</span></span>  
  
8.  <span data-ttu-id="2b05c-123">En supposant qu'aucun autre point d'arrêt n'est défini et que les commandes correctes sont répliquées, l'exécution s'arrête lorsqu'elle atteint le point d'arrêt dans le gestionnaire de logique métier.</span><span class="sxs-lookup"><span data-stu-id="2b05c-123">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
### <a name="to-debug-a-business-logic-handler-on-a-web-server-using-web-synchronization-or-for-a-sql-server-compact-subscriber"></a><span data-ttu-id="2b05c-124">Pour déboguer un gestionnaire de logique métier sur un serveur Web à l'aide de la synchronisation Web ou pour un abonné SQL Server Compact</span><span class="sxs-lookup"><span data-stu-id="2b05c-124">To debug a business logic handler on a Web server using Web synchronization, or for a SQL Server Compact Subscriber</span></span>  
  
1.  <span data-ttu-id="2b05c-125">Configurez la publication et la distribution, créez une publication et créez un abonnement par extraction à la publication.</span><span class="sxs-lookup"><span data-stu-id="2b05c-125">Configure publishing and distribution, create a publication, and create a pull subscription to the publication.</span></span> <span data-ttu-id="2b05c-126">La publication doit prendre en charge la synchronisation Web ou les Abonnés [!INCLUDE[ssEW](../../includes/ssew-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2b05c-126">The publication must support Web synchronization or [!INCLUDE[ssEW](../../includes/ssew-md.md)] Subscribers.</span></span>  
  
2.  <span data-ttu-id="2b05c-127">Créez et inscrivez un gestionnaire de logique métier.</span><span class="sxs-lookup"><span data-stu-id="2b05c-127">Create and register a business logic handler.</span></span> <span data-ttu-id="2b05c-128">Pour plus d’informations, voir [Implémenter un gestionnaire de logique métier pour un article de fusion](implement-a-business-logic-handler-for-a-merge-article.md).</span><span class="sxs-lookup"><span data-stu-id="2b05c-128">For more information, see [Implement a Business Logic Handler for a Merge Article](implement-a-business-logic-handler-for-a-merge-article.md).</span></span>  
  
3.  <span data-ttu-id="2b05c-129">Définissez un point d'arrêt dans le code du gestionnaire de logique métier, soit dans la méthode en cours de débogage, soit dans le constructeur de classe.</span><span class="sxs-lookup"><span data-stu-id="2b05c-129">Set a breakpoint in the business logic handler code, either in the method being debugged or in the class constructor.</span></span> <span data-ttu-id="2b05c-130">Pour plus d'informations sur les méthodes qui peuvent être implémentées dans un gestionnaire de logique métier, consultez la rubrique sur les méthodes <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> .</span><span class="sxs-lookup"><span data-stu-id="2b05c-130">For more information about the methods that can be implemented in a business logic handler, see the <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> methods topic.</span></span>  
  
4.  <span data-ttu-id="2b05c-131">Construisez le gestionnaire de logique métier en mode débogage et déployez l'assembly et le fichier de symboles de débogage (.pdb) sur le serveur Web, dans l'emplacement inscrit à l'étape 1.</span><span class="sxs-lookup"><span data-stu-id="2b05c-131">Build the business logic handler in debug mode and deploy the assembly and debugging symbol file (.pdb) at the Web server in the location registered in step 1.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2b05c-132">Si la création du gestionnaire de logique métier échoue car l'assembly est en cours d'utilisation, tapez la commande `iisreset` sur le serveur Web à l'invite de commandes pour réinitialiser le serveur Web.</span><span class="sxs-lookup"><span data-stu-id="2b05c-132">If the business logic handler fails to build because the assembly is in use, type the command `iisreset` on the Web server at the command prompt to reset the Web server.</span></span>  
  
5.  <span data-ttu-id="2b05c-133">Synchronisez l'abonnement avec la synchronisation Web activée.</span><span class="sxs-lookup"><span data-stu-id="2b05c-133">Synchronize the subscription with Web synchronization enabled.</span></span> <span data-ttu-id="2b05c-134">Pendant la synchronisation, le serveur Web charge l'assembly inscrit.</span><span class="sxs-lookup"><span data-stu-id="2b05c-134">During synchronization, the Web server loads the registered assembly.</span></span>  
  
6.  <span data-ttu-id="2b05c-135">À l'aide du débogueur Visual Studio .NET, attachez à l'un des processus suivants sur le serveur Web :</span><span class="sxs-lookup"><span data-stu-id="2b05c-135">Using the Visual Studio .NET debugger, attach to the one of the following processes on the Web server:</span></span>  
  
    -   <span data-ttu-id="2b05c-136">w3wp.exe – Windows Server 2003.</span><span class="sxs-lookup"><span data-stu-id="2b05c-136">w3wp.exe - Windows Server 2003.</span></span>  
  
    -   <span data-ttu-id="2b05c-137">inetinfo.exe – Windows 2000 et Windows XP.</span><span class="sxs-lookup"><span data-stu-id="2b05c-137">inetinfo.exe - Windows 2000 and Windows XP.</span></span>  
  
7.  <span data-ttu-id="2b05c-138">Dans la fenêtre **Sortie** , examinez la sortie de débogage pour vérifier que les symboles pour l'assembly inscrit ont été chargés correctement.</span><span class="sxs-lookup"><span data-stu-id="2b05c-138">In the **Output** window, check the debug output to verify that the symbols for the registered assembly loaded properly.</span></span> <span data-ttu-id="2b05c-139">Si les symboles n'ont pas été chargés, assurez-vous que le fichier .pdb correct a été copié à l'étape 4 et répétez l'étape 5.</span><span class="sxs-lookup"><span data-stu-id="2b05c-139">If the symbols were not loaded, ensure that the correct .pdb file was copied in step 4, and repeat step 5.</span></span>  
  
8.  <span data-ttu-id="2b05c-140">Exécutez des commandes d'insertion, de mise à jour ou de suppression sur la base de données d'abonnement ou de publication.</span><span class="sxs-lookup"><span data-stu-id="2b05c-140">Execute insert, update, or delete commands against the subscription or publication database.</span></span> <span data-ttu-id="2b05c-141">L'emplacement de commande et d'exécution dépend de la méthode faisant l'objet du débogage.</span><span class="sxs-lookup"><span data-stu-id="2b05c-141">The command and execution location depends on the method being debugged.</span></span>  
  
9. <span data-ttu-id="2b05c-142">À l'aide du débogueur Visual Studio, attachez au processus w3wp.exe.</span><span class="sxs-lookup"><span data-stu-id="2b05c-142">Using the Visual Studio debugger, attach to the w3wp.exe process.</span></span>  
  
10. <span data-ttu-id="2b05c-143">Synchronisez de nouveau l'abonnement, à l'aide de la synchronisation Web.</span><span class="sxs-lookup"><span data-stu-id="2b05c-143">Synchronize the subscription again, using Web synchronization.</span></span>  
  
11. <span data-ttu-id="2b05c-144">En supposant qu'aucun autre point d'arrêt n'est défini et que les commandes correctes sont répliquées, l'exécution s'arrête lorsqu'elle atteint le point d'arrêt dans le gestionnaire de logique métier.</span><span class="sxs-lookup"><span data-stu-id="2b05c-144">Assuming that no other breakpoints are set and the proper commands are replicated, the execution stops when it reaches the breakpoint in the business logic handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b05c-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b05c-145">See Also</span></span>  
 [<span data-ttu-id="2b05c-146">Implémenter un gestionnaire de logique métier pour un article de fusion</span><span class="sxs-lookup"><span data-stu-id="2b05c-146">Implement a Business Logic Handler for a Merge Article</span></span>](implement-a-business-logic-handler-for-a-merge-article.md)  
  
  
