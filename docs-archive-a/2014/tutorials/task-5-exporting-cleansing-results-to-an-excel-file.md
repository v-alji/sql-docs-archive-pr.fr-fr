---
title: 'Tâche 5 : exportation des résultats du nettoyage dans un fichier Excel | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eaeafd65-d0d4-4a7d-a3ad-110ef644e90b
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0dbdc1bef348e03e211e4933132985ea2c089b97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612650"
---
# <a name="task-5-exporting-cleansing-results-to-an-excel-file"></a><span data-ttu-id="09e48-102">Tâche 5 : Exportation des résultats du nettoyage vers un fichier Excel</span><span class="sxs-lookup"><span data-stu-id="09e48-102">Task 5: Exporting Cleansing Results to an Excel File</span></span>
  <span data-ttu-id="09e48-103">Dans cette tâche, vous allez exporter les résultats de l'activité de nettoyage dans un fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="09e48-103">In this task, you export results from the cleansing activity to an Excel file.</span></span> <span data-ttu-id="09e48-104">Pour plus d’informations, consultez la rubrique relative à la [phase d’exportation](https://msdn.microsoft.com/library/hh213061.aspx#Export) .</span><span class="sxs-lookup"><span data-stu-id="09e48-104">See [Export Stage](https://msdn.microsoft.com/library/hh213061.aspx#Export) topic for more details.</span></span>  
  
1.  <span data-ttu-id="09e48-105">Dans le volet droit, sélectionnez **Excel** comme **type de destination**.</span><span class="sxs-lookup"><span data-stu-id="09e48-105">In the right pane, select **Excel** for the **Destination Type**.</span></span>  
  
2.  <span data-ttu-id="09e48-106">Cliquez sur **Parcourir**, spécifiez le nom du fichier de sortie en tant que **fournisseur nettoyé List.xls**, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="09e48-106">Click **Browse**, specify the output file name as **Cleansed Supplier List.xls**, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="09e48-107">Sélectionnez **données uniquement** pour le format de **sortie** afin d’exporter uniquement les données nettoyées.</span><span class="sxs-lookup"><span data-stu-id="09e48-107">Select **Data Only** for the **Output** format to export just the cleansed data.</span></span> <span data-ttu-id="09e48-108">La deuxième option, **données et informations de nettoyage**, vous permet d’exporter les détails de l’activité de nettoyage, ainsi que les données nettoyées.</span><span class="sxs-lookup"><span data-stu-id="09e48-108">The second option, **Data and Cleansing Info**, lets you export cleansing activity details along with the cleansed data.</span></span> <span data-ttu-id="09e48-109">L’option de **format standard** vous permet d’appliquer les formats de sortie que vous définissez sur un domaine aux valeurs de ce domaine.</span><span class="sxs-lookup"><span data-stu-id="09e48-109">The **Standardize Format** option lets you apply any output formats you define on a domain to the values of that domain.</span></span> <span data-ttu-id="09e48-110">Vous n'avez pas défini de format de sortie pour un domaine dans le didacticiel.</span><span class="sxs-lookup"><span data-stu-id="09e48-110">You have not defined an output format on any domain in the tutorial.</span></span>  
  
     <span data-ttu-id="09e48-111">![Page Exporter les résultats de nettoyage](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Page Exporter les résultats de nettoyage")</span><span class="sxs-lookup"><span data-stu-id="09e48-111">![Export Cleansing Results Page](../../2014/tutorials/media/et-exportingcleansingresultstoanexcelfile.jpg "Export Cleansing Results Page")</span></span>  
  
4.  <span data-ttu-id="09e48-112">Cliquez sur **Exporter** pour exporter les données.</span><span class="sxs-lookup"><span data-stu-id="09e48-112">Click **Export** to export the data.</span></span> <span data-ttu-id="09e48-113">Ne cliquez pas encore sur **Terminer** .</span><span class="sxs-lookup"><span data-stu-id="09e48-113">Do not click **Finish** yet.</span></span>  
  
5.  <span data-ttu-id="09e48-114">Cliquez sur **Fermer** dans la boîte de dialogue **exportation** .</span><span class="sxs-lookup"><span data-stu-id="09e48-114">Click **Close** on the **Exporting** dialog box.</span></span>  
  
6.  <span data-ttu-id="09e48-115">Cliquez sur **Terminer** pour terminer l’activité.</span><span class="sxs-lookup"><span data-stu-id="09e48-115">Click **Finish** to finish the activity.</span></span> <span data-ttu-id="09e48-116">Si vous avez oublié d’exporter les résultats avant de cliquer sur **Terminer**, cliquez sur **ouvrir le projet de qualité des données** dans la page principale du **client DQS**, sélectionnez **nettoyer la liste des fournisseurs** dans la liste des projets, puis cliquez sur **suivant** en bas de l’écran pour revenir à l’étape d' **exportation** du processus de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="09e48-116">If you forgot to export results before clicking **Finish**, click **Open Data Quality Project** in the main page of **DQS Client**, select **Cleanse Supplier List** from the list of projects, and click **Next** at the bottom of the screen to get to the **Export** stage of cleansing process again.</span></span> <span data-ttu-id="09e48-117">Vous pouvez également basculer vers l’onglet **gérer et afficher les résultats** en cliquant sur le bouton **précédent** .</span><span class="sxs-lookup"><span data-stu-id="09e48-117">You can also switch to **Manage and View Results** tab by clicking **Back** button.</span></span>  
  
7.  <span data-ttu-id="09e48-118">Ouvrez le **List.xlsdu fournisseur nettoyé** et procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="09e48-118">Open the **Cleansed Supplier List.xls** and do the following:</span></span>  
  
    1.  <span data-ttu-id="09e48-119">Assurez-vous qu’il n’y a pas d’adresse de messagerie se terminant par adventure-work.com (sans le caractère') en recherchant adventure-work.com dans la feuille de calcul.</span><span class="sxs-lookup"><span data-stu-id="09e48-119">Ensure that there are no email addresses that end with adventure-work.com (without character 's') by searching for adventure-work.com in the worksheet.</span></span>  
  
    2.  <span data-ttu-id="09e48-120">Vérifiez qu’il n’y a pas de valeur **USA** dans la colonne **Country** .</span><span class="sxs-lookup"><span data-stu-id="09e48-120">See that there is no **USA** value in the **Country** column.</span></span>  
  
    3.  <span data-ttu-id="09e48-121">Recherchez **Los Angeles** et vérifiez que l' **État** est défini sur **ca**.</span><span class="sxs-lookup"><span data-stu-id="09e48-121">Search for **Los Angeles** and see that the **State** is set to **CA**.</span></span>  
  
    4.  <span data-ttu-id="09e48-122">Confirmez qu’il n’y a pas de termes **Co.**, **Corp.** et **Inc.**</span><span class="sxs-lookup"><span data-stu-id="09e48-122">Confirm that there are no terms **Co.**, **Corp.**, and **Inc.**.</span></span>  
  
    5.  <span data-ttu-id="09e48-123">Supprimez la colonne **validation d’adresse** de la feuille de calcul et enregistrez le fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="09e48-123">Delete the **Address Validation** column from the spreadsheet and save the excel file.</span></span> <span data-ttu-id="09e48-124">Cette colonne supplémentaire correspond au domaine composite Validation d'adresses.</span><span class="sxs-lookup"><span data-stu-id="09e48-124">This additional column corresponds to the Address Validation composite domain.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="09e48-125">étape suivante</span><span class="sxs-lookup"><span data-stu-id="09e48-125">Next Step</span></span>  
 [<span data-ttu-id="09e48-126">Tâche 6 : Importation de valeurs depuis le projet de nettoyage de la liste des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="09e48-126">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>](../../2014/tutorials/task-6-importing-values-from-the-cleanse-supplier-list-project.md)  
  
  
