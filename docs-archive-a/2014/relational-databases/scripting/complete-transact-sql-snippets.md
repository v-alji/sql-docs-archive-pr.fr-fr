---
title: Compléter des extraits de code Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], completing snippets
- snippets [Transact-SQL], completing
- Transact-SQL snippets, completing
ms.assetid: a8316a58-bb57-485e-845f-84c23360314c
author: rothja
ms.author: jroth
ms.openlocfilehash: d90c77f72ba8ce80d26503645d9b04d795f5e503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603896"
---
# <a name="complete-transact-sql-snippets"></a><span data-ttu-id="92ca2-102">Compléter des extraits de code Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92ca2-102">Complete Transact-SQL Snippets</span></span>
  <span data-ttu-id="92ca2-103">Une fois un extrait de code [!INCLUDE[tsql](../../includes/tsql-md.md)] inséré dans un script, vous modifiez le contenu de l'extrait de code pour générer une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] complète.</span><span class="sxs-lookup"><span data-stu-id="92ca2-103">Once a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet has been inserted into a script, you edit the contents of the snippet to build a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="completing-snippets"></a><span data-ttu-id="92ca2-104">Compléter des extraits de code</span><span class="sxs-lookup"><span data-stu-id="92ca2-104">Completing Snippets</span></span>  
 <span data-ttu-id="92ca2-105">Lorsque vous ajoutez un extrait de code [!INCLUDE[tsql](../../includes/tsql-md.md)] à votre script, l'instruction de l'extrait de code insérée présente un ou plusieurs points de remplacement, mis en surbrillance.</span><span class="sxs-lookup"><span data-stu-id="92ca2-105">When you add a [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet to your script, the inserted snippet statement has one or more replacement points, which are highlighted.</span></span> <span data-ttu-id="92ca2-106">Si vous placez le pointeur de votre souris sur un point de remplacement, une info-bulle apparaît avec une description de l'élément syntaxique que vous pouvez spécifier.</span><span class="sxs-lookup"><span data-stu-id="92ca2-106">If you rest your mouse pointer on a replacement point, a tooltip appears with a description of the syntax element you can specify.</span></span> <span data-ttu-id="92ca2-107">L’éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] reconnaît l’extrait de code comme un élément distinct du script environnant jusqu’à ce que vous fermiez le fichier source.</span><span class="sxs-lookup"><span data-stu-id="92ca2-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor recognizes the snippet as separate from the surrounding script until you close the source file.</span></span> <span data-ttu-id="92ca2-108">Les points de remplacement restent actifs jusqu'à la fermeture du fichier source.</span><span class="sxs-lookup"><span data-stu-id="92ca2-108">The replacement points remain active until you close the source file.</span></span>  
  
 <span data-ttu-id="92ca2-109">Vous pouvez également ajouter des éléments syntaxiques supplémentaires au code du modèle inséré par un extrait de code.</span><span class="sxs-lookup"><span data-stu-id="92ca2-109">You can also add additional syntax elements to the template code inserted by a snippet.</span></span> <span data-ttu-id="92ca2-110">Par exemple, le modèle d'extrait de code Create Table génère deux définitions de colonne ; vous devez ajouter des définitions de colonne supplémentaires pour créer une table avec plus de deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="92ca2-110">For example, the Create Table snippet template generates two column definitions; you must add additional column definitions to create a table with more than two columns.</span></span>  
  
#### <a name="completing-the-snippet-statement"></a><span data-ttu-id="92ca2-111">Compléter l'instruction de l'extrait de code</span><span class="sxs-lookup"><span data-stu-id="92ca2-111">Completing the Snippet Statement</span></span>  
  
1.  <span data-ttu-id="92ca2-112">Utilisez la touche TABULATION pour passer d'un point de remplacement au suivant.</span><span class="sxs-lookup"><span data-stu-id="92ca2-112">Use the TAB key to move from one replacement point to the next.</span></span> <span data-ttu-id="92ca2-113">Utilisez SHIFT+TAB pour revenir au point de remplacement précédent.</span><span class="sxs-lookup"><span data-stu-id="92ca2-113">Use SHIFT+TAB to move to the previous replacement point.</span></span>  
  
2.  <span data-ttu-id="92ca2-114">Cliquez sur CTRL+SPACE pour appeler IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="92ca2-114">Click CTRL+SPACE to invoke IntelliSense.</span></span>  
  
3.  <span data-ttu-id="92ca2-115">Sélectionnez un élément dans la liste ou tapez le code de remplacement de votre choix.</span><span class="sxs-lookup"><span data-stu-id="92ca2-115">Select an item from the list, or type a replacement of your choice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ca2-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92ca2-116">See Also</span></span>  
 <span data-ttu-id="92ca2-117">[Insérer des extraits de code Transact-SQL](insert-transact-sql-snippets.md) </span><span class="sxs-lookup"><span data-stu-id="92ca2-117">[Insert Transact-SQL Snippets](insert-transact-sql-snippets.md) </span></span>  
 [<span data-ttu-id="92ca2-118">Insérer des extraits de code d’entourage (surround-with) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92ca2-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
