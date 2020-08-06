---
title: MSSQLSERVER_5237 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 5237 (Database Engine error)
ms.assetid: 9ff28935-d1eb-47ee-99b3-1a65cb948ce7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 224317e290ce15aaed979129733b6273b3b663df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612841"
---
# <a name="mssqlserver_5237"></a><span data-ttu-id="d77e2-102">MSSQLSERVER_5237</span><span class="sxs-lookup"><span data-stu-id="d77e2-102">MSSQLSERVER_5237</span></span>
    
## <a name="details"></a><span data-ttu-id="d77e2-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d77e2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d77e2-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d77e2-104">Product Name</span></span>|<span data-ttu-id="d77e2-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d77e2-105">SQL Server</span></span>|  
|<span data-ttu-id="d77e2-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d77e2-106">Event ID</span></span>|<span data-ttu-id="d77e2-107">5237</span><span class="sxs-lookup"><span data-stu-id="d77e2-107">5237</span></span>|  
|<span data-ttu-id="d77e2-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d77e2-108">Event Source</span></span>|<span data-ttu-id="d77e2-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d77e2-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d77e2-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d77e2-110">Component</span></span>|<span data-ttu-id="d77e2-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d77e2-111">SQLEngine</span></span>|  
|<span data-ttu-id="d77e2-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d77e2-112">Symbolic Name</span></span>|<span data-ttu-id="d77e2-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span><span class="sxs-lookup"><span data-stu-id="d77e2-113">DBCC4_INDEXED_VIEW_CHECK_QUERY_FAILED_NO_ERRORCODE</span></span>|  
|<span data-ttu-id="d77e2-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d77e2-114">Message Text</span></span>|<span data-ttu-id="d77e2-115">Échec de la vérification entre ensembles de lignes DBCC pour l'objet 'NAME' (ID d'objet O_ID) en raison d'une erreur de requête interne.</span><span class="sxs-lookup"><span data-stu-id="d77e2-115">DBCC cross-rowset check failed for object 'NAME' (object ID O_ID) due to an internal query error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d77e2-116">Explication</span><span class="sxs-lookup"><span data-stu-id="d77e2-116">Explanation</span></span>  
 <span data-ttu-id="d77e2-117">Suite à une erreur interne, DBCC n'est pas en mesure d'exécuter la requête pour vérifier des vues indexées.</span><span class="sxs-lookup"><span data-stu-id="d77e2-117">An internal error resulted in DBCC not being able to execute the query to check indexed views.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d77e2-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d77e2-118">User Action</span></span>  
 <span data-ttu-id="d77e2-119">Exécutez de nouveau la commande DBCC.</span><span class="sxs-lookup"><span data-stu-id="d77e2-119">Rerun the DBCC command.</span></span>  
  
  
