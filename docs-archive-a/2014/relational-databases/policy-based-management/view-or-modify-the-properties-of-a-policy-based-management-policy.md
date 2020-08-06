---
title: Afficher ou modifier les propriétés d’une stratégie de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, modify policies
- Policy-Based Management, view policies
ms.assetid: ba805504-5db5-4731-a8da-a0e89cb20c37
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: da2226d3049a84098eb8e561635161f73b71ab10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603432"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-policy"></a><span data-ttu-id="810f4-102">Afficher ou modifier les propriétés d'une stratégie de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="810f4-102">View or Modify the Properties of a Policy-Based Management Policy</span></span>
  <span data-ttu-id="810f4-103">Cette rubrique décrit comment afficher ou modifier les propriétés d'une stratégie de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="810f4-103">This topic describes how to view or modify a Policy-Based Management policy's properties in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="810f4-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="810f4-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="810f4-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="810f4-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="810f4-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="810f4-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="810f4-107">**Pour afficher ou modifier les propriétés d'une stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="810f4-107">**To view or modify a policy's properties, using:**</span></span>  
  
     [<span data-ttu-id="810f4-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="810f4-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="810f4-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="810f4-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="810f4-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="810f4-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="810f4-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="810f4-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="810f4-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="810f4-112">Permissions</span></span>  
 <span data-ttu-id="810f4-113">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="810f4-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="810f4-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="810f4-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-all-policies-on-an-object"></a><span data-ttu-id="810f4-115">Pour afficher les propriétés de toutes les stratégies sur un objet</span><span class="sxs-lookup"><span data-stu-id="810f4-115">To view the properties of all policies on an object</span></span>  
  
1.  <span data-ttu-id="810f4-116">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur, un objet de serveur, une base de données ou un objet de base de données, pointez sur **Stratégies** et sélectionnez **Afficher**.</span><span class="sxs-lookup"><span data-stu-id="810f4-116">In Object Explorer, right-click a server, server object, database, or database object, point to **Policies** and select **View**.</span></span> <span data-ttu-id="810f4-117">Pour plus d’informations sur les options disponibles dans la boîte de dialogue **Afficher les stratégies -**_nom_objet_, consultez [Boîte de dialogue Afficher les stratégies](view-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="810f4-117">For more information on the available options in the **View Policies -**_object_name_ dialog box, see [View Policies Dialog Box](view-policies-dialog-box.md).</span></span>  
  
2.  <span data-ttu-id="810f4-118">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="810f4-118">When finished, click **Close**.</span></span>  
  
#### <a name="to-view-or-modify-a-specific-policys-properties"></a><span data-ttu-id="810f4-119">Pour afficher ou modifier les propriétés d'une stratégie spécifique</span><span class="sxs-lookup"><span data-stu-id="810f4-119">To view or modify a specific policy's properties</span></span>  
  
1.  <span data-ttu-id="810f4-120">Dans **l’Explorateur d’objets**, cliquez sur le signe plus (+) pour développer la stratégie de gestion basée sur des stratégies que vous souhaitez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="810f4-120">In **Object Explorer**, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="810f4-121">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="810f4-121">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="810f4-122">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="810f4-122">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="810f4-123">Cliquez sur le signe plus (+) pour développer le dossier **Stratégies** .</span><span class="sxs-lookup"><span data-stu-id="810f4-123">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="810f4-124">Cliquez avec le bouton droit sur la stratégie que vous souhaitez afficher ou modifier, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="810f4-124">Right-click the policy that you want to view or modify and select **Properties**.</span></span> <span data-ttu-id="810f4-125">Pour plus d’informations sur les options disponibles dans la boîte de dialogue **Créer une nouvelle stratégie -**_nom_stratégie_, consultez [Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Général](../../integration-services/general-page-of-integration-services-designers-options.md) et [Boîte de dialogue Créer une nouvelle stratégie ou Ouvrir une stratégie, page Description](create-new-policy-or-open-policy-dialog-box-description-page.md).</span><span class="sxs-lookup"><span data-stu-id="810f4-125">For more information on the available options in the **Open Policy -**_policy_name_ dialog box, see [Create New Policy or Open Policy Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md) and [Create New Policy or Open Policy Dialog Box, Description Page](create-new-policy-or-open-policy-dialog-box-description-page.md).</span></span>  
  
6.  <span data-ttu-id="810f4-126">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="810f4-126">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="810f4-127">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="810f4-127">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-policys-properties"></a><span data-ttu-id="810f4-128">Pour afficher les propriétés d'une stratégie</span><span class="sxs-lookup"><span data-stu-id="810f4-128">To view a policy's properties</span></span>  
  
1.  <span data-ttu-id="810f4-129">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="810f4-129">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="810f4-130">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="810f4-130">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="810f4-131">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="810f4-131">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       execution_mode,  
       description,  
       is_enabled,  
       job_id  
    FROM syspolicy_policies;  
    GO  
    ```  
  
 <span data-ttu-id="810f4-132">Pour plus d’informations, consultez [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="810f4-132">For more information, see [syspolicy_policies &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-policies-transact-sql).</span></span>  
  
  
