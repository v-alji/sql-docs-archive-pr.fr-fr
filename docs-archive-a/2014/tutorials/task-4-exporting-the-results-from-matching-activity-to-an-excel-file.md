---
title: 'Tâche 4 : exportation des résultats de l’activité de correspondance dans un fichier Excel | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 644454c4-3c5a-469a-90ec-e51dc7fb99fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b583e44f887fc0595fb904ec977f1de28c2fecd9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704419"
---
# <a name="task-4-exporting-the-results-from-matching-activity-to-an-excel-file"></a><span data-ttu-id="f5476-102">Tâche 4 : Exportation des résultats de l’activité de mise en correspondance dans un fichier Excel</span><span class="sxs-lookup"><span data-stu-id="f5476-102">Task 4: Exporting the Results from Matching Activity to an Excel File</span></span>
  <span data-ttu-id="f5476-103">Dans cette tâche, vous allez exporter les résultats de l'activité de mise en correspondance dans un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="f5476-103">In this task, you export the results from the matching activity to an Excel file.</span></span>

1.  <span data-ttu-id="f5476-104">Dans la page **Exporter** , sélectionnez **fichier Excel** pour le **type de destination**.</span><span class="sxs-lookup"><span data-stu-id="f5476-104">In the **Export** page, select **Excel File** for the **Destination Type**.</span></span>

2.  <span data-ttu-id="f5476-105">Sélectionnez l’option **résultats de survie** .</span><span class="sxs-lookup"><span data-stu-id="f5476-105">Select **Survivorship Results** option.</span></span> <span data-ttu-id="f5476-106">Dans le processus de survie, DQS détermine un enregistrement survivant pour chaque cluster en fonction de la **règle de survie** que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="f5476-106">In the survivorship process, DQS determines a survivor record for each cluster based on the **Survivorship Rule** you selected.</span></span>

3.  <span data-ttu-id="f5476-107">Cliquez sur **Parcourir** et accédez au dossier dans lequel vous souhaitez stocker le fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="f5476-107">Click **Browse** and navigate to the folder where you want to store the output file.</span></span>

4.  <span data-ttu-id="f5476-108">Tapez **nettoyer et faire correspondre Suppliers.xls** pour le nom et cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="f5476-108">Type **Cleansed and Matched Suppliers.xls** for the name and click **Open**.</span></span>

5.  <span data-ttu-id="f5476-109">Vérifiez que l' **enregistrement pivot** est sélectionné pour la **règle de survie**.</span><span class="sxs-lookup"><span data-stu-id="f5476-109">Confirm that **Pivot Record** is selected for the **Survivorship Rule**.</span></span> <span data-ttu-id="f5476-110">Lorsque vous sélectionnez cette option, l'enregistrement pivot de chaque cluster est choisi pour la sortie d'un cluster.</span><span class="sxs-lookup"><span data-stu-id="f5476-110">When you select this option, the pivot record for each cluster is picked for the output from a cluster.</span></span> <span data-ttu-id="f5476-111">Les autres options de la règle de survivance sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="f5476-111">The other options for the Survivorship Rule are:</span></span>

    1.  <span data-ttu-id="f5476-112">**Enregistrement le plus complet :** L’enregistrement survivant est celui avec le plus grand nombre de champs remplis.</span><span class="sxs-lookup"><span data-stu-id="f5476-112">**Most complete record:** Survivor record is the one with the largest number of populated fields.</span></span>

    2.  <span data-ttu-id="f5476-113">**Enregistrement le plus long :** L’enregistrement survivant est celui avec le plus grand nombre de termes dans les champs sources.</span><span class="sxs-lookup"><span data-stu-id="f5476-113">**Longest record:** Survivor record is the one with the largest number of terms in source fields.</span></span>

    3.  <span data-ttu-id="f5476-114">**Enregistrement le plus complet et le plus long :** L’enregistrement survivant est celui avec le plus grand nombre de champs remplis et contient le plus grand nombre de termes dans chaque champ.</span><span class="sxs-lookup"><span data-stu-id="f5476-114">**Most complete and longest record:** Survivor record is the one with the largest number of populated fields, and has the largest number of terms in each field.</span></span>

     <span data-ttu-id="f5476-115">![Exporter les résultats à partir de la Page de correspondance](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Exporter les résultats à partir de la Page de correspondance")</span><span class="sxs-lookup"><span data-stu-id="f5476-115">![Export Results from Matching Page](../../2014/tutorials/media/et-exportingtheresultsfrommatoanexcelfile.jpg "Export Results from Matching Page")</span></span>

6.  <span data-ttu-id="f5476-116">Cliquez sur **Exporter** pour exporter les résultats vers un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="f5476-116">Click **Export** to export the results to an Excel file.</span></span>

7.  <span data-ttu-id="f5476-117">Cliquez sur **Fermer** pour fermer la boîte de dialogue **Exporter correspondante** .</span><span class="sxs-lookup"><span data-stu-id="f5476-117">Click **Close** to close the **Matching Export** dialog box.</span></span>

8.  <span data-ttu-id="f5476-118">Cliquez sur **Terminer** pour terminer l’activité de correspondance.</span><span class="sxs-lookup"><span data-stu-id="f5476-118">Click **Finish** to finish the matching activity.</span></span>

9. <span data-ttu-id="f5476-119">Ouvrez le fichier **nettoyé et mis en correspondance Suppliers.xlsx** et vérifiez que vous ne voyez pas de doublons (RéfFournisseur).</span><span class="sxs-lookup"><span data-stu-id="f5476-119">Open the **Cleansed and Matched Suppliers.xlsx** file and confirm that you do not see any duplicates (SupplierID).</span></span>

 <span data-ttu-id="f5476-120">À présent, les données des fournisseurs ont été nettoyées et mises en correspondance pour supprimer les doublons.</span><span class="sxs-lookup"><span data-stu-id="f5476-120">Now, you have supplier data that has been cleansed and matched to remove duplicates.</span></span>

## <a name="next-step"></a><span data-ttu-id="f5476-121">étape suivante</span><span class="sxs-lookup"><span data-stu-id="f5476-121">Next Step</span></span>
 [<span data-ttu-id="f5476-122">Leçon 4 : Stockage des données sur les fournisseurs dans MDS</span><span class="sxs-lookup"><span data-stu-id="f5476-122">Lesson 4: Storing Supplier Data in MDS</span></span>](../../2014/tutorials/lesson-4-storing-supplier-data-in-mds.md)


