---
title: MSSQLSERVER_3937 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3937 (Database Engine error)
ms.assetid: 312d5bbe-c8de-42db-af4b-4ccb448ce6ef
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: cac466e6eb50ad4b7a8848a1159963cb0fd35e22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699629"
---
# <a name="mssqlserver_3937"></a><span data-ttu-id="5df9d-102">MSSQLSERVER_3937</span><span class="sxs-lookup"><span data-stu-id="5df9d-102">MSSQLSERVER_3937</span></span>
    
## <a name="details"></a><span data-ttu-id="5df9d-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5df9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5df9d-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5df9d-104">Product Name</span></span>|<span data-ttu-id="5df9d-105">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5df9d-105">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5df9d-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5df9d-106">Event ID</span></span>|<span data-ttu-id="5df9d-107">3937</span><span class="sxs-lookup"><span data-stu-id="5df9d-107">3937</span></span>|  
|<span data-ttu-id="5df9d-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5df9d-108">Event Source</span></span>|<span data-ttu-id="5df9d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5df9d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5df9d-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5df9d-110">Component</span></span>|<span data-ttu-id="5df9d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5df9d-111">SQLEngine</span></span>|  
|<span data-ttu-id="5df9d-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5df9d-112">Symbolic Name</span></span>|<span data-ttu-id="5df9d-113">XACT_FILESTREAM_ROLLBACK_ERROR</span><span class="sxs-lookup"><span data-stu-id="5df9d-113">XACT_FILESTREAM_ROLLBACK_ERROR</span></span>|  
|<span data-ttu-id="5df9d-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5df9d-114">Message Text</span></span>|<span data-ttu-id="5df9d-115">Une erreur s'est produite en tentant d'avertir le pilote de filtre FILESTREAM qu'une transaction était restaurée.</span><span class="sxs-lookup"><span data-stu-id="5df9d-115">An error occurred while trying to notify the FILESTREAM filter driver that a transaction was rolled back.</span></span> <span data-ttu-id="5df9d-116">Code d’erreur : 0x%0x.</span><span class="sxs-lookup"><span data-stu-id="5df9d-116">Error code: 0x%0x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5df9d-117">Explication</span><span class="sxs-lookup"><span data-stu-id="5df9d-117">Explanation</span></span>  
 <span data-ttu-id="5df9d-118">Une erreur a été retournée par le pilote RsFx lors de la publication d'une notification de restauration pour une transaction.</span><span class="sxs-lookup"><span data-stu-id="5df9d-118">An error was returned by the RsFx driver when issuing a rollback notification for a transaction.</span></span> <span data-ttu-id="5df9d-119">Cela est probablement dû à une insuffisance de ressources.</span><span class="sxs-lookup"><span data-stu-id="5df9d-119">This is probably caused by a resource shortage.</span></span> <span data-ttu-id="5df9d-120">Cela peut provoquer une petite fuite de mémoire dans le pilote de filtre RsFx, mais elle sera libérée lorsque le processus sqlservr.exe qui a créé la transaction se terminera.</span><span class="sxs-lookup"><span data-stu-id="5df9d-120">This can cause a small memory leak in the RsFx filter driver, but this will be freed when the sqlservr.exe process that created the transaction exits.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5df9d-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5df9d-121">User Action</span></span>  
  
