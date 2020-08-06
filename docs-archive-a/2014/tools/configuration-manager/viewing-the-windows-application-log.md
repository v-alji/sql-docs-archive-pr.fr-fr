---
title: Affichage du journal des applications Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- application logs [SQL Server]
- Windows application logs [SQL Server]
- viewing Windows application logs
- errors [SQL Server], logs
- system logs [SQL Server]
- security logs [SQL Server]
- displaying Windows application logs
- logs [SQL Server], Windows application logs
ms.assetid: f9853b74-7db7-47cc-b957-e49ed5bc0a1a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 22f900a0b203e652bbc9cc6e9638711d138756c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604778"
---
# <a name="viewing-the-windows-application-log"></a><span data-ttu-id="0a3ee-102">Affichage du journal des applications Windows</span><span class="sxs-lookup"><span data-stu-id="0a3ee-102">Viewing the Windows Application Log</span></span>
  <span data-ttu-id="0a3ee-103">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est configuré pour utiliser le journal des applications Windows, chaque session [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] écrit un nouvel événement dans ce journal.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Microsoft Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="0a3ee-104">Contrairement au journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , un nouveau journal des applications n'est pas créé chaque fois que vous démarrez une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a3ee-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0a3ee-105">Affichez et gérez le journal des applications Windows en utilisant l'Observateur d'événements de Windows ou la Visionneuse du journal de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0a3ee-105">View and manage the Windows application log by using Windows Event Viewer or the Log Viewer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="0a3ee-106">Il existe trois journaux pouvant être affichés avec l’Observateur d’événements.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-106">There are three logs that can be viewed with Event Viewer.</span></span>  
  
|<span data-ttu-id="0a3ee-107">Type de journal Windows</span><span class="sxs-lookup"><span data-stu-id="0a3ee-107">Windows log type</span></span>|<span data-ttu-id="0a3ee-108">Description</span><span class="sxs-lookup"><span data-stu-id="0a3ee-108">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="0a3ee-109">Journal système</span><span class="sxs-lookup"><span data-stu-id="0a3ee-109">System log</span></span>|<span data-ttu-id="0a3ee-110">Il enregistre les événements consignés par les composants du système d'exploitation Windows.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-110">Records events logged by the Windows operating system components.</span></span> <span data-ttu-id="0a3ee-111">L'échec du chargement d'un pilote ou d'un autre composant du système lors du démarrage, par exemple, est consigné dans le journal système.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-111">For example, the failure of a driver or other system component to load during startup is recorded in the system log.</span></span>|  
|<span data-ttu-id="0a3ee-112">Journal de sécurité</span><span class="sxs-lookup"><span data-stu-id="0a3ee-112">Security log</span></span>|<span data-ttu-id="0a3ee-113">Il enregistre les événements de sécurité comme les tentatives de connexion qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-113">Records security events, such as failed login attempts.</span></span> <span data-ttu-id="0a3ee-114">Cela permet de rechercher les modifications du système de sécurité et d'identifier les violations possibles de la sécurité.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-114">This helps track changes to the security system and identify possible breaches to security.</span></span> <span data-ttu-id="0a3ee-115">Par exemple, les tentatives de connexion au système doivent être enregistrées dans le journal de sécurité, en fonction des paramètres d'audit du gestionnaire des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-115">For example, attempts to log on to the system may be recorded in the security log, depending on the audit settings in the User Manager.</span></span><br /><br /> <span data-ttu-id="0a3ee-116">Seuls les membres du rôle serveur fixe **sysadmin** peuvent afficher le journal de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-116">Only members of the **sysadmin** fixed server role can view the security log.</span></span>|  
|<span data-ttu-id="0a3ee-117">Journal des application</span><span class="sxs-lookup"><span data-stu-id="0a3ee-117">Application log</span></span>|<span data-ttu-id="0a3ee-118">Il enregistre les événements qui sont consignés par les applications.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-118">Records events that are logged by applications.</span></span> <span data-ttu-id="0a3ee-119">Par exemple, une application de base de données peut enregistrer un fichier d'erreurs dans le journal des applications.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-119">For example, a database application might record a file error in the application log.</span></span>|  
  
 <span data-ttu-id="0a3ee-120">Pour plus d'informations sur l'utilisation de l'Observateur d'événements, la gestion du journal des applications et la signification des données qui y figurent, consultez la documentation de Windows.</span><span class="sxs-lookup"><span data-stu-id="0a3ee-120">For more information about using Event Viewer, managing the application log, and understanding the information it presents, see the Windows documentation.</span></span>  
  
 <span data-ttu-id="0a3ee-121">**Pour consulter le journal des applications Windows**</span><span class="sxs-lookup"><span data-stu-id="0a3ee-121">**To view the Windows application log**</span></span>  
  
 [<span data-ttu-id="0a3ee-122">Afficher le journal des applications Windows &#40;Windows&#41;</span><span class="sxs-lookup"><span data-stu-id="0a3ee-122">View the Windows Application Log &#40;Windows&#41;</span></span>](../../relational-databases/performance/view-the-windows-application-log-windows-10.md)  
  
  
