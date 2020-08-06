---
title: Configurer l’ensemble de champs par défaut pour les rapports de Power View (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- ql12.asvs.bidtoolset.deffieldset.f1
ms.assetid: 6836b42f-28b8-4a98-a86d-2c3c109f0189
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66fbbacd0cc2efd7d379bcc8e68149551476869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696152"
---
# <a name="configure-default-field-set-for-power-view-reports-ssas-tabular"></a><span data-ttu-id="0cea9-102">Configurer un ensemble de champs par défaut pour les rapports Power View (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="0cea9-102">Configure Default Field Set for Power View Reports (SSAS Tabular)</span></span>
  <span data-ttu-id="0cea9-103">Un ensemble de champs par défaut est une liste prédéfinie de colonnes et de mesures qui sont automatiquement ajoutées à une zone de dessin de rapport [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] quand vous sélectionnez la table dans la liste des champs du rapport.</span><span class="sxs-lookup"><span data-stu-id="0cea9-103">A default field set is a predefined list of columns and measures that are automatically added to a [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] report canvas when the table is selected in the report field list.</span></span> <span data-ttu-id="0cea9-104">Les auteurs de modèles tabulaires peuvent créer un ensemble de champs par défaut pour éliminer les étapes redondantes pour les auteurs de rapport qui utilisent le modèle pour leurs rapports.</span><span class="sxs-lookup"><span data-stu-id="0cea9-104">Tabular model authors can create a default field set to eliminate redundant steps for report authors who use the model for their reports.</span></span> <span data-ttu-id="0cea9-105">Par exemple, si vous savez que la plupart des auteurs de rapport qui utilisent des coordonnées de clients souhaitent toujours voir un nom de contact, un numéro de téléphone principal, une adresse de messagerie et un nom de société, vous pouvez présélectionner ces colonnes afin qu'elles soient toujours ajoutées à la zone de dessin du rapport lorsque l'auteur clique sur la table Customer Contact.</span><span class="sxs-lookup"><span data-stu-id="0cea9-105">For example, if you know that most report authors who work with customer contact information always want to see a contact name, a primary phone number, an email address, and a company name, you can pre-select those columns so that they are always added to the report canvas when the author clicks the Customer Contact table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cea9-106">Un ensemble de champs par défaut s'applique uniquement à un modèle tabulaire utilisé comme modèle de données dans [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cea9-106">A default field set applies only to a tabular model used as a data model in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="0cea9-107">Les ensembles de champs par défaut ne sont pas pris en charge dans les rapports de tableau croisé dynamique Excel.</span><span class="sxs-lookup"><span data-stu-id="0cea9-107">Default field sets are not supported in Excel pivot reports.</span></span>  
  
## <a name="creating-a-default-field-set"></a><span data-ttu-id="0cea9-108">Création d'un ensemble de champs par défaut</span><span class="sxs-lookup"><span data-stu-id="0cea9-108">Creating a Default Field Set</span></span>  
 <span data-ttu-id="0cea9-109">Vous pouvez déterminer les champs, le cas échéant, qui sont inclus par défaut chaque fois qu’une table spécifique est sélectionnée dans [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cea9-109">You can determine which fields, if any, are included by default whenever a specific table is selected in [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)].</span></span> <span data-ttu-id="0cea9-110">Vous pouvez également déterminer l'ordre dans lequel les champs s'affichent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="0cea9-110">You can also determine the order in which fields appear in the list.</span></span> <span data-ttu-id="0cea9-111">Pour spécifier un ensemble de champs par défaut, vous définissez des propriétés de rapport dans le projet de modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="0cea9-111">To specify a default field set, you set report properties in the tabular model project.</span></span>  
  
#### <a name="to-add-a-default-field-set"></a><span data-ttu-id="0cea9-112">Pour ajouter un ensemble de champs par défaut</span><span class="sxs-lookup"><span data-stu-id="0cea9-112">To add a default field set</span></span>  
  
1.  <span data-ttu-id="0cea9-113">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur la table (l’onglet) pour laquelle vous configurez une liste de champs par défaut.</span><span class="sxs-lookup"><span data-stu-id="0cea9-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the table (tab) for which you are configuring a default field list.</span></span>  
  
2.  <span data-ttu-id="0cea9-114">Dans la fenêtre **Propriétés** , dans la propriété **Ensemble de champs par défaut** , cliquez sur **Cliquer pour modifier**.</span><span class="sxs-lookup"><span data-stu-id="0cea9-114">In the **Properties** window, in the **Default Field Set** property, click **Click to edit**.</span></span>  
  
3.  <span data-ttu-id="0cea9-115">Dans la boîte de dialogue Ensemble de champs par défaut, sélectionnez un ou plusieurs champs.</span><span class="sxs-lookup"><span data-stu-id="0cea9-115">In the Default Field Set dialog, select one or more fields.</span></span> <span data-ttu-id="0cea9-116">Vous pouvez choisir n'importe quel champ de la table, y compris des mesures.</span><span class="sxs-lookup"><span data-stu-id="0cea9-116">You can choose any field in the table, including measures.</span></span> <span data-ttu-id="0cea9-117">Maintenez la touche Maj enfoncée pour sélectionner une plage, ou la touche Ctrl pour sélectionner des champs individuels.</span><span class="sxs-lookup"><span data-stu-id="0cea9-117">Hold down the Shift key to select a range, or the Ctrl key to select individual fields.</span></span>  
  
4.  <span data-ttu-id="0cea9-118">Cliquez sur **Ajouter** pour les ajouter à l’ensemble de champs par défaut.</span><span class="sxs-lookup"><span data-stu-id="0cea9-118">Click **Add** to add them to the default field set.</span></span>  
  
5.  <span data-ttu-id="0cea9-119">Utilisez les boutons Monter et Descendre pour indiquer l'ordre dans la liste de champs.</span><span class="sxs-lookup"><span data-stu-id="0cea9-119">Use the Up and Down buttons to specify an order to the field list.</span></span> <span data-ttu-id="0cea9-120">Les champs sont ajoutés au rapport dans l'ordre défini pour l'ensemble de champs.</span><span class="sxs-lookup"><span data-stu-id="0cea9-120">Fields will be added to the report in the order defined for the field set.</span></span>  
  
6.  <span data-ttu-id="0cea9-121">Répétez ces étapes pour les autres tables de votre classeur.</span><span class="sxs-lookup"><span data-stu-id="0cea9-121">Repeat these steps for other tables in your workbook.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="0cea9-122">étape suivante</span><span class="sxs-lookup"><span data-stu-id="0cea9-122">Next Step</span></span>  
 <span data-ttu-id="0cea9-123">Après avoir créé un ensemble de champs par défaut, vous pouvez encore influencer l'expérience de conception de rapports en spécifiant les étiquettes par défaut, les images par défaut, le comportement de groupe par défaut, ou si les lignes qui contiennent la même valeur sont regroupées dans une ligne ou répertoriées individuellement.</span><span class="sxs-lookup"><span data-stu-id="0cea9-123">After you create a default field set, you can further influence the report design experience by specifying default labels, default images, default group behavior, or whether rows that contain the same value are grouped together in one row or listed individually.</span></span> <span data-ttu-id="0cea9-124">Pour plus d’informations, consultez [Configurer les propriétés de comportement de table pour les rapports Power View &#40;SSAS Tabulaire&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span><span class="sxs-lookup"><span data-stu-id="0cea9-124">For more information, see [Configure Table Behavior Properties for Power View Reports &#40;SSAS Tabular&#41;](power-view-configure-table-behavior-properties-for-reports.md).</span></span>  
  
  
