---
title: MSSQLSERVER_825 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 825 (Database Engine error)
ms.assetid: f69f8214-5af1-4769-878b-117ad6eaff52
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3b17dfac371ad3c805fdbb0b5d3269fc451dd9d1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604503"
---
# <a name="mssqlserver_825"></a><span data-ttu-id="87e6b-102">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="87e6b-102">MSSQLSERVER_825</span></span>
    
## <a name="details"></a><span data-ttu-id="87e6b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="87e6b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="87e6b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="87e6b-104">Product Name</span></span>|<span data-ttu-id="87e6b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="87e6b-105">SQL Server</span></span>|  
|<span data-ttu-id="87e6b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="87e6b-106">Event ID</span></span>|<span data-ttu-id="87e6b-107">825</span><span class="sxs-lookup"><span data-stu-id="87e6b-107">825</span></span>|  
|<span data-ttu-id="87e6b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="87e6b-108">Event Source</span></span>|<span data-ttu-id="87e6b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="87e6b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="87e6b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="87e6b-110">Component</span></span>|<span data-ttu-id="87e6b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="87e6b-111">SQLEngine</span></span>|  
|<span data-ttu-id="87e6b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="87e6b-112">Symbolic Name</span></span>|<span data-ttu-id="87e6b-113">B_RETRYWORKED</span><span class="sxs-lookup"><span data-stu-id="87e6b-113">B_RETRYWORKED</span></span>|  
|<span data-ttu-id="87e6b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="87e6b-114">Message Text</span></span>|<span data-ttu-id="87e6b-115">La lecture du fichier '%ls' au décalage %#016I64x a réussi après avoir échoué %d fois avec l'erreur %ls.</span><span class="sxs-lookup"><span data-stu-id="87e6b-115">A read of the file '%ls' at offset %#016I64x succeeded after failing %d time(s) with error: %ls.</span></span> <span data-ttu-id="87e6b-116">D'autres messages peuvent fournir davantage d'informations dans le journal des erreurs SQL Server et le journal des événements système.</span><span class="sxs-lookup"><span data-stu-id="87e6b-116">Additional messages in the SQL Server error log and system event log may provide more detail.</span></span> <span data-ttu-id="87e6b-117">Cette condition d'erreur menace l'intégrité de la base de données et elle doit être résolue.</span><span class="sxs-lookup"><span data-stu-id="87e6b-117">This error condition threatens database integrity and must be corrected.</span></span> <span data-ttu-id="87e6b-118">Effectuez une vérification complète de la cohérence de la base de données (DBCC CHECKDB).</span><span class="sxs-lookup"><span data-stu-id="87e6b-118">Complete a full database consistency check (DBCC CHECKDB).</span></span> <span data-ttu-id="87e6b-119">Cette erreur peut avoir de nombreuses causes ; pour plus d'informations, consultez la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="87e6b-119">This error can be caused by many factors; for more information, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="87e6b-120">Explication</span><span class="sxs-lookup"><span data-stu-id="87e6b-120">Explanation</span></span>  
 <span data-ttu-id="87e6b-121">Ce message indique que l'opération de lecture a dû être réexécutée au moins une fois et signale un problème majeur avec le lecteur de disques.</span><span class="sxs-lookup"><span data-stu-id="87e6b-121">This message indicates that the read operation had to be reissued at least one time, and indicates a major problem with the disk hardware.</span></span> <span data-ttu-id="87e6b-122">Ce message n'indique pas pour le moment un problème avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mais le problème de disque peut entraîner la perte de données ou l'altération de bases de données s'il n'est pas résolu.</span><span class="sxs-lookup"><span data-stu-id="87e6b-122">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem, but the disk problem could cause data loss or database corruption if it is not resolved.</span></span> <span data-ttu-id="87e6b-123">Le journal des événements système peut contenir des événements associés qui vous aideront à diagnostiquer le problème.</span><span class="sxs-lookup"><span data-stu-id="87e6b-123">The system event log may contain related events that help to diagnose the problem.</span></span> <span data-ttu-id="87e6b-124">Pour plus d’informations sur les erreurs d’E/S, consultez [Concepts de base des E/S Microsoft SQL Server, chapitre 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="87e6b-124">For more information about I/O errors, see [Microsoft SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10)).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="87e6b-125">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="87e6b-125">User Action</span></span>  
 <span data-ttu-id="87e6b-126">Les actions suivantes peuvent vous aider à identifier et à résoudre le problème sous-jacent :</span><span class="sxs-lookup"><span data-stu-id="87e6b-126">The following actions may help you identify and resolve the underlying problem:</span></span>  
  
-   <span data-ttu-id="87e6b-127">Consultez le journal des erreurs et le texte spécifique de ce message pour trouver des indications expliquant pourquoi le problème s'est produit.</span><span class="sxs-lookup"><span data-stu-id="87e6b-127">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="87e6b-128">Vérifiez votre système de disques.</span><span class="sxs-lookup"><span data-stu-id="87e6b-128">Check your disk system.</span></span> <span data-ttu-id="87e6b-129">Le problème peut être lié aux disques, aux contrôleurs de disques, aux cartes de disques ou aux pilotes de disques.</span><span class="sxs-lookup"><span data-stu-id="87e6b-129">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="87e6b-130">Contactez le fabricant de vos disques pour vous procurer les utilitaires les plus récents afin de vérifier l'état de votre système de disques.</span><span class="sxs-lookup"><span data-stu-id="87e6b-130">Contact the disk manufacturer for the latest utilities for checking the status of your disk system.</span></span>  
  
-   <span data-ttu-id="87e6b-131">Contactez le fabricant de vos disques pour obtenir les dernières mises à jour des pilotes.</span><span class="sxs-lookup"><span data-stu-id="87e6b-131">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
  
