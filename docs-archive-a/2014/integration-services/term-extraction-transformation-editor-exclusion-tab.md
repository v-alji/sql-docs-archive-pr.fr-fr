---
title: Éditeur de transformation d’extraction de terme (onglet exclusion) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bc4b0401a1dd27111d0498e9e0d848c80da1742
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614168"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a><span data-ttu-id="393d6-102">Éditeur de transformation d'extraction de terme (onglet Exclusion)</span><span class="sxs-lookup"><span data-stu-id="393d6-102">Term Extraction Transformation Editor (Exclusion Tab)</span></span>
  <span data-ttu-id="393d6-103">Utilisez l'onglet **Exclusion** de la boîte de dialogue **Éditeur de transformation d'extraction de terme** pour définir une connexion à une table de connexion et les colonnes qui contiennent des termes d'exclusion.</span><span class="sxs-lookup"><span data-stu-id="393d6-103">Use the **Exclusion** tab of the **Term Extraction Transformation Editor** dialog box to set up a connection to an exclusion table and specify the columns that contain exclusion terms.</span></span>  
  
 <span data-ttu-id="393d6-104">Pour en savoir plus sur la transformation d'extraction de terme, consultez [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="393d6-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="393d6-105">Options</span><span class="sxs-lookup"><span data-stu-id="393d6-105">Options</span></span>  
 <span data-ttu-id="393d6-106">**Utiliser les termes d'exclusion**</span><span class="sxs-lookup"><span data-stu-id="393d6-106">**Use exclusion terms**</span></span>  
 <span data-ttu-id="393d6-107">Indique si vous voulez exclure des termes au cours de l'extraction de termes en définissant une colonne qui contient les termes d'exclusion.</span><span class="sxs-lookup"><span data-stu-id="393d6-107">Indicate whether to exclude specific terms during term extraction by specifying a column that contains exclusion terms.</span></span> <span data-ttu-id="393d6-108">Vous devez définir les propriétés sources suivantes si vous choisissez d'exclure des termes.</span><span class="sxs-lookup"><span data-stu-id="393d6-108">You must specify the following source properties if you choose to exclude terms.</span></span>  
  
 <span data-ttu-id="393d6-109">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="393d6-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="393d6-110">Sélectionnez un gestionnaire de connexions OLE DB existant ou créez une connexion en cliquant sur **Nouvelle**.</span><span class="sxs-lookup"><span data-stu-id="393d6-110">Select an existing OLE DB connection manager, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="393d6-111">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="393d6-111">**New**</span></span>  
 <span data-ttu-id="393d6-112">Créez une connexion à une base de données à l’aide de la boîte de dialogue **Configurer le Gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="393d6-112">Create a new connection to a database by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="393d6-113">**Table ou vue**</span><span class="sxs-lookup"><span data-stu-id="393d6-113">**Table or view**</span></span>  
 <span data-ttu-id="393d6-114">Sélectionnez la table ou la vue qui contient les termes d'exclusion.</span><span class="sxs-lookup"><span data-stu-id="393d6-114">Select the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="393d6-115">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="393d6-115">**Column**</span></span>  
 <span data-ttu-id="393d6-116">Sélectionnez la colonne de la table ou de la vue qui contient les termes d'exclusion.</span><span class="sxs-lookup"><span data-stu-id="393d6-116">Select the column in the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="393d6-117">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="393d6-117">**Configure Error Output**</span></span>  
 <span data-ttu-id="393d6-118">Utilisez la boîte de dialogue [Configurer l’affichage des erreurs](../../2014/integration-services/configure-error-output.md) pour spécifier la gestion des erreurs dans les lignes qui provoquent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="393d6-118">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="393d6-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="393d6-119">See Also</span></span>  
 <span data-ttu-id="393d6-120">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="393d6-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="393d6-121">[Éditeur de transformation d’extraction de terme &#40;onglet extraction de terme&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="393d6-121">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="393d6-122">[Éditeur de transformation d’extraction de terme &#40;onglet Avancé&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="393d6-122">[Term Extraction Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="393d6-123">Transformation de recherche de terme</span><span class="sxs-lookup"><span data-stu-id="393d6-123">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
