---
title: Sélectionner des tables et des vues (flux de données) (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviewsdf.f1
ms.assetid: 6c4fafe0-e02e-47d1-b8bc-e70e872690af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46c317ecf2a87adcde264e8d6d7e822eb833b8b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604170"
---
# <a name="select-tables-and-views-data-feeds-ssas"></a><span data-ttu-id="75f50-102">Sélectionner des tables et des vues (flux de données) (SSAS)</span><span class="sxs-lookup"><span data-stu-id="75f50-102">Select Tables and Views (Data Feeds) (SSAS)</span></span>
  <span data-ttu-id="75f50-103">Cette page de **l’Assistant Importation de table** vous permet de sélectionner les tables et les vues à partir desquelles vous voulez importer des données.</span><span class="sxs-lookup"><span data-stu-id="75f50-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="75f50-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="75f50-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="75f50-105">L'apparence des tables et des vues dans cette page ne garantit pas que l'importation réussira.</span><span class="sxs-lookup"><span data-stu-id="75f50-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="75f50-106">Si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée, l'importation échouera.</span><span class="sxs-lookup"><span data-stu-id="75f50-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="75f50-107">Pour les sources de données qui utilisent l'Authentification Windows, les informations d'identification de l'utilisateur actuel sont utilisées pour extraire les tables et les vues dans la boîte de dialogue Sélectionner des tables et des vues.</span><span class="sxs-lookup"><span data-stu-id="75f50-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="75f50-108">Pour d'autres sources de données, les informations d'identification fournies dans la chaîne de connexion sont utilisées pour extraire les données.</span><span class="sxs-lookup"><span data-stu-id="75f50-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="75f50-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="75f50-109">UI element list</span></span>  
 <span data-ttu-id="75f50-110">**URL du flux de données**</span><span class="sxs-lookup"><span data-stu-id="75f50-110">**Data feed URL**</span></span>  
 <span data-ttu-id="75f50-111">Affiche l'URL pour le flux de données que vous avez sélectionné.</span><span class="sxs-lookup"><span data-stu-id="75f50-111">Displays the URL for the data feed that you selected.</span></span>  
  
 <span data-ttu-id="75f50-112">**Tables et vues**</span><span class="sxs-lookup"><span data-stu-id="75f50-112">**Tables and views**</span></span>  
 <span data-ttu-id="75f50-113">Affiche la liste des tables et des vues dans la source des données.</span><span class="sxs-lookup"><span data-stu-id="75f50-113">Lists the tables and views in the data feed.</span></span> <span data-ttu-id="75f50-114">Activez la case à cocher en regard de chaque table et vue que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="75f50-114">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="75f50-115">**Table source**</span><span class="sxs-lookup"><span data-stu-id="75f50-115">**Source Table**</span></span>  
 <span data-ttu-id="75f50-116">Spécifie le nom de la table source en fonction du type de source de données.</span><span class="sxs-lookup"><span data-stu-id="75f50-116">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="75f50-117">**Nom convivial**</span><span class="sxs-lookup"><span data-stu-id="75f50-117">**Friendly Name**</span></span>  
 <span data-ttu-id="75f50-118">Spécifie le nom convivial de la table source.</span><span class="sxs-lookup"><span data-stu-id="75f50-118">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="75f50-119">Par défaut, la colonne affiche le nom de la table source qui apparaît dans la colonne **Table source** .</span><span class="sxs-lookup"><span data-stu-id="75f50-119">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span>  
  
 <span data-ttu-id="75f50-120">**Détails du filtre**</span><span class="sxs-lookup"><span data-stu-id="75f50-120">**Filter Details**</span></span>  
 <span data-ttu-id="75f50-121">Affiche le filtre d’importation de données dans la boîte de dialogue **Détails du filtre** quand un filtre a été appliqué aux données importées.</span><span class="sxs-lookup"><span data-stu-id="75f50-121">Displays the data import filter in the **Filter Details** dialog box, when a filter has been applied to the data that is being imported.</span></span> <span data-ttu-id="75f50-122">Pour plus d’informations, consultez [Détails du filtre &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="75f50-122">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="75f50-123">**Afficher un aperçu et filtrer**</span><span class="sxs-lookup"><span data-stu-id="75f50-123">**Preview and Filter**</span></span>  
 <span data-ttu-id="75f50-124">Affiche la boîte de dialogue **Aperçu de la table sélectionnée** qui permet d’appliquer un filtre aux données importées.</span><span class="sxs-lookup"><span data-stu-id="75f50-124">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="75f50-125">Pour plus d’informations, consultez [Aperçu de la table sélectionnée &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="75f50-125">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="75f50-126">**Sélectionner les tables associées**</span><span class="sxs-lookup"><span data-stu-id="75f50-126">**Select Related Tables**</span></span>  
 <span data-ttu-id="75f50-127">Sélectionnez les tables associées aux tables et aux vues que vous avez sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="75f50-127">Select tables that are related to the tables and views that you have selected.</span></span>  
  
  
