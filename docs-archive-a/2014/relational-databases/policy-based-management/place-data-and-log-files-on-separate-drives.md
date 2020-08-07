---
title: Placer les fichiers de données et les fichiers journaux sur des lecteurs distincts | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d3f972ea29322a046c09657e2ed2499655c82aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611723"
---
# <a name="place-data-and-log-files-on-separate-drives"></a><span data-ttu-id="8ad53-102">Placer les fichiers de données et les fichiers journaux sur des lecteurs distincts</span><span class="sxs-lookup"><span data-stu-id="8ad53-102">Place Data and Log Files on Separate Drives</span></span>
  <span data-ttu-id="8ad53-103">Cette règle vérifie si les fichiers de données et les fichiers journaux sont placés sur des lecteurs logiques distincts.</span><span class="sxs-lookup"><span data-stu-id="8ad53-103">This rule checks whether data and log files are placed on separate logical drives.</span></span> <span data-ttu-id="8ad53-104">Si les fichiers de données et les fichiers journaux sont placés sur le même lecteur, des problèmes de contention peuvent se produire sur ce lecteur et les performances risquent de se dégrader.</span><span class="sxs-lookup"><span data-stu-id="8ad53-104">Placing both data and log files on the same device can cause contention for that device and result in poor performance.</span></span> <span data-ttu-id="8ad53-105">Lorsque ces fichiers sont placés sur des lecteurs distincts, l'activité E/S peut avoir lieu simultanément pour les fichiers de données et les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="8ad53-105">Placing the files on separate drives allows the I/O activity to occur at the same time for both the data and log files.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="8ad53-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="8ad53-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="8ad53-107">Lorsque vous créez une base de données, spécifiez des lecteurs distincts pour les fichiers de données et les fichiers journaux.</span><span class="sxs-lookup"><span data-stu-id="8ad53-107">When you create a new database, specify separate drives for the data and log.</span></span> <span data-ttu-id="8ad53-108">Pour déplacer ces fichiers une fois la base de données créée, cette dernière doit être placée hors connexion.</span><span class="sxs-lookup"><span data-stu-id="8ad53-108">To move files after the database is created, the database must be taken offline.</span></span> <span data-ttu-id="8ad53-109">Déplacez les fichiers à l'aide d'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="8ad53-109">Move the files by using one of the following methods:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ad53-110">Cette stratégie ne permet pas de détecter des périphériques physiques distincts par le biais de points de montage.</span><span class="sxs-lookup"><span data-stu-id="8ad53-110">This policy cannot detect separate physical devices through mount points</span></span>  
  
-   <span data-ttu-id="8ad53-111">Restaurez la base de données à partir d'une sauvegarde à l'aide de l'instruction RESTORE DATABASE avec l'option WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="8ad53-111">Restore the database from backup by using the RESTORE DATABASE statement with the WITH MOVE option.</span></span>  
  
-   <span data-ttu-id="8ad53-112">Détachez puis attachez la base de données en spécifiant des emplacements distincts pour les unités de données et les unités de journaux.</span><span class="sxs-lookup"><span data-stu-id="8ad53-112">Detach and then attach the database specifying separate locations for the data and log devices.</span></span>  
  
-   <span data-ttu-id="8ad53-113">Spécifiez un nouvel emplacement en exécutant l'instruction ALTER DATABASE avec l'option MODIFY FILE, puis en redémarrant l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ad53-113">Specify a new location by running the ALTER DATABASE statement with the MODIFY FILE option, and then restarting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="8ad53-114">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="8ad53-114">For More Information</span></span>  
 [<span data-ttu-id="8ad53-115">Déplacer des fichiers de bases de données</span><span class="sxs-lookup"><span data-stu-id="8ad53-115">Move Database Files</span></span>](../databases/move-database-files.md)  
  
 [<span data-ttu-id="8ad53-116">Déplacer des bases de données utilisateur</span><span class="sxs-lookup"><span data-stu-id="8ad53-116">Move User Databases</span></span>](../databases/move-user-databases.md)  
  
 [<span data-ttu-id="8ad53-117">Attacher et détacher une base de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="8ad53-117">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ad53-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ad53-118">See Also</span></span>  
 [<span data-ttu-id="8ad53-119">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="8ad53-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
