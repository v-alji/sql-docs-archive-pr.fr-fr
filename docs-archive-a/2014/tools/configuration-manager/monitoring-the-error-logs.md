---
title: Surveillance des journaux d’erreurs | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server]
- database performance [SQL Server], errors
- Windows application logs [SQL Server]
- monitoring performance [SQL Server], errors
- server performance [SQL Server], errors
- comparing error and application log output
- errors [SQL Server], logs
- tuning databases [SQL Server], errors
- database monitoring [SQL Server], errors
- SQL Server error log
- logs [SQL Server], SQL Server error logs
- error logs [SQL Server]
- logs [SQL Server], Windows application logs
ms.assetid: e250336b-0695-44f6-a42f-23222f94e377
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2a47891599dbe735bd437f5239c73bfd34c422ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604788"
---
# <a name="monitoring-the-error-logs"></a><span data-ttu-id="93879-102">Surveillance des journaux d'erreurs</span><span class="sxs-lookup"><span data-stu-id="93879-102">Monitoring the Error Logs</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="93879-103">enregistre certains événements système ainsi que des événements définis par l’utilisateur dans le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le journal des applications [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="93879-103">logs certain system events and user-defined events to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span> <span data-ttu-id="93879-104">Tous les événements consignés dans ces deux journaux sont automatiquement datés.</span><span class="sxs-lookup"><span data-stu-id="93879-104">Both logs automatically timestamp all recorded events.</span></span> <span data-ttu-id="93879-105">Utilisez les informations du journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour résoudre des problèmes liés à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="93879-105">Use the information in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log to troubleshoot problems related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="93879-106">Le journal des applications Windows fournit une vue d'ensemble des événements survenus dans le système d'exploitation Windows, ainsi que des événements survenus dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et dans l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93879-106">The Windows application log provides an overall picture of events that occur on the Windows operating system, as well as events in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent.</span></span> <span data-ttu-id="93879-107">Utilisez l'Observateur d'événements Windows pour afficher le journal des applications Windows et filtrer les informations.</span><span class="sxs-lookup"><span data-stu-id="93879-107">Use the Windows Event Viewer to view the Windows application log and to filter the information.</span></span> <span data-ttu-id="93879-108">Par exemple, vous pouvez filtrer des d'événements, comme les informations, les avertissements, les erreurs, les audits de succès et les audits d'échecs.</span><span class="sxs-lookup"><span data-stu-id="93879-108">For example, you can filter events, such as information, warning, error, success audit, and failure audit.</span></span>  
  
## <a name="comparing-error-and-application-log-output"></a><span data-ttu-id="93879-109">comparaison des sorties des journaux d'erreurs et des applications</span><span class="sxs-lookup"><span data-stu-id="93879-109">Comparing Error and Application Log Output</span></span>  
 <span data-ttu-id="93879-110">Vous pouvez utiliser le journal des erreurs de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le journal des applications Windows pour identifier les causes des problèmes.</span><span class="sxs-lookup"><span data-stu-id="93879-110">You can use both the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and the Windows application log to identify the cause of problems.</span></span> <span data-ttu-id="93879-111">Par exemple, pendant la surveillance du journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous pouvez rencontrer des messages d'erreur qui ne contiennent pas d'informations sur la cause.</span><span class="sxs-lookup"><span data-stu-id="93879-111">For example, while monitoring the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, you may encounter error messages that do not contain cause information.</span></span> <span data-ttu-id="93879-112">En comparant les dates et les heures des événements intervenus entre ces journaux, vous pouvez réduire la liste des causes possibles.</span><span class="sxs-lookup"><span data-stu-id="93879-112">By comparing the dates and times for events between these logs, you can narrow the list of probable causes.</span></span> <span data-ttu-id="93879-113">La visionneuse du fichier journal de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] permet d'intégrer l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les journaux Windows dans une même liste, facilitant ainsi la compréhension d'événements serveur et d'événements [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] liés.</span><span class="sxs-lookup"><span data-stu-id="93879-113">The [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Log File Viewer lets you integrate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent, and the Windows logs into a single list, making it easy to understand related server events and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events.</span></span> <span data-ttu-id="93879-114">Pour plus d'informations, consultez la rubrique relative à la visionneuse du fichier journal dans la documentation en ligne de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="93879-114">For more information, see the topic "Log File Viewer" in SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="93879-115">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="93879-115">In This Section</span></span>  
  
|<span data-ttu-id="93879-116">Rubrique</span><span class="sxs-lookup"><span data-stu-id="93879-116">Topic</span></span>|<span data-ttu-id="93879-117">Description</span><span class="sxs-lookup"><span data-stu-id="93879-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="93879-118">Consultation du journal des erreurs de SQL Server</span><span class="sxs-lookup"><span data-stu-id="93879-118">Viewing the SQL Server Error Log</span></span>](../../../2014/tools/configuration-manager/viewing-the-sql-server-error-log.md)|<span data-ttu-id="93879-119">Contient des informations sur le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et la procédure pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="93879-119">Contains information about the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log and how to view it.</span></span>|  
|[<span data-ttu-id="93879-120">Affichage du journal des applications Windows</span><span class="sxs-lookup"><span data-stu-id="93879-120">Viewing the Windows Application Log</span></span>](viewing-the-windows-application-log.md)|<span data-ttu-id="93879-121">Contient des informations sur le journal des applications Windows et la procédure pour l'afficher.</span><span class="sxs-lookup"><span data-stu-id="93879-121">Contains information about the Windows application log and how to view it.</span></span>|  
  
  
