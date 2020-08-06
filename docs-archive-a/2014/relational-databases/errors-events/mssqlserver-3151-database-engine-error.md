---
title: MSSQLSERVER_3151 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605478"
---
# <a name="mssqlserver_3151"></a><span data-ttu-id="8cefa-102">MSSQLSERVER_3151</span><span class="sxs-lookup"><span data-stu-id="8cefa-102">MSSQLSERVER_3151</span></span>
    
## <a name="details"></a><span data-ttu-id="8cefa-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8cefa-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cefa-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8cefa-104">Product Name</span></span>|<span data-ttu-id="8cefa-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8cefa-105">SQL Server</span></span>|  
|<span data-ttu-id="8cefa-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8cefa-106">Event ID</span></span>|<span data-ttu-id="8cefa-107">3151</span><span class="sxs-lookup"><span data-stu-id="8cefa-107">3151</span></span>|  
|<span data-ttu-id="8cefa-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8cefa-108">Event Source</span></span>|<span data-ttu-id="8cefa-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8cefa-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8cefa-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8cefa-110">Component</span></span>|<span data-ttu-id="8cefa-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8cefa-111">SQLEngine</span></span>|  
|<span data-ttu-id="8cefa-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8cefa-112">Symbolic Name</span></span>|<span data-ttu-id="8cefa-113">LDDB_MASTER_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="8cefa-113">LDDB_MASTER_LOAD_FAILED</span></span>|  
|<span data-ttu-id="8cefa-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8cefa-114">Message Text</span></span>|<span data-ttu-id="8cefa-115">Échec de la restauration de la base de données master.</span><span class="sxs-lookup"><span data-stu-id="8cefa-115">Failed to restore master database.</span></span> <span data-ttu-id="8cefa-116">Arrêt du serveur SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cefa-116">Shutting down SQL Server.</span></span> <span data-ttu-id="8cefa-117">Check the error logs, and rebuild the master database.</span><span class="sxs-lookup"><span data-stu-id="8cefa-117">Check the error logs, and rebuild the master database.</span></span> <span data-ttu-id="8cefa-118">Pour plus d'informations sur la façon de reconstruire la base de données master, consultez la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cefa-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8cefa-119">Explication</span><span class="sxs-lookup"><span data-stu-id="8cefa-119">Explanation</span></span>  
 <span data-ttu-id="8cefa-120">Ceci est un message d’erreur général qui indique des problèmes variés avec la base de données **MASTER**.</span><span class="sxs-lookup"><span data-stu-id="8cefa-120">This is a general error message indicating various problems with the **master** database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8cefa-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8cefa-121">User Action</span></span>  
 <span data-ttu-id="8cefa-122">Consultez les journaux des erreurs pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="8cefa-122">Check the error logs for more information.</span></span> <span data-ttu-id="8cefa-123">Pour créer une base de données **MASTER** utilisable, exécutez Setup.exe avec l’option REBUILDDATABASE.</span><span class="sxs-lookup"><span data-stu-id="8cefa-123">To create a usable **master** database, run Setup.exe with the REBUILDDATABASE option.</span></span> <span data-ttu-id="8cefa-124">Pour plus d’informations, consultez « Procédure : installer SQL Server à partir de l’invite de commandes » dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cefa-124">For more information see "How to: Install SQL Server from the Command Prompt" in SQL Server Books Online.</span></span>  
  
  
