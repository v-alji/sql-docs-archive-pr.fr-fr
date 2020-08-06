---
title: Définitions de requête incohérentes, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69639
- vdtsql.chm:69640
- vdt.dlgbox.querydefinitionsdiffer
ms.assetid: 90383473-2922-40e5-9682-3850849aa856
author: stevestein
ms.author: sstein
ms.openlocfilehash: b9a39d5d6b739fa4ab1a96ea95b513ecb7f6682f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704652"
---
# <a name="query-definitions-differ-dialog-box-visual-database-tools"></a><span data-ttu-id="88698-102">Définitions de requête incohérentes, boîte de dialogue (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="88698-102">Query Definitions Differ Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="88698-103">Cette boîte de dialogue vous informe que votre requête ne peut pas être représentée graphiquement dans les volets Schéma et Critères, et qu'elle peut être modifiée seulement dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="88698-103">This dialog box notifies you that your query cannot be represented graphically in the Diagram and Criteria panes, and that you can edit your query only in the SQL pane.</span></span>  
  
 <span data-ttu-id="88698-104">Elle peut apparaître quand vous entrez ou modifiez une instruction SQL dans le volet SQL ; vous passez alors à un autre volet, vérifiez la requête ou tentez d’exécuter la requête, et l’une des conditions suivantes s’applique :</span><span class="sxs-lookup"><span data-stu-id="88698-104">This dialog box may appear when you enter or edit an SQL statement in the SQL pane; you then move to another pane, verify the query, or attempt to execute the query; and one of the following conditions applies:</span></span>  
  
-   <span data-ttu-id="88698-105">L'instruction SQL est incomplète ou contient une ou plusieurs erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="88698-105">The SQL statement is incomplete or contains one or more syntax errors.</span></span>  
  
-   <span data-ttu-id="88698-106">L'instruction SQL est valide mais n'est pas prise en charge dans les volets graphiques (par exemple, une requête Union).</span><span class="sxs-lookup"><span data-stu-id="88698-106">The SQL statement is valid but is not supported in the graphical panes (for example, a Union query).</span></span>  
  
-   <span data-ttu-id="88698-107">L'instruction SQL est valide mais contient une syntaxe spécifique à la connexion de données que vous utilisez.</span><span class="sxs-lookup"><span data-stu-id="88698-107">The SQL statement is valid but contains syntax specific to the data connection you are using.</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="88698-108">Vous pouvez vérifier si une instruction est valide à l’aide du bouton **Vérifier l’instruction SQL** situé dans la barre d’outils **Requête** .</span><span class="sxs-lookup"><span data-stu-id="88698-108">You can check whether a statement is valid using the **Verify SQL Statement** button on the **Query** toolbar.</span></span>  
  
 <span data-ttu-id="88698-109">La boîte de dialogue affiche un message expliquant la raison pour laquelle l'instruction SQL ne peut pas être représentée, puis vous demande comment vous souhaitez poursuivre.</span><span class="sxs-lookup"><span data-stu-id="88698-109">The dialog box displays a message with the reason that the SQL statement cannot be represented, and then asks how you want to proceed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88698-110">La boîte de dialogue **Définitions de requête incohérentes** n’apparaît pas si vous avez masqué les volets Schéma et Critères.</span><span class="sxs-lookup"><span data-stu-id="88698-110">The **Query Definitions Differ** dialog box does not appear if you have hidden the Diagram and Criteria panes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="88698-111">Options</span><span class="sxs-lookup"><span data-stu-id="88698-111">Options</span></span>  
 <span data-ttu-id="88698-112">**Bouton Ignorer**</span><span class="sxs-lookup"><span data-stu-id="88698-112">**Ignore Button**</span></span>  
 <span data-ttu-id="88698-113">Choisissez ce bouton pour spécifier que vous acceptez l'instruction SQL, pour la modifier ultérieurement ou pour l'exécuter.</span><span class="sxs-lookup"><span data-stu-id="88698-113">Choose this button to specify that you want to accept the SQL statement, either to edit it further or to execute it.</span></span> <span data-ttu-id="88698-114">Si vous acceptez l'instruction, les volets Schéma et Critères apparaissent estompés pour indiquer qu'ils ne représentent pas l'instruction dans le volet SQL.</span><span class="sxs-lookup"><span data-stu-id="88698-114">If you accept the statement, the Diagram and Criteria panes appear dimmed to indicate that they do not represent the statement in the SQL pane.</span></span>  
  
 <span data-ttu-id="88698-115">**Bouton Annuler**</span><span class="sxs-lookup"><span data-stu-id="88698-115">**Undo Button**</span></span>  
 <span data-ttu-id="88698-116">Choisissez ce bouton pour annuler les modifications que vous avez apportées au volet SQL.</span><span class="sxs-lookup"><span data-stu-id="88698-116">Choose this button to discard your changes to the SQL pane.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="88698-117">Si l'instruction est correcte, mais si sa représentation graphique n'est pas prise en charge par le Concepteur de requêtes et de vues, vous pouvez l'exécuter même si elle ne peut pas être représentée dans les volets Schéma et Critères.</span><span class="sxs-lookup"><span data-stu-id="88698-117">If the statement is correct but not supported graphically by the Query and View Designer, you can execute it even though it cannot be represented in the Diagram and Criteria panes.</span></span> <span data-ttu-id="88698-118">Par exemple, si vous entrez une requête Union, l'instruction peut être exécutée mais pas représentée dans les autres volets.</span><span class="sxs-lookup"><span data-stu-id="88698-118">For example, if you enter a Union query, the statement can be executed but not represented in the other panes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88698-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="88698-119">See Also</span></span>  
 [<span data-ttu-id="88698-120">Outils du concepteur de requêtes et de vues &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="88698-120">Query and View Designer Tools &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
