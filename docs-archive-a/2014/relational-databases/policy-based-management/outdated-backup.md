---
title: Sauvegarde obsolète | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 307a4ad0-675a-4f97-9a3c-cedd61bdfae5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c6a944b08b15d591a9bbce47a0c0c6a8de3eb54a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611727"
---
# <a name="outdated-backup"></a><span data-ttu-id="8b4b2-102">Sauvegarde obsolète</span><span class="sxs-lookup"><span data-stu-id="8b4b2-102">Outdated Backup</span></span>
  <span data-ttu-id="8b4b2-103">Cette règle vérifie qu'une base de données dispose de sauvegardes récentes.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-103">This rule checks that a database has recent backups.</span></span> <span data-ttu-id="8b4b2-104">La planification de sauvegardes régulières est importante pour éviter les pertes de données pouvant résulter de défaillances diverses.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-104">Scheduling regular backups is important for protecting your databases against data loss from many different failures.</span></span> <span data-ttu-id="8b4b2-105">La fréquence appropriée de sauvegarde des données dépend du mode de récupération de la base de données, des spécifications métier concernant les pertes de données éventuelles et de la fréquence de mise à jour de la base de données.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-105">The appropriate frequency for backing up data depends on the recovery model of the database, on business requirements about potential data loss, and on how frequently the database is updated.</span></span> <span data-ttu-id="8b4b2-106">Dans une base de données fréquemment mise à jour, les risques de perte de travail augmentent relativement vite entre les sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-106">In a frequently updated database, the work-loss exposure increases fairly quickly between backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="8b4b2-107">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="8b4b2-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="8b4b2-108">Nous vous recommandons d'effectuer des sauvegardes suffisamment fréquentes pour protéger les bases de données contre les pertes de données.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-108">We recommend that you perform backups frequently enough to protect databases against data loss.</span></span>  
  
 <span data-ttu-id="8b4b2-109">Le mode de récupération simple et le mode de récupération complète requièrent tous deux des sauvegardes de données.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-109">The simple recovery model and full recovery model both require data backups.</span></span> <span data-ttu-id="8b4b2-110">Dans ces deux modes, vous pouvez compléter vos sauvegardes complètes avec des sauvegardes différentielles de manière à réduire efficacement le risque de perte de données.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-110">For either recovery model, you can supplement your full backups with differential backups to efficiently reduce the risk of data loss.</span></span>  
  
 <span data-ttu-id="8b4b2-111">Pour une base de données qui utilise le mode de récupération simple, nous vous recommandons d'effectuer des sauvegardes fréquentes des journaux.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-111">For a database that uses the full recovery model, we recommend that you take frequent log backups.</span></span> <span data-ttu-id="8b4b2-112">Pour une base de données de production qui contient des données très importantes, les sauvegardes de journaux doivent généralement être effectuées toutes les une à quinze minutes.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-112">For a production database that contains very important data, log backups would typically be taken every one to fifteen minutes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8b4b2-113">La méthode recommandée pour planifier les sauvegardes est un plan de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="8b4b2-113">The recommended method for scheduling backups is a database maintenance plan.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="8b4b2-114">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="8b4b2-114">For More Information</span></span>  
 [<span data-ttu-id="8b4b2-115">Sauvegarde et restauration des bases de données système &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b4b2-115">Back Up and Restore of System Databases &#40;SQL Server&#41;</span></span>](../backup-restore/back-up-and-restore-of-system-databases-sql-server.md)  
  
 [<span data-ttu-id="8b4b2-116">Modes de récupération &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b4b2-116">Recovery Models &#40;SQL Server&#41;</span></span>](../backup-restore/recovery-models-sql-server.md)  
  
 [<span data-ttu-id="8b4b2-117">Créer une sauvegarde différentielle de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b4b2-117">Create a Differential Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-differential-database-backup-sql-server.md)  
  
 [<span data-ttu-id="8b4b2-118">Créer une sauvegarde complète de base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b4b2-118">Create a Full Database Backup &#40;SQL Server&#41;</span></span>](../backup-restore/create-a-full-database-backup-sql-server.md)  
  
 [<span data-ttu-id="8b4b2-119">Plans de maintenance</span><span class="sxs-lookup"><span data-stu-id="8b4b2-119">Maintenance Plans</span></span>](../maintenance-plans/maintenance-plans.md)  
  
 [<span data-ttu-id="8b4b2-120">Sauvegardes des journaux de transactions &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8b4b2-120">Transaction Log Backups &#40;SQL Server&#41;</span></span>](../backup-restore/transaction-log-backups-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="8b4b2-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8b4b2-121">See Also</span></span>  
 [<span data-ttu-id="8b4b2-122">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="8b4b2-122">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
