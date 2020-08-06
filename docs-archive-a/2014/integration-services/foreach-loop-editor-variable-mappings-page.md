---
title: Éditeur de boucle foreach (page mappage de variables) | Microsoft Docs
ms.custom: ''
ms.date: 08/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.foreachloopcontainer.mapping.f1
ms.assetid: aa847b87-f391-48a5-9849-eeda2d6b00b9
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd37c8c6c00f18d8b5493a058239cc880ecc1f5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710739"
---
# <a name="foreach-loop-editor-variable-mappings-page"></a><span data-ttu-id="d949d-102">Éditeur de boucle Foreach (page Mappage de variables)</span><span class="sxs-lookup"><span data-stu-id="d949d-102">Foreach Loop Editor (Variable Mappings Page)</span></span>
  <span data-ttu-id="d949d-103">Utilisez la page **Mappage de variables** de la boîte de dialogue **Éditeur de boucle Foreach** pour mapper les variables à la valeur de la collection.</span><span class="sxs-lookup"><span data-stu-id="d949d-103">Use the **Variables Mappings** page of the **Foreach Loop Editor** dialog box to map variables to the collection value.</span></span> <span data-ttu-id="d949d-104">La valeur de cette variable est mise à jour avec les valeurs de la collection à chaque itération de la boucle.</span><span class="sxs-lookup"><span data-stu-id="d949d-104">The value of the variable is updated with the collection values on each iteration of the loop.</span></span>  
  
 <span data-ttu-id="d949d-105">Pour en savoir plus sur l’utilisation du conteneur de boucles Foreach dans un package Integration Services, consultez [Conteneur de boucles Foreach](control-flow/foreach-loop-container.md) .</span><span class="sxs-lookup"><span data-stu-id="d949d-105">To learn about how to use the Foreach Loop container in an Integration Services package,  see [Foreach Loop Container](control-flow/foreach-loop-container.md) .</span></span> <span data-ttu-id="d949d-106">Pour en savoir plus sur la façon de le configurer, consultez [Configurer un conteneur de boucles Foreach](../../2014/integration-services/configure-a-foreach-loop-container.md).</span><span class="sxs-lookup"><span data-stu-id="d949d-106">To learn about how to configure it, see [Configure a Foreach Loop Container](../../2014/integration-services/configure-a-foreach-loop-container.md).</span></span>  
  
 <span data-ttu-id="d949d-107">Le tutoriel « Création d’un package ETL simple » de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] inclut une leçon sur l’ajout et la configuration d’une boucle Foreach.</span><span class="sxs-lookup"><span data-stu-id="d949d-107">The [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] tutorial, Creating a Simple ETL Package Tutorial, includes a lesson that teaches you to add and configure a Foreach Loop.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d949d-108">Options</span><span class="sxs-lookup"><span data-stu-id="d949d-108">Options</span></span>  
 <span data-ttu-id="d949d-109">**Variable**</span><span class="sxs-lookup"><span data-stu-id="d949d-109">**Variable**</span></span>  
 <span data-ttu-id="d949d-110">Sélectionnez une variable existante ou cliquez sur \<**New variable...**> pour en créer une.</span><span class="sxs-lookup"><span data-stu-id="d949d-110">Select an existing variable, or click \<**New variable...**> to create a new variable.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d949d-111">Après avoir mappé une variable, une nouvelle ligne s’ajoute automatiquement à la liste **Variable**.</span><span class="sxs-lookup"><span data-stu-id="d949d-111">After you map a variable, a new row is automatically added to the **Variable** list.</span></span>  
  
 <span data-ttu-id="d949d-112">**Rubriques connexes :** [Variables Integration Services &#40;SSIS&#41;](integration-services-ssis-variables.md), [Ajouter une variable](../../2014/integration-services/add-variable.md)</span><span class="sxs-lookup"><span data-stu-id="d949d-112">**Related Topics**: [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md), [Add Variable](../../2014/integration-services/add-variable.md)</span></span>  
  
 <span data-ttu-id="d949d-113">**Index**</span><span class="sxs-lookup"><span data-stu-id="d949d-113">**Index**</span></span>  
 <span data-ttu-id="d949d-114">Si vous utilisez l'énumérateur Foreach Item, indiquez l'index de la colonne de la valeur de la collection à mapper à la variable.</span><span class="sxs-lookup"><span data-stu-id="d949d-114">If using the Foreach Item enumerator, specify the index of the column in the collection value to map to the variable.</span></span> <span data-ttu-id="d949d-115">Pour les autres types d'énumérateur, l'index est en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="d949d-115">For other enumerator types, the index is read-only.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d949d-116">L'index commence à 0.</span><span class="sxs-lookup"><span data-stu-id="d949d-116">The index is 0-based.</span></span>  
  
 <span data-ttu-id="d949d-117">**Rubrique connexe**: [Effectuer une boucle dans des fichiers et des tables Excel en utilisant un conteneur de boucles Foreach](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span><span class="sxs-lookup"><span data-stu-id="d949d-117">**Related Topics**: [Loop through Excel Files and Tables by Using a Foreach Loop Container](control-flow/loop-through-excel-files-and-tables-by-using-a-foreach-loop-container.md)</span></span>  
  
 <span data-ttu-id="d949d-118">**Supprimer**</span><span class="sxs-lookup"><span data-stu-id="d949d-118">**Delete**</span></span>  
 <span data-ttu-id="d949d-119">Sélectionnez une variable, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="d949d-119">Select a variable, and then click **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d949d-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d949d-120">See Also</span></span>  
 <span data-ttu-id="d949d-121">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="d949d-121">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="d949d-122">[Éditeur de boucle foreach &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="d949d-122">[Foreach Loop Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="d949d-123">[Éditeur de boucle foreach &#40;page de collection&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span><span class="sxs-lookup"><span data-stu-id="d949d-123">[Foreach Loop Editor &#40;Collection Page&#41;](../../2014/integration-services/foreach-loop-editor-collection-page.md) </span></span>  
 <span data-ttu-id="d949d-124">[Page Expressions](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="d949d-124">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="d949d-125">Conteneur de boucles For</span><span class="sxs-lookup"><span data-stu-id="d949d-125">For Loop Container</span></span>](control-flow/for-loop-container.md)  
  
  
