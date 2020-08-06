---
title: 'Tâche 2 : mappage des colonnes Excel aux domaines DQS | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613242"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a><span data-ttu-id="74215-102">Tâche 2 : Mappage de colonnes d’Excel aux domaines DQS</span><span class="sxs-lookup"><span data-stu-id="74215-102">Task 2: Mapping Excel Columns to DQS Domains</span></span>
    
1.  <span data-ttu-id="74215-103">Dans la page **Mapper** , sélectionnez **Fichier Excel** pour **Source de données**.</span><span class="sxs-lookup"><span data-stu-id="74215-103">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
2.  <span data-ttu-id="74215-104">Cliquez sur **Parcourir**, sélectionnez **Suppliers.xlsx**, puis cliquez sur **ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="74215-104">Click **Browse**, select **Suppliers.xlsx**, and click **Open**.</span></span>  
  
3.  <span data-ttu-id="74215-105">Sélectionnez **IncomingSuppliers $** pour la **feuille de calcul**.</span><span class="sxs-lookup"><span data-stu-id="74215-105">Select **IncomingSuppliers$** for the **Worksheet**.</span></span>  
  
4.  <span data-ttu-id="74215-106">Mappez les colonnes comme indiqué dans le tableau suivant et dans la capture d'écran.</span><span class="sxs-lookup"><span data-stu-id="74215-106">Map columns as shown in the following table and screenshot.</span></span> <span data-ttu-id="74215-107">Lorsque vous créez des mappages pour le domaine d' **État** , cliquez sur le bouton **Ajouter un mappage de colonnes** dans la barre d’outils située juste au-dessus de la liste.</span><span class="sxs-lookup"><span data-stu-id="74215-107">When creating mappings for the **State** domain, click **Add a column mapping** button on the toolbar located just above the list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="74215-108">Vous n’utilisez pas la colonne/le domaine de l' **ID de fournisseur** pour le nettoyage.</span><span class="sxs-lookup"><span data-stu-id="74215-108">You are not using **Supplier ID** column/domain for cleansing.</span></span> <span data-ttu-id="74215-109">Vous utiliserez le domaine **ID du fournisseur** ultérieurement dans l’activité de correspondance.</span><span class="sxs-lookup"><span data-stu-id="74215-109">You will use the **Supplier ID** domain later in the matching activity.</span></span>  
  
    |<span data-ttu-id="74215-110">Colonne Excel</span><span class="sxs-lookup"><span data-stu-id="74215-110">Excel column</span></span>|<span data-ttu-id="74215-111">Domaine DQS</span><span class="sxs-lookup"><span data-stu-id="74215-111">DQS Domain</span></span>|  
    |------------------|----------------|  
    |<span data-ttu-id="74215-112">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="74215-112">Supplier Name</span></span>|<span data-ttu-id="74215-113">Nom du fournisseur</span><span class="sxs-lookup"><span data-stu-id="74215-113">Supplier Name</span></span>|  
    |<span data-ttu-id="74215-114">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="74215-114">ContactEmailAddress</span></span>|<span data-ttu-id="74215-115">E-mail du contact</span><span class="sxs-lookup"><span data-stu-id="74215-115">Contact Email</span></span>|  
    |<span data-ttu-id="74215-116">Adresse</span><span class="sxs-lookup"><span data-stu-id="74215-116">Address Line</span></span>|<span data-ttu-id="74215-117">Adresse</span><span class="sxs-lookup"><span data-stu-id="74215-117">Address Line</span></span>|  
    |<span data-ttu-id="74215-118">City</span><span class="sxs-lookup"><span data-stu-id="74215-118">City</span></span>|<span data-ttu-id="74215-119">City</span><span class="sxs-lookup"><span data-stu-id="74215-119">City</span></span>|  
    |<span data-ttu-id="74215-120">State</span><span class="sxs-lookup"><span data-stu-id="74215-120">State</span></span>|<span data-ttu-id="74215-121">State</span><span class="sxs-lookup"><span data-stu-id="74215-121">State</span></span>|  
    |<span data-ttu-id="74215-122">Pays (cliquez sur **+ (ajouter un mappage de colonnes)** barre d’outils pour ajouter une ligne)</span><span class="sxs-lookup"><span data-stu-id="74215-122">Country (Click **+(Add a column mapping)** toolbar to add a row)</span></span>|<span data-ttu-id="74215-123">Pays ou région</span><span class="sxs-lookup"><span data-stu-id="74215-123">Country</span></span>|  
    |<span data-ttu-id="74215-124">Code postal</span><span class="sxs-lookup"><span data-stu-id="74215-124">Zip Code</span></span>|<span data-ttu-id="74215-125">Zip</span><span class="sxs-lookup"><span data-stu-id="74215-125">Zip</span></span>|  
  
     <span data-ttu-id="74215-126">![Mappages des colonnes d'Excel aux domaines](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappages des colonnes d'Excel aux domaines")</span><span class="sxs-lookup"><span data-stu-id="74215-126">![Mappings of Excel Columns to Domains](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappings of Excel Columns to Domains")</span></span>  
  
5.  <span data-ttu-id="74215-127">Comme vous avez mappé tous les domaines individuels dans le domaine composite **validation d’adresse** , le domaine composite participe automatiquement au processus de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="74215-127">As you have mapped all the individual domains within the **Address Validation** composite domain, the composite domain automatically participates in the cleansing process.</span></span> <span data-ttu-id="74215-128">Cliquez sur le bouton **Afficher/sélectionner des domaines composites** pour voir que le domaine composite **validation d’adresse** est sélectionné automatiquement, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="74215-128">Click **View/Select Composite Domains** button to see that the **Address Validation** composite domain is automatically selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="74215-129">![Boîte de dialogue Afficher/Sélectionner des domaines composites](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Boîte de dialogue Afficher/Sélectionner des domaines composites")</span><span class="sxs-lookup"><span data-stu-id="74215-129">![View/Select Composite Domains Dialog Box](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "View/Select Composite Domains Dialog Box")</span></span>  
  
6.  <span data-ttu-id="74215-130">Cliquez sur **suivant** pour basculer vers la page **nettoyer** .</span><span class="sxs-lookup"><span data-stu-id="74215-130">Click **Next** to switch to the **Cleanse** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="74215-131">étape suivante</span><span class="sxs-lookup"><span data-stu-id="74215-131">Next Step</span></span>  
 [<span data-ttu-id="74215-132">Tâche 3 : Nettoyage des données dans la base de connaissances Fournisseurs</span><span class="sxs-lookup"><span data-stu-id="74215-132">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
