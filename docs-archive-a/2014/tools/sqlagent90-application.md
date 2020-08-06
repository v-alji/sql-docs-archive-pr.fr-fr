---
title: Application sqlagent90 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- starting SQL Server Agent
- sqlagent90 application
- SQL Server Agent, starting
- command prompt utilities [SQL Server], sqlagent90
ms.assetid: e8b80e8d-d0c9-4500-a868-0ce08233da08
author: stevestein
ms.author: sstein
ms.openlocfilehash: 290cb69f39aa3b08bb290c210b2d37977614a1ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603174"
---
# <a name="sqlagent90-application"></a><span data-ttu-id="6a1e5-102">application sqlagent90</span><span class="sxs-lookup"><span data-stu-id="6a1e5-102">sqlagent90 Application</span></span>
  <span data-ttu-id="6a1e5-103">L’application **sqlagent90** démarre [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent à partir de l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-103">The **sqlagent90** application starts [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent from the command prompt.</span></span> <span data-ttu-id="6a1e5-104">En règle générale, l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] doit être exécuté à partir de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ou en utilisant des méthodes SQL-SMO dans une application.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-104">Usually, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent should be run from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] or by using SQL-SMO methods in an application.</span></span> <span data-ttu-id="6a1e5-105">N’exécutez **sqlagent90** à partir de l’invite de commandes que si vous effectuez un diagnostic de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, ou lorsque vous y êtes invité par votre fournisseur de support principal.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-105">Only run **sqlagent90** from the command prompt when you are diagnosing [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent, or when you are directed to it by your primary support provider.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1e5-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6a1e5-106">Syntax</span></span>  
  
```  
  
sqlagent90  
-c [-v] [-iinstance_name]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6a1e5-107">Arguments</span><span class="sxs-lookup"><span data-stu-id="6a1e5-107">Arguments</span></span>  
 <span data-ttu-id="6a1e5-108">**-c**</span><span class="sxs-lookup"><span data-stu-id="6a1e5-108">**-c**</span></span>  
 <span data-ttu-id="6a1e5-109">Indique que l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] s'exécute depuis l'invite de commandes et est indépendant du Gestionnaire de contrôle du service Windows.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-109">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent is running from the command prompt and is independent of the Microsoft Windows Services Control Manager.</span></span> <span data-ttu-id="6a1e5-110">Lorsque **-c** est utilisé, l’Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] ne peut pas être commandé depuis l’application Services dans les Outils d’administration ni depuis le Gestionnaire de configuration de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a1e5-110">When **-c** is used, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent cannot be controlled from either the Services application in Administrative Tools or [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Configuration Manager.</span></span> <span data-ttu-id="6a1e5-111">Cet argument est obligatoire.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-111">This argument is mandatory.</span></span>  
  
 <span data-ttu-id="6a1e5-112">**-v**</span><span class="sxs-lookup"><span data-stu-id="6a1e5-112">**-v**</span></span>  
 <span data-ttu-id="6a1e5-113">Indique que l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] s'exécute en mode documenté et inscrit les informations de diagnostic dans la fenêtre de l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-113">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent runs in verbose mode and writes diagnostic information to the command-prompt window.</span></span> <span data-ttu-id="6a1e5-114">Les informations de diagnostic sont semblables à celles inscrites dans le journal des erreurs de l'Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6a1e5-114">The diagnostic information is the same as the information written to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent error log.</span></span>  
  
 <span data-ttu-id="6a1e5-115">**-i** *instance_name*</span><span class="sxs-lookup"><span data-stu-id="6a1e5-115">**-i** *instance_name*</span></span>  
 <span data-ttu-id="6a1e5-116">Indique que l’Agent [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] se connecte à l’instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nommée qui est spécifiée par l’argument *instance_name*.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-116">Indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Agent connects to the named [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance specified by *instance_name*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a1e5-117">Notes</span><span class="sxs-lookup"><span data-stu-id="6a1e5-117">Remarks</span></span>  
 <span data-ttu-id="6a1e5-118">Après avoir affiché un message de copyright, **sqlagent90** ne présente une sortie dans la fenêtre d’invite de commandes que si le commutateur **-v** a été spécifié.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-118">After displaying a copyright message, **sqlagent90** displays output in the command prompt window only when the **-v** switch is specified.</span></span> <span data-ttu-id="6a1e5-119">Pour arrêter **sqlagent90**, appuyez sur CTRL+C à l’invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-119">To stop **sqlagent90**, press CTRL+C at the command prompt.</span></span> <span data-ttu-id="6a1e5-120">Ne fermez pas la fenêtre d’invite de commandes avant d’arrêter **sqlagent90**.</span><span class="sxs-lookup"><span data-stu-id="6a1e5-120">Do not close the command-prompt window before stopping **sqlagent90**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a1e5-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6a1e5-121">See Also</span></span>  
 [<span data-ttu-id="6a1e5-122">Tâches d’administration automatisée &#40;SQL Server Agent&#41;</span><span class="sxs-lookup"><span data-stu-id="6a1e5-122">Automated Administration Tasks &#40;SQL Server Agent&#41;</span></span>](../ssms/agent/automated-administration-tasks-sql-server-agent.md)  
  
  
