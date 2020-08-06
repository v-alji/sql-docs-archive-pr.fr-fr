---
title: 'Tâche 6 : importation de valeurs à partir du projet nettoyer la liste des fournisseurs | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fec0deef-a729-4ff1-b709-72d2b3f407ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b674cfb42ddf31c3b903a465d1be1b04e9a355ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601833"
---
# <a name="task-6-importing-values-from-the-cleanse-supplier-list-project"></a><span data-ttu-id="64d12-102">Tâche 6 : Importation de valeurs depuis le projet de nettoyage de la liste des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="64d12-102">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>
  <span data-ttu-id="64d12-103">Dans cette tâche, vous allez importer les connaissances de qualité des données collectées pendant le processus de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="64d12-103">In this task, you import the data quality knowledge gathered during the cleansing process.</span></span> <span data-ttu-id="64d12-104">Pour plus d’informations, consultez [importation de valeurs de projet de nettoyage dans un domaine](https://msdn.microsoft.com/library/hh479581.aspx) .</span><span class="sxs-lookup"><span data-stu-id="64d12-104">See [Importing Cleansing Project Values into a Domain](https://msdn.microsoft.com/library/hh479581.aspx) topic for more details.</span></span> <span data-ttu-id="64d12-105">Vous exportez également la base de connaissances dans un fichier DQS avant de publier la base de connaissances **fournisseurs** mise à jour.</span><span class="sxs-lookup"><span data-stu-id="64d12-105">You also export the knowledge base into a DQS file before publishing the updated **Suppliers** knowledge base.</span></span>  
  
1.  <span data-ttu-id="64d12-106">Dans la page principale du **client DQS**, cliquez sur la **flèche droite** en regard de **fournisseurs** sous **bases de connaissances récentes** , puis cliquez sur **gestion de domaine**.</span><span class="sxs-lookup"><span data-stu-id="64d12-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** under **Recent Knowledge Bases** and click **Domain Management**.</span></span>  
  
2.  <span data-ttu-id="64d12-107">Cliquez sur **adresse de messagerie du contact** dans la liste des domaines et basculez vers l’onglet valeurs du **domaine** dans le volet droit.</span><span class="sxs-lookup"><span data-stu-id="64d12-107">Click **Contact Email** in the list of domains, and switch to the **Domain Values** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="64d12-108">Cliquez sur la **flèche vers le bas** en regard de l’icône **importer des valeurs** dans la barre d’outils, puis cliquez sur Importer les **valeurs du projet**.</span><span class="sxs-lookup"><span data-stu-id="64d12-108">Click **down arrow** next to the **Import Values** icon on the toolbar and click **Import Project Values**.</span></span>  
  
     <span data-ttu-id="64d12-109">![Bouton à la barre d'outils Importer des valeurs de projet](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Bouton à la barre d'outils Importer des valeurs de projet")</span><span class="sxs-lookup"><span data-stu-id="64d12-109">![Import Project Values Toolbar Button](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Import Project Values Toolbar Button")</span></span>  
  
4.  <span data-ttu-id="64d12-110">Dans la boîte de dialogue **Importer les valeurs du projet** , sélectionnez le projet nettoyer la liste des **fournisseurs** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="64d12-110">In the **Import Project Values** dialog box, select the **Cleanse Supplier List** project, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="64d12-111">Notez que toutes les adresses électroniques sont importées avec les deux corrections effectuées lors du nettoyage interactif.</span><span class="sxs-lookup"><span data-stu-id="64d12-111">Notice that all the emails are imported along with the two corrections you did during interactive cleansing.</span></span> <span data-ttu-id="64d12-112">Faites défiler la liste pour afficher les deux corrections.</span><span class="sxs-lookup"><span data-stu-id="64d12-112">Scroll to see the two corrections.</span></span>  
  
    |<span data-ttu-id="64d12-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="64d12-113">Value</span></span>|<span data-ttu-id="64d12-114">Corriger vers</span><span class="sxs-lookup"><span data-stu-id="64d12-114">Correct To</span></span>|  
    |-----------|----------------|  
    |bobby0@adventure-work.com|bobby0@adventure-works.com|  
    |tad0@adventure-work.com|tad0@adventure-works.com|  
  
6.  <span data-ttu-id="64d12-115">Répétez l’étape précédente pour importer des valeurs de projet pour le domaine **Country** et Notez qu’une nouvelle entrée est ajoutée pour corriger l' **État des États-Unis** à **États-Unis** (avec').</span><span class="sxs-lookup"><span data-stu-id="64d12-115">Repeat the previous step of importing project values for the **Country** domain and notice that a new entry is added for correcting **United State** to **United States** (with 's').</span></span>  
  
    |<span data-ttu-id="64d12-116">Valeur</span><span class="sxs-lookup"><span data-stu-id="64d12-116">Value</span></span>|<span data-ttu-id="64d12-117">Corriger vers</span><span class="sxs-lookup"><span data-stu-id="64d12-117">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="64d12-118">United State</span><span class="sxs-lookup"><span data-stu-id="64d12-118">United State</span></span>|<span data-ttu-id="64d12-119">États-Unis</span><span class="sxs-lookup"><span data-stu-id="64d12-119">United States</span></span>|  
  
7.  <span data-ttu-id="64d12-120">Pour afficher les anciennes valeurs de domaine, désactivez la case à cocher **afficher uniquement les nouvelles** .</span><span class="sxs-lookup"><span data-stu-id="64d12-120">To see the old domain values, clear **Show Only New** checkbox.</span></span>  
  
8.  <span data-ttu-id="64d12-121">Répétez l’étape précédente pour importer des valeurs de projet pour le domaine **nom du fournisseur** .</span><span class="sxs-lookup"><span data-stu-id="64d12-121">Repeat the previous step of importing project values for the **Supplier Name** domain.</span></span> <span data-ttu-id="64d12-122">Par défaut, après l'importation, vous verrez seulement les nouvelles valeurs.</span><span class="sxs-lookup"><span data-stu-id="64d12-122">By default, after importing, you will only see the new values.</span></span> <span data-ttu-id="64d12-123">Pour afficher toutes les valeurs, désactivez la case à cocher **afficher uniquement les nouvelles** .</span><span class="sxs-lookup"><span data-stu-id="64d12-123">To see all the values, clear **Show Only New** check box.</span></span> <span data-ttu-id="64d12-124">Vous avez enrichi la base de connaissances **fournisseurs** avec ce que vous avez appris de l’activité de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="64d12-124">You have enriched the **Suppliers** knowledge base with what you learned from the cleansing activity.</span></span> <span data-ttu-id="64d12-125">Plus la base de connaissances sera consolidée, meilleurs seront les résultats du nettoyage.</span><span class="sxs-lookup"><span data-stu-id="64d12-125">The stronger the knowledge base is, the better the cleansing results are.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="64d12-126">Il n'est pas possible d'importer des valeurs pour un domaine composite.</span><span class="sxs-lookup"><span data-stu-id="64d12-126">It is not possible import values for a composite domain.</span></span>  
  
9. <span data-ttu-id="64d12-127">Cliquez sur Exporter l’icône de **base de connaissances** dans la barre d’outils, puis cliquez sur Exporter la base de **connaissances**.</span><span class="sxs-lookup"><span data-stu-id="64d12-127">Click **Export Knowledge Base** icon on the toolbar and then click **Export Knowledge Base**.</span></span>  
  
     <span data-ttu-id="64d12-128">![Menu Exporter la base de connaissances](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Menu Exporter la base de connaissances")</span><span class="sxs-lookup"><span data-stu-id="64d12-128">![Export Knowledge Base Menu](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Export Knowledge Base Menu")</span></span>  
  
10. <span data-ttu-id="64d12-129">Accédez au dossier du didacticiel, tapez **Suppliers. DQS** comme **nom de fichier**, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="64d12-129">Navigate to the Tutorial folder, type **Suppliers.dqs** for the **file name**, and click **Save**.</span></span> <span data-ttu-id="64d12-130">Vous pouvez utiliser ce fichier DQS pour créer une nouvelle base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="64d12-130">You can use this DQS file to create a new knowledge base based on it.</span></span>  
  
11. <span data-ttu-id="64d12-131">Cliquez sur **OK** pour fermer la boîte de message **Exporter la base de connaissances-fournisseurs** .</span><span class="sxs-lookup"><span data-stu-id="64d12-131">Click **OK** to close the **Export Knowledge Base - Suppliers** message box.</span></span>  
  
12. <span data-ttu-id="64d12-132">Cliquez sur **Terminer** pour terminer l’activité.</span><span class="sxs-lookup"><span data-stu-id="64d12-132">Click **Finish** to finish the activity.</span></span>  
  
13. <span data-ttu-id="64d12-133">Cliquez sur **Publier**.</span><span class="sxs-lookup"><span data-stu-id="64d12-133">Click **Publish**.</span></span>  
  
14. <span data-ttu-id="64d12-134">Cliquez sur **OK** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="64d12-134">Click **OK** on the message box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="64d12-135">étape suivante</span><span class="sxs-lookup"><span data-stu-id="64d12-135">Next Step</span></span>  
 [<span data-ttu-id="64d12-136">Leçon 3 : Faire correspondre les données pour supprimer les doublons de la liste des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="64d12-136">Lesson 3: Matching Data to Remove Duplicates from Supplier List</span></span>](../../2014/tutorials/lesson-3-matching-data-to-remove-duplicates-from-supplier-list.md)  
  
  
