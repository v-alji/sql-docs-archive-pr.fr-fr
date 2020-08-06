---
title: MSSQLSERVER_9004 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9004 (Database Engine error)
ms.assetid: b528bb49-340c-4a81-9c8d-cefce6562f16
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 910665b4349e5b13c5abb4fd687dcf0c6fc122cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604492"
---
# <a name="mssqlserver_9004"></a><span data-ttu-id="b700c-102">MSSQLSERVER_9004</span><span class="sxs-lookup"><span data-stu-id="b700c-102">MSSQLSERVER_9004</span></span>
    
## <a name="details"></a><span data-ttu-id="b700c-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b700c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b700c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b700c-104">Product Name</span></span>|<span data-ttu-id="b700c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b700c-105">SQL Server</span></span>|  
|<span data-ttu-id="b700c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b700c-106">Event ID</span></span>|<span data-ttu-id="b700c-107">9004</span><span class="sxs-lookup"><span data-stu-id="b700c-107">9004</span></span>|  
|<span data-ttu-id="b700c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b700c-108">Event Source</span></span>|<span data-ttu-id="b700c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b700c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b700c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b700c-110">Component</span></span>|<span data-ttu-id="b700c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b700c-111">SQLEngine</span></span>|  
|<span data-ttu-id="b700c-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b700c-112">Symbolic Name</span></span>|<span data-ttu-id="b700c-113">LOG_CORRUPT</span><span class="sxs-lookup"><span data-stu-id="b700c-113">LOG_CORRUPT</span></span>|  
|<span data-ttu-id="b700c-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b700c-114">Message Text</span></span>|<span data-ttu-id="b700c-115">Une erreur s'est produite lors du traitement du journal de la base de données '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="b700c-115">An error occurred while processing the log for database '%.\*ls'.</span></span>  <span data-ttu-id="b700c-116">If possible, restore from backup.</span><span class="sxs-lookup"><span data-stu-id="b700c-116">If possible, restore from backup.</span></span> <span data-ttu-id="b700c-117">Si aucune sauvegarde n'est disponible, vous devrez peut-être recréer le journal.</span><span class="sxs-lookup"><span data-stu-id="b700c-117">If a backup is not available, it might be necessary to rebuild the log.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b700c-118">Explication</span><span class="sxs-lookup"><span data-stu-id="b700c-118">Explanation</span></span>  
 <span data-ttu-id="b700c-119">Une erreur s'est produite lors du traitement du journal, au cours d'une annulation, d'une récupération ou d'une réplication.</span><span class="sxs-lookup"><span data-stu-id="b700c-119">An error was encountered while processing the log during rollback, recovery, or replication.</span></span> <span data-ttu-id="b700c-120">Cela peut indiquer une erreur détectée par le système d'exploitation ou une erreur de cohérence interne détectée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b700c-120">This could indicate an error detected by the operating system-or an internal consistency error detected by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b700c-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b700c-121">User Action</span></span>  
 <span data-ttu-id="b700c-122">L'une des actions ci-dessous corrigera cette erreur :</span><span class="sxs-lookup"><span data-stu-id="b700c-122">One of the following actions will correct this error:</span></span>  
  
-   <span data-ttu-id="b700c-123">Effectuez la restauration à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="b700c-123">Restore from a backup.</span></span>  
  
-   <span data-ttu-id="b700c-124">Régénérez le journal.</span><span class="sxs-lookup"><span data-stu-id="b700c-124">Rebuild the log.</span></span>  
  
 <span data-ttu-id="b700c-125">Vérifiez également les journaux des événements et les journaux des erreurs du système qui peuvent être à l'origine du problème.</span><span class="sxs-lookup"><span data-stu-id="b700c-125">Also, check system event and error logs to identify issues within the system that may have caused the problem.</span></span>  
  
  
