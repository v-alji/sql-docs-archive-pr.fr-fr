---
title: Afficher les informations relatives à une alerte | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, alerts
- viewing alerts
- alerts [SQL Server], viewing
- displaying alerts
- status information [SQL Server], alerts
ms.assetid: a0e3a8c4-e3c2-42a5-b2f8-aa06061d3fa6
author: stevestein
ms.author: sstein
ms.openlocfilehash: ee72512a507299e71f13fee689709a9403bb04e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603770"
---
# <a name="view-information-about-an-alert"></a><span data-ttu-id="d94b5-102">Afficher les informations relatives à une alerte</span><span class="sxs-lookup"><span data-stu-id="d94b5-102">View Information About an Alert</span></span>
  <span data-ttu-id="d94b5-103">Cette rubrique explique comment afficher des informations sur les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertes de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d94b5-103">This topic describes how to view information about [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="d94b5-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d94b5-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d94b5-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d94b5-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d94b5-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d94b5-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d94b5-107">**Pour afficher des informations relatives à une alerte, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d94b5-107">**To view information about an alert, using:**</span></span>  
  
     [<span data-ttu-id="d94b5-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d94b5-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="d94b5-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d94b5-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d94b5-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d94b5-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d94b5-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d94b5-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="d94b5-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="d94b5-112">Permissions</span></span>  
 <span data-ttu-id="d94b5-113">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent afficher des informations sur une alerte.</span><span class="sxs-lookup"><span data-stu-id="d94b5-113">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="d94b5-114">Les autres utilisateurs doivent disposer du rôle de base de données fixe **SQLAgentOperatorRole** dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="d94b5-114">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d94b5-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d94b5-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="d94b5-116">Pour afficher des informations relatives à une alerte</span><span class="sxs-lookup"><span data-stu-id="d94b5-116">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="d94b5-117">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez afficher des informations sur une alerte.</span><span class="sxs-lookup"><span data-stu-id="d94b5-117">In **Object Explorer,** click the plus sign to expand the server where you want to view information about an alert.</span></span>  
  
2.  <span data-ttu-id="d94b5-118">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="d94b5-118">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="d94b5-119">Cliquez sur le signe plus (+) pour développer le dossier **Alertes** .</span><span class="sxs-lookup"><span data-stu-id="d94b5-119">Click the plus sign to expand the **Alerts** folder.</span></span>  
  
4.  <span data-ttu-id="d94b5-120">Cliquez avec le bouton droit sur l'alerte comportant les informations que vous voulez afficher, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d94b5-120">Right-click the alert that has the information you want to view and select **Properties**.</span></span>  
  
     <span data-ttu-id="d94b5-121">Pour plus d’informations sur les options disponibles contenues dans la boîte de dialogue _Propriétés de l’alerte_**nom_alerte** , consultez :</span><span class="sxs-lookup"><span data-stu-id="d94b5-121">For more information on the available options contained in the _alert_name_**alert properties** dialog box, see:</span></span>  
  
    -   [<span data-ttu-id="d94b5-122">Propriétés de l’alerte-nouvelle alerte &#40;page général&#41;</span><span class="sxs-lookup"><span data-stu-id="d94b5-122">Alert Properties-New Alert &#40;General Page&#41;</span></span>](../../integration-services/general-page-of-integration-services-designers-options.md)  
  
    -   [<span data-ttu-id="d94b5-123">Propriétés de l’alerte-page nouvelle réponse &#40;alerte&#41;</span><span class="sxs-lookup"><span data-stu-id="d94b5-123">Alert Properties-New Alert &#40;Response Page&#41;</span></span>](alert-properties-new-alert-response-page.md)  
  
    -   [<span data-ttu-id="d94b5-124">Propriétés de l’alerte : nouvelle page d’options &#40;d’alerte&#41;</span><span class="sxs-lookup"><span data-stu-id="d94b5-124">Alert Properties: New Alert &#40;Options Page&#41;</span></span>](alert-properties-new-alert-options-page.md)  
  
    -   [<span data-ttu-id="d94b5-125">Propriétés de l'alerte &#40;page Historique&#41;</span><span class="sxs-lookup"><span data-stu-id="d94b5-125">Alert Properties &#40;History Page&#41;</span></span>](alert-properties-history-page.md)  
  
5.  <span data-ttu-id="d94b5-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="d94b5-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="d94b5-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d94b5-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-information-about-an-alert"></a><span data-ttu-id="d94b5-128">Pour afficher des informations relatives à une alerte</span><span class="sxs-lookup"><span data-stu-id="d94b5-128">To view information about an alert</span></span>  
  
1.  <span data-ttu-id="d94b5-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d94b5-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d94b5-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d94b5-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d94b5-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d94b5-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- reports information about the Demo: Sev. 25 Errors alert  
    -- This example assumes that the 'Demo: Sev. 25 Errors' alert exists.  
    USE msdb ;  
    GO  
  
    EXEC sp_help_alert @alert_name = 'Demo: Sev. 25 Errors'  
    GO  
    ```  
  
 <span data-ttu-id="d94b5-132">Pour plus d’informations, consultez [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d94b5-132">For more information, see [sp_help_alert &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-help-alert-transact-sql).</span></span>  
  
  
