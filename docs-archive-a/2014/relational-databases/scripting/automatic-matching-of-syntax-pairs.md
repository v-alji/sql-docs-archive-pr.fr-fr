---
title: Correspondance automatique des paires de syntaxe
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], delimiter highlighting
- IntelliSense [SQL Server], syntax pair matching
ms.assetid: bfc54cda-bfd6-4545-a5b9-f9db2ae13769
author: rothja
ms.author: jroth
ms.openlocfilehash: d1237eeb9aaec39e3210b00c880c0005ef3d95bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603912"
---
# <a name="automatic-matching-of-syntax-pairs"></a><span data-ttu-id="ebe07-102">Correspondance automatique des paires de syntaxe</span><span class="sxs-lookup"><span data-stu-id="ebe07-102">Automatic Matching of Syntax Pairs</span></span>
  <span data-ttu-id="ebe07-103">La correspondance automatique des paires de syntaxe vous informe immédiatement si les éléments syntaxiques qui doivent être codés par paire sont correctement assortis.</span><span class="sxs-lookup"><span data-stu-id="ebe07-103">Automatic matching of syntax pairs gives you immediate feedback on whether syntax elements that must be coded in pairs are correctly paired.</span></span> <span data-ttu-id="ebe07-104">Cette correspondance est connue comme correspondance des séparateurs dans l’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] , correspondance des accolades dans l’éditeur de requête XMLA Analysis Services et correspondance des parenthèses dans les éditeurs MDX et DMX.</span><span class="sxs-lookup"><span data-stu-id="ebe07-104">This is known as delimiter matching in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor, brace matching in the Analysis Services XMLA Query Editor, and parenthesis matching in the MDX and DMX editors.</span></span>  
  
## <a name="database-engine-query-editor-delimiter-matching"></a><span data-ttu-id="ebe07-105">Correspondance des séparateurs dans l'éditeur de requête du moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="ebe07-105">Database Engine Query Editor Delimiter Matching</span></span>  
 <span data-ttu-id="ebe07-106">L’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] correspond aux séparateurs qui identifient les limites des blocs de code.</span><span class="sxs-lookup"><span data-stu-id="ebe07-106">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor matches the delimiters that identify the boundaries of code blocks.</span></span> <span data-ttu-id="ebe07-107">La correspondance est réalisée de deux façons :</span><span class="sxs-lookup"><span data-stu-id="ebe07-107">The matching is done in two ways:</span></span>  
  
-   <span data-ttu-id="ebe07-108">L'éditeur met en surbrillance les deux séparateurs d'une paire lorsque vous terminez de taper le second séparateur de la paire.</span><span class="sxs-lookup"><span data-stu-id="ebe07-108">The editor highlights both delimiters in a pair when you finish typing the second delimiter in the pair.</span></span>  
  
-   <span data-ttu-id="ebe07-109">Chaque fois que le curseur est dans l'un des séparateurs d'une paire, vous pouvez utiliser le raccourci clavier CTRL+] pour atteindre le séparateur correspondant.</span><span class="sxs-lookup"><span data-stu-id="ebe07-109">Anytime the cursor is in one of the delimiters in a pair, you can use the CTRL+] keyboard shortcut to jump to the matching delimiter.</span></span>  
  
### <a name="delimiter-pairs"></a><span data-ttu-id="ebe07-110">Paires de séparateurs</span><span class="sxs-lookup"><span data-stu-id="ebe07-110">Delimiter Pairs</span></span>  
 <span data-ttu-id="ebe07-111">La correspondance automatique des séparateurs reconnaît les jeux de séparateurs suivants :</span><span class="sxs-lookup"><span data-stu-id="ebe07-111">Automatic delimiter matching recognizes the following sets of delimiters:</span></span>  
  
|<span data-ttu-id="ebe07-112">Séparateur de début</span><span class="sxs-lookup"><span data-stu-id="ebe07-112">Lead Delimiter</span></span>|<span data-ttu-id="ebe07-113">Séparateur de fin</span><span class="sxs-lookup"><span data-stu-id="ebe07-113">Closing Delimiter</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="ebe07-114">**(**</span><span class="sxs-lookup"><span data-stu-id="ebe07-114">**(**</span></span>|<span data-ttu-id="ebe07-115">**)**</span><span class="sxs-lookup"><span data-stu-id="ebe07-115">**)**</span></span>|  
|<span data-ttu-id="ebe07-116">**BEGIN**</span><span class="sxs-lookup"><span data-stu-id="ebe07-116">**BEGIN**</span></span>|<span data-ttu-id="ebe07-117">**END**</span><span class="sxs-lookup"><span data-stu-id="ebe07-117">**END**</span></span>|  
|<span data-ttu-id="ebe07-118">**BEGIN TRY**</span><span class="sxs-lookup"><span data-stu-id="ebe07-118">**BEGIN TRY**</span></span>|<span data-ttu-id="ebe07-119">**END TRY**</span><span class="sxs-lookup"><span data-stu-id="ebe07-119">**END TRY**</span></span>|  
|<span data-ttu-id="ebe07-120">**BEGIN CATCH**</span><span class="sxs-lookup"><span data-stu-id="ebe07-120">**BEGIN CATCH**</span></span>|<span data-ttu-id="ebe07-121">**END CATCH**</span><span class="sxs-lookup"><span data-stu-id="ebe07-121">**END CATCH**</span></span>|  
  
 <span data-ttu-id="ebe07-122">La correspondance automatique des séparateurs ne reconnaît pas les séparateurs pour les identificateurs entre parenthèses ([ObjectName]) ou les identificateurs entre guillemets ("ObjectName").</span><span class="sxs-lookup"><span data-stu-id="ebe07-122">Automatic delimiter matching does not recognize the delimiters for bracketed identifiers ([ObjectName]), or quoted identifiers ("ObjectName").</span></span> <span data-ttu-id="ebe07-123">La correspondance des paires ne fonctionne pas pour les séparateurs à guillemet simple des littéraux de chaîne ('chaîne') parce que le codage de couleur donne déjà une indication sur le fait que la chaîne a été délimitée ou pas.</span><span class="sxs-lookup"><span data-stu-id="ebe07-123">Pair matching does not match the single quotation delimiters for string literals ('string') because color coding already gives a visual indication of whether the string has been delimited.</span></span>  
  
### <a name="delimiter-highlighting"></a><span data-ttu-id="ebe07-124">Mise en surbrillance de séparateurs</span><span class="sxs-lookup"><span data-stu-id="ebe07-124">Delimiter Highlighting</span></span>  
 <span data-ttu-id="ebe07-125">La correspondance met en surbrillance l'élément de début et l'élément de fin d'une paire de séparateurs.</span><span class="sxs-lookup"><span data-stu-id="ebe07-125">Matching highlights both the lead and closing element of a pair of delimiters.</span></span> <span data-ttu-id="ebe07-126">Vous pouvez ainsi identifier visuellement les blocs de code et rechercher les erreurs de paires de séparateurs.</span><span class="sxs-lookup"><span data-stu-id="ebe07-126">This lets you visually identify code blocks and check for mismatched pairs of delimiters.</span></span>  
  
 <span data-ttu-id="ebe07-127">Les séparateurs sont mis en surbrillance lorsque vous tapez la dernière lettre qui complète la paire.</span><span class="sxs-lookup"><span data-stu-id="ebe07-127">Delimiters are highlighted when you type the final letter that completes the pair.</span></span> <span data-ttu-id="ebe07-128">Par exemple, pour une paire BEGIN END où vous tapez d'abord BEGIN suivi de END, la mise en surbrillance s'active lorsque vous tapez la dernière lettre de END.</span><span class="sxs-lookup"><span data-stu-id="ebe07-128">For example, for a BEGIN END pair where you type BEGIN first followed by END, highlighting turns on when you type the final letter in END.</span></span> <span data-ttu-id="ebe07-129">Vous n'avez pas à taper le séparateur de début suivi du séparateur de fin pour activer la mise en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="ebe07-129">You do not have to type the lead delimiter followed by the closing delimiter to turn on highlighting.</span></span> <span data-ttu-id="ebe07-130">Si vous tapez en premier END, puis faites défiler le script vers le haut et tapez BEGIN, la mise en surbrillance est activée lorsque vous tapez la dernière lettre de BEGIN.</span><span class="sxs-lookup"><span data-stu-id="ebe07-130">If you type END first, then scroll back up the script and type BEGIN, highlighting is turned on when you type the final letter in BEGIN.</span></span> <span data-ttu-id="ebe07-131">La dernière lettre tapée n'est pas forcément la dernière lettre du séparateur.</span><span class="sxs-lookup"><span data-stu-id="ebe07-131">The final letter typed does not have to be the end letter in the delimiter.</span></span> <span data-ttu-id="ebe07-132">Par exemple, si vous orthographiez mal BEGIN et tapez BEIN, lorsque vous insérez le G, la paire BEGIN END est mise en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="ebe07-132">For example, you could misspell BEGIN as BEIN, when you insert the final G the BEGIN END pair is highlighted.</span></span>  
  
 <span data-ttu-id="ebe07-133">La paire de séparateurs reste en surbrillance jusqu'à ce que vous déplaciez le curseur.</span><span class="sxs-lookup"><span data-stu-id="ebe07-133">The delimiter pair remains highlighted until you move the cursor.</span></span> <span data-ttu-id="ebe07-134">La mise en surbrillance est désactivée lorsque le curseur est déplacé, même si la nouvelle position du curseur demeure dans le même séparateur.</span><span class="sxs-lookup"><span data-stu-id="ebe07-134">The highlighting is turned off when the cursor is moved, even if the new cursor position remains in the same delimiter.</span></span> <span data-ttu-id="ebe07-135">Vous pouvez réactiver la mise en surbrillance en supprimant et en retapant une lettre de l'un des membres de la paire.</span><span class="sxs-lookup"><span data-stu-id="ebe07-135">You can turn the highlighting back on by deleting and retyping any letter in either member of the pair.</span></span>  
  
## <a name="analysis-services-xmla-query-editor-brace-matching"></a><span data-ttu-id="ebe07-136">Correspondance des accolades de l'éditeur de requête XMLA Analysis Services</span><span class="sxs-lookup"><span data-stu-id="ebe07-136">Analysis Services XMLA Query Editor Brace Matching</span></span>  
 <span data-ttu-id="ebe07-137">La correspondance des accolades de l'éditeur de requête XMLA montre si vous avez fermé des éléments en mettant en surbrillance les accolades d'ouverture et de fermeture.</span><span class="sxs-lookup"><span data-stu-id="ebe07-137">The XMLA Query Editor brace matching shows if you have closed elements by highlighting opening and closing braces.</span></span> <span data-ttu-id="ebe07-138">Vous pouvez également utiliser le raccourci clavier CTRL+] pour passer d'une accolade à l'accolade correspondante.</span><span class="sxs-lookup"><span data-stu-id="ebe07-138">You can also use the CTRL+] keyboard shortcut to jump from one brace to the matching brace.</span></span>  
  
 <span data-ttu-id="ebe07-139">L'éditeur de requête XMLA effectue la correspondance des accolades pour les termes suivants :</span><span class="sxs-lookup"><span data-stu-id="ebe07-139">The XMLA Query Editor does brace matching for the following terms:</span></span>  
  
-   <span data-ttu-id="ebe07-140">Correspondance des balises de début et de fin.</span><span class="sxs-lookup"><span data-stu-id="ebe07-140">Matching start and end tags.</span></span>  
  
-   <span data-ttu-id="ebe07-141">Toute paire de \<" and "> crochets «».</span><span class="sxs-lookup"><span data-stu-id="ebe07-141">Any pair of "\<" and ">" angle brackets.</span></span>  
  
-   <span data-ttu-id="ebe07-142">Début et fin des commentaires.</span><span class="sxs-lookup"><span data-stu-id="ebe07-142">Start and end of comments.</span></span>  
  
-   <span data-ttu-id="ebe07-143">Début et fin des instructions de traitement.</span><span class="sxs-lookup"><span data-stu-id="ebe07-143">Start and end of processing instructions.</span></span>  
  
-   <span data-ttu-id="ebe07-144">Début et fin des blocs CDATA.</span><span class="sxs-lookup"><span data-stu-id="ebe07-144">Start and end of CDATA blocks.</span></span>  
  
-   <span data-ttu-id="ebe07-145">Début et fin des déclarations DTD.</span><span class="sxs-lookup"><span data-stu-id="ebe07-145">Start and end of DTD declarations.</span></span>  
  
-   <span data-ttu-id="ebe07-146">Ouverture et fermeture des guillemets sur les attributs.</span><span class="sxs-lookup"><span data-stu-id="ebe07-146">Opening and closing quotes on attributes.</span></span>  
  
## <a name="mdx-and-dmx-editor-parenthesis-matching"></a><span data-ttu-id="ebe07-147">Correspondance des parenthèses de l'éditeur MDX et DMX</span><span class="sxs-lookup"><span data-stu-id="ebe07-147">MDX and DMX Editor Parenthesis Matching</span></span>  
 <span data-ttu-id="ebe07-148">Les éditeurs MDX (Multi-Dimensional Expressions) et DMX (Data Mining Expressions) font correspondre automatiquement les paires de parenthèses dans les fonctions.</span><span class="sxs-lookup"><span data-stu-id="ebe07-148">The Multi-Dimensional Expressions (MDX) and Data Mining Expressions (DMX) Editors automatically match parenthesis pairs in functions.</span></span>  
  
  
