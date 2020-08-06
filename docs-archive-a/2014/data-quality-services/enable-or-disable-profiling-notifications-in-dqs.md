---
title: Activer ou désactiver les notifications de profilage dans DQS | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
helpviewer_keywords:
- enable notifications
- notifications,enable
- notifications,disable
ms.assetid: e439bb29-60cc-4afd-a79a-f629b8d843c1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b3b5e8cec1cac3eb1ce4357480c0f994a33d4c40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700265"
---
# <a name="enable-or-disable-profiling-notifications-in-dqs"></a><span data-ttu-id="a5c81-102">Activer ou désactiver les notifications de profilage dans DQS</span><span class="sxs-lookup"><span data-stu-id="a5c81-102">Enable or Disable Profiling Notifications in DQS</span></span>
  <span data-ttu-id="a5c81-103">Cette rubrique explique comment activer ou désactiver les notifications de profilage dans [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="a5c81-103">This topic describes how to enable or disable profiling notifications in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="a5c81-104">Par défaut, les notifications de profilage sont activées dans DQS.</span><span class="sxs-lookup"><span data-stu-id="a5c81-104">By default, profiling notifications are enabled in DQS.</span></span> <span data-ttu-id="a5c81-105">Les notifications de profilage vous indiquent des faits importants sur la source de données et l'efficacité de l'activité actuelle effectuée sur les données.</span><span class="sxs-lookup"><span data-stu-id="a5c81-105">Profiling notifications tell you important facts about the data source and the effectiveness of the current activity performed on the data.</span></span> <span data-ttu-id="a5c81-106">Pour plus d’informations, consultez [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="a5c81-106">For more information, see [Data Profiling and Notifications in DQS](../../2014/data-quality-services/data-profiling-and-notifications-in-dqs.md).</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="a5c81-107">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a5c81-107">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="a5c81-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="a5c81-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="a5c81-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="a5c81-109">Permissions</span></span>  
 <span data-ttu-id="a5c81-110">Vous devez disposer du rôle dqs_administrator sur la base de données DQS_MAIN pour activer les notifications.</span><span class="sxs-lookup"><span data-stu-id="a5c81-110">You must have the dqs_administrator role on the DQS_MAIN database to enable notifications.</span></span>  
  
##  <a name="enable-or-disable-profiling-notifications"></a><a name="Enable"></a><span data-ttu-id="a5c81-111">Activer ou désactiver les notifications de profilage</span><span class="sxs-lookup"><span data-stu-id="a5c81-111">Enable or Disable Profiling Notifications</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="a5c81-112">[Exécutez l’Application Data Quality client](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span><span class="sxs-lookup"><span data-stu-id="a5c81-112">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="a5c81-113">Dans l'écran d'accueil de [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] , cliquez sur **Configuration**.</span><span class="sxs-lookup"><span data-stu-id="a5c81-113">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Configuration**.</span></span>  
  
3.  <span data-ttu-id="a5c81-114">Ensuite, cliquez sur l'onglet **Paramètres généraux** .</span><span class="sxs-lookup"><span data-stu-id="a5c81-114">Next, click the **General Settings** tab.</span></span>  
  
4.  <span data-ttu-id="a5c81-115">Désactivez ou activez la case à cocher **Activer les notifications** pour activer ou désactiver les notifications de profilage pour diverses activités dans DQS.</span><span class="sxs-lookup"><span data-stu-id="a5c81-115">Clear or select the **Enable Notifications** check box to disable or enable profiling notifications for various activities in DQS.</span></span>  
  
5.  <span data-ttu-id="a5c81-116">Cliquez sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="a5c81-116">Click **Close**.</span></span>  
  
  
