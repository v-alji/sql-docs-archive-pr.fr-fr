---
title: Spécifier le nombre d’objets (Assistant Optimisation de l’utilisation) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 306c7c25-ae24-4852-ab8c-c82f68a4bc1f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 862be19f12308def815a280dba04f42f0cbe6878
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612505"
---
# <a name="specify-object-counts-usage-based-optimization-wizard"></a><span data-ttu-id="00ef8-102">Spécifier le nombre d'objets (Assistant Optimisation de l'utilisation)</span><span class="sxs-lookup"><span data-stu-id="00ef8-102">Specify Object Counts (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="00ef8-103">La page **Spécifier le nombre d'objets** permet de calculer automatiquement le nombre d'objets inclus dans le cube ou d'entrer une estimation manuellement.</span><span class="sxs-lookup"><span data-stu-id="00ef8-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="00ef8-104">L'Assistant Optimisation de l'utilisation utilise le nombre d'objets pour évaluer la capacité de stockage nécessaire.</span><span class="sxs-lookup"><span data-stu-id="00ef8-104">The Usage-Based Optimization Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00ef8-105">Options</span><span class="sxs-lookup"><span data-stu-id="00ef8-105">Options</span></span>  
 <span data-ttu-id="00ef8-106">**Objets de cube**</span><span class="sxs-lookup"><span data-stu-id="00ef8-106">**Cube Objects**</span></span>  
 <span data-ttu-id="00ef8-107">Affiche les dimensions et les attributs du cube.</span><span class="sxs-lookup"><span data-stu-id="00ef8-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="00ef8-108">Seuls les attributs dont la propriété n’est pas `AggregationUsage` définie sur aucun dans la page **passer en revue l’utilisation** de l’agrégation de l’Assistant sont affichés, car il s’agit des seuls attributs dont le nombre est spécifié.</span><span class="sxs-lookup"><span data-stu-id="00ef8-108">Only the attributes that do not have their `AggregationUsage` property set to None in the **Review Aggregation Usage** page of the wizard are shown because those are the only attributes that need counts specified.</span></span>  
  
 <span data-ttu-id="00ef8-109">**Nombre estimé**</span><span class="sxs-lookup"><span data-stu-id="00ef8-109">**Estimated count**</span></span>  
 <span data-ttu-id="00ef8-110">Affiche le nombre estimé de lignes dans le groupe de mesures et l'estimation du nombre de membres d'attribut dans les dimensions de base de données.</span><span class="sxs-lookup"><span data-stu-id="00ef8-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="00ef8-111">Vous pouvez taper une valeur à utiliser comme nombre estimé ou vous pouvez calculer les valeurs du compteur estimées.</span><span class="sxs-lookup"><span data-stu-id="00ef8-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="00ef8-112">Pour calculer les valeurs du compteur, tapez 0 dans le champ puis cliquez sur **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="00ef8-112">To calculate the count values, type 0 in the field and then click **Count**.</span></span> <span data-ttu-id="00ef8-113">Les champs qui affichent déjà un nombre ne sont pas mis à jour.</span><span class="sxs-lookup"><span data-stu-id="00ef8-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="00ef8-114">**Nombre de partitions**</span><span class="sxs-lookup"><span data-stu-id="00ef8-114">**Partition count**</span></span>  
 <span data-ttu-id="00ef8-115">(Facultatif) Tapez le nombre estimé de lignes dans le groupe de mesures et l'estimation du nombre de membres d'attribut dans les partitions.</span><span class="sxs-lookup"><span data-stu-id="00ef8-115">(Optional) Type the estimated number of rows in the measure group and the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="00ef8-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="00ef8-116">**Count**</span></span>  
 <span data-ttu-id="00ef8-117">Calcule et remplit à nouveau les valeurs de la colonne **Nombre estimé** pour tous les champs vides.</span><span class="sxs-lookup"><span data-stu-id="00ef8-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="00ef8-118">Les champs qui affichent déjà un nombre ne sont pas mis à jour.</span><span class="sxs-lookup"><span data-stu-id="00ef8-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00ef8-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00ef8-119">See Also</span></span>  
 <span data-ttu-id="00ef8-120">[Aide (F1) de l’Assistant conception d’agrégation](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="00ef8-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="00ef8-121">Analysis Services assistants &#40;&#41;de données multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="00ef8-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
