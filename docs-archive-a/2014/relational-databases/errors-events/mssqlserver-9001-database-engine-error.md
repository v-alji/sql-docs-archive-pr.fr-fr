---
title: MSSQLSERVER_9001 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9001 (Database Engine error)
ms.assetid: a54de936-90c6-4845-aa96-29d32f154601
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0e61894d0d071fbdb36dcfb77895c46c61d0bbd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704108"
---
# <a name="mssqlserver_9001"></a><span data-ttu-id="9e75a-102">MSSQLSERVER_9001</span><span class="sxs-lookup"><span data-stu-id="9e75a-102">MSSQLSERVER_9001</span></span>
    
## <a name="details"></a><span data-ttu-id="9e75a-103">Détails</span><span class="sxs-lookup"><span data-stu-id="9e75a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9e75a-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="9e75a-104">Product Name</span></span>|<span data-ttu-id="9e75a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e75a-105">SQL Server</span></span>|  
|<span data-ttu-id="9e75a-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="9e75a-106">Event ID</span></span>|<span data-ttu-id="9e75a-107">9001</span><span class="sxs-lookup"><span data-stu-id="9e75a-107">9001</span></span>|  
|<span data-ttu-id="9e75a-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="9e75a-108">Event Source</span></span>|<span data-ttu-id="9e75a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="9e75a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="9e75a-110">Composant</span><span class="sxs-lookup"><span data-stu-id="9e75a-110">Component</span></span>|<span data-ttu-id="9e75a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="9e75a-111">SQLEngine</span></span>|  
|<span data-ttu-id="9e75a-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="9e75a-112">Symbolic Name</span></span>|<span data-ttu-id="9e75a-113">LOG_NOT_AVAIL</span><span class="sxs-lookup"><span data-stu-id="9e75a-113">LOG_NOT_AVAIL</span></span>|  
|<span data-ttu-id="9e75a-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="9e75a-114">Message Text</span></span>|<span data-ttu-id="9e75a-115">Le journal de la base de données '%.\*ls' n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="9e75a-115">The log for database '%.\*ls' is not available.</span></span> <span data-ttu-id="9e75a-116">Consultez le journal des événements pour voir s'il contient des messages d'erreur liés à ce problème.</span><span class="sxs-lookup"><span data-stu-id="9e75a-116">Check the event log for related error messages.</span></span> <span data-ttu-id="9e75a-117">Résolvez toutes les erreurs et redémarrez la base de données.</span><span class="sxs-lookup"><span data-stu-id="9e75a-117">Resolve any errors and restart the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="9e75a-118">Explication</span><span class="sxs-lookup"><span data-stu-id="9e75a-118">Explanation</span></span>  
 <span data-ttu-id="9e75a-119">Le journal de la base de données a été mis hors connexion.</span><span class="sxs-lookup"><span data-stu-id="9e75a-119">The database log was taken offline.</span></span> <span data-ttu-id="9e75a-120">Habituellement cela signifie une panne catastrophique qui nécessite le redémarrage de la base de données.</span><span class="sxs-lookup"><span data-stu-id="9e75a-120">Usually this signifies a catastrophic failure that requires the database to restart.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9e75a-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9e75a-121">User Action</span></span>  
 <span data-ttu-id="9e75a-122">Diagnostiquez d'autres erreurs et redémarrez l'instance de SQL Server si elle n'a pas déjà redémarré.</span><span class="sxs-lookup"><span data-stu-id="9e75a-122">Diagnose other errors and restart the instance of SQL Server if it has not already restarted itself.</span></span>  
  
  
