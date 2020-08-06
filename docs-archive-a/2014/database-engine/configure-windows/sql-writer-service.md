---
title: Service SQL Writer | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- VDI [SQL Server]
- restoring [SQL Server], SQL Writer Service
- backups [SQL Server], while SQL Server running
- Volume Shadow Copy Service
- volume backups while running [SQL Server]
- Virtual Backup Device Interface [SQL Server]
- SQL Writer Service
- services [SQL Server], SQL Writer
- MSDE Writer
- VSS
ms.assetid: 0f299867-f499-4c2a-ad6f-b2ef1869381d
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 310722c6617c7a2c9e0f384ec23ae371ab230536
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601084"
---
# <a name="sql-writer-service"></a><span data-ttu-id="f1a09-102">Service SQL Writer</span><span class="sxs-lookup"><span data-stu-id="f1a09-102">SQL Writer Service</span></span>
  <span data-ttu-id="f1a09-103">Le service SQL Writer complète les fonctionnalités de sauvegarde et de restauration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par le biais du service VSS.</span><span class="sxs-lookup"><span data-stu-id="f1a09-103">The SQL Writer Service provides added functionality for backup and restore of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] through the Volume Shadow Copy Service framework.</span></span>  
  
 <span data-ttu-id="f1a09-104">Le service SQL Writer est installé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="f1a09-104">The SQL Writer Service is installed automatically.</span></span> <span data-ttu-id="f1a09-105">Il doit être en cours d'exécution lorsque l'application VSS (Volume Shadow Copy Service) demande une sauvegarde ou une restauration.</span><span class="sxs-lookup"><span data-stu-id="f1a09-105">It must be running when the Volume Shadow Copy Service (VSS) application requests a backup or restore.</span></span> <span data-ttu-id="f1a09-106">Pour configurer le service, utilisez l'applet des services [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="f1a09-106">To configure the service, use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services applet.</span></span> <span data-ttu-id="f1a09-107">Le service SQL Writer s'installe sur tous les systèmes d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="f1a09-107">The SQL Writer Service installs on all operating systems.</span></span>  
  
## <a name="purpose"></a><span data-ttu-id="f1a09-108">Objectif</span><span class="sxs-lookup"><span data-stu-id="f1a09-108">Purpose</span></span>  
 <span data-ttu-id="f1a09-109">Lors de son exécution, le [!INCLUDE[ssDE](../../includes/ssde-md.md)] verrouille les fichiers de données pour être seul à pouvoir y accéder.</span><span class="sxs-lookup"><span data-stu-id="f1a09-109">When running, [!INCLUDE[ssDE](../../includes/ssde-md.md)] locks and has exclusive access to the data files.</span></span> <span data-ttu-id="f1a09-110">Lorsque le service SQL Writer n'est pas exécuté, les programmes de sauvegarde exécutés dans Windows n'ont pas accès à ces fichiers de données, et les sauvegardes doivent s'effectuer au moyen de la sauvegarde [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1a09-110">When the SQL Writer Service is not running, backup programs running in Windows do not have access to the data files, and backups must be performed using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup.</span></span>  
  
 <span data-ttu-id="f1a09-111">Utilisez le service SQL Writer pour permettre aux programmes de sauvegarde de Windows de copier les fichiers de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] même lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="f1a09-111">Use the SQL Writer Service to permit Windows backup programs to copy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data files while [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>  
  
## <a name="volume-shadow-copy-service"></a><span data-ttu-id="f1a09-112">Service VSS</span><span class="sxs-lookup"><span data-stu-id="f1a09-112">Volume Shadow Copy Service</span></span>  
 <span data-ttu-id="f1a09-113">Le service VSS est un ensemble d'API COM qui forment un cadre permettant la sauvegarde de volumes même lorsque des opérations d'écriture sont en cours.</span><span class="sxs-lookup"><span data-stu-id="f1a09-113">The VSS is a set of COM APIs that implements a framework to allow volume backups to be performed while applications on a system continue to write to the volumes.</span></span> <span data-ttu-id="f1a09-114">Il offre une interface cohérente qui permet la coordination entre les différentes applications utilisateur qui mettent à jour les données sur le disque (les writers) et celles qui assurent la sauvegarde des applications (les demandeurs).</span><span class="sxs-lookup"><span data-stu-id="f1a09-114">The VSS provides a consistent interface that allows coordination between user applications that update data on disk (writers) and those that back up applications (requestors).</span></span>  
  
 <span data-ttu-id="f1a09-115">Ce service capture et copie des images stables pour la sauvegarde sur des systèmes en cours d'utilisation, en particulier des serveurs, sans dégradation superflue des performances et de la stabilité des services qu'ils assurent.</span><span class="sxs-lookup"><span data-stu-id="f1a09-115">The VSS captures and copies stable images for backup on running systems, particularly servers, without unduly degrading the performance and stability of the services they provide.</span></span> <span data-ttu-id="f1a09-116">Pour plus d'informations sur le service VSS, consultez votre documentation Windows.</span><span class="sxs-lookup"><span data-stu-id="f1a09-116">For more information on the VSS, see your Windows documentation.</span></span>  
  
## <a name="virtual-backup-device-interface-vdi"></a><span data-ttu-id="f1a09-117">Interface d'unité de sauvegarde virtuelle</span><span class="sxs-lookup"><span data-stu-id="f1a09-117">Virtual Backup Device Interface (VDI)</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f1a09-118">fournit une API appelée « Interface d’unité de sauvegarde virtuelle » qui permet aux éditeurs de logiciels indépendants d’intégrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans leurs produits pour la prise en charge des opérations de sauvegarde et de restauration.</span><span class="sxs-lookup"><span data-stu-id="f1a09-118">provides an API called Virtual Backup Device Interface (VDI) that enables independent software vendors to integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] into their products for providing support for backup and restore operations.</span></span> <span data-ttu-id="f1a09-119">Conçues pour fournir une fiabilité et des performances optimales, ces API prennent en charge l'éventail complet de fonctions de sauvegarde et de restauration de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , y compris la gamme totale des sauvegardes à chaud et instantanées.</span><span class="sxs-lookup"><span data-stu-id="f1a09-119">These APIs are engineered to provide maximum reliability and performance, and support the full range of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] backup and restore functionality, including the full range of hot and snapshot backup capabilities.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="f1a09-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f1a09-120">Permissions</span></span>  
 <span data-ttu-id="f1a09-121">Le service SQL Writer doit s'exécuter sous le compte **système local** .</span><span class="sxs-lookup"><span data-stu-id="f1a09-121">The SQL Writer service must run under the **Local System** account.</span></span> <span data-ttu-id="f1a09-122">Le service SQL Writer utilise la connexion **NT Service\SQLWriter** pour la connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1a09-122">The SQL Writer service uses the **NT Service\SQLWriter** login to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f1a09-123">Le fait d’utiliser la connexion **NT Service\SQLWriter** permet au processus SQL Writer de s’exécuter à un niveau de droits inférieur dans un compte indiqué comme étant **sans connexion**, ce qui limite la vulnérabilité.</span><span class="sxs-lookup"><span data-stu-id="f1a09-123">Using the **NT Service\SQLWriter** login allows the SQL Writer process to run at a lower privilege level in an account designated as **no login**, which limits vulnerability.</span></span> <span data-ttu-id="f1a09-124">Si le service SQL Writer est désactivé, les utilitaires qui s'appuient sur les instantanés VSS, tels que System Center Data Protection Manager, ainsi que certains autres produits tiers, seront rompus ou pire, risquent d'effectuer des sauvegardes de bases de données qui ne sont pas cohérentes.</span><span class="sxs-lookup"><span data-stu-id="f1a09-124">If the SQL Writer service is disabled, then any utility which in relies on VSS snapshots, such as System Center Data Protection Manager, as well as some other 3rd-party products, would be broken, or worse, at risk of taking backups of databases which were not consistent.</span></span> <span data-ttu-id="f1a09-125">Si ni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le système sur lequel il s'exécute, ni le système hôte (dans le cas d'une machine virtuelle), ne doit utiliser un élément autre que la sauvegarde [!INCLUDE[tsql](../../includes/tsql-md.md)] , le service SQL Writer peut être désactivé en toute sécurité et la connexion supprimée.</span><span class="sxs-lookup"><span data-stu-id="f1a09-125">If neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the system it runs on, nor the host system (in the event of a virtual machine), need to use anything besides [!INCLUDE[tsql](../../includes/tsql-md.md)] backup, then the SQL Writer service can be safely disabled and the login removed.</span></span>  <span data-ttu-id="f1a09-126">Notez que le service SQL Writer peut être appelé par une sauvegarde au niveau du système ou du volume, que la sauvegarde repose directement sur des instantanés ou non.</span><span class="sxs-lookup"><span data-stu-id="f1a09-126">Note that the SQL Writer service may be invoked by a system or volume level backup, whether the backup is directly snapshot-based or not.</span></span> <span data-ttu-id="f1a09-127">Certains logiciels de sauvegarde système utilisent VSS pour éviter d’être bloqués par des fichiers ouverts ou verrouillés.</span><span class="sxs-lookup"><span data-stu-id="f1a09-127">Some system backup products use VSS to avoid being blocked by open or locked files.</span></span> <span data-ttu-id="f1a09-128">Le service SQL Writer nécessite des autorisations élevées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . En effet, au cours de ses activités, il fige brièvement toutes les E/S pour l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1a09-128">The SQL Writer service needs elevated permissions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] because in the course of its activities it briefly freezes all I/O for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="features"></a><span data-ttu-id="f1a09-129">Fonctionnalités</span><span class="sxs-lookup"><span data-stu-id="f1a09-129">Features</span></span>  
 <span data-ttu-id="f1a09-130">SQL Writer prend en charge les possibilités suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1a09-130">SQL Writer supports:</span></span>  
  
-   <span data-ttu-id="f1a09-131">Sauvegarde et restauration complètes de bases de données, y compris des catalogues de texte intégral</span><span class="sxs-lookup"><span data-stu-id="f1a09-131">Full database backup and restore including full-text catalogs</span></span>  
  
-   <span data-ttu-id="f1a09-132">Sauvegarde et restauration différentielle</span><span class="sxs-lookup"><span data-stu-id="f1a09-132">Differential backup and restore</span></span>  
  
-   <span data-ttu-id="f1a09-133">Restauration avec déplacement</span><span class="sxs-lookup"><span data-stu-id="f1a09-133">Restore with move</span></span>  
  
-   <span data-ttu-id="f1a09-134">Modification du nom d'une base de données</span><span class="sxs-lookup"><span data-stu-id="f1a09-134">Database rename</span></span>  
  
-   <span data-ttu-id="f1a09-135">Sauvegarde de copie seule</span><span class="sxs-lookup"><span data-stu-id="f1a09-135">Copy-only backup</span></span>  
  
-   <span data-ttu-id="f1a09-136">Récupération automatique d'un instantané de base de données</span><span class="sxs-lookup"><span data-stu-id="f1a09-136">Auto-recovery of database snapshot</span></span>  
  
 <span data-ttu-id="f1a09-137">SQL Writer ne prend pas en charge les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="f1a09-137">SQL Writer does not support:</span></span>  
  
-   <span data-ttu-id="f1a09-138">Sauvegarde de journaux</span><span class="sxs-lookup"><span data-stu-id="f1a09-138">Log backups</span></span>  
  
-   <span data-ttu-id="f1a09-139">Sauvegarde de fichiers et de groupes de fichiers</span><span class="sxs-lookup"><span data-stu-id="f1a09-139">File and filegroup backup</span></span>  
  
-   <span data-ttu-id="f1a09-140">Restauration de pages</span><span class="sxs-lookup"><span data-stu-id="f1a09-140">Page restore</span></span>  
  
  
