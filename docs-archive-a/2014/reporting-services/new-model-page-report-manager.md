---
title: Page nouveau modèle (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 27d5bf66-b0e7-489e-a830-ffe2ec8e5350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed591108585b494ebb4498c1a0ab3e782693a45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612192"
---
# <a name="new-model-page-report-manager"></a><span data-ttu-id="b49e4-102">Page Nouveau modèle (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="b49e4-102">New Model Page (Report Manager)</span></span>
  <span data-ttu-id="b49e4-103">Utilisez cette page pour générer un modèle de rapport par défaut à partir d'une source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="b49e4-103">Use this page to generate a default report model from a shared data source.</span></span> <span data-ttu-id="b49e4-104">Vous ne pouvez générer des modèles de rapport qu'à partir de sources de données multidimensionnelles [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] , de sources de données relationnelles [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et de sources de données relationnelles Oracle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-104">You can only generate report models from [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional data sources, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relational data sources, and Oracle relational data sources.</span></span>  
  
 <span data-ttu-id="b49e4-105">Les modèles que vous générez dans le Gestionnaire de rapports sont basés sur le schéma de la source de données partagée.</span><span class="sxs-lookup"><span data-stu-id="b49e4-105">Models that you generate in Report Manager are based on the schema of the shared data source.</span></span> <span data-ttu-id="b49e4-106">Les entités, dossiers et champs sont créés pour toutes les tables et colonnes dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="b49e4-106">Entities, folders, and fields are created for all tables and columns in the data source.</span></span> <span data-ttu-id="b49e4-107">Vous ne pouvez pas exclure d'éléments, ni définir d'options qui déterminent la façon dont le modèle est généré.</span><span class="sxs-lookup"><span data-stu-id="b49e4-107">You cannot exclude items, nor can you set options that determine how the model is generated.</span></span> <span data-ttu-id="b49e4-108">Si vous souhaitez personnaliser ou affiner un modèle, vous devez plutôt utiliser le Générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="b49e4-108">If you want to customize or refine a model, you must use Model Designer instead.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="b49e4-109">Navigation</span><span class="sxs-lookup"><span data-stu-id="b49e4-109">Navigation</span></span>  
 <span data-ttu-id="b49e4-110">Utilisez la procédure suivante pour naviguer jusqu'à cet emplacement dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b49e4-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-model-page"></a><span data-ttu-id="b49e4-111">Pour ouvrir la page Nouveau modèle</span><span class="sxs-lookup"><span data-stu-id="b49e4-111">To open the New Model page</span></span>  
  
1.  <span data-ttu-id="b49e4-112">Ouvrez le Gestionnaire de rapports et recherchez la source de données partagée depuis laquelle vous souhaitez générer un modèle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-112">Open Report Manager, and locate the shared data source from which you want to generate a model.</span></span>  
  
2.  <span data-ttu-id="b49e4-113">Pointez sur la source de données et cliquez sur la flèche déroulante.</span><span class="sxs-lookup"><span data-stu-id="b49e4-113">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="b49e4-114">Dans le menu déroulant, effectuez l'une des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="b49e4-114">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="b49e4-115">Cliquez sur **Générer le modèle de rapport** pour ouvrir la page Nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-115">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="b49e4-116">Cliquez sur **Gérer** pour ouvrir la page des propriétés générales du rapport.</span><span class="sxs-lookup"><span data-stu-id="b49e4-116">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="b49e4-117">Cliquez ensuite sur **Générer le modèle** pour ouvrir la page Nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-117">Then click **Generate Model** to open the New Model page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="b49e4-118">Options</span><span class="sxs-lookup"><span data-stu-id="b49e4-118">Options</span></span>  
 <span data-ttu-id="b49e4-119">**Nom**</span><span class="sxs-lookup"><span data-stu-id="b49e4-119">**Name**</span></span>  
 <span data-ttu-id="b49e4-120">Spécifie le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-120">Specifies the name of the model.</span></span> <span data-ttu-id="b49e4-121">Le nom doit contenir un caractère alphanumérique au minimum.</span><span class="sxs-lookup"><span data-stu-id="b49e4-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="b49e4-122">Il peut également comporter des espaces et quelques symboles.</span><span class="sxs-lookup"><span data-stu-id="b49e4-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="b49e4-123">N'utilisez pas les caractères suivants dans le nom :</span><span class="sxs-lookup"><span data-stu-id="b49e4-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="b49e4-124">; ?</span><span class="sxs-lookup"><span data-stu-id="b49e4-124">; ?</span></span> <span data-ttu-id="b49e4-125">: \@ & = +, $/\* \< > | " /</span><span class="sxs-lookup"><span data-stu-id="b49e4-125">: \@ & = + , $ / \* \< > | " /</span></span>  
  
 <span data-ttu-id="b49e4-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="b49e4-126">**Description**</span></span>  
 <span data-ttu-id="b49e4-127">Affiche une description du modèle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-127">Shows a description of the model.</span></span> <span data-ttu-id="b49e4-128">Les utilisateurs qui consultent cet élément par le biais du Gestionnaire de rapports affichent cette description en parcourant l'arborescence des dossiers.</span><span class="sxs-lookup"><span data-stu-id="b49e4-128">Users who view this item through Report Manager see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="b49e4-129">**Modifier l'emplacement**</span><span class="sxs-lookup"><span data-stu-id="b49e4-129">**Change Location**</span></span>  
 <span data-ttu-id="b49e4-130">Affiche l'emplacement du dossier pour le nouveau modèle.</span><span class="sxs-lookup"><span data-stu-id="b49e4-130">Shows the folder location for the new model.</span></span> <span data-ttu-id="b49e4-131">Vous pouvez cliquer sur le bouton **Modifier l'emplacement** pour sélectionner un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="b49e4-131">You can click the **Change Location** button to select a different location.</span></span>  
  
  
