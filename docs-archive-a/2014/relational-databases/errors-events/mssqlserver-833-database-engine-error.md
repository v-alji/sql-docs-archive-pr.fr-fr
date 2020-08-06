---
title: MSSQLSERVER_833 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 833 (Database Engine error)
ms.assetid: 14129cc4-be80-4772-9e3f-0e5da4d0696b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8e20018c0fe1cd0748f4930e0022622adcbfad10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605436"
---
# <a name="mssqlserver_833"></a><span data-ttu-id="0b393-102">MSSQLSERVER_833</span><span class="sxs-lookup"><span data-stu-id="0b393-102">MSSQLSERVER_833</span></span>
    
## <a name="details"></a><span data-ttu-id="0b393-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0b393-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b393-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0b393-104">Product Name</span></span>|<span data-ttu-id="0b393-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="0b393-105">SQL Server</span></span>|  
|<span data-ttu-id="0b393-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0b393-106">Event ID</span></span>|<span data-ttu-id="0b393-107">833</span><span class="sxs-lookup"><span data-stu-id="0b393-107">833</span></span>|  
|<span data-ttu-id="0b393-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0b393-108">Event Source</span></span>|<span data-ttu-id="0b393-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="0b393-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="0b393-110">Composant</span><span class="sxs-lookup"><span data-stu-id="0b393-110">Component</span></span>|<span data-ttu-id="0b393-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="0b393-111">SQLEngine</span></span>|  
|<span data-ttu-id="0b393-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="0b393-112">Symbolic Name</span></span>|<span data-ttu-id="0b393-113">BUF_LONG_IO</span><span class="sxs-lookup"><span data-stu-id="0b393-113">BUF_LONG_IO</span></span>|  
|<span data-ttu-id="0b393-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0b393-114">Message Text</span></span>|<span data-ttu-id="0b393-115">SQL Server a rencontré% d occurrence (s) de requêtes d’e/s qui prennent plus de% d secondes à se terminer dans le fichier [% ls] de la base de données `[%ls] (%d)` .</span><span class="sxs-lookup"><span data-stu-id="0b393-115">SQL Server has encountered %d occurrence(s) of I/O requests taking longer than %d seconds to complete on file [%ls] in database`[%ls] (%d)`.</span></span>  <span data-ttu-id="0b393-116">Le descripteur de fichier du système d'exploitation est 0x%p.</span><span class="sxs-lookup"><span data-stu-id="0b393-116">The OS file handle is 0x%p.</span></span>  <span data-ttu-id="0b393-117">Le décalage de la dernière E/S longue est : %#016I64x.</span><span class="sxs-lookup"><span data-stu-id="0b393-117">The offset of the latest long I/O is: %#016I64x.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b393-118">Explication</span><span class="sxs-lookup"><span data-stu-id="0b393-118">Explanation</span></span>  
 <span data-ttu-id="0b393-119">Ce message indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a émis une demande de lecture ou d'écriture à partir du disque et que la demande a mis plus de 15 secondes à retourner un résultat.</span><span class="sxs-lookup"><span data-stu-id="0b393-119">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has issued a read or write request from disk, and that the request has taken longer than 15 seconds to return.</span></span> <span data-ttu-id="0b393-120">Cette erreur est signalée par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et indique un problème avec le sous-système d'E/S.</span><span class="sxs-lookup"><span data-stu-id="0b393-120">This error is reported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and indicates a problem with the IO subsystem.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="0b393-121">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="0b393-121">Possible Causes</span></span>  
 <span data-ttu-id="0b393-122">Cette erreur peut être due à des problèmes de performances du système, à des erreurs matérielles, à des erreurs de microprogramme, à des problèmes de pilote de périphérique ou à l'intervention d'un pilote de filtre dans le processus d'E/S.</span><span class="sxs-lookup"><span data-stu-id="0b393-122">This problem can be caused system performance issues, hardware errors, firmware errors, device driver problems, or filter driver intervention in the IO process.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b393-123">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0b393-123">User Action</span></span>  
 <span data-ttu-id="0b393-124">Essayez de résoudre le problème en recherchant dans le journal des événements système d'éventuels messages d'erreur liés au matériel.</span><span class="sxs-lookup"><span data-stu-id="0b393-124">Troubleshoot this error by examining the system event log for hardware-related error messages.</span></span> <span data-ttu-id="0b393-125">Examinez également les journaux spécifiques au matériel s'ils sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="0b393-125">Also, examine hardware-specific logs if they are available.</span></span>  
  
 <span data-ttu-id="0b393-126">Utilisez l'Analyseur de performances pour consulter les compteurs suivants :</span><span class="sxs-lookup"><span data-stu-id="0b393-126">Use Performance Monitor to examine the following counters:</span></span>  
  
-   <span data-ttu-id="0b393-127">**Moyenne disque s/transfert**</span><span class="sxs-lookup"><span data-stu-id="0b393-127">**Average Disk Sec/Transfer**</span></span>  
  
-   <span data-ttu-id="0b393-128">**Longueur moyenne de la file d’attente du disque**</span><span class="sxs-lookup"><span data-stu-id="0b393-128">**Average Disk Queue Length**</span></span>  
  
-   <span data-ttu-id="0b393-129">**Longueur actuelle de la file d’attente du disque**</span><span class="sxs-lookup"><span data-stu-id="0b393-129">**Current Disk Queue Length**</span></span>  
  
 <span data-ttu-id="0b393-130">Par exemple, la durée **Moyenne disque s/transfert** sur un ordinateur exécutant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est généralement inférieure à 15 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="0b393-130">For example, the **Average Disk Sec/Transfer** time on a computer that is running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is typically less than 15 milliseconds.</span></span> <span data-ttu-id="0b393-131">Si la valeur **Moyenne disque s/transfert** augmente, cela indique que le sous-système d’E/S ne parvient pas parfaitement à suivre la demande d’E/S.</span><span class="sxs-lookup"><span data-stu-id="0b393-131">If the **Average Disk Sec/Transfer** value increases, this indicates that the I/O subsystem is not optimally keeping up with the I/O demand.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0b393-132">L'accès au disque peut être ralenti par un antivirus.</span><span class="sxs-lookup"><span data-stu-id="0b393-132">Disk access can be slowed by an antivirus program.</span></span> <span data-ttu-id="0b393-133">Pour augmenter la vitesse d'accès, excluez des analyses antivirus actives les fichiers de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui sont spécifiés dans le message d'erreur.</span><span class="sxs-lookup"><span data-stu-id="0b393-133">To increase access speed, exclude the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files that are specified in the error message from active virus scans.</span></span>  
  
 <span data-ttu-id="0b393-134">Pour plus d’informations sur les erreurs d’E/S, consultez [Concepts de base des E/S de Microsoft SQL Server, chapitre 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) et l’article de la Base de connaissances disponible à l’adresse [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span><span class="sxs-lookup"><span data-stu-id="0b393-134">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)) and the Knowledge Base article at [https://support.microsoft.com/kb/897284](https://support.microsoft.com/kb/897284).</span></span>  
  
  
