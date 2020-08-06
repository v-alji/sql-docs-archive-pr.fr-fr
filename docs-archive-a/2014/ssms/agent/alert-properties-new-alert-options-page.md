---
title: 'Propriétés de l’alerte : nouvelle alerte (page Options) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.ag.alert.options.f1
ms.assetid: 6e4f41aa-832d-46ba-b6b5-cf1d3b15d33f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 4a1507372aa1516c2a88b8682faa77a7d57e58f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705907"
---
# <a name="alert-properties-new-alert-options-page"></a><span data-ttu-id="c06fa-102">Propriétés de l’alerte : Nouvelle alerte (page Options)</span><span class="sxs-lookup"><span data-stu-id="c06fa-102">Alert Properties: New Alert (Options Page)</span></span>
  <span data-ttu-id="c06fa-103">Utilisez cette page pour afficher et modifier les options des [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alertes de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c06fa-103">Use this page to view and modify options for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent alerts.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c06fa-104">Options</span><span class="sxs-lookup"><span data-stu-id="c06fa-104">Options</span></span>  
 <span data-ttu-id="c06fa-105">**Courriel**</span><span class="sxs-lookup"><span data-stu-id="c06fa-105">**E-mail**</span></span>  
 <span data-ttu-id="c06fa-106">Permet d'inclure le texte d'erreur de l'événement, le cas échéant, dans les notifications par courrier électronique.</span><span class="sxs-lookup"><span data-stu-id="c06fa-106">Include error text from the event, if any, in e-mail notifications.</span></span>  
  
 <span data-ttu-id="c06fa-107">**Radiomessagerie**</span><span class="sxs-lookup"><span data-stu-id="c06fa-107">**Pager**</span></span>  
 <span data-ttu-id="c06fa-108">Permet d'inclure le texte d'erreur de l'événement, le cas échéant, dans les notifications de radiomessagerie.</span><span class="sxs-lookup"><span data-stu-id="c06fa-108">Include error text from the event, if any, in pager notifications.</span></span>  
  
 <span data-ttu-id="c06fa-109">**Envoi réseau**</span><span class="sxs-lookup"><span data-stu-id="c06fa-109">**Net send**</span></span>  
 <span data-ttu-id="c06fa-110">Permet d'inclure le texte d'erreur de l'événement, le cas échéant, dans les notifications d'envoi réseau.</span><span class="sxs-lookup"><span data-stu-id="c06fa-110">Include error text from the event, if any, in net send notifications.</span></span>  
  
 <span data-ttu-id="c06fa-111">**Message de notification supplémentaire à envoyer**</span><span class="sxs-lookup"><span data-stu-id="c06fa-111">**Additional notification message to send**</span></span>  
 <span data-ttu-id="c06fa-112">Tapez tout texte supplémentaire à inclure dans les messages de notification.</span><span class="sxs-lookup"><span data-stu-id="c06fa-112">Type any additional text to include in notification messages.</span></span>  
  
 <span data-ttu-id="c06fa-113">**Délai entre les réponses**</span><span class="sxs-lookup"><span data-stu-id="c06fa-113">**Delay between responses**</span></span>  
 <span data-ttu-id="c06fa-114">Spécifiez un délai pour les occurrences répétées de l'événement.</span><span class="sxs-lookup"><span data-stu-id="c06fa-114">Specify a delay for repeated occurrences of the event.</span></span> <span data-ttu-id="c06fa-115">Certains événements peuvent se produire fréquemment au court d'une courte période de temps.</span><span class="sxs-lookup"><span data-stu-id="c06fa-115">Some events may occur frequently during a short period of time.</span></span> <span data-ttu-id="c06fa-116">Dans ce cas, vous voudrez peut-être savoir que l'événement s'est produit sans vouloir de réponse pour chaque événement.</span><span class="sxs-lookup"><span data-stu-id="c06fa-116">In this case, you may want to know that the event has occurred, but you may not want a response for every event.</span></span> <span data-ttu-id="c06fa-117">Utilisez cette option pour spécifier un délai d’attente. Avec un délai, une fois que l’alerte a répondu à un événement, l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] agent attend le délai spécifié avant de répondre de nouveau, que l’événement se produise ou non pendant ce délai.</span><span class="sxs-lookup"><span data-stu-id="c06fa-117">Use this option to specify a time-out. With a delay, after the alert responds to an event, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent waits for the delay specified before responding again, regardless of whether the event occurs during the delay.</span></span>  
  
 <span data-ttu-id="c06fa-118">**Maximum**</span><span class="sxs-lookup"><span data-stu-id="c06fa-118">**Minutes**</span></span>  
 <span data-ttu-id="c06fa-119">Spécifiez un délai en minutes.</span><span class="sxs-lookup"><span data-stu-id="c06fa-119">Specify a delay in minutes.</span></span> <span data-ttu-id="c06fa-120">Pour répondre chaque fois qu'un événement se produit, spécifiez 0 minutes et 0 secondes.</span><span class="sxs-lookup"><span data-stu-id="c06fa-120">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
 <span data-ttu-id="c06fa-121">**Durée**</span><span class="sxs-lookup"><span data-stu-id="c06fa-121">**Seconds**</span></span>  
 <span data-ttu-id="c06fa-122">Spécifiez un délai en secondes.</span><span class="sxs-lookup"><span data-stu-id="c06fa-122">Specify a delay in seconds.</span></span> <span data-ttu-id="c06fa-123">Pour répondre chaque fois qu'un événement se produit, spécifiez 0 minutes et 0 secondes.</span><span class="sxs-lookup"><span data-stu-id="c06fa-123">To respond every time the event occurs, specify 0 minutes and 0 seconds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06fa-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c06fa-124">See Also</span></span>  
 [<span data-ttu-id="c06fa-125">Alertes</span><span class="sxs-lookup"><span data-stu-id="c06fa-125">Alerts</span></span>](alerts.md)  
  
  
