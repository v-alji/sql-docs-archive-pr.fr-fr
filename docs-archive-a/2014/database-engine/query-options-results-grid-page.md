---
title: Résultats des options de requête (page grille) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.grid.f1
ms.assetid: 764bf435-3aab-4c62-b4e0-64fe020a5a95
author: rothja
ms.author: jroth
ms.openlocfilehash: bf300dd5071128b0259230ae788a27595bd8d29e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613118"
---
# <a name="query-options-results-grid-page"></a><span data-ttu-id="524eb-102">Options de requête – Résultats (page Grille)</span><span class="sxs-lookup"><span data-stu-id="524eb-102">Query Options Results (Grid Page)</span></span>
  <span data-ttu-id="524eb-103">Cette page vous permet de spécifier les options d'affichage du jeu de résultats d'une requête au format grille.</span><span class="sxs-lookup"><span data-stu-id="524eb-103">Use this page to specify the options for displaying a query result set in grid format.</span></span>  
  
## <a name="options"></a><span data-ttu-id="524eb-104">Options</span><span class="sxs-lookup"><span data-stu-id="524eb-104">Options</span></span>  
 <span data-ttu-id="524eb-105">**Inclure la requête dans l'ensemble de résultats**</span><span class="sxs-lookup"><span data-stu-id="524eb-105">**Include the query in the result set**</span></span>  
 <span data-ttu-id="524eb-106">Retourne le texte de la requête dans l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="524eb-106">Returns the text of the query as part of the result set.</span></span>  
  
 <span data-ttu-id="524eb-107">**Inclure des en-têtes de colonne lors de la copie ou de l'enregistrement de résultats**</span><span class="sxs-lookup"><span data-stu-id="524eb-107">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="524eb-108">Permet d'inclure les en-têtes (titres) des colonnes lorsque les résultats sont copiés dans le Presse-papiers ou enregistrés dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="524eb-108">Include column headers (titles) when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="524eb-109">Désactivez cette case à cocher si vous voulez que les résultats copiés ou enregistrés contiennent seulement les données, sans les en-têtes des colonnes.</span><span class="sxs-lookup"><span data-stu-id="524eb-109">Clear this check box if you do not want saved or copied result data to have only the data, and not the column headings.</span></span>  
  
 <span data-ttu-id="524eb-110">**Ignorer les résultats après l'exécution**</span><span class="sxs-lookup"><span data-stu-id="524eb-110">**Discard results after execution**</span></span>  
 <span data-ttu-id="524eb-111">Permet de libérer de la mémoire en ignorant les résultats de la requête une fois qu'ils ont été affichés à l'écran.</span><span class="sxs-lookup"><span data-stu-id="524eb-111">Free memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="524eb-112">**Afficher les résultats dans un onglet séparé**</span><span class="sxs-lookup"><span data-stu-id="524eb-112">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="524eb-113">Permet d'afficher l'ensemble de résultats dans une nouvelle fenêtre de document et non pas en bas de la fenêtre de requête de document.</span><span class="sxs-lookup"><span data-stu-id="524eb-113">Display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="524eb-114">**Basculer vers l'onglet des résultats après l'exécution de la requête**</span><span class="sxs-lookup"><span data-stu-id="524eb-114">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="524eb-115">Affiche automatiquement l'ensemble de résultats à l'écran.</span><span class="sxs-lookup"><span data-stu-id="524eb-115">Automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="524eb-116">**Nombre maximal de caractères récupérés**</span><span class="sxs-lookup"><span data-stu-id="524eb-116">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="524eb-117">**Données non-XML :**</span><span class="sxs-lookup"><span data-stu-id="524eb-117">**Non XML data**:</span></span>  
  
 <span data-ttu-id="524eb-118">Entrez un nombre compris entre 1 et 65 535 pour indiquer le nombre maximal de caractères affichés dans chaque cellule.</span><span class="sxs-lookup"><span data-stu-id="524eb-118">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="524eb-119">Si vous précisez un nombre trop élevé, les données de l'ensemble de résultats risquent d'être tronquées à l'affichage.</span><span class="sxs-lookup"><span data-stu-id="524eb-119">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="524eb-120">Le nombre maximal de caractères affichés dans chaque cellule dépend de la taille de police.</span><span class="sxs-lookup"><span data-stu-id="524eb-120">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="524eb-121">Si les ensembles de résultats retournés sont volumineux, il est préférable de ne pas spécifier une valeur trop élevée sans quoi vous risquez d'être confronté à une mémoire insuffisante pour l'exécution de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou à une dégradation des performances système.</span><span class="sxs-lookup"><span data-stu-id="524eb-121">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="524eb-122">**Données XML**:</span><span class="sxs-lookup"><span data-stu-id="524eb-122">**XML data**:</span></span>  
  
 <span data-ttu-id="524eb-123">Sélectionnez **1 Mo**, **2 Mo**ou **5 Mo**.</span><span class="sxs-lookup"><span data-stu-id="524eb-123">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="524eb-124">Sélectionnez **Illimité** pour récupérer tous les caractères.</span><span class="sxs-lookup"><span data-stu-id="524eb-124">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="524eb-125">**Rétablir les valeurs par défaut**</span><span class="sxs-lookup"><span data-stu-id="524eb-125">**Reset to Default**</span></span>  
 <span data-ttu-id="524eb-126">Rétablit toutes les valeurs par défaut initiales des options de cette page.</span><span class="sxs-lookup"><span data-stu-id="524eb-126">Resets all values on this page to the original default values.</span></span>  
  
  
