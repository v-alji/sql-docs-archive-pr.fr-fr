---
title: Exporter une stratégie de gestion basée sur des stratégies | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, export policy
ms.assetid: f0001b33-9078-4432-8460-496736fb325a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 15f554aeeebfd47c3fa1ea13b100fbe6bcfcc055
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610622"
---
# <a name="export-a-policy-based-management-policy"></a><span data-ttu-id="aadac-102">Exporter une stratégie de gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="aadac-102">Export a Policy-Based Management Policy</span></span>
  <span data-ttu-id="aadac-103">Cette rubrique explique comment exporter une stratégie de gestion basée sur des stratégies dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aadac-103">This topic describes how to export a Policy-Based Management policy in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="aadac-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="aadac-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="aadac-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="aadac-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="aadac-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aadac-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="aadac-107">**Pour exporter une stratégie à l'aide de :**</span><span class="sxs-lookup"><span data-stu-id="aadac-107">**To export a policy, using:**</span></span>  
  
     [<span data-ttu-id="aadac-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aadac-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="aadac-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="aadac-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="aadac-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="aadac-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="aadac-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="aadac-111">Permissions</span></span>  
 <span data-ttu-id="aadac-112">Nécessite l'appartenance au rôle PolicyAdministratorRole dans la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="aadac-112">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="aadac-113">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="aadac-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-export-a-policy"></a><span data-ttu-id="aadac-114">Pour exporter une stratégie</span><span class="sxs-lookup"><span data-stu-id="aadac-114">To export a policy</span></span>  
  
1.  <span data-ttu-id="aadac-115">Dans l'Explorateur d'objets, cliquez sur le signe plus (+) pour développer la stratégie de gestion basée sur des stratégies que vous souhaitez exporter.</span><span class="sxs-lookup"><span data-stu-id="aadac-115">In Object Explorer, click the plus sign to expand the server that contains the Policy-Based Management policy that you want to export.</span></span>  
  
2.  <span data-ttu-id="aadac-116">Cliquez sur le signe plus (+) pour développer le dossier **Gestion** .</span><span class="sxs-lookup"><span data-stu-id="aadac-116">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="aadac-117">Cliquez sur le signe plus (+) pour développer **Gestion de la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="aadac-117">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="aadac-118">Cliquez sur le signe plus (+) pour développer le dossier **Stratégies** .</span><span class="sxs-lookup"><span data-stu-id="aadac-118">Click the plus sign to expand the **Policies** folder.</span></span>  
  
5.  <span data-ttu-id="aadac-119">Cliquez avec le bouton droit sur la stratégie à exporter, puis sélectionnez **Exporter la stratégie**.</span><span class="sxs-lookup"><span data-stu-id="aadac-119">Right-click the policy that you want to export and select **Export Policy**.</span></span>  
  
6.  <span data-ttu-id="aadac-120">Dans la boîte de dialogue **Exporter la stratégie** , tapez le chemin d'accès et le nom du fichier dans la barre d'adresses.</span><span class="sxs-lookup"><span data-stu-id="aadac-120">In the **Export Policy** dialog box, type the path and name of the file in the address bar.</span></span> <span data-ttu-id="aadac-121">Ou bien, recherchez un emplacement approprié pour le fichier dans le volet de navigation de la boîte de dialogue, puis tapez le nom du fichier XML dans la zone **Nom de fichier** .</span><span class="sxs-lookup"><span data-stu-id="aadac-121">Alternately, find a suitable location for the file in the dialog box's navigation pane, and then type the name of the XML file in the **File Name** box.</span></span>  
  
7.  <span data-ttu-id="aadac-122">Lorsque vous avez terminé, cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="aadac-122">When finished, click **Save**.</span></span>  
  
  
