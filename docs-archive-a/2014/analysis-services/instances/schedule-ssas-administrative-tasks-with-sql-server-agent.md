---
title: Planifier des tâches d’administration SSAS avec SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2d1484b3-51d9-48a0-93d2-0c3e4ed22b87
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2c78fa5fcebc0589ba863163b93ad2d10731b75a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702060"
---
# <a name="schedule-ssas-administrative-tasks-with-sql-server-agent"></a><span data-ttu-id="e6ae1-102">Planifier des tâches administratives SSAS avec SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e6ae1-102">Schedule SSAS Administrative Tasks with SQL Server Agent</span></span>
  <span data-ttu-id="e6ae1-103">Le service SQL Server Agent vous permet de planifier des tâches administratives [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] à exécuter dans l’ordre et au moment que vous précisez.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-103">Using the SQL Server Agent service, you can schedule [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrative tasks to run in the order and times that you need.</span></span> <span data-ttu-id="e6ae1-104">Les tâches planifiées vous aident à automatiser les processus qui s’exécutent selon des cycles réguliers ou prévisibles.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-104">Scheduled tasks help you automate processes that run on regular or predictable cycles.</span></span> <span data-ttu-id="e6ae1-105">Vous pouvez planifier l'exécution de tâches administratives, telles que le traitement de cubes, durant les périodes de faible activité.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-105">You can schedule administrative tasks, such as cube processing, to run during times of slow business activity.</span></span> <span data-ttu-id="e6ae1-106">Vous pouvez également déterminer l'ordre dans lequel les tâches s'exécutent en créant des étapes de travail au sein d'un travail de l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-106">You can also determine the order in which tasks run by creating job steps within a SQL Server Agent job.</span></span> <span data-ttu-id="e6ae1-107">Par exemple, vous pouvez traiter un cube, puis effectuer une sauvegarde de ce cube.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-107">For example, you can process a cube and then perform a backup of the cube.</span></span>  
  
 <span data-ttu-id="e6ae1-108">Les étapes de travail vous permettent de contrôler le flux d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-108">Job steps give you control over flow of execution.</span></span> <span data-ttu-id="e6ae1-109">Si un travail échoue, vous pouvez configurer l'Agent SQL Server de sorte qu'il continue d'exécuter les tâches restantes ou qu'il arrête l'exécution.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-109">If one job fails, you can configure SQL Server Agent to continue to run the remaining tasks or to stop execution.</span></span> <span data-ttu-id="e6ae1-110">Vous pouvez également configurer SQL Server Agent de sorte qu'il envoie des notifications concernant le succès ou l'échec de l'exécution d'un travail.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-110">You can also configure SQL Server Agent to send notifications about the success or failure of job execution.</span></span>  
  
 <span data-ttu-id="e6ae1-111">Cette rubrique est une procédure pas à pas qui décrit deux méthodes d'utilisation de SQL Server Agent pour exécuter le script XMLA.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-111">This topic is a walkthrough that shows two ways of using SQL Server Agent to run XMLA script.</span></span> <span data-ttu-id="e6ae1-112">Le premier exemple montre comment planifier le traitement d'une dimension unique.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-112">The first example demonstrates how to schedule processing of a single dimension.</span></span> <span data-ttu-id="e6ae1-113">Le deuxième exemple montre comment combiner les tâches de traitement dans un seul script qui s'exécute sur une planification.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-113">Example two shows how to combine processing tasks into a single script that runs on a schedule.</span></span> <span data-ttu-id="e6ae1-114">Pour effectuer cette procédure pas à pas, vous devez satisfaire aux conditions suivantes.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-114">To complete this walkthrough, you will need to meet the following prerequisites.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e6ae1-115">Prérequis</span><span class="sxs-lookup"><span data-stu-id="e6ae1-115">Prerequisites</span></span>  
 <span data-ttu-id="e6ae1-116">Le service Agent SQL Server doit être installé.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-116">SQL Server Agent service must be installed.</span></span>  
  
 <span data-ttu-id="e6ae1-117">Par défaut, les travaux s'exécutent sous le compte de service.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-117">By default, jobs run under the service account.</span></span> <span data-ttu-id="e6ae1-118">Dans [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , le compte par défaut de SQL Server Agent est NT Service\SQLAgent $ \<instancename> .</span><span class="sxs-lookup"><span data-stu-id="e6ae1-118">In [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], the default account for SQL Server Agent is NT Service\SQLAgent$\<instancename>.</span></span> <span data-ttu-id="e6ae1-119">Pour effectuer une sauvegarde ou une tâche de traitement, ce compte doit être un administrateur système sur l'instance Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-119">To perform a backup or processing task, this account must be a system administrator on the Analysis Services instance.</span></span> <span data-ttu-id="e6ae1-120">Pour plus d’informations, consultez [accorder des autorisations d’administrateur de serveur &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae1-120">For more information, see [Grant Server Administrator Permissions &#40;Analysis Services&#41;](grant-server-admin-rights-to-an-analysis-services-instance.md).</span></span>  
  
 <span data-ttu-id="e6ae1-121">Vous devez également disposer d'une base de données de test.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-121">You should also have a test database to work with.</span></span> <span data-ttu-id="e6ae1-122">Vous pouvez déployer l'exemple de base de données multidimensionnelle AdventureWorks ou un projet du didacticiel MDX Analysis Services dans cette procédure pas à pas.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-122">You can deploy the AdventureWorks multidimensional sample database or a project from the Analysis Services multidimensional tutorial to use in this walkthrough.</span></span> <span data-ttu-id="e6ae1-123">Pour plus d’informations, consultez [installer des exemples de données et de projets pour le Analysis Services didacticiel sur la modélisation multidimensionnelle](../install-sample-data-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae1-123">For more information, see [Install Sample Data and Projects for the Analysis Services Multidimensional Modeling Tutorial](../install-sample-data-and-projects.md).</span></span>  
  
## <a name="example-1-processing-a-dimension-in-a-scheduled-task"></a><span data-ttu-id="e6ae1-124">Exemple 1 : traitement d'une dimension dans une tâche planifiée</span><span class="sxs-lookup"><span data-stu-id="e6ae1-124">Example 1: Processing a dimension in a scheduled task</span></span>  
 <span data-ttu-id="e6ae1-125">Cet exemple montre comment créer et planifier un travail qui traite une dimension.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-125">This example demonstrates how to create and schedule a job that processes a dimension.</span></span>  
  
 <span data-ttu-id="e6ae1-126">Une tâche planifiée [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] est un script XMLA imbriqué dans un travail de SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-126">An [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] scheduled task is an XMLA script that is embedded into a SQL Server Agent job.</span></span> <span data-ttu-id="e6ae1-127">Ce travail est planifié pour s'exécuter à une heure et une fréquence souhaitées.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-127">This job is scheduled to run at desired times and frequency.</span></span> <span data-ttu-id="e6ae1-128">SQL Server Agent faisant partie de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous travaillez avec le Moteur de base de données et avec [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour créer et planifier une tâche administrative.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-128">Because the SQL Server Agent is part of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you work with both the Database Engine and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to create and schedule an administrative task.</span></span>  
  
###  <a name="create-a-script-for-processing-a-dimension-in-a-sql-server-agent-job"></a><a name="bkmk_CreateScript"></a><span data-ttu-id="e6ae1-129">Créer un script pour traiter une dimension dans un travail de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e6ae1-129">Create a script for processing a dimension in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="e6ae1-130">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6ae1-130">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="e6ae1-131">Ouvrez un dossier de base de données et recherchez une dimension.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-131">Open a database folder and find a dimension.</span></span> <span data-ttu-id="e6ae1-132">Cliquez sur la dimension et sélectionnez **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-132">Right-click the dimension and select **Process**.</span></span>  
  
2.  <span data-ttu-id="e6ae1-133">Dans la boîte de dialogue **Traiter la dimension** , dans la colonne **Options de traitement** sous **Liste d'objets**, vérifiez que l'option pour cette colonne est **Traiter entièrement**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-133">In the **Process Dimension** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span> <span data-ttu-id="e6ae1-134">Si ce n’est pas le cas, sous **Options de traitement**, cliquez sur l’option, puis sélectionnez **Traiter entièrement** dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-134">If it is not, under **Process Options**, click the option, and then select **Process Full** from the drop-down list.</span></span>  
  
3.  <span data-ttu-id="e6ae1-135">Cliquez sur **Script**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-135">Click **Script**.</span></span>  
  
     <span data-ttu-id="e6ae1-136">Cette étape permet d'ouvrir une fenêtre **Requête Xml** qui contient le script XMLA qui traite la dimension.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-136">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="e6ae1-137">Dans la boîte de dialogue **Traiter la dimension** , cliquez sur **Annuler** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-137">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="e6ae1-138">Dans la fenêtre **Requête XMLA** , mettez en surbrillance le script XMLA, cliquez avec le bouton droit sur le script en surbrillance et sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-138">In the **XMLA Query** window, highlight the XMLA script, right-click the highlighted script, and select **Copy**.</span></span>  
  
     <span data-ttu-id="e6ae1-139">Cette étape copie le script XMLA dans le presse-papiers Windows.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-139">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="e6ae1-140">Vous pouvez laisser le script XMLA dans le presse-papiers ou le coller dans le Bloc-notes ou un éditeur de texte différent.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-140">You can leave the XMLA script in the Clipboard or paste it into Notepad or another text editor.</span></span> <span data-ttu-id="e6ae1-141">Voici un exemple de script XMLA.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-141">The following is an example of the XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Account</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
###  <a name="create-and-schedule-the-dimension-processing-job"></a><a name="bkmk_ProcessJob"></a><span data-ttu-id="e6ae1-142">Créer et planifier le travail de traitement de dimension</span><span class="sxs-lookup"><span data-stu-id="e6ae1-142">Create and schedule the dimension processing job</span></span>  
  
1.  <span data-ttu-id="e6ae1-143">Connectez-vous à une instance du moteur de base de données et ouvrez l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-143">Connect to an instance of the Database Engine and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="e6ae1-144">Développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-144">Expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="e6ae1-145">Cliquez avec le bouton droit sur **Travaux** et sélectionnez **Nouveau travail**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-145">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="e6ae1-146">Dans la boîte de dialogue **Nouveau travail** , tapez un nom pour le travail dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-146">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="e6ae1-147">Sous **Sélectionner une page**, sélectionnez **Étapes**puis cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-147">Under **Select a page**, select **Steps**, and then click **New**.</span></span>  
  
6.  <span data-ttu-id="e6ae1-148">Dans la boîte de dialogue **Nouvelle étape de travail** , tapez un nom pour l'étape dans **Nom de l'étape**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-148">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="e6ae1-149">Dans **serveur**, tapez **localhost** pour une instance par défaut [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] de **et \\ localhost** \<*instance name*> pour une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-149">In **Server**, type **localhost** for a default instance of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] and **localhost\\**\<*instance name*> for a named instance.</span></span>  
  
     <span data-ttu-id="e6ae1-150">Si vous allez exécuter le travail à partir d'un ordinateur distant, utilisez le nom du serveur et le nom de l'instance où le travail s'exécutera.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-150">If you will be running the job from a remote computer, use the server name and instance name where the job will run.</span></span> <span data-ttu-id="e6ae1-151">Utilisez le format \<*server name*> d’une instance par défaut et le \<*server name*> \\ < *nom d’instance*> pour une instance nommée.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-151">Use the format \<*server name*> for a default instance, and \<*server name*>\\<*instance name*> for a named instance.</span></span>  
  
8.  <span data-ttu-id="e6ae1-152">Dans **Type**, sélectionnez **Commande SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-152">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
9. <span data-ttu-id="e6ae1-153">Dans **Commande**, cliquez avec le bouton droit et sélectionnez **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-153">In **Command**, right-click and select **Paste**.</span></span> <span data-ttu-id="e6ae1-154">Le script XMLA que vous avez créé à l'étape précédente doit apparaître dans la fenêtre de commande.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-154">The XMLA script that you generated in the previous step should appear in the command window.</span></span>  
  
10. <span data-ttu-id="e6ae1-155">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-155">Click **OK**.</span></span>  
  
11. <span data-ttu-id="e6ae1-156">Sous **Sélectionner une page**, cliquez sur **Planifications**puis cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-156">Under **Select a page**, click **Schedules**, and then click **New**.</span></span>  
  
12. <span data-ttu-id="e6ae1-157">Dans la boîte de dialogue **Nouvelle planification du travail** , entrez un nom pour la planification dans **Nom**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-157">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e6ae1-158">Cette étape crée une planification pour dimanche à 0h00 du matin.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-158">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="e6ae1-159">L'étape suivante montre comment exécuter manuellement le travail.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-159">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="e6ae1-160">Vous pouvez également spécifier une planification qui exécute le travail pendant que vous le surveillez.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-160">You can also specify a schedule that executes the job when you are monitoring it.</span></span>  
  
13. <span data-ttu-id="e6ae1-161">Dans la boîte de dialogue **Nouveau travail** , cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-161">In the **New Job** dialog box, click **OK**.</span></span>  
  
14. <span data-ttu-id="e6ae1-162">Dans **l’Explorateur d’objets**, développez **Travaux**, cliquez avec le bouton droit sur le travail que vous avez créé, puis sélectionnez **Démarrer le travail à l’étape**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-162">In **Object Explorer**, expand **Jobs**, right-click the job you created, and then select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="e6ae1-163">Étant donné que le travail comporte une seule étape, il s'exécute immédiatement.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-163">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="e6ae1-164">Si le travail contient plusieurs étapes, vous pouvez sélectionner celle à laquelle il doit démarrer.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-164">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
15. <span data-ttu-id="e6ae1-165">Lorsque le travail est terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-165">When the job finishes, click **Close**.</span></span>  
  
## <a name="example-2-batch-processing-a-dimension-and-a-partition-in-a-scheduled-task"></a><span data-ttu-id="e6ae1-166">Exemple 2 : traitement par lots d'une dimension et d'une partition dans une tâche planifiée</span><span class="sxs-lookup"><span data-stu-id="e6ae1-166">Example 2: Batch processing a dimension and a partition in a scheduled task</span></span>  
 <span data-ttu-id="e6ae1-167">Les procédures de cet exemple montrent comment créer et planifier un travail qui traite par lots une dimension de base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] et en même temps traiter une partition de cube qui dépend de la dimension pour l'agrégation.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-167">The procedures in this example demonstrate how to create and schedule a job that batch processes an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database dimension, and at the same time to process a  cube partition that depends on the dimension for aggregation.</span></span> <span data-ttu-id="e6ae1-168">Pour plus d’informations sur le traitement par lots des objets [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], consultez [Traitement par lots &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e6ae1-168">For more information about batch processing of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] objects, see [Batch Processing &#40;Analysis Services&#41;](../multidimensional-models/batch-processing-analysis-services.md).</span></span>  
  
###  <a name="create-a-script-for-batch-processing-a-dimension-and-partition-in-a-sql-server-agent-job"></a><a name="bkmk_BatchProcess"></a><span data-ttu-id="e6ae1-169">Créer un script pour le traitement par lots d’une dimension et d’une partition dans un travail de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="e6ae1-169">Create a script for batch processing a dimension and partition in a SQL Server Agent job</span></span>  
  
1.  <span data-ttu-id="e6ae1-170">À l’aide de la même base de données, développez **Dimensions**, cliquez avec le bouton droit sur la dimension **Client** et sélectionnez **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-170">Using the same database, expand **Dimensions**, right-click the **Customer** dimension, and select **Process**.</span></span>  
  
2.  <span data-ttu-id="e6ae1-171">Dans la boîte de dialogue **Traiter la dimension** , dans la colonne **Options de traitement** sous **Liste d'objets**, vérifiez que l'option pour cette colonne est **Traiter entièrement**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-171">In the **Process Dimension** dialog box, in **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
3.  <span data-ttu-id="e6ae1-172">Cliquez sur **Script**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-172">Click **Script**.</span></span>  
  
     <span data-ttu-id="e6ae1-173">Cette étape permet d'ouvrir une fenêtre **Requête Xml** qui contient le script XMLA qui traite la dimension.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-173">This step opens an **XML Query** window that contains the XMLA script that processes the dimension.</span></span>  
  
4.  <span data-ttu-id="e6ae1-174">Dans la boîte de dialogue **Traiter la dimension** , cliquez sur **Annuler** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-174">In the **Process Dimension** dialog box, click **Cancel** to close the dialog box.</span></span>  
  
5.  <span data-ttu-id="e6ae1-175">Développez **Cubes**, **Adventure Works**, **Groupes de mesures**, **Internet Sales**, **Partitions**, cliquez avec le bouton droit sur la dernière partition dans la liste, puis sélectionnez **Traiter**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-175">Expand **Cubes**, expand **Adventure Works**, expand **Measure Groups**, expand **Internet Sales**, expand **Partitions**, right-click the last partition in the list, and then select **Process**.</span></span>  
  
6.  <span data-ttu-id="e6ae1-176">Dans la boîte de dialogue **Traiter la partition** , dans la colonne **Options de traitement** sous **Liste d'objets**, vérifiez que l'option pour cette colonne est **Traiter entièrement**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-176">In the **Process Partition** dialog box, in the **Process Options** column under **Object list**, verify that the option for this column is **Process Full**.</span></span>  
  
7.  <span data-ttu-id="e6ae1-177">Cliquez sur **Script**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-177">Click **Script**.</span></span>  
  
     <span data-ttu-id="e6ae1-178">Cette étape permet d'ouvrir une seconde fenêtre **Requête Xml** qui contient le script XMLA qui traite la partition.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-178">This step opens a second **XML Query** window that contains the XMLA script that processes the partition.</span></span>  
  
8.  <span data-ttu-id="e6ae1-179">Dans la boîte de dialogue **Traiter la partition** , cliquez sur **Annuler** pour fermer l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-179">In the **Process Partition** dialog box, click **Cancel** to close the editor.</span></span>  
  
     <span data-ttu-id="e6ae1-180">À ce stade, vous devez fusionner les deux scripts et vérifier que la dimension est traitée en premier.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-180">At this point you must merge the two scripts, and ensure that the dimension is processed first.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="e6ae1-181">Si la partition est traitée en premier, le traitement ultérieur de la dimension provoque le non traitement de la partition.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-181">If the partition is processed first, the subsequent dimension processing causes the partition to become unprocessed.</span></span> <span data-ttu-id="e6ae1-182">La partition nécessiterait alors un second traitement pour atteindre l'état traité.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-182">The partition would then require a second processing to reach a processed state.</span></span>  
  
9. <span data-ttu-id="e6ae1-183">Dans la fenêtre **Requête XMLA** qui contient le script XMLA qui traite la partition, mettez en surbrillance le code à l’intérieur des indicateurs `Batch` et `Parallel` , cliquez avec le bouton droit sur le script en surbrillance, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-183">In the **XMLA Query** window that contains the XMLA script that processes the partition, highlight the code inside the `Batch` and `Parallel` tags, right-click the highlighted script, and select **Copy**.</span></span>  
  
    ```  
    <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID> Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID> Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
    ```  
  
10. <span data-ttu-id="e6ae1-184">Ouvrez la fenêtre **Requête XMLA** qui contient le script XMLA qui traite la dimension.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-184">Open the **XMLA Query** window that contains the XMLA script that processes the dimension.</span></span> <span data-ttu-id="e6ae1-185">Cliquez avec le bouton droit dans le script à gauche de l’indicateur `</Process>` et sélectionnez **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-185">Right-click within the script to the left of the `</Process>` tag and select **Paste**.</span></span>  
  
     <span data-ttu-id="e6ae1-186">L'exemple suivant affiche le script XMLA modifié.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-186">The following example shows the revised XMLA script.</span></span>  
  
    ```  
    <Batch xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
     <Parallel>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <DimensionID>Dim Customer</DimensionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
      <Process xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
        <Object>  
          <DatabaseID>Adventure Works DW Multidimensional</DatabaseID>  
          <CubeID>Adventure Works</CubeID>  
          <MeasureGroupID>Fact Internet Sales 1</MeasureGroupID>  
          <PartitionID>Internet_Sales_2004</PartitionID>  
        </Object>  
        <Type>ProcessFull</Type>  
        <WriteBackTableCreation>UseExisting</WriteBackTableCreation>  
      </Process>  
     </Parallel>  
    </Batch>  
    ```  
  
11. <span data-ttu-id="e6ae1-187">Mettez en surbrillance le script XMLA modifié, cliquez avec le bouton droit sur le script en surbrillance, puis sélectionnez **Copier**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-187">Highlight the revised XMLA script, right-click the highlighted script, and select **Copy.**</span></span>  
  
12. <span data-ttu-id="e6ae1-188">Cette étape copie le script XMLA dans le presse-papiers Windows.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-188">This step copies the XMLA script to the Windows Clipboard.</span></span> <span data-ttu-id="e6ae1-189">Vous pouvez laisser le script XMLA dans le presse-papiers, l'enregistrer dans un fichier ou le coller dans le Bloc-notes ou un éditeur de texte différent.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-189">You can leave the XMLA script in the Clipboard, save it to a file, or paste it into Notepad or another text editor.</span></span>  
  
###  <a name="create-and-schedule-the-batch-processing-job"></a><a name="bkmk_Scheduling"></a><span data-ttu-id="e6ae1-190">Créer et planifier le travail de traitement par lots</span><span class="sxs-lookup"><span data-stu-id="e6ae1-190">Create and schedule the batch processing job</span></span>  
  
1.  <span data-ttu-id="e6ae1-191">Connectez-vous à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]et ouvrez l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-191">Connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and then open Object Explorer.</span></span>  
  
2.  <span data-ttu-id="e6ae1-192">Développez **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-192">Expand **SQL Server Agent**.</span></span> <span data-ttu-id="e6ae1-193">Démarrez le service, s'il n'est pas déjà en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-193">Start the service if is not running.</span></span>  
  
3.  <span data-ttu-id="e6ae1-194">Cliquez avec le bouton droit sur **Travaux** et sélectionnez **Nouveau travail**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-194">Right-click **Jobs** and select **New Job**.</span></span>  
  
4.  <span data-ttu-id="e6ae1-195">Dans la boîte de dialogue **Nouveau travail** , tapez un nom pour le travail dans le champ **Nom**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-195">In the **New Job** dialog box, enter a job name in **Name**.</span></span>  
  
5.  <span data-ttu-id="e6ae1-196">Dans **Étapes**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-196">In **Steps**, click **New**.</span></span>  
  
6.  <span data-ttu-id="e6ae1-197">Dans la boîte de dialogue **Nouvelle étape de travail** , tapez un nom pour l'étape dans **Nom de l'étape**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-197">In the **New Job Step** dialog box, enter a step name in **Step Name**.</span></span>  
  
7.  <span data-ttu-id="e6ae1-198">Dans **Type**, sélectionnez **Commande SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-198">In **Type**, select **SQL Server Analysis Services Command**.</span></span>  
  
8.  <span data-ttu-id="e6ae1-199">Dans **Exécuter en tant que**, sélectionnez le **Compte de service SQL Server Agent**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-199">In **Run as**, select the **SQL Server Agent Service Account**.</span></span> <span data-ttu-id="e6ae1-200">Comme l'indique la section Configuration requise, ce compte doit avoir des autorisations d'administrateur sur Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-200">Recall from the Prerequisites section that this account must have administrative permissions on Analysis Services.</span></span>  
  
9. <span data-ttu-id="e6ae1-201">Dans **Serveur**, spécifiez le nom du serveur de l'instance d'Analysis Service.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-201">In **Server**, specify the server name of the Analysis Services instance.</span></span>  
  
10. <span data-ttu-id="e6ae1-202">Dans **Commande**, cliquez avec le bouton droit et sélectionnez **Coller**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-202">In **Command**, right-click and select **Paste**.</span></span>  
  
11. <span data-ttu-id="e6ae1-203">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-203">Click **OK**.</span></span>  
  
12. <span data-ttu-id="e6ae1-204">Dans la page **Planifications** , cliquez sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-204">In the **Schedules** page, click **New**.</span></span>  
  
13. <span data-ttu-id="e6ae1-205">Dans la boîte de dialogue **Nouvelle planification du travail** , entrez un nom pour la planification dans **Nom**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-205">In the **New Job Schedule** dialog box, enter a schedule name in **Name**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="e6ae1-206">Cette étape crée une planification pour dimanche à 0h00 du matin.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-206">This step creates a schedule for Sunday at 12:00 AM.</span></span> <span data-ttu-id="e6ae1-207">L'étape suivante montre comment exécuter manuellement le travail.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-207">The next step shows you how to manually execute the job.</span></span> <span data-ttu-id="e6ae1-208">Vous pouvez également sélectionner une planification qui exécute le travail pendant que vous le surveillez.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-208">You can also select a schedule which will execute the job when you are monitoring it.</span></span>  
  
14. <span data-ttu-id="e6ae1-209">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-209">Click **OK** to close the dialog box.</span></span>  
  
15. <span data-ttu-id="e6ae1-210">Dans **l’Explorateur d’objets**, développez **Travaux**, cliquez avec le bouton droit sur le travail que vous avez créé, puis sélectionnez **Démarrer le travail à l’étape**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-210">In **Object Explorer**, expand **Jobs**, right-click the job you created, and select **Start Job at Step**.</span></span>  
  
     <span data-ttu-id="e6ae1-211">Étant donné que le travail comporte une seule étape, il s'exécute immédiatement.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-211">Because the job has only one step, the job executes immediately.</span></span> <span data-ttu-id="e6ae1-212">Si le travail contient plusieurs étapes, vous pouvez sélectionner celle à laquelle il doit démarrer.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-212">If the job contains more than one step, you can select the step at which the job should start.</span></span>  
  
16. <span data-ttu-id="e6ae1-213">Lorsque le travail est terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="e6ae1-213">When the job finishes, click **Close**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ae1-214">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6ae1-214">See Also</span></span>  
 <span data-ttu-id="e6ae1-215">[Options de traitement et paramètres &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e6ae1-215">[Processing Options and Settings &#40;Analysis Services&#41;](../multidimensional-models/processing-options-and-settings-analysis-services.md) </span></span>  
 <span data-ttu-id="e6ae1-216">[Tâches d'administration à l'aide de scripts dans Analysis Services]](../script-administrative-tasks-in-analysis-services.md)</span><span class="sxs-lookup"><span data-stu-id="e6ae1-216">[Script Administrative Tasks in Analysis Services](../script-administrative-tasks-in-analysis-services.md)</span></span>  
  
  
