---
title: Insérer des extraits de code Transact-SQL
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], snippets
- Transact-SQL snippets, code
- snippets [Transact-SQL], how to insert
ms.assetid: d66c96f4-2e84-4d79-9bfd-3635fdd98425
author: rothja
ms.author: jroth
ms.openlocfilehash: 26a7a224e700c726ee3d4437321843d45ddb6e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613971"
---
# <a name="insert-transact-sql-snippets"></a><span data-ttu-id="6d55b-102">Insérer des extraits de code Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d55b-102">Insert Transact-SQL Snippets</span></span>
  <span data-ttu-id="6d55b-103">Un extrait de code [!INCLUDE[tsql](../../includes/tsql-md.md)] est un modèle que vous pouvez utiliser comme point de départ durant l’écriture de nouvelles instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dans l’Éditeur de requête du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d55b-103">A [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet is a template you can use as a starting point when writing new [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor.</span></span>  
  
## <a name="inserting-snippets"></a><span data-ttu-id="6d55b-104">Insertion d'extraits de code</span><span class="sxs-lookup"><span data-stu-id="6d55b-104">Inserting Snippets</span></span>  
 <span data-ttu-id="6d55b-105">Vous pouvez utiliser le menu **Insérer un extrait** pour ouvrir une liste par catégorie d’extraits de code et en choisir un.</span><span class="sxs-lookup"><span data-stu-id="6d55b-105">You can use the **Insert Snippet** menu to open a categorized list of snippets to choose from.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="6d55b-106">Les extraits de code contiennent des points de remplacement : du texte qui suggère la syntaxe pertinente pour ce point.</span><span class="sxs-lookup"><span data-stu-id="6d55b-106">snippets contain replacement points: text that suggests the syntax relevant to that point.</span></span> <span data-ttu-id="6d55b-107">Par exemple, l'extrait de code CREATE TABLE contient des points de remplacement pour des éléments tels que le nom de la table, les noms de colonne et les types de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="6d55b-107">For example, the CREATE TABLE snippet has replacement points for elements such as the table name, column names, and column data types.</span></span> <span data-ttu-id="6d55b-108">Après avoir inséré l'extrait de code, vous devez modifier le texte de remplacement pour former une instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] valide.</span><span class="sxs-lookup"><span data-stu-id="6d55b-108">After inserting the snippet, you must change the replacement text to form a valid [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span> <span data-ttu-id="6d55b-109">Pour plus d’informations, consultez [Compléter des extraits de code Transact-SQL](complete-transact-sql-snippets.md).</span><span class="sxs-lookup"><span data-stu-id="6d55b-109">For more information, see [Complete Transact-SQL Snippets](complete-transact-sql-snippets.md).</span></span>  
  
#### <a name="inserting-a-snippet-by-using-the-insert-snippet-menu"></a><span data-ttu-id="6d55b-110">Insertion d'un extrait de code à l'aide du menu Insérer un extrait</span><span class="sxs-lookup"><span data-stu-id="6d55b-110">Inserting a Snippet by Using the Insert Snippet Menu</span></span>  
  
1.  <span data-ttu-id="6d55b-111">Dans la fenêtre de l’Éditeur de requête [!INCLUDE[ssDE](../../includes/ssde-md.md)] , placez le curseur à l’endroit où vous voulez insérer l’extrait de code [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d55b-111">In the [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window, put the cursor where you want to insert the [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet.</span></span>  
  
2.  <span data-ttu-id="6d55b-112">Lancez l'info-bulle du sélecteur d'extraits de l'une des trois façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="6d55b-112">Launch the snippet picker tooltip in one of three ways:</span></span>  
  
    -   <span data-ttu-id="6d55b-113">Appuyez sur CTRL+K, CTRL+X.</span><span class="sxs-lookup"><span data-stu-id="6d55b-113">Press CTRL+K, CTRL+X.</span></span>  
  
    -   <span data-ttu-id="6d55b-114">Dans le menu **Edition** , pointez sur **IntelliSense**, puis cliquez sur **Insérer un extrait**.</span><span class="sxs-lookup"><span data-stu-id="6d55b-114">On the **Edit** menu, point to **IntelliSense**, then click **Insert Snippet**.</span></span>  
  
    -   <span data-ttu-id="6d55b-115">Cliquez sur le bouton droit de la souris, puis sélectionnez la commande **Insérer un extrait** dans le menu contextuel.</span><span class="sxs-lookup"><span data-stu-id="6d55b-115">Right-click the mouse and then select the **Insert Snippet** command from the shortcut menu.</span></span>  
  
3.  <span data-ttu-id="6d55b-116">Double-cliquez sur l'extrait de code ou sélectionnez l'extrait de code dans le sélecteur d'extraits, puis appuyez sur TABULATION ou ENTRÉE.</span><span class="sxs-lookup"><span data-stu-id="6d55b-116">Double-click the snippet, or select the snippet from the snippet picker and then press TAB or ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d55b-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d55b-117">See Also</span></span>  
 [<span data-ttu-id="6d55b-118">Insérer des extraits de code d’entourage (surround-with) Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="6d55b-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
