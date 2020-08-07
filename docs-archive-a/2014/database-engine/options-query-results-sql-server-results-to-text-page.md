---
title: Options (résultats de la requête-SQL Server des résultats dans une page de texte) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryResults.SqlServer.SQLResultsToText
ms.assetid: 2ccbdf17-e14f-42f1-a836-ca999a3432c9
author: rothja
ms.author: jroth
ms.openlocfilehash: 4ece458e4bab9a57cb6692d4ac6dfdf2e8f4bd22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703235"
---
# <a name="options-query-results-sql-server-results-to-text-page"></a><span data-ttu-id="8562a-102">Options (résultats de la requête-SQL Server des résultats dans une page de texte)</span><span class="sxs-lookup"><span data-stu-id="8562a-102">Options (Query Results-SQL Server-Results to Text Page)</span></span>
  <span data-ttu-id="8562a-103">Utilisez cette page pour définir les options d'affichage d'un jeu de résultats de requête au format texte.</span><span class="sxs-lookup"><span data-stu-id="8562a-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="8562a-104">Les modifications apportées à ces options sont appliquées uniquement aux nouvelles requêtes [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8562a-104">Changes to these options are applied only to new [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="8562a-105">Pour modifier les options des requêtes en cours, cliquez sur **options de requête** dans le menu **requête** ou cliquez avec le bouton droit dans la fenêtre de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] requête et sélectionnez **options de requête**.</span><span class="sxs-lookup"><span data-stu-id="8562a-105">To change the options for the current queries, click **Query Options** on the **Query** menu, or right-click in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window, and select **Query Options**.</span></span> <span data-ttu-id="8562a-106">Dans la boîte de dialogue **Options de requête**, sous **Résultats**, cliquez sur **Texte**.</span><span class="sxs-lookup"><span data-stu-id="8562a-106">In the **Query Options** dialog box, under **Results**, click **Text**.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="8562a-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="8562a-107">UI element list</span></span>  
 <span data-ttu-id="8562a-108">**Format de sortie**</span><span class="sxs-lookup"><span data-stu-id="8562a-108">**Output format**</span></span>  
 <span data-ttu-id="8562a-109">Par défaut, la sortie est affichée sous la forme de colonnes créées par le remplissage des résultats à l'aide d'espaces.</span><span class="sxs-lookup"><span data-stu-id="8562a-109">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="8562a-110">Vous pouvez également utiliser des virgules, des tabulations ou des espaces pour séparer les colonnes.</span><span class="sxs-lookup"><span data-stu-id="8562a-110">Other options are to use commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="8562a-111">Sélectionnez **Délimiteur personnalisé** dans cette liste déroulante pour spécifier un autre séparateur dans la zone de texte **Délimiteur personnalisé**.</span><span class="sxs-lookup"><span data-stu-id="8562a-111">Select **Custom delimiter** from this drop-down list to specify a different delimiting character in the **Custom delimiter** text box.</span></span>  
  
 <span data-ttu-id="8562a-112">**Séparateur personnalisé**</span><span class="sxs-lookup"><span data-stu-id="8562a-112">**Custom delimiter**</span></span>  
 <span data-ttu-id="8562a-113">Indiquez le caractère à utiliser pour séparer les colonnes.</span><span class="sxs-lookup"><span data-stu-id="8562a-113">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="8562a-114">Cette zone de texte est disponible uniquement si vous avez cliqué sur Délimiteur personnalisé dans la zone de liste déroulante **Format de sortie**.</span><span class="sxs-lookup"><span data-stu-id="8562a-114">This text box is available only if you clicked Custom delimiter in the **Output format** drop-down list box.</span></span>  
  
 <span data-ttu-id="8562a-115">**Inclure des en-têtes de colonne dans l'ensemble de résultats**</span><span class="sxs-lookup"><span data-stu-id="8562a-115">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="8562a-116">Désactivez cette case à cocher si vous ne voulez pas que chaque colonne soit étiquetée au moyen d'un titre de colonne.</span><span class="sxs-lookup"><span data-stu-id="8562a-116">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="8562a-117">**Inclure la requête dans l'ensemble de résultats**</span><span class="sxs-lookup"><span data-stu-id="8562a-117">**Include the query in the result set**</span></span>  
 <span data-ttu-id="8562a-118">Activez cette case à cocher pour inclure le texte de la requête en cours d'exécution dans le volet de résultats avant les résultats de la requête.</span><span class="sxs-lookup"><span data-stu-id="8562a-118">Select this check box to include the text of the query that is running in the results pane before the results of the query.</span></span>  
  
 <span data-ttu-id="8562a-119">**Défilement pendant réception des résultats**</span><span class="sxs-lookup"><span data-stu-id="8562a-119">**Scroll as results are received**</span></span>  
 <span data-ttu-id="8562a-120">Activez cette case à cocher pour suivre l'exécution de la requête et afficher les enregistrements les plus récents à la fin de l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="8562a-120">Select this check box to keep the display focus on the most recently returned records at the end of the results set.</span></span> <span data-ttu-id="8562a-121">Désactivez-la pour cibler l'affichage sur les premières lignes retournées.</span><span class="sxs-lookup"><span data-stu-id="8562a-121">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="8562a-122">**Aligner les valeurs numériques à droite**</span><span class="sxs-lookup"><span data-stu-id="8562a-122">**Right align numeric values**</span></span>  
 <span data-ttu-id="8562a-123">Activez cette case à cocher pour aligner les valeurs numériques à droite de la colonne.</span><span class="sxs-lookup"><span data-stu-id="8562a-123">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="8562a-124">Cela peut faciliter l'analyse de nombres comportant un nombre de décimales invariable.</span><span class="sxs-lookup"><span data-stu-id="8562a-124">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="8562a-125">**Ignorer les résultats après l'exécution de la requête**</span><span class="sxs-lookup"><span data-stu-id="8562a-125">**Discard result after query executes**</span></span>  
 <span data-ttu-id="8562a-126">Activez cette case à cocher pour ignorer les résultats de la requête une fois qu'ils sont affichés dans le volet de résultats de la fenêtre de la requête.</span><span class="sxs-lookup"><span data-stu-id="8562a-126">Select this check box to discard the query results after they are displayed in the results pane of the query window.</span></span>  
  
 <span data-ttu-id="8562a-127">**Afficher les résultats dans un onglet séparé**</span><span class="sxs-lookup"><span data-stu-id="8562a-127">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="8562a-128">Activez cette case à cocher pour afficher l'ensemble de résultats dans une nouvelle fenêtre de document, et non au bas de la fenêtre de document de la requête.</span><span class="sxs-lookup"><span data-stu-id="8562a-128">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="8562a-129">**Basculer vers l'onglet des résultats après l'exécution de la requête**</span><span class="sxs-lookup"><span data-stu-id="8562a-129">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="8562a-130">Activez cette case à cocher pour afficher automatiquement l'ensemble de résultats à l'écran.</span><span class="sxs-lookup"><span data-stu-id="8562a-130">Select this check box to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="8562a-131">**Nombre maximal de caractères affichés dans chaque colonne**</span><span class="sxs-lookup"><span data-stu-id="8562a-131">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="8562a-132">Cette valeur est par défaut 256.</span><span class="sxs-lookup"><span data-stu-id="8562a-132">This value defaults to 256.</span></span> <span data-ttu-id="8562a-133">Augmentez cette valeur pour afficher des jeux de résultats plus grands sans les tronquer.</span><span class="sxs-lookup"><span data-stu-id="8562a-133">Increase this value to display larger result sets without truncation.</span></span> <span data-ttu-id="8562a-134">La valeur maximale est 8 192.</span><span class="sxs-lookup"><span data-stu-id="8562a-134">The maximum value is 8,192.</span></span>  
  
 <span data-ttu-id="8562a-135">**Rétablir les valeurs par défaut**</span><span class="sxs-lookup"><span data-stu-id="8562a-135">**Reset to Default**</span></span>  
 <span data-ttu-id="8562a-136">Rétablit toutes les valeurs par défaut initiales des options de cette page.</span><span class="sxs-lookup"><span data-stu-id="8562a-136">Resets all values on this page to the original default values.</span></span>  
  
  
