---
title: MSSQLSERVER_8443 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 8443 (Database Engine error)
ms.assetid: a3541b9c-b1a8-4280-add1-275f08696b62
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ae02cc0d9e5661f4069884c22bf6eea0697bd2d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704111"
---
# <a name="mssqlserver_8443"></a><span data-ttu-id="f40e1-102">MSSQLSERVER_8443</span><span class="sxs-lookup"><span data-stu-id="f40e1-102">MSSQLSERVER_8443</span></span>
    
## <a name="details"></a><span data-ttu-id="f40e1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f40e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f40e1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f40e1-104">Product Name</span></span>|<span data-ttu-id="f40e1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f40e1-105">SQL Server</span></span>|  
|<span data-ttu-id="f40e1-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f40e1-106">Event ID</span></span>|<span data-ttu-id="f40e1-107">8443</span><span class="sxs-lookup"><span data-stu-id="f40e1-107">8443</span></span>|  
|<span data-ttu-id="f40e1-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f40e1-108">Event Source</span></span>|<span data-ttu-id="f40e1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f40e1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f40e1-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f40e1-110">Component</span></span>|<span data-ttu-id="f40e1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f40e1-111">SQLEngine</span></span>|  
|<span data-ttu-id="f40e1-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f40e1-112">Symbolic Name</span></span>|<span data-ttu-id="f40e1-113">SB_DIALOG_WO_CONV_GROUP</span><span class="sxs-lookup"><span data-stu-id="f40e1-113">SB_DIALOG_WO_CONV_GROUP</span></span>|  
|<span data-ttu-id="f40e1-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f40e1-114">Message Text</span></span>|<span data-ttu-id="f40e1-115">La conversation avec l’ID '%.\*ls' et l’initiateur %d fait référence à un groupe de conversations manquant '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="f40e1-115">The conversation with ID '%.\*ls' and initiator %d references a missing conversation group '%.\*ls'.</span></span> <span data-ttu-id="f40e1-116">Exécutez DBCC CHECKDB pour analyser et réparer la base de données.</span><span class="sxs-lookup"><span data-stu-id="f40e1-116">Run DBCC CHECKDB to analyze and repair the database.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f40e1-117">Explication</span><span class="sxs-lookup"><span data-stu-id="f40e1-117">Explanation</span></span>  
 <span data-ttu-id="f40e1-118">La couche de métadonnées a retourné la valeur NULL pour le groupe de conversations.</span><span class="sxs-lookup"><span data-stu-id="f40e1-118">The metadata layer returned NULL for the conversation group.</span></span> <span data-ttu-id="f40e1-119">La base de données a été endommagée d'une certaine façon.</span><span class="sxs-lookup"><span data-stu-id="f40e1-119">The database has been corrupted in some way.</span></span> <span data-ttu-id="f40e1-120">Une erreur de disque est une source d'endommagement possible.</span><span class="sxs-lookup"><span data-stu-id="f40e1-120">One possible source of corruption is a disk error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f40e1-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f40e1-121">User Action</span></span>  
 <span data-ttu-id="f40e1-122">Exécutez DBCC CHECKDB en mode réparation pour ramener la base de données à un état cohérent.</span><span class="sxs-lookup"><span data-stu-id="f40e1-122">Run DBCC CHECKDB in repair mode to bring the database back into a consistent state.</span></span> <span data-ttu-id="f40e1-123">Cela peut entraîner la suppression de messages si cela s'avère nécessaire pour restaurer la cohérence.</span><span class="sxs-lookup"><span data-stu-id="f40e1-123">It may delete messages if necessary to restore consistency.</span></span> <span data-ttu-id="f40e1-124">Examinez les journaux des erreurs du système pour voir si cette erreur a été causée par une autre défaillance dans le système.</span><span class="sxs-lookup"><span data-stu-id="f40e1-124">Investigate system error logs to see if this error was caused by another failure in the system.</span></span>  
  
  
