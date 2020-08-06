---
title: Spécifier le nombre d’objets (Assistant conception d’agrégation) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66b972395f86746b2d08df234db8aa0c71d03fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611338"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a><span data-ttu-id="be1fa-102">Spécifier le nombre d'objets (Assistant Conception d'agrégation)</span><span class="sxs-lookup"><span data-stu-id="be1fa-102">Specify Object Counts (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="be1fa-103">La page **Spécifier le nombre d'objets** permet de calculer automatiquement le nombre d'objets inclus dans le cube ou d'entrer une estimation manuellement.</span><span class="sxs-lookup"><span data-stu-id="be1fa-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="be1fa-104">L'Assistant Conception d'agrégation utilise le nombre d'objets pour évaluer la capacité de stockage nécessaire.</span><span class="sxs-lookup"><span data-stu-id="be1fa-104">The Aggregation Design Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="be1fa-105">Options</span><span class="sxs-lookup"><span data-stu-id="be1fa-105">Options</span></span>  
 <span data-ttu-id="be1fa-106">**Objets de cube**</span><span class="sxs-lookup"><span data-stu-id="be1fa-106">**Cube Objects**</span></span>  
 <span data-ttu-id="be1fa-107">Affiche les dimensions et les attributs du cube.</span><span class="sxs-lookup"><span data-stu-id="be1fa-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="be1fa-108">Seuls les attributs dont la propriété a la `AggregationUsage` valeur `None` dans la page **vérifier l’utilisation** de l’agrégation de l’Assistant sont affichés, car il s’agit des seuls attributs qui nécessitent la spécification des nombres.</span><span class="sxs-lookup"><span data-stu-id="be1fa-108">Only the attributes that do not have their `AggregationUsage` property set to `None` in the **Review Aggregation Usage** page of the wizard are shown, because those are the only attributes that require the counts to be specified.</span></span>  
  
 <span data-ttu-id="be1fa-109">**Nombre estimé**</span><span class="sxs-lookup"><span data-stu-id="be1fa-109">**Estimated count**</span></span>  
 <span data-ttu-id="be1fa-110">Affiche le nombre estimé de lignes dans le groupe de mesures et l'estimation du nombre de membres d'attribut dans les dimensions de base de données.</span><span class="sxs-lookup"><span data-stu-id="be1fa-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="be1fa-111">Vous pouvez taper une valeur à utiliser comme nombre estimé ou vous pouvez calculer les valeurs du compteur estimées.</span><span class="sxs-lookup"><span data-stu-id="be1fa-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="be1fa-112">Pour calculer les valeurs de nombre, tapez `0` dans le champ, puis cliquez sur **nombre**.</span><span class="sxs-lookup"><span data-stu-id="be1fa-112">To calculate the count values, type `0` in the field and then click **Count**.</span></span> <span data-ttu-id="be1fa-113">Les champs qui affichent déjà un nombre ne sont pas mis à jour.</span><span class="sxs-lookup"><span data-stu-id="be1fa-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="be1fa-114">**Nombre de partitions**</span><span class="sxs-lookup"><span data-stu-id="be1fa-114">**Partition count**</span></span>  
 <span data-ttu-id="be1fa-115">(Facultatif) Tapez le nombre estimé de lignes dans le groupe de mesures et tapez l'estimation du nombre de membres d'attribut dans les partitions.</span><span class="sxs-lookup"><span data-stu-id="be1fa-115">(Optional) Type the estimated number of rows in the measure group and type the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="be1fa-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="be1fa-116">**Count**</span></span>  
 <span data-ttu-id="be1fa-117">Calcule et remplit à nouveau les valeurs de la colonne **Nombre estimé** pour tous les champs vides.</span><span class="sxs-lookup"><span data-stu-id="be1fa-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="be1fa-118">Les champs qui affichent déjà un nombre ne sont pas mis à jour.</span><span class="sxs-lookup"><span data-stu-id="be1fa-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be1fa-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="be1fa-119">See Also</span></span>  
 <span data-ttu-id="be1fa-120">[Aide (F1) de l’Assistant conception d’agrégation](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="be1fa-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="be1fa-121">Analysis Services assistants &#40;&#41;de données multidimensionnelles</span><span class="sxs-lookup"><span data-stu-id="be1fa-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
