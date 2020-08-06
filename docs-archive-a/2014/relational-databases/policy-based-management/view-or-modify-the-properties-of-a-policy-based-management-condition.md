---
title: Afficher ou modifier les propriétés d’une condition de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view policy conditions
- Policy-Based Management, modify policy conditions
ms.assetid: 890d7384-8444-4767-bb6f-f5debb155747
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 08baec48bd13445ef56ea6a29520d23ebaf683b1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603431"
---
# <a name="view-or-modify-the-properties-of-a-policy-based-management-condition"></a><span data-ttu-id="99f1b-102">Afficher ou modifier les propriétés d'une condition de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="99f1b-102">View or Modify the Properties of a Policy-Based Management Condition</span></span>
  <span data-ttu-id="99f1b-103">Cette rubrique explique comment afficher ou modifier les propriétés d'une condition de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99f1b-103">This topic describes how to view or modify the properties of a Policy-Based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="99f1b-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="99f1b-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="99f1b-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="99f1b-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="99f1b-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="99f1b-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="99f1b-107">**Pour afficher ou modifier les propriétés d'une condition à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="99f1b-107">**To view or modify a condition's properties, using:**</span></span>  
  
     [<span data-ttu-id="99f1b-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99f1b-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="99f1b-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99f1b-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="99f1b-110">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="99f1b-110">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="99f1b-111">Sécurité</span><span class="sxs-lookup"><span data-stu-id="99f1b-111">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="99f1b-112">Autorisations</span><span class="sxs-lookup"><span data-stu-id="99f1b-112">Permissions</span></span>  
 <span data-ttu-id="99f1b-113">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="99f1b-113">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="99f1b-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="99f1b-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-or-modify-a-conditions-properties"></a><span data-ttu-id="99f1b-115">Pour afficher ou modifier les propriétés d'une condition</span><span class="sxs-lookup"><span data-stu-id="99f1b-115">To view or modify a condition's properties</span></span>  
  
1.  <span data-ttu-id="99f1b-116">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la condition que vous souhaitez afficher ou modifier.</span><span class="sxs-lookup"><span data-stu-id="99f1b-116">In **Object Explorer**, click the plus sign to expand the server that contains the condition that you want to view or modify.</span></span>  
  
2.  <span data-ttu-id="99f1b-117">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="99f1b-117">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="99f1b-118">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="99f1b-118">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="99f1b-119">Cliquez sur le signe plus (+) pour développer le dossier **Conditions** .</span><span class="sxs-lookup"><span data-stu-id="99f1b-119">Click the plus sign to expand the **Conditions** folder.</span></span>  
  
5.  <span data-ttu-id="99f1b-120">Cliquez avec le bouton droit sur la condition à afficher ou supprimer, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="99f1b-120">Right-click the condition that you want to view or edit and select **Properties**.</span></span> <span data-ttu-id="99f1b-121">Pour plus d’informations sur les options disponibles dans la boîte de dialogue **ouvrir un**_condition_name_ de condition, consultez boîte de dialogue [créer une nouvelle condition ou ouvrir une condition, page général](../../integration-services/general-page-of-integration-services-designers-options.md), [boîte de dialogue Ouvrir une condition, page stratégies dépendantes](open-condition-dialog-box-dependent-policies-page.md), boîte de dialogue créer une [nouvelle condition ou ouvrir](create-new-condition-or-open-condition-dialog-box-description-page.md)une condition, page Description et boîte de dialogue [modification avancée des &#40;des conditions&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="99f1b-121">For more information on the available options in the **Open Condition -**_condition_name_ dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Open Condition Dialog Box, Dependent Policies Page](open-condition-dialog-box-dependent-policies-page.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="99f1b-122">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="99f1b-122">When finished, click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="99f1b-123">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="99f1b-123">Using Transact-SQL</span></span>  
  
#### <a name="to-view-a-conditions-properties"></a><span data-ttu-id="99f1b-124">Pour afficher les propriétés d'une condition</span><span class="sxs-lookup"><span data-stu-id="99f1b-124">To view a condition's properties</span></span>  
  
1.  <span data-ttu-id="99f1b-125">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="99f1b-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="99f1b-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="99f1b-126">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="99f1b-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="99f1b-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE msdb;  
    GO  
    SELECT name,  
       description,  
       facet,  
       expression,  
       is_name_condition,  
       obj_name  
    FROM syspolicy_conditions;  
    GO  
  
    ```  
  
 <span data-ttu-id="99f1b-128">Pour plus d’informations, consultez [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99f1b-128">For more information, see [syspolicy_conditions &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/syspolicy-conditions-transact-sql).</span></span>  
  
  
