---
title: 'Tâche 6 : ajout d’une source Excel au workflow de données | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0209055e-cb6b-4a07-909e-836596727a2c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: ae183dee04619a407655026a49b189f7bb3ac6fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612645"
---
# <a name="task-6-adding-excel-source-to-the-data-flow"></a><span data-ttu-id="7c41f-102">Tâche 6 : Ajout d’une source Excel au flux de données</span><span class="sxs-lookup"><span data-stu-id="7c41f-102">Task 6: Adding Excel Source to the Data Flow</span></span>
  <span data-ttu-id="7c41f-103">Dans cette tâche, vous allez ajouter une source Excel au flux de données pour lire les données des fournisseurs à partir du fichier Excel source.</span><span class="sxs-lookup"><span data-stu-id="7c41f-103">In this task, you add an Excel Source to the data flow to read supplier data from the source Excel file.</span></span> <span data-ttu-id="7c41f-104">La source Excel extrait des données depuis des feuilles de calcul ou des plages dans des classeurs Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="7c41f-104">The Excel Source extracts data from worksheets or ranges in Microsoft Excel workbooks.</span></span> <span data-ttu-id="7c41f-105">Consultez la rubrique [Source Excel](../integration-services/data-flow/excel-source.md) pour plus de détails.</span><span class="sxs-lookup"><span data-stu-id="7c41f-105">See [Excel Source](../integration-services/data-flow/excel-source.md) topic for more details.</span></span>

1.  <span data-ttu-id="7c41f-106">Faites glisser la **Source Excel** depuis **Autres sources** dans **Boîte à outils SSIS** vers l'onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="7c41f-106">Drag-drop **Excel Source** from **Other Sources** in **SSIS Toolbox** to the **Data Flow** tab.</span></span>

2.  <span data-ttu-id="7c41f-107">Cliquez avec le bouton droit sur **Source Excel** dans l'onglet **Flux de données** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="7c41f-107">Right-click on **Excel Source** in the **Data Flow** tab, and click **Rename**.</span></span>

3.  <span data-ttu-id="7c41f-108">Entrez **Lire les données des fournisseurs à partir d'un fichier Excel** et appuyez sur **ENTRÉE**.</span><span class="sxs-lookup"><span data-stu-id="7c41f-108">Type **Read Supplier Data from Excel File** and press **ENTER**.</span></span>

4.  <span data-ttu-id="7c41f-109">Double-cliquez sur **Lire les données des fournisseurs à partir d'un fichier Excel** pour ouvrir la boîte de dialogue **Éditeur de source Excel** .</span><span class="sxs-lookup"><span data-stu-id="7c41f-109">Double-click **Read Supplier Data from Excel File** to launch the **Excel Source Editor** dialog box.</span></span>

5.  <span data-ttu-id="7c41f-110">Dans la boîte de dialogue **Éditeur de source Excel** , cliquez sur **Nouveau** pour créer une connexion à Excel.</span><span class="sxs-lookup"><span data-stu-id="7c41f-110">In the **Excel Source Editor** dialog box, click **New** to create an Excel connection.</span></span>

6.  <span data-ttu-id="7c41f-111">Dans la boîte de dialogue **Gestionnaire de connexions Excel** , cliquez sur **Parcourir**, puis recherchez le fichier **Suppliers.xls** dans le dossier **EIM Tutorial** .</span><span class="sxs-lookup"><span data-stu-id="7c41f-111">In the **Excel Connection Manager** dialog box, click **Browse**, and then select the **Suppliers.xls** file in the **EIM Tutorial** folder.</span></span> <span data-ttu-id="7c41f-112">Vérifiez que **Microsoft Excel 97-2003** est sélectionné dans la zone **Version Excel** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="7c41f-112">Confirm that **Microsoft Excel 97-2003** is selected in the **Excel Version** box and then click **OK**.</span></span>

     <span data-ttu-id="7c41f-113">![Boîte de dialogue Gestionnaire de connexions d'Excel](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Boîte de dialogue Gestionnaire de connexions d'Excel")</span><span class="sxs-lookup"><span data-stu-id="7c41f-113">![Excel Connection Manager Dialog Box](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-01.jpg "Excel Connection Manager Dialog Box")</span></span>

7.  <span data-ttu-id="7c41f-114">Dans la boîte de dialogue **Éditeur de source Excel** , sélectionnez **IncomingSuppliers$** dans la zone de liste **Nom de la feuille Excel** .</span><span class="sxs-lookup"><span data-stu-id="7c41f-114">In the **Excel Source Editor** dialog box, select **IncomingSuppliers$** in the **Name of the Excel sheet** list box.</span></span>

     <span data-ttu-id="7c41f-115">![Nom de la feuille Excel - Fournisseurs entrants$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Nom de la feuille Excel - Fournisseurs entrants$")</span><span class="sxs-lookup"><span data-stu-id="7c41f-115">![Name of Excel Sheet - Incoming Suppliers$](../../2014/tutorials/media/et-addingexcelsourcetothedataflow-02.jpg "Name of Excel Sheet - Incoming Suppliers$")</span></span>

8.  <span data-ttu-id="7c41f-116">Cliquez sur **Aperçu** pour afficher un aperçu des données dans le fichier Excel.</span><span class="sxs-lookup"><span data-stu-id="7c41f-116">Click **Preview** to preview the data in Excel file.</span></span>

9. <span data-ttu-id="7c41f-117">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="7c41f-117">Click **OK** to close the dialog box.</span></span>

10. <span data-ttu-id="7c41f-118">Faites glisser la transformation **Nettoyage DQS** dans **Autres transformations** dans la **Boîte à outils SSIS** vers l'onglet **Flux de données** sous **Lire les données des fournisseurs à partir d'un fichier Excel**.</span><span class="sxs-lookup"><span data-stu-id="7c41f-118">Drag-drop **DQS Cleansing** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Read Supplier Data from Excel File**.</span></span> <span data-ttu-id="7c41f-119">La transformation de nettoyage DQS utilise Data Quality Services (DQS) pour corriger les données en appliquant des règles approuvées dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="7c41f-119">The DQS Cleansing transformation uses Data Quality Services (DQS) to correct data by applying approved rules in the knowledge base.</span></span> <span data-ttu-id="7c41f-120">Cette transformation, au moment de l'exécution, crée un projet de nettoyage DQS sur le serveur DQS.</span><span class="sxs-lookup"><span data-stu-id="7c41f-120">This transform, at runtime, creates a DQS cleansing project on the DQS server.</span></span> <span data-ttu-id="7c41f-121">Consultez la rubrique [Transformation de nettoyage DQS](https://msdn.microsoft.com/library/ee677619.aspx) pour plus de détails.</span><span class="sxs-lookup"><span data-stu-id="7c41f-121">See [DQS Cleansing Transformation](https://msdn.microsoft.com/library/ee677619.aspx) topic for more details.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c41f-122">étape suivante</span><span class="sxs-lookup"><span data-stu-id="7c41f-122">Next Step</span></span>

[<span data-ttu-id="7c41f-123">Tâche 7 : Ajout d’une transformation de nettoyage DQS au flux de données</span><span class="sxs-lookup"><span data-stu-id="7c41f-123">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>](task-7-adding-dqs-cleansing-transform-to-the-data-flow.md)

### <a name="see-also"></a><span data-ttu-id="7c41f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7c41f-124">See Also</span></span>

[<span data-ttu-id="7c41f-125">Flux de données</span><span class="sxs-lookup"><span data-stu-id="7c41f-125">Data Flow</span></span>](../integration-services/data-flow/data-flow.md)
