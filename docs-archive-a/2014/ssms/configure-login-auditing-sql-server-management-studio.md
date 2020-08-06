---
title: Configurer l’audit de connexion en cours (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7e05f6c254e098a67a5ce00435c009cd450af44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614304"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a><span data-ttu-id="97331-102">Configurer l'audit de connexion en cours (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="97331-102">Configure Login Auditing (SQL Server Management Studio)</span></span>
  <span data-ttu-id="97331-103">Cette rubrique explique comment configurer l'audit de connexion dans [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] pour surveiller l'activité de connexion de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97331-103">This topic describes how to configure login auditing in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] to monitor [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] login activity.</span></span> <span data-ttu-id="97331-104">L'audit de connexion en cours peut être configuré pour écrire les événements suivants dans le journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="97331-104">Login auditing can be configured to write to the error log on the following events.</span></span>  
  
-   <span data-ttu-id="97331-105">Échecs de connexion</span><span class="sxs-lookup"><span data-stu-id="97331-105">Failed logins</span></span>  
  
-   <span data-ttu-id="97331-106">Connexions réussies</span><span class="sxs-lookup"><span data-stu-id="97331-106">Successful logins</span></span>  
  
-   <span data-ttu-id="97331-107">Échecs et réussites de connexion</span><span class="sxs-lookup"><span data-stu-id="97331-107">Both failed and successful logins</span></span>  
  
 <span data-ttu-id="97331-108">Vous devez redémarrer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] pour que cette option prenne effet.</span><span class="sxs-lookup"><span data-stu-id="97331-108">You must restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before this option will take effect.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="97331-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="97331-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-login-auditing"></a><span data-ttu-id="97331-110">Pour configurer l'audit de connexion en cours</span><span class="sxs-lookup"><span data-stu-id="97331-110">To configure login auditing</span></span>  
  
1.  <span data-ttu-id="97331-111">Dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connectez-vous à une instance de [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] au moyen de l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="97331-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="97331-112">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nom du serveur, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="97331-112">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="97331-113">Dans la page **Sécurité** , sous **Audit de connexion en cours** , cliquez sur l’option de votre choix, puis fermez la page **Propriétés du serveur** .</span><span class="sxs-lookup"><span data-stu-id="97331-113">On the **Security** page, under **Login** auditing, click the desired option and close the **Server Properties** page.</span></span>  
  
4.  <span data-ttu-id="97331-114">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nom du serveur, puis cliquez sur **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="97331-114">In Object Explorer, right-click the server name, and then click **Restart**.</span></span>  
  
  
