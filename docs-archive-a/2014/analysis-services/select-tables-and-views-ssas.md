---
title: Sélectionner des tables et des vues (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.seltablesviews.f1
ms.assetid: 5e8121cc-03f0-4168-98cf-63c5c032bb0b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 891da51478670122f5dbce8fdd7be55c98c898c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706835"
---
# <a name="select-tables-and-views-ssas"></a><span data-ttu-id="3aeb9-102">Sélectionner des tables et des vues (SSAS)</span><span class="sxs-lookup"><span data-stu-id="3aeb9-102">Select Tables and Views (SSAS)</span></span>
  <span data-ttu-id="3aeb9-103">Cette page de **l’Assistant Importation de table** vous permet de sélectionner les tables et les vues à partir desquelles vous voulez importer des données.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-103">This page of the **Table Import Wizard** enables you to select the tables and views that you want to import data from.</span></span> <span data-ttu-id="3aeb9-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="3aeb9-105">L'apparence des tables et des vues dans cette page ne garantit pas que l'importation réussira.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-105">The appearance of tables and views on this page does not guarantee that import will succeed.</span></span> <span data-ttu-id="3aeb9-106">Si l'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée, l'importation échouera.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-106">If the user specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
 <span data-ttu-id="3aeb9-107">Pour les sources de données qui utilisent l'Authentification Windows, les informations d'identification de l'utilisateur actuel sont utilisées pour extraire les tables et les vues dans la boîte de dialogue Sélectionner des tables et des vues.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the tables and views in the Select Tables and Views dialog.</span></span> <span data-ttu-id="3aeb9-108">Pour d'autres sources de données, les informations d'identification fournies dans la chaîne de connexion sont utilisées pour extraire les données.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="3aeb9-109">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="3aeb9-109">UI element list</span></span>  
 <span data-ttu-id="3aeb9-110">**Serveur**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-110">**Server**</span></span>  
 <span data-ttu-id="3aeb9-111">Affiche le serveur auquel vous êtes connecté.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-111">Displays the server that you are connected to.</span></span>  
  
 <span data-ttu-id="3aeb9-112">**Sauvegarde de la base de données**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-112">**Database**</span></span>  
 <span data-ttu-id="3aeb9-113">Affiche la base de données que vous avez sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-113">Displays the database that you selected.</span></span>  
  
 <span data-ttu-id="3aeb9-114">**Tables et vues**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-114">**Tables and Views**</span></span>  
 <span data-ttu-id="3aeb9-115">Répertorie les tables et vues contenues dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-115">Lists the tables and views in the database.</span></span> <span data-ttu-id="3aeb9-116">Activez la case à cocher en regard de chaque table et vue que vous souhaitez importer.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-116">Select the checkbox beside each table and view that you want to import.</span></span>  
  
 <span data-ttu-id="3aeb9-117">**Table source**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-117">**Source Table**</span></span>  
 <span data-ttu-id="3aeb9-118">Spécifie le nom de la table source en fonction du type de source de données.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-118">Specifies the name of the source table based on the type of data source.</span></span>  
  
 <span data-ttu-id="3aeb9-119">**Schéma**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-119">**Schema**</span></span>  
 <span data-ttu-id="3aeb9-120">Spécifie le schéma contenant la table source.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-120">Specifies the schema in which the source table is contained.</span></span> <span data-ttu-id="3aeb9-121">Selon le type de base de données, un schéma fonctionne comme un conteneur pour d'autres objets, tels que des tables, et peut également indiquer la propriété de ces objets.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-121">Depending on the type of database, a schema functions as a container for other objects, such as tables, and can also indicate ownership of those objects.</span></span>  
  
 <span data-ttu-id="3aeb9-122">**Nom convivial**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-122">**Friendly Name**</span></span>  
 <span data-ttu-id="3aeb9-123">Spécifie le nom convivial de la table source.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-123">Specifies the friendly name of the source table.</span></span> <span data-ttu-id="3aeb9-124">Par défaut, la colonne affiche le nom de la table source qui apparaît dans la colonne **Table source** .</span><span class="sxs-lookup"><span data-stu-id="3aeb9-124">By default, the column displays the name of the source table that appears in the **Source Table** column.</span></span> <span data-ttu-id="3aeb9-125">Modifiez le nom si vous souhaitez utiliser un nom différent de celui utilisé dans la base de données source.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-125">Change the name if you want to use a different name than the name used in the source database.</span></span>  
  
 <span data-ttu-id="3aeb9-126">**Détails du filtre**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-126">**Filter Details**</span></span>  
 <span data-ttu-id="3aeb9-127">Quand un filtre a été appliqué aux données importées, affiche le filtre d’importation de données dans la boîte de dialogue **Détails du filtre**.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-127">When a filter has been applied to the data that is being imported, displays the data import filter in the **Filter Details** dialog box.</span></span> <span data-ttu-id="3aeb9-128">Pour plus d’informations, consultez [Détails du filtre &#40;SSAS&#41;](filter-details-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="3aeb9-128">For more information, see [Filter Details &#40;SSAS&#41;](filter-details-ssas.md).</span></span>  
  
 <span data-ttu-id="3aeb9-129">**Afficher un aperçu et filtrer**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-129">**Preview and Filter**</span></span>  
 <span data-ttu-id="3aeb9-130">Affiche la boîte de dialogue **Aperçu de la table sélectionnée** qui permet d’appliquer un filtre aux données importées.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-130">Displays the **Preview Selected Table** dialog box that is used to apply a filter to the data that is being imported.</span></span> <span data-ttu-id="3aeb9-131">Pour plus d’informations, consultez [Aperçu de la table sélectionnée &#40;SSAS&#41;](preview-selected-table-ssas.md).</span><span class="sxs-lookup"><span data-stu-id="3aeb9-131">For more information, see [Preview Selected Table &#40;SSAS&#41;](preview-selected-table-ssas.md).</span></span>  
  
 <span data-ttu-id="3aeb9-132">**Sélectionner les tables associées**</span><span class="sxs-lookup"><span data-stu-id="3aeb9-132">**Select Related Tables**</span></span>  
 <span data-ttu-id="3aeb9-133">Sélectionne pour l'importation les tables et les vues associées aux tables et aux vues que vous avez déjà sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="3aeb9-133">Selects for import those tables and views that are related to the tables and views that you have already selected.</span></span>  
  
  
