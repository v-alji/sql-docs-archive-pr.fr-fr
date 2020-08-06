---
title: Spécifier les données d’apprentissage (Assistant Exploration de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.dm.dmwizard.specifytrainingdata.f1
ms.assetid: cb04deeb-0f89-4bba-b3f1-efccada16825
author: minewiskan
ms.author: owend
ms.openlocfilehash: 87a802256d287a3e8e9e7fb65bbd91687cb71a4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612496"
---
# <a name="specify-the-training-data-data-mining-wizard"></a><span data-ttu-id="67499-102">Spécifier les données d'apprentissage (Assistant Exploration de données)</span><span class="sxs-lookup"><span data-stu-id="67499-102">Specify the Training Data (Data Mining Wizard)</span></span>
  <span data-ttu-id="67499-103">Utilisez la page **Spécifier les données d’apprentissage** pour identifier les colonnes à inclure dans la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67499-103">Use the **Specify the Training Data** page to identify which columns to include in the mining structure.</span></span> <span data-ttu-id="67499-104">Vous pouvez sélectionner des colonnes à inclure même dans la structure même si vous ne les utilisez pas dans tous les modèles.</span><span class="sxs-lookup"><span data-stu-id="67499-104">You can select columns to include in the structure even if you do not use them in all models.</span></span> <span data-ttu-id="67499-105">Par exemple, si vous souhaitez procéder à une extraction des colonnes à partir du modèle d'exploration de données, vous pouvez les inclure dans la structure mais pas dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="67499-105">For example, if you want to drill through to the columns from the mining model, you can include them in the structure but not in the model.</span></span>  
  
 <span data-ttu-id="67499-106">Au moins une colonne clé est requise pour chaque table incluse dans la structure.</span><span class="sxs-lookup"><span data-stu-id="67499-106">At least one key column is required for each table that is included in the structure.</span></span> <span data-ttu-id="67499-107">La colonne que vous choisissez en tant que clé varie selon que la table est une table de cas ou une table imbriquée.</span><span class="sxs-lookup"><span data-stu-id="67499-107">The column that you pick as the key depends on whether the table is a case table or a nested table.</span></span> <span data-ttu-id="67499-108">Si la table est une table imbriquée, la clé est souvent la colonne prédictible également, pas la clé étrangère relationnelle.</span><span class="sxs-lookup"><span data-stu-id="67499-108">If the table is a nested table, the key is often also the predictable column, not the relational foreign key.</span></span> <span data-ttu-id="67499-109">Pour en savoir plus sur les clés imbriquées, consultez [Tables imbriquées &#40;Analysis Services - Exploration de données&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="67499-109">To learn about nested keys, see [Nested Tables &#40;Analysis Services - Data Mining&#41;](data-mining/nested-tables-analysis-services-data-mining.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67499-110">Les différents algorithmes d'exploration de données utilisent les clés différemment.</span><span class="sxs-lookup"><span data-stu-id="67499-110">Different mining algorithms use keys differently.</span></span> <span data-ttu-id="67499-111">Pour en savoir plus sur les différents types de clés, consultez [Types de contenu &#40;exploration de données&#41;](data-mining/content-types-data-mining.md).</span><span class="sxs-lookup"><span data-stu-id="67499-111">To learn about the different kinds of keys, see [Content Types &#40;Data Mining&#41;](data-mining/content-types-data-mining.md).</span></span>  
  
 <span data-ttu-id="67499-112">**Pour plus d’informations :** [Structures d’exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Colonnes d’un modèle d’exploration de données](data-mining/mining-model-columns.md), [Assistant Exploration de données &#40;Analysis Services - Exploration de données&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Créer une structure d’exploration de données relationnelle](data-mining/create-a-relational-mining-structure.md)</span><span class="sxs-lookup"><span data-stu-id="67499-112">**For More Information:** [Mining Structures &#40;Analysis Services - Data Mining&#41;](data-mining/mining-structures-analysis-services-data-mining.md), [Mining Model Columns](data-mining/mining-model-columns.md), [Data Mining Wizard &#40;Analysis Services - Data Mining&#41;](data-mining/data-mining-wizard-analysis-services-data-mining.md), [Create a Relational Mining Structure](data-mining/create-a-relational-mining-structure.md)</span></span>  
  
## <a name="options"></a><span data-ttu-id="67499-113">Options</span><span class="sxs-lookup"><span data-stu-id="67499-113">Options</span></span>  
 <span data-ttu-id="67499-114">**Tables/Colonnes**</span><span class="sxs-lookup"><span data-stu-id="67499-114">**Tables/Columns**</span></span>  
 <span data-ttu-id="67499-115">Affiche les tables et les colonnes sélectionnées dans la page précédente de l'Assistant.</span><span class="sxs-lookup"><span data-stu-id="67499-115">Displays the tables and columns that you selected on the previous page of the wizard.</span></span>  
  
 **\<check box>**  
 <span data-ttu-id="67499-116">Sélectionnez les colonnes à inclure dans la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67499-116">Select the columns to include in the mining structure.</span></span>  
  
 <span data-ttu-id="67499-117">Si votre source de données inclut des tables imbriquées ou plusieurs vues, développez la liste de colonnes pour afficher les tables imbriquées.</span><span class="sxs-lookup"><span data-stu-id="67499-117">If your data source includes nested tables or multiple views, expand the column list to view the nested tables.</span></span>  
  
 <span data-ttu-id="67499-118">**Clé**</span><span class="sxs-lookup"><span data-stu-id="67499-118">**Key**</span></span>  
 <span data-ttu-id="67499-119">Sélectionnez cette option pour utiliser la colonne en tant qu'identificateur unique des données.</span><span class="sxs-lookup"><span data-stu-id="67499-119">Select to use the column as a unique identifier for the data.</span></span>  
  
 <span data-ttu-id="67499-120">Pour une table de cas, la clé est habituellement l'identificateur unique.</span><span class="sxs-lookup"><span data-stu-id="67499-120">For a case table, the key is usually the unique identifier.</span></span>  
  
 <span data-ttu-id="67499-121">Pour une table imbriquée, la **Clé** indique l’identificateur d’une ligne dans le contexte du cas associé.</span><span class="sxs-lookup"><span data-stu-id="67499-121">For nested table, the **Key** indicates the identifier of a row in the context of the associated case.</span></span>  
  
 <span data-ttu-id="67499-122">**Entrée**</span><span class="sxs-lookup"><span data-stu-id="67499-122">**Input**</span></span>  
 <span data-ttu-id="67499-123">Sélectionnez cette option pour utiliser la colonne dans la création des prévisions.</span><span class="sxs-lookup"><span data-stu-id="67499-123">Select to use the column in creating predictions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="67499-124">Cette colonne est uniquement disponible lorsque vous créez un modèle d'exploration de données avec la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67499-124">This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="67499-125">**Prédictible**</span><span class="sxs-lookup"><span data-stu-id="67499-125">**Predictable**</span></span>  
 <span data-ttu-id="67499-126">Sélectionnez cette option pour permettre à la table ou à la colonne d'être prédite en fonction d'une entrée supplémentaire ultérieure.</span><span class="sxs-lookup"><span data-stu-id="67499-126">Select to enable the table or column to be predicted based on additional future input.</span></span>  
  
 <span data-ttu-id="67499-127">Si vous marquez également une table imbriquée comme prévisible, la totalité de la table imbriquée devient prévisible.</span><span class="sxs-lookup"><span data-stu-id="67499-127">If you also mark a nested table as predictable, the whole nested table becomes predictable.</span></span> <span data-ttu-id="67499-128">Si aucune colonne de la table imbriquée n'est marquée comme colonne d'entrée ou colonne prédictible, la table imbriquée est visible dans la structure d'exploration de données, mais elle est ignorée dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="67499-128">If no columns in the nested table are marked as input or predictable, the nested table will appear in the mining structure, but will be ignored in the model.</span></span>  
  
 <span data-ttu-id="67499-129">**Remarque** Cette colonne est uniquement disponible quand vous créez un modèle d’exploration de données avec la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67499-129">**Note** This column is only available when you are creating a mining model together with the mining structure.</span></span>  
  
 <span data-ttu-id="67499-130">**Suggérer**</span><span class="sxs-lookup"><span data-stu-id="67499-130">**Suggest**</span></span>  
 <span data-ttu-id="67499-131">Cliquez sur ce bouton pour ouvrir la boîte de dialogue **Suggérer des colonnes associées** , qui effectue l’analyse d’un échantillon de données pour identifier les colonnes d’entrée qui présentent la relation la plus forte avec la colonne **Prédictible** sélectionnée basée sur la méthode entropique.</span><span class="sxs-lookup"><span data-stu-id="67499-131">Click to open the **Suggest Related Columns** dialog box, which performs an analysis on a sample of data to identify input columns that show the greatest relationship to the selected **Predictable** column based on entropy.</span></span> <span data-ttu-id="67499-132">Cette analyse s'applique également aux colonnes de tables imbriquées ou aux structures d'exploration de données basées sur les sources OLAP.</span><span class="sxs-lookup"><span data-stu-id="67499-132">This analysis also applies to nested table columns or mining structures that are based on OLAP sources.</span></span>  
  
 <span data-ttu-id="67499-133">**Remarque** Cette colonne est uniquement disponible quand vous créez un modèle d’exploration de données avec la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="67499-133">**Note** This column only available when you are creating a mining model together with the mining structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67499-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67499-134">See Also</span></span>  
 <span data-ttu-id="67499-135">[Aide (F1) de l’Assistant Exploration de données &#40;Analysis Services-exploration de données&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="67499-135">[Data Mining Wizard F1 Help &#40;Analysis Services - Data Mining&#41;](data-mining-wizard-f1-help-analysis-services-data-mining.md) </span></span>  
 <span data-ttu-id="67499-136">[Suggérer des colonnes associées &#40;l’Assistant Exploration de données&#41;](suggest-related-columns-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="67499-136">[Suggest Related Columns &#40;Data Mining Wizard&#41;](suggest-related-columns-data-mining-wizard.md) </span></span>  
 <span data-ttu-id="67499-137">[Spécifier les types de tables &#40;l’Assistant Exploration de données&#41;](specify-table-types-data-mining-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="67499-137">[Specify Table Types &#40;Data Mining Wizard&#41;](specify-table-types-data-mining-wizard.md) </span></span>  
 [<span data-ttu-id="67499-138">Spécifiez le contenu et le type de données de la colonne &#40;l’Assistant Exploration de données&#41;</span><span class="sxs-lookup"><span data-stu-id="67499-138">Specify the Column's Content and Data Type &#40;Data Mining Wizard&#41;</span></span>](specify-the-column-s-content-and-data-type-data-mining-wizard.md)  
  
  
