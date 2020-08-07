---
title: MSSQLSERVER_847 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 847 (Database Engine error)
ms.assetid: 67208b7c-bd8d-48a1-9f70-a6488e0f5f9b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6b2d5c0a35533700606a44867d2a51cf9087e399
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611817"
---
# <a name="mssqlserver_847"></a><span data-ttu-id="d0f5b-102">MSSQLSERVER_847</span><span class="sxs-lookup"><span data-stu-id="d0f5b-102">MSSQLSERVER_847</span></span>
    
## <a name="details"></a><span data-ttu-id="d0f5b-103">Détails</span><span class="sxs-lookup"><span data-stu-id="d0f5b-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0f5b-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="d0f5b-104">Product Name</span></span>|<span data-ttu-id="d0f5b-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0f5b-105">SQL Server</span></span>|  
|<span data-ttu-id="d0f5b-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="d0f5b-106">Event ID</span></span>|<span data-ttu-id="d0f5b-107">847</span><span class="sxs-lookup"><span data-stu-id="d0f5b-107">847</span></span>|  
|<span data-ttu-id="d0f5b-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="d0f5b-108">Event Source</span></span>|<span data-ttu-id="d0f5b-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d0f5b-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d0f5b-110">Composant</span><span class="sxs-lookup"><span data-stu-id="d0f5b-110">Component</span></span>|<span data-ttu-id="d0f5b-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d0f5b-111">SQLEngine</span></span>|  
|<span data-ttu-id="d0f5b-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="d0f5b-112">Symbolic Name</span></span>|<span data-ttu-id="d0f5b-113">N/A</span><span class="sxs-lookup"><span data-stu-id="d0f5b-113">N/A</span></span>|  
|<span data-ttu-id="d0f5b-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="d0f5b-114">Message Text</span></span>|<span data-ttu-id="d0f5b-115">Un dépassement de délai s’est produit lors de l’attente du verrou : classe '%ls', id %p, type %d, tâche 0x%p : %d, temps d’attente %d, indicateurs 0x%I64x, tâche propriétaire 0x%p.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-115">Time-out occurred while waiting for latch: class '%ls', id %p, type %d, Task 0x%p : %d, waittime %d, flags 0x%I64x, owning task 0x%p.</span></span> <span data-ttu-id="d0f5b-116">Poursuite de l'attente.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-116">Continuing to wait.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d0f5b-117">Explication</span><span class="sxs-lookup"><span data-stu-id="d0f5b-117">Explanation</span></span>  
 <span data-ttu-id="d0f5b-118">Un ordinateur peut ne plus répondre, ou bien un dépassement de délai ou une autre perturbation peuvent se produire, au même moment où [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écrit des erreurs de verrous de tampon dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0f5b-118">A computer might stop responding, or a time-out or some other disruption of regular operations might occur at the same time that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] writes buffer latch errors to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="d0f5b-119">Si le champ des statistiques du message a la valeur 0x04 activée, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attend une opération d'E/S.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-119">If the stat field in the message has the value of 0x04 on, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is waiting for an I/O operation.</span></span> <span data-ttu-id="d0f5b-120">Vous pouvez également recevoir le message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0f5b-120">You may also receive message [MSSQLSERVER_833](mssqlserver-833-database-engine-error.md) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log.</span></span>  
  
 <span data-ttu-id="d0f5b-121">Si le champ des statistiques du message a la valeur 0x04 désactivée, cela signifie qu'il existe une contention importante pour une page.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-121">If the stat field in the message has the value 0x04 off, there is heavy contention for a page.</span></span> <span data-ttu-id="d0f5b-122">Si l'objet est une page de données, une conception de code inefficace peut être à l'origine du problème.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-122">If the object is a data page, this can be caused by inefficient code design.</span></span> <span data-ttu-id="d0f5b-123">Si la page ne contient pas de données, l'erreur peut être causée par des goulots d'étranglement de serveurs tels qu'une insuffisance au niveau des ressources matérielles.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-123">If the page is nondata, the error might be caused by server bottlenecks, such as insufficient hardware resources.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d0f5b-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="d0f5b-124">User Action</span></span>  
 <span data-ttu-id="d0f5b-125">Pour contourner ce problème, une ou plusieurs des étapes suivantes (selon votre environnement) peuvent réduire ou éliminer les messages d'erreur :</span><span class="sxs-lookup"><span data-stu-id="d0f5b-125">To work around this problem, depending on your environment, one or more of the following steps might reduce or eliminate the error messages:</span></span>  
  
-   <span data-ttu-id="d0f5b-126">Déterminez la présence de goulots d'étranglement matériels.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-126">Determine whether you have any hardware bottlenecks.</span></span> <span data-ttu-id="d0f5b-127">Si nécessaire, procédez à une mise à niveau de votre matériel afin que vous puissiez répondre aux exigences de configuration, requête et chargement de votre environnement.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-127">If it is necessary, upgrade your hardware so that it can support the configuration, query, and load requirements of your environment.</span></span> <span data-ttu-id="d0f5b-128">Pour plus d’informations sur les goulots d’étranglement, consultez [Identifier les goulots d’étranglement](../performance/identify-bottlenecks.md).</span><span class="sxs-lookup"><span data-stu-id="d0f5b-128">For more information about bottlenecks, see [Identify Bottlenecks](../performance/identify-bottlenecks.md).</span></span>  
  
-   <span data-ttu-id="d0f5b-129">Vérifiez si vous avez des erreurs dans le journal et exécutez tous les diagnostics que votre fournisseur de matériel vous a procurés.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-129">Check for any logged errors and run any diagnostics provided by your hardware vendor.</span></span>  
  
-   <span data-ttu-id="d0f5b-130">Assurez-vous que vos lecteurs de disque ne sont pas compressés.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-130">Make sure that your disk drives are not compressed.</span></span> <span data-ttu-id="d0f5b-131">Le stockage de données ou de fichiers journaux sur des disques compressés n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-131">Storing data or log files on compressed drives is not supported.</span></span> <span data-ttu-id="d0f5b-132">Pour plus d’informations sur les fichiers physiques, consultez [Groupes de fichiers et fichiers de base de données](../databases/database-files-and-filegroups.md).</span><span class="sxs-lookup"><span data-stu-id="d0f5b-132">For more information about physical files, see [Database Files and Filegroups](../databases/database-files-and-filegroups.md).</span></span>  
  
-   <span data-ttu-id="d0f5b-133">Vérifiez que les messages d'erreur disparaissent lorsque vous désactivez les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d0f5b-133">See whether the error messages disappear when you set the following options to off:</span></span>  
  
    -   <span data-ttu-id="d0f5b-134">Option permettant de configurer le renforcement de la priorité SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0f5b-134">SQL Server priority boost configuration option</span></span>  
  
    -   <span data-ttu-id="d0f5b-135">Option « Regroupement léger » (mode fibre)</span><span class="sxs-lookup"><span data-stu-id="d0f5b-135">Lightweight pooling (fiber mode) option</span></span>  
  
    -   <span data-ttu-id="d0f5b-136">Option « set working set size »</span><span class="sxs-lookup"><span data-stu-id="d0f5b-136">Set working set size option</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d0f5b-137">Les anciens paramètres peuvent souvent s'avérer contre productifs si vous modifiez leur valeur par défaut, OFF.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-137">The previous settings can frequently be counter-productive if you change them from their default setting of OFF.</span></span> <span data-ttu-id="d0f5b-138">Pour plus d’informations sur les paramètres, consultez [Options de configuration de serveur &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d0f5b-138">For more information about the settings, see [Server Configuration Options &#40;SQL Server&#41;](../../database-engine/configure-windows/server-configuration-options-sql-server.md).</span></span>  
  
-   <span data-ttu-id="d0f5b-139">Ajustez les requêtes pour réduire les ressources utilisées sur le système.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-139">Tune queries to reduce resources used on the system.</span></span> <span data-ttu-id="d0f5b-140">Le réglage des performances permettra de réduire l'effort système et d'améliorer le temps de réponse de chaque requête.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-140">Performance tuning will help reduce the stress on a system and improve response time for individual queries.</span></span>  
  
-   <span data-ttu-id="d0f5b-141">Définissez l'option AUTO_SHRINK avec la valeur OFF pour réduire la surcharge qu'entraînent les modifications de taille des bases de données.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-141">Set the AUTO_SHRINK option to OFF to reduce the overhead of changes to the database size.</span></span>  
  
-   <span data-ttu-id="d0f5b-142">Assurez-vous de définir l'option FILEGROWTH avec des incréments suffisamment espacés.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-142">Make sure that you set the FILEGROWTH option to increments that are large enough to be infrequent.</span></span> <span data-ttu-id="d0f5b-143">Planifiez une tâche pour vérifier l'espace disponible dans les bases de données, puis augmentez la taille des bases de données pendant les heures creuses.</span><span class="sxs-lookup"><span data-stu-id="d0f5b-143">Schedule a job to check the available space in the databases, and then increase the database size during nonpeak hours.</span></span>  
  
  
