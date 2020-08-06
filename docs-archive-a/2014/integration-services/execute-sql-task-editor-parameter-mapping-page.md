---
title: Éditeur de tâche d’exécution SQL (page mappage de paramètre) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603573"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a><span data-ttu-id="e292a-102">Éditeur de tâche d'exécution de requête SQL (page Mappage de paramètre)</span><span class="sxs-lookup"><span data-stu-id="e292a-102">Execute SQL Task Editor (Parameter Mapping Page)</span></span>
  <span data-ttu-id="e292a-103">Utilisez la page **Mappage de paramètre** de la boîte de dialogue **Éditeur de tâche d’exécution de requêtes SQL** pour associer des variables à des paramètres dans une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="e292a-103">Use the **Parameter Mapping** page of the **Execute SQL Task Editor** dialog box to map variables to parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="e292a-104">Pour en savoir plus sur cette tâche, consultez [Tache d’exécution de requêtes SQL](control-flow/execute-sql-task.md) et [Paramètres et codes de retour dans la tâche d’exécution SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="e292a-104">To learn about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e292a-105">Options</span><span class="sxs-lookup"><span data-stu-id="e292a-105">Options</span></span>  
 <span data-ttu-id="e292a-106">**Nom de la variable**</span><span class="sxs-lookup"><span data-stu-id="e292a-106">**Variable Name**</span></span>  
 <span data-ttu-id="e292a-107">Après avoir ajouté un mappage de paramètre en cliquant sur **Ajouter**, sélectionnez une variable système ou une variable définie par l’utilisateur dans la liste, ou cliquez sur \<**New variable...**> pour ajouter une nouvelle variable par le biais de la boîte de dialogue **Ajouter une variable**.</span><span class="sxs-lookup"><span data-stu-id="e292a-107">After you have added a parameter mapping by clicking **Add**, select a system or user-defined variable from the list or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="e292a-108">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="e292a-108">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
 <span data-ttu-id="e292a-109">**Sens**</span><span class="sxs-lookup"><span data-stu-id="e292a-109">**Direction**</span></span>  
 <span data-ttu-id="e292a-110">Sélectionnez le sens du paramètre.</span><span class="sxs-lookup"><span data-stu-id="e292a-110">Select the direction of the parameter.</span></span> <span data-ttu-id="e292a-111">Associez chaque variable à un paramètre d'entrée, un paramètre de sortie ou un code de retour.</span><span class="sxs-lookup"><span data-stu-id="e292a-111">Map each variable to an input parameter, output parameter, or a return code.</span></span>  
  
 <span data-ttu-id="e292a-112">**Type de données**</span><span class="sxs-lookup"><span data-stu-id="e292a-112">**Data Type**</span></span>  
 <span data-ttu-id="e292a-113">Sélectionnez le type de données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="e292a-113">Select the data type of the parameter.</span></span> <span data-ttu-id="e292a-114">La liste des types de données disponibles est propre au fournisseur sélectionné dans le gestionnaire de connexions utilisé par la tâche.</span><span class="sxs-lookup"><span data-stu-id="e292a-114">The list of available data types is specific to the provider selected in the connection manager used by the task.</span></span>  
  
 <span data-ttu-id="e292a-115">**Nom du paramètre**</span><span class="sxs-lookup"><span data-stu-id="e292a-115">**Parameter Name**</span></span>  
 <span data-ttu-id="e292a-116">Fournissez un nom de paramètre.</span><span class="sxs-lookup"><span data-stu-id="e292a-116">Provide a parameter name.</span></span>  
  
 <span data-ttu-id="e292a-117">En fonction du type de gestionnaire de connexions que la tâche utilise, vous devez utiliser des nombres ou des noms de paramètres.</span><span class="sxs-lookup"><span data-stu-id="e292a-117">Depending on the connection manager type that the task uses, you must use numbers or parameter names.</span></span> <span data-ttu-id="e292a-118">Certains types de gestionnaires de connexions exigent que le premier caractère du nom de paramètre soit le signe \@, des noms spécifiques tels que \@Param1 ou des noms de colonnes comme noms de paramètres.</span><span class="sxs-lookup"><span data-stu-id="e292a-118">Some connection manager types require that the first character of the parameter name is the \@ sign , specific names like \@Param1, or column names as parameter names.</span></span>  
  
 <span data-ttu-id="e292a-119">**Rubriques connexes :** [Paramètres et codes de retour dans la tâche d’exécution SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="e292a-119">**Related Topics:** [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="e292a-120">**Taille de paramètre**</span><span class="sxs-lookup"><span data-stu-id="e292a-120">**Parameter Size**</span></span>  
 <span data-ttu-id="e292a-121">Indiquez la taille des paramètres qui ont une longueur variable, par exemple les chaînes et champs binaires.</span><span class="sxs-lookup"><span data-stu-id="e292a-121">Provide the size of parameters that have variable length, such as strings and binary fields.</span></span>  
  
 <span data-ttu-id="e292a-122">Ce paramètre garantit que le fournisseur alloue l'espace suffisant pour les valeurs de paramètre à longueur variable.</span><span class="sxs-lookup"><span data-stu-id="e292a-122">This setting ensures that the provider allocates sufficient space for variable-length parameter values.</span></span>  
  
 <span data-ttu-id="e292a-123">**Ajouter**</span><span class="sxs-lookup"><span data-stu-id="e292a-123">**Add**</span></span>  
 <span data-ttu-id="e292a-124">Cliquez pour ajouter une association de paramètre.</span><span class="sxs-lookup"><span data-stu-id="e292a-124">Click to add a parameter mapping.</span></span>  
  
 <span data-ttu-id="e292a-125">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e292a-125">**Remove**</span></span>  
 <span data-ttu-id="e292a-126">Sélectionnez une association de paramètre dans la liste et cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="e292a-126">Select a parameter mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e292a-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e292a-127">See Also</span></span>  
 <span data-ttu-id="e292a-128">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e292a-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e292a-129">[Éditeur de tâche d’exécution de SQL &#40;&#41;page général](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e292a-129">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e292a-130">[Éditeur de tâche d’exécution de SQL &#40;page ensemble de résultats&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span><span class="sxs-lookup"><span data-stu-id="e292a-130">[Execute SQL Task Editor &#40;Result Set Page&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span></span>  
 [<span data-ttu-id="e292a-131">Référence Transact-SQL &#40;moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="e292a-131">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
