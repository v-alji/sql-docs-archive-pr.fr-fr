---
title: Moteur de base de données SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server]
- SQL Server Database Engine
ms.assetid: 65e2f424-1386-45a6-8912-bd053f434073
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a6c243115e940f7af085c0068d2ca5c277aa5162
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601062"
---
# <a name="sql-server-database-engine"></a><span data-ttu-id="9e63c-102">Moteur de base de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e63c-102">SQL Server Database Engine</span></span>
  <span data-ttu-id="9e63c-103">Le [!INCLUDE[ssDE](../includes/ssde-md.md)] est le service central qui permet de stocker, traiter et sécuriser les données.</span><span class="sxs-lookup"><span data-stu-id="9e63c-103">The [!INCLUDE[ssDE](../includes/ssde-md.md)] is the core service for storing, processing, and securing data.</span></span> <span data-ttu-id="9e63c-104">Le [!INCLUDE[ssDE](../includes/ssde-md.md)] permet de contrôler les accès et de traiter rapidement les transactions pour répondre aux besoins des applications consommatrices de données les plus exigeantes de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="9e63c-104">The [!INCLUDE[ssDE](../includes/ssde-md.md)] provides controlled access and rapid transaction processing to meet the requirements of the most demanding data consuming applications within your enterprise.</span></span>

 <span data-ttu-id="9e63c-105">Utilisez le [!INCLUDE[ssDE](../includes/ssde-md.md)] afin de créer des bases de données relationnelles pour le traitement de transaction en ligne ou les données de traitement analytique en ligne.</span><span class="sxs-lookup"><span data-stu-id="9e63c-105">Use the [!INCLUDE[ssDE](../includes/ssde-md.md)] to create relational databases for online transaction processing or online analytical processing data.</span></span> <span data-ttu-id="9e63c-106">Ces opérations comprennent la création de tables pour le stockage des données, et les objets de base de données tels que les index, les vues et les procédures stockées pour l'affichage, la gestion et la sécurisation des données.</span><span class="sxs-lookup"><span data-stu-id="9e63c-106">This includes creating tables for storing data, and database objects such as indexes, views, and stored procedures for viewing, managing, and securing data.</span></span> <span data-ttu-id="9e63c-107">Vous pouvez faire appel à [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour gérer les objets de base de données, et à [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] pour capturer des événements de serveur.</span><span class="sxs-lookup"><span data-stu-id="9e63c-107">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to manage the database objects, and [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] to capture server events.</span></span>

 <span data-ttu-id="9e63c-108">Icône **Parcourir le contenu par** ![petite zone dossier de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers") [Nouveautés (moteur de base de données)](whats-new-in-sql-server-2016.md)</span><span class="sxs-lookup"><span data-stu-id="9e63c-108">**Browse Content by Area** ![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [What's New (Database Engine)](whats-new-in-sql-server-2016.md)</span></span>

 <span data-ttu-id="9e63c-109">![Petite icône de dossier de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers") [SQL Server moteur de base de données la compatibilité descendante](sql-server-database-engine-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="9e63c-109">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Database Engine Backward Compatibility](sql-server-database-engine-backward-compatibility.md)</span></span>

 <span data-ttu-id="9e63c-110">![Petite icône de dossier de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers") [Outils d’administration SQL Server la compatibilité descendante](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="9e63c-110">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [SQL Server Management Tools Backward Compatibility](../../2014/database-engine/sql-server-management-tools-backward-compatibility.md)</span></span>

 <span data-ttu-id="9e63c-111">![Petite icône de dossier de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers") [fonctionnalités et tâches de base de données](../../2014/database-engine/database-engine-features-and-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="9e63c-111">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Database Features and Tasks](../../2014/database-engine/database-engine-features-and-tasks.md)</span></span>

 <span data-ttu-id="9e63c-112">Informations [techniques de référence](../../2014/database-engine/technical-reference-database-engine.md) sur les ![petites icônes de dossiers de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers")</span><span class="sxs-lookup"><span data-stu-id="9e63c-112">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Technical Reference](../../2014/database-engine/technical-reference-database-engine.md)</span></span>

 <span data-ttu-id="9e63c-113">![Petite icône de dossier de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers") [référence Transact-SQL](/sql/t-sql/language-reference)</span><span class="sxs-lookup"><span data-stu-id="9e63c-113">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [Transact-SQL Reference](/sql/t-sql/language-reference)</span></span>

 <span data-ttu-id="9e63c-114">![Petite icône de dossier de fichiers](../../2014/integration-services/media/filefolder-small.gif "Petite icône de dossier de fichiers") [référence XQuery](/sql/xquery/xquery-language-reference-sql-server)</span><span class="sxs-lookup"><span data-stu-id="9e63c-114">![Small File Folder Icon](../../2014/integration-services/media/filefolder-small.gif "Small File Folder Icon") [XQuery Reference](/sql/xquery/xquery-language-reference-sql-server)</span></span>

## <a name="see-also"></a><span data-ttu-id="9e63c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e63c-115">See Also</span></span>
 [<span data-ttu-id="9e63c-116">Centre de ressources SQL Server</span><span class="sxs-lookup"><span data-stu-id="9e63c-116">SQL Server Resource Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=219676)


