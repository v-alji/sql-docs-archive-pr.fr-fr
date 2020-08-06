---
title: 'Exemple : restauration en ligne d’un fichier en lecture seule (mode de récupération complète) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- full recovery model [SQL Server], RESTORE example
- online restores [SQL Server], full recovery model
- restore sequences [SQL Server], online
ms.assetid: 7ea2d2af-086f-48dc-9636-38dc194c7090
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f493c88d64e6ed22e44f33f1442ae581daa8ed4b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709687"
---
# <a name="example-online-restore-of-a-read-only-file-full-recovery-model"></a><span data-ttu-id="98ab8-102">Exemple : Restauration en ligne d’un fichier en lecture seule (mode de restauration complète)</span><span class="sxs-lookup"><span data-stu-id="98ab8-102">Example: Online Restore of a Read-Only File (Full Recovery Model)</span></span>
  <span data-ttu-id="98ab8-103">Cette rubrique concerne les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui relèvent du mode de récupération complète et qui contiennent plusieurs fichiers ou groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="98ab8-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the full recovery model that contain multiple files or filegroups.</span></span>  
  
 <span data-ttu-id="98ab8-104">Dans cet exemple, une base de données appelée `adb`qui utilise le mode de restauration complète, contient trois groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="98ab8-104">In this example, a database named `adb`, which uses the full recovery model, contains three filegroups.</span></span> <span data-ttu-id="98ab8-105">Le groupe de fichiers `A` est en lecture-écriture, et les groupes de fichiers `B` et `C` sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="98ab8-105">Filegroup `A` is read/write, and filegroup `B` and filegroup `C` are read-only.</span></span> <span data-ttu-id="98ab8-106">Au départ, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="98ab8-106">Initially, all of the filegroups are online.</span></span>  
  
 <span data-ttu-id="98ab8-107">Un fichier en lecture seule `b1`du groupe de fichiers `B` de la base de données `adb` doit être restauré.</span><span class="sxs-lookup"><span data-stu-id="98ab8-107">A read-only file, `b1`, in filegroup `B` of database `adb` has to be restored.</span></span> <span data-ttu-id="98ab8-108">Une sauvegarde ayant été réalisée depuis que le fichier est devenu accessible en lecture seule ; les sauvegardes du journal ne sont pas nécessaires.</span><span class="sxs-lookup"><span data-stu-id="98ab8-108">A backup was taken since the file became read-only; therefore, log backups are not required.</span></span> <span data-ttu-id="98ab8-109">Le groupe de fichiers `B` est hors connexion pendant la restauration, mais le reste de la base de données demeure en ligne.</span><span class="sxs-lookup"><span data-stu-id="98ab8-109">Filegroup `B` is offline for the duration of the restore, but the remainder of the database remains online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="98ab8-110">Séquence de restauration</span><span class="sxs-lookup"><span data-stu-id="98ab8-110">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="98ab8-111">La syntaxe pour une séquence de restauration en ligne est la même que pour une séquence de restauration hors connexion.</span><span class="sxs-lookup"><span data-stu-id="98ab8-111">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="98ab8-112">Pour restaurer le fichier, l'administrateur de la base de données doit utiliser la séquence de restauration suivante :</span><span class="sxs-lookup"><span data-stu-id="98ab8-112">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup  
WITH RECOVERY   
```  
  
 <span data-ttu-id="98ab8-113">Le groupe de fichiers B est maintenant en ligne.</span><span class="sxs-lookup"><span data-stu-id="98ab8-113">Filegroup B is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="98ab8-114">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="98ab8-114">Additional Examples</span></span>  
  
-   [<span data-ttu-id="98ab8-115">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-115">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="98ab8-116">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-116">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="98ab8-117">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-117">Example: Online Restore of a Read-Only File &#40;Simple Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-simple-recovery-model.md)  
  
-   [<span data-ttu-id="98ab8-118">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="98ab8-119">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="98ab8-120">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="98ab8-121"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="98ab8-121">See Also</span></span>  
 <span data-ttu-id="98ab8-122">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ab8-122">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="98ab8-123">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="98ab8-123">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 <span data-ttu-id="98ab8-124">[Restaurations de fichiers &#40;mode de récupération complète&#41;](file-restores-full-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="98ab8-124">[File Restores &#40;Full Recovery Model&#41;](file-restores-full-recovery-model.md) </span></span>  
 [<span data-ttu-id="98ab8-125">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="98ab8-125">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
