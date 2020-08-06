---
title: Éditeur de tâche d’exécution SQL (page ensemble de résultats) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.resultset.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: d27000c8-8d91-4e1c-b45e-bca9a3c12f6d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 027f3c77e84b47958e9fb6567acdb308c14eb1e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603572"
---
# <a name="execute-sql-task-editor-result-set-page"></a><span data-ttu-id="79dd7-102">Éditeur de tâche d'exécution SQL (page Ensemble de résultats)</span><span class="sxs-lookup"><span data-stu-id="79dd7-102">Execute SQL Task Editor (Result Set Page)</span></span>
  <span data-ttu-id="79dd7-103">Utilisez la page **Jeu de résultats** de la boîte de dialogue **Éditeur de tâche d’exécution de requêtes SQL** pour mapper le résultat de l’instruction SQL à des variables nouvelles ou existantes.</span><span class="sxs-lookup"><span data-stu-id="79dd7-103">Use the **Result Set** page of the **Execute SQL Task Editor** dialog to map the result of the SQL statement to new or existing variables.</span></span> <span data-ttu-id="79dd7-104">Les options de cette boîte de dialogue sont désactivées si **ResultSet** dans la page Général est défini sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="79dd7-104">The options in this dialog box are disabled if **ResultSet** on the General page is set to **None**.</span></span>  
  
 <span data-ttu-id="79dd7-105">Pour plus d’informations sur cette tâche, consultez [Tache d’exécution de requêtes SQL](control-flow/execute-sql-task.md) et [Ensembles de résultats dans la tâche d’exécution SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="79dd7-105">For more information about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="79dd7-106">Options</span><span class="sxs-lookup"><span data-stu-id="79dd7-106">Options</span></span>  
 <span data-ttu-id="79dd7-107">**Nom de résultat**</span><span class="sxs-lookup"><span data-stu-id="79dd7-107">**Result Name**</span></span>  
 <span data-ttu-id="79dd7-108">Après avoir ajouté un ensemble de mappages d’un jeu de résultats en cliquant sur **Ajouter**, donnez un nom au résultat.</span><span class="sxs-lookup"><span data-stu-id="79dd7-108">After you have added a result set mapping set by clicking **Add**, provide a name for the result.</span></span> <span data-ttu-id="79dd7-109">Selon le type de jeu de résultats, vous devez utiliser des noms de résultats spécifiques.</span><span class="sxs-lookup"><span data-stu-id="79dd7-109">Depending on the result set type, you must use specific result names.</span></span>  
  
 <span data-ttu-id="79dd7-110">Si le type de jeu de résultats est **Ligne unique**, le nom peut être celui d’une colonne retournée par la requête ou le numéro qui, dans la liste des colonnes, représente la position d’une colonne retournée par la requête.</span><span class="sxs-lookup"><span data-stu-id="79dd7-110">If the result set type is **Single row**, you can use either the name of a column returned by the query or the number that represents the position of a column in the column list of a column returned by the query.</span></span>  
  
 <span data-ttu-id="79dd7-111">Si le type de l'ensemble de résultats est **Ensemble de résultats complet** ou **XML**, vous devez utiliser 0 comme nom de jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="79dd7-111">If the result set type is **Full result set** or **XML**, you must use 0 as the result set name.</span></span>  
  
 <span data-ttu-id="79dd7-112">**Rubriques connexes**: [Jeux de résultats dans la tâche d’exécution de requêtes SQL](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="79dd7-112">**Related Topics**: [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="79dd7-113">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="79dd7-113">**Variable Name**</span></span>  
 <span data-ttu-id="79dd7-114">Mappez le jeu de résultats à une variable en sélectionnant celle-ci, ou cliquez sur \<**New variable...**> pour ajouter une nouvelle variable par le biais de la boîte de dialogue **Ajouter une variable**.</span><span class="sxs-lookup"><span data-stu-id="79dd7-114">Map the result set to a variable by selecting a variable or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="79dd7-115">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="79dd7-115">**Add**</span></span>  
 <span data-ttu-id="79dd7-116">Ajoute une correspondance de jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="79dd7-116">Click to add a result set mapping.</span></span>  
  
 <span data-ttu-id="79dd7-117">**Remove**</span><span class="sxs-lookup"><span data-stu-id="79dd7-117">**Remove**</span></span>  
 <span data-ttu-id="79dd7-118">Sélectionnez un mappage de jeu de résultats dans la liste, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="79dd7-118">Select a result set mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79dd7-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79dd7-119">See Also</span></span>  
 <span data-ttu-id="79dd7-120">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="79dd7-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="79dd7-121">[Éditeur de tâche d’exécution de SQL &#40;&#41;page général](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="79dd7-121">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="79dd7-122">[Éditeur de tâche d’exécution de SQL &#40;page mappage de paramètre&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span><span class="sxs-lookup"><span data-stu-id="79dd7-122">[Execute SQL Task Editor &#40;Parameter Mapping Page&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span></span>  
 [<span data-ttu-id="79dd7-123">Référence Transact-SQL &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="79dd7-123">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
