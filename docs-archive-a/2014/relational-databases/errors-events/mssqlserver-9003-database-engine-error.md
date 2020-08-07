---
title: MSSQLSERVER_9003 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 9003 (Database Engine error)
ms.assetid: 7fdfb391-5c6f-428b-b434-6c3d0b30fd7b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6f67e4184ea54be6bcd5c2a74d3c0e0711b702f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611803"
---
# <a name="mssqlserver_9003"></a><span data-ttu-id="d5c35-102">MSSQLSERVER_9003</span><span class="sxs-lookup"><span data-stu-id="d5c35-102">MSSQLSERVER_9003</span></span>
    
## <a name="details"></a><span data-ttu-id="d5c35-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d5c35-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5c35-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d5c35-104">Product Name</span></span>|<span data-ttu-id="d5c35-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d5c35-105">SQL Server</span></span>|  
|<span data-ttu-id="d5c35-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d5c35-106">Event ID</span></span>|<span data-ttu-id="d5c35-107">9003</span><span class="sxs-lookup"><span data-stu-id="d5c35-107">9003</span></span>|  
|<span data-ttu-id="d5c35-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d5c35-108">Event Source</span></span>|<span data-ttu-id="d5c35-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d5c35-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d5c35-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d5c35-110">Component</span></span>|<span data-ttu-id="d5c35-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d5c35-111">SQLEngine</span></span>|  
|<span data-ttu-id="d5c35-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d5c35-112">Symbolic Name</span></span>|<span data-ttu-id="d5c35-113">LOG_INVALID_LSN</span><span class="sxs-lookup"><span data-stu-id="d5c35-113">LOG_INVALID_LSN</span></span>|  
|<span data-ttu-id="d5c35-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d5c35-114">Message Text</span></span>|<span data-ttu-id="d5c35-115">Le numéro d'analyse du journal % S_LSN transmis à l'analyse du journal dans la base de données '%.\*ls' n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="d5c35-115">The log scan number %S_LSN passed to log scan in database '%.\*ls' is not valid.</span></span> <span data-ttu-id="d5c35-116">Cette erreur peut indiquer les données sont endommagées ou que le fichier journal (.ldf) ne correspond pas au fichier de données (.mdf).</span><span class="sxs-lookup"><span data-stu-id="d5c35-116">This error may indicate data corruption or that the log file (.ldf) does not match the data file (.mdf).</span></span> <span data-ttu-id="d5c35-117">Si cette erreur s'est produite pendant la réplication, recréez la publication.</span><span class="sxs-lookup"><span data-stu-id="d5c35-117">If this error occurred during replication, re-create the publication.</span></span> <span data-ttu-id="d5c35-118">Sinon, restaurez les données à partir d'une sauvegarde si le problème se traduit par une défaillance lors du démarrage.</span><span class="sxs-lookup"><span data-stu-id="d5c35-118">Otherwise, restore from backup if the problem results in a failure during startup.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5c35-119">Explication</span><span class="sxs-lookup"><span data-stu-id="d5c35-119">Explanation</span></span>  
 <span data-ttu-id="d5c35-120">Un composant a passé un numéro séquentiel dans le journal non valide au gestionnaire de fichiers journaux de la base de données.</span><span class="sxs-lookup"><span data-stu-id="d5c35-120">A component passed an invalid log sequence number to the log manager for the database.</span></span> <span data-ttu-id="d5c35-121">Il peut s'agir d'une réplication, d'une altération ou d'une incohérence entre le fichier de données primaires et le journal.</span><span class="sxs-lookup"><span data-stu-id="d5c35-121">This could be replication, corruption, or an inconsistency between the primary data file and the log.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5c35-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d5c35-122">User Action</span></span>  
 <span data-ttu-id="d5c35-123">Si cela s’est produit pendant la réplication, recréez la publication.</span><span class="sxs-lookup"><span data-stu-id="d5c35-123">If this occurred during replication, recreate the publication.</span></span> <span data-ttu-id="d5c35-124">Sinon, effectuez une restauration à partir de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="d5c35-124">Otherwise, restore from backup.</span></span>  
  
  
