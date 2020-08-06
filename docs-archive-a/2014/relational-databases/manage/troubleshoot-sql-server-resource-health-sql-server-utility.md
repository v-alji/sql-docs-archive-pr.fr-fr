---
title: Résoudre les problèmes de contrôle d’intégrité de SQL Server (utilitaire SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 614f07b5-f221-4013-9f8d-22964cf42270
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 182225dd618dd1e9e058c549bdc07818813ba764
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602134"
---
# <a name="troubleshoot-sql-server-resource-health-sql-server-utility"></a><span data-ttu-id="6f13a-102">Résoudre les problèmes de contrôle d'intégrité de SQL Server (Utilitaire SQL Server)</span><span class="sxs-lookup"><span data-stu-id="6f13a-102">Troubleshoot SQL Server Resource Health (SQL Server Utility)</span></span>
  <span data-ttu-id="6f13a-103">La résolution des problèmes d'intégrité des ressources identifiés par un UCP [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut inclure l'atténuation de l'UC surexploitée sur un ordinateur ou sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ou atténuer l'UC surexploitée pour une application de la couche Données.</span><span class="sxs-lookup"><span data-stu-id="6f13a-103">Troubleshooting resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP might include mitigating overutilized CPU on a computer or on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or mitigating overutilized CPU for a data-tier application.</span></span> <span data-ttu-id="6f13a-104">D'autres problèmes peuvent inclure la résolution de l'espace de fichier surexploité pour les fichiers de base de données ou la résolution de la surexploitation d'espace disque alloué sur un volume de stockage.</span><span class="sxs-lookup"><span data-stu-id="6f13a-104">Other issues might include resolving overutilized file space for database files or resolving overutilization of allocated disk space on a storage volume.</span></span>  
  
 <span data-ttu-id="6f13a-105">Notez que, si une base de données se trouve dans l’état « urgence », l’état d’intégrité affiche l’espace de fichier journal surexploité.</span><span class="sxs-lookup"><span data-stu-id="6f13a-105">Note that if a database is in "emergency" state, the health state will display overutilized log file space.</span></span>  
  
 <span data-ttu-id="6f13a-106">Pour plus d’informations sur l’échec de la collecte de données qui provoque des icônes d’état grises en mode Liste d’instances gérées sur un UCP, consultez [Résolution des problèmes liés à l’utilitaire SQL Server](../../database-engine/troubleshoot-the-sql-server-utility.md).</span><span class="sxs-lookup"><span data-stu-id="6f13a-106">For more information about failed data collection resulting in gray status icons in the managed instance list view on a UCP, see [Troubleshoot the SQL Server Utility](../../database-engine/troubleshoot-the-sql-server-utility.md).</span></span> <span data-ttu-id="6f13a-107">Pour plus d’informations sur la prise en main de l’utilitaire [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , consultez [Fonctionnalités et tâches de l’utilitaire SQL Server](sql-server-utility-features-and-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="6f13a-107">For more information about getting started with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, see [SQL Server Utility Features and Tasks](sql-server-utility-features-and-tasks.md).</span></span>  
  
 <span data-ttu-id="6f13a-108">Pour plus d'informations sur l'atténuation de problèmes d'intégrité des ressources spécifiques identifiés par un UCP [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="6f13a-108">For more information about mitigating specific resource health issues identified by a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] UCP, see the following topics:</span></span>  
  
-   [<span data-ttu-id="6f13a-109">Comment identifier la version et l'édition de votre SQL Server</span><span class="sxs-lookup"><span data-stu-id="6f13a-109">How to identify your SQL Server version and edition</span></span>](https://go.microsoft.com/fwlink/?LinkID=178504)  
  
-   [<span data-ttu-id="6f13a-110">Résolution des problèmes de performances dans SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="6f13a-110">Troubleshooting Performance Problems in SQL Server 2008</span></span>](https://go.microsoft.com/fwlink/?LinkId=151354)  
  
  
