---
title: MSSQLSERVER_823 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 823 (Database Engine error)
ms.assetid: 0d9fce3c-3772-46ce-a7a3-4f4988dc6cae
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fa5858bbdc9452a33a3d43fdd783e59556a11e57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605446"
---
# <a name="mssqlserver_823"></a><span data-ttu-id="8cc86-102">MSSQLSERVER_823</span><span class="sxs-lookup"><span data-stu-id="8cc86-102">MSSQLSERVER_823</span></span>
    
## <a name="details"></a><span data-ttu-id="8cc86-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8cc86-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cc86-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8cc86-104">Product Name</span></span>|<span data-ttu-id="8cc86-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="8cc86-105">SQL Server</span></span>|  
|<span data-ttu-id="8cc86-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8cc86-106">Event ID</span></span>|<span data-ttu-id="8cc86-107">823</span><span class="sxs-lookup"><span data-stu-id="8cc86-107">823</span></span>|  
|<span data-ttu-id="8cc86-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8cc86-108">Event Source</span></span>|<span data-ttu-id="8cc86-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="8cc86-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="8cc86-110">Composant</span><span class="sxs-lookup"><span data-stu-id="8cc86-110">Component</span></span>|<span data-ttu-id="8cc86-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="8cc86-111">SQLEngine</span></span>|  
|<span data-ttu-id="8cc86-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="8cc86-112">Symbolic Name</span></span>|<span data-ttu-id="8cc86-113">B_HARDERR</span><span class="sxs-lookup"><span data-stu-id="8cc86-113">B_HARDERR</span></span>|  
|<span data-ttu-id="8cc86-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8cc86-114">Message Text</span></span>|<span data-ttu-id="8cc86-115">Le système d'exploitation a retourné l'erreur %ls à SQL Server pendant une opération de %S_MSG au niveau du décalage %#016I64x dans le fichier '%ls'.</span><span class="sxs-lookup"><span data-stu-id="8cc86-115">The operating system returned error %ls to SQL Server during a %S_MSG at offset %#016I64x in file '%ls'.</span></span> <span data-ttu-id="8cc86-116">D'autres messages peuvent fournir davantage d'informations dans le journal des erreurs SQL Server et le journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="8cc86-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="8cc86-117">Il s'agit d'une condition d'erreur sévère de niveau système qui met en péril l'intégrité de la base de données et qui doit être corrigée immédiatement.</span><span class="sxs-lookup"><span data-stu-id="8cc86-117">This is a severe system-level error condition that threatens database integrity and must be corrected immediately.</span></span> <span data-ttu-id="8cc86-118">Effectuez une vérification complète de la cohérence de la base de données (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="8cc86-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="8cc86-119">Cette erreur peut avoir de nombreuses causes ; pour plus d'informations, consultez la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8cc86-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8cc86-120">Explication</span><span class="sxs-lookup"><span data-stu-id="8cc86-120">Explanation</span></span>  
 <span data-ttu-id="8cc86-121">Une demande de lecture ou d'écriture sous Windows a échoué.</span><span class="sxs-lookup"><span data-stu-id="8cc86-121">A Windows read or write request has failed.</span></span> <span data-ttu-id="8cc86-122">Le code d'erreur retourné par Windows et le texte correspondant sont intégrés au message.</span><span class="sxs-lookup"><span data-stu-id="8cc86-122">The error code that is returned by Windows and the corresponding text are inserted into the message.</span></span> <span data-ttu-id="8cc86-123">Dans le cas de la lecture, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a déjà retenté la demande quatre fois.</span><span class="sxs-lookup"><span data-stu-id="8cc86-123">In the read case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will have already retried the read request four times.</span></span> <span data-ttu-id="8cc86-124">Cette erreur résulte généralement d'un problème matériel, mais elle peut également provenir du pilote de périphérique.</span><span class="sxs-lookup"><span data-stu-id="8cc86-124">This error is often the result of a hardware error, but may be caused by the device driver.</span></span> <span data-ttu-id="8cc86-125">Pour plus d’informations sur l’erreur 823, consultez [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339) .</span><span class="sxs-lookup"><span data-stu-id="8cc86-125">For more information about error 823, see [https://support.microsoft.com/kb/828339](https://support.microsoft.com/kb/828339).</span></span> <span data-ttu-id="8cc86-126">Pour plus d’informations sur les erreurs d’E/S, consultez [Concepts de base des E/S Microsoft SQL Server, chapitre 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="8cc86-126">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8cc86-127">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8cc86-127">User Action</span></span>  
 <span data-ttu-id="8cc86-128">Cherchez des informations supplémentaires dans le journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="8cc86-128">Check for additional information in the system event log.</span></span> <span data-ttu-id="8cc86-129">Contactez le fabricant du matériel ou le service clientèle et support technique de Microsoft pour déterminer la cause et l'action corrective à entreprendre.</span><span class="sxs-lookup"><span data-stu-id="8cc86-129">Contact the hardware manufacturer or Microsoft Customer Services and Support to determine the cause and corrective action.</span></span> <span data-ttu-id="8cc86-130">Une fois l'erreur matérielle corrigée, restaurez toutes les bases de données et exécutez DBCC CHECKDB.</span><span class="sxs-lookup"><span data-stu-id="8cc86-130">After the hardware error is fixed, restore all databases and run DBCC CHECKDB.</span></span>  
  
  
