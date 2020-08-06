---
title: Les fichiers de sauvegarde doivent se trouver sur des appareils distincts des fichiers de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7039bebb-1f25-4cf3-81f1-393dfb78da12
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d5eff9cb3139e1e1043f99ba63d11160b1010c27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701898"
---
# <a name="backup-files-must-be-on-separate-devices-from-the-database-files"></a><span data-ttu-id="c444a-102">Les fichiers de sauvegarde doivent être placés sur des périphériques distincts des fichiers de base de données</span><span class="sxs-lookup"><span data-stu-id="c444a-102">Backup Files Must Be on Separate Devices from the Database Files</span></span>
  <span data-ttu-id="c444a-103">Cette règle vérifie si les fichiers de base de données sont placés sur des périphériques distincts des fichiers de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c444a-103">This rule checks whether database files are on devices separate from the backup files.</span></span> <span data-ttu-id="c444a-104">Si les fichiers de base de données et les fichiers de sauvegarde sont placés sur le même périphérique et que ce dernier échoue, la base de données et ses sauvegardes ne sont pas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c444a-104">If database files and backup files are on the same device and the device fails, the database and backups will be unavailable.</span></span> <span data-ttu-id="c444a-105">De la même manière, le fait de placer les fichiers de base de données et les fichiers de sauvegarde sur des périphériques distincts optimise les performances d'E/S pour l'utilisation en production de la base de données et l'écriture des sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="c444a-105">Also, putting the database and backup files on the separate devices optimizes the I/O performance for both the production use of the database and the writing of backups.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="c444a-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="c444a-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="c444a-107">Nous vous recommandons vivement de placer la base de données et les sauvegardes sur des périphériques de sauvegarde distincts.</span><span class="sxs-lookup"><span data-stu-id="c444a-107">We strongly recommend that you put the database and backups on separate backup devices.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c444a-108">Cette stratégie ne permet pas de détecter des périphériques physiques distincts par le biais de points de montage.</span><span class="sxs-lookup"><span data-stu-id="c444a-108">This policy cannot detect separate physical devices through mount points.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="c444a-109">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="c444a-109">For More Information</span></span>  
 [<span data-ttu-id="c444a-110">Unités de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="c444a-110">Backup Devices &#40;SQL Server&#41;</span></span>](../relational-databases/backup-restore/backup-devices-sql-server.md)  
  
 [<span data-ttu-id="c444a-111">Sauvegarder et restaurer des bases de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="c444a-111">Back Up and Restore of SQL Server Databases</span></span>](../relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="c444a-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c444a-112">See Also</span></span>  
 [<span data-ttu-id="c444a-113">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="c444a-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
