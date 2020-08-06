---
title: Sélectionner des tables et des vues (Assistant vue de source de données) (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac7159255ef526d871ed8906fc873d9f16d2eb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706832"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a><span data-ttu-id="43c4b-102">Sélectionner des tables et des vues (Assistant Vue de source de données) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="43c4b-102">Select Tables and Views (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="43c4b-103">Utilisez la page **Sélectionner des tables et des vues** pour sélectionner des tables ou des vues dans la source de données que vous voulez inclure dans la vue de la source des données.</span><span class="sxs-lookup"><span data-stu-id="43c4b-103">Use the **Select Tables and Views** page to select the tables or views from the data source that you want to include in the data source view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="43c4b-104">Options</span><span class="sxs-lookup"><span data-stu-id="43c4b-104">Options</span></span>  
 <span data-ttu-id="43c4b-105">**Objets disponibles**</span><span class="sxs-lookup"><span data-stu-id="43c4b-105">**Available objects**</span></span>  
 <span data-ttu-id="43c4b-106">Affiche la liste des tables et des vues dans le schéma de la source des données.</span><span class="sxs-lookup"><span data-stu-id="43c4b-106">Lists the tables and views in the data source schema.</span></span> <span data-ttu-id="43c4b-107">Le nom du schéma précède le nom de chaque objet si plusieurs schémas figurent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="43c4b-107">The schema name prefixes the name of every object if more than one schema is listed.</span></span> <span data-ttu-id="43c4b-108">Si un seul schéma est affiché, son nom ne précède pas les noms des objets.</span><span class="sxs-lookup"><span data-stu-id="43c4b-108">If only one schema is listed, the schema's name does not prefix the object names.</span></span>  
  
 <span data-ttu-id="43c4b-109">Pour afficher la liste en ordre croissant ou décroissant, cliquez sur **Nom** ou sur **Type**.</span><span class="sxs-lookup"><span data-stu-id="43c4b-109">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="43c4b-110">**Objets inclus**</span><span class="sxs-lookup"><span data-stu-id="43c4b-110">**Included objects**</span></span>  
 <span data-ttu-id="43c4b-111">Affiche la liste des tables et des vues à inclure dans la vue de la source des données.</span><span class="sxs-lookup"><span data-stu-id="43c4b-111">Lists the tables and views to include in the data source view.</span></span>  
  
 <span data-ttu-id="43c4b-112">Pour afficher la liste en ordre croissant ou décroissant, cliquez sur **Nom** ou sur **Type**.</span><span class="sxs-lookup"><span data-stu-id="43c4b-112">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="43c4b-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="43c4b-113">**Filter**</span></span>  
 <span data-ttu-id="43c4b-114">Filtre les objets répertoriés sous **Objets disponibles**.</span><span class="sxs-lookup"><span data-stu-id="43c4b-114">Filters the objects listed under **Available objects**.</span></span> <span data-ttu-id="43c4b-115">Tapez une chaîne, puis cliquez sur **Filtre** pour afficher uniquement les noms qui contiennent une chaîne de caractères donnée.</span><span class="sxs-lookup"><span data-stu-id="43c4b-115">Type a string, and then click **Filter** to list only the names that contain a specified string.</span></span> <span data-ttu-id="43c4b-116">Pour rechercher une chaîne précise, placez-la entre guillemets.</span><span class="sxs-lookup"><span data-stu-id="43c4b-116">To find an exact string of characters, enclose the string between double quotation marks.</span></span> <span data-ttu-id="43c4b-117">Le filtre ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="43c4b-117">The filter is not case sensitive.</span></span>  
  
 <span data-ttu-id="43c4b-118">Vous pouvez inclure n'importe où dans la chaîne de caractères les caractères génériques indiqués dans la liste ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="43c4b-118">You can include the wildcard characters listed in the following table anywhere in the filter string.</span></span>  
  
|<span data-ttu-id="43c4b-119">Caractère générique</span><span class="sxs-lookup"><span data-stu-id="43c4b-119">Wildcard character</span></span>|<span data-ttu-id="43c4b-120">Valeur</span><span class="sxs-lookup"><span data-stu-id="43c4b-120">Value</span></span>|  
|------------------------|-----------|  
|**\***|<span data-ttu-id="43c4b-121">N'importe quelle chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="43c4b-121">Any string of characters</span></span>|  
|**%**|<span data-ttu-id="43c4b-122">N'importe quelle chaîne de caractères</span><span class="sxs-lookup"><span data-stu-id="43c4b-122">Any string of characters</span></span>|  
|<span data-ttu-id="43c4b-123">**?**</span><span class="sxs-lookup"><span data-stu-id="43c4b-123">**?**</span></span>|<span data-ttu-id="43c4b-124">Un seul caractère</span><span class="sxs-lookup"><span data-stu-id="43c4b-124">A single character</span></span>|  
|<span data-ttu-id="43c4b-125">**«** *chaîne* **»**</span><span class="sxs-lookup"><span data-stu-id="43c4b-125">**"** *string* **"**</span></span>|<span data-ttu-id="43c4b-126">Chaîne de caractères littérale.</span><span class="sxs-lookup"><span data-stu-id="43c4b-126">A literal string of characters.</span></span> <span data-ttu-id="43c4b-127">Ce caractère générique correspond à toute sous-chaîne figurant dans le nom de l'objet.</span><span class="sxs-lookup"><span data-stu-id="43c4b-127">This wildcard character will match any substring within the object name.</span></span>|  
  
 <span data-ttu-id="43c4b-128">**Afficher les objets système**</span><span class="sxs-lookup"><span data-stu-id="43c4b-128">**Show system objects**</span></span>  
 <span data-ttu-id="43c4b-129">Affiche les objets système dans **Objets disponibles**.</span><span class="sxs-lookup"><span data-stu-id="43c4b-129">Displays system objects under **Available objects**.</span></span> <span data-ttu-id="43c4b-130">Cette option est disponible uniquement si le fournisseur de la source des données expose les objets système.</span><span class="sxs-lookup"><span data-stu-id="43c4b-130">This option is available only if the data source provider exposes system objects.</span></span> <span data-ttu-id="43c4b-131">La suppression d’un objet système de la liste **Objets inclus** sélectionne automatiquement cette option.</span><span class="sxs-lookup"><span data-stu-id="43c4b-131">Removing a system object from the **Included objects** list automatically selects this option.</span></span>  
  
 <span data-ttu-id="43c4b-132">**Ajouter des tables associées**</span><span class="sxs-lookup"><span data-stu-id="43c4b-132">**Add related tables**</span></span>  
 <span data-ttu-id="43c4b-133">Ajoute toutes les tables associées à celles figurant dans la liste **Objets inclus**.</span><span class="sxs-lookup"><span data-stu-id="43c4b-133">Adds all the tables that are related to those listed under **Included objects**.</span></span> <span data-ttu-id="43c4b-134">Cette option n'ajoute pas de vues.</span><span class="sxs-lookup"><span data-stu-id="43c4b-134">This option does not add views.</span></span> <span data-ttu-id="43c4b-135">Néanmoins, elle ajoute des tables partitionnées.</span><span class="sxs-lookup"><span data-stu-id="43c4b-135">However, this option does add partitioned tables.</span></span> <span data-ttu-id="43c4b-136">Si vous sélectionnez des critères de correspondance des noms dans la page **Correspondance de noms** de l’Assistant, cette option inclut également les tables logiquement selon les critères sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="43c4b-136">If you select name-matching criteria on the **Name Matching** page of the wizard, this option also includes logically related tables according to the criteria you select.</span></span> <span data-ttu-id="43c4b-137">Les tables sont également incluses si elles sont associées à des tables récemment ajoutées et si leur structure est identique à celle de la table d'origine.</span><span class="sxs-lookup"><span data-stu-id="43c4b-137">Tables are also included if they are related to the newly added related tables, and if they have an identical structure to the original table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c4b-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43c4b-138">See Also</span></span>  
 <span data-ttu-id="43c4b-139">[Aide (F1) de l’Assistant vue de source de données &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="43c4b-139">[Data Source View Wizard F1 Help &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span></span>  
 [<span data-ttu-id="43c4b-140">Vues de sources de données dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="43c4b-140">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
