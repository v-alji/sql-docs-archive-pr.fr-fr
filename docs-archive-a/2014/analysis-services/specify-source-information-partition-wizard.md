---
title: Spécifier les informations sur la source (Assistant Partition) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.partitionwizard.specifydsvandfacttables.f1
ms.assetid: b6c13587-c690-45d9-af90-b3d652afc55b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 088a8abf7b143b68766f22af37f8ff4fa2065d65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612502"
---
# <a name="specify-source-information-partition-wizard"></a><span data-ttu-id="eedcc-102">Spécifier des informations sur la source (Assistant Partition)</span><span class="sxs-lookup"><span data-stu-id="eedcc-102">Specify Source Information (Partition Wizard)</span></span>
  <span data-ttu-id="eedcc-103">La page **Spécifier des informations sur la source** permet de sélectionner le groupe de mesures dans lequel doit être créée la partition ainsi que la vue de source de données et les tables filtrées se rapportant à cette dernière.</span><span class="sxs-lookup"><span data-stu-id="eedcc-103">Use the **Specify Source Information** page to select the measure group in which to create the partition, and also the data source view and filter tables for your partition.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="eedcc-104"> Si vous indiquez une table dans **Tables disponibles** mais que cette table est déjà utilisée par une autre partition, vous devez dans ce cas établir une requête dans la page **Restreindre les lignes** ou risquer d'obtenir des données en double dans le cube.</span><span class="sxs-lookup"><span data-stu-id="eedcc-104">If you specify a table in **Available Tables** that is used by another partition, you must provide a query in the **Restrict Rows** page or risk duplicating data in the cube.</span></span>  
  
## <a name="options"></a><span data-ttu-id="eedcc-105">Options</span><span class="sxs-lookup"><span data-stu-id="eedcc-105">Options</span></span>  
 <span data-ttu-id="eedcc-106">**Groupe de mesures**</span><span class="sxs-lookup"><span data-stu-id="eedcc-106">**Measure group**</span></span>  
 <span data-ttu-id="eedcc-107">Permet de sélectionner un groupe de mesures destiné à cette partition.</span><span class="sxs-lookup"><span data-stu-id="eedcc-107">Select a measure group for this partition.</span></span>  
  
 <span data-ttu-id="eedcc-108">**Chercher dans**</span><span class="sxs-lookup"><span data-stu-id="eedcc-108">**Look in**</span></span>  
 <span data-ttu-id="eedcc-109">Permet d'indiquer la source de données ou la vue de source de données contenant les tables source destinées à cette partition.</span><span class="sxs-lookup"><span data-stu-id="eedcc-109">Select the data source or data source view that contains the source tables for this partition.</span></span> <span data-ttu-id="eedcc-110">La vue de source de données utilisée par le groupe de mesures est l'élément sélectionné par défaut.</span><span class="sxs-lookup"><span data-stu-id="eedcc-110">The data source view used by the measure group is selected by default.</span></span>  
  
 <span data-ttu-id="eedcc-111">**Filtrer les tables**</span><span class="sxs-lookup"><span data-stu-id="eedcc-111">**Filter tables**</span></span>  
 <span data-ttu-id="eedcc-112">Permet d’entrer la chaîne utilisée pour restreindre les tables affichées dans **Tables disponibles**d’après leur nom.</span><span class="sxs-lookup"><span data-stu-id="eedcc-112">Type the string used to restrict, by table name, the tables displayed in **Available tables**.</span></span>  
  
 <span data-ttu-id="eedcc-113">**Rechercher des tables**</span><span class="sxs-lookup"><span data-stu-id="eedcc-113">**Find tables**</span></span>  
 <span data-ttu-id="eedcc-114">Permet d’actualiser la liste des tables répertoriées dans **Tables disponibles**, et d’affiner la liste d’après les critères d’une chaîne indiquée dans **Filtrer les tables**, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="eedcc-114">Select to refresh the list of tables in **Available tables**, further restricting the list if a string was specified in **Filter tables**.</span></span>  
  
 <span data-ttu-id="eedcc-115">**Tables disponibles**</span><span class="sxs-lookup"><span data-stu-id="eedcc-115">**Available tables**</span></span>  
 <span data-ttu-id="eedcc-116">Permet de sélectionner les tables à utiliser en tant que tables source pour les partitions.</span><span class="sxs-lookup"><span data-stu-id="eedcc-116">Select the tables to use as source tables for partitions.</span></span> <span data-ttu-id="eedcc-117">L' **Assistant Partition** crée une partition pour chaque table sélectionnée dans **Tables disponibles**.</span><span class="sxs-lookup"><span data-stu-id="eedcc-117">The **Partition Wizard** creates one partition for each table selected in **Available tables**.</span></span>  
  
 <span data-ttu-id="eedcc-118">Si aucun filtre n'est précisé dans **Filtrer les tables**, cette option répertorie alors toutes les tables de la source de données ou de la vue de source de données indiquées dans **Regarder dans** et dont la structure est similaire à la table de faits utilisée par le groupe de mesures mentionné dans **Groupe de mesures**.</span><span class="sxs-lookup"><span data-stu-id="eedcc-118">If no filter is specified in **Filter tables**, this option lists all tables in the data source or data source view that are specified in **Look in** and that are similar in structure to the fact table used by the measure group specified in **Measure group**.</span></span>  
  
 <span data-ttu-id="eedcc-119">Si un filtre est spécifié dans **Filtrer les tables**, la liste est plus restreinte encore en comparant le filtre aux noms des tables satisfaisant le critère précédent.</span><span class="sxs-lookup"><span data-stu-id="eedcc-119">If a filter is specified in **Filter tables**, the list is further restricted by comparing the filter against the table names that meet the previous criteria.</span></span> <span data-ttu-id="eedcc-120">Ainsi, seules les tables contenant la chaîne spécifiée dans **Filtrer les tables** sont affichées.</span><span class="sxs-lookup"><span data-stu-id="eedcc-120">Only those tables that contain the string specified in **Filter tables** are displayed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eedcc-121">Si plusieurs tables sont sélectionnées, la page **Restreindre les lignes** ne peut alors pas s'afficher et les lignes ne peuvent pas être restreintes pour les partitions créées à partir des tables sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="eedcc-121">If more than one table is selected, the **Restrict Rows** page cannot be displayed and rows cannot be restricted for the partitions created from the selected tables.</span></span> <span data-ttu-id="eedcc-122">Dans ce cas, pour restreindre les lignes relatives à chaque partition, lancez l'Assistant Partition une fois pour chaque table à partir de laquelle une partition doit être créée.</span><span class="sxs-lookup"><span data-stu-id="eedcc-122">To restrict rows for each partition, run the Partition Wizard once for each table from which a partition is to be created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eedcc-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eedcc-123">See Also</span></span>  
 [<span data-ttu-id="eedcc-124">Partitions &#40;Analysis Services - Données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="eedcc-124">Partitions &#40;Analysis Services - Multidimensional Data&#41;</span></span>](multidimensional-models-olap-logical-cube-objects/partitions-analysis-services-multidimensional-data.md)  
  
  
