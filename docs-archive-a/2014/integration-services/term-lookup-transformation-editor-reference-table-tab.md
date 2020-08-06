---
title: Éditeur de transformation de recherche de terme (onglet table de référence) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.referencetable.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 86ccec6d-615b-4f84-9226-ff80d8012f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f76f15d894896e70139ef80cb2ebad7004ef47ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614164"
---
# <a name="term-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="f72d0-102">Éditeur de transformation de recherche de terme (onglet Table de référence)</span><span class="sxs-lookup"><span data-stu-id="f72d0-102">Term Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="f72d0-103">Utilisez l’onglet **Table de référence** de la boîte de dialogue **Éditeur de transformation de recherche de terme** pour définir la connexion à la table de référence (recherche).</span><span class="sxs-lookup"><span data-stu-id="f72d0-103">Use the **Reference Table** tab of the **Term Lookup Transformation Editor** dialog box to specify the connection to the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="f72d0-104">Pour en savoir plus sur la transformation de recherche de terme, consultez [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="f72d0-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="f72d0-105">Options</span><span class="sxs-lookup"><span data-stu-id="f72d0-105">Options</span></span>  
 <span data-ttu-id="f72d0-106">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="f72d0-106">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="f72d0-107">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez une nouvelle connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f72d0-107">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="f72d0-108">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="f72d0-108">**New**</span></span>  
 <span data-ttu-id="f72d0-109">Crée une connexion en utilisant la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="f72d0-109">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="f72d0-110">**Nom de la table de référence**</span><span class="sxs-lookup"><span data-stu-id="f72d0-110">**Reference table name**</span></span>  
 <span data-ttu-id="f72d0-111">Sélectionnez une table ou une vue de recherche dans la base de données en sélectionnant un élément dans la liste.</span><span class="sxs-lookup"><span data-stu-id="f72d0-111">Select a lookup table or view from the database by selecting an item from the list.</span></span> <span data-ttu-id="f72d0-112">La table ou la vue doit contenir une colonne avec une liste de termes existante à laquelle le texte de la colonne source peut être comparé.</span><span class="sxs-lookup"><span data-stu-id="f72d0-112">The table or view should contain a column with an existing list of terms that the text in the source column can be compared to.</span></span>  
  
 <span data-ttu-id="f72d0-113">**Configurer la sortie d’erreur**</span><span class="sxs-lookup"><span data-stu-id="f72d0-113">**Configure Error Output**</span></span>  
 <span data-ttu-id="f72d0-114">Utilisez la boîte de dialogue [Configurer l’affichage des erreurs](../../2014/integration-services/configure-error-output.md) pour spécifier les options de gestion des erreurs dans les lignes qui provoquent des erreurs.</span><span class="sxs-lookup"><span data-stu-id="f72d0-114">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72d0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f72d0-115">See Also</span></span>  
 <span data-ttu-id="f72d0-116">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="f72d0-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="f72d0-117">[Éditeur de transformation de recherche de terme &#40;onglet recherche de terme&#41;](../../2014/integration-services/term-lookup-transformation-editor-term-lookup-tab.md) </span><span class="sxs-lookup"><span data-stu-id="f72d0-117">[Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-term-lookup-tab.md) </span></span>  
 <span data-ttu-id="f72d0-118">[Éditeur de transformation de recherche de terme &#40;onglet Avancé&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="f72d0-118">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="f72d0-119">Transformation d'extraction de terme</span><span class="sxs-lookup"><span data-stu-id="f72d0-119">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
