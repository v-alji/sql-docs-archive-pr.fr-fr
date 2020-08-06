---
title: Afficher les propriétés d’une facette de la gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, view facet properties
ms.assetid: 022a244c-c2e7-4467-b9a2-c7a27859be22
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea24ff2768ecaeec426a8689455912d848b54813
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603427"
---
# <a name="view-the-properties-of-a-policy-based-management-facet"></a><span data-ttu-id="77b70-102">Afficher les propriétés d'une facette de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="77b70-102">View the Properties of a Policy-Based Management Facet</span></span>
  <span data-ttu-id="77b70-103">Cette rubrique explique comment afficher les propriétés d'une facette de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77b70-103">This topic describes how to view the properties of a Policy-Based Management facet in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="77b70-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="77b70-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="77b70-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="77b70-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="77b70-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="77b70-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="77b70-107">**Pour afficher les propriétés d'une facette à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="77b70-107">**To view the properties of a facet, using:**</span></span>  
  
     [<span data-ttu-id="77b70-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77b70-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="77b70-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="77b70-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="77b70-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="77b70-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="77b70-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="77b70-111">Permissions</span></span>  
 <span data-ttu-id="77b70-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="77b70-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="77b70-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77b70-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-view-the-properties-of-a-facet"></a><span data-ttu-id="77b70-114">Pour afficher les propriétés d'une facette</span><span class="sxs-lookup"><span data-stu-id="77b70-114">To view the properties of a facet</span></span>  
  
1.  <span data-ttu-id="77b70-115">Dans l' **Explorateur d'objets**, cliquez sur le signe plus (+) pour développer le serveur qui contient la facette dont vous souhaiter afficher les propriétés.</span><span class="sxs-lookup"><span data-stu-id="77b70-115">In **Object Explorer**, click the plus sign to expand the server that contains the facet whose properties you want to view.</span></span>  
  
2.  <span data-ttu-id="77b70-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="77b70-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="77b70-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="77b70-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="77b70-118">Cliquez sur le signe plus (+) pour développer le dossier **Facettes** .</span><span class="sxs-lookup"><span data-stu-id="77b70-118">Click the plus sign to expand the **Facets** folder.</span></span>  
  
5.  <span data-ttu-id="77b70-119">Cliquez avec le bouton droit sur la facette dont vous souhaitez afficher les propriétés, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="77b70-119">Right-click the facet whose properties you want to view and select **Properties**.</span></span> <span data-ttu-id="77b70-120">Pour plus d’informations sur les options disponibles dans la boîte de dialogue **Propriétés de la facette -**_nom_facette_, consultez [Boîte de dialogue Propriétés de la facette, page Général](../../integration-services/general-page-of-integration-services-designers-options.md), [Boîte de dialogue Propriétés de la facette, page Stratégies dépendantes](facet-properties-dialog-box-dependent-policies-page.md) et [Boîte de dialogue Propriétés de la facette, page Conditions dépendantes](facet-properties-dialog-box-dependent-conditions-page.md).</span><span class="sxs-lookup"><span data-stu-id="77b70-120">For more information on the available options in the **Facet Properties -**_facet_name_ dialog box, see [Facet Properties Dialog Box, General Page](../../integration-services/general-page-of-integration-services-designers-options.md), [Facet Properties Dialog Box, Dependent Policies Page](facet-properties-dialog-box-dependent-policies-page.md), and [Facet Properties Dialog Box, Dependent Conditions Page](facet-properties-dialog-box-dependent-conditions-page.md).</span></span>  
  
6.  <span data-ttu-id="77b70-121">Lorsque vous avez terminé, cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="77b70-121">When finished, click **Close**.</span></span>  
  
  
