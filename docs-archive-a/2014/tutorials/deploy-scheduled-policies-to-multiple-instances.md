---
title: Déployer des stratégies planifiées sur plusieurs instances | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: f551b8e8-3668-4ed4-852f-bae826254f4f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 30faf94c2033be43ac035517e58d5a18c0c68ab8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696344"
---
# <a name="deploy-scheduled-policies-to-multiple-instances"></a><span data-ttu-id="28d53-102">Déployer des stratégies planifiées sur plusieurs instances</span><span class="sxs-lookup"><span data-stu-id="28d53-102">Deploy Scheduled Policies to Multiple Instances</span></span>
  <span data-ttu-id="28d53-103">En utilisant des serveurs inscrits, vous pouvez déployer des stratégies planifiées sur des serveurs gérés à partir d'un emplacement central.</span><span class="sxs-lookup"><span data-stu-id="28d53-103">By using Registered Servers, you can deploy scheduled policies to managed servers from a central location.</span></span> <span data-ttu-id="28d53-104">Vous pouvez déployer des stratégies planifiées à partir d'un groupe de serveurs locaux ou à partir d'un serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="28d53-104">You can deploy scheduled policies from either a local server group, or from a Central Management Server.</span></span>  
  
 <span data-ttu-id="28d53-105">Dans cette tâche, vous effectuerez les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="28d53-105">In this task, you will do the following:</span></span>  
  
1.  <span data-ttu-id="28d53-106">exporter vers un dossier les stratégies que vous avez planifiées au cours de la tâche précédente ;</span><span class="sxs-lookup"><span data-stu-id="28d53-106">Export the policies that you scheduled in the previous task to a folder.</span></span>  
  
2.  <span data-ttu-id="28d53-107">déployer les stratégies planifiées sur des instances cibles qui sont gérées via les serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="28d53-107">Deploy the scheduled policies to target instances that are managed through Registered Servers.</span></span>  
  
 <span data-ttu-id="28d53-108">Vous effectuerez ces tâches sur l'ordinateur sur lequel vous avez effectué la tâche précédente de cette leçon.</span><span class="sxs-lookup"><span data-stu-id="28d53-108">You will perform these tasks on the computer where you completed the previous tasks in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="28d53-109">Prérequis</span><span class="sxs-lookup"><span data-stu-id="28d53-109">Prerequisites</span></span>  
 <span data-ttu-id="28d53-110">Les conditions préalables de cette tâche sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="28d53-110">This task has the following prerequisites:</span></span>  
  
-   <span data-ttu-id="28d53-111">Vous devez avoir effectué les tâches précédentes de cette leçon.</span><span class="sxs-lookup"><span data-stu-id="28d53-111">You must have completed the previous tasks in this lesson.</span></span>  
  
-   <span data-ttu-id="28d53-112">Les instances sur lesquelles vous voulez déployer les stratégies planifiées doivent exécuter [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ou version ultérieure.</span><span class="sxs-lookup"><span data-stu-id="28d53-112">The instances where you want to deploy the scheduled policies must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="28d53-113">L'automation requiert que les stratégies soient stockées localement, ce qui n'est pas pris en charge sur les versions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28d53-113">Automation requires the policies to be stored locally, which is not supported on versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
-   <span data-ttu-id="28d53-114">Les serveurs sur lesquels vous souhaitez déployer les stratégies planifiées doivent être enregistrés dans les serveurs inscrits dans le nœud groupes de serveurs **locaux** ou **serveurs de gestion centralisée** .</span><span class="sxs-lookup"><span data-stu-id="28d53-114">The servers where you want to deploy the scheduled policies must be registered in Registered Servers in either the **Local Server Groups** or the **Central Management Servers** node.</span></span> <span data-ttu-id="28d53-115">Pour plus d'informations, voir les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="28d53-115">For more information, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="28d53-116">Créer ou modifier un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="28d53-116">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
    -   <span data-ttu-id="28d53-117">[Inscrire un serveur connecté &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="28d53-117">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
    -   [<span data-ttu-id="28d53-118">Créer un serveur d’administration centralisée et un groupe de serveurs &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="28d53-118">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-export-the-scheduled-policies-as-xml-files"></a><span data-ttu-id="28d53-119">Pour exporter les stratégies planifiées sous la forme de fichiers .xml</span><span class="sxs-lookup"><span data-stu-id="28d53-119">To export the scheduled policies as .xml files</span></span>  
  
1.  <span data-ttu-id="28d53-120">Sur le serveur où vous avez configuré les stratégies planifiées au cours de la tâche précédente, développez **gestion**, gestion de la **stratégie**, puis cliquez sur **stratégies**.</span><span class="sxs-lookup"><span data-stu-id="28d53-120">On the server where you configured scheduled policies in the previous task, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span>  
  
2.  <span data-ttu-id="28d53-121">Dans le menu **Affichage** , cliquez sur **Détails de l’Explorateur d’objets**.</span><span class="sxs-lookup"><span data-stu-id="28d53-121">On the **View** menu, click **Object Explorer Details**.</span></span>  
  
3.  <span data-ttu-id="28d53-122">Dans le volet Détails de l' **Explorateur d’objets** , sélectionnez toutes les stratégies des meilleures pratiques planifiées que vous souhaitez déployer sur d’autres serveurs via les serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="28d53-122">In the **Object Explorer Details** pane, select all the scheduled best practices policies that you want to deploy to other servers through Registered Servers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28d53-123">Vous pouvez cliquer sur l’en-tête **catégorie** pour trier les stratégies par catégorie.</span><span class="sxs-lookup"><span data-stu-id="28d53-123">You can click the **Category** heading to sort the policies by category.</span></span>  
  
4.  <span data-ttu-id="28d53-124">Cliquez avec le bouton droit sur la sélection, puis cliquez sur **Exporter la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="28d53-124">Right-click the selection, and then click **Export Policy**.</span></span>  
  
5.  <span data-ttu-id="28d53-125">Si vous avez sélectionné plusieurs stratégies à exporter, dans la boîte de dialogue **Rechercher un dossier** , sélectionnez un dossier de destination ou créez un nouveau dossier.</span><span class="sxs-lookup"><span data-stu-id="28d53-125">If you selected multiple policies to export, in the **Browse For Folder** dialog box, select a destination folder, or create a new folder.</span></span> <span data-ttu-id="28d53-126">Pour cette leçon, créez un nouveau dossier avec le chemin **c:\ Scheduled_BP_Policies**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="28d53-126">For this lesson, create a new folder with the path **C:\Scheduled_BP_Policies**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="28d53-127">Si vous avez sélectionné une seule stratégie à exporter, dans la boîte de dialogue **Exporter la stratégie** , créez un nouveau dossier avec le chemin **c:\ Scheduled_BP_Policies**, cliquez sur **ouvrir**, puis sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="28d53-127">If you only selected one policy to export, in the **Export Policy** dialog box, create a new folder with the path **C:\Scheduled_BP_Policies**, click **Open**, and then click **Save**.</span></span>  
  
     <span data-ttu-id="28d53-128">Les fichiers de stratégie .xml sont créés à l'emplacement du dossier.</span><span class="sxs-lookup"><span data-stu-id="28d53-128">The .xml policy files are created in the folder location.</span></span>  
  
### <a name="to-deploy-the-scheduled-policies-to-servers-that-are-managed-through-registered-servers"></a><span data-ttu-id="28d53-129">Pour déployer les stratégies planifiées sur des serveurs qui sont gérés via les serveurs inscrits</span><span class="sxs-lookup"><span data-stu-id="28d53-129">To deploy the scheduled policies to servers that are managed through Registered Servers</span></span>  
  
1.  <span data-ttu-id="28d53-130">Dans le menu **Affichage** , cliquez sur **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="28d53-130">On the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="28d53-131">Développez **moteur de base de données**, développez **groupes de serveurs locaux** ou **serveurs de gestion centralisée**, cliquez avec le bouton droit sur le nœud sur lequel vous souhaitez déployer les stratégies, puis cliquez sur **importer des stratégies**.</span><span class="sxs-lookup"><span data-stu-id="28d53-131">Expand **Database Engine**, expand either **Local Server Groups** or **Central Management Servers**, right-click the node that you want to deploy the policies to, and then click **Import Policies**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28d53-132">Si vous cliquez avec le bouton droit sur **groupes de serveurs locaux** ou sur le serveur de gestion centralisée, les stratégies sont déployées sur tous les serveurs gérés.</span><span class="sxs-lookup"><span data-stu-id="28d53-132">If you right-click **Local Server Groups** or the Central Management Server itself, the policies will be deployed to all managed servers.</span></span> <span data-ttu-id="28d53-133">Si vous cliquez avec le bouton droit sur un groupe de serveurs spécifique, les stratégies seront déployées uniquement sur les serveurs de ce groupe.</span><span class="sxs-lookup"><span data-stu-id="28d53-133">If you right-click a specific server group, the policies will only be deployed to servers in that group.</span></span> <span data-ttu-id="28d53-134">Si vous cliquez avec le bouton droit sur un serveur inscrit spécifique, les stratégies seront déployées uniquement sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="28d53-134">If you right-click a specific registered server, the policies will only be deployed to that server.</span></span>  
  
3.  <span data-ttu-id="28d53-135">En regard de **fichiers à importer**, cliquez sur le bouton de sélection (**...**).</span><span class="sxs-lookup"><span data-stu-id="28d53-135">Next to **Files to import**, click the ellipsis button (**...**).</span></span>  
  
4.  <span data-ttu-id="28d53-136">Dans la boîte de dialogue **Sélectionner une stratégie** , accédez à l’emplacement du dossier où vous avez enregistré les stratégies planifiées.</span><span class="sxs-lookup"><span data-stu-id="28d53-136">In the **Select Policy** dialog box, browse to the folder location where you saved the scheduled policies.</span></span> <span data-ttu-id="28d53-137">Pour cet exemple, accédez à l’emplacement **c:\ Scheduled_BP_Policies**.</span><span class="sxs-lookup"><span data-stu-id="28d53-137">For this example, browse to the location **C:\Scheduled_BP_Policies**.</span></span>  
  
5.  <span data-ttu-id="28d53-138">Sélectionnez les stratégies que vous souhaitez importer dans les instances cibles, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="28d53-138">Select the policies that you want to import to the target instances, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="28d53-139">Dans la boîte de dialogue **Importer** , dans la liste État de la **stratégie** , sélectionnez l’état de stratégie souhaité.</span><span class="sxs-lookup"><span data-stu-id="28d53-139">In the **Import** dialog box, in the **Policy state** list, select the desired policy state.</span></span> <span data-ttu-id="28d53-140">Vous pouvez choisir de conserver l'état de la stratégie, d'activer les stratégies ou de les désactiver lors de l'importation.</span><span class="sxs-lookup"><span data-stu-id="28d53-140">You can choose to preserve the policy state, enable, or disable the policies on import.</span></span> <span data-ttu-id="28d53-141">Sachez que les stratégies doivent être activées pour s'exécuter selon une planification.</span><span class="sxs-lookup"><span data-stu-id="28d53-141">Be aware that the policies must be enabled to run on a schedule.</span></span>  
  
7.  <span data-ttu-id="28d53-142">Cliquez sur **OK** pour importer les stratégies vers toutes les instances cibles.</span><span class="sxs-lookup"><span data-stu-id="28d53-142">Click **OK** to import the policies to all the target instances.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28d53-143">En cas d’erreur, la boîte de dialogue **Importer** ne disparaît pas.</span><span class="sxs-lookup"><span data-stu-id="28d53-143">If there are any errors, the **Import** dialog box does not disappear.</span></span> <span data-ttu-id="28d53-144">Cliquez sur la page **Journal** pour passer en revue les messages.</span><span class="sxs-lookup"><span data-stu-id="28d53-144">Click the **Log** page to review the messages.</span></span> <span data-ttu-id="28d53-145">Cliquez sur **Annuler** pour refermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="28d53-145">Click **Cancel** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="28d53-146">Pour afficher les stratégies à partir d’une instance cible, connectez-vous à l’instance, ouvrez l’Explorateur d’objets, développez **gestion**, puis développez **stratégies**.</span><span class="sxs-lookup"><span data-stu-id="28d53-146">To view the policies from a target instance, connect to the instance, open Object Explorer, expand **Management**, and then expand **Policies**.</span></span> <span data-ttu-id="28d53-147">Vous devez voir les stratégies importées dans le nœud **stratégies** .</span><span class="sxs-lookup"><span data-stu-id="28d53-147">You should see the imported policies in the **Policies** node.</span></span> <span data-ttu-id="28d53-148">Si vous double-cliquez sur chaque stratégie, vous pouvez afficher la planification ou modifier les paramètres.</span><span class="sxs-lookup"><span data-stu-id="28d53-148">If you double-click each policy, you can view the schedule, or change the settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="28d53-149">Pour afficher les résultats d'évaluation après l'exécution d'une stratégie planifiée, ouvrez le journal Historique de la stratégie sur l'instance cible.</span><span class="sxs-lookup"><span data-stu-id="28d53-149">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="28d53-150">Pour ouvrir le journal, cliquez avec le bouton droit sur **gestion des stratégies**, puis cliquez sur **afficher l’historique**.</span><span class="sxs-lookup"><span data-stu-id="28d53-150">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="28d53-151">Récapitulatif</span><span class="sxs-lookup"><span data-stu-id="28d53-151">Summary</span></span>  
 <span data-ttu-id="28d53-152">Ce didacticiel vous a montré comment effectuer des évaluations à la demande et des évaluations planifiées des stratégies des meilleures pratiques sur une ou plusieurs instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="28d53-152">This tutorial has shown you how to perform both on-demand and scheduled evaluations of the best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="28d53-153">Suivant</span><span class="sxs-lookup"><span data-stu-id="28d53-153">Next</span></span>  
 <span data-ttu-id="28d53-154">Ce didacticiel est terminé.</span><span class="sxs-lookup"><span data-stu-id="28d53-154">This tutorial is finished.</span></span> <span data-ttu-id="28d53-155">Pour revenir au début, consultez [Didacticiel : évaluation des meilleures pratiques à l’aide de la gestion basée sur des stratégies](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="28d53-155">To return to the start, see [Tutorial: Evaluating Best Practices by Using Policy-Based Management](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="28d53-156">Pour afficher la liste des [!INCLUDE[ssDE](../includes/ssde-md.md)] didacticiels, cliquez sur [moteur de base de données didacticiels](../relational-databases/database-engine-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="28d53-156">To see a list of [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorials, click [Database Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d53-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28d53-157">See Also</span></span>  
 [<span data-ttu-id="28d53-158">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="28d53-158">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
