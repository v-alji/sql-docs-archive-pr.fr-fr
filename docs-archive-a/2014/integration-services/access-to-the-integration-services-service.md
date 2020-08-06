---
title: Accès au service Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7dd6fbed4bedc285069306ab4c400f0f67f9f293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602273"
---
# <a name="access-to-the-integration-services-service"></a><span data-ttu-id="dcdeb-102">Accéder au service Integration Services</span><span class="sxs-lookup"><span data-stu-id="dcdeb-102">Access to the Integration Services Service</span></span>
  <span data-ttu-id="dcdeb-103">Les niveaux de protection des packages peuvent définir des restrictions quant aux utilisateurs autorisés à modifier et exécuter un package.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-103">Package protection levels can limit who is allowed to edit and execute a package.</span></span> <span data-ttu-id="dcdeb-104">Une protection supplémentaire est nécessaire pour limiter les utilisateurs autorisés à afficher la liste des packages actuellement en cours d’exécution sur un serveur et ceux qui peuvent arrêter les packages en cours d’exécution dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcdeb-104">Additional protection is needed to limit who can view the list of packages currently running on a server and who can stop currently executing packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="dcdeb-105">utilise le service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour établir la liste des packages en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-105">uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service to list running packages.</span></span> <span data-ttu-id="dcdeb-106">Les membres du groupe Administrateurs de Windows peuvent afficher et arrêter tous les packages en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-106">Members of the Windows Administrators group can view and stop all currently running packages.</span></span> <span data-ttu-id="dcdeb-107">Les utilisateurs n'appartenant pas au groupe Administrateurs de Windows ne peuvent afficher et arrêter que les packages qu'ils ont démarrés.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-107">Users who are not members of the Administrators group can view and stop only packages that they started.</span></span>  
  
 <span data-ttu-id="dcdeb-108">Il est important de restreindre l'accès aux ordinateurs qui exécutent un service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , notamment un service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui peut énumérer des dossiers distants.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-108">It is important to restrict access to computers that run an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service, especially an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service that can enumerate remote folders.</span></span> <span data-ttu-id="dcdeb-109">Tout utilisateur authentifié peut demander l'énumération des packages.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-109">Any authenticated user can request the enumeration of packages.</span></span> <span data-ttu-id="dcdeb-110">Même si le service ne trouve pas le service, il énumère les dossiers.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-110">Even if the service doesn not find the service, the service enumerates folders.</span></span> <span data-ttu-id="dcdeb-111">Ces noms de dossiers peuvent être utilisés par un utilisateur malveillant.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-111">These folder names may be useful to a malicious user.</span></span> <span data-ttu-id="dcdeb-112">Si un administrateur a configuré le service pour qu'il énumère les dossiers sur un ordinateur distant, les utilisateurs peuvent également voir des noms de dossiers qu'ils ne pourraient pas voir en temps normal.</span><span class="sxs-lookup"><span data-stu-id="dcdeb-112">If an administrator has configured the service to enumerate folders on a remote machine, users may also be able to see folder names that they would normally not be able to see.</span></span>  
  
  
