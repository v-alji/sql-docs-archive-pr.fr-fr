---
title: 'Tâche 13 : ajout d’OLE DB destination pour écrire des données dans la table de mise en lots MDS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: e6c67fa9-bb52-44a9-82f6-d86551cf12b2
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 77799782518a3be2441b4c461467e3132781298d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698975"
---
# <a name="task-13-adding-ole-db-destination-to-write-data-to-mds-staging-table"></a><span data-ttu-id="f2fe5-102">Tâche 13 : Ajout d’une destination OLE DB pour écrire des données dans une table intermédiaire MDS</span><span class="sxs-lookup"><span data-stu-id="f2fe5-102">Task 13: Adding OLE DB Destination to Write Data to MDS Staging Table</span></span>
  <span data-ttu-id="f2fe5-103">Maintenant que vous avez ajouté des valeurs **ImportType** et **BatchTag** à tous les enregistrements, vous êtes prêt à les envoyer à MDS pour la mise en lots.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-103">Now that you have added **ImportType** and **BatchTag** values to all records, you are ready to send them over to MDS for staging.</span></span> <span data-ttu-id="f2fe5-104">Au cours de cette tâche, vous allez utiliser la destination de la OLE DB pour écrire les données dans **STG. supplier_Leaf** table de mise en lots.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-104">In this task, you use the OLE DB Destination to write the data into **stg.supplier_Leaf** staging table.</span></span>  
  
1.  <span data-ttu-id="f2fe5-105">Faites **glisser OLE DB** la section destination à partir d' **autres destinations** de la **boîte à outils SSIS** vers l’onglet de **Workflow** et déposez-la sous **Ajouter les colonnes requises par MDS**.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-105">Drag **OLE DB Destination** from **Other Destinations** section in the **SSIS Toolbox** to the **Data Flow** tab and drop it under **Add Columns Required by MDS**.</span></span>  
  
2.  <span data-ttu-id="f2fe5-106">Cliquez avec le bouton droit sur **OLE DB destination** dans l’onglet **Flow Data** , puis cliquez sur **Renommer**.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-106">Right-click **OLE DB Destination** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="f2fe5-107">Tapez **écrire les données des fournisseurs dans la table intermédiaire MDS** et appuyez sur **entrée**.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-107">Type **Write Supplier Data to MDS Staging Table** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="f2fe5-108">Connectez le **module ajouter les colonnes requises par MDS** pour **écrire les données des fournisseurs dans la table intermédiaire MDS** à l’aide du connecteur bleu.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-108">Connect the **Add Columns Required by MDS** to **Write Supplier Data to MDS Staging Table** using the blue connector.</span></span>  
  
4.  <span data-ttu-id="f2fe5-109">Double-cliquez sur **écrire les données des fournisseurs dans la table intermédiaire MDS** sous l’onglet du tableau de **bord de données** .</span><span class="sxs-lookup"><span data-stu-id="f2fe5-109">Double-click **Write Supplier Data to MDS Staging Table** in the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="f2fe5-110">Dans la boîte de dialogue **éditeur de Destination OLE DB** , assurez-vous que **(local). MDS** (ou **localhost. MDS**) est sélectionné pour le champ **Gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="f2fe5-110">In the **OLE DB Destination Editor** Dialog box, make sure that **(local).MDS** (or **localhost.MDS**) is selected for the **OLE DB Connection Manager** field.</span></span>  
  
6.  <span data-ttu-id="f2fe5-111">Sélectionnez **STG. Supplier_Leaf** table de la liste de **noms de la table ou**de la vue.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-111">Select **stg.Supplier_Leaf** table from the list of **Name of the table or the view**.</span></span>  
  
     <span data-ttu-id="f2fe5-112">![Éditeur de destination OLEDB](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "Éditeur de destination OLEDB")</span><span class="sxs-lookup"><span data-stu-id="f2fe5-112">![OLEDB Destination Editor](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-01.jpg "OLEDB Destination Editor")</span></span>  
  
7.  <span data-ttu-id="f2fe5-113">Basculez vers la page **mappages** en cliquant sur **mappage** dans le menu de gauche.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-113">Switch to the **Mappings** page by clicking **Mapping** on the menu on left.</span></span>  
  
8.  <span data-ttu-id="f2fe5-114">Mappez les colonnes **d’entrée** et de **destination** comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-114">Map **input** and **destination** columns as shown in the following table.</span></span>  
  
     <span data-ttu-id="f2fe5-115">![Éditeur de destination OLEDB - Mappages](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "Éditeur de destination OLEDB - Mappages")</span><span class="sxs-lookup"><span data-stu-id="f2fe5-115">![OLEDB Destination Editor - Mappings](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-02.jpg "OLEDB Destination Editor - Mappings")</span></span>  
  
9. <span data-ttu-id="f2fe5-116">Vérifiez que vous utilisez **_output** colonnes pour les colonnes d’entrée, et non les colonnes **_Status** ou **_source** .</span><span class="sxs-lookup"><span data-stu-id="f2fe5-116">Confirm that you are using **_Output** columns for Input Columns, not the **_Status** or **_Source** columns.</span></span> <span data-ttu-id="f2fe5-117">**_Output** colonnes contiennent les valeurs de sortie du nettoyage DQS.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-117">**_Output** columns contain the output values from DQS Cleansing.</span></span>  
  
10. <span data-ttu-id="f2fe5-118">Cliquez sur **OK** pour fermer la boîte de dialogue **éditeur de destination de OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="f2fe5-118">Click **OK** to close the **OLE DB Destination Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="f2fe5-119">Le flux de données devrait être similaire à l'illustration suivante.</span><span class="sxs-lookup"><span data-stu-id="f2fe5-119">The data flow should like the following image.</span></span>  
  
     <span data-ttu-id="f2fe5-120">![Flux de données terminé](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Flux de données terminé")</span><span class="sxs-lookup"><span data-stu-id="f2fe5-120">![Completed Data Flow](../../2014/tutorials/media/et-addingoledbdestinationtowdtomdsst-03.jpg "Completed Data Flow")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="f2fe5-121">étape suivante</span><span class="sxs-lookup"><span data-stu-id="f2fe5-121">Next Step</span></span>  
 [<span data-ttu-id="f2fe5-122">Tâche 14 : Ajout d’une tâche d’exécution SQL au flux de contrôle pour exécuter la procédure stockée pour MDS</span><span class="sxs-lookup"><span data-stu-id="f2fe5-122">Task 14: Adding Execute SQL Task to Control Flow to Run the Stored Procedure for MDS</span></span>](../../2014/tutorials/task-14-add-execute-to-control-flow-run-mds-stored-procedure.md)  
  
  
