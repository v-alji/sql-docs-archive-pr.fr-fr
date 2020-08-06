---
title: Sauvegarder sur un support de sauvegarde miroir (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
ms.assetid: 5fc43a5d-dfd6-4c53-a4ef-3c8da23ccc81
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 255a3c190139c029f5211dcab9780b6d07d975a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610691"
---
# <a name="back-up-to-a-mirrored-media-set-transact-sql"></a><span data-ttu-id="6855f-102">Sauvegarder sur un support de sauvegarde miroir (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="6855f-102">Back Up to a Mirrored Media Set (Transact-SQL)</span></span>
  <span data-ttu-id="6855f-103">Cette rubrique explique comment utiliser l’instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] [Backup](/sql/t-sql/statements/backup-transact-sql) pour spécifier un support de sauvegarde mis en miroir lors de la sauvegarde d’une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] base de données.</span><span class="sxs-lookup"><span data-stu-id="6855f-103">This topic describes how to use the [!INCLUDE[tsql](../../includes/tsql-md.md)][BACKUP](/sql/t-sql/statements/backup-transact-sql) statement to specify a mirrored media set when backing up a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="6855f-104">Dans l'instruction BACKUP, spécifiez le premier miroir dans la clause TO.</span><span class="sxs-lookup"><span data-stu-id="6855f-104">In your BACKUP statement, specify the first mirror in the TO clause.</span></span> <span data-ttu-id="6855f-105">Spécifiez ensuite chaque miroir dans sa propre clause MIRROR TO.</span><span class="sxs-lookup"><span data-stu-id="6855f-105">Then, specify each mirror in its own MIRROR TO clause.</span></span> <span data-ttu-id="6855f-106">Les clauses TO et MIRROR TO doivent spécifier le même nombre et type d'unités de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="6855f-106">The TO and MIRROR TO clauses must specify the same number and type of backup devices.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6855f-107"> Exemple</span><span class="sxs-lookup"><span data-stu-id="6855f-107">Example</span></span>  
 <span data-ttu-id="6855f-108">L'exemple suivant crée le support de sauvegarde mis en miroir illustré dans la figure précédente et sauvegarde la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] sur les deux miroirs.</span><span class="sxs-lookup"><span data-stu-id="6855f-108">The following example creates the mirrored media set illustrated in the previous illustration and backs up the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database to both mirrors.</span></span>  
  
```  
BACKUP DATABASE AdventureWorks2012  
TO TAPE = '\\.\tape0', TAPE = '\\.\tape1'  
MIRROR TO TAPE = '\\.\tape2', TAPE = '\\.\tape3'  
WITH  
    FORMAT,  
    MEDIANAME = 'AdventureWorks2012Set1';  
GO  
```  
  
## <a name="related-tasks"></a><span data-ttu-id="6855f-109">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="6855f-109">Related Tasks</span></span>  
 <span data-ttu-id="6855f-110">**Pour restaurer une sauvegarde miroir**</span><span class="sxs-lookup"><span data-stu-id="6855f-110">**To restore from a mirrored backup**</span></span>  
  
-   [<span data-ttu-id="6855f-111">RESTORE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6855f-111">RESTORE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/restore-statements-transact-sql)  
  
## <a name="see-also"></a><span data-ttu-id="6855f-112"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6855f-112">See Also</span></span>  
 <span data-ttu-id="6855f-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6855f-113">[BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql) </span></span>  
 [<span data-ttu-id="6855f-114">Jeux de supports de sauvegarde en miroir &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6855f-114">Mirrored Backup Media Sets &#40;SQL Server&#41;</span></span>](mirrored-backup-media-sets-sql-server.md)  
  
  
