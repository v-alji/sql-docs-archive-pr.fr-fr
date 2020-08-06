---
title: Journal des erreurs de SQL Server Agent | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], SQL Server Agent
- messages [SQL Server], SQL Server Agent
- errors [SQL Server], logs
- SQL Server Agent, errors
ms.assetid: 0b2d6e6e-cd2d-4b8b-9fa2-2bbd2fc0da41
author: stevestein
ms.author: sstein
ms.openlocfilehash: ea9a723695c6993f4f07897f49d8014a86ce78b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699167"
---
# <a name="sql-server-agent-error-log"></a><span data-ttu-id="2410f-102">Journal des erreurs de SQL Server Agent</span><span class="sxs-lookup"><span data-stu-id="2410f-102">SQL Server Agent Error Log</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2410f-103">Agent crée un journal des erreurs qui, par défaut, enregistre les avertissements et les erreurs.</span><span class="sxs-lookup"><span data-stu-id="2410f-103">Agent creates an error log that records warnings and errors by default.</span></span> <span data-ttu-id="2410f-104">Le journal contient :</span><span class="sxs-lookup"><span data-stu-id="2410f-104">The following warnings and errors are displayed in the log:</span></span>  
  
-   <span data-ttu-id="2410f-105">Messages d’avertissement qui fournissent des informations sur les problèmes potentiels, tels que « la tâche \<*job_name*> a été supprimée pendant son exécution ».</span><span class="sxs-lookup"><span data-stu-id="2410f-105">Warning messages that provide information about potential problems, such as "Job \<*job_name*> was deleted while it was running."</span></span>  
  
-   <span data-ttu-id="2410f-106">Des messages d'erreur dont la solution nécessite habituellement l'intervention d'un administrateur système, tels que « Impossible de démarrer la session de messagerie ».</span><span class="sxs-lookup"><span data-stu-id="2410f-106">Error messages that usually require intervention by a system administrator, such as "Unable to start mail session."</span></span> <span data-ttu-id="2410f-107">Les messages d’erreur peuvent être envoyés à un utilisateur ou un ordinateur spécifique via **net send**.</span><span class="sxs-lookup"><span data-stu-id="2410f-107">Error messages can be sent to a specific user or computer by **net send**.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2410f-108">conserve jusqu’à neuf journaux des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2410f-108">maintains up to nine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error logs.</span></span> <span data-ttu-id="2410f-109">Chaque journal des erreurs archivé possède un suffixe indiquant son ancienneté relative.</span><span class="sxs-lookup"><span data-stu-id="2410f-109">Each archived log has an extension that indicates the relative age of the log.</span></span> <span data-ttu-id="2410f-110">Par exemple, le suffixe .1 signale le journal des erreurs le plus récemment archivé alors que le suffixe .9 indique qu'il s'agit du plus ancien journal des erreurs existant.</span><span class="sxs-lookup"><span data-stu-id="2410f-110">For example, an extension of .1 indicates the newest archived error log and an extension of .9 indicates the oldest archived error log.</span></span>  
  
 <span data-ttu-id="2410f-111">Par défaut, les messages de trace d'exécution ne sont pas écrits dans le journal d'erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, parce qu'ils risquent de le remplir.</span><span class="sxs-lookup"><span data-stu-id="2410f-111">By default, execution trace messages are not written to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log, because they can fill it.</span></span> <span data-ttu-id="2410f-112">Lorsque le fichier d'erreurs est plein, votre possibilité de sélectionner et analyser les erreurs plus difficiles se trouve réduite.</span><span class="sxs-lookup"><span data-stu-id="2410f-112">When the error log is full, your ability to select and analyze more difficult errors is reduced.</span></span> <span data-ttu-id="2410f-113">Le journal étant une charge supplémentaire de travail pour le serveur, il est important de bien réfléchir à ce que la capture de messages de trace d’exécution dans le journal des erreurs vous apporte.</span><span class="sxs-lookup"><span data-stu-id="2410f-113">Because the log adds to the server's processing load, it is important to consider carefully what value you obtain by capturing execution trace messages to the error log.</span></span> <span data-ttu-id="2410f-114">Il est en général préférable de capturer tous les messages uniquement au moment de corriger un problème donné.</span><span class="sxs-lookup"><span data-stu-id="2410f-114">Generally, it is best to capture all messages only when you are debugging a specific problem.</span></span>  
  
 <span data-ttu-id="2410f-115">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent n'est pas activé, vous pouvez modifier l'emplacement du journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2410f-115">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is stopped, you can modify the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent error log.</span></span> <span data-ttu-id="2410f-116">Lorsque le journal est vide, il ne peut pas être ouvert.</span><span class="sxs-lookup"><span data-stu-id="2410f-116">When the error log is empty, the log cannot be opened.</span></span> <span data-ttu-id="2410f-117">Vous pouvez parcourir le journal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent à n'importe quel moment sans devoir interrompre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span><span class="sxs-lookup"><span data-stu-id="2410f-117">You can cycle the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent log at any time without stopping [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span>  
  
 <span data-ttu-id="2410f-118">**Pour afficher le journal des erreurs SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="2410f-118">**To view the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="2410f-119">Afficher le journal des erreurs SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2410f-119">View SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](view-sql-server-agent-error-log-sql-server-management-studio.md) 
  
 <span data-ttu-id="2410f-120">**Pour renommer le journal des erreurs SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="2410f-120">**To rename a SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="2410f-121">Renommer un journal d’erreurs SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2410f-121">Rename a SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](rename-a-sql-server-agent-error-log-sql-server-management-studio.md)  
  
 <span data-ttu-id="2410f-122">**Pour envoyer des messages d'erreur de SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="2410f-122">**To send SQL Server Agent error messages**</span></span>  
  
-   [<span data-ttu-id="2410f-123">Send SQL Server Agent Error Messages</span><span class="sxs-lookup"><span data-stu-id="2410f-123">Send SQL Server Agent Error Messages</span></span>](send-sql-server-agent-error-messages.md)  
  
 <span data-ttu-id="2410f-124">**Pour écrire des messages de trace d'exécution dans le journal des erreurs SQL Server Agent**</span><span class="sxs-lookup"><span data-stu-id="2410f-124">**To write execution trace messages to the SQL Server Agent error log**</span></span>  
  
-   [<span data-ttu-id="2410f-125">Écrire des messages de trace d’exécution dans le journal des erreurs SQL Server Agent &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="2410f-125">Write Execution Trace Messages to the SQL Server Agent Error Log &#40;SQL Server Management Studio&#41;</span></span>](write-execution-trace-messages-to-sql-server-agent-log-ssms.md)  
  
  
