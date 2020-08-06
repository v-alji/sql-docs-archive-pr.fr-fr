---
title: MSSQLSERVER_7916 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7916 (Database Engine error)
ms.assetid: 9bac3536-de14-4e98-84c2-bde9a59ba0d1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 21b31eedf61369d9c4d1cfdfd5f53eebd3f5341c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610667"
---
# <a name="mssqlserver_7916"></a><span data-ttu-id="592db-102">MSSQLSERVER_7916</span><span class="sxs-lookup"><span data-stu-id="592db-102">MSSQLSERVER_7916</span></span>
    
## <a name="details"></a><span data-ttu-id="592db-103">Détails</span><span class="sxs-lookup"><span data-stu-id="592db-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="592db-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="592db-104">Product Name</span></span>|<span data-ttu-id="592db-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="592db-105">SQL Server</span></span>|  
|<span data-ttu-id="592db-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="592db-106">Event ID</span></span>|<span data-ttu-id="592db-107">7916</span><span class="sxs-lookup"><span data-stu-id="592db-107">7916</span></span>|  
|<span data-ttu-id="592db-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="592db-108">Event Source</span></span>|<span data-ttu-id="592db-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="592db-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="592db-110">Composant</span><span class="sxs-lookup"><span data-stu-id="592db-110">Component</span></span>|<span data-ttu-id="592db-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="592db-111">SQLEngine</span></span>|  
|<span data-ttu-id="592db-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="592db-112">Symbolic Name</span></span>|<span data-ttu-id="592db-113">DBCC2_REPAIR_RECORD_DELETED</span><span class="sxs-lookup"><span data-stu-id="592db-113">DBCC2_REPAIR_RECORD_DELETED</span></span>|  
|<span data-ttu-id="592db-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="592db-114">Message Text</span></span>|<span data-ttu-id="592db-115">Réparation : enregistrement supprimé pour l’ID d’objet O_ID, ID d’index I_ID, ID de partition PN_ID, ID d’unité d’allocation A_ID (type TYPE), à la page P_ID, emplacement S_ID.</span><span class="sxs-lookup"><span data-stu-id="592db-115">Repair: Deleted record for object ID O_ID, index ID I_ID, partition ID PN_ID, alloc unit ID A_ID (type TYPE), on page P_ID, slot S_ID.</span></span> <span data-ttu-id="592db-116">Les index seront reconstruits.</span><span class="sxs-lookup"><span data-stu-id="592db-116">Indexes will be rebuilt.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="592db-117">Explication</span><span class="sxs-lookup"><span data-stu-id="592db-117">Explanation</span></span>  
 <span data-ttu-id="592db-118">Ceci est un message d'information de REPAIR qui indique que l'enregistrement spécifié a été supprimé de la page.</span><span class="sxs-lookup"><span data-stu-id="592db-118">This is an information messages from REPAIR that indicates the specified record was deleted from the page.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="592db-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="592db-119">User Action</span></span>  
 <span data-ttu-id="592db-120">None</span><span class="sxs-lookup"><span data-stu-id="592db-120">None</span></span>  
  
  
