---
title: Options (résultats de la requête-SQL Server-résultats dans la page de grille) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToGrid
ms.assetid: f88a0f5c-e800-473b-ae23-c3943de5ed63
author: rothja
ms.author: jroth
ms.openlocfilehash: 3f9cec7e544c295420a9ae2a25e96ea9aa82030b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703239"
---
# <a name="options-query-results-sql-server-results-to-grid-page"></a><span data-ttu-id="f864d-102">Options (résultats de la requête-SQL Server-résultats dans la page de grille)</span><span class="sxs-lookup"><span data-stu-id="f864d-102">Options (Query Results-SQL Server-Results to Grid Page)</span></span>
  <span data-ttu-id="f864d-103">Cette page vous permet de spécifier les options d'affichage du jeu de résultats d'une requête au format grille.</span><span class="sxs-lookup"><span data-stu-id="f864d-103">Use this page to specify the options for displaying a query result set in grid format.</span></span> <span data-ttu-id="f864d-104">Les modifications apportées à ces options sont appliquées uniquement aux nouvelles requêtes [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f864d-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="f864d-105">Pour modifier les options des requêtes en cours, cliquez sur **options de requête** dans le menu **requête** ou cliquez avec le bouton droit dans la fenêtre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requête et sélectionnez **options de requête**.</span><span class="sxs-lookup"><span data-stu-id="f864d-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window and select **Query Options**.</span></span> <span data-ttu-id="f864d-106">Dans le volet gauche de la boîte de dialogue **Options de requête** , cliquez sur **Grille**sous **Résultats**.</span><span class="sxs-lookup"><span data-stu-id="f864d-106">In the left pane of the **Query Options** dialog box, under **Results**, click **Grid**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="f864d-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="f864d-107">UI element list</span></span>  
 <span data-ttu-id="f864d-108">**Inclure la requête dans l'ensemble de résultats**</span><span class="sxs-lookup"><span data-stu-id="f864d-108">**Include the query in the result set**</span></span>  
 <span data-ttu-id="f864d-109">Retourne le texte de la requête dans la sortie.</span><span class="sxs-lookup"><span data-stu-id="f864d-109">Returns the text of the query as part of the query output.</span></span>  
  
 <span data-ttu-id="f864d-110">**Inclure des en-têtes de colonne lors de la copie ou de l'enregistrement de résultats**</span><span class="sxs-lookup"><span data-stu-id="f864d-110">**Include column headers when copying or saving the results**</span></span>  
 <span data-ttu-id="f864d-111">Activez cette case à cocher pour inclure des en-têtes de colonne lorsque les résultats sont copiés dans le Presse-papiers ou enregistrés dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="f864d-111">Select this check box to include column headers when results are copied to the clipboard, or saved in a file.</span></span> <span data-ttu-id="f864d-112">Désactivez-la si vous ne voulez pas inclure ces en-têtes et que vous voulez limiter les résultats aux données uniquement.</span><span class="sxs-lookup"><span data-stu-id="f864d-112">Clear this check box if you want saved or copied result data to have only the data and not the column headings.</span></span>  
  
 <span data-ttu-id="f864d-113">**Ignorer les résultats après l'exécution**</span><span class="sxs-lookup"><span data-stu-id="f864d-113">**Discard results after execution**</span></span>  
 <span data-ttu-id="f864d-114">Empêche les résultats de la requête d'être affichés dans le volet Révision.</span><span class="sxs-lookup"><span data-stu-id="f864d-114">Prevents query results from being displayed in the reviewing pane.</span></span> <span data-ttu-id="f864d-115">Les résultats sont ignorés immédiatement après l'exécution.</span><span class="sxs-lookup"><span data-stu-id="f864d-115">The results are discarded immediately after execution.</span></span> <span data-ttu-id="f864d-116">La spécification de cette option aide à économiser de la mémoire.</span><span class="sxs-lookup"><span data-stu-id="f864d-116">Specifying this option helps save memory.</span></span>  
  
 <span data-ttu-id="f864d-117">**Afficher les résultats dans un onglet séparé**</span><span class="sxs-lookup"><span data-stu-id="f864d-117">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="f864d-118">Activez cette case à cocher pour afficher l'ensemble de résultats dans un nouvel onglet, et non au bas de la fenêtre de document de la requête.</span><span class="sxs-lookup"><span data-stu-id="f864d-118">Select this check box to display the result set in a new tab, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="f864d-119">**Basculer vers l'onglet des résultats après l'exécution de la requête**</span><span class="sxs-lookup"><span data-stu-id="f864d-119">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="f864d-120">Cliquez sur cette option pour que le volet de résultats devienne actif automatiquement après qu'une requête a été exécutée.</span><span class="sxs-lookup"><span data-stu-id="f864d-120">Click to automatically set the screen focus to the results pane upon execution of a query.</span></span>  
  
 <span data-ttu-id="f864d-121">**Nombre maximal de caractères récupérés**</span><span class="sxs-lookup"><span data-stu-id="f864d-121">**Maximum Characters Retrieved**</span></span>  
 <span data-ttu-id="f864d-122">**Données non-XML :**</span><span class="sxs-lookup"><span data-stu-id="f864d-122">**Non XML data**:</span></span>  
  
 <span data-ttu-id="f864d-123">Entrez un nombre compris entre 1 et 65 535 pour indiquer le nombre maximal de caractères affichés dans chaque cellule.</span><span class="sxs-lookup"><span data-stu-id="f864d-123">Enter a number from 1 through 65535 to specify the maximum number of characters that will be displayed in each cell.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f864d-124">Si vous précisez un nombre trop élevé, les données de l'ensemble de résultats risquent d'être tronquées à l'affichage.</span><span class="sxs-lookup"><span data-stu-id="f864d-124">Specifying a large number of characters may cause data in the result set to appear truncated.</span></span> <span data-ttu-id="f864d-125">Le nombre maximal de caractères affichés dans chaque cellule dépend de la taille de police.</span><span class="sxs-lookup"><span data-stu-id="f864d-125">The maximum number of characters displayed in each cell is dependent on the font size.</span></span> <span data-ttu-id="f864d-126">Si les ensembles de résultats retournés sont volumineux, il est préférable de ne pas spécifier une valeur trop élevée sans quoi vous risquez d'être confronté à une mémoire insuffisante pour l'exécution de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou à une dégradation des performances système.</span><span class="sxs-lookup"><span data-stu-id="f864d-126">When large result sets are returned, a high value in this box can cause [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to run low on memory and hinder system performance.</span></span>  
  
 <span data-ttu-id="f864d-127">**Données XML**:</span><span class="sxs-lookup"><span data-stu-id="f864d-127">**XML data**:</span></span>  
  
 <span data-ttu-id="f864d-128">Sélectionnez **1 Mo**, **2 Mo**ou **5 Mo**.</span><span class="sxs-lookup"><span data-stu-id="f864d-128">Select **1 MB**, **2 MB**, or **5 MB**.</span></span> <span data-ttu-id="f864d-129">Sélectionnez **Illimité** pour récupérer tous les caractères.</span><span class="sxs-lookup"><span data-stu-id="f864d-129">Select **Unlimited** to retrieve all characters.</span></span>  
  
 <span data-ttu-id="f864d-130">**Rétablir les valeurs par défaut**</span><span class="sxs-lookup"><span data-stu-id="f864d-130">**Reset to Default**</span></span>  
 <span data-ttu-id="f864d-131">Rétablit toutes les valeurs par défaut initiales des options de cette page.</span><span class="sxs-lookup"><span data-stu-id="f864d-131">Resets all values on this page to the original default values.</span></span>  
  
  
