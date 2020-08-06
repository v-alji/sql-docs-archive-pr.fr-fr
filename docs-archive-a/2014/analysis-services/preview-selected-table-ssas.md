---
title: Aperçu de la table sélectionnée (SSAS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.previewselecttable.f1
ms.assetid: b6b34b5a-43b3-4a75-9f3b-b2ad1084b1b6
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25eb4d4424223449052ab1f65b41cf270da81fb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708736"
---
# <a name="preview-selected-table-ssas"></a><span data-ttu-id="c7b13-102">Aperçu de la table sélectionnée (SSAS)</span><span class="sxs-lookup"><span data-stu-id="c7b13-102">Preview Selected Table (SSAS)</span></span>
  <span data-ttu-id="c7b13-103">Cette page de l' **Assistant Importation de table** vous permet d'afficher un aperçu des données dans la table sélectionnée, pour sélectionner les colonnes à inclure dans l'importation de données et pour filtrer des données dans les colonnes sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="c7b13-103">This page of the **Table Import Wizard** enables you to preview the data in the selected table, to select the columns to include in the data import, and to filter data in the selected columns.</span></span> <span data-ttu-id="c7b13-104">Pour accéder à l'Assistant [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], dans le menu **Modèle** , cliquez sur **Importer à partir de la source de données**.</span><span class="sxs-lookup"><span data-stu-id="c7b13-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="c7b13-105">Les lignes de la table ne sont pas toutes affichées.</span><span class="sxs-lookup"><span data-stu-id="c7b13-105">Not all the rows in the table are displayed.</span></span> <span data-ttu-id="c7b13-106">Toutefois, les filtres que vous définissez sont appliqués à toutes les données de la table pendant l'importation.</span><span class="sxs-lookup"><span data-stu-id="c7b13-106">However, the filters that you set will be applied to all of the data in the table during import.</span></span>  
  
 <span data-ttu-id="c7b13-107">Pour les sources de données qui utilisent l'Authentification Windows, les informations d'identification de l'utilisateur actuel sont utilisées pour extraire les données affichées dans la boîte de dialogue Afficher un aperçu et filtrer.</span><span class="sxs-lookup"><span data-stu-id="c7b13-107">For data sources using Windows authentication, the credentials of the current user are used to fetch the data displayed in the Preview and Filter dialog.</span></span> <span data-ttu-id="c7b13-108">Pour d'autres sources de données, les informations d'identification fournies dans la chaîne de connexion sont utilisées pour extraire les données.</span><span class="sxs-lookup"><span data-stu-id="c7b13-108">For other data sources, the credentials supplied in the connection string are used to fetch the data.</span></span>  
  
 <span data-ttu-id="c7b13-109">L'apparence des données dans cette page ne garantit pas que l'importation réussira.</span><span class="sxs-lookup"><span data-stu-id="c7b13-109">The appearance of data on this page does not guarantee import will succeed.</span></span> <span data-ttu-id="c7b13-110">Si le nom d'utilisateur spécifié dans la page Informations d'emprunt d'identité n'a pas de privilèges suffisants pour lire la base de données sélectionnée, l'importation échouera.</span><span class="sxs-lookup"><span data-stu-id="c7b13-110">If the user name specified in the Impersonation Information page does not have sufficient privileges to read from the selected database, import will fail.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="c7b13-111">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="c7b13-111">UI element list</span></span>  
 <span data-ttu-id="c7b13-112">**Case à cocher dans l'en-tête de colonne**</span><span class="sxs-lookup"><span data-stu-id="c7b13-112">**Checkbox in the column header**</span></span>  
 <span data-ttu-id="c7b13-113">Activez la case à cocher pour inclure la colonne lors de l'importation des données.</span><span class="sxs-lookup"><span data-stu-id="c7b13-113">Select the checkbox to include the column in the data import.</span></span> <span data-ttu-id="c7b13-114">Désactivez la case à cocher pour supprimer la colonne lors de l'importation de données.</span><span class="sxs-lookup"><span data-stu-id="c7b13-114">Clear the checkbox to remove the column from the data import.</span></span>  
  
 <span data-ttu-id="c7b13-115">**Bouton Flèche vers le bas dans l'en-tête de colonne**</span><span class="sxs-lookup"><span data-stu-id="c7b13-115">**Down-arrow button in the column header**</span></span>  
 <span data-ttu-id="c7b13-116">Filtrez les données dans la colonne.</span><span class="sxs-lookup"><span data-stu-id="c7b13-116">Filter data in the column.</span></span>  
  
 <span data-ttu-id="c7b13-117">**Désactiver les filtres de lignes**</span><span class="sxs-lookup"><span data-stu-id="c7b13-117">**Clear Row Filters**</span></span>  
 <span data-ttu-id="c7b13-118">Supprimez tous les filtres appliqués aux données dans les colonnes.</span><span class="sxs-lookup"><span data-stu-id="c7b13-118">Remove all filters that were applied to the data in the columns.</span></span>  
  
  
