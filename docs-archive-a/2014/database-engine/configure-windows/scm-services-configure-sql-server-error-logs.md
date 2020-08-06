---
title: Configurer les journaux des erreurs SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8acc27150f42049384e2789ef83ae66a737da9bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614845"
---
# <a name="configure-sql-server-error-logs"></a><span data-ttu-id="a9338-102">Configurer des journaux d'erreurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9338-102">Configure SQL Server Error Logs</span></span>
  <span data-ttu-id="a9338-103">Cette rubrique indique comment consulter ou modifier la méthode de recyclage des journaux d'erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9338-103">This topic describes how to view or modify the way [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs are recycled.</span></span>  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a><span data-ttu-id="a9338-104">Pour ouvrir la boîte de dialogue Configurer les journaux d'erreurs SQL Server</span><span class="sxs-lookup"><span data-stu-id="a9338-104">To open the Configure SQL Server Error Logs dialog box</span></span>  
  
1.  <span data-ttu-id="a9338-105">Dans l’Explorateur d’objets, développez l’instance de SQL Server, puis **Gestion**, cliquez avec le bouton droit sur **Journaux SQL Server**, puis sélectionnez **Configurer**.</span><span class="sxs-lookup"><span data-stu-id="a9338-105">In Object Explorer, expand the instance of SQL Server, expand **Management**, right-click **SQL Server Logs**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="a9338-106">Dans la boîte de dialogue **Configurer les journaux d'erreurs SQL Server** , choisissez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="a9338-106">In the **Configure SQL Server Error Logs** dialog box, choose from the following options.</span></span>  
  
     <span data-ttu-id="a9338-107">**Limiter le nombre de fichiers de journaux d'erreurs avant qu'ils ne soient recyclés**</span><span class="sxs-lookup"><span data-stu-id="a9338-107">**Limit the number of the error log files before they are recycled**</span></span>  
     <span data-ttu-id="a9338-108">Activez cette option pour limiter le nombre de journaux d'erreurs créés avant le recyclage.</span><span class="sxs-lookup"><span data-stu-id="a9338-108">Check to limit the number of error logs created before they are recycled.</span></span> <span data-ttu-id="a9338-109">Un nouveau journal des erreurs est créé à chaque démarrage d'une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a9338-109">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="a9338-110">conserve des copies de sauvegarde des six derniers journaux, sauf si vous avez activé cette option et spécifié un autre nombre maximal de fichiers de journaux des erreurs ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a9338-110">retains backups of the previous six logs, unless you check this option, and specify a different maximum number of error log files below.</span></span>  
  
     <span data-ttu-id="a9338-111">**Nombre maximal de fichiers de journaux d'erreurs**</span><span class="sxs-lookup"><span data-stu-id="a9338-111">**Maximum number of error log files**</span></span>  
     <span data-ttu-id="a9338-112">Spécifiez le nombre maximal de fichiers de journaux d'erreurs pouvant être créés avant le recyclage.</span><span class="sxs-lookup"><span data-stu-id="a9338-112">Specify the maximum number of error log files created before they are recycled.</span></span> <span data-ttu-id="a9338-113">La valeur par défaut est 6, ce qui correspond au nombre de journaux sauvegardés que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conserve avant de les recycler.</span><span class="sxs-lookup"><span data-stu-id="a9338-113">The default is 6, which is the number of previous backup logs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains before recycling them.</span></span>  
  
  
