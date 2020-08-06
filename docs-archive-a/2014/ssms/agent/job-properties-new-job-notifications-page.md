---
title: 'Propriétés du travail : nouveau travail (page notifications) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.job.notifications.f1
ms.assetid: ed393cbd-4496-4399-a177-e5baa92fb689
author: stevestein
ms.author: sstein
ms.openlocfilehash: 30eca88943b48bd81bd38e236711d19ee7ec4503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601250"
---
# <a name="job-properties-new-job-notifications-page"></a><span data-ttu-id="d8c48-102">Propriétés du travail : Nouveau travail (page Notifications)</span><span class="sxs-lookup"><span data-stu-id="d8c48-102">Job Properties: New Job (Notifications Page)</span></span>
  <span data-ttu-id="d8c48-103">Utilisez cette page pour définir des actions [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que l’agent doit effectuer une fois le travail terminé.</span><span class="sxs-lookup"><span data-stu-id="d8c48-103">Use this page to set actions for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent to perform when the job completes.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d8c48-104">Options</span><span class="sxs-lookup"><span data-stu-id="d8c48-104">Options</span></span>  
 <span data-ttu-id="d8c48-105">**Courriel**</span><span class="sxs-lookup"><span data-stu-id="d8c48-105">**E-mail**</span></span>  
 <span data-ttu-id="d8c48-106">Sélectionnez cette option pour envoyer un courrier électronique lorsque le travail se termine.</span><span class="sxs-lookup"><span data-stu-id="d8c48-106">Select this option to send e-mail when the job completes.</span></span> <span data-ttu-id="d8c48-107">Choisissez ensuite l’opérateur qu’il faut avertir et la condition qui va déclencher la notification : **Lors de la réussite du travail**, **Lors de l’échec du travail**ou **Lorsque le travail est terminé**.</span><span class="sxs-lookup"><span data-stu-id="d8c48-107">After selecting this option, choose the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="d8c48-108">**Page**</span><span class="sxs-lookup"><span data-stu-id="d8c48-108">**Page**</span></span>  
 <span data-ttu-id="d8c48-109">Sélectionnez cette option pour envoyer un courrier électronique à un opérateur via la radiomessagerie lorsque le travail se termine.</span><span class="sxs-lookup"><span data-stu-id="d8c48-109">Select this option to send e-mail to an operator's pager when the job completes.</span></span> <span data-ttu-id="d8c48-110">Spécifiez ensuite l’opérateur qu’il faut avertir et la condition qui va déclencher la notification : **Lors de la réussite du travail**, **Lors de l’échec du travail**ou **Lorsque le travail est terminé**.</span><span class="sxs-lookup"><span data-stu-id="d8c48-110">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="d8c48-111">**Envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="d8c48-111">**Net send**</span></span>  
 <span data-ttu-id="d8c48-112">Sélectionnez cette option pour avertir un opérateur de la fin du travail via l'envoi réseau.</span><span class="sxs-lookup"><span data-stu-id="d8c48-112">Select this option to use net send to notify an operator when the job completes.</span></span> <span data-ttu-id="d8c48-113">Spécifiez ensuite l’opérateur qu’il faut avertir et la condition qui va déclencher la notification : **Lors de la réussite du travail**, **Lors de l’échec du travail**ou **Lorsque le travail est terminé**.</span><span class="sxs-lookup"><span data-stu-id="d8c48-113">After selecting this option, specify the operator to notify and the condition that will trigger the notification: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="d8c48-114">**Écrire dans le journal des événements des applications Windows**</span><span class="sxs-lookup"><span data-stu-id="d8c48-114">**Write to the Windows Application event log**</span></span>  
 <span data-ttu-id="d8c48-115">Sélectionnez cette option pour écrire une entrée dans le journal des événements des applications lorsque le travail est terminé.</span><span class="sxs-lookup"><span data-stu-id="d8c48-115">Select this option to write an entry in the application event log when the job completes.</span></span> <span data-ttu-id="d8c48-116">Choisissez ensuite la condition qui va déclencher l’écriture de l’entrée : **Lors de la réussite du travail**, **Lors de l’échec du travail**ou **Lorsque le travail est terminé**.</span><span class="sxs-lookup"><span data-stu-id="d8c48-116">After selecting this option, specify the condition that will cause the entry to be written: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
 <span data-ttu-id="d8c48-117">**Supprimer le travail automatiquement**</span><span class="sxs-lookup"><span data-stu-id="d8c48-117">**Automatically delete job**</span></span>  
 <span data-ttu-id="d8c48-118">Sélectionnez cette option pour supprimer le travail une fois celui-ci terminé.</span><span class="sxs-lookup"><span data-stu-id="d8c48-118">Select this option to delete the job when the job completes.</span></span> <span data-ttu-id="d8c48-119">Choisissez ensuite la condition qui va déclencher la suppression du travail : **Lors de la réussite du travail**, **Lors de l’échec du travail**ou **Lorsque le travail est terminé**.</span><span class="sxs-lookup"><span data-stu-id="d8c48-119">After selecting this option, specify the condition that will trigger deletion of the job: **When the job succeeds**; **When the job fails**; or **When the job completes**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c48-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8c48-120">See Also</span></span>  
 <span data-ttu-id="d8c48-121">[Implémenter des travaux](implement-jobs.md) </span><span class="sxs-lookup"><span data-stu-id="d8c48-121">[Implement Jobs](implement-jobs.md) </span></span>  
 [<span data-ttu-id="d8c48-122">Configurer la messagerie SQL Server Agent en vue d’utiliser la messagerie de base de données</span><span class="sxs-lookup"><span data-stu-id="d8c48-122">Configure SQL Server Agent Mail to Use Database Mail</span></span>](../../relational-databases/database-mail/configure-sql-server-agent-mail-to-use-database-mail.md)  
  
  
