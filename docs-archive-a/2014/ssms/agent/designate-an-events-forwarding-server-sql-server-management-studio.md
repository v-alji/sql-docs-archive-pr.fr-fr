---
title: Désigner un serveur de transfert d’événements (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- event forwarding servers [SQL Server]
- events [SQL Server], forwarding
- alerts [SQL Server], forwarded events
ms.assetid: 81dfcbe4-3000-4e77-99de-bf85fef63a12
author: stevestein
ms.author: sstein
ms.openlocfilehash: bc5f01507bf893d1bffc682f65a01b9ff48ffa9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705879"
---
# <a name="designate-an-events-forwarding-server-sql-server-management-studio"></a><span data-ttu-id="ebe27-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ebe27-102">Designate an Events Forwarding Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ebe27-103">Cette rubrique explique comment désigner un serveur vers lequel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] transfère les événements dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ebe27-103">This topic describes how to designate a server to which [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] forwards events in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span></span> <span data-ttu-id="ebe27-104">Notez que le transfert d'événements s'applique aux événements transférés entre serveurs, et non aux événements transférés entre instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hébergées sur un même ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ebe27-104">Note that event forwarding applies to events forwarded between servers, not to events forwarded between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hosted on a single computer.</span></span> <span data-ttu-id="ebe27-105">Notez également qu'afin de recevoir les événements transférés, le serveur de gestion des alertes doit être une instance par défaut de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ebe27-105">Also note that in order to receive forwarded events, the alerts management server must be a default instance of SQL Server.</span></span>  
  
 <span data-ttu-id="ebe27-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="ebe27-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ebe27-107">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ebe27-107">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ebe27-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ebe27-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ebe27-109">**Pour désigner un serveur de transfert d'événements, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="ebe27-109">**To designate an events forwarding server, using:**</span></span>  
  
     [<span data-ttu-id="ebe27-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ebe27-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ebe27-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ebe27-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ebe27-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ebe27-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ebe27-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ebe27-113">Permissions</span></span>  
 <span data-ttu-id="ebe27-114">Nécessite l'appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="ebe27-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ebe27-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ebe27-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-an-events-forwarding-server"></a><span data-ttu-id="ebe27-116">Pour désigner un serveur de transfert d'événements</span><span class="sxs-lookup"><span data-stu-id="ebe27-116">To designate an events forwarding server</span></span>  
  
1.  <span data-ttu-id="ebe27-117">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur depuis lequel vous souhaitez transférer des événements vers un autre serveur.</span><span class="sxs-lookup"><span data-stu-id="ebe27-117">In **Object Explorer,** click the plus sign to expand the server from which you want to forward events to another server.</span></span>  
  
2.  <span data-ttu-id="ebe27-118">Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ebe27-118">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="ebe27-119">Dans la boîte de dialogue **Propriétés de SQL Server Agent -**_nom_serveur_, sous **Sélectionner une page**, sélectionnez **Avancé**.</span><span class="sxs-lookup"><span data-stu-id="ebe27-119">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Advanced**.</span></span>  

4.  <span data-ttu-id="ebe27-120">Sous **Transfert d'événements SQL Server**, sélectionnez la case à cocher **Transférer les événements sur un autre serveur** .</span><span class="sxs-lookup"><span data-stu-id="ebe27-120">Under **SQL Server event forwarding**, select the **Forward events to a different server** check box.</span></span>  
  
5.  <span data-ttu-id="ebe27-121">Dans la liste **Serveur** , sélectionnez un serveur, puis, sous **Événements**, sélectionnez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ebe27-121">In the **Server** list, select a server, and then, under **Events**, select one of the following:</span></span>  
  
    -   <span data-ttu-id="ebe27-122">Sélectionnez **Événements non gérés** pour ne transmettre que les événements qui n'ont pas été gérés par des alertes locales.</span><span class="sxs-lookup"><span data-stu-id="ebe27-122">Select **Unhandled events** to forward only the events that have not been handled by local alerts.</span></span>  
  
    -   <span data-ttu-id="ebe27-123">Sélectionnez **Tous les événements** pour transférer tous les événements, indépendamment de leur gestion par des alertes locales ou non.</span><span class="sxs-lookup"><span data-stu-id="ebe27-123">Select **All events** to forward all events regardless of whether they have been handled by local alerts.</span></span>  
  
6.  <span data-ttu-id="ebe27-124">Dans la liste **Si l'événement a une gravité au moins égale à** , cliquez sur le niveau de gravité auquel les événements sont transférés au serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ebe27-124">In the **If event has severity at or above** list, click the severity level at which events are forwarded to the selected server.</span></span>  
  
7.  <span data-ttu-id="ebe27-125">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebe27-125">When finished, click **OK**.</span></span>  
  
  
