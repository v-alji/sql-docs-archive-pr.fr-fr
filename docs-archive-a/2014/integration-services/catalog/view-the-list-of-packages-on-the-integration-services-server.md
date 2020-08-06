---
title: Afficher la liste des packages sur le serveur Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 67a992d1-7524-4f4b-b3d8-ebd9e5ea82a8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 47b30f9ea0b2abae73f9260b873b7c8436c423eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694675"
---
# <a name="view-the-list-of-packages-on-the-integration-services-server"></a><span data-ttu-id="73968-102">Afficher la liste des packages sur le serveur Integration Services</span><span class="sxs-lookup"><span data-stu-id="73968-102">View the List of Packages on the Integration Services Server</span></span>
  <span data-ttu-id="73968-103">Vous pouvez afficher la liste des packages stockés sur le serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de deux façons :</span><span class="sxs-lookup"><span data-stu-id="73968-103">You can view the list of packages that are stored on the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server in one of two ways.</span></span>  
  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="73968-104">Accès Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="73968-104">access</span></span>  
 <span data-ttu-id="73968-105">Pour afficher la liste des packages stockés sur le serveur, interrogez la vue [catalog.packages &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="73968-105">To view the list of packages that are stored on the server, query the view, [catalog.packages &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-packages-ssisdb-database).</span></span>  
  
 <span data-ttu-id="73968-106">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73968-106">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
 <span data-ttu-id="73968-107">Pour afficher les packages stockés sur le serveur à l’aide de l’Explorateur d’objets dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], procédez comme indiqué ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="73968-107">To view packages stored on the server by using Object Explorer in [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], follow the procedure below.</span></span>  
  
### <a name="to-view-packages-using-ssmanstudiofull"></a><span data-ttu-id="73968-108">Pour afficher les packages à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73968-108">To view packages using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)]</span></span>  
  
1.  <span data-ttu-id="73968-109">Dans [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connectez-vous au serveur [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73968-109">In [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)], connect to the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="73968-110">Autrement dit, connectez-vous à l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] qui héberge la base de données [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="73968-110">That is, connect to the instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] that hosts the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="73968-111">Dans l'Explorateur d'objets, développez l'arborescence pour afficher le nœud **Integration Services Catalogues** .</span><span class="sxs-lookup"><span data-stu-id="73968-111">In Object Explorer, expand the tree to display the **Integration Services Catalogs** node.</span></span>  
  
3.  <span data-ttu-id="73968-112">Développez le nœud **Catalogues Integration Services** pour afficher le nœud **SSISDB** .</span><span class="sxs-lookup"><span data-stu-id="73968-112">Expand the **Integration Services Catalogs** node to display the **SSISDB** node.</span></span>  
  
4.  <span data-ttu-id="73968-113">Développez le nœud **SSISDB** pour afficher une liste d'un ou de plusieurs dossiers.</span><span class="sxs-lookup"><span data-stu-id="73968-113">Expand the **SSISDB** node to display a list of one or more folders.</span></span> <span data-ttu-id="73968-114">Chaque dossier contient un ou plusieurs projets dans le dossier **Projets** et chaque projet contient un ou plusieurs packages dans le dossier **Packages** .</span><span class="sxs-lookup"><span data-stu-id="73968-114">Each folder contains one or more projects in the **Projects** folder, and each project contains one more packages in the **Packages** folder.</span></span>  
  
  
