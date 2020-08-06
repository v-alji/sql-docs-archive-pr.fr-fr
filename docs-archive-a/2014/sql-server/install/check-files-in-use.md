---
title: Vérifier les fichiers en cours d’utilisation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccd65867-d4c0-43b2-8361-7fd41c6f79ac
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 51505b0dece146b7f6fcdf982e6f88a5715357e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604962"
---
# <a name="check-files-in-use"></a><span data-ttu-id="064da-102">Vérifier les fichiers en cours d'utilisation</span><span class="sxs-lookup"><span data-stu-id="064da-102">Check Files In Use</span></span>
  <span data-ttu-id="064da-103">Pour éviter d'avoir à redémarrer Windows après avoir installé des mises à jour de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , utilisez la page Vérifier les fichiers en cours d'utilisation afin d'identifier les processus qui verrouillent des fichiers requis par le programme d'installation des mises à jour de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="064da-103">To avoid restarting Windows after you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] updates, use the Check Files in Use page to identify processes that are locking files required by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] update Setup program.</span></span>  
  
 <span data-ttu-id="064da-104">Arrêtez toutes les applications et tous les services qui établissent des connexions aux instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui sont en cours de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="064da-104">Stop all applications and services that make connections to the instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that are being updated.</span></span> <span data-ttu-id="064da-105">Cela implique l'arrêt de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] et [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="064da-105">This includes stopping [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="064da-106">Si le programme d'installation détermine que des fichiers sont verrouillés au cours de l'installation, vous devrez peut-être redémarrer votre ordinateur au terme de l'installation.</span><span class="sxs-lookup"><span data-stu-id="064da-106">If Setup determines that files are locked during installation, you might have to restart your computer after installation is completed.</span></span> <span data-ttu-id="064da-107">Si tel est le cas, le programme d'installation vous demandera de le faire.</span><span class="sxs-lookup"><span data-stu-id="064da-107">If necessary, Setup prompts you to restart your computer.</span></span> <span data-ttu-id="064da-108">Si le programme d'installation doit arrêter un service au cours de l'installation, il redémarrera ce dernier une fois l'installation terminée.</span><span class="sxs-lookup"><span data-stu-id="064da-108">If the Setup program must stop a service during installation, it will restart the service after installation is completed.</span></span>  
  
 <span data-ttu-id="064da-109">Pour vous éviter d'avoir à redémarrer votre ordinateur après l'installation, le programme d'installation affiche la liste des processus qui verrouillent des fichiers.</span><span class="sxs-lookup"><span data-stu-id="064da-109">To eliminate the requirement to restart your computer after installation, Setup displays a list of processes that are locking files.</span></span> <span data-ttu-id="064da-110">Arrêtez les processus et les applications de la liste.</span><span class="sxs-lookup"><span data-stu-id="064da-110">Stop or end the processes and applications in the list.</span></span> <span data-ttu-id="064da-111">Cliquez sur **Actualiser la vérification** pour réexécuter la vérification.</span><span class="sxs-lookup"><span data-stu-id="064da-111">Then click **Refresh check** to rerun the check.</span></span> <span data-ttu-id="064da-112">Cliquez sur **Arrêter la vérification** pour mettre fin à une vérification en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="064da-112">Click **Stop check** to end a check that is running.</span></span> <span data-ttu-id="064da-113">Si aucun fichier verrouillé n'est détecté, le tableau est vide.</span><span class="sxs-lookup"><span data-stu-id="064da-113">If locked files are not found, the table is empty.</span></span> <span data-ttu-id="064da-114">Une fois que tous les processus bloquants ont été arrêtés, cliquez sur **Suivant** pour continuer.</span><span class="sxs-lookup"><span data-stu-id="064da-114">When all locked processes have been closed or stopped, click **Next** to continue.</span></span>  
  
 <span data-ttu-id="064da-115">Le programme d'installation enregistre les informations dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="064da-115">Setup logs the information in the log files.</span></span> <span data-ttu-id="064da-116">Pour plus d’informations sur la consultation des fichiers journaux, consultez [Afficher et lire les fichiers journaux d’installation de SQL Server](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) et [Procédure : lire un fichier journal d’installation de SQL Server](https://go.microsoft.com/fwlink/?LinkID=134490).</span><span class="sxs-lookup"><span data-stu-id="064da-116">For more information about how to view the log files, see [View and Read SQL Server Setup Log Files](../../database-engine/install-windows/view-and-read-sql-server-setup-log-files.md) and [How to: Read a SQL Server Setup Log File](https://go.microsoft.com/fwlink/?LinkID=134490).</span></span>  
  
 <span data-ttu-id="064da-117">Les informations suivantes sont contenues dans le fichier journal :</span><span class="sxs-lookup"><span data-stu-id="064da-117">The following information is included in the log file:</span></span>  
  
-   <span data-ttu-id="064da-118">Nom du processus</span><span class="sxs-lookup"><span data-stu-id="064da-118">Name of the process</span></span>  
  
-   <span data-ttu-id="064da-119">Nom de la fonctionnalité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="064da-119">Name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature</span></span>  
  
-   <span data-ttu-id="064da-120">Type de processus</span><span class="sxs-lookup"><span data-stu-id="064da-120">Process type</span></span>  
  
-   <span data-ttu-id="064da-121">Compte sous lequel le processus est en cours d'exécution</span><span class="sxs-lookup"><span data-stu-id="064da-121">Account under which the process is running</span></span>  
  
-   <span data-ttu-id="064da-122">ID du processus</span><span class="sxs-lookup"><span data-stu-id="064da-122">Process ID</span></span>  
  
-   <span data-ttu-id="064da-123">Nom du fichier verrouillé</span><span class="sxs-lookup"><span data-stu-id="064da-123">Name of the file that is locked</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="064da-124">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="064da-124">UI element list</span></span>  
  
|<span data-ttu-id="064da-125">Nom</span><span class="sxs-lookup"><span data-stu-id="064da-125">Name</span></span>|<span data-ttu-id="064da-126">Description</span><span class="sxs-lookup"><span data-stu-id="064da-126">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="064da-127">Process</span><span class="sxs-lookup"><span data-stu-id="064da-127">Process</span></span>|<span data-ttu-id="064da-128">Affiche le nom complet du processus qui utilise les fichiers à mettre à jour.</span><span class="sxs-lookup"><span data-stu-id="064da-128">Displays the full name of the process that is using the files to be updated.</span></span>|  
|<span data-ttu-id="064da-129">Type</span><span class="sxs-lookup"><span data-stu-id="064da-129">Type</span></span>|<span data-ttu-id="064da-130">Affiche le type de processus.</span><span class="sxs-lookup"><span data-stu-id="064da-130">Displays the type of process.</span></span>|  
|<span data-ttu-id="064da-131">Compte</span><span class="sxs-lookup"><span data-stu-id="064da-131">Account</span></span>|<span data-ttu-id="064da-132">Affiche le compte sous lequel le processus est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="064da-132">Displays the account under which the process is running.</span></span>|  
|<span data-ttu-id="064da-133">ID du processus</span><span class="sxs-lookup"><span data-stu-id="064da-133">Process ID</span></span>|<span data-ttu-id="064da-134">Affiche l'ID de processus.</span><span class="sxs-lookup"><span data-stu-id="064da-134">Displays the process ID.</span></span>|  
  
  
