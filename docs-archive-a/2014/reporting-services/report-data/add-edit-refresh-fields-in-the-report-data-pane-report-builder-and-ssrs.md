---
title: Ajouter, modifier ou actualiser des champs dans le volet Données du rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 2e36f0fe-8100-4513-b169-14d611646f81
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2a20880b84383fc5d9f96c5611419a08facb9ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600586"
---
# <a name="add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs"></a><span data-ttu-id="2e72a-102">ajouter, modifier ou actualiser des champs dans le volet des données de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="2e72a-102">Add, Edit, Refresh Fields in the Report Data Pane (Report Builder and SSRS)</span></span>
  <span data-ttu-id="2e72a-103">Les champs de dataset sont la collection intégrée de noms de champs qui représentent les données qui sont retournées lorsqu'une requête de dataset s'exécute sur une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="2e72a-103">Dataset fields are the built-in collection of field names that represent the data that is returned when a dataset query runs on an external data source.</span></span>  
  
 <span data-ttu-id="2e72a-104">Pour un dataset incorporé, les champs de dataset sont les champs créés après avoir terminé la génération d'une requête et fermé le volet Concepteur de requêtes, ainsi que les champs calculés que vous créez.</span><span class="sxs-lookup"><span data-stu-id="2e72a-104">For an embedded dataset, the dataset fields are the fields that are created after you finish building a query and close the Query Designer pane, and calculated fields that you create.</span></span>  
  
 <span data-ttu-id="2e72a-105">Pour un dataset partagé, les champs de dataset sont les champs de la définition du dataset partagé lorsque vous l'avez ajoutée à votre rapport.</span><span class="sxs-lookup"><span data-stu-id="2e72a-105">For a shared dataset, the dataset fields are the fields from the shared dataset definition when you added it to your report.</span></span> <span data-ttu-id="2e72a-106">Bien que la requête depuis le dataset partagé sur le serveur de rapports soit toujours utilisée lorsque vous exécutez le rapport, la liste de champs de dataset est statique dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="2e72a-106">Although the query from the shared dataset on the report server is always used when you run the report, the list of dataset fields in the report is static.</span></span>  
  
 <span data-ttu-id="2e72a-107">Utilisez **Actualiser les champs** pour mettre à jour la liste de champs dans le rapport afin qu'elle corresponde à la liste actuelle des champs de la requête du dataset partagé.</span><span class="sxs-lookup"><span data-stu-id="2e72a-107">Use **Refresh Fields** to update the list of fields in the report to match the current list of fields from the shared dataset query.</span></span> <span data-ttu-id="2e72a-108">L'actualisation de la liste de champs n'affecte pas les champs calculés que vous définissez dans votre rapport.</span><span class="sxs-lookup"><span data-stu-id="2e72a-108">Refreshing the field list does not affect the calculated fields that you define in your report.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-a-query-field"></a><span data-ttu-id="2e72a-109">Pour ajouter un champ de requête</span><span class="sxs-lookup"><span data-stu-id="2e72a-109">To add a query field</span></span>  
  
1.  <span data-ttu-id="2e72a-110">Dans le volet des données de rapport, cliquez avec le bouton droit sur le dataset, puis sélectionnez **Ajouter un champ de requête**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-110">In the Report Data pane, right-click the dataset, and then click **Add Query Field**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e72a-111">Si le volet des données de rapport n’est pas visible, cliquez sur **Données du rapport** dans le menu **Affichage**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-111">If you cannot see the Report Data pane, from the **View** menu, click **Report Data**.</span></span>  
  
2.  <span data-ttu-id="2e72a-112">Dans la page **Champs** de la boîte de dialogue **Propriétés du dataset** , cliquez sur **Ajouter**, puis sur **Champ de requête**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-112">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Query Field**.</span></span> <span data-ttu-id="2e72a-113">Une nouvelle ligne est ajoutée au bas de la grille.</span><span class="sxs-lookup"><span data-stu-id="2e72a-113">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="2e72a-114">Dans la zone de texte **Nom du champ** , tapez le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="2e72a-114">In the **Field Name** text box, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e72a-115">Les noms doivent être uniques dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="2e72a-115">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="2e72a-116">Dans la zone de texte **Champ source** , tapez le nom d'un champ existant sur la source de données.</span><span class="sxs-lookup"><span data-stu-id="2e72a-116">In the **Field Source** text box, type the name of an existing field on the data source.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-add-a-calculated-field"></a><span data-ttu-id="2e72a-117">Pour ajouter un champ calculé</span><span class="sxs-lookup"><span data-stu-id="2e72a-117">To add a calculated field</span></span>  
  
1.  <span data-ttu-id="2e72a-118">Dans le volet des données de rapport, cliquez avec le bouton droit sur le dataset, puis cliquez sur **Ajouter un champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-118">In the Report Data pane, right-click the dataset, and then click **Add Calculated Field**.</span></span>  
  
2.  <span data-ttu-id="2e72a-119">Dans la page **Champs** de la boîte de dialogue **Propriétés du dataset** , cliquez sur **Ajouter**, puis sur **Champ calculé**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-119">In the **Fields** page of the **Dataset Properties** dialog box, click **Add**, and then click **Calculated Field**.</span></span> <span data-ttu-id="2e72a-120">Une nouvelle ligne est ajoutée au bas de la grille.</span><span class="sxs-lookup"><span data-stu-id="2e72a-120">A new row is added to the bottom of the grid.</span></span>  
  
3.  <span data-ttu-id="2e72a-121">Dans la zone de texte **Nom du champ** , tapez le nom du champ.</span><span class="sxs-lookup"><span data-stu-id="2e72a-121">In the **Field Name** text bo, type the name for the field.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e72a-122">Les noms doivent être uniques dans le dataset.</span><span class="sxs-lookup"><span data-stu-id="2e72a-122">Names must be unique in the dataset.</span></span>  
  
4.  <span data-ttu-id="2e72a-123">Dans la zone de texte **Champ source** , tapez l'expression du champ.</span><span class="sxs-lookup"><span data-stu-id="2e72a-123">In the **Field Source** text box, type the expression for the field.</span></span> <span data-ttu-id="2e72a-124">Cliquez sur le bouton d’expression (**fx**) pour générer une expression.</span><span class="sxs-lookup"><span data-stu-id="2e72a-124">Click the expression (**fx**) button to build an expression.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2e72a-125">L'expression d'un champ calculé ne peut contenir ni agrégations, ni références à des éléments de rapport.</span><span class="sxs-lookup"><span data-stu-id="2e72a-125">The expression for a calculated field cannot contain aggregates or references to report items.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-edit-a-query-field-or-a-dataset-field"></a><span data-ttu-id="2e72a-126">Pour modifier un champ de requête ou un champ de dataset</span><span class="sxs-lookup"><span data-stu-id="2e72a-126">To edit a query field or a dataset field</span></span>  
  
1.  <span data-ttu-id="2e72a-127">Dans le volet des données de rapport, cliquez avec le bouton droit sur le champ, puis cliquez sur **Propriétés du champ**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-127">In the Report Data pane, right-click the field, and then click **Field Properties**.</span></span>  
  
2.  <span data-ttu-id="2e72a-128">Dans la page **Champs** de la boîte de dialogue **Propriétés du dataset** , cliquez sur un champ existant pour sélectionner la ligne.</span><span class="sxs-lookup"><span data-stu-id="2e72a-128">In the **Fields** page of the **Dataset Properties** dialog box, click an existing field to select the row.</span></span>  
  
3.  <span data-ttu-id="2e72a-129">Modifiez le nom ou la valeur du champ.</span><span class="sxs-lookup"><span data-stu-id="2e72a-129">Change the name of the field or the value of the field.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-query-field-or-a-calculated-field"></a><span data-ttu-id="2e72a-130">Pour supprimer un champ de requête ou un champ calculé</span><span class="sxs-lookup"><span data-stu-id="2e72a-130">To delete a query field or a calculated field</span></span>  
  
1.  <span data-ttu-id="2e72a-131">Dans le volet des données de rapport, développez le dataset pour afficher la collection de champs.</span><span class="sxs-lookup"><span data-stu-id="2e72a-131">In the Report Data pane, expand the dataset to display the field collection.</span></span>  
  
2.  <span data-ttu-id="2e72a-132">Cliquez avec le bouton droit sur le champ à supprimer, puis sélectionnez **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-132">Right-click the field you want to remove, and then click **Delete**.</span></span>  
  
### <a name="to-refresh-the-field-collection-in-the-report-data-pane-for-a-shared-dataset"></a><span data-ttu-id="2e72a-133">Pour actualiser la collection de champs dans le volet des données de rapport d'un dataset partagé</span><span class="sxs-lookup"><span data-stu-id="2e72a-133">To refresh the field collection in the Report Data Pane for a shared dataset</span></span>  
  
1.  <span data-ttu-id="2e72a-134">Dans le volet des données de rapport, cliquez avec le bouton droit sur le dataset, puis cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-134">In the Report Data pane, right-click the dataset, and then click **Query**.</span></span>  
  
2.  <span data-ttu-id="2e72a-135">Cliquez sur **Actualiser les champs**.</span><span class="sxs-lookup"><span data-stu-id="2e72a-135">Click **Refresh Fields**.</span></span>  
  
     <span data-ttu-id="2e72a-136">Sur le serveur de rapports, la requête du dataset partagé exécute et retourne la collection de champs actuelle.</span><span class="sxs-lookup"><span data-stu-id="2e72a-136">On the report server, the shared dataset query runs and returns the current field collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e72a-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e72a-137">See Also</span></span>  
 <span data-ttu-id="2e72a-138">[Collection de champs de dataset &#40;Générateur de rapports et SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e72a-138">[Dataset Fields Collection &#40;Report Builder and SSRS&#41;](dataset-fields-collection-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e72a-139">[Ajouter des données à un rapport &#40;Générateur de rapports et SSRS&#41;](report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e72a-139">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="2e72a-140">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="2e72a-140">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="2e72a-141">[Concepteurs de requêtes Reporting Services](../reporting-services-query-designers.md) </span><span class="sxs-lookup"><span data-stu-id="2e72a-141">[Reporting Services Query Designers](../reporting-services-query-designers.md) </span></span>  
 [<span data-ttu-id="2e72a-142">Concepteurs de requêtes &#40;Générateur de rapports&#41;</span><span class="sxs-lookup"><span data-stu-id="2e72a-142">Query Designers &#40;Report Builder&#41;</span></span>](../query-designers-report-builder.md)  
  
  
