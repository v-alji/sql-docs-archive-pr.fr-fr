---
title: 'Tâche 16 : vérification à l’aide de la Data Manager maître | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 57ad9d3e-8f95-4df6-af01-c291ccf49164
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d1649582f97e9e08691726745e4ba14b2f8226bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700511"
---
# <a name="task-16-verifying-with-master-data-manager"></a><span data-ttu-id="23418-102">Tâche 16 : Vérification à l’aide de Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="23418-102">Task 16: Verifying with Master Data Manager</span></span>
  <span data-ttu-id="23418-103">Dans cette tâche, vous allez vérifier l'état du programme de traitement par lots soumis par le package SSIS et vérifiez que les données ont été téléchargées sur le serveur MDS à l'aide de Master Data Manager.</span><span class="sxs-lookup"><span data-stu-id="23418-103">In this task, you check the status of the batch job submitted by the SSIS package and verify that the data was uploaded to MDS server by using Master Data Manager.</span></span>  
  
1.  <span data-ttu-id="23418-104">Lancez le **Data Manager maître** ( `http://localhost/MDS` ).</span><span class="sxs-lookup"><span data-stu-id="23418-104">Launch **Master Data Manager** (`http://localhost/MDS`).</span></span> <span data-ttu-id="23418-105">S’il est déjà ouvert, cliquez sur **Microsoft SQL Server Master Data Services** en haut pour basculer vers la **page d’hébergement**.</span><span class="sxs-lookup"><span data-stu-id="23418-105">If it is already open, click **Microsoft SQL Server Master Data Services** at the top to switch to the **home page**.</span></span>  
  
2.  <span data-ttu-id="23418-106">Cliquez sur gestion de l' **intégration**.</span><span class="sxs-lookup"><span data-stu-id="23418-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="23418-107">Notez qu’il existe un lot avec nommé **EIMBatch** que vous avez envoyé dans la liste.</span><span class="sxs-lookup"><span data-stu-id="23418-107">Notice that there is a batch with named **EIMBatch** that you submitted in the list.</span></span> <span data-ttu-id="23418-108">Si vous ne voyez pas l’écran suivant, cliquez sur **importer des données** dans la barre de menus.</span><span class="sxs-lookup"><span data-stu-id="23418-108">Click **Import Data** on the menu bar if you do not see the following screen.</span></span>  
  
     <span data-ttu-id="23418-109">![Lot EIM](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "Lot EIM")</span><span class="sxs-lookup"><span data-stu-id="23418-109">![EIM Batch](../../2014/tutorials/media/et-verifyingwithmasterdatamanager.jpg "EIM Batch")</span></span>  
  
4.  <span data-ttu-id="23418-110">Revenez à la page d’hébergement en cliquant sur **SQL Server 2012 Master Data Services** en haut.</span><span class="sxs-lookup"><span data-stu-id="23418-110">Switch back to the home page by click **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
5.  <span data-ttu-id="23418-111">Assurez-vous que le modèle **fournisseurs** est sélectionné pour **modèle** et que **Version_1** est sélectionné pour **version**, puis cliquez sur **Explorateur**.</span><span class="sxs-lookup"><span data-stu-id="23418-111">Make sure that **Suppliers** model is selected for **Model** and **VERSION_1** is selected for **Version**, and click **Explorer**.</span></span>  
  
6.  <span data-ttu-id="23418-112">Vous pouvez voir le package de données SSIS importé dans MDS.</span><span class="sxs-lookup"><span data-stu-id="23418-112">You can see the data SSIS package imported into MDS.</span></span> <span data-ttu-id="23418-113">Les données doivent être nettoyées et ne pas avoir de valeurs de **code** en double (Remarque : la colonne **RéfFournisseur** dans Excel correspond à l’attribut **code** de l’entité fournisseur dans MDS).</span><span class="sxs-lookup"><span data-stu-id="23418-113">The data should be cleansed and have no duplicates **Code** values (Note: **SupplierID** column in Excel corresponds to **Code** attribute of Supplier entity in MDS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="23418-114">étape suivante</span><span class="sxs-lookup"><span data-stu-id="23418-114">Next Step</span></span>  
 [<span data-ttu-id="23418-115">Tâche 17 : Examen du projet de nettoyage DQS créé par le package SSIS</span><span class="sxs-lookup"><span data-stu-id="23418-115">Task 17: Reviewing DQS Cleansing Project Created by the SSIS package</span></span>](../../2014/tutorials/task-17-reviewing-dqs-cleansing-project-created-by-the-ssis-package.md)  
  
  
