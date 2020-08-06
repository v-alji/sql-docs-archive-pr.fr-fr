---
title: Opération de point de contrôle pour les tables optimisées en mémoire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47975bd5-373f-43cd-946a-da8e8088b610
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 07560ea0bf147198fb759f6769ae1c6d5c68a71e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708375"
---
# <a name="checkpoint-operation-for-memory-optimized-tables"></a><span data-ttu-id="338d3-102">Opération de point de contrôle pour les tables mémoire optimisées</span><span class="sxs-lookup"><span data-stu-id="338d3-102">Checkpoint Operation for Memory-Optimized Tables</span></span>
  <span data-ttu-id="338d3-103">Un point de contrôle doit être effectué régulièrement pour que les données mémoire optimisées dans les fichiers de données/delta puissent anticiper la partie active du journal des transactions.</span><span class="sxs-lookup"><span data-stu-id="338d3-103">A checkpoint needs to occur periodically for memory-optimized data in data and delta files to advance the active part of transaction log.</span></span> <span data-ttu-id="338d3-104">Le point de contrôle permet aux tables mémoire optimisées de restaurer ou récupérer le dernier point de contrôle réussi, puis la partie active du journal des transactions est appliquée pour mettre à jour les tables mémoire optimisées afin de terminer la récupération.</span><span class="sxs-lookup"><span data-stu-id="338d3-104">The checkpoint allows memory-optimized tables to restore or recover to the last successful checkpoint and then the active portion of transaction log is applied to update the memory-optimized tables to complete the recovery.</span></span> <span data-ttu-id="338d3-105">Les opérations de point de contrôle des tables sur disque et des tables mémoire optimisées sont des opérations distinctes.</span><span class="sxs-lookup"><span data-stu-id="338d3-105">The checkpoint operation for disk-based tables and memory-optimized tables are distinct operations.</span></span> <span data-ttu-id="338d3-106">La section suivante décrit différents scénarios et le comportement des points de contrôle pour les tables sur disque et les tables mémoire optimisées :</span><span class="sxs-lookup"><span data-stu-id="338d3-106">The following describes different scenarios and the checkpoint behavior for disk-based and memory-optimized tables:</span></span>  
  
## <a name="manual-checkpoint"></a><span data-ttu-id="338d3-107">Point de contrôle manuel</span><span class="sxs-lookup"><span data-stu-id="338d3-107">Manual Checkpoint</span></span>  
 <span data-ttu-id="338d3-108">Lorsque vous définissez un point de contrôle manuel, le point de contrôle des tables sur disque et des tables mémoire optimisées est fermé.</span><span class="sxs-lookup"><span data-stu-id="338d3-108">When you issue a manual checkpoint, it closes the checkpoint for both disk-based and memory-optimized tables.</span></span> <span data-ttu-id="338d3-109">Le fichier de données actif est fermé même s'il est partiellement rempli.</span><span class="sxs-lookup"><span data-stu-id="338d3-109">The active data file is closed even though it may be partially filled.</span></span>  
  
## <a name="automatic-checkpoint"></a><span data-ttu-id="338d3-110">Point de contrôle automatique</span><span class="sxs-lookup"><span data-stu-id="338d3-110">Automatic Checkpoint</span></span>  
 <span data-ttu-id="338d3-111">Le point de contrôle automatique est implémenté différemment pour les tables sur disque et pour les tables mémoire optimisées en raison des différentes méthodes de persistance des données.</span><span class="sxs-lookup"><span data-stu-id="338d3-111">Automatic checkpoint is implemented differently for disk-based and memory-optimized tables because of the different ways the data is persisted.</span></span>  
  
 <span data-ttu-id="338d3-112">Pour les tables sur disque, un point de contrôle automatique est pris en fonction de l’option de configuration de l’intervalle de récupération (pour plus d’informations, consultez [Modifier la durée de récupération cible d’une base de données &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span><span class="sxs-lookup"><span data-stu-id="338d3-112">For disk-based tables, an automatic checkpoint is taken based on the recovery interval configuration option (for more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span></span>  
  
 <span data-ttu-id="338d3-113">Pour les tables mémoire optimisées, un point de contrôle automatique est pris lorsque la taille du fichier journal des transactions devient supérieure à 512 Mo depuis le dernier point de contrôle.</span><span class="sxs-lookup"><span data-stu-id="338d3-113">For memory-optimized tables, an automatic checkpoint is taken when transaction log file becomes bigger than 512 MB since the last checkpoint.</span></span> <span data-ttu-id="338d3-114">Les 512 Mo incluent les enregistrements du journal des transactions à la fois pour les tables sur disque et les tables mémoire optimisées.</span><span class="sxs-lookup"><span data-stu-id="338d3-114">512 MB includes transaction log records for both disk-based and memory-optimized tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338d3-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="338d3-115">See Also</span></span>  
 [<span data-ttu-id="338d3-116">Création et gestion du stockage des objets à mémoire optimisée</span><span class="sxs-lookup"><span data-stu-id="338d3-116">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
