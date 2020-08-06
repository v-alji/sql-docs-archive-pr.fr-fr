---
title: Modifier la disponibilité d’un opérateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent jobs, operators
- canceling operators
- reactivating operators
- removing operators
- deleting operators
- available operators [SQL Server]
- dropping operators
- jobs [SQL Server Agent], operators
- notifications [SQL Server], job status
- disabling operators
- operators (users) [Database Engine], changing availability with Management Studio
ms.assetid: 10d58b92-b67b-47e2-af9c-9f9fd6968bba
author: stevestein
ms.author: sstein
ms.openlocfilehash: fb369ea6a2d1edf1ed8f4377b627fb1ba7339a03
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614343"
---
# <a name="change-an-operator39s-availability"></a><span data-ttu-id="003fd-102">Modifier la disponibilité d’un opérateur</span><span class="sxs-lookup"><span data-stu-id="003fd-102">Change an Operator&#39;s Availability</span></span>
  <span data-ttu-id="003fd-103">Cette rubrique explique comment modifier la disponibilité d'un opérateur pour la réception des notifications d'alertes dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="003fd-103">This topic describes how to change an operator's schedule for receiving alert notifications in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="003fd-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="003fd-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="003fd-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="003fd-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="003fd-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="003fd-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="003fd-107">**Pour modifier la disponibilité d'un opérateur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="003fd-107">**To change an operator's availability, using:**</span></span>  
  
     [<span data-ttu-id="003fd-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="003fd-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="003fd-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="003fd-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="003fd-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="003fd-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="003fd-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="003fd-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="003fd-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="003fd-112">Permissions</span></span>  
 <span data-ttu-id="003fd-113">Seuls les membres du rôle serveur fixe **sysadmin** peuvent modifier des opérateurs.</span><span class="sxs-lookup"><span data-stu-id="003fd-113">Only members of the **sysadmin** fixed server role can edit operators.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="003fd-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="003fd-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="003fd-115">Pour modifier la disponibilité d'un opérateur</span><span class="sxs-lookup"><span data-stu-id="003fd-115">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="003fd-116">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient l'opérateur que vous souhaitez activer ou désactiver.</span><span class="sxs-lookup"><span data-stu-id="003fd-116">In **Object Explorer**, click the plus sign to expand server that contains the operator that you want to enable or disable.</span></span>  
  
2.  <span data-ttu-id="003fd-117">Cliquez sur le signe plus (+) pour développer **Agent SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="003fd-117">Click the plus sign to expand **SQL Server Agent**.</span></span>  
  
3.  <span data-ttu-id="003fd-118">Cliquez sur le signe plus (+) pour développer le dossier **Opérateurs** .</span><span class="sxs-lookup"><span data-stu-id="003fd-118">Click the plus sign to expand the **Operators** folder.</span></span>  
  
4.  <span data-ttu-id="003fd-119">Cliquez avec le bouton droit sur l’opérateur que vous souhaitez activer ou désactiver et sélectionnez **Propriétés**, puis cliquez sur l’onglet **Général** .</span><span class="sxs-lookup"><span data-stu-id="003fd-119">Right-click the operator that you want to enable or disable and select **Properties**, then click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="003fd-120">Dans la boîte de dialogue**Propriétés** de la _operator_name_, activez ou désactivez la case à cocher **activé** .</span><span class="sxs-lookup"><span data-stu-id="003fd-120">In the _operator_name_**Properties** dialog box, select or clear the **Enabled** check box.</span></span>  
  
6.  <span data-ttu-id="003fd-121">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="003fd-121">Click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="003fd-122">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="003fd-122">Using Transact-SQL</span></span>  
  
#### <a name="to-change-an-operators-availability"></a><span data-ttu-id="003fd-123">Pour modifier la disponibilité d'un opérateur</span><span class="sxs-lookup"><span data-stu-id="003fd-123">To change an operator's availability</span></span>  
  
1.  <span data-ttu-id="003fd-124">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="003fd-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="003fd-125">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="003fd-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="003fd-126">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="003fd-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- disables the 'Fran??ois Ajenstat' operator  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_update_operator   
        @name = N'Fran??ois Ajenstat',  
        @enabled = 0;  
    GO  
    ```  
  
 <span data-ttu-id="003fd-127">Pour plus d’informations, consultez [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="003fd-127">For more information, see [sp_update_operator &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-update-operator-transact-sql).</span></span>  
  
  
