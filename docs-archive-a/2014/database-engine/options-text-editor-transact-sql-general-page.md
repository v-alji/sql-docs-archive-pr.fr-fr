---
title: Options (éditeur de texte-Transact-SQL-page général) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.SQL.General
dev_langs:
- TSQL
ms.assetid: 7021ecb7-8fb5-4d8c-b984-3d34fcde8be2
author: rothja
ms.author: jroth
ms.openlocfilehash: f008d0d84a15cfbf0bfa988232015e6619f4f5c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611951"
---
# <a name="options-text-editor---transact-sql--general-page"></a><span data-ttu-id="5dcaf-102">Options (éditeur de texte-Transact-SQL-page général)</span><span class="sxs-lookup"><span data-stu-id="5dcaf-102">Options (Text Editor - Transact-SQL- General Page)</span></span>
  <span data-ttu-id="5dcaf-103">Utilisez la boîte de dialogue d’options **Général** pour modifier le comportement d’édition général de l’Éditeur de requête [!INCLUDE[ssDE](../includes/ssde-md.md)], qui permet de modifier des scripts [!INCLUDE[tsql](../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dcaf-103">Use the **General** options dialog box to change the general editing behavior of the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor, which is used to edit [!INCLUDE[tsql](../includes/tsql-md.md)] scripts.</span></span> <span data-ttu-id="5dcaf-104">Pour afficher ces paramètres, cliquez sur **Options** dans le menu **Outils**, développez le sous-dossier **Transact-SQL**, puis cliquez sur **Général**.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-104">To display these settings, click **Options** on the **Tools** menu, expand the **Transact-SQL** subfolder, and then click **General**.</span></span>  
  
## <a name="setting-options-in-multiple-locations"></a><span data-ttu-id="5dcaf-105">Définition d'options en plusieurs emplacements</span><span class="sxs-lookup"><span data-stu-id="5dcaf-105">Setting Options in Multiple Locations</span></span>  
 <span data-ttu-id="5dcaf-106">Les options de l’Éditeur de requête [!INCLUDE[ssDE](../includes/ssde-md.md)] peuvent également être définies dans la boîte de dialogue **Tous les langages Général**.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-106">Options for the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor can also be set in the **All Languages General** dialog.</span></span> <span data-ttu-id="5dcaf-107">Si vous utilisez les boîtes de dialogue **Tous les langages** pour définir des options différentes pour les autres éditeurs [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], comme les éditeurs DMX ou MDX, vous devez réinitialiser les options de l’Éditeur de requête [!INCLUDE[ssDE](../includes/ssde-md.md)] dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-107">If you use the **All Languages** dialogs to set different options for the other [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] editors, such as the DMX or MDX editors, you must reset the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor options using this dialog.</span></span>  
  
## <a name="statement-completion"></a><span data-ttu-id="5dcaf-108">Compléter automatiquement les instructions</span><span class="sxs-lookup"><span data-stu-id="5dcaf-108">Statement Completion</span></span>  
 <span data-ttu-id="5dcaf-109">**Répertorier automatiquement les membres**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-109">**Auto list members**</span></span>  
 <span data-ttu-id="5dcaf-110">Lorsque cette case à cocher est activée, des listes d'objets de base de données et de schéma, de colonnes, de fonctions table ou de fonctions disponibles sont affichées au fur et à mesure que vous tapez dans l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-110">When this check box is selected, lists of available database and schema objects, columns, table-valued functions, or functions are displayed as you type in the editor.</span></span> <span data-ttu-id="5dcaf-111">Sélectionnez un élément dans la liste contextuelle pour l'insérer dans votre code.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-111">Choose any item from the pop-up list to insert it into your code.</span></span>  
  
 <span data-ttu-id="5dcaf-112">**Masquer les membres avancés**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-112">**Hide advanced members**</span></span>  
 <span data-ttu-id="5dcaf-113">Cette case à cocher n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-113">This check box is unavailable.</span></span>  
  
 <span data-ttu-id="5dcaf-114">**Informations sur les paramètres**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-114">**Parameter information**</span></span>  
 <span data-ttu-id="5dcaf-115">Lorsque cette case à cocher est activée, les informations de paramètres sont affichées pour une procédure stockée ou une fonction située juste à gauche du point d'insertion (curseur).</span><span class="sxs-lookup"><span data-stu-id="5dcaf-115">When this check box is selected, parameter information is displayed for a stored procedure or function that is immediately to the left of the insertion point (cursor).</span></span> <span data-ttu-id="5dcaf-116">Les informations incluent une liste des paramètres disponibles avec leurs noms et types de données.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-116">The information includes a list of the available parameters with their names and data types.</span></span>  
  
## <a name="settings"></a><span data-ttu-id="5dcaf-117">Paramètres</span><span class="sxs-lookup"><span data-stu-id="5dcaf-117">Settings</span></span>  
 <span data-ttu-id="5dcaf-118">**Activer l'espace virtuel**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-118">**Enable virtual space**</span></span>  
 <span data-ttu-id="5dcaf-119">Lorsque cette case à cocher est activée, vous pouvez cliquer au-delà de la fin d'une ligne de code et taper du texte.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-119">When this check box is selected, you can click anywhere beyond the end of a line of code and type.</span></span> <span data-ttu-id="5dcaf-120">Activez cette case à cocher pour placer des commentaires à un point cohérent, en regard de votre code.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-120">Select this check box to position comments at a consistent point next to your code.</span></span> <span data-ttu-id="5dcaf-121">Activer cette case à cocher désactive la case à cocher **Retour automatique à la ligne**.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-121">Selecting this check box disables the **Word wrap** check box.</span></span>  
  
 <span data-ttu-id="5dcaf-122">**Retour automatique à la ligne**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-122">**Word wrap**</span></span>  
 <span data-ttu-id="5dcaf-123">Lorsque cette case à cocher est activée, toute partie d'une ligne qui s'étend horizontalement au-delà de la zone visible de l'éditeur est affichée automatiquement à la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-123">When this check box is selected, any portion of a line that extends horizontally beyond the viewable editor area is automatically displayed on the next line.</span></span> <span data-ttu-id="5dcaf-124">Cocher cette case coche la case **Afficher des glyphes visuels pour le retour automatique à la ligne** et décoche la case **Activer l’espace virtuel**.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-124">Selecting this check box enables the **Show visual glyphs for word wrap** check box and disables the **Enable virtual space** check box.</span></span>  
  
 <span data-ttu-id="5dcaf-125">**Afficher des glyphes visuels pour le retour automatique à la ligne**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-125">**Show visual glyphs for word wrap**</span></span>  
 <span data-ttu-id="5dcaf-126">Lorsque cette case à cocher est activée, une flèche retour est affichée si une ligne longue nécessite un retour automatique à la ligne suivante.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-126">When this check box is selected, a return arrow indicator is displayed where a long line wraps to the next line.</span></span>  
  
 <span data-ttu-id="5dcaf-127">**Appliquer les commandes Couper ou Copier aux lignes vides en l'absence de sélection**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-127">**Apply Cut/Copy commands to blank lines when there is no selection**</span></span>  
 <span data-ttu-id="5dcaf-128">Cette case à cocher définit le comportement de l'éditeur lorsque vous placez le point d'insertion sur une ligne vide, n'effectuez aucune sélection et cliquez sur **Copier** ou **Couper**.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-128">This check box sets the behavior of the editor when you place the insertion point on a blank line, select nothing, and then click **Copy** or **Cut**.</span></span>  
  
 <span data-ttu-id="5dcaf-129">Lorsque cette case à cocher est activée, la ligne vide est copiée ou coupée.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-129">When this check box is selected, the blank line is copied or cut.</span></span> <span data-ttu-id="5dcaf-130">Si vous cliquez ensuite sur **Coller**, une nouvelle ligne vide est insérée.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-130">If you then click **Paste**, a new, blank line is inserted.</span></span>  
  
 <span data-ttu-id="5dcaf-131">Lorsque cette case à cocher est désactivée, aucun élément n'est copié ou coupé.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-131">When this check box is cleared, nothing is copied or cut.</span></span> <span data-ttu-id="5dcaf-132">Si vous cliquez ensuite sur **Coller**, le dernier contenu copié est collé.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-132">If you then click **Paste**, the content most recently copied is pasted.</span></span> <span data-ttu-id="5dcaf-133">Si aucune sélection n'a été copiée précédemment, aucune sélection n'est collée.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-133">If nothing has been copied previously, nothing is pasted.</span></span>  
  
 <span data-ttu-id="5dcaf-134">Ce paramètre n'a aucun effet sur les commandes **Copier** ou **Couper** lorsqu'une ligne n'est pas vide.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-134">This setting has no effect on **Copy** or **Cut** when a line is not blank.</span></span> <span data-ttu-id="5dcaf-135">Si aucun élément n'est sélectionné, la totalité de la ligne est copiée ou coupée.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-135">If nothing is selected, the entire line is copied or cut.</span></span> <span data-ttu-id="5dcaf-136">Si vous cliquez ensuite sur **Coller**, le texte de la totalité de la ligne et son caractère de fin de ligne sont collés.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-136">If you then click **Paste**, the text of the entire line and its end line character are pasted.</span></span>  
  
## <a name="display"></a><span data-ttu-id="5dcaf-137">Afficher</span><span class="sxs-lookup"><span data-stu-id="5dcaf-137">Display</span></span>  
 <span data-ttu-id="5dcaf-138">**Numéros de ligne**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-138">**Line numbers**</span></span>  
 <span data-ttu-id="5dcaf-139">Lorsque cette case à cocher est activée, un numéro de ligne est affiché en regard de chaque ligne de code.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-139">When this check box is selected, a line number appears next to each line of code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5dcaf-140">Ces numéros de ligne ne sont pas ajoutés à votre code et ne s'impriment pas.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-140">These line numbers are not added to your code, and they do not print.</span></span> <span data-ttu-id="5dcaf-141">Ils servent de référence uniquement.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-141">They are for reference only.</span></span>  
  
 <span data-ttu-id="5dcaf-142">**Activer la navigation dans les URL par simple clic**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-142">**Enable single-click URL navigation**</span></span>  
 <span data-ttu-id="5dcaf-143">Lorsque cette case à cocher est activée, le curseur est remplacé par une main avec un doigt tendu lorsqu'il passe sur une URL dans l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-143">When this check box is selected, the cursor changes to a pointing hand as it passes over a URL in the editor.</span></span> <span data-ttu-id="5dcaf-144">Vous pouvez alors cliquer sur l'URL pour afficher la page correspondante dans votre navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-144">You can click the URL to display the indicated page in your Web browser.</span></span>  
  
 <span data-ttu-id="5dcaf-145">**Barre de navigation**</span><span class="sxs-lookup"><span data-stu-id="5dcaf-145">**Navigation bar**</span></span>  
 <span data-ttu-id="5dcaf-146">Cette case à cocher n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="5dcaf-146">This check box is unavailable.</span></span>  
  
  
