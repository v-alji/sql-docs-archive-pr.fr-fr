---
title: Ajouter, modifier ou supprimer un paramètre de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d44a8e0a-10cf-4502-9391-09743ffc9bad
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 231cd51d7ed0a481f004b39a2e8819df3fc33748
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605217"
---
# <a name="add-change-or-delete-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="b5703-102">Ajouter, modifier ou supprimer un paramètre de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="b5703-102">Add, Change, or Delete a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="b5703-103">Un paramètre de rapport permet de choisir les données du rapport, d'interconnecter les rapports associés et de varier la présentation du rapport concerné.</span><span class="sxs-lookup"><span data-stu-id="b5703-103">A report parameter provides a way to choose report data, connect related reports together, and vary the report presentation.</span></span> <span data-ttu-id="b5703-104">Vous pouvez fournir une valeur par défaut et une liste de valeurs disponibles. De son côté, l'utilisateur peut modifier la sélection.</span><span class="sxs-lookup"><span data-stu-id="b5703-104">You can provide a default value and a list of available values, and the user can change the selection.</span></span>  
  
 <span data-ttu-id="b5703-105">Après la publication d'un rapport, vous pouvez modifier les valeurs par défaut, les valeurs disponibles et d'autres propriétés d'un paramètre de rapport sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b5703-105">After you publish a report, you can change the default values, the available values, and other properties for a report parameter on the report server.</span></span> <span data-ttu-id="b5703-106">Vous pouvez fournir plusieurs jeux de valeurs de paramètre par défaut en créant des rapports liés.</span><span class="sxs-lookup"><span data-stu-id="b5703-106">You can provide multiple sets of default parameter values by creating linked reports.</span></span> <span data-ttu-id="b5703-107">Pour plus d'informations, consultez la rubrique « Définition des propriétés de paramètres d'un rapport publié » dans la documentation [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] de la documentation en ligne [SQL Server](https://go.microsoft.com/fwlink/?linkid=120955).</span><span class="sxs-lookup"><span data-stu-id="b5703-107">For more information, see "Setting Parameter Properties for a Published Report" in the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] documentation in [SQL Server Books Online](https://go.microsoft.com/fwlink/?linkid=120955).</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-add-or-edit-a-report-parameter"></a><span data-ttu-id="b5703-108">Pour ajouter ou modifier un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="b5703-108">To add or edit a report parameter</span></span>  
  
1.  <span data-ttu-id="b5703-109">Dans le volet **Données du rapport** , cliquez avec le bouton droit sur le nœud **Paramètres** , puis cliquez sur **Ajouter un paramètre**.</span><span class="sxs-lookup"><span data-stu-id="b5703-109">In the **Report Data** pane, right-click the **Parameters** node and click **Add Parameter**.</span></span> <span data-ttu-id="b5703-110">La boîte de dialogue **Propriétés du paramètre de rapport** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="b5703-110">The **Report Parameter Properties** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="b5703-111">Dans **Nom**, tapez le nom du paramètre ou acceptez le nom par défaut.</span><span class="sxs-lookup"><span data-stu-id="b5703-111">In **Name**, type the name of the parameter or accept the default name.</span></span>  
  
3.  <span data-ttu-id="b5703-112">Dans **Demander**, tapez le texte à afficher en regard de la zone de texte du paramètre lorsque l'utilisateur exécute le rapport.</span><span class="sxs-lookup"><span data-stu-id="b5703-112">In **Prompt**, type the text that appears next to the parameter text box when the user runs the report.</span></span>  
  
4.  <span data-ttu-id="b5703-113">Dans **Type de données**, sélectionnez le type de données pour la valeur du paramètre.</span><span class="sxs-lookup"><span data-stu-id="b5703-113">In **Data type**, select the data type for the parameter value.</span></span>  
  
5.  <span data-ttu-id="b5703-114">Si le paramètre peut contenir une valeur vide, sélectionnez **Autoriser une valeur vide**.</span><span class="sxs-lookup"><span data-stu-id="b5703-114">If the parameter can contain a blank value, select **Allow blank value**.</span></span>  
  
6.  <span data-ttu-id="b5703-115">Si le paramètre peut contenir une valeur Null, sélectionnez **Autoriser les valeurs de type NULL**.</span><span class="sxs-lookup"><span data-stu-id="b5703-115">If the parameter can contain a null value, select **Allow null value**.</span></span>  
  
7.  <span data-ttu-id="b5703-116">Pour autoriser un utilisateur à sélectionner plusieurs valeurs pour le paramètre, sélectionnez **Autoriser les valeurs multiples**.</span><span class="sxs-lookup"><span data-stu-id="b5703-116">To allow a user to select more than one value for the parameter, select **Allow multiple values**.</span></span>  
  
8.  <span data-ttu-id="b5703-117">Définissez l'option de visibilité.</span><span class="sxs-lookup"><span data-stu-id="b5703-117">Set the visibility option.</span></span>  
  
    -   <span data-ttu-id="b5703-118">Pour afficher le paramètre dans la barre d'outils en haut du rapport, sélectionnez **Visible**.</span><span class="sxs-lookup"><span data-stu-id="b5703-118">To show the parameter on the toolbar at the top of the report, select **Visible**.</span></span>  
  
    -   <span data-ttu-id="b5703-119">Pour masquer le paramètre afin qu'il n'affiche pas dans la barre d'outils, sélectionnez **Masqué**.</span><span class="sxs-lookup"><span data-stu-id="b5703-119">To hide the parameter so that it does not display on the toolbar, select **Hidden**.</span></span>  
  
    -   <span data-ttu-id="b5703-120">Pour masquer le paramètre et empêcher sa modification sur le serveur de rapports une fois le rapport publié, sélectionnez **Interne**.</span><span class="sxs-lookup"><span data-stu-id="b5703-120">To hide the parameter and protect it from being modified on the report server after the report is published, select **Internal**.</span></span> <span data-ttu-id="b5703-121">Le paramètre de rapport ne peut alors être affiché que dans la définition du rapport.</span><span class="sxs-lookup"><span data-stu-id="b5703-121">The report parameter can then only be viewed in the report definition.</span></span> <span data-ttu-id="b5703-122">Pour cette option, vous devez définir une valeur par défaut ou autoriser le paramètre à accepter une valeur nulle.</span><span class="sxs-lookup"><span data-stu-id="b5703-122">For this option, you must set a default value or allow the parameter to accept a null value.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-delete-a-report-parameter"></a><span data-ttu-id="b5703-123">Pour supprimer un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="b5703-123">To delete a report parameter</span></span>  
  
1.  <span data-ttu-id="b5703-124">Dans le volet **Données du rapport** , développez le nœud **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="b5703-124">In the **Report Data** pane, expand the **Parameters** node.</span></span>  
  
2.  <span data-ttu-id="b5703-125">Cliquez avec le bouton droit sur le paramètre de rapport, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="b5703-125">Right-click the report parameter and click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5703-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5703-126">See Also</span></span>  
 <span data-ttu-id="b5703-127">[Ajouter, modifier ou supprimer les valeurs disponibles d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-127">[Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="b5703-128">[Ajoutez, modifiez ou supprimez les valeurs par défaut d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-128">[Add, Change, or Delete Default Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-default-values-for-a-report-parameter.md) </span></span>  
 <span data-ttu-id="b5703-129">[Modifier l’ordre d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-129">[Change the Order of a Report Parameter &#40;Report Builder and SSRS&#41;](change-the-order-of-a-report-parameter-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b5703-130">[Paramètres de rapport &#40;Générateur de rapports et de Concepteur de rapports&#41;](report-parameters-report-builder-and-report-designer.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-130">[Report Parameters &#40;Report Builder and Report Designer&#41;](report-parameters-report-builder-and-report-designer.md) </span></span>  
 <span data-ttu-id="b5703-131">[Aide Générateur de rapports pour les boîtes de dialogue, les volets et les assistants](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-131">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 <span data-ttu-id="b5703-132">[Ajouter des paramètres en cascade à un rapport &#40;Générateur de rapports et SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-132">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="b5703-133">[Didacticiel : ajouter un paramètre à votre rapport &#40;Générateur de rapports&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-133">[Tutorial: Add a Parameter to Your Report &#40;Report Builder&#41;](../tutorial-add-a-parameter-to-your-report-report-builder.md) </span></span>  
 <span data-ttu-id="b5703-134">[Didacticiels &#40;Générateur de rapports&#41;](../report-builder-tutorials.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-134">[Tutorials &#40;Report Builder&#41;](../report-builder-tutorials.md) </span></span>  
 <span data-ttu-id="b5703-135">[Ajouter des filtres de datasets, des filtres de régions de données et des filtres de groupe &#40;Générateur de rapports et SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-135">[Add Dataset Filters, Data Region Filters, and Group Filters &#40;Report Builder and SSRS&#41;](add-dataset-filters-data-region-filters-and-group-filters.md) </span></span>  
 <span data-ttu-id="b5703-136">[La collection Parameters fait référence &#40;Générateur de rapports et SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="b5703-136">[Parameters Collection References &#40;Report Builder and SSRS&#41;](built-in-collections-parameters-collection-references-report-builder.md) </span></span>  
 [<span data-ttu-id="b5703-137">Ajouter un paramètre à valeurs multiples sur un rapport</span><span class="sxs-lookup"><span data-stu-id="b5703-137">Add a multi-value parameter to a Report</span></span>](add-a-multi-value-parameter-to-a-report.md)  
  
  
