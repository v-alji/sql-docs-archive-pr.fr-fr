---
title: Éditeur de transformation de regroupement probable (onglet Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.connection.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 47b1446d-5331-473c-9cb5-a98b1f55bf5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2a8b0af9f36fdd386f7da375184fd4e4ec5c4be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613017"
---
# <a name="fuzzy-grouping-transformation-editor-connection-manager-tab"></a><span data-ttu-id="53754-102">Éditeur de transformation de regroupement probable (onglet Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="53754-102">Fuzzy Grouping Transformation Editor (Connection Manager Tab)</span></span>
  <span data-ttu-id="53754-103">Utilisez l'onglet **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de transformation de regroupement probable** pour sélectionner une connexion existante ou en créer une.</span><span class="sxs-lookup"><span data-stu-id="53754-103">Use the **Connection Manager** tab of the **Fuzzy Grouping Transformation Editor** dialog box to select an existing connection or create a new one.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53754-104">Le serveur défini par la connexion doit exécuter [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53754-104">The server specified by the connection must be running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="53754-105">La transformation de regroupement probable crée des objets de données temporaires dans tempdb qui peuvent être aussi volumineux que l’ensemble de l’entrée de la transformation.</span><span class="sxs-lookup"><span data-stu-id="53754-105">The Fuzzy Grouping transformation creates temporary data objects in tempdb that may be as large as the full input to the transformation.</span></span> <span data-ttu-id="53754-106">Au cours de son exécution, la transformation envoie des requêtes serveur par rapport aux objets temporaires,</span><span class="sxs-lookup"><span data-stu-id="53754-106">While the transformation executes, it issues server queries against these temporary objects.</span></span> <span data-ttu-id="53754-107">ce qui peut affecter les performances générales du serveur.</span><span class="sxs-lookup"><span data-stu-id="53754-107">This can affect overall server performance.</span></span>  
  
 <span data-ttu-id="53754-108">Pour en savoir plus sur la transformation de regroupement approximatif, consultez [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="53754-108">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="53754-109">Options</span><span class="sxs-lookup"><span data-stu-id="53754-109">Options</span></span>  
 <span data-ttu-id="53754-110">**Gestionnaire de connexions OLE DB**</span><span class="sxs-lookup"><span data-stu-id="53754-110">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="53754-111">Sélectionnez une connexion OLE DB existante en utilisant la zone de liste, ou créez une connexion en utilisant le bouton **Nouvelle** .</span><span class="sxs-lookup"><span data-stu-id="53754-111">Select an existing OLE DB connection manager by using the list box, or create a new connection by using the **New** button.</span></span>  
  
 <span data-ttu-id="53754-112">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="53754-112">**New**</span></span>  
 <span data-ttu-id="53754-113">Crée une connexion en utilisant la boîte de dialogue **Configurer le gestionnaire de connexions OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="53754-113">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53754-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53754-114">See Also</span></span>  
 <span data-ttu-id="53754-115">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="53754-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="53754-116">Identifier des lignes de données semblables à l'aide de la transformation de regroupement probable</span><span class="sxs-lookup"><span data-stu-id="53754-116">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
