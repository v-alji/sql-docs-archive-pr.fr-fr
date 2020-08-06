---
title: 'Leçon 5 : concevoir le rapport enfant à l’aide de l’Assistant Rapport | Microsoft Docs'
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 19a3f927-ea97-4f40-a5f8-cd5f2598e4da
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f188a914fc2a2bb8370843191a31474a54c02aa8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601963"
---
# <a name="lesson-5-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="9dc9b-102">Leçon 5 : concevoir le rapport enfant à l'aide de l'Assistant Rapport</span><span class="sxs-lookup"><span data-stu-id="9dc9b-102">Lesson 5: Design the Child Report using the Report Wizard</span></span>
  <span data-ttu-id="9dc9b-103">Après avoir créé une connexion de données et une table de données pour le rapport enfant, l'étape suivante consiste à concevoir le rapport enfant à l'aide de l'Assistant Rapport dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-103">After you create a data connection and data table for the child report, your next step is to design the child report using the Report Wizard in Report Designer.</span></span> <span data-ttu-id="9dc9b-104">Pour plus d’informations sur le Concepteur de rapports, consultez [Concevoir des rapports à l’aide du Concepteur de rapports &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="9dc9b-104">For more information about Report Designer, see [Design Reports with Report Designer &#40;SSRS&#41;](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md).</span></span>  
  
### <a name="to-design-the-child-report-using-the-report-wizard"></a><span data-ttu-id="9dc9b-105">Pour concevoir le rapport enfant à l'aide de l'Assistant Rapport</span><span class="sxs-lookup"><span data-stu-id="9dc9b-105">To design the child report using the Report Wizard</span></span>  
  
1.  <span data-ttu-id="9dc9b-106">Vérifiez que le site web de niveau supérieur est sélectionné dans **l’Explorateur de solutions**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-106">Make sure that the top-level website is selected in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="9dc9b-107">Cliquez avec le bouton droit sur le site web et sélectionnez **Ajouter un nouvel élément**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-107">Right-click on the website and select **Add New Item**.</span></span>  
  
3.  <span data-ttu-id="9dc9b-108">Dans la boîte de dialogue **Ajouter un nouvel élément** , cliquez sur **Assistant Rapport**, entrez un nom pour le fichier de rapport, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-108">In the **Add New Item** dialog box, click **Report Wizard**, enter a name for the report file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="9dc9b-109">Cette opération permet de lancer l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-109">This launches the Report Wizard.</span></span>  
  
4.  <span data-ttu-id="9dc9b-110">Dans la page **Propriétés du DataSet** , dans la zone source de **données** , cliquez sur **dataset2**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-110">In the **Dataset Properties** page, in the **Data source** box, click **DataSet2**.</span></span>  
  
     <span data-ttu-id="9dc9b-111">La zone **Datasets disponibles** est automatiquement mise à jour avec l’objet DataTable que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-111">The **Available datasets** box is automatically updated with the DataTable you created.</span></span>  
  
5.  <span data-ttu-id="9dc9b-112">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-112">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="9dc9b-113">Dans la page **Organiser les champs** , procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9dc9b-113">In the **Arrange Fields** page do the following:</span></span>  
  
    1.  <span data-ttu-id="9dc9b-114">Faites glisser **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**et **StockedQty** depuis **Champs disponibles** vers la zone **Valeurs** .</span><span class="sxs-lookup"><span data-stu-id="9dc9b-114">Drag **ProductID**, **PurchaseOrderID**, **PurchaseOrderDetailID**, **OrderQty**, **ReceivedQty**, **RejectedQty**, and **StockedQty** from **Available Fields** to the **Values** box.</span></span>  
  
    2.  <span data-ttu-id="9dc9b-115">Cliquez sur la flèche en regard de **Sum (ProductID)**, **Sum (PurchaseOrderID)**, **Sum (PurchaseOrderDetailID)**, **Sum (OrderQty)**, **Sum (ReceivedQty)**, **Sum (RejectedQty)** et **Sum (StockedQty)** et effacez la sélection **Sum** .</span><span class="sxs-lookup"><span data-stu-id="9dc9b-115">Click the arrow next to **Sum(ProductID)**, **Sum(PurchaseOrderID)**, **Sum(PurchaseOrderDetailID)**, **Sum(OrderQty)**, **Sum(ReceivedQty)**, **Sum(RejectedQty)**, and **Sum(StockedQty)** and clear the **Sum** selection.</span></span>  
  
7.  <span data-ttu-id="9dc9b-116">Cliquez sur **suivant** à deux reprises, puis sur **Terminer** pour fermer l' **Assistant Rapport**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-116">Click **Next** twice, then click **Finish** to close the **Report Wizard**.</span></span>  
  
     <span data-ttu-id="9dc9b-117">Vous avez maintenant créé le fichier .rdlc.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-117">You've now created the .rdlc file.</span></span> <span data-ttu-id="9dc9b-118">Le fichier s'ouvre dans le Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-118">The file opens in Report Designer.</span></span> <span data-ttu-id="9dc9b-119">Le tableau matriciel que vous avez conçu est maintenant affiché dans l'aire de conception.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-119">The tablix you designed is now displayed in the design surface.</span></span>  
  
8.  <span data-ttu-id="9dc9b-120">Le fichier .rdlc étant ouvert, ajoutez un paramètre en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="9dc9b-120">With the .rdlc file open, add a parameter by doing the following:</span></span>  
  
    1.  <span data-ttu-id="9dc9b-121">Dans le volet **données du rapport** , cliquez sur **paramètres** , puis sur **Ajouter des paramètres**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-121">Click **Parameters** in the **Report Data** pane, and then click **Add Parameters**.</span></span>  
  
    2.  <span data-ttu-id="9dc9b-122">Entrez **productid** dans la zone **Nom** .</span><span class="sxs-lookup"><span data-stu-id="9dc9b-122">Enter **productid** in the **Name** box.</span></span>  
  
    3.  <span data-ttu-id="9dc9b-123">Vérifiez que **Entier** est sélectionné dans la zone de liste **Type de données** .</span><span class="sxs-lookup"><span data-stu-id="9dc9b-123">Confirm that **Integer** is selected in the **Data Type** list box.</span></span>  
  
    4.  <span data-ttu-id="9dc9b-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="9dc9b-125">Enregistrez le fichier .rdlc.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-125">Save the .rdlc file.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="9dc9b-126">Tâche suivante</span><span class="sxs-lookup"><span data-stu-id="9dc9b-126">Next Task</span></span>  
 <span data-ttu-id="9dc9b-127">Vous venez de concevoir le rapport enfant à l'aide de l'Assistant Rapport.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-127">You have successfully designed the child report by using the Report Wizard.</span></span> <span data-ttu-id="9dc9b-128">Vous allez à présent ajouter un contrôle ReportViewer dans l'application de site Web.</span><span class="sxs-lookup"><span data-stu-id="9dc9b-128">Next, you will add a ReportViewer control to the website application.</span></span>  
  
  
