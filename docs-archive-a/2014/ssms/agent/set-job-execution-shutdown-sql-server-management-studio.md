---
title: Définir l’arrêt de l’exécution d’un travail (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- jobs [SQL Server Agent], stopping
- SQL Server Agent jobs, stopping
- stopping jobs
- SQL Server Agent jobs, execution shutdowns
ms.assetid: ac23e88f-53fc-41de-bb16-0c27c002d5a5
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0e60807676c3c54faf1d44de318ff0a31c2e20b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613270"
---
# <a name="set-job-execution-shutdown-sql-server-management-studio"></a><span data-ttu-id="c292d-102">Définir l'arrêt de l'exécution d'un travail (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c292d-102">Set Job Execution Shutdown (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c292d-103">Cette rubrique explique comment définir le délai pendant lequel [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent doit attendre la fin de l’exécution des travaux avant la fin de l’exécution [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de l’agent lui-même dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c292d-103">This topic describes how to set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c292d-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c292d-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c292d-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c292d-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c292d-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c292d-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c292d-107">**Pour définir une heure d'arrêt pour un travail de SQL Server Agent, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c292d-107">**To set a shutdown time for a SQL Server Agent job, using:**</span></span>  
  
     [<span data-ttu-id="c292d-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c292d-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c292d-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c292d-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c292d-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c292d-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c292d-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c292d-111">Permissions</span></span>  
 <span data-ttu-id="c292d-112">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent définir la durée pendant laquelle [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent doit attendre la fin de l’exécution des travaux avant la fin de l’exécution de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent lui-même.</span><span class="sxs-lookup"><span data-stu-id="c292d-112">By default, members of the **sysadmin** fixed server role can set the time that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span> <span data-ttu-id="c292d-113">Les autres utilisateurs doivent disposer de l'un des rôles de base de données fixes suivants de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent dans la base de données **msdb** :</span><span class="sxs-lookup"><span data-stu-id="c292d-113">Other users must be granted one of the following [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent fixed database roles in the **msdb** database:</span></span>  
  
-   <span data-ttu-id="c292d-114">**SQLAgentUserRole**</span><span class="sxs-lookup"><span data-stu-id="c292d-114">**SQLAgentUserRole**</span></span>  
  
-   <span data-ttu-id="c292d-115">**SQLAgentReaderRole**</span><span class="sxs-lookup"><span data-stu-id="c292d-115">**SQLAgentReaderRole**</span></span>  
  
-   <span data-ttu-id="c292d-116">**SQLAgentOperatorRole**</span><span class="sxs-lookup"><span data-stu-id="c292d-116">**SQLAgentOperatorRole**</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c292d-117">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c292d-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-set-job-execution-shutdown"></a><span data-ttu-id="c292d-118">Pour définir l'arrêt de l'exécution d'un travail</span><span class="sxs-lookup"><span data-stu-id="c292d-118">To set job execution shutdown</span></span>  
  
1.  <span data-ttu-id="c292d-119">Dans **l’Explorateur d'objets,** , cliquez sur le signe plus pour développer le serveur sur lequel vous souhaitez définir un intervalle d'arrêt d'exécution d'un travail.</span><span class="sxs-lookup"><span data-stu-id="c292d-119">In **Object Explorer,** , click the plus sign to expand the server where you want to set a job execution shutdown interval.</span></span>  
  
2.  <span data-ttu-id="c292d-120">Cliquez avec le bouton droit sur **SQL Server Agent** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c292d-120">Right-click **SQL Server Agent** and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="c292d-121">Sous **Sélectionner une page**, sélectionnez **Système de travaux**.</span><span class="sxs-lookup"><span data-stu-id="c292d-121">Under **Select a page**, select **Job System**.</span></span>  
  
4.  <span data-ttu-id="c292d-122">Définissez **l’intervalle du délai d’arrêt** en secondes pour augmenter ou réduire l’intervalle d’arrêt.</span><span class="sxs-lookup"><span data-stu-id="c292d-122">Set the **Shutdown time-out interval** in seconds to increase or decrease the shutdown time-out interval.</span></span> <span data-ttu-id="c292d-123">Cette valeur détermine le délai d'attente pendant lequel [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent attend la fin de l'exécution des travaux avant la fin de l'exécution de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent lui-même.</span><span class="sxs-lookup"><span data-stu-id="c292d-123">This determines how long [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent will wait for executing jobs to finish before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent itself finishes.</span></span>  
  
  
