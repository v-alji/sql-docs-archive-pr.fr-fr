---
title: MSSQLSERVER_1807 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1807 (Database Engine error)
ms.assetid: 13c1b240-098b-4d9e-89aa-21599548e074
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 261d352084e490fb7f9216e1a7e352542e85a6f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604529"
---
# <a name="mssqlserver_1807"></a><span data-ttu-id="66ec1-102">MSSQLSERVER_1807</span><span class="sxs-lookup"><span data-stu-id="66ec1-102">MSSQLSERVER_1807</span></span>
    
## <a name="details"></a><span data-ttu-id="66ec1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="66ec1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="66ec1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="66ec1-104">Product Name</span></span>|<span data-ttu-id="66ec1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="66ec1-105">SQL Server</span></span>|  
|<span data-ttu-id="66ec1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="66ec1-106">Event ID</span></span>|<span data-ttu-id="66ec1-107">1807</span><span class="sxs-lookup"><span data-stu-id="66ec1-107">1807</span></span>|  
|<span data-ttu-id="66ec1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="66ec1-108">Event Source</span></span>|<span data-ttu-id="66ec1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="66ec1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="66ec1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="66ec1-110">Component</span></span>|<span data-ttu-id="66ec1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="66ec1-111">SQLEngine</span></span>|  
|<span data-ttu-id="66ec1-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="66ec1-112">Symbolic Name</span></span>|<span data-ttu-id="66ec1-113">CANNOT_EX_LOCK</span><span class="sxs-lookup"><span data-stu-id="66ec1-113">CANNOT_EX_LOCK</span></span>|  
|<span data-ttu-id="66ec1-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="66ec1-114">Message Text</span></span>|<span data-ttu-id="66ec1-115">Impossible d'obtenir un verrou exclusif sur la base de données '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="66ec1-115">Could not obtain exclusive lock on database '%.\*ls'.</span></span> <span data-ttu-id="66ec1-116">Recommencez l'opération ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="66ec1-116">Retry the operation later.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="66ec1-117">Explication</span><span class="sxs-lookup"><span data-stu-id="66ec1-117">Explanation</span></span>  
 <span data-ttu-id="66ec1-118">Une opération qui requérait un accès exclusif à la base de données n'a pas pu l'obtenir.</span><span class="sxs-lookup"><span data-stu-id="66ec1-118">An operation that required exclusive access to the database was unable to obtain it.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66ec1-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="66ec1-119">User Action</span></span>  
 <span data-ttu-id="66ec1-120">Arrêtez toutes les connexions à cette base de données ou relancez la requête ultérieurement.</span><span class="sxs-lookup"><span data-stu-id="66ec1-120">Disconnect all the connections to that database or try the query again later.</span></span>  
  
  
