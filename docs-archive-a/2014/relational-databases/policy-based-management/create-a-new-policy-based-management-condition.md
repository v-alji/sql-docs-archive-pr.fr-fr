---
title: Créer une condition de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, creating policy conditions
ms.assetid: 8a612f7e-6c70-49db-a4de-48431e097cc5
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: e4fe206c9a82b69101508f6f0a760ca9c1bc423d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610629"
---
# <a name="create-a-new-policy-based-management-condition"></a><span data-ttu-id="67458-102">Créer une condition de gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="67458-102">Create a New Policy-Based Management Condition</span></span>
  <span data-ttu-id="67458-103">Cette rubrique explique comment créer une condition de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67458-103">This topic describes how to create a Policy-based Management condition in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="67458-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="67458-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="67458-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="67458-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="67458-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="67458-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="67458-107">**Pour créer une condition à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="67458-107">**To create a condition, using:**</span></span>  
  
     [<span data-ttu-id="67458-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67458-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="67458-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="67458-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="67458-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="67458-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="67458-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="67458-111">Permissions</span></span>  
 <span data-ttu-id="67458-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="67458-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="67458-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="67458-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-condition"></a><span data-ttu-id="67458-114">Pour créer une condition</span><span class="sxs-lookup"><span data-stu-id="67458-114">To create a condition</span></span>  
  
1.  <span data-ttu-id="67458-115">Dans l’ **Explorateur d’objets**, cliquez sur le signe plus (+) pour développer le serveur sur lequel vous souhaitez créer une condition de gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="67458-115">In **Object Explorer**, click the plus sign to expand the server where you want to create a Policy-based Management condition.</span></span>  
  
2.  <span data-ttu-id="67458-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="67458-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="67458-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="67458-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="67458-118">Cliquez sur le signe plus (+) pour développer le dossier **Facettes** .</span><span class="sxs-lookup"><span data-stu-id="67458-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="67458-119">Cliquez avec le bouton droit sur la facette dans laquelle vous souhaitez créer une nouvelle condition et sélectionnez **Nouvelle condition**.</span><span class="sxs-lookup"><span data-stu-id="67458-119">Right-click the facet in which you want to create a new condition and select **New Condition**.</span></span>  
  
6.  <span data-ttu-id="67458-120">Dans la boîte de dialogue **Créer une nouvelle condition** , dans la zone **Nom** , tapez le nom de la nouvelle condition.</span><span class="sxs-lookup"><span data-stu-id="67458-120">In the **Create New Condition** dialog box, in the **Name** box, type the name of the new condition.</span></span>  
  
7.  <span data-ttu-id="67458-121">Confirmez la facette correcte dans la liste **Facette** ou sélectionnez une facette différente.</span><span class="sxs-lookup"><span data-stu-id="67458-121">Confirm the correct facet in the **Facet** list, or select a different facet.</span></span>  
  
8.  <span data-ttu-id="67458-122">Sous **Expression**, construisez des expressions de condition en sélectionnant une propriété de facette dans la zone **Champ** , avec son opérateur et sa valeur associés.</span><span class="sxs-lookup"><span data-stu-id="67458-122">Under **Expression**, construct condition expressions by selecting a facet property in the **Field** box, together with its associated operator and value.</span></span> <span data-ttu-id="67458-123">Lorsque vous ajoutez plusieurs expressions, celles-ci peuvent être jointes à l'aide de **Et** ou **Ou**.</span><span class="sxs-lookup"><span data-stu-id="67458-123">When you add multiple expressions, the expressions can be joined by using **And** or **Or**.</span></span> <span data-ttu-id="67458-124">Pour plus d’informations sur les options disponibles dans cette boîte de dialogue, consultez [Boîte de dialogue Créer une nouvelle condition ou Ouvrir une condition, page Général](../../integration-services/general-page-of-integration-services-designers-options.md), [Boîte de dialogue Créer une nouvelle condition ou Ouvrir une condition, page Description](create-new-condition-or-open-condition-dialog-box-description-page.md) et [Boîte de dialogue Modification avancée &#40;Condition&#41;](advanced-edit-condition-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="67458-124">For more information on the available options in this dialog box, see [Create New Condition or Open Condition Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Create New Condition or Open Condition Dialog Box, Description Page](create-new-condition-or-open-condition-dialog-box-description-page.md), and [Advanced Edit &#40;Condition&#41; Dialog Box](advanced-edit-condition-dialog-box.md).</span></span>  
  
9. <span data-ttu-id="67458-125">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67458-125">When finished, click **OK**.</span></span>  
  
  
