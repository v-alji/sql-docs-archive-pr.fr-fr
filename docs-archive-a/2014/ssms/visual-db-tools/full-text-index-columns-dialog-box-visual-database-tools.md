---
title: Colonnes d’index de texte intégral, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.fulltextcolumn
ms.assetid: a6f41c5c-d950-4d64-9e42-d062925917b6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7f1cd2c94739a13e1820d8c05b338abd91d8a908
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708891"
---
# <a name="full-text-index-columns-dialog-box-visual-database-tools"></a><span data-ttu-id="19b26-102">Boîte de dialogue Colonnes d'index de texte intégral (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="19b26-102">Full-Text Index Columns Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="19b26-103">Cette boîte de dialogue répertorie les colonnes qui participent à l'index de texte intégral pour la table ouverte dans le Concepteur de tables.</span><span class="sxs-lookup"><span data-stu-id="19b26-103">This dialog box lists the columns participating in the full-text index for the table open in Table Designer.</span></span> <span data-ttu-id="19b26-104">Pour accéder à cette boîte de dialogue, cliquez avec le bouton droit sur la table dans le Concepteur de tables, choisissez **Index de texte intégral**, et dans la boîte de dialogue **Index de texte intégral**, cliquez sur l’index avec les colonnes que vous souhaitez afficher ou modifier, cliquez sur le champ **Colonnes** dans la grille à droite et enfin, cliquez sur le bouton de sélection ( **...** ).</span><span class="sxs-lookup"><span data-stu-id="19b26-104">To access this dialog box, right-click the table in Table Designer, choose **Full-Text Index**, and in the **Full-Text Index** dialog box, click the index with columns you want to view or edit, click the **Columns** field in the grid to the right, and click the ellipses (**...**).</span></span>  
  
## <a name="options"></a><span data-ttu-id="19b26-105">Options</span><span class="sxs-lookup"><span data-stu-id="19b26-105">Options</span></span>  
 <span data-ttu-id="19b26-106">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="19b26-106">**Column**</span></span>  
 <span data-ttu-id="19b26-107">Affiche le nom des colonnes qui participent à l'index de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="19b26-107">Shows the names of columns participating in the full-text index.</span></span> <span data-ttu-id="19b26-108">Pour ajouter une colonne, cliquez dans la première cellule vide et choisissez une colonne dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="19b26-108">To add a column, click in the first empty cell and choose a column from the drop-down list.</span></span> <span data-ttu-id="19b26-109">Seules les colonnes avec le type de données texte ou image sont accessibles.</span><span class="sxs-lookup"><span data-stu-id="19b26-109">Only columns with either text-based or image data types will be accessible.</span></span>  
  
 <span data-ttu-id="19b26-110">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="19b26-110">**Data Type**</span></span>  
 <span data-ttu-id="19b26-111">Affiche le type de données pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="19b26-111">Shows the data type for each column.</span></span> <span data-ttu-id="19b26-112">Il s’agit d’une propriété en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="19b26-112">This is a read-only property.</span></span> <span data-ttu-id="19b26-113">Pour modifier un type de données, ouvrez la table dans le Concepteur de tables, cliquez sur la colonne et modifiez le type de données sous l’onglet **Propriétés des colonnes** .</span><span class="sxs-lookup"><span data-stu-id="19b26-113">To change a data type, open the table in Table Designer, click the column, and edit the data type in the **Column Properties** tab.</span></span>  
  
 <span data-ttu-id="19b26-114">**Saisi par colonne**</span><span class="sxs-lookup"><span data-stu-id="19b26-114">**Typed by Column**</span></span>  
 <span data-ttu-id="19b26-115">S'applique uniquement aux colonnes avec le type de données `image`.</span><span class="sxs-lookup"><span data-stu-id="19b26-115">Applies only to columns with the data type `image`.</span></span> <span data-ttu-id="19b26-116">Fournit une liste déroulante dans laquelle vous pouvez choisir les autres colonnes qui représentent le type de données de cette colonne.</span><span class="sxs-lookup"><span data-stu-id="19b26-116">Provides a drop-down list from which you can choose which of the other columns represent the data type of this column.</span></span> <span data-ttu-id="19b26-117">Si cette colonne n'a pas de type de données `image`, la valeur sera équivalente à Aucun.</span><span class="sxs-lookup"><span data-stu-id="19b26-117">If this column is not of the `image` data type the value will be None.</span></span>  
  
 <span data-ttu-id="19b26-118">Les colonnes avec le type de données `image` peuvent contenir des fichiers Microsoft Office™ (.doc, .xls et .ppt), des fichiers texte (.txt) et des fichiers HTML (.htm), et l'affectation de la valeur d'image au type de données de cette colonne permet à la recherche en texte intégral de rechercher le contenu des fichiers.</span><span class="sxs-lookup"><span data-stu-id="19b26-118">Columns with the data type `image` can contain Microsoft Office files (.doc, .xls, and .ppt files), text files (.txt files), and HTML files (.htm files), and setting the data type of that column to image allows the full-text search to search the contents of the files.</span></span>  
  
 <span data-ttu-id="19b26-119">**Langage**</span><span class="sxs-lookup"><span data-stu-id="19b26-119">**Language**</span></span>  
 <span data-ttu-id="19b26-120">Répertorie les langues disponibles.</span><span class="sxs-lookup"><span data-stu-id="19b26-120">Lists available languages.</span></span> <span data-ttu-id="19b26-121">Dans la liste déroulante, choisissez la langue appropriée pour les données de la colonne.</span><span class="sxs-lookup"><span data-stu-id="19b26-121">Choose the language from the drop-down list appropriate for your column data.</span></span> <span data-ttu-id="19b26-122">Par exemple, si vous utilisez un système d'exploitation en français, mais souhaitez indexer une colonne qui contient de l'allemand, choisissez Allemand dans la liste déroulante pour obtenir un index plus performant.</span><span class="sxs-lookup"><span data-stu-id="19b26-122">For example, if you are using an English operating system, but you want to index a column that contains German text, choose German from the drop-down list to improve the index's performance.</span></span>  
  
 <span data-ttu-id="19b26-123">**Sémantique statistique**</span><span class="sxs-lookup"><span data-stu-id="19b26-123">**Statistical Semantics**</span></span>  
 <span data-ttu-id="19b26-124">Sélectionnez s'il faut activer l'indexation sémantique pour la colonne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="19b26-124">Select whether to enable semantic indexing for the selected column.</span></span> <span data-ttu-id="19b26-125">Pour plus d’informations, consultez [Recherche sémantique &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="19b26-125">For more information, see [Semantic Search &#40;SQL Server&#41;](../../relational-databases/search/semantic-search-sql-server.md).</span></span>  
  
 <span data-ttu-id="19b26-126">Si vous sélectionnez une **langue** avant de sélectionner **Sémantique statistique**, et que la langue sélectionnée n'est pas associée à un modèle linguistique sémantique, la case à cocher **Sémantique statistique** est désactivée.</span><span class="sxs-lookup"><span data-stu-id="19b26-126">If you select a **Language** prior to selecting **Statistical Semantics**, and the selected language does not have an associated Semantic Language Model, then the **Statistical Semantics** checkbox is disabled.</span></span> <span data-ttu-id="19b26-127">Si vous sélectionnez **Sémantique statistique** avant de sélectionner une **langue**, les langues disponibles dans la zone de liste déroulante sont limitées à celles pour lesquelles il existe une prise en charge de modèle linguistique sémantique.</span><span class="sxs-lookup"><span data-stu-id="19b26-127">If you select **Statistical Semantics** prior to selecting a **Language**, the languages available in the drop-down combo box will be restricted to those for which there is Semantic Language Model support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b26-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="19b26-128">See Also</span></span>  
 [<span data-ttu-id="19b26-129">Boîte de dialogue Index de texte intégral &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="19b26-129">Full-Text Index Dialog Box &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
