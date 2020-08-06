---
title: Mettre en forme des adresses de radiomessagerie pour les alertes | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- pager addresses [SQL Server]
- SQL Server Agent, alerts
- formats [SQL Server], pager addresses
- pager notifications [SQL Server]
- addresses [SQL Server]
- alerts [SQL Server], pager addresses
ms.assetid: a9797d01-1050-442c-9038-ed4bfee1e76a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 471f9a4958f51491b312d89239a2204c907e25e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600462"
---
# <a name="format-pager-addresses-for-alerts"></a><span data-ttu-id="5c40a-102">Format Pager Addresses for Alerts</span><span class="sxs-lookup"><span data-stu-id="5c40a-102">Format Pager Addresses for Alerts</span></span>
  <span data-ttu-id="5c40a-103">Cette rubrique explique comment mettre en forme des adresses de radiomessagerie pour les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertes de l’agent dans à [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] l’aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5c40a-103">This topic describes how to format pager addresses for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="5c40a-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="5c40a-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="5c40a-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="5c40a-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="5c40a-106">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5c40a-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="5c40a-107">**Pour mettre en forme des adresses de radiomessagerie, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="5c40a-107">**To format pager addresses, using:**</span></span>  
  
     [<span data-ttu-id="5c40a-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c40a-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="5c40a-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="5c40a-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="5c40a-110">Sécurité</span><span class="sxs-lookup"><span data-stu-id="5c40a-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="5c40a-111">Autorisations</span><span class="sxs-lookup"><span data-stu-id="5c40a-111">Permissions</span></span>  
 <span data-ttu-id="5c40a-112">Par défaut, les membres du rôle serveur fixe **sysadmin** peuvent afficher des informations sur une alerte.</span><span class="sxs-lookup"><span data-stu-id="5c40a-112">By default, members of the **sysadmin** fixed server role can view information about an alert.</span></span> <span data-ttu-id="5c40a-113">Les autres utilisateurs doivent disposer du rôle de base de données fixe **SQLAgentOperatorRole** dans la base de données **msdb** .</span><span class="sxs-lookup"><span data-stu-id="5c40a-113">Other users must be granted the **SQLAgentOperatorRole** fixed database role in the **msdb** database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="5c40a-114">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="5c40a-114">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-format-pager-addresses"></a><span data-ttu-id="5c40a-115">Pour mettre en forme des adresses de radiomessagerie</span><span class="sxs-lookup"><span data-stu-id="5c40a-115">To format pager addresses</span></span>  
  
1.  <span data-ttu-id="5c40a-116">Dans l' **Explorateur d'objets**, cliquez sur le signe plus pour développer le serveur qui contient l'alerte que vous souhaitez envoyer à un récepteur de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="5c40a-116">In **Object Explorer**, click the plus sign to expand the server that contains the alert that you want to send to a pager.</span></span>  
  
2.  <span data-ttu-id="5c40a-117">Cliquez avec le bouton droit sur **Agent SQL Server** , puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="5c40a-117">Right-click **SQL Server Agent** and select **Properties**</span></span>  
  
3.  <span data-ttu-id="5c40a-118">Sous **Sélectionner une page**, sélectionnez **Système d'alerte**.</span><span class="sxs-lookup"><span data-stu-id="5c40a-118">Under **Select a page**, select **Alert System**.</span></span>  
  
4.  <span data-ttu-id="5c40a-119">Dans les zones **Ligne À** et **Ligne Cc** du champ **Format d’adresse pour les messages de radiomessagerie** , entrez le préfixe ou le suffixe de l’adresse de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="5c40a-119">In the **To line** and **CC line** boxes of the **Address formatting for pager e-mails** field, enter the pager address prefix or suffix.</span></span> <span data-ttu-id="5c40a-120">L'adresse réelle de radiomessagerie de l'opérateur est insérée lors de l'envoi d'une notification.</span><span class="sxs-lookup"><span data-stu-id="5c40a-120">The operator's actual pager address is inserted when a notification is sent.</span></span>  
  
5.  <span data-ttu-id="5c40a-121">Dans la zone **Objet** , entrez le préfixe ou le suffixe de la ligne Objet.</span><span class="sxs-lookup"><span data-stu-id="5c40a-121">In the **Subject** box, enter the subject line prefix or suffix.</span></span>  
  
6.  <span data-ttu-id="5c40a-122">Cochez la case **Inclure le corps du message dans la page de notification** pour inclure l’e-mail complet, ainsi que le message de radiomessagerie (contrairement à la ligne Objet uniquement).</span><span class="sxs-lookup"><span data-stu-id="5c40a-122">Select the **Include body of e-mail in notification page** check box to include the full e-mail message with the pager message (as opposed to the subject line only).</span></span>  
  
7.  <span data-ttu-id="5c40a-123">Lorsque vous avez terminé, cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c40a-123">When finished, click **OK**.</span></span>  
  
  
