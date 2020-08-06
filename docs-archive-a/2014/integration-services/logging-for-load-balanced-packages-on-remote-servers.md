---
title: Journalisation des packages à charge équilibrée sur les serveurs distants | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], remote packages
ms.assetid: fd571567-b625-4f9a-8b7e-42c5c588b11b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b45fa6607d6edc1559d8ebcbbbc7598e11eac408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605556"
---
# <a name="logging-for-load-balanced-packages-on-remote-servers"></a><span data-ttu-id="de305-102">Journalisation des packages à charge équilibrée sur les serveurs distants</span><span class="sxs-lookup"><span data-stu-id="de305-102">Logging for Load Balanced Packages on Remote Servers</span></span>
  <span data-ttu-id="de305-103">Il est plus facile pour un administrateur de gérer les journaux de tous les packages enfants en cours d'exécution sur différents serveurs lorsque tous ces packages enfants utilisent le même module fournisseur d'informations et qu'ils écrivent tous dans la même destination.</span><span class="sxs-lookup"><span data-stu-id="de305-103">It is easier for an administrator to manage the logs for all the child packages that are running on various servers when all the child packages use the same log provider and they all write to the same destination.</span></span> <span data-ttu-id="de305-104">Une manière de créer un fichier journal commun pour tous les packages enfants est de configurer les packages enfants de telle sorte qu'ils inscrivent leurs événements dans un module fournisseur d'informations SQL Server.</span><span class="sxs-lookup"><span data-stu-id="de305-104">One way that you can create a common log file for all child packages is to configure the child packages to log their events to a SQL Server log provider.</span></span> <span data-ttu-id="de305-105">Vous pouvez configurer tous les packages pour qu'ils utilisent la même base de données, le même serveur et la même instance du serveur.</span><span class="sxs-lookup"><span data-stu-id="de305-105">You can configure all the packages to use the same database, the same server, and the same instance of the server.</span></span>  
  
 <span data-ttu-id="de305-106">Pour afficher les fichiers journaux, l'administrateur n'a à se connecter qu'à un seul serveur pour afficher les fichiers journaux de tous les packages enfants.</span><span class="sxs-lookup"><span data-stu-id="de305-106">To view the log files, the administrator only has to log on to a single server to view the log files for all child packages.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="de305-107">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="de305-107">Related Tasks</span></span>  
 <span data-ttu-id="de305-108">Pour plus d’informations sur la façon d’activer la journalisation dans un package, consultez [Activer la journalisation des packages dans SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span><span class="sxs-lookup"><span data-stu-id="de305-108">For information about how to enable logging in a package, see [Enable Package Logging in SQL Server Data Tools](../../2014/integration-services/enable-package-logging-in-sql-server-data-tools.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de305-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="de305-109">See Also</span></span>  
 [<span data-ttu-id="de305-110">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="de305-110">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
