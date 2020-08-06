---
title: 'Étape 2 : Ajout et configuration de la journalisation | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 56105f3f-e500-4669-8c8e-acf434527727
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0f2cdce6f34a19e22830d357d20f5d99cff8c14f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700013"
---
# <a name="step-2-adding-and-configuring-logging"></a><span data-ttu-id="81201-102">Étape 2 : Activation et configuration du mode d’écriture dans un journal</span><span class="sxs-lookup"><span data-stu-id="81201-102">Step 2: Adding and Configuring Logging</span></span>
  <span data-ttu-id="81201-103">Dans cette tâche, vous allez activer la journalisation pour le flux de données dans le package Lesson 3.dtsx.</span><span class="sxs-lookup"><span data-stu-id="81201-103">In this task, you will enable logging for the data flow in the Lesson 3.dtsx package.</span></span> <span data-ttu-id="81201-104">Vous allez ensuite configurer un module fournisseur d'informations pour les fichiers texte, pour enregistrer les événements PipelineExecutionPlan et PipelineExecuteTrees.</span><span class="sxs-lookup"><span data-stu-id="81201-104">Then, you will configure a Text File log provider to log the PipelineExecutionPlan and PipelineExecuteTrees events.</span></span> <span data-ttu-id="81201-105">Le module fournisseur d'informations pour les fichiers texte crée des journaux faciles à créer et à déplacer.</span><span class="sxs-lookup"><span data-stu-id="81201-105">The Text Files log provider creates logs that are easy to view and easily transportable.</span></span> <span data-ttu-id="81201-106">La simplicité de ces fichiers journaux les rend particulièrement utiles pendant la phase de test de base d'un package.</span><span class="sxs-lookup"><span data-stu-id="81201-106">The simplicity of these log files makes these files especially useful during the basic testing phase of a package.</span></span> <span data-ttu-id="81201-107">Vous pouvez également consulter les entrées du journal dans la fenêtre Journaux d'événements du Concepteur [!INCLUDE[ssIS](../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81201-107">You can also view the log entries in the Log Events window of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span>  
  
### <a name="to-add-logging-to-the-package"></a><span data-ttu-id="81201-108">Pour activer le mode d'écriture dans un journal pour le package</span><span class="sxs-lookup"><span data-stu-id="81201-108">To add logging to the package</span></span>  
  
1.  <span data-ttu-id="81201-109">Dans le menu **SSIS** , cliquez sur **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="81201-109">On the **SSIS** menu, click **Logging**.</span></span>  
  
2.  <span data-ttu-id="81201-110">Dans le volet **Conteneurs** de la boîte de dialogue **Configurer les journaux SSIS** , vérifiez si l’objet situé au niveau le plus élevé, et qui représente le package Lesson 3, est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="81201-110">In the **Configure SSIS Logs** dialog box, in the **Containers** pane, make sure that the topmost object, which represents the Lesson 3 package, is selected.</span></span>  
  
3.  <span data-ttu-id="81201-111">Sous l’onglet **Fournisseurs et journaux** , dans la zone **Type de fournisseur** , sélectionnez **Module fournisseur d’informations SSIS pour les fichiers texte**, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="81201-111">On the **Providers and Logs** tab, in the **Provider type** box, select **SSIS log provider for Text files**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="81201-112">Integration Services ajoute un nouveau module fournisseur d’informations de journalisation de fichier texte au package avec le nom par défaut module **fournisseur d’informations SSIS pour les fichiers texte**.</span><span class="sxs-lookup"><span data-stu-id="81201-112">Integration Services adds a new Text File log provider to the package with the default name **SSIS log provider for text files**.</span></span> <span data-ttu-id="81201-113">Vous pouvez maintenant configurer le nouveau module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="81201-113">You can now configure the new log provider.</span></span>  
  
4.  <span data-ttu-id="81201-114">Dans la colonne **nom** , tapez `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="81201-114">In the **Name** column, type `Lesson 3 Log File`.</span></span>  
  
5.  <span data-ttu-id="81201-115">Modifiez éventuellement les informations figurant dans **Description**.</span><span class="sxs-lookup"><span data-stu-id="81201-115">Optionally, modify the **Description**.</span></span>  
  
6.  <span data-ttu-id="81201-116">Dans la colonne **Configuration** , cliquez sur **\<New Connection>** pour spécifier la destination dans laquelle enregistrer les informations du journal.</span><span class="sxs-lookup"><span data-stu-id="81201-116">In the **Configuration** column, click **\<New Connection>** to specify the destination to which the log information is written.</span></span>  
  
     <span data-ttu-id="81201-117">Dans la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers** , pour **Type d’utilisation**, sélectionnez **Créer un fichier**, puis cliquez sur **Parcourir**.</span><span class="sxs-lookup"><span data-stu-id="81201-117">In the **File Connection Manager Editor** dialog box, for **Usage type**, select **Create file**, and then click **Browse**.</span></span> <span data-ttu-id="81201-118">Par défaut, la boîte de dialogue **Sélectionner un fichier** qui s’affiche présente le dossier du projet, mais il est possible d’enregistrer les informations de journal n’importe où ailleurs.</span><span class="sxs-lookup"><span data-stu-id="81201-118">By default, the **Select File** dialog box opens the project folder, but you can save log information to any location.</span></span>  
  
7.  <span data-ttu-id="81201-119">Dans la boîte de dialogue **Sélectionner le fichier** , dans la zone **nom de fichier** `TutorialLog.log` , tapez, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="81201-119">In the **Select File** dialog box, in the **File name** box type `TutorialLog.log`, and click **Open**.</span></span>  
  
8.  <span data-ttu-id="81201-120">Cliquez sur **OK** pour fermer la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers** .</span><span class="sxs-lookup"><span data-stu-id="81201-120">Click **OK** to close the **File Connection Manager Editor** dialog box.</span></span>  
  
9. <span data-ttu-id="81201-121">Dans le volet **Conteneurs** , développez tous les nœuds de la hiérarchie des conteneurs du package, puis décochez toutes les cases, notamment la case **Extract Sample Currency Data** .</span><span class="sxs-lookup"><span data-stu-id="81201-121">In the **Containers** pane, expand all nodes of the package container hierarchy, and then clear all check boxes, including the **Extract Sample Currency Data** check box.</span></span> <span data-ttu-id="81201-122">Maintenant, cochez la case **Extract Sample Currency Data** pour extraire uniquement les événements de ce nœud.</span><span class="sxs-lookup"><span data-stu-id="81201-122">Now select the check box for **Extract Sample Currency Data** to get only the events for this node.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="81201-123">Si la case à cocher **Extract Sample Currency Data** n’apparaît pas sélectionnée mais grisée, la tâche utilise les paramètres du journal du conteneur parent et vous ne pouvez pas activer les journaux d’événements propres à cette tâche.</span><span class="sxs-lookup"><span data-stu-id="81201-123">If the state of the **Extract Sample Currency Data** check box is dimmed instead of selected, the task uses the log settings of the parent container and you cannot enable the log events that are specific to the task.</span></span>  
  
10. <span data-ttu-id="81201-124">Dans le volet **Détails** , dans la colonne **Événements** , sélectionnez les événements **PipelineExecutionPlan** et **PipelineExecutionTrees** .</span><span class="sxs-lookup"><span data-stu-id="81201-124">On the **Details** tab, in the **Events** column, select the **PipelineExecutionPlan** and **PipelineExecutionTrees** events.</span></span>  
  
11. <span data-ttu-id="81201-125">Cliquez sur **Avancés** pour vérifier les informations détaillées que le module de fournisseur d’informations enregistrera dans le journal pour chaque événement.</span><span class="sxs-lookup"><span data-stu-id="81201-125">Click **Advanced** to review the details that the log provider will write to the log for each event.</span></span> <span data-ttu-id="81201-126">Par défaut, toutes les catégories d'informations sont automatiquement sélectionnées pour les événements que vous avez spécifiés.</span><span class="sxs-lookup"><span data-stu-id="81201-126">By default, all information categories are automatically selected for the events you specify.</span></span>  
  
12. <span data-ttu-id="81201-127">Cliquez sur **De base** pour masquer les catégories d’informations.</span><span class="sxs-lookup"><span data-stu-id="81201-127">Click **Basic** to hide the information categories.</span></span>  
  
13. <span data-ttu-id="81201-128">Sous l’onglet **fournisseur et journaux** , dans la colonne **nom** , sélectionnez `Lesson 3 Log File` .</span><span class="sxs-lookup"><span data-stu-id="81201-128">On the **Provider and Logs** tab, in the **Name** column, select `Lesson 3 Log File`.</span></span> <span data-ttu-id="81201-129">Une fois que vous avez créé un module fournisseur d'informations pour votre package, vous pouvez éventuellement le désélectionner temporairement pour désactiver la journalisation, sans avoir à supprimer puis à recréer un module fournisseur d'informations.</span><span class="sxs-lookup"><span data-stu-id="81201-129">Once you have created a log provider for your package, you can optionally deselect it to temporarily turn off logging, without having to delete and re-create a log provider.</span></span>  
  
14. <span data-ttu-id="81201-130">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="81201-130">Click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="81201-131">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="81201-131">Next Steps</span></span>  
 [<span data-ttu-id="81201-132">Étape 3 : Test du package du tutoriel de la leçon 3</span><span class="sxs-lookup"><span data-stu-id="81201-132">Step 3: Testing the Lesson 3 Tutorial Package</span></span>](../integration-services/lesson-3-3-testing-the-lesson-3-tutorial-package.md)  
  
  
