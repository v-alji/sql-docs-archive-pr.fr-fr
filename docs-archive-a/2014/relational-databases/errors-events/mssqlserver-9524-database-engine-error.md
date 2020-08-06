---
title: MSSQLSERVER_9524 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9524 (Database Engine error)
ms.assetid: 12da7931-e124-4466-889c-046f1b7b7bfd
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e6c46ee0ef0bd1be299614e2cb04a3d6cd99d92e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604487"
---
# <a name="mssqlserver_9524"></a><span data-ttu-id="36e31-102">MSSQLSERVER_9524</span><span class="sxs-lookup"><span data-stu-id="36e31-102">MSSQLSERVER_9524</span></span>
    
## <a name="details"></a><span data-ttu-id="36e31-103">Détails</span><span class="sxs-lookup"><span data-stu-id="36e31-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36e31-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="36e31-104">Product Name</span></span>|<span data-ttu-id="36e31-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="36e31-105">SQL Server</span></span>|  
|<span data-ttu-id="36e31-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="36e31-106">Event ID</span></span>|<span data-ttu-id="36e31-107">9254</span><span class="sxs-lookup"><span data-stu-id="36e31-107">9254</span></span>|  
|<span data-ttu-id="36e31-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="36e31-108">Event Source</span></span>|<span data-ttu-id="36e31-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="36e31-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="36e31-110">Composant</span><span class="sxs-lookup"><span data-stu-id="36e31-110">Component</span></span>|<span data-ttu-id="36e31-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="36e31-111">SQLEngine</span></span>|  
|<span data-ttu-id="36e31-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="36e31-112">Symbolic Name</span></span>|<span data-ttu-id="36e31-113">XMLERR_INVALID_COLUMNSET_XML</span><span class="sxs-lookup"><span data-stu-id="36e31-113">XMLERR_INVALID_COLUMNSET_XML</span></span>|  
|<span data-ttu-id="36e31-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="36e31-114">Message Text</span></span>|<span data-ttu-id="36e31-115">Le contenu XML fourni n'est pas conforme au format XML requis pour les jeux de colonnes éparses.</span><span class="sxs-lookup"><span data-stu-id="36e31-115">The XML content provided does not conform to the required XML format for sparse column sets.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="36e31-116">Explication</span><span class="sxs-lookup"><span data-stu-id="36e31-116">Explanation</span></span>  
 <span data-ttu-id="36e31-117">Une tentative de modification d'un jeu de colonnes a été effectuée.</span><span class="sxs-lookup"><span data-stu-id="36e31-117">An attempt was made to modify a column set.</span></span> <span data-ttu-id="36e31-118">Le contenu XML d'un jeu de colonnes doit satisfaire les restrictions de format d'un jeu de colonnes.</span><span class="sxs-lookup"><span data-stu-id="36e31-118">The XML content of a column set must meet the format restrictions of a column set.</span></span> <span data-ttu-id="36e31-119">Le format général d'un jeu de colonnes est le suivant :</span><span class="sxs-lookup"><span data-stu-id="36e31-119">The general format of a column set is as follows:</span></span>  
  
 `<column_name_1>value1</column_name_1><column_name_2>value2</column_name_2>...`  
  
 <span data-ttu-id="36e31-120">Pour plus d'informations sur les jeux de colonnes, consultez la rubrique « Utilisation de jeux de colonnes » dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36e31-120">For more information about column sets, see the topic "Using Column Sets" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36e31-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="36e31-121">User Action</span></span>  
 <span data-ttu-id="36e31-122">Corrigez le format des données XML du jeu de colonnes mentionné dans l'instruction.</span><span class="sxs-lookup"><span data-stu-id="36e31-122">Correct the format of the XML for the column set in the statement.</span></span>  
  
  
