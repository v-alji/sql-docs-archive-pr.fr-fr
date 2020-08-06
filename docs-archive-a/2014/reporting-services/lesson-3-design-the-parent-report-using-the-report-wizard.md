---
title: 'Leçon 3 : concevoir le rapport parent à l’aide de l’Assistant Rapport | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2f69dcd3-cd6d-45a9-a62a-ba6f5f3179d8
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f3cb6a0972a2bb63e82e80c02b3ce90912ba01c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601969"
---
# <a name="lesson-3-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="3261f-102">Leçon 3 : concevoir le rapport parent à l'aide de l'Assistant Rapport</span><span class="sxs-lookup"><span data-stu-id="3261f-102">Lesson 3: Design the Parent Report using the Report Wizard</span></span>
  <span data-ttu-id="3261f-103">Après avoir créé une connexion de données et une table de données pour le rapport parent, l'étape suivante consiste à concevoir le rapport parent à l'aide de l'Assistant Rapport dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3261f-103">After you create a data connection and a data table for the parent report, your next step is to design the parent report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="3261f-104">Pour plus d’informations sur le Concepteur de rapports, consultez [Concevoir des rapports à l’aide du Concepteur de rapports &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="3261f-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-parent-report-using-the-report-wizard"></a><span data-ttu-id="3261f-105">Pour concevoir le rapport parent à l'aide de l'Assistant Rapport</span><span class="sxs-lookup"><span data-stu-id="3261f-105">To design the parent report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="3261f-106">Vérifiez que le site web de niveau supérieur est sélectionné dans **l’Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="3261f-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="3261f-107">Cliquez avec le bouton droit sur le site web et sélectionnez **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="3261f-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="3261f-108">Dans la boîte de dialogue **Ajouter un nouvel élément** , sélectionnez **Assistant Rapport**, entrez un nom pour le fichier de rapport, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="3261f-108">In the **Add New Item** dialog box, select **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="3261f-109">Cette opération permet de lancer l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="3261f-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="3261f-110">Dans la page **Propriétés du dataset** , dans la zone **Source de données** , sélectionnez le **DataSet1** que vous avez créé à la [Leçon 2 : Définir une connexion de données et une table de données pour le rapport parent](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span><span class="sxs-lookup"><span data-stu-id="3261f-110">On the **Dataset Properties** page, in the **Data source** box, select the **DataSet1** you created in [Lesson 2: Define a Data Connection and Data Table for Parent Report](lesson-2-define-a-data-connection-and-data-table-for-parent-report.md).</span></span>  
    <span data-ttu-id="3261f-111">La zone **Datasets disponibles** est mise à jour automatiquement avec l’objet **DataTable** créé précédemment.</span><span class="sxs-lookup"><span data-stu-id="3261f-111">The **Available datasets** box is automatically updated with the **DataTable** you created above.</span></span>  
  
5.  <span data-ttu-id="3261f-112">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="3261f-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3261f-113">Dans la page **Organiser les champs** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3261f-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="3261f-114">Faites glisser **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**et **ReorderLevel** depuis **Champs disponibles** vers la zone **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="3261f-114">Drag **ProductID**, **Name**, **ProductNumber**, **SafetyStockLevel**, and **ReorderLevel** from **Available fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="3261f-115">Cliquez sur la flèche en regard de **Sum (ProductID)**, **Sum (SafetyStockLevel)**, **Sum (ReorderLevel)** et effacez la sélection **Sum** .</span><span class="sxs-lookup"><span data-stu-id="3261f-115">Click the arrow next to **Sum(ProductID)**, **Sum(SafetyStockLevel)**, **Sum(ReorderLevel)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="3261f-116">Cliquez sur **suivant** à deux reprises, puis sur **Terminer** pour fermer l' **Assistant Rapport**.</span><span class="sxs-lookup"><span data-stu-id="3261f-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="3261f-117">Vous avez maintenant créé le fichier .rdlc.</span><span class="sxs-lookup"><span data-stu-id="3261f-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="3261f-118">Le fichier s'ouvre dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3261f-118">The file opens in Report Designer.</span></span> <span data-ttu-id="3261f-119">Le tableau matriciel que vous avez conçu est maintenant affiché dans l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="3261f-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="3261f-120">Enregistrez le fichier .rdlc.</span><span class="sxs-lookup"><span data-stu-id="3261f-120">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="3261f-121">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="3261f-121">Next Task</span></span>  
 <span data-ttu-id="3261f-122">Vous venez de concevoir le rapport parent à l'aide de l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="3261f-122">You have successfully designed the parent report using the Report Wizard.</span></span> <span data-ttu-id="3261f-123">Vous allez à présent créer une connexion de données et une table de données pour le rapport enfant.</span><span class="sxs-lookup"><span data-stu-id="3261f-123">Next, you will create a data connection and a data table for the child report.</span></span>  
  
  
