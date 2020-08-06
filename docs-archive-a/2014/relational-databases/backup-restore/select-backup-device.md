---
title: Sélectionner l’unité de sauvegarde | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.selectbackupdevice.f1
ms.assetid: 7887c9fd-15ce-4cc8-b069-845c1d09088c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8a848f9188eec0ebb09931bca460b0389b9570ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705188"
---
# <a name="select-backup-device"></a><span data-ttu-id="165da-102">Sélectionner l'unité de sauvegarde</span><span class="sxs-lookup"><span data-stu-id="165da-102">Select Backup Device</span></span>
  <span data-ttu-id="165da-103">La boîte de dialogue **Sélectionner l'unité de sauvegarde** vous permet de sélectionner une unité logique de sauvegarde pour l'opération de restauration.</span><span class="sxs-lookup"><span data-stu-id="165da-103">Use the **Select Backup Device** dialog box to select a logical backup device for the restore operation.</span></span>  
  
 <span data-ttu-id="165da-104">Une unité logique de sauvegarde est une unité logique définie par l'utilisateur et qui correspond à une unité physique, telle qu'un lecteur de bande ou un lecteur de disque, et fournie par le système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="165da-104">A logical backup device is a user-defined logical device that corresponds to a physical device, either a tape drive or a disk drive, that is provided by the operating system.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="165da-105">Si une sauvegarde utilise plusieurs unités de sauvegarde, elles doivent toutes correspondre à un même type d'unité.</span><span class="sxs-lookup"><span data-stu-id="165da-105">If a backup uses multiple backup devices, they all must correspond to a single type of device.</span></span>  
  
 <span data-ttu-id="165da-106">**Pour utiliser SQL Server Management Studio pour afficher le contenu d'une unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="165da-106">**To use SQL Server Management Studio to view the contents of a backup device**</span></span>  
  
-   [<span data-ttu-id="165da-107">Afficher le contenu d’un fichier ou d’une bande de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="165da-107">View the Contents of a Backup Tape or File &#40;SQL Server&#41;</span></span>](view-the-contents-of-a-backup-tape-or-file-sql-server.md)  
  
-   [<span data-ttu-id="165da-108">Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="165da-108">View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;</span></span>](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md)  
  
## <a name="options"></a><span data-ttu-id="165da-109">Options</span><span class="sxs-lookup"><span data-stu-id="165da-109">Options</span></span>  
 <span data-ttu-id="165da-110">**unité de sauvegarde**</span><span class="sxs-lookup"><span data-stu-id="165da-110">**Backup device**</span></span>  
 <span data-ttu-id="165da-111">Dans la zone de liste, sélectionnez le nom de l'unité logique de sauvegarde à partir de laquelle vous voulez effectuer la restauration.</span><span class="sxs-lookup"><span data-stu-id="165da-111">In the list box, select the name of a logical backup device from which you want to restore.</span></span>  
  
 <span data-ttu-id="165da-112">Pour plus d’informations sur la façon d’afficher le contenu d’une unité de sauvegarde, consultez [Afficher les propriétés et le contenu d’une unité de sauvegarde logique &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="165da-112">For information about how to view the contents of a backup device, see [View the Properties and Contents of a Logical Backup Device &#40;SQL Server&#41;](view-the-properties-and-contents-of-a-logical-backup-device-sql-server.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="165da-113">Notes </span><span class="sxs-lookup"><span data-stu-id="165da-113">Remarks</span></span>  
 <span data-ttu-id="165da-114">Si aucune unité logique de sauvegarde ne contient la sauvegarde recherchée dans la liste, il est possible que la sauvegarde ait été écrite directement sur un ou plusieurs fichiers ou lecteurs de bande.</span><span class="sxs-lookup"><span data-stu-id="165da-114">If you do not see a logical backup device that contains the backup you are seeking on the list, the backup might have been written directly to one or more files or tape drives.</span></span> <span data-ttu-id="165da-115">Le cas échant, fermez la boîte de dialogue **Sélectionner l'unité de sauvegarde** et dans la boîte de dialogue **Spécifier la sauvegarde** , sélectionnez **Fichier** ou **Bande** dans la zone de liste **Support de sauvegarde** .</span><span class="sxs-lookup"><span data-stu-id="165da-115">If this is the case, cancel the **Select Backup Device** dialog box; and in the **Specify Backup** dialog box, select **File** or **Tape** in the **Backup media** list box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="165da-116"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="165da-116">See Also</span></span>  
 [<span data-ttu-id="165da-117">Unités de sauvegarde &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="165da-117">Backup Devices &#40;SQL Server&#41;</span></span>](backup-devices-sql-server.md)  
  
  
