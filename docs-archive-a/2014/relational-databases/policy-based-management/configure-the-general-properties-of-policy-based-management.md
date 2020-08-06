---
title: Configurer les propriétés générales de la gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
f1_keywords:
- sql12.swb.dmf.PolicyManagement.f1
helpviewer_keywords:
- Policy-Based Management, configure properties
ms.assetid: 6d1e0e37-29ea-408a-a055-384984d884be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a2efb37fafa29bcb043dedbcfa8719d0092b1c77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699473"
---
# <a name="configure-the-general-properties-of-policy-based-management"></a><span data-ttu-id="92830-102">Configurer les propriétés générales de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="92830-102">Configure the General Properties of Policy-Based Management</span></span>
  <span data-ttu-id="92830-103">Cette rubrique explique comment configurer les propriétés de la gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92830-103">This topic describes how to configure the properties for Policy-Based Management in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="92830-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="92830-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="92830-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="92830-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="92830-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="92830-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="92830-107">**Pour configurer la gestion basée sur des stratégies à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="92830-107">**To configure Policy-Based Management, using:**</span></span>  
  
     [<span data-ttu-id="92830-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92830-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="92830-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92830-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="92830-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="92830-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="92830-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="92830-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="92830-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="92830-112">Permissions</span></span>  
 <span data-ttu-id="92830-113">Nécessite l'appartenance au rôle de base de données fixe PolicyAdministratorRole.</span><span class="sxs-lookup"><span data-stu-id="92830-113">Requires membership in the PolicyAdministratorRole fixed database role.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="92830-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="92830-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="92830-115">Pour configurer la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="92830-115">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="92830-116">Dans l’ **Explorateur d’objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous voulez configurer les propriétés de la gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="92830-116">In **Object Explorer**, click the plus sign to expand the server where you want to configure Policy-Based Management properties.</span></span>  
  
2.  <span data-ttu-id="92830-117">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="92830-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="92830-118">Cliquez avec le bouton droit sur **Gestion de la stratégie** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="92830-118">Right-click **Policy Management** and select **Properties**.</span></span>  
  
     <span data-ttu-id="92830-119">Les options suivantes sont disponibles dans la boîte de dialogue **Propriétés de gestion de la stratégie** .</span><span class="sxs-lookup"><span data-stu-id="92830-119">The following options are available in **Policy Management Properties** dialog box.</span></span>  
  
     <span data-ttu-id="92830-120">**Activé**</span><span class="sxs-lookup"><span data-stu-id="92830-120">**Enabled**</span></span>  
     <span data-ttu-id="92830-121">Spécifie si la Gestion basée sur des stratégies est activée.</span><span class="sxs-lookup"><span data-stu-id="92830-121">Specifies whether Policy-Based Management is enabled.</span></span>  
  
     <span data-ttu-id="92830-122">**HistoryRetentionInDays**</span><span class="sxs-lookup"><span data-stu-id="92830-122">**HistoryRetentionInDays**</span></span>  
     <span data-ttu-id="92830-123">Spécifie le nombre de jours pendant lesquels l'historique des évaluations de stratégies doit être conservé.</span><span class="sxs-lookup"><span data-stu-id="92830-123">Specifies the number of days that policy evaluation history should be retained.</span></span> <span data-ttu-id="92830-124">Si cette valeur est 0 (valeur par défaut), l'historique n'est pas supprimé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="92830-124">If this value is 0 (the default), the history will not be automatically removed.</span></span>  
  
     <span data-ttu-id="92830-125">**LogOnSuccess**</span><span class="sxs-lookup"><span data-stu-id="92830-125">**LogOnSuccess**</span></span>  
     <span data-ttu-id="92830-126">Spécifie si la Gestion basée sur des stratégies consigne les évaluations de stratégies réussies.</span><span class="sxs-lookup"><span data-stu-id="92830-126">Specifies whether Policy-Based Management logs successful policy evaluations.</span></span>  
  
    -   <span data-ttu-id="92830-127">Lorsque cette valeur est False (valeur par défaut), seules les évaluations de stratégies qui ont échoué sont consignées.</span><span class="sxs-lookup"><span data-stu-id="92830-127">When this value is false (the default), only failed policy evaluations are logged.</span></span>  
  
    -   <span data-ttu-id="92830-128">Lorsque cette valeur est True, les réussites et les échecs des évaluations de stratégies sont enregistrés.</span><span class="sxs-lookup"><span data-stu-id="92830-128">When this value is true, both successful and failed policy evaluations are logged.</span></span>  
  
4.  <span data-ttu-id="92830-129">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="92830-129">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="92830-130">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="92830-130">Using Transact-SQL</span></span>  
  
#### <a name="to-configure-policy-based-management"></a><span data-ttu-id="92830-131">Pour configurer la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="92830-131">To configure Policy-Based Management</span></span>  
  
1.  <span data-ttu-id="92830-132">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92830-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="92830-133">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="92830-133">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="92830-134">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="92830-134">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- enables Policy-Based Management   
    USE msdb;  
    GO  
    EXEC dbo.sp_syspolicy_configure   
         @name = N'Enabled',   
         @value = 1;  
    GO  
    ```  
  
 <span data-ttu-id="92830-135">Pour plus d’informations, consultez [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="92830-135">For more information, see [sp_syspolicy_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-syspolicy-configure-transact-sql).</span></span>  
  
  
