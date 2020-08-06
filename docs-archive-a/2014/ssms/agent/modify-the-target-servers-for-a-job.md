---
title: Modifier les serveurs cibles pour un travail | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- modifying target servers
- SQL Server Agent jobs, target servers
- target servers [SQL Server], modifying
ms.assetid: 9dbe24f2-acec-4aa2-920c-e8e96efa18e4
author: stevestein
ms.author: sstein
ms.openlocfilehash: 246a5bb59a681a70734cc8cabef4f724cda1b52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603786"
---
# <a name="modify-the-target-servers-for-a-job"></a><span data-ttu-id="0c351-102">Modify the Target Servers for a Job</span><span class="sxs-lookup"><span data-stu-id="0c351-102">Modify the Target Servers for a Job</span></span>
  <span data-ttu-id="0c351-103">Cette rubrique explique comment modifier les serveurs cibles pour les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] travaux de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c351-103">This topic describes how to change the target servers for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent jobs in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="0c351-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0c351-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0c351-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="0c351-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0c351-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0c351-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0c351-107">**Pour modifier les serveurs cibles pour un travail à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="0c351-107">**To modify the target servers for a job, using:**</span></span>  
  
     [<span data-ttu-id="0c351-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c351-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0c351-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c351-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c351-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0c351-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0c351-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0c351-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="0c351-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="0c351-112">Permissions</span></span>  
 <span data-ttu-id="0c351-113">Par défaut, les membres du rôle serveur fixe sysadmin peuvent exécuter cette procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="0c351-113">By default, members of the sysadmin fixed server role can execute this stored procedure.</span></span> <span data-ttu-id="0c351-114">Les autres utilisateurs doivent disposer de l'un des rôles de base de données fixes de l'Agent SQL Server suivants dans la base de données msdb :</span><span class="sxs-lookup"><span data-stu-id="0c351-114">Other users must be granted one of the following SQL Server Agent fixed database roles in the msdb database:</span></span>  
  
1.  `SQLAgentUserRole`  
  
2.  `SQLAgentReaderRole`  
  
3.  <span data-ttu-id="0c351-115">SQLAgentOperatorRole</span><span class="sxs-lookup"><span data-stu-id="0c351-115">SQLAgentOperatorRole</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0c351-116">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c351-116">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="0c351-117">Pour modifier les serveurs cibles pour un travail</span><span class="sxs-lookup"><span data-stu-id="0c351-117">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="0c351-118">Dans l' **Explorateur d’objets,** Connectez-vous à une instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] , puis développez cette instance.</span><span class="sxs-lookup"><span data-stu-id="0c351-118">In **Object Explorer,** connect to an instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="0c351-119">Développez **l’Agent SQL Server**, développez **Travaux**, cliquez avec le bouton droit sur un travail, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0c351-119">Expand **SQL Server Agent**, expand **Jobs**, right-click a job, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="0c351-120">Dans la boîte de dialogue **Propriétés du travail** , sélectionnez la page **Cibles**, puis cliquez sur **Serveur cible local**ou sur **Plusieurs serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="0c351-120">In the **Job Properties** dialog, select the **Targets**page, and click **Target local server**, or **Target multiple servers**.</span></span>  
  
     <span data-ttu-id="0c351-121">Si vous choisissez **Plusieurs serveurs cibles**, désignez les serveurs qui seront les cibles pour le travail en activant la case à cocher figurant à gauche du nom du serveur.</span><span class="sxs-lookup"><span data-stu-id="0c351-121">If you choose **Target multiple servers**, designate the servers that will be targets for the job by checking the box to the left of the server name.</span></span> <span data-ttu-id="0c351-122">Vérifiez que les cases à cocher correspondant aux serveurs qui ne seront pas des cibles sont désactivées.</span><span class="sxs-lookup"><span data-stu-id="0c351-122">Verify that the check boxes for servers that will not be targets of the job are unchecked.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0c351-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c351-123">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-target-servers-for-a-job"></a><span data-ttu-id="0c351-124">Pour modifier les serveurs cibles pour un travail</span><span class="sxs-lookup"><span data-stu-id="0c351-124">To modify the target servers for a job</span></span>  
  
1.  <span data-ttu-id="0c351-125">Connectez-vous au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c351-125">Connect to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c351-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="0c351-126">From the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0c351-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0c351-127">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0c351-128">Cet exemple attribue le travail multiserveur Weekly Sales Backups au serveur SEATTLE2.</span><span class="sxs-lookup"><span data-stu-id="0c351-128">This example assigns the multiserver job Weekly Sales Backups to the server SEATTLE2.</span></span>  
  
```  
USE msdb ;  
GO  
  
EXEC dbo.sp_add_jobserver  
    @job_name = N'Weekly Sales Backups',   
    @server_name = N'SEATTLE2' ;   
GO  
  
```  
  
 <span data-ttu-id="0c351-129">Pour plus d’informations, consultez [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="0c351-129">For more information, see [sp_add_jobserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-add-jobserver-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c351-130"> Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c351-130">See Also</span></span>  
 [<span data-ttu-id="0c351-131">Administration automatisée à l'échelle d'une entreprise</span><span class="sxs-lookup"><span data-stu-id="0c351-131">Automated Administration Across an Enterprise</span></span>](automated-administration-across-an-enterprise.md)  
  
  
