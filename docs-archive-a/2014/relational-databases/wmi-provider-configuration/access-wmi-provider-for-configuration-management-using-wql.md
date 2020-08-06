---
title: Accéder au fournisseur WMI pour la gestion de la configuration à l’aide de WQL | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
ms.assetid: 26499530-d93b-452b-bbe4-217ef1d11e68
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b58297c5e292ceb18a6e2e50e2b25b9aa352e2fa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599815"
---
# <a name="access-wmi-provider-for-configuration-management-using-wql"></a><span data-ttu-id="e14d2-102">Accéder au fournisseur WMI pour Gestion de l'ordinateur à l'aide de WQL</span><span class="sxs-lookup"><span data-stu-id="e14d2-102">Access WMI Provider for Configuration Management using WQL</span></span>
  <span data-ttu-id="e14d2-103">Cette section décrit comment exécuter des instructions [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) contre le fournisseur WMI pour Gestion de l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="e14d2-103">This section describes how to execute [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Management Instrumentation Query Language (WQL) statements against the WMI Provider for Computer Management.</span></span>  
  
 <span data-ttu-id="e14d2-104">L'exemple utilise un éditeur WQL, WBEMtest.exe, pour exécuter des requêtes WQL contre le fournisseur WMI afin d'énumérer des services, des protocoles réseaux et des alias [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e14d2-104">The example uses a WQL editor, WBEMtest.exe, to run WQL queries against the WMI Provider to enumerate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, network protocols, and aliases.</span></span>  
  
### <a name="querying-services-using-wbemtest"></a><span data-ttu-id="e14d2-105">Interrogation de services à l'aide de WBEMtest</span><span class="sxs-lookup"><span data-stu-id="e14d2-105">Querying services using WBEMtest</span></span>  
  
1.  <span data-ttu-id="e14d2-106">Dans le menu **Démarrer** , cliquez sur **exécuter**, puis entrez `WBEMtest` .</span><span class="sxs-lookup"><span data-stu-id="e14d2-106">From the **Start** menu, click **Run**, and then enter `WBEMtest`.</span></span>  
  
2.  <span data-ttu-id="e14d2-107">La boîte de dialogue WBEMtest.exe apparaît.</span><span class="sxs-lookup"><span data-stu-id="e14d2-107">The WBEMtest.exe dialog appears.</span></span> <span data-ttu-id="e14d2-108">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="e14d2-108">Click **Connect**.</span></span>  
  
3.  <span data-ttu-id="e14d2-109">Dans le premier champ de texte, tapez l'espace de noms de fournisseur WMI pour Gestion de l'ordinateur : root\Microsoft\SqlServer\ComputerManagement11.</span><span class="sxs-lookup"><span data-stu-id="e14d2-109">In the first text field, type the WMI Provider for Computer Management namespace: root\Microsoft\SqlServer\ComputerManagement11.</span></span> <span data-ttu-id="e14d2-110">Cliquez sur **Connecter**.</span><span class="sxs-lookup"><span data-stu-id="e14d2-110">Click **Connect**.</span></span>  
  
4.  <span data-ttu-id="e14d2-111">Cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="e14d2-111">Click **Query**.</span></span> <span data-ttu-id="e14d2-112">Tapez une requête qui retourne les services en cours d’exécution sur l’ordinateur local : **sélectionnez \* dans SqlService.**</span><span class="sxs-lookup"><span data-stu-id="e14d2-112">Type a query that returns the current services running on the local computer: **SELECT \* FROM SqlService.**</span></span> <span data-ttu-id="e14d2-113">Cliquez sur **Appliquer**.</span><span class="sxs-lookup"><span data-stu-id="e14d2-113">Click **Apply**.</span></span>  
  
5.  <span data-ttu-id="e14d2-114">Affinez davantage la requête en ajoutant `WHERE ServiceName = "MSSQLSERVER"`.</span><span class="sxs-lookup"><span data-stu-id="e14d2-114">Further refine the query by adding `WHERE ServiceName = "MSSQLSERVER"`.</span></span>  
  
  
