---
title: Notifier l’état d’un travail à un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- status information [SQL Server], jobs
- jobs [SQL Server Agent], notification options
- SQL Server Agent jobs, status
- jobs [SQL Server Agent], status
- SQL Server Agent jobs, notification options
- notifications [SQL Server], job status
ms.assetid: e7399505-27ac-48d9-a637-73bf92b9df49
author: stevestein
ms.author: sstein
ms.openlocfilehash: a202327ad63cf7ef8f51d3572b257816ee6d9419
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603781"
---
# <a name="notify-an-operator-of-job-status"></a><span data-ttu-id="d80b4-102">Notify an Operator of Job Status</span><span class="sxs-lookup"><span data-stu-id="d80b4-102">Notify an Operator of Job Status</span></span>
  <span data-ttu-id="d80b4-103">Cette rubrique explique comment définir des options de notification dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , [!INCLUDE[tsql](../../includes/tsql-md.md)] ou SQL Server Management Objects, de sorte que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent puisse envoyer des notifications aux opérateurs à propos des travaux.</span><span class="sxs-lookup"><span data-stu-id="d80b4-103">This topic describes how to set notification options in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], [!INCLUDE[tsql](../../includes/tsql-md.md)], or SQL Server Management Objects, so [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent can send notifications to operators about jobs.</span></span>  
  
 <span data-ttu-id="d80b4-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="d80b4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="d80b4-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="d80b4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="d80b4-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d80b4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="d80b4-107">**Pour notifier l'état d'un travail à un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="d80b4-107">**To notify an operator of job status, using:**</span></span>  
  
     [<span data-ttu-id="d80b4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d80b4-108">SQL Server Management Studio</span></span>](#SSMS)  
  
     [<span data-ttu-id="d80b4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d80b4-109">Transact-SQL</span></span>](#TSQL)  
  
     [<span data-ttu-id="d80b4-110">SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d80b4-110">SQL Server Management Objects</span></span>](#SMO)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="d80b4-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="d80b4-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="d80b4-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d80b4-112">Security</span></span>  
 <span data-ttu-id="d80b4-113">Pour plus d'informations, consultez [Implémenter la sécurité de SQL Server Agent](implement-sql-server-agent-security.md).</span><span class="sxs-lookup"><span data-stu-id="d80b4-113">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="d80b4-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d80b4-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="d80b4-115">Pour notifier l'état d'un travail à un opérateur</span><span class="sxs-lookup"><span data-stu-id="d80b4-115">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="d80b4-116">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="d80b4-116">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="d80b4-117">Développez **Agent SQL Server**, puis **Travaux**, cliquez avec le bouton droit sur le travail à modifier et sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="d80b4-117">Expand **SQL Server Agent**, expand **Jobs**, right-click the job you want to edit, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="d80b4-118">Dans la boîte de dialogue **Propriétés du travail** , sélectionnez la page **Notifications** .</span><span class="sxs-lookup"><span data-stu-id="d80b4-118">In the **Job Properties** dialog box, select the **Notifications** page.</span></span>  
  
4.  <span data-ttu-id="d80b4-119">Pour avertir un opérateur par e-mail, cochez la case **Messagerie électronique**, sélectionnez un opérateur dans la liste, puis l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d80b4-119">If you want to notify an operator by e-mail, check **E-mail**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="d80b4-120">**Lors de la réussite du travail** pour avertir l'opérateur quand le travail s'est effectué avec succès ;</span><span class="sxs-lookup"><span data-stu-id="d80b4-120">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="d80b4-121">**Lors de l'échec du travail** pour avertir l'opérateur quand le travail a échoué.</span><span class="sxs-lookup"><span data-stu-id="d80b4-121">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="d80b4-122">**Lorsque le travail est terminé** pour avertir l'opérateur, quel que soit l'état du travail à son achèvement.</span><span class="sxs-lookup"><span data-stu-id="d80b4-122">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
5.  <span data-ttu-id="d80b4-123">Pour avertir un opérateur par radiomessagerie, activez la case à cocher **Radiomessagerie**, sélectionnez un opérateur dans la liste, puis l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d80b4-123">If you want to notify an operator by pager, check **Page**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="d80b4-124">**Lors de la réussite du travail** pour avertir l'opérateur quand le travail s'est effectué avec succès ;</span><span class="sxs-lookup"><span data-stu-id="d80b4-124">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="d80b4-125">**Lors de l'échec du travail** pour avertir l'opérateur quand le travail a échoué.</span><span class="sxs-lookup"><span data-stu-id="d80b4-125">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="d80b4-126">**Lorsque le travail est terminé** pour avertir l'opérateur, quel que soit l'état du travail à son achèvement.</span><span class="sxs-lookup"><span data-stu-id="d80b4-126">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
6.  <span data-ttu-id="d80b4-127">Pour avertir un opérateur par envoi réseau, activez la case à cocher **Envoi réseau**, sélectionnez un opérateur dans la liste, puis l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d80b4-127">If you want to notify an operator by net send, check **Net send**, select an operator from the list, and then select one of the following:</span></span>  
  
    -   <span data-ttu-id="d80b4-128">**Lors de la réussite du travail** pour avertir l'opérateur quand le travail s'est effectué avec succès ;</span><span class="sxs-lookup"><span data-stu-id="d80b4-128">**When the job succeeds** to notify the operator when the job completes successfully.</span></span>  
  
    -   <span data-ttu-id="d80b4-129">**Lors de l'échec du travail** pour avertir l'opérateur quand le travail a échoué.</span><span class="sxs-lookup"><span data-stu-id="d80b4-129">**When the job fails** to notify the operator when the job completes unsuccessfully.</span></span>  
  
    -   <span data-ttu-id="d80b4-130">**Lorsque le travail est terminé** pour avertir l'opérateur, quel que soit l'état du travail à son achèvement.</span><span class="sxs-lookup"><span data-stu-id="d80b4-130">**When the job completes** to notify the operator regardless of completion status.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TSQL"></a> <span data-ttu-id="d80b4-131">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="d80b4-131">Using Transact-SQL</span></span>  
  
#### <a name="to-notify-an-operator-of-job-status"></a><span data-ttu-id="d80b4-132">Pour notifier l'état d'un travail à un opérateur</span><span class="sxs-lookup"><span data-stu-id="d80b4-132">To notify an operator of job status</span></span>  
  
1.  <span data-ttu-id="d80b4-133">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d80b4-133">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="d80b4-134">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="d80b4-134">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="d80b4-135">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="d80b4-135">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```sql
    -- adds an e-mail notification for the specified alert (Test Alert).  
    -- This example assumes that Test Alert already exists and that Fran??ois Ajenstat is a valid operator name.  
    USE msdb ;  
    GO  
    EXEC dbo.sp_add_notification   
    @alert_name = N'Test Alert',   
    @operator_name = N'Fran??ois Ajenstat',   
    @notification_method = 1 ;  
    GO  
    ```  
  
 <span data-ttu-id="d80b4-136">Pour plus d’informations, consultez [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d80b4-136">For more information, see [sp_add_notification &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-notification-transact-sql).</span></span>  
  
##  <a name="using-sql-server-management-objects"></a><a name="SMO"></a><span data-ttu-id="d80b4-137">Utilisation de SQL Server Management Objects</span><span class="sxs-lookup"><span data-stu-id="d80b4-137">Using SQL Server Management Objects</span></span>  
 <span data-ttu-id="d80b4-138">**Pour notifier l'état d'un travail à un opérateur**</span><span class="sxs-lookup"><span data-stu-id="d80b4-138">**To notify an operator of job status**</span></span>  
  
 <span data-ttu-id="d80b4-139">Utilisez la classe `Job` à l'aide d'un langage de programmation que vous choisissez, tel que Visual Basic, Visual C# ou PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d80b4-139">Use the `Job` class by using a programming language that you choose, such as Visual Basic, Visual C#, or PowerShell.</span></span> <span data-ttu-id="d80b4-140">Pour plus d’informations, consultez [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span><span class="sxs-lookup"><span data-stu-id="d80b4-140">For more information, see [SQL Server Management Objects (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).</span></span>  
