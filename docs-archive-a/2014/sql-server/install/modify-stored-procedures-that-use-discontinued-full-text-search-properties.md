---
title: Modifier les procédures stockées qui utilisent des propriétés de recherche en texte intégral supprimées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- discontinued properties [Full-Text Search]
- stored procedures [Full-Text Search]
ms.assetid: 8d9392d9-a9ba-4378-84e4-59f516b67ddb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 12262a588742f0e3be094e32a2a0208a85b6f28a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604921"
---
# <a name="modify-stored-procedures-that-use-discontinued-full-text-search-properties"></a><span data-ttu-id="9be3c-102">Modifier les procédures stockées qui utilisent des propriétés de recherche en texte intégral obsolètes</span><span class="sxs-lookup"><span data-stu-id="9be3c-102">Modify stored procedures that use discontinued Full-Text Search properties</span></span>
  <span data-ttu-id="9be3c-103">Pour garantir le bon fonctionnement de vos procédures stockées, vous devez modifier les procédures existantes et supprimer les propriétés et les paramètres liées au texte intégral qui n'existent plus ou sont déconseillés.</span><span class="sxs-lookup"><span data-stu-id="9be3c-103">To ensure that your stored procedures perform correctly, you should edit existing procedures and remove those full-text related properties and settings that have been removed or deprecated.</span></span>  
  
## <a name="component"></a><span data-ttu-id="9be3c-104">Composant</span><span class="sxs-lookup"><span data-stu-id="9be3c-104">Component</span></span>  
 <span data-ttu-id="9be3c-105">Recherche en texte intégral</span><span class="sxs-lookup"><span data-stu-id="9be3c-105">Full-Text Search</span></span>  
  
## <a name="description"></a><span data-ttu-id="9be3c-106">Description</span><span class="sxs-lookup"><span data-stu-id="9be3c-106">Description</span></span>  
 <span data-ttu-id="9be3c-107">Les propriétés et paramètres suivants associés à la recherche en texte intégral ont été supprimés.</span><span class="sxs-lookup"><span data-stu-id="9be3c-107">The following Full-Text Search-related properties and settings have been removed.</span></span>  
  
-   <span data-ttu-id="9be3c-108">**DataTimeout**</span><span class="sxs-lookup"><span data-stu-id="9be3c-108">**DataTimeout**</span></span>  
  
-   <span data-ttu-id="9be3c-109">**ConnectTimeout**</span><span class="sxs-lookup"><span data-stu-id="9be3c-109">**ConnectTimeout**</span></span>  
  
-   <span data-ttu-id="9be3c-110">**Clean_up**</span><span class="sxs-lookup"><span data-stu-id="9be3c-110">**Clean_up**</span></span>  
  
-   <span data-ttu-id="9be3c-111">**LogSize**</span><span class="sxs-lookup"><span data-stu-id="9be3c-111">**LogSize**</span></span>  
  
 <span data-ttu-id="9be3c-112">Les propriétés et paramètres suivants associés à la recherche en texte intégral ont été supprimés ou déconseillés.</span><span class="sxs-lookup"><span data-stu-id="9be3c-112">The following Full-Text Search-related properties and settings have been removed or deprecated:</span></span>  
  
-   <span data-ttu-id="9be3c-113">'Path' du catalogue de texte intégral.</span><span class="sxs-lookup"><span data-stu-id="9be3c-113">'Path' of the Full-Text Catalog.</span></span> <span data-ttu-id="9be3c-114">Le catalogue de texte intégral est un objet logique sans chemin d'accès de fichier spécifique dans le système.</span><span class="sxs-lookup"><span data-stu-id="9be3c-114">The Full-Text Catalog will be a logic object without a specific file path in the system.</span></span>  
  
-   <span data-ttu-id="9be3c-115">L'activation/désactivation de SP_FULLTEXT_DATABASE n'a plus aucun effet puisque les bases de données sont activées pour la recherche en texte intégral à tous moments et par défaut dans [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9be3c-115">Enable/disable in SP_FULLTEXT_DATABASE has no effect anymore as databases are enabled for Full-Text Search at all times and by default in [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="9be3c-116">Action corrective</span><span class="sxs-lookup"><span data-stu-id="9be3c-116">Corrective Action</span></span>  
 <span data-ttu-id="9be3c-117">Modifiez vos procédures stockées de manière à supprimer ces propriétés.</span><span class="sxs-lookup"><span data-stu-id="9be3c-117">Modify your stored procedures to remove these properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9be3c-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9be3c-118">See Also</span></span>  
 [<span data-ttu-id="9be3c-119">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="9be3c-119">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
