---
title: Effectuer une évaluation à la demande à l’aide de l’Explorateur d’objets | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: ee6d3b79-18bc-49d3-8a1d-0c0905b990f0
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e32876978ac462af361986d84e11ef3dc0f278e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600407"
---
# <a name="perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="fb562-102">Effectuer une évaluation à la demande à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="fb562-102">Perform an On-Demand Evaluation by Using Object Explorer</span></span>
  <span data-ttu-id="fb562-103">Dans cette tâche, vous allez utiliser l’Explorateur d’objets pour effectuer une évaluation à la demande des stratégies des meilleures pratiques pour le [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] sur une seule instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb562-103">In this task, you will use Object Explorer to perform an on-demand evaluation of best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb562-104">Vous pouvez également évaluer des stratégies sur une instance unique via des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="fb562-104">You can also evaluate policies on a single instance through Registered Servers.</span></span> <span data-ttu-id="fb562-105">Pour plus d’informations, consultez [effectuer une évaluation à la demande à l’aide de serveurs inscrits](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="fb562-105">For more information, see [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fb562-106">Prérequis</span><span class="sxs-lookup"><span data-stu-id="fb562-106">Prerequisites</span></span>  
 <span data-ttu-id="fb562-107">Cette leçon est basée sur la version de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] de [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fb562-107">This lesson is based on the version of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fb562-108">Pour effectuer une évaluation à la demande des stratégies des meilleures pratiques sur des instances qui exécutent [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] , vous devez utiliser la procédure décrite dans la rubrique [effectuer une évaluation à la demande à l’aide de serveurs inscrits](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="fb562-108">To perform an on-demand evaluation of best practices policies against instances that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you must use the procedure in the topic [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
### <a name="to-perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="fb562-109">Pour effectuer une évaluation à la demande à l'aide de l'Explorateur d'objets</span><span class="sxs-lookup"><span data-stu-id="fb562-109">To perform an on-demand evaluation by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="fb562-110">Démarrez [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] , puis connectez-vous au [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fb562-110">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="fb562-111">Dans l’Explorateur d’objets, développez **gestion**, gestion de la **stratégie**, cliquez avec le bouton droit sur **stratégies**, puis cliquez sur **évaluer**.</span><span class="sxs-lookup"><span data-stu-id="fb562-111">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and then click **Evaluate**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb562-112">Par défaut, l'instance locale est utilisée comme source des stratégies.</span><span class="sxs-lookup"><span data-stu-id="fb562-112">By default, the local instance is used as the source of the policies.</span></span> <span data-ttu-id="fb562-113">Si vous avez précédemment importé des stratégies des meilleures pratiques, elles apparaîtront avec toutes les autres stratégies que vous avez créées.</span><span class="sxs-lookup"><span data-stu-id="fb562-113">If you have previously imported best practices policies, they will be listed, together with any other policies that you have created.</span></span> <span data-ttu-id="fb562-114">Vous pouvez sélectionner l’une des stratégies des meilleures pratiques importées, puis cliquer sur **évaluer**.</span><span class="sxs-lookup"><span data-stu-id="fb562-114">You can select any of the imported best practices policies, and then click **Evaluate**.</span></span> <span data-ttu-id="fb562-115">Si vous n'avez pas importé les stratégies des meilleures pratiques, continuez cette procédure.</span><span class="sxs-lookup"><span data-stu-id="fb562-115">If you have not imported the best practices policies, continue with this procedure.</span></span>  
  
3.  <span data-ttu-id="fb562-116">Dans la boîte de dialogue **évaluer les stratégies** , en regard de la zone **source** , cliquez sur le bouton de sélection (**...**).</span><span class="sxs-lookup"><span data-stu-id="fb562-116">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
4.  <span data-ttu-id="fb562-117">Dans la boîte de dialogue **Sélectionner une source** , vous pouvez sélectionner **fichiers** ou **serveur** comme source des fichiers de stratégie à évaluer.</span><span class="sxs-lookup"><span data-stu-id="fb562-117">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="fb562-118">Si vous cliquez sur **serveur**, vous pouvez effectuer une évaluation à la demande des stratégies des meilleures pratiques qui ont été précédemment importées dans la gestion basée sur des stratégies sur un serveur local ou distant.</span><span class="sxs-lookup"><span data-stu-id="fb562-118">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="fb562-119">Dans ce didacticiel, vous allez cliquer sur **fichiers**, puis sélectionner les fichiers de stratégie individuels que vous souhaitez évaluer.</span><span class="sxs-lookup"><span data-stu-id="fb562-119">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="fb562-120">Pour ce faire, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="fb562-120">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="fb562-121">Cliquez sur **fichiers**.</span><span class="sxs-lookup"><span data-stu-id="fb562-121">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="fb562-122">En regard de **fichiers**, cliquez sur le bouton de sélection (**...**).</span><span class="sxs-lookup"><span data-stu-id="fb562-122">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="fb562-123">Dans la boîte de dialogue **Sélectionner une stratégie** , accédez au dossier suivant, qui contient les stratégies des meilleures pratiques :</span><span class="sxs-lookup"><span data-stu-id="fb562-123">In the **Select Policy** dialog box, browse to the following folder, which contains the best practices policies:</span></span>  
  
         <span data-ttu-id="fb562-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="fb562-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="fb562-125">Le chemin d'accès du fichier varie, selon l'emplacement d'installation des fichiers programme [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], si vous exécutez un système d'exploitation 32 bits ou 64 bits, et selon l'identificateur de langue.</span><span class="sxs-lookup"><span data-stu-id="fb562-125">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
    4.  <span data-ttu-id="fb562-126">Sélectionnez un ou plusieurs fichiers de stratégie. XML à évaluer, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="fb562-126">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="fb562-127">La liste des fichiers sélectionnés s’affiche dans la zone **fichiers** .</span><span class="sxs-lookup"><span data-stu-id="fb562-127">The list of selected files appears in the **Files** box.</span></span>  
  
    5.  <span data-ttu-id="fb562-128">Dans la boîte de dialogue **Sélectionner une source** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb562-128">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="fb562-129">Si la boîte de dialogue **chargement des stratégies** s’affiche, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="fb562-129">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="fb562-130">Les stratégies que vous avez sélectionnées sont répertoriées dans la page sélection de la **stratégie** .</span><span class="sxs-lookup"><span data-stu-id="fb562-130">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="fb562-131">Gardez à l'esprit qu'une icône d'avertissement en regard d'une stratégie indique que la stratégie contient des scripts.</span><span class="sxs-lookup"><span data-stu-id="fb562-131">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
5.  <span data-ttu-id="fb562-132">Cliquez sur **évaluer** pour évaluer les stratégies.</span><span class="sxs-lookup"><span data-stu-id="fb562-132">Click **Evaluate** to evaluate the policies.</span></span>  
  
     <span data-ttu-id="fb562-133">Dans le tableau des **résultats** , les résultats de chaque stratégie sont répertoriés.</span><span class="sxs-lookup"><span data-stu-id="fb562-133">In the **Results** table, the results for each policy are listed.</span></span> <span data-ttu-id="fb562-134">Une icône rouge avec un x indique que la conformité aux stratégies a échoué.</span><span class="sxs-lookup"><span data-stu-id="fb562-134">A red "x" icon indicates that policy compliance failed.</span></span>  
  
6.  <span data-ttu-id="fb562-135">Pour certains échecs de stratégie, la Gestion basée sur des stratégies vous permet de mettre immédiatement en vigueur la conformité aux stratégies sur la cible.</span><span class="sxs-lookup"><span data-stu-id="fb562-135">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="fb562-136">Pour de tels échecs, une case à cocher s'affichera en regard de la stratégie qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="fb562-136">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="fb562-137">Si vous activez la case à cocher, le bouton **appliquer** devient disponible.</span><span class="sxs-lookup"><span data-stu-id="fb562-137">If you select the check box, the **Apply** button becomes available.</span></span> <span data-ttu-id="fb562-138">Lorsque vous cliquez sur **appliquer**, le paramètre non conforme est automatiquement mis à jour sur l’instance cible.</span><span class="sxs-lookup"><span data-stu-id="fb562-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instance.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="fb562-139">Assurez-vous de bien comprendre le paramètre de stratégie avant de mettre à jour automatiquement une instance cible.</span><span class="sxs-lookup"><span data-stu-id="fb562-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="fb562-140">Après avoir sélectionné une ou plusieurs cases à cocher, nous vous recommandons de cliquer sur **script**et de choisir un emplacement de sortie afin de pouvoir examiner le code sous-jacent [!INCLUDE[tsql](../includes/tsql-md.md)] avant d’appliquer les modifications.</span><span class="sxs-lookup"><span data-stu-id="fb562-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
7.  <span data-ttu-id="fb562-141">Pour afficher les résultats détaillés d’une stratégie, cliquez sur la stratégie dans le tableau des **résultats** .</span><span class="sxs-lookup"><span data-stu-id="fb562-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="fb562-142">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="fb562-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="fb562-143">Effectuer une évaluation à la demande à l'aide des serveurs inscrits</span><span class="sxs-lookup"><span data-stu-id="fb562-143">Perform an On-Demand Evaluation by Using Registered Servers</span></span>](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)  
  
  
