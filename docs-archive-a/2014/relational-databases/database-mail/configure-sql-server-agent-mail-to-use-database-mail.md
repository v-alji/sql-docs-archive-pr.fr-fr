---
title: Configurer la messagerie de SQL Server Agent en vue de l’utilisation de la messagerie de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- Database Mail [SQL Server], SQL Server Agent Mail
- SQL Server Agent Mail
ms.assetid: 4b8b61bd-4bd1-43cd-b6e5-c6ed2e101dce
author: stevestein
ms.author: sstein
ms.openlocfilehash: 31d116c0bc8d7e148fc2ef6d2e344400516ad923
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695707"
---
# <a name="configure-sql-server-agent-mail-to-use-database-mail"></a><span data-ttu-id="ed259-102">Configurer la messagerie de l'Agent SQL Server en vue de l'utilisation de la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="ed259-102">Configure SQL Server Agent Mail to Use Database Mail</span></span>
  <span data-ttu-id="ed259-103">Cette rubrique explique comment configurer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour utiliser la messagerie de base de données pour envoyer une notification et des alertes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ed259-103">This topic describes how to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to use Database Mail to send notification and alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="ed259-104">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="ed259-104">**Before you begin:**</span></span>  
  
-   [<span data-ttu-id="ed259-105">Composants requis</span><span class="sxs-lookup"><span data-stu-id="ed259-105">Prerequisites</span></span>](#Prerequisites)  
  
-   [<span data-ttu-id="ed259-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ed259-106">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="ed259-107">Pour configurer l'Agent SQL Server en vue de l'utilisation de la messagerie de base de données, à l'aide de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed259-107">To Configure SQL Server Agent to use Database Mail, using SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="ed259-108">Tâches de suivi</span><span class="sxs-lookup"><span data-stu-id="ed259-108">Follow-up Tasks</span></span>](#Follow_Up)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ed259-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="ed259-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="ed259-110">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="ed259-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="ed259-111">Activer la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed259-111">Enable Database Mail.</span></span>  
  
-   <span data-ttu-id="ed259-112">Créer un compte de messagerie de base de données pour le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent à utiliser.</span><span class="sxs-lookup"><span data-stu-id="ed259-112">Create a Database Mail account for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use.</span></span>  
  
-   <span data-ttu-id="ed259-113">Créer un profil de messagerie de base de données pour le compte de service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent à utiliser, et ajouter l'utilisateur au rôle **DatabaseMailUserRole** de la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="ed259-113">Create a Database Mail profile for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent service account to use and add the user to the **DatabaseMailUserRole** in the **msdb** database.</span></span>  
  
-   <span data-ttu-id="ed259-114">Définir le profil comme profil par défaut pour la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="ed259-114">Set the profile as the default profile for the **msdb** database.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ed259-115">Sécurité</span><span class="sxs-lookup"><span data-stu-id="ed259-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ed259-116">Autorisations</span><span class="sxs-lookup"><span data-stu-id="ed259-116">Permissions</span></span>  
 <span data-ttu-id="ed259-117">L'utilisateur qui crée les comptes de profils et exécute des procédures stockées doit être membre du rôle serveur fixe sysadmin.</span><span class="sxs-lookup"><span data-stu-id="ed259-117">The user creating the profiles accounts and executing stored procedures should be a member of the sysadmin fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ed259-118">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ed259-118">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="ed259-119">**Pour configurer l'Agent SQL Server en vue de l'utilisation de la messagerie de base de données**</span><span class="sxs-lookup"><span data-stu-id="ed259-119">**To configure SQL Server Agent to use Database Mail**</span></span>  
  
-   <span data-ttu-id="ed259-120">Dans l'Explorateur d'objets, développez une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ed259-120">In Object Explorer, expand a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="ed259-121">Cliquez avec le bouton droit sur **SQL Server Agent**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ed259-121">Right-click **SQL Server Agent**, and then click **Properties**.</span></span>  
  
-   <span data-ttu-id="ed259-122">Cliquez sur **Système d'alerte**.</span><span class="sxs-lookup"><span data-stu-id="ed259-122">Click **Alert System**.</span></span>  
  
-   <span data-ttu-id="ed259-123">Sélectionnez **Activer le profil de messagerie**.</span><span class="sxs-lookup"><span data-stu-id="ed259-123">Select **Enable Mail Profile**.</span></span>  
  
-   <span data-ttu-id="ed259-124">Dans la liste **Système de messagerie** , choisissez **Database Mail**.</span><span class="sxs-lookup"><span data-stu-id="ed259-124">In the **Mail system** list, select **Database Mail**.</span></span>  
  
-   <span data-ttu-id="ed259-125">Dans la liste **Profil de la messagerie**, sélectionnez un profil de messagerie pour la messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="ed259-125">In the **Mail profile list**, select a mail profile for Database Mail.</span></span>  
  
-   <span data-ttu-id="ed259-126">Redémarrez l'Agent SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ed259-126">Restart SQL Server Agent.</span></span>  
  
##  <a name="follow-up-tasks"></a><a name="Follow_Up"></a> <span data-ttu-id="ed259-127">Tâches de suivi</span><span class="sxs-lookup"><span data-stu-id="ed259-127">Follow-up Tasks</span></span>  
 <span data-ttu-id="ed259-128">Les tâches suivantes sont nécessaires pour terminer la configuration de l'Agent pour envoyer des alertes et des notifications.</span><span class="sxs-lookup"><span data-stu-id="ed259-128">The following tasks are necessary to complete the configuration of Agent to send alerts and notifications.</span></span>  
  
-   [<span data-ttu-id="ed259-129">Alertes</span><span class="sxs-lookup"><span data-stu-id="ed259-129">Alerts</span></span>](../../ssms/agent/alerts.md)  
  
     <span data-ttu-id="ed259-130">Les alertes peuvent être configurées pour notifier à un opérateur une situation du système d'exploitation ou un événement de base de données particuliers.</span><span class="sxs-lookup"><span data-stu-id="ed259-130">Alerts can be configured to notify an operator of a particular database event or operating system condition.</span></span>  
  
-   [<span data-ttu-id="ed259-131">Opérateurs</span><span class="sxs-lookup"><span data-stu-id="ed259-131">Operators</span></span>](../../ssms/agent/operators.md)  
  
     <span data-ttu-id="ed259-132">Les opérateurs sont des alias pour les personnes ou les groupes qui peuvent recevoir une notification électronique</span><span class="sxs-lookup"><span data-stu-id="ed259-132">Operators are aliases for people or groups that can receive electronic notification</span></span>  
  
  
