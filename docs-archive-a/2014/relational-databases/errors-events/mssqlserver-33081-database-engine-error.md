---
title: MSSQLSERVER_33081 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33081 (Database Engine error)
ms.assetid: 839705e7-fa37-4c0d-9f3f-95a9eab98bcf
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0752220cc20641d9b51a3a66fecc86f9efd63433
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604509"
---
# <a name="mssqlserver_33081"></a><span data-ttu-id="e1a90-102">MSSQLSERVER_33081</span><span class="sxs-lookup"><span data-stu-id="e1a90-102">MSSQLSERVER_33081</span></span>
    
## <a name="details"></a><span data-ttu-id="e1a90-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e1a90-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e1a90-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e1a90-104">Product Name</span></span>|<span data-ttu-id="e1a90-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e1a90-105">SQL Server</span></span>|  
|<span data-ttu-id="e1a90-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e1a90-106">Event ID</span></span>|<span data-ttu-id="e1a90-107">33081</span><span class="sxs-lookup"><span data-stu-id="e1a90-107">33081</span></span>|  
|<span data-ttu-id="e1a90-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e1a90-108">Event Source</span></span>|<span data-ttu-id="e1a90-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e1a90-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e1a90-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e1a90-110">Component</span></span>|<span data-ttu-id="e1a90-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e1a90-111">SQLEngine</span></span>|  
|<span data-ttu-id="e1a90-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e1a90-112">Symbolic Name</span></span>|<span data-ttu-id="e1a90-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span><span class="sxs-lookup"><span data-stu-id="e1a90-113">SEC_DLL_TRUST_VERIFICATION_FAILED</span></span>|  
|<span data-ttu-id="e1a90-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e1a90-114">Message Text</span></span>|<span data-ttu-id="e1a90-115">Impossible de charger le fournisseur de services de chiffrement '%.\*ls' en raison d'une signature Authenticode non valide ou d'un chemin d'accès non valide.</span><span class="sxs-lookup"><span data-stu-id="e1a90-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span>  <span data-ttu-id="e1a90-116">Recherchez d'autres défaillances dans les messages précédents.</span><span class="sxs-lookup"><span data-stu-id="e1a90-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e1a90-117">Explication</span><span class="sxs-lookup"><span data-stu-id="e1a90-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e1a90-118">n’a pas pu charger le fournisseur de services de chiffrement répertorié dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="e1a90-118">was unable to load the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="e1a90-119">Il existe plusieurs échecs d'API Windows susceptibles de provoquer cette erreur.</span><span class="sxs-lookup"><span data-stu-id="e1a90-119">There are several Win API failures which might cause this error.</span></span> <span data-ttu-id="e1a90-120">La mémoire tampon en anneau contient le nom de l'API qui a échoué et le code d'erreur windows retourné par l'API.</span><span class="sxs-lookup"><span data-stu-id="e1a90-120">The ring buffer contains the name of the failed API and the Windows error code returned by the API.</span></span> <span data-ttu-id="e1a90-121">Pour obtenir plus d’informations, interrogez la vue sys.dm_os_ring_buffers en utilisant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="e1a90-121">To get more information, query the sys.dm_os_ring_buffers view using the following query.</span></span>  
  
```  
SELECT * FROM sys.dm_os_ring_buffers   
WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
```  
  
## <a name="user-action"></a><span data-ttu-id="e1a90-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e1a90-122">User Action</span></span>  
 <span data-ttu-id="e1a90-123">Pour examiner le problème, recherchez le code d’erreur Windows dans MSDN (https://msdn.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e1a90-123">To investigate the problem, search for the Windows error code in MSDN (https://msdn.microsoft.com/).</span></span> <span data-ttu-id="e1a90-124">Résolvez l'erreur, ou contactez le support technique [!INCLUDE[msCoName](../../includes/msconame-md.md)] pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="e1a90-124">Resolve the error, or contact [!INCLUDE[msCoName](../../includes/msconame-md.md)] CSS for more information.</span></span> <span data-ttu-id="e1a90-125">Si vous devez contacter les services de support technique, collectez les informations suivantes pour notre équipe d'assistance :</span><span class="sxs-lookup"><span data-stu-id="e1a90-125">If you need to contact CSS, collect the following information for our support staff.</span></span>  
  
-   <span data-ttu-id="e1a90-126">Le journal des erreurs affichant l'erreur qui indique que le fournisseur de services de chiffrement n'a pas pu être chargé.</span><span class="sxs-lookup"><span data-stu-id="e1a90-126">The error log showing the failed to load cryptographic provider error.</span></span>  
  
-   <span data-ttu-id="e1a90-127">La sortie à partir de l'instruction ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="e1a90-127">The output from the following statement:</span></span>  
  
    ```  
    SELECT * FROM sys.dm_os_ring_buffers   
    WHERE ring_buffer_type = 'RING_BUFFER_SECURITY_ERROR';  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="e1a90-128">Essayez de collecter des informations de mémoire tampon en anneau rapidement, car les informations de mémoire tampon en anneau peuvent être perdues lors d'un redémarrage.</span><span class="sxs-lookup"><span data-stu-id="e1a90-128">Try to collect the ring buffer information promptly as ring buffer information can be lost during a restart.</span></span>  
  
  
