---
title: MSSQLSERVER_3271 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3271 (Database Engine error)
ms.assetid: 21b8de4b-6624-4163-9561-1a6cc8fe3d51
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 56bdb5875dbba3fbe5037a308d713170a9b6f9ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604512"
---
# <a name="mssqlserver_3271"></a><span data-ttu-id="cc427-102">MSSQLSERVER_3271</span><span class="sxs-lookup"><span data-stu-id="cc427-102">MSSQLSERVER_3271</span></span>
    
## <a name="details"></a><span data-ttu-id="cc427-103">Détails</span><span class="sxs-lookup"><span data-stu-id="cc427-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cc427-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="cc427-104">Product Name</span></span>|<span data-ttu-id="cc427-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="cc427-105">SQL Server</span></span>|  
|<span data-ttu-id="cc427-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="cc427-106">Event ID</span></span>|<span data-ttu-id="cc427-107">3271</span><span class="sxs-lookup"><span data-stu-id="cc427-107">3271</span></span>|  
|<span data-ttu-id="cc427-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="cc427-108">Event Source</span></span>|<span data-ttu-id="cc427-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="cc427-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="cc427-110">Composant</span><span class="sxs-lookup"><span data-stu-id="cc427-110">Component</span></span>|<span data-ttu-id="cc427-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="cc427-111">SQLEngine</span></span>|  
|<span data-ttu-id="cc427-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="cc427-112">Symbolic Name</span></span>|<span data-ttu-id="cc427-113">DMPIO_IO_ERROR</span><span class="sxs-lookup"><span data-stu-id="cc427-113">DMPIO_IO_ERROR</span></span>|  
|<span data-ttu-id="cc427-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="cc427-114">Message Text</span></span>|<span data-ttu-id="cc427-115">Une erreur d'E/S non récupérable s'est produite dans le fichier "%ls" : %ls</span><span class="sxs-lookup"><span data-stu-id="cc427-115">A nonrecoverable I/O error occurred on file "%ls:" %ls.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cc427-116">Explication</span><span class="sxs-lookup"><span data-stu-id="cc427-116">Explanation</span></span>  
 <span data-ttu-id="cc427-117">Il s'agit d'une erreur générale qui survient lorsque le système d'exploitation déclenche une erreur en effectuant une E/S au cours d'une opération de sauvegarde ou de restauration.</span><span class="sxs-lookup"><span data-stu-id="cc427-117">This is a general error that occurs when the operating system raises an error while performing I/O during a backup or restore operation.</span></span> <span data-ttu-id="cc427-118">La cause la plus courante est simplement que le support de sauvegarde est plein.</span><span class="sxs-lookup"><span data-stu-id="cc427-118">In most situations the cause is simply that the backup medium is full.</span></span>  
  
 <span data-ttu-id="cc427-119">L'erreur peut inclure un texte supplémentaire du système d'exploitation indiquant que le disque est plein.</span><span class="sxs-lookup"><span data-stu-id="cc427-119">The error may include additional text from the operating system indicating that the disk is full.</span></span> <span data-ttu-id="cc427-120">Lorsque vous effectuez une opération de sauvegarde ou de restauration à l'aide d'un logiciel tiers de sauvegarde, un message supplémentaire peut s'afficher pour signaler l'échec de la sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="cc427-120">When performing a backup or restore operation with third-party backup software an additional message may occur indicating that the backup failed.</span></span> <span data-ttu-id="cc427-121">Il peut se formuler comme suit :</span><span class="sxs-lookup"><span data-stu-id="cc427-121">The message may look similar to the following text:</span></span>  
  
```  
"2005-08-02 16:05:16.04 spid55 Error: 18210, Severity: 16, State: 1.  
 2005-08-02 16:05:16.04 spid55 BackupVirtualDeviceFile  
::RequestDurableMedia: Flush failure on backup device 'VDINULL'.   
Operating system error 995(The I/O operation has been aborted because   
of either a thread exit or an application request.)."  
```  
  
 <span data-ttu-id="cc427-122">Ceci indique que le logiciel de sauvegarde a demandé l'arrêt de l'opération de sauvegarde ou de restauration.</span><span class="sxs-lookup"><span data-stu-id="cc427-122">This is an indication that the backup software requested a termination of the backup or restore operation.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cc427-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="cc427-123">User Action</span></span>  
 <span data-ttu-id="cc427-124">Effectuez les tâches suivantes comme il convient :</span><span class="sxs-lookup"><span data-stu-id="cc427-124">Perform the following tasks as appropriate:</span></span>  
  
-   <span data-ttu-id="cc427-125">Consultez les messages d'erreur du système sous-jacent et de SQL Server qui ont précédé, afin d'identifier la cause de la défaillance.</span><span class="sxs-lookup"><span data-stu-id="cc427-125">Review the underlying system error messages and SQL Server error messages preceding this one to identify the cause of the failure.</span></span>  
  
-   <span data-ttu-id="cc427-126">Assurez-vous que le support de sauvegarde et de restauration possède suffisamment d'espace.</span><span class="sxs-lookup"><span data-stu-id="cc427-126">Ensure that the backup and restore medium has sufficient space.</span></span>  
  
-   <span data-ttu-id="cc427-127">Corrigez toutes les erreurs déclenchées par le logiciel tiers de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="cc427-127">Correct any errors raised by third-party backup and restore software.</span></span>  
  
  
