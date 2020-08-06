---
title: 'Tâche 17 : examen du projet de nettoyage DQS créé par le package SSIS | Microsoft Docs'
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fc6cc258-72f5-4593-8edb-9f5bc66de9db
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0876a0b727e810f8834fcf5445958bf9884a87f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694848"
---
# <a name="task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package"></a><span data-ttu-id="79c57-102">Tâche 17 : Examen du projet de nettoyage DQS créé par le package SSIS</span><span class="sxs-lookup"><span data-stu-id="79c57-102">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>
  <span data-ttu-id="79c57-103">Dans cette tâche, vous allez ouvrir le projet DQS créé par le package SSIS dans le client DQS, vous allez examiner les résultats du processus de nettoyage, et vous allez éventuellement effectuer un nettoyage interactif, puis exporter les résultats.</span><span class="sxs-lookup"><span data-stu-id="79c57-103">In this task, you open the DQS project created by the SSIS package in DQS Client, review the results from the cleansing process, and optionally perform interactive cleansing and export the results.</span></span>  
  
1.  <span data-ttu-id="79c57-104">Lancez **Data Quality client**.</span><span class="sxs-lookup"><span data-stu-id="79c57-104">Launch **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="79c57-105">Cliquez sur **analyse des activités** dans le volet **administration** .</span><span class="sxs-lookup"><span data-stu-id="79c57-105">Click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
3.  <span data-ttu-id="79c57-106">Triez la liste en fonction de l' **heure de début** de l’activité pour afficher le dernier enregistrement.</span><span class="sxs-lookup"><span data-stu-id="79c57-106">Sort the list based on **Activity Start Time** to see the latest record.</span></span>  
  
4.  <span data-ttu-id="79c57-107">Notez que vous voyez un nom du projet au format suivant : **CleanseAndCurate. Clean do Supplier Data. Guid**.</span><span class="sxs-lookup"><span data-stu-id="79c57-107">Notice that you see a name of the project in the following format: **CleanseAndCurate.Cleanse Supplier Data.GUID**.</span></span>  
  
     <span data-ttu-id="79c57-108">![Projet de nettoyage DQS créé par le package SSIS](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "Projet de nettoyage DQS créé par le package SSIS")</span><span class="sxs-lookup"><span data-stu-id="79c57-108">![DQS Cleansing Project Created by SSIS Package](../../2014/tutorials/media/et-reviewingdqscpcreatedbythessispackage.jpg "DQS Cleansing Project Created by SSIS Package")</span></span>  
  
5.  <span data-ttu-id="79c57-109">Notez que la valeur du champ **est active** est **active**.</span><span class="sxs-lookup"><span data-stu-id="79c57-109">Notice that the value in the **Is Active** field is **Active**.</span></span>  
  
6.  <span data-ttu-id="79c57-110">Cliquez sur l’onglet **Générateur de profils** dans le volet inférieur pour afficher les statistiques du profileur pour l’activité de nettoyage effectuée par le package SSIS.</span><span class="sxs-lookup"><span data-stu-id="79c57-110">Click **Profiler** tab in the bottom pane to see profiler statistics for the Cleansing activity that the SSIS package performed.</span></span>  
  
7.  <span data-ttu-id="79c57-111">Cliquez sur **Fermer** pour fermer l’écran **administration** .</span><span class="sxs-lookup"><span data-stu-id="79c57-111">Click **Close** to close the **Administration** screen.</span></span>  
  
8.  <span data-ttu-id="79c57-112">Dans la page principale du **client DQS**, cliquez sur **ouvrir le projet de qualité des données** dans le volet projets de qualité des **données** .</span><span class="sxs-lookup"><span data-stu-id="79c57-112">In the main page of **DQS Client**, click **Open Data Quality Project** in the **Data Quality Projects** pane.</span></span>  
  
9. <span data-ttu-id="79c57-113">Dans la liste des projets, sélectionnez le projet créé par le composant de nettoyage DQS SSIS.</span><span class="sxs-lookup"><span data-stu-id="79c57-113">In the list of projects, select the project created by SSIS DQS Cleansing component.</span></span> <span data-ttu-id="79c57-114">Le nom du projet doit être au format : **CleanseAndCurate. Clean do Supplier Data. Guid (en couleur rouge)**.</span><span class="sxs-lookup"><span data-stu-id="79c57-114">The name of the project should be in format:  **CleanseAndCurate.Cleanse Supplier Data.GUID (in red color)**.</span></span> <span data-ttu-id="79c57-115">Vous devrez peut-être trier la liste en fonction de la colonne **Date de création** et rechercher le dernier enregistrement.</span><span class="sxs-lookup"><span data-stu-id="79c57-115">You may need to sort the list based on **Date Created** column and look for the latest record.</span></span>  
  
10. <span data-ttu-id="79c57-116">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="79c57-116">Click **Next**.</span></span>  
  
11. <span data-ttu-id="79c57-117">La page **gérer et afficher les résultats** doit vous être familière du nettoyage interactif que vous avez fait précédemment dans ce didacticiel.</span><span class="sxs-lookup"><span data-stu-id="79c57-117">The **Manage and View Results** page should be familiar to you from the interactive cleansing you did earlier in this tutorial.</span></span>  
  
12. <span data-ttu-id="79c57-118">Examinez les résultats du nettoyage.</span><span class="sxs-lookup"><span data-stu-id="79c57-118">Review the cleansing results.</span></span> <span data-ttu-id="79c57-119">Vous pouvez également effectuer le nettoyage interactif et exporter les résultats vers un fichier Excel ou une base de données, dans la page suivante.</span><span class="sxs-lookup"><span data-stu-id="79c57-119">You can also perform interactive cleansing and export results to an Excel file or to a database in the next page.</span></span>  
  
13. <span data-ttu-id="79c57-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="79c57-120">Click **Next**.</span></span> <span data-ttu-id="79c57-121">Dans cette page **Exporter** , vous pouvez exporter les résultats vers un fichier Excel, un fichier CSV ou une base de données SQL.</span><span class="sxs-lookup"><span data-stu-id="79c57-121">In this **Export** page, you can export results to an excel file, CSV file, or to a SQL database.</span></span>  
  
14. <span data-ttu-id="79c57-122">Cliquez sur **Terminer** pour terminer l’activité.</span><span class="sxs-lookup"><span data-stu-id="79c57-122">Click **Finish** to finish the activity.</span></span>  
  
15. <span data-ttu-id="79c57-123">Dans la page principale du **client DQS**, cliquez sur **analyse des activités** dans le volet **administration** .</span><span class="sxs-lookup"><span data-stu-id="79c57-123">In the main page of **DQS Client**, click **Activity Monitoring** in the **Administration** pane.</span></span>  
  
16. <span data-ttu-id="79c57-124">Notez que la valeur du champ **IsActive** pour le projet est maintenant **terminée** .</span><span class="sxs-lookup"><span data-stu-id="79c57-124">Notice that the value of **IsActive** field for the project is **Ended** now.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="79c57-125">étape suivante</span><span class="sxs-lookup"><span data-stu-id="79c57-125">Next Step</span></span>  
 [<span data-ttu-id="79c57-126">Conclusion</span><span class="sxs-lookup"><span data-stu-id="79c57-126">Conclusion</span></span>](../../2014/tutorials/conclusion.md)  
  
  
