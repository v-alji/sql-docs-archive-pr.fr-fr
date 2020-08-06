---
title: Synchroniser les horloges des serveurs cibles (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, target servers
- clocks [SQL Server]
- master servers [SQL Server], clock synchronization
- synchronization [SQL Server], target server clocks
- target servers [SQL Server], clock synchronization
ms.assetid: 4fb80502-d271-4d06-bcbc-bfbbceb5f2a2
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8e7150cd42699503ab22cdd89fb6206194bd64e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695244"
---
# <a name="synchronize-target-server-clocks-sql-server-management-studio"></a><span data-ttu-id="c7087-102">Synchroniser les horloges des serveurs cibles (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="c7087-102">Synchronize Target Server Clocks (SQL Server Management Studio)</span></span>
  <span data-ttu-id="c7087-103">Cette rubrique décrit la procédure de synchronisation des horloges des serveurs cibles dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] avec celle du serveur maître à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7087-103">This topic describes how to synchronize target server clocks in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] with the master server clock by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="c7087-104">La synchronisation de ces horloges système gère vos planifications de travail.</span><span class="sxs-lookup"><span data-stu-id="c7087-104">Synchronizing these system clocks supports your job schedules.</span></span>  
  
 <span data-ttu-id="c7087-105">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="c7087-105">**In This Topic**</span></span>  
  
-   <span data-ttu-id="c7087-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c7087-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c7087-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c7087-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c7087-108">**Pour synchroniser les horloges des serveurs cibles, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c7087-108">**To synchronize target server clocks, using:**</span></span>  
  
     [<span data-ttu-id="c7087-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7087-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="c7087-110">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7087-110">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c7087-111">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c7087-111">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c7087-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c7087-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c7087-113">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c7087-113">Permissions</span></span>  
 <span data-ttu-id="c7087-114">Nécessite l'appartenance au rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="c7087-114">Requires membership in the **sysadmin** fixed server role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="c7087-115">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c7087-115">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="c7087-116">Pour synchroniser les horloges des serveurs cibles</span><span class="sxs-lookup"><span data-stu-id="c7087-116">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="c7087-117">Dans l' **Explorateur d'objets** , cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez synchroniser les horloges des serveurs cibles avec celle du serveur maître.</span><span class="sxs-lookup"><span data-stu-id="c7087-117">In **Object Explorer,** click the plus sign to expand the server where you want to synchronize the target server clocks with the master server clock.</span></span>  
  
2.  <span data-ttu-id="c7087-118">Cliquez avec le bouton droit sur **SQL Server Agent**, pointez sur **Administration multiserveur**, puis sélectionnez **Gérer les serveurs cibles**.</span><span class="sxs-lookup"><span data-stu-id="c7087-118">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and select **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="c7087-119">Dans la boîte de dialogue **Gérer les serveurs cibles** , cliquez sur **Publier les instructions**.</span><span class="sxs-lookup"><span data-stu-id="c7087-119">In the **Manage Target Servers** dialog box, click **Post Instructions**.</span></span>  
  
4.  <span data-ttu-id="c7087-120">Dans la liste **Type d'instruction** , cliquez sur **Synchroniser les horloges**.</span><span class="sxs-lookup"><span data-stu-id="c7087-120">In the **Instruction type** list, select **Synchronize clocks**.</span></span>  
  
5.  <span data-ttu-id="c7087-121">Sous **Destinataires**, activez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="c7087-121">Under **Recipients**, do one of the following:</span></span>  
  
    -   <span data-ttu-id="c7087-122">Cliquez sur **Tous les serveurs cibles** pour synchroniser les horloges de tous les serveurs cibles avec celle du serveur maître.</span><span class="sxs-lookup"><span data-stu-id="c7087-122">Click **All target servers** to synchronize all target server clocks with the master server clock.</span></span>  
  
    -   <span data-ttu-id="c7087-123">Cliquez sur **Serveurs cible sélectionnés** pour synchroniser l'horloge de certains serveurs, puis sélectionnez chacun des serveurs cibles dont vous souhaitez synchroniser l'horloge avec celle du serveur maître.</span><span class="sxs-lookup"><span data-stu-id="c7087-123">Click **These target servers** to synchronize certain server clocks, and then select each target server whose clock you want to synchronize with the master server clock.</span></span>  
  
6.  <span data-ttu-id="c7087-124">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7087-124">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="c7087-125">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c7087-125">Using Transact-SQL</span></span>  
  
#### <a name="to-synchronize-target-server-clocks"></a><span data-ttu-id="c7087-126">Pour synchroniser les horloges des serveurs cibles</span><span class="sxs-lookup"><span data-stu-id="c7087-126">To synchronize target server clocks</span></span>  
  
1.  <span data-ttu-id="c7087-127">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7087-127">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="c7087-128">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="c7087-128">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="c7087-129">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="c7087-129">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb ;  
    GO  
    -- resynchronizes the SEATTLE1 target server  
    EXEC dbo.sp_resync_targetserver  
        N'SEATTLE1' ;  
    GO  
    ```  
  
 <span data-ttu-id="c7087-130">Pour plus d’informations, consultez [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c7087-130">For more information, see [sp_resync_targetserver &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-resync-targetserver-transact-sql).</span></span>  
  
  
