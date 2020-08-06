---
title: Désigner un opérateur de prévention de défaillance | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- fail-safe operator [SQL Server]
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
ms.assetid: 0f4eb513-5c0a-4523-974e-e85c1deeb57f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 714ed78875bd289f2fe2d64a5699c59bce58ced0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705883"
---
# <a name="designate-a-fail-safe-operator"></a><span data-ttu-id="5a0bf-102">Désigner un opérateur de prévention de défaillance</span><span class="sxs-lookup"><span data-stu-id="5a0bf-102">Designate a Fail-Safe Operator</span></span>
  <span data-ttu-id="5a0bf-103">Un opérateur de prévention de défaillance est un utilisateur qui reçoit l'alerte si l'opérateur désigné n'est pas joignable.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-103">A fail-safe operator is a user who receives the alert if the designated operator cannot be reached.</span></span> <span data-ttu-id="5a0bf-104">Cette rubrique explique comment définir un opérateur de prévention de défaillance pour recevoir [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] des notifications d’alerte de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5a0bf-104">This topic describes how to set a fail-safe operator to receive [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="5a0bf-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5a0bf-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5a0bf-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5a0bf-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5a0bf-107">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5a0bf-107">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="5a0bf-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a0bf-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5a0bf-109">**Pour désigner un opérateur de prévention de défaillance, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5a0bf-109">**To designate a fail-safe operator, using:**</span></span>  
  
     [<span data-ttu-id="5a0bf-110">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a0bf-110">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5a0bf-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5a0bf-111">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="5a0bf-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="5a0bf-112">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="5a0bf-113">Les options du récepteur de radiomessagerie et **net send** seront supprimées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans une version future de [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5a0bf-113">The Pager and **net send** options will be removed from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent in a future version of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5a0bf-114">Évitez d'utiliser ces fonctionnalités dans une nouvelle tâche de développement et prévoyez de modifier les applications qui les utilisent actuellement.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-114">Avoid using these features in new development work, and plan to modify applications that currently use these features.</span></span>  
  
-   <span data-ttu-id="5a0bf-115">Remarque : SQL Server Agent doit être configuré pour utiliser la messagerie de base de données pour envoyer des notifications aux opérateurs par messagerie électronique ou radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-115">Note that SQL Server Agent must be configured to use Database Mail to send e-mail and pager notifications to operators.</span></span> <span data-ttu-id="5a0bf-116">Pour plus d'informations, consultez [Affecter des alertes à un opérateur](assign-alerts-to-an-operator.md).</span><span class="sxs-lookup"><span data-stu-id="5a0bf-116">For more information, see [Assign Alerts to an Operator](assign-alerts-to-an-operator.md).</span></span>  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="5a0bf-117">est un outil dont l'interface graphique permet de gérer facilement les travaux. Son utilisation est recommandée pour créer et gérer l'infrastructure des travaux.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-117">provides an easy, graphical way to manage jobs, and is the recommended way to create and manage the job infrastructure.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5a0bf-118">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5a0bf-118">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5a0bf-119">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5a0bf-119">Permissions</span></span>  
 <span data-ttu-id="5a0bf-120">Seuls les membres du rôle serveur fixe **sysadmin** peuvent désigner des opérateurs de prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-120">Only members of the **sysadmin** fixed server role can designate fail-safe operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5a0bf-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5a0bf-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-designate-a-fail-safe-operator"></a><span data-ttu-id="5a0bf-122">Pour désigner un opérateur de prévention de défaillance</span><span class="sxs-lookup"><span data-stu-id="5a0bf-122">To designate a fail-safe operator</span></span>  
  
1.  <span data-ttu-id="5a0bf-123">Dans **l’Explorateur d’objets** , cliquez sur le signe plus pour développer le serveur qui contient l’opérateur de SQL Server Agent que vous souhaitez désigner comme opérateur de prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-123">In **Object Explorer,** click the plus sign to expand the server that contains the SQL Server Agent operator that you want to designate as a fail-safe.</span></span>  
  
2.  <span data-ttu-id="5a0bf-124">Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-124">Right-click **SQL Server Agent** and select **Properties**.</span></span>  

3.  <span data-ttu-id="5a0bf-125">Dans la boîte de dialogue Propriétés de la **SQL Server Agent-**_Server_name_ , sous **Sélectionner une page**, sélectionnez **système d’alerte**.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-125">In the **SQL Server Agent Properties -**_server_name_ dialog box, under **Select a page**, select **Alert System**.</span></span>  
 
4.  <span data-ttu-id="5a0bf-126">Sous **Opérateur de prévention de défaillance**, sélectionnez **Activer l’opérateur de prévention de défaillance**.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-126">Under **Fail-safe operator**, select **Enable fail-safe operator**.</span></span>  
  
5.  <span data-ttu-id="5a0bf-127">Dans la liste **Opérateur** , sélectionnez l’opérateur que vous souhaitez définir comme opérateur de prévention de défaillance.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-127">In the **Operator** list, select the operator that you want to make a fail-safe.</span></span>  
  
6.  <span data-ttu-id="5a0bf-128">Cochez tout ou partie des cases suivantes pour spécifier comment l’opérateur doit être informé : **Messagerie électronique**, **Radiomessagerie**ou **NET SEND**.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-128">Select either any or all of the following check boxes to specify how the operator will be notified: **E-mail**, **Pager**, or **Net send**.</span></span>  
  
7.  <span data-ttu-id="5a0bf-129">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5a0bf-129">When finished, click **OK**.</span></span>  
  
  
