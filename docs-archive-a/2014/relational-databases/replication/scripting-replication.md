---
title: Création de scripts de réplication | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- scripts [SQL Server replication], replication objects
- merge replication scripting [SQL Server replication]
- replication [SQL Server], scripting
- snapshot replication [SQL Server], scripting
- scripts [SQL Server replication]
- transactional replication, scripting
ms.assetid: e50fac44-54c0-470c-a4ea-9c111fa4322b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 2e865e2664a399bca4738c1fc157bef176f35e96
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600764"
---
# <a name="scripting-replication"></a><span data-ttu-id="b2a2f-102">Création de scripts de réplication</span><span class="sxs-lookup"><span data-stu-id="b2a2f-102">Scripting Replication</span></span>
  <span data-ttu-id="b2a2f-103">Tous les composants de réplication dans une topologie doivent faire l'objet d'un script et s'intégrer dans un plan de récupération des données en cas de sinistre ; les scripts peuvent également être utilisés pour automatiser des tâches répétitives.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-103">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="b2a2f-104">Un script contient les procédures stockées système Transact-SQL nécessaires pour mettre en œuvre le ou les composants de réplication définis dans des scripts, tels qu'une publication ou un abonnement.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-104">A script contains the Transact-SQL system stored procedures necessary to implement the replication component(s) scripted, such as a publication or subscription.</span></span> <span data-ttu-id="b2a2f-105">Il est possible de créer des scripts à l’aide d’un Assistant (comme l’Assistant Nouvelle publication) ou dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] après avoir créé un composant.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-105">Scripts can be created in a wizard (such as the New Publication Wizard) or in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] after you create a component.</span></span> <span data-ttu-id="b2a2f-106">Vous pouvez afficher, modifier et exécuter le script à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou **sqlcmd**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-106">You can view, modify, and run the script using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or **sqlcmd**.</span></span> <span data-ttu-id="b2a2f-107">Les scripts peuvent être stockés avec les fichiers de sauvegarde dans le cas où la topologie de réplication doit être reconfigurée.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-107">Scripts can be stored with backup files to be used in case a replication topology must be reconfigured.</span></span>  
  
 <span data-ttu-id="b2a2f-108">Un nouveau script doit être généré pour un composant si des modifications sont apportées à ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-108">A component should be re-scripted if any property changes are made.</span></span> <span data-ttu-id="b2a2f-109">Si vous utilisez des procédures stockées personnalisées avec la réplication transactionnelle, une copie de chaque procédure doit être stockée avec les scripts ; la copie doit être mise à jour si la procédure change (les procédures sont généralement mises à jour suite à des modifications de schéma ou à des modifications des conditions requises par l'application).</span><span class="sxs-lookup"><span data-stu-id="b2a2f-109">If you use custom stored procedures with transactional replication, a copy of each procedure should be stored with the scripts; the copy should be updated if the procedure changes (procedures are typically updated due to schema changes or changing application requirements).</span></span> <span data-ttu-id="b2a2f-110">Pour plus d’informations sur les procédures personnalisées, consultez [Spécifier le mode de propagation des modifications des articles transactionnels](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="b2a2f-110">For more information about custom procedures, see [Specify How Changes Are Propagated for Transactional Articles](transactional/transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
 <span data-ttu-id="b2a2f-111">Pour les publications de fusion qui utilisent des filtres paramétrés, les scripts de publication contiennent l'appel de la procédure stockée pour créer des partitions de données.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-111">For merge publications that use parameterized filters, publication scripts contain the stored procedure calls to create data partitions.</span></span> <span data-ttu-id="b2a2f-112">Le script fournit une référence pour les partitions créées et un moyen permettant de recréer si nécessaire une ou plusieurs partitions.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-112">The script provides a reference for the partitions created and a way in which to re-create one or more partitions if necessary.</span></span>  
  
## <a name="example-of-automating-a-task-with-scripts"></a><span data-ttu-id="b2a2f-113">Exemple d'automatisation d'une tâche avec des scripts</span><span class="sxs-lookup"><span data-stu-id="b2a2f-113">Example of Automating a Task with Scripts</span></span>  
 <span data-ttu-id="b2a2f-114">Considérons [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], qui met en œuvre la réplication de fusion pour distribuer des données à sa force de vente distante.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-114">Consider [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)], which implements merge replication to distribute data to its remote sales force.</span></span> <span data-ttu-id="b2a2f-115">Un commercial télécharge toutes les données qui se rapportent aux clients de son territoire, à l'aide d'abonnements par extraction de données (pull).</span><span class="sxs-lookup"><span data-stu-id="b2a2f-115">A sales representative downloads all the data that pertains to the customers in her territory using pull subscriptions.</span></span> <span data-ttu-id="b2a2f-116">En mode déconnecté, les représentants commerciaux mettent à jour des données et entrent de nouveaux clients et de nouvelles commandes.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-116">When working offline, the sales representative updates data and enters new customers and orders.</span></span> <span data-ttu-id="b2a2f-117">[!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] employant plus de 50 représentants commerciaux sur des territoires différents, il serait donc très long de créer les différents abonnements sur chaque Abonné avec l'Assistant Nouvel abonnement.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-117">Because [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] has more than fifty sales representatives in different territories, it would be time-consuming to create the different subscriptions at each Subscriber with the New Subscription Wizard.</span></span> <span data-ttu-id="b2a2f-118">À la place, l'administrateur de réplication peut procéder selon les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b2a2f-118">Instead, the replication administrator can follow these steps:</span></span>  
  
1.  <span data-ttu-id="b2a2f-119">Configurez les publications de fusion nécessaires avec des partitions basées sur le représentant commercial ou son territoire.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-119">Set up the necessary merge publications with partitions based on the sales representative or their territory.</span></span>  
  
2.  <span data-ttu-id="b2a2f-120">Créez un abonnement par extraction de données (pull) pour un Abonné.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-120">Create a pull subscription for one Subscriber.</span></span>  
  
3.  <span data-ttu-id="b2a2f-121">Générez un script basé sur cet abonnement par extraction de données (pull).</span><span class="sxs-lookup"><span data-stu-id="b2a2f-121">Generate a script based on that pull subscription.</span></span>  
  
4.  <span data-ttu-id="b2a2f-122">Modifiez le script, en changeant des valeurs comme le nom de l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-122">Modify the script, changing such values as the name of the Subscriber.</span></span>  
  
5.  <span data-ttu-id="b2a2f-123">Exécutez le script sur plusieurs Abonnés pour générer les abonnements par extraction de données (pull) requis.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-123">Run the script at multiple Subscribers to generate the required pull subscriptions.</span></span>  
  
## <a name="script-replication-objects"></a><span data-ttu-id="b2a2f-124">Objets de réplication Script</span><span class="sxs-lookup"><span data-stu-id="b2a2f-124">Script Replication Objects</span></span>  
 <span data-ttu-id="b2a2f-125">Générez des scripts pour des objets de réplication à partir des Assistants de réplication ou du dossier **Réplication** de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2a2f-125">Script replication objects from the replication wizards or from the **Replication** folder in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="b2a2f-126">Si vous générez des scripts à partir des Assistants, vous pouvez opter pour la création d'objets et leur intégration dans un script ou pour la génération de scripts seuls.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-126">If you script from the wizards, you can choose to create objects and script them, or you can choose only to script them.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b2a2f-127">Tous les mots de passe sont définis dans le script avec la valeur NULL.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-127">All passwords are scripted as NULL.</span></span> <span data-ttu-id="b2a2f-128">Lorsque c'est possible, demande aux utilisateurs de fournir les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-128">When possible, prompt users to enter security credentials at runtime.</span></span> <span data-ttu-id="b2a2f-129">Si vous stockez des informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher tout accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-129">If you store credentials in a script file, you must secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="b2a2f-130">Pour plus d'informations sur l'utilisation des Assistants de réplication, consultez :</span><span class="sxs-lookup"><span data-stu-id="b2a2f-130">For more information about using the replication wizards, see:</span></span>  
  
-   [<span data-ttu-id="b2a2f-131">Configurer la publication et la distribution</span><span class="sxs-lookup"><span data-stu-id="b2a2f-131">Configure Publishing and Distribution</span></span>](configure-publishing-and-distribution.md)  
  
-   [<span data-ttu-id="b2a2f-132">Créer une publication</span><span class="sxs-lookup"><span data-stu-id="b2a2f-132">Create a Publication</span></span>](publish/create-a-publication.md)  
  
-   [<span data-ttu-id="b2a2f-133">Créer un abonnement par émission de données</span><span class="sxs-lookup"><span data-stu-id="b2a2f-133">Create a Push Subscription</span></span>](create-a-push-subscription.md)  
  
-   [<span data-ttu-id="b2a2f-134">Créer un abonnement par extraction de données (pull)</span><span class="sxs-lookup"><span data-stu-id="b2a2f-134">Create a Pull Subscription</span></span>](create-a-pull-subscription.md)  
  
#### <a name="to-script-an-object-from-a-replication-wizard"></a><span data-ttu-id="b2a2f-135">Pour générer un script pour un objet à partir d'un Assistant de réplication</span><span class="sxs-lookup"><span data-stu-id="b2a2f-135">To script an object from a replication wizard</span></span>  
  
1.  <span data-ttu-id="b2a2f-136">Dans la page **Actions de l'Assistant** d'un Assistant, activez la case à cocher adaptée à l'Assistant :</span><span class="sxs-lookup"><span data-stu-id="b2a2f-136">On the **Wizard Actions** page of a wizard, select the check box appropriate for the wizard:</span></span>  
  
    -   <span data-ttu-id="b2a2f-137">**Générer un fichier de script comportant les étapes de création d'une publication**</span><span class="sxs-lookup"><span data-stu-id="b2a2f-137">**Generate a script file with steps to create a publication**</span></span>  
  
    -   <span data-ttu-id="b2a2f-138">**Générer un fichier de script comportant les étapes de création d'une ou de plusieurs publications**</span><span class="sxs-lookup"><span data-stu-id="b2a2f-138">**Generate a script file with steps to create the subscription(s)**</span></span>  
  
    -   <span data-ttu-id="b2a2f-139">**Générer un fichier de script comportant les étapes de configuration de la distribution**</span><span class="sxs-lookup"><span data-stu-id="b2a2f-139">**Generate a script file with steps to configure distribution**</span></span>  
  
2.  <span data-ttu-id="b2a2f-140">Spécifiez les options dans la page **Propriétés du fichier de script** .</span><span class="sxs-lookup"><span data-stu-id="b2a2f-140">Specify options on the **Script File Properties** page.</span></span>  
  
3.  <span data-ttu-id="b2a2f-141">Terminez l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-141">Complete the wizard.</span></span>  
  
#### <a name="to-script-an-object-from-management-studio"></a><span data-ttu-id="b2a2f-142">Pour générer un script pour un objet à partir de Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2a2f-142">To script an object from Management Studio</span></span>  
  
1.  <span data-ttu-id="b2a2f-143">Connectez-vous au serveur de distribution, au serveur de publication ou à l'Abonné dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-143">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b2a2f-144">Développez le dossier **Réplication** , puis le dossier **Publications locales** ou le dossier **Abonnements locaux** .</span><span class="sxs-lookup"><span data-stu-id="b2a2f-144">Expand the **Replication** folder, and then expand the **Local Publications** folder or the **Local Subscriptions** folder.</span></span>  
  
3.  <span data-ttu-id="b2a2f-145">Cliquez avec le bouton droit sur une publication ou un abonnement, puis cliquez sur **Générer des scripts**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-145">Right-click a publication or subscription, and then click **Generate Scripts**.</span></span>  
  
4.  <span data-ttu-id="b2a2f-146">Spécifiez les options dans la boîte de dialogue **Générer un script SQL - \<ReplicationObject>** .</span><span class="sxs-lookup"><span data-stu-id="b2a2f-146">Specify options in the **Generate SQL Script - \<ReplicationObject>** dialog box.</span></span>  
  
5.  <span data-ttu-id="b2a2f-147">Cliquez sur **Générer un script sur fichier**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-147">Click **Script to File**.</span></span>  
  
6.  <span data-ttu-id="b2a2f-148">Entrez un nom de fichier dans la boîte de dialogue **Emplacement du fichier de script** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-148">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="b2a2f-149">Un message d'état est affiché.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-149">A status message is displayed.</span></span>  
  
7.  <span data-ttu-id="b2a2f-150">Cliquez sur **OK**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-150">Click **OK**, and then click **Close**.</span></span>  
  
#### <a name="to-script-multiple-objects-from-management-studio"></a><span data-ttu-id="b2a2f-151">Pour générer un script pour plusieurs objets à partir de Management Studio</span><span class="sxs-lookup"><span data-stu-id="b2a2f-151">To script multiple objects from Management Studio</span></span>  
  
1.  <span data-ttu-id="b2a2f-152">Connectez-vous au serveur de distribution, au serveur de publication ou à l'Abonné dans [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], puis développez le nœud du serveur.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-152">Connect to the Distributor, Publisher, or Subscriber in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], and then expand the server node.</span></span>  
  
2.  <span data-ttu-id="b2a2f-153">Cliquez avec le bouton droit sur le dossier **Réplication** , puis cliquez sur **Générer des scripts**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-153">Right-click the **Replication** folder, and then click **Generate Scripts**.</span></span>  
  
3.  <span data-ttu-id="b2a2f-154">Spécifiez les options dans la boîte de dialogue **Générer un script SQL** .</span><span class="sxs-lookup"><span data-stu-id="b2a2f-154">Specify options in the **Generate SQL Script** dialog box.</span></span>  
  
4.  <span data-ttu-id="b2a2f-155">Cliquez sur **Générer un script sur fichier**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-155">Click **Script to File**.</span></span>  
  
5.  <span data-ttu-id="b2a2f-156">Entrez un nom de fichier dans la boîte de dialogue **Emplacement du fichier de script** , puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-156">Enter a file name in the **Script File Location** dialog box, and then click **Save**.</span></span> <span data-ttu-id="b2a2f-157">Un message d'état est affiché.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-157">A status message is displayed.</span></span>  
  
6.  <span data-ttu-id="b2a2f-158">Cliquez sur **OK** , puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="b2a2f-158">Click **OK, and then** click **Close**.</span></span>  
  
  
