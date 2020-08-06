---
title: 'Tâche 3 : création et exécution d’un projet de qualité des données pour la correspondance | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 6260e911-ea8b-4c69-a39d-d1bccd565a32
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 221d6d583c61ee035c20fcb63f0ed5278f2b8678
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601842"
---
# <a name="task-3-creating-and-running-a-data-quality-project-for-matching"></a><span data-ttu-id="955d8-102">Tâche 3 : Création et exécution d’un projet de qualité des données pour la mise en correspondance</span><span class="sxs-lookup"><span data-stu-id="955d8-102">Task 3: Creating and Running a Data Quality Project for Matching</span></span>
  <span data-ttu-id="955d8-103">Dans cette tâche, vous allez créer un projet de qualité des données pour l'activité de correspondance, puis exécuter le processus de mise en correspondance sur les données des fournisseurs nettoyées pour supprimer les doublons.</span><span class="sxs-lookup"><span data-stu-id="955d8-103">In this task, you create a Data Quality Project for the matching activity and run the matching process on cleansed supplier data to remove any duplicates in the data.</span></span>

1.  <span data-ttu-id="955d8-104">Sur la page principale du **client DQS**, cliquez sur **nouveau projet de qualité des données**.</span><span class="sxs-lookup"><span data-stu-id="955d8-104">On the main page of **DQS Client**, click **New Data Quality Project**.</span></span>

2.  <span data-ttu-id="955d8-105">Tapez **Supprimer les doublons de fournisseur** du **nom du projet**.</span><span class="sxs-lookup"><span data-stu-id="955d8-105">Type **Remove Supplier Duplicates** from the **Name of the project**.</span></span>

3.  <span data-ttu-id="955d8-106">Sélectionnez **fournisseurs** dans la liste des bases de connaissances du champ **utiliser la base de connaissances** .</span><span class="sxs-lookup"><span data-stu-id="955d8-106">Select **Suppliers** from the list of KBs for the **Use Knowledge Base** field.</span></span> <span data-ttu-id="955d8-107">Vous avez créé une stratégie de correspondance dans cette base de connaissances dans la leçon précédente.</span><span class="sxs-lookup"><span data-stu-id="955d8-107">You have created a matching policy in this knowledge base in the previous lesson.</span></span>

4.  <span data-ttu-id="955d8-108">Sélectionnez **correspondance** dans la **liste des activités** dans le volet inférieur droit.</span><span class="sxs-lookup"><span data-stu-id="955d8-108">Select **Matching** from the **list of activities** from the bottom-right pane.</span></span>

     <span data-ttu-id="955d8-109">![Nouveau projet de qualité des données - Correspondance sélectionnée](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "Nouveau projet de qualité des données - Correspondance sélectionnée")</span><span class="sxs-lookup"><span data-stu-id="955d8-109">![New Data Quality Project - Matching Selected](../../2014/tutorials/media/et-creatingandrunningadqpformatching.jpg "New Data Quality Project - Matching Selected")</span></span>

5.  <span data-ttu-id="955d8-110">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="955d8-110">Click **Next**.</span></span>

6.  <span data-ttu-id="955d8-111">Dans la page **Mapper** , sélectionnez **Fichier Excel** pour **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="955d8-111">In the **Map** page, select **Excel File** for **Data Source**.</span></span>

7.  <span data-ttu-id="955d8-112">Cliquez sur **Parcourir** et sélectionnez le \*\*List.xlsde fournisseur nettoyé \*\*, qui est le fichier de sortie de l’activité de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="955d8-112">Click **Browse** and select **Cleansed Supplier List.xls**, which is the output file from the cleansing activity.</span></span>

8.  <span data-ttu-id="955d8-113">Mappez la colonne source **RéfFournisseur** au domaine de l' **ID** de fournisseur, à la colonne **nom du fournisseur** en domaine **nom du fournisseur** et à la colonne **ContactEmailAddress** sur contacter le domaine de **messagerie** .</span><span class="sxs-lookup"><span data-stu-id="955d8-113">Map **SupplierID** source column to the **Supplier ID** domain, **Supplier Name** column to **Supplier Name** domain, and **ContactEmailAddress** column to **Contact Email** domain.</span></span>

9. <span data-ttu-id="955d8-114">Cliquez sur **suivant** pour basculer vers la page **correspondante** .</span><span class="sxs-lookup"><span data-stu-id="955d8-114">Click **Next** to switch to the **Matching** page.</span></span>

10. <span data-ttu-id="955d8-115">Cliquez sur **Démarrer** pour démarrer le processus de correspondance.</span><span class="sxs-lookup"><span data-stu-id="955d8-115">Click **Start** to start the matching process.</span></span> <span data-ttu-id="955d8-116">Vous devez obtenir des résultats semblables à ceux de la tâche précédente, car vous avez utilisé le même fichier d'entrée pour définir la stratégie de correspondance.</span><span class="sxs-lookup"><span data-stu-id="955d8-116">You should see results similar to those from the previous task because you used the same input file for defining the matching policy.</span></span>

11. <span data-ttu-id="955d8-117">Examinez tous les enregistrements correspondants et leur score de correspondance dans la zone de liste.</span><span class="sxs-lookup"><span data-stu-id="955d8-117">Review all the matched records and their matching score in the list box.</span></span> <span data-ttu-id="955d8-118">Les résultats doivent correspondre à ceux que vous avez obtenus dans la tâche précédente.</span><span class="sxs-lookup"><span data-stu-id="955d8-118">The results should be same as the ones you saw in the previous task.</span></span> <span data-ttu-id="955d8-119">Reportez-vous aux étapes de la tâche précédente pour analyser les résultats de cette activité de correspondance.</span><span class="sxs-lookup"><span data-stu-id="955d8-119">See the steps in the previous task to analyze the results from this matching activity.</span></span>

12. <span data-ttu-id="955d8-120">Cliquez sur **suivant** pour passer à la page **Exporter** .</span><span class="sxs-lookup"><span data-stu-id="955d8-120">Click **Next** to switch to the **Export** page.</span></span>

## <a name="next-step"></a><span data-ttu-id="955d8-121">étape suivante</span><span class="sxs-lookup"><span data-stu-id="955d8-121">Next Step</span></span>
 [<span data-ttu-id="955d8-122">Tâche 4 : Exportation des résultats de l’activité de mise en correspondance dans un fichier Excel</span><span class="sxs-lookup"><span data-stu-id="955d8-122">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>](../../2014/tutorials/task-4-exporting-the-results-from-matching-activity-to-an-excel-file.md)


