---
title: Afficher les facettes de gestion basée sur des stratégies sur un objet SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facets
ms.assetid: 5f423b9f-a6c4-41a7-9d8d-8f4926ce1fb4
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9137971a79e9e5a18e0ef5d901184133a4c3eff3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603428"
---
# <a name="view-the-policy-based-management-facets-on-a-sql-server-object"></a><span data-ttu-id="f0ab3-102">Afficher les facettes de gestion basée sur des stratégies sur un objet SQL Server</span><span class="sxs-lookup"><span data-stu-id="f0ab3-102">View the Policy-Based Management Facets on a SQL Server Object</span></span>
  <span data-ttu-id="f0ab3-103">Cette rubrique explique comment afficher toutes les facettes de gestion basée sur des stratégies appliquées à un objet spécifique de SQL Server dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f0ab3-103">This topic describes how to view all of the Policy-Based Management facets applied to a specific SQL Server object in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f0ab3-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="f0ab3-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f0ab3-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="f0ab3-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f0ab3-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0ab3-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f0ab3-107">**Pour afficher toutes les facettes dans un objet à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="f0ab3-107">**To view all of the facets in an object, using:**</span></span>  
  
     [<span data-ttu-id="f0ab3-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0ab3-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f0ab3-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="f0ab3-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f0ab3-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="f0ab3-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f0ab3-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="f0ab3-111">Permissions</span></span>  
 <span data-ttu-id="f0ab3-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="f0ab3-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f0ab3-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f0ab3-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-all-of-the-facets-in-an-object"></a><span data-ttu-id="f0ab3-114">Pour afficher toutes les facettes dans un objet</span><span class="sxs-lookup"><span data-stu-id="f0ab3-114">To view all of the facets in an object</span></span>  
  
1.  <span data-ttu-id="f0ab3-115">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un objet d’instance, une base de données ou un objet de base de données, puis cliquez sur **Facettes**.</span><span class="sxs-lookup"><span data-stu-id="f0ab3-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="f0ab3-116">Dans la boîte de dialogue **Afficher les facettes -**_nom_objet_, sélectionnez une facette dans la liste **Facette** pour afficher ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="f0ab3-116">In the **View Facets -**_object_name_ dialog box, in the **Facet** list, select a facet to view its properties.</span></span> <span data-ttu-id="f0ab3-117">Pour plus d'informations sur les options disponibles dans cette boîte de dialogue, consultez [View Facets Dialog Box](view-facets-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f0ab3-117">For more information on the available options in this dialog box, see [View Facets Dialog Box](view-facets-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="f0ab3-118">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0ab3-118">When finished, click **OK**.</span></span>  
  
  
