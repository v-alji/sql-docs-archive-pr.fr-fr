---
title: Résultats des options de requête (page texte) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.query.text.f1
ms.assetid: fd2fb409-58f9-4ede-8349-ce007126b68d
author: rothja
ms.author: jroth
ms.openlocfilehash: 45019450c8fc959b440aac5bf1e9098e59cecefc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613117"
---
# <a name="query-options-results-text-page"></a><span data-ttu-id="f08c8-102">Options de requête — Résultats de requête (page Texte)</span><span class="sxs-lookup"><span data-stu-id="f08c8-102">Query Options Results (Text Page)</span></span>
  <span data-ttu-id="f08c8-103">Utilisez cette page pour définir les options d'affichage d'un jeu de résultats de requête au format texte.</span><span class="sxs-lookup"><span data-stu-id="f08c8-103">Use this page to specify the options for displaying a query result set in text format.</span></span> <span data-ttu-id="f08c8-104">Ses paramètres s'appliquent également lorsque **Résultats dans un fichier** est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f08c8-104">The settings on this page also apply when **Results to File** is selected.</span></span>  
  
 <span data-ttu-id="f08c8-105">**Format de sortie**</span><span class="sxs-lookup"><span data-stu-id="f08c8-105">**Output format**</span></span>  
 <span data-ttu-id="f08c8-106">Par défaut, la sortie est affichée sous la forme de colonnes créées par le remplissage des résultats à l'aide d'espaces.</span><span class="sxs-lookup"><span data-stu-id="f08c8-106">By default the output is displayed in columns created by padding the results with spaces.</span></span> <span data-ttu-id="f08c8-107">Il est également possible de séparer les colonnes à l'aide de virgules, de tabulations ou d'espaces.</span><span class="sxs-lookup"><span data-stu-id="f08c8-107">Other options are using commas, tabs, or spaces to separate columns.</span></span> <span data-ttu-id="f08c8-108">Activez la case à cocher **Séparateur personnalisé** pour définir un autre **caractère de délimitation** dans la zone de même nom.</span><span class="sxs-lookup"><span data-stu-id="f08c8-108">Select the **Custom delimiter** check box to specify a different delimiting character in the **Custom delimiter** box.</span></span>  
  
 <span data-ttu-id="f08c8-109">**Séparateur personnalisé**</span><span class="sxs-lookup"><span data-stu-id="f08c8-109">**Custom delimiter**</span></span>  
 <span data-ttu-id="f08c8-110">Indiquez le caractère à utiliser pour séparer les colonnes.</span><span class="sxs-lookup"><span data-stu-id="f08c8-110">Specify the character of your choice to separate columns.</span></span> <span data-ttu-id="f08c8-111">Cette option n'est disponible que lorsque la case à cocher **Séparateur personnalisé** est activée dans la zone **Format de sortie** .</span><span class="sxs-lookup"><span data-stu-id="f08c8-111">This option is only available if the **Custom delimiter** check box is selected in the **Output format** box.</span></span>  
  
 <span data-ttu-id="f08c8-112">**Inclure des en-têtes de colonne dans l'ensemble de résultats**</span><span class="sxs-lookup"><span data-stu-id="f08c8-112">**Include column headers in the result set**</span></span>  
 <span data-ttu-id="f08c8-113">Désactivez cette case à cocher si vous ne voulez pas que chaque colonne soit étiquetée au moyen d'un titre de colonne.</span><span class="sxs-lookup"><span data-stu-id="f08c8-113">Clear this check box if you do not want each column labeled with a column title.</span></span>  
  
 <span data-ttu-id="f08c8-114">**Défilement pendant réception des résultats**</span><span class="sxs-lookup"><span data-stu-id="f08c8-114">**Scroll as results are received**</span></span>  
 <span data-ttu-id="f08c8-115">Activez cette case à cocher pour cibler l'affichage sur les derniers enregistrements retournés au bas de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="f08c8-115">Select this check box to keep the display focus on the most recently returned records at the bottom.</span></span> <span data-ttu-id="f08c8-116">Désactivez-la pour cibler l'affichage sur les premières lignes retournées.</span><span class="sxs-lookup"><span data-stu-id="f08c8-116">Clear this check box to keep the display focus on the first rows received.</span></span>  
  
 <span data-ttu-id="f08c8-117">**Aligner les valeurs numériques à droite**</span><span class="sxs-lookup"><span data-stu-id="f08c8-117">**Right align numeric values**</span></span>  
 <span data-ttu-id="f08c8-118">Activez cette case à cocher pour aligner les valeurs numériques à droite de la colonne.</span><span class="sxs-lookup"><span data-stu-id="f08c8-118">Select this check box to align numeric values to the right of the column.</span></span> <span data-ttu-id="f08c8-119">Cela peut faciliter l'analyse de nombres comportant un nombre de décimales invariable.</span><span class="sxs-lookup"><span data-stu-id="f08c8-119">This can make it easier to review numbers with a fixed number of decimal places.</span></span>  
  
 <span data-ttu-id="f08c8-120">**Ignorer les résultats après l'exécution de la requête**</span><span class="sxs-lookup"><span data-stu-id="f08c8-120">**Discard result after query executes**</span></span>  
 <span data-ttu-id="f08c8-121">Libère de la mémoire en ignorant les résultats de la requête une fois ceux-ci affichés à l'écran.</span><span class="sxs-lookup"><span data-stu-id="f08c8-121">Frees memory by discarding the query results after the screen display has received them.</span></span>  
  
 <span data-ttu-id="f08c8-122">**Afficher les résultats dans un onglet séparé**</span><span class="sxs-lookup"><span data-stu-id="f08c8-122">**Display results in a separate tab**</span></span>  
 <span data-ttu-id="f08c8-123">Activez cette case à cocher pour afficher l'ensemble de résultats dans une nouvelle fenêtre de document, et non au bas de la fenêtre de document de la requête.</span><span class="sxs-lookup"><span data-stu-id="f08c8-123">Select this check box to display the result set in a new document window, instead of at the bottom of the query document window.</span></span>  
  
 <span data-ttu-id="f08c8-124">**Basculer vers l'onglet des résultats après l'exécution de la requête**</span><span class="sxs-lookup"><span data-stu-id="f08c8-124">**Switch to results tab after the query executes**</span></span>  
 <span data-ttu-id="f08c8-125">Cliquez sur cette option pour que l'affichage soit automatiquement ciblé sur l'ensemble de résultats.</span><span class="sxs-lookup"><span data-stu-id="f08c8-125">Click to automatically set the screen focus to the result set.</span></span>  
  
 <span data-ttu-id="f08c8-126">**Nombre maximal de caractères affichés dans chaque colonne**</span><span class="sxs-lookup"><span data-stu-id="f08c8-126">**Maximum number of characters displayed in each column**</span></span>  
 <span data-ttu-id="f08c8-127">Cette valeur est par défaut 256.</span><span class="sxs-lookup"><span data-stu-id="f08c8-127">This value defaults to 256.</span></span> <span data-ttu-id="f08c8-128">Augmentez cette valeur pour afficher des jeux de résultats plus grands sans les tronquer.</span><span class="sxs-lookup"><span data-stu-id="f08c8-128">Increase this value to display larger result sets without truncation.</span></span>  
  
 <span data-ttu-id="f08c8-129">**Rétablir les valeurs par défaut**</span><span class="sxs-lookup"><span data-stu-id="f08c8-129">**Reset to Default**</span></span>  
 <span data-ttu-id="f08c8-130">Rétablit toutes les valeurs par défaut initiales des options de cette page.</span><span class="sxs-lookup"><span data-stu-id="f08c8-130">Resets all values on this page to the original default values.</span></span>  
  
## <a name="saving-a-text-result-set-with-headers"></a><span data-ttu-id="f08c8-131">Enregistrement d'un ensemble de résultats sous la forme de texte avec des en-têtes</span><span class="sxs-lookup"><span data-stu-id="f08c8-131">Saving a text result set with headers</span></span>  
 <span data-ttu-id="f08c8-132">Pour enregistrer les résultats de la requête sous forme de fichier texte avec en-têtes, activez la case à cocher **Inclure des en-têtes de colonne dans l'ensemble de résultats** et spécifiez un format de sortie délimité.</span><span class="sxs-lookup"><span data-stu-id="f08c8-132">To save query results as a text file with headers, select the **Include column headers in the result set** check box and a delimited output format.</span></span> <span data-ttu-id="f08c8-133">Le fichier de rapport contiendra alors des en-têtes si vous cliquez sur **Résultats dans un fichier** dans la barre d’outils ou si vous cliquez avec le bouton droit sur des résultats de requête et que vous cliquez sur **Enregistrer les résultats sous**, que vous tapez un nom de fichier, puis que vous cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="f08c8-133">Now the report file will contain headers when you click **Results to File** on the toolbar, or when you right-click any query results, click **Save Results As**, type a file name, and then click **Save**.</span></span>  
  
  
