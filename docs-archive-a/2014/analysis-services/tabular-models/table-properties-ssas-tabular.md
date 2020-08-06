---
title: Propriétés de la table (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.tableprop.f1
ms.assetid: 16d3347b-7e43-4a6b-9956-fdd6ede092e6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9613609c42de8fd3a4aab7aec3208dfe3d31be4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706787"
---
# <a name="table-properties-ssas-tabular"></a><span data-ttu-id="c5e4d-102">Propriétés de table (SSAS Tabular)</span><span class="sxs-lookup"><span data-stu-id="c5e4d-102">Table Properties (SSAS Tabular)</span></span>
  <span data-ttu-id="c5e4d-103">Cette rubrique décrit les propriétés de table d'un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-103">This topic describes tabular model table properties.</span></span> <span data-ttu-id="c5e4d-104">Les propriétés décrites ici sont différentes de celles figurant dans la boîte de dialogue Modifier les propriétés de la table, lesquelles définissent les colonnes importées de la source.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-104">The properties described here are different from those in the Edit Table Properties dialog box, which define which columns from the source are imported.</span></span>  
  
 <span data-ttu-id="c5e4d-105">Sections de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="c5e4d-105">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="c5e4d-106">Propriétés de la table</span><span class="sxs-lookup"><span data-stu-id="c5e4d-106">Table Properties</span></span>](#bkmk_properties)  
  
-   [<span data-ttu-id="c5e4d-107">Pour configurer les paramètres de propriété de table</span><span class="sxs-lookup"><span data-stu-id="c5e4d-107">To configure table property settings</span></span>](#bkmk_config_prop)  
  
##  <a name="table-properties"></a><a name="bkmk_properties"></a><span data-ttu-id="c5e4d-108">Propriétés de la table</span><span class="sxs-lookup"><span data-stu-id="c5e4d-108">Table Properties</span></span>  
 <span data-ttu-id="c5e4d-109">**De base**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-109">**Basic**</span></span>  
  
|<span data-ttu-id="c5e4d-110">Propriété</span><span class="sxs-lookup"><span data-stu-id="c5e4d-110">Property</span></span>|<span data-ttu-id="c5e4d-111">Paramètre par défaut</span><span class="sxs-lookup"><span data-stu-id="c5e4d-111">Default Setting</span></span>|<span data-ttu-id="c5e4d-112">Description</span><span class="sxs-lookup"><span data-stu-id="c5e4d-112">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="c5e4d-113">**Nom de connexion**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-113">**Connection Name**</span></span>|\<connection name>|<span data-ttu-id="c5e4d-114">Nom de la connexion à la source de données de la table.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-114">The name of the connection to the table's data source.</span></span><br /><br /> <span data-ttu-id="c5e4d-115">Pour modifier la connexion, cliquez sur le bouton.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-115">To edit the connection, click the button.</span></span>|  
|<span data-ttu-id="c5e4d-116">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-116">**Hidden**</span></span>|<span data-ttu-id="c5e4d-117">False</span><span class="sxs-lookup"><span data-stu-id="c5e4d-117">False</span></span>|<span data-ttu-id="c5e4d-118">Spécifie si la table est masquée dans les listes de champs de client de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-118">Specifies whether the table is hidden from reporting client field lists.</span></span>|  
|<span data-ttu-id="c5e4d-119">**Partitions**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-119">**Partitions**</span></span>||<span data-ttu-id="c5e4d-120">Les partitions de la table ne peuvent pas être affichées dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="c5e4d-120">Partitions for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="c5e4d-121">Pour afficher, créer ou modifier des partitions, cliquez sur le bouton pour ouvrir le Gestionnaire de partition.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-121">To view, create, or edit partitions, click the button to open the Partition Manager.</span></span>|  
|<span data-ttu-id="c5e4d-122">**Données sources**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-122">**Source Data**</span></span>||<span data-ttu-id="c5e4d-123">Les données sources de la table ne peuvent pas être affichées dans la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="c5e4d-123">Source data for the table cannot be displayed in the **Properties** window.</span></span> <span data-ttu-id="c5e4d-124">Pour afficher ou modifier les données sources, cliquez sur le bouton pour ouvrir la boîte de dialogue Modifier les propriétés de la table.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-124">To view or edit the source data, click the button to open the Edit Table Properties dialog box.</span></span>|  
|<span data-ttu-id="c5e4d-125">**Description de la table**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-125">**Table Description**</span></span>||<span data-ttu-id="c5e4d-126">Description textuelle de la table.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-126">A text description for the table.</span></span><br /><br /> <span data-ttu-id="c5e4d-127">Dans [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], si un utilisateur positionne le curseur sur cette table dans la liste des champs, la description apparaît sous la forme d'une info-bulle.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-127">In [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], if an end-user places the cursor over this table in the field list, the description appears as a tooltip.</span></span>|  
|<span data-ttu-id="c5e4d-128">**Nom du tableau**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-128">**Table Name**</span></span>|\<friendly name>|<span data-ttu-id="c5e4d-129">Spécifie le nom convivial de la table.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-129">Specifies the table's friendly name.</span></span> <span data-ttu-id="c5e4d-130">Le nom de la table peut être spécifié lorsqu'une table est importée à l'aide de l'Assistant Importation de table ou à tout moment après l'importation.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-130">The table name can be specified when a table is imported using the Table Import Wizard or at any time after import.</span></span> <span data-ttu-id="c5e4d-131">Le nom de la table dans le modèle peut être différent de la table associée à la source.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-131">The table name in the model can be different from the associated table at the source.</span></span> <span data-ttu-id="c5e4d-132">Le nom convivial de la table s'affiche dans la liste de champs de l'application cliente de création de rapports ainsi que dans la base de données model dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5e4d-132">The table friendly name appears in the reporting client application field list as well as in the model database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>|  
  
 <span data-ttu-id="c5e4d-133">**Propriétés de la création de rapports**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-133">**Reporting Properties**</span></span>  
  
 <span data-ttu-id="c5e4d-134">Pour obtenir des descriptions détaillées et des informations de configuration concernant les propriétés de génération de rapport, consultez [Propriétés de la génération de rapports Power View &#40;SSAS Tabulaire&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="c5e4d-134">For detailed descriptions and configuration information for reporting properties, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
|<span data-ttu-id="c5e4d-135">Propriété</span><span class="sxs-lookup"><span data-stu-id="c5e4d-135">Property</span></span>|<span data-ttu-id="c5e4d-136">Paramètre par défaut</span><span class="sxs-lookup"><span data-stu-id="c5e4d-136">Default Setting</span></span>|<span data-ttu-id="c5e4d-137">Description</span><span class="sxs-lookup"><span data-stu-id="c5e4d-137">Description</span></span>|  
|--------------|---------------------|-----------------|  
|<span data-ttu-id="c5e4d-138">**Ensemble de champs par défaut**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-138">**Default Field Set**</span></span>|||  
|<span data-ttu-id="c5e4d-139">Comportement de la table</span><span class="sxs-lookup"><span data-stu-id="c5e4d-139">Table Behavior</span></span>|||  
  
###  <a name="to-configure-table-property-settings"></a><a name="bkmk_config_prop"></a><span data-ttu-id="c5e4d-140">Pour configurer les paramètres de propriété de table</span><span class="sxs-lookup"><span data-stu-id="c5e4d-140">To configure table property settings</span></span>  
  
1.  <span data-ttu-id="c5e4d-141">Dans le concepteur de modèles, dans la vue de données, cliquez sur une table (onglet) ou, dans la vue du diagramme, cliquez sur un en-tête de table.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-141">In the model designer, in Data View, click a table (tab), or, in Diagram View, click a table header.</span></span>  
  
2.  <span data-ttu-id="c5e4d-142">Dans la fenêtre **Propriétés** , cliquez sur une propriété, puis tapez une valeur ou cliquez sur le bouton pour afficher des options de configuration supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-142">In the **Properties** window, click on a property, and then type a value or click the button for additional configuration options.</span></span>  
  
  
