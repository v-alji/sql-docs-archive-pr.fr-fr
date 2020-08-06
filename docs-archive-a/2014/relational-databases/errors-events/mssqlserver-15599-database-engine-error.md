---
title: MSSQLSERVER_15599 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15599 (Database Engine error)
ms.assetid: 97e427a9-8587-46ea-954b-974b5df9c223
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 15f1b3eb6d97837f1c1c4a9944535cade5b31300
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612899"
---
# <a name="mssqlserver_15599"></a><span data-ttu-id="a58c7-102">MSSQLSERVER_15599</span><span class="sxs-lookup"><span data-stu-id="a58c7-102">MSSQLSERVER_15599</span></span>
    
## <a name="details"></a><span data-ttu-id="a58c7-103">Détails</span><span class="sxs-lookup"><span data-stu-id="a58c7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a58c7-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="a58c7-104">Product Name</span></span>|<span data-ttu-id="a58c7-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="a58c7-105">SQL Server</span></span>|  
|<span data-ttu-id="a58c7-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="a58c7-106">Event ID</span></span>|<span data-ttu-id="a58c7-107">15599</span><span class="sxs-lookup"><span data-stu-id="a58c7-107">15599</span></span>|  
|<span data-ttu-id="a58c7-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="a58c7-108">Event Source</span></span>|<span data-ttu-id="a58c7-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="a58c7-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="a58c7-110">Composant</span><span class="sxs-lookup"><span data-stu-id="a58c7-110">Component</span></span>|<span data-ttu-id="a58c7-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="a58c7-111">SQLEngine</span></span>|  
|<span data-ttu-id="a58c7-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="a58c7-112">Symbolic Name</span></span>|<span data-ttu-id="a58c7-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span><span class="sxs-lookup"><span data-stu-id="a58c7-113">SEC_LOCAL_TEMP_AUDIT_PERMISSIONS</span></span>|  
|<span data-ttu-id="a58c7-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="a58c7-114">Message Text</span></span>|<span data-ttu-id="a58c7-115">Impossible de définir l'audit et des autorisations sur des objets temporaires locaux.</span><span class="sxs-lookup"><span data-stu-id="a58c7-115">Auditing and permissions can't be set on local temporary objects.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a58c7-116">Explication</span><span class="sxs-lookup"><span data-stu-id="a58c7-116">Explanation</span></span>  
 <span data-ttu-id="a58c7-117">L'audit et les autorisations n'ont aucun effet une fois définis pour les objets temporaires locaux ou globaux.</span><span class="sxs-lookup"><span data-stu-id="a58c7-117">Auditing and permissions do not have any effect when set for local or global temp objects.</span></span> <span data-ttu-id="a58c7-118">Les instructions ne provoquent pas une erreur (les opérations réussissent), mais n'ont aucun effet.</span><span class="sxs-lookup"><span data-stu-id="a58c7-118">The statements do not result in an error (the operations will return success), but have no effect.</span></span>  
  
 <span data-ttu-id="a58c7-119">Ce comportement n'a pas changé, mais à partir de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], ce message d'information avertit l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a58c7-119">This behavior has not changed, however beginning with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], this informational message alerts the user.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a58c7-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="a58c7-120">User Action</span></span>  
 <span data-ttu-id="a58c7-121">Aucune action n'est nécessaire, mais envisagez de supprimer les instructions qui essaient de définir l'audit ou des autorisations sur les objets temporaires locaux ou globaux.</span><span class="sxs-lookup"><span data-stu-id="a58c7-121">No action is necessary, but consider removing statements that attempt to set auditing or permissions on local or global temp objects.</span></span>  
  
  
