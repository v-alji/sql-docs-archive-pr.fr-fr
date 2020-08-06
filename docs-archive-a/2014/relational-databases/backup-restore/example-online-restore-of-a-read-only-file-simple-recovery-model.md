---
title: 'Exemple : restauration en ligne d’un fichier en lecture seule (mode de récupération simple) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
helpviewer_keywords:
- restore sequences [SQL Server], online
- online restores [SQL Server], simple recovery model
- simple recovery model [SQL Server], RESTORE examples
ms.assetid: 0c691fc6-9865-46a7-b055-8097424492d6
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d84c920a2cb40866ba106b4d30d8e24c4caea611
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709684"
---
# <a name="example-online-restore-of-a-read-only-file-simple-recovery-model"></a><span data-ttu-id="b7091-102">Exemple : Restauration en ligne d’un fichier en lecture seule (Mode de récupération simple)</span><span class="sxs-lookup"><span data-stu-id="b7091-102">Example: Online Restore of a Read-Only File (Simple Recovery Model)</span></span>
  <span data-ttu-id="b7091-103">Cette rubrique concerne les bases de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] obéissant au mode de récupération simple et contenant un groupe de fichiers en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="b7091-103">This topic is relevant for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases under the simple recovery model that contain a read-only filegroup.</span></span> <span data-ttu-id="b7091-104">Avec le mode de récupération simple, un fichier en lecture seule peut être restauré en ligne s'il en existe une sauvegarde créée depuis que le fichier est passé en lecture seule pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="b7091-104">Under the simple recovery model, a read-only file can be restored online if a file backup exists that was taken since the file became read-only for the last time.</span></span>  
  
 <span data-ttu-id="b7091-105">Dans cet exemple, une base de données appelée `adb` contient trois groupes de fichiers.</span><span class="sxs-lookup"><span data-stu-id="b7091-105">In this example, a database named `adb` contains three filegroups.</span></span> <span data-ttu-id="b7091-106">Le groupe de fichiers `A` est en lecture/écriture, et les groupes de fichiers `B` et `C` sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="b7091-106">Filegroup `A` is read/write, and filegroups `B` and `C` are read-only.</span></span> <span data-ttu-id="b7091-107">Au départ, tous les groupes de fichiers sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="b7091-107">Initially, all of the filegroups are online.</span></span> <span data-ttu-id="b7091-108">Un fichier en lecture seule du groupe de fichiers `B`, `b1`doit être restauré.</span><span class="sxs-lookup"><span data-stu-id="b7091-108">A read-only file in filegroup `B`, `b1`, has to be restored.</span></span> <span data-ttu-id="b7091-109">L'administrateur de la base de données peut le restaurer à l'aide d'une sauvegarde créée après que le fichier est passé en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="b7091-109">The database administrator can restore it by using a backup that was taken after the file became read-only.</span></span> <span data-ttu-id="b7091-110">Pendant la durée de la restauration, le groupe de fichiers `B` est hors connexion. Les autres parties de la base de données restent en ligne.</span><span class="sxs-lookup"><span data-stu-id="b7091-110">For the duration of the restore, filegroup `B` will be offline, but the remainder of the database will remain online.</span></span>  
  
## <a name="restore-sequence"></a><span data-ttu-id="b7091-111">Séquence de restauration</span><span class="sxs-lookup"><span data-stu-id="b7091-111">Restore Sequence</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b7091-112">La syntaxe pour une séquence de restauration en ligne est la même que pour une séquence de restauration hors connexion.</span><span class="sxs-lookup"><span data-stu-id="b7091-112">The syntax for an online restore sequence is the same as for an offline restore sequence.</span></span>  
  
 <span data-ttu-id="b7091-113">Pour restaurer le fichier, l'administrateur de la base de données doit utiliser la séquence de restauration suivante :</span><span class="sxs-lookup"><span data-stu-id="b7091-113">To restore the file, the database administrator uses the following restore sequence:</span></span>  
  
```  
RESTORE DATABASE adb FILE='b1' FROM filegroup_B_backup   
WITH RECOVERY  
```  
  
 <span data-ttu-id="b7091-114">Le fichier est en ligne.</span><span class="sxs-lookup"><span data-stu-id="b7091-114">The file is now online.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="b7091-115">Autres exemples</span><span class="sxs-lookup"><span data-stu-id="b7091-115">Additional Examples</span></span>  
  
-   [<span data-ttu-id="b7091-116">Exemple : restauration fragmentaire d’une base de données &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-116">Example: Piecemeal Restore of Database &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-simple-recovery-model.md)  
  
-   [<span data-ttu-id="b7091-117">Exemple : restauration fragmentaire de quelques groupes de fichiers uniquement &#40;mode de récupération simple&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-117">Example: Piecemeal Restore of Only Some Filegroups &#40;Simple Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-simple-recovery-model.md)  
  
-   [<span data-ttu-id="b7091-118">Exemple : restauration fragmentaire d’une base de données &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-118">Example: Piecemeal Restore of Database &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-database-full-recovery-model.md)  
  
-   [<span data-ttu-id="b7091-119">Exemple : restauration fragmentaire de quelques groupes de fichiers &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-119">Example: Piecemeal Restore of Only Some Filegroups &#40;Full Recovery Model&#41;</span></span>](example-piecemeal-restore-of-only-some-filegroups-full-recovery-model.md)  
  
-   [<span data-ttu-id="b7091-120">Exemple : restauration en ligne d’un fichier en lecture/écriture &#40;mode de récupération complète&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-120">Example: Online Restore of a Read-Write File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-write-file-full-recovery-model.md)  
  
-   [<span data-ttu-id="b7091-121">Exemple : restauration en ligne d’un fichier en lecture seule &#40;mode de restauration complète&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-121">Example: Online Restore of a Read-Only File &#40;Full Recovery Model&#41;</span></span>](example-online-restore-of-a-read-only-file-full-recovery-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="b7091-122"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7091-122">See Also</span></span>  
 <span data-ttu-id="b7091-123">[Restauration en ligne &#40;SQL Server&#41;](online-restore-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b7091-123">[Online Restore &#40;SQL Server&#41;](online-restore-sql-server.md) </span></span>  
 <span data-ttu-id="b7091-124">[Restaurations fragmentaires &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b7091-124">[Piecemeal Restores &#40;SQL Server&#41;](piecemeal-restores-sql-server.md) </span></span>  
 <span data-ttu-id="b7091-125">[Restaurations de fichiers &#40;mode de récupération simple&#41;](file-restores-simple-recovery-model.md) </span><span class="sxs-lookup"><span data-stu-id="b7091-125">[File Restores &#40;Simple Recovery Model&#41;](file-restores-simple-recovery-model.md) </span></span>  
 <span data-ttu-id="b7091-126">[Vue d’ensemble de la restauration et de la récupération &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b7091-126">[Restore and Recovery Overview &#40;SQL Server&#41;](restore-and-recovery-overview-sql-server.md) </span></span>  
 [<span data-ttu-id="b7091-127">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="b7091-127">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
  
