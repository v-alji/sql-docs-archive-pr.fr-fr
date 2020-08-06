---
title: Exécuter l’application Data Quality Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.browseforservers.f1
- sql12.dqs.connecttoserver.f1
ms.assetid: 0b2aa202-7ab2-4c9d-b0f1-802588053a1e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45372ce22fd1b18f0ec13f7a7fd76a369b78dfd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709971"
---
# <a name="run-the-data-quality-client-application"></a><span data-ttu-id="6883e-102">Exécuter l'application Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="6883e-102">Run the Data Quality Client Application</span></span>
  <span data-ttu-id="6883e-103">Vous pouvez utiliser [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) en exécutant [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] et en ouvrant une session sur [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6883e-103">You can use [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) by running [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], and logging on to a [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="6883e-104">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="6883e-104">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="6883e-105">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="6883e-105">Prerequisites</span></span>  
 <span data-ttu-id="6883e-106">Vous devez avoir terminé l'installation du [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] en exécutant le fichier DQSInstaller.exe.</span><span class="sxs-lookup"><span data-stu-id="6883e-106">You must have completed the [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] installation by running the DQSInstaller.exe file.</span></span> <span data-ttu-id="6883e-107">Pour plus d’informations, consultez [Exécuter DQSInstaller.exe pour terminer l’installation du serveur DQS](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="6883e-107">For more information, see [Run DQSInstaller.exe to Complete Data Quality Server Installation](install-windows/run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="6883e-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="6883e-108">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="6883e-109">Autorisations</span><span class="sxs-lookup"><span data-stu-id="6883e-109">Permissions</span></span>  
 <span data-ttu-id="6883e-110">Pour se connecter à [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)], un utilisateur doit disposer de l'un des trois rôles DQS suivants sur la base de données DQS_MAIN : dqs_administrator, dqs_kb_editor ou dqs_kb_operator.</span><span class="sxs-lookup"><span data-stu-id="6883e-110">You must have one of the three DQS roles (dqs_adminstrator, dqs_kb_editor, or dqs_kb_operator) granted on the DQS_MAIN database to be able to log on to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)].</span></span>  
  
##  <a name="run-data-quality-client"></a><a name="Run"></a><span data-ttu-id="6883e-111">Exécuter Data Quality Client</span><span class="sxs-lookup"><span data-stu-id="6883e-111">Run Data Quality Client</span></span>  
 <span data-ttu-id="6883e-112">Pour exécuter [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] sur l'ordinateur où vous l'avez installé, opérez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6883e-112">To run [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] on the computer where you have installed it, proceed as follows:</span></span>  
  
1.  <span data-ttu-id="6883e-113">Cliquez sur **Démarrer**, pointez sur **Tous les programmes**, cliquez sur **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, cliquez sur **Data Quality Services**, puis sur **Data Quality Client**.</span><span class="sxs-lookup"><span data-stu-id="6883e-113">Click **Start**, point to **All Programs**, click **[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]**, click **Data Quality Services**, and then click **Data Quality Client**.</span></span>  
  
2.  <span data-ttu-id="6883e-114">Dans la boîte de dialogue **Se connecter au serveur** :</span><span class="sxs-lookup"><span data-stu-id="6883e-114">In the **Connect to Server** dialog box:</span></span>  
  
    1.  <span data-ttu-id="6883e-115">Spécifiez le serveur auquel vous souhaitez connecter l'application [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6883e-115">Specify the server that you want to connect the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] application to.</span></span> <span data-ttu-id="6883e-116">Sélectionnez **(LOCAL)** pour vous connecter à [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] sur l'ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="6883e-116">Select **(LOCAL)** to connect to [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] on the local computer.</span></span> <span data-ttu-id="6883e-117">Vous pouvez également cliquer sur la flèche vers le bas et sélectionner **\<Browse network for more servers>** pour vous connecter à un autre serveur (ou pour vous connecter au serveur local par son nom).</span><span class="sxs-lookup"><span data-stu-id="6883e-117">You can also click the down arrow and select **\<Browse network for more servers>** to connect to a different server (or to connect to the local server by name).</span></span> <span data-ttu-id="6883e-118">La boîte de dialogue **Parcourir les serveurs** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="6883e-118">The **Browse for Servers** dialog box will be displayed.</span></span> <span data-ttu-id="6883e-119">Vous pouvez sélectionner un serveur sous l'onglet **Serveurs locaux** ou sous l'onglet **Serveurs réseau** .</span><span class="sxs-lookup"><span data-stu-id="6883e-119">You can select a server in the **Local Servers** tab or in the **Network Servers** tab.</span></span>  
  
    2.  <span data-ttu-id="6883e-120">Si vous souhaitez chiffrer le transfert de données entre [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] et [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], cliquez sur **Options**, puis cochez **Chiffrer la connexion**.</span><span class="sxs-lookup"><span data-stu-id="6883e-120">If you want to encrypt data transfer between [!INCLUDE[ssDQSServer](../includes/ssdqsserver-md.md)] and [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)], click **Options**, and then select the **Encrypt Connection** check box.</span></span>  
  
3.  <span data-ttu-id="6883e-121">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="6883e-121">Click **Connect**.</span></span>  
  
 <span data-ttu-id="6883e-122">L'écran d'accueil [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] apparaît.</span><span class="sxs-lookup"><span data-stu-id="6883e-122">The [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen appears.</span></span> <span data-ttu-id="6883e-123">Pour plus d’informations, consultez [Écran d’accueil de Data Quality Client](../../2014/data-quality-services/data-quality-client-home-screen.md).</span><span class="sxs-lookup"><span data-stu-id="6883e-123">For more information, see [Data Quality Client Home Screen](../../2014/data-quality-services/data-quality-client-home-screen.md).</span></span>  
  
  
