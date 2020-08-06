---
title: Se connecter au serveur (page Propriétés de connexion) — Analysis Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttoas.connectionproperties.f1
ms.assetid: 26cf53e3-3bcb-4697-8a88-53e93bc68b56
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 04706671ea8b0a50f2bf72cd7b73db88dce34d89
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694699"
---
# <a name="connect-to-server-connection-properties-page-analysis-services"></a><span data-ttu-id="7a54c-102">Se connecter au serveur (page Propriétés de connexion) - Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7a54c-102">Connect to Server (Connection Properties Page) Analysis Services</span></span>
  <span data-ttu-id="7a54c-103">Utilisez cet onglet pour afficher ou spécifier des options lors de la connexion [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ou [!INCLUDE[ssAS](../includes/ssas-md.md)] de l’inscription à des **serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="7a54c-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] or registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="7a54c-104">**Se connecter** et **Options** s’affichent uniquement dans cette boîte de dialogue lors d’une connexion.</span><span class="sxs-lookup"><span data-stu-id="7a54c-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="7a54c-105">**Tester** et **Enregistrer** s’affichent uniquement dans cette boîte de dialogue lors de l’inscription du [!INCLUDE[ssAS](../includes/ssas-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7a54c-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssAS](../includes/ssas-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="7a54c-106">Options</span><span class="sxs-lookup"><span data-stu-id="7a54c-106">Options</span></span>  
 <span data-ttu-id="7a54c-107">**Connecter à la base de données**</span><span class="sxs-lookup"><span data-stu-id="7a54c-107">**Connect to database**</span></span>  
 <span data-ttu-id="7a54c-108">Dans la liste, sélectionnez une base de données à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="7a54c-108">Select a database to connect to from the list.</span></span> <span data-ttu-id="7a54c-109">Si vous sélectionnez **\<default>** , vous serez connecté à la base de données par défaut pour le serveur.</span><span class="sxs-lookup"><span data-stu-id="7a54c-109">If you select **\<default>**, you will be connected to the default database for the server.</span></span> <span data-ttu-id="7a54c-110">Si vous sélectionnez **\<Browse server>** , vous pouvez parcourir le serveur à la recherche de la base de données à laquelle vous souhaitez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="7a54c-110">If you select **\<Browse server>**, you can browse the server for the database you would like to connect to.</span></span>  
  
 <span data-ttu-id="7a54c-111">**Délai de connexion**</span><span class="sxs-lookup"><span data-stu-id="7a54c-111">**Connection timeout**</span></span>  
 <span data-ttu-id="7a54c-112">Entrez le nombre de secondes d’attente de l’établissement d’une connexion avant expiration du délai d’attente. La valeur par défaut est 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="7a54c-112">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="7a54c-113">**Délai d’exécution**</span><span class="sxs-lookup"><span data-stu-id="7a54c-113">**Execution timeout**</span></span>  
 <span data-ttu-id="7a54c-114">Entrez le nombre de secondes que peut prendre l'exécution d'une tâche sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="7a54c-114">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="7a54c-115">La valeur par défaut est égale à zéro seconde, ce qui définit un délai d'attente illimité.</span><span class="sxs-lookup"><span data-stu-id="7a54c-115">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="7a54c-116">**Chiffrer la connexion**</span><span class="sxs-lookup"><span data-stu-id="7a54c-116">**Encrypt connection**</span></span>  
 <span data-ttu-id="7a54c-117">Force le chiffrement de la connexion.</span><span class="sxs-lookup"><span data-stu-id="7a54c-117">Forces encryption of the connection.</span></span>  
  
 <span data-ttu-id="7a54c-118">**Réinitialiser tout**</span><span class="sxs-lookup"><span data-stu-id="7a54c-118">**Reset All**</span></span>  
 <span data-ttu-id="7a54c-119">Remplace toutes les valeurs de propriété de connexion entrées manuellement par les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="7a54c-119">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="7a54c-120">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="7a54c-120">**Connect**</span></span>  
 <span data-ttu-id="7a54c-121">Tente d'établir une connexion à l'aide des valeurs indiquées.</span><span class="sxs-lookup"><span data-stu-id="7a54c-121">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="7a54c-122">**Options**</span><span class="sxs-lookup"><span data-stu-id="7a54c-122">**Options**</span></span>  
 <span data-ttu-id="7a54c-123">Cliquez sur cette option pour modifier l'apparence de la boîte de dialogue en masquant les options de connexion serveur supplémentaires, comme la mémorisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7a54c-123">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="7a54c-124">**Test**</span><span class="sxs-lookup"><span data-stu-id="7a54c-124">**Test**</span></span>  
 <span data-ttu-id="7a54c-125">Quand vous inscrivez [!INCLUDE[ssAS](../includes/ssas-md.md)] dans **Serveurs inscrits**, cliquez ici pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="7a54c-125">When registering [!INCLUDE[ssAS](../includes/ssas-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="7a54c-126">**Save**</span><span class="sxs-lookup"><span data-stu-id="7a54c-126">**Save**</span></span>  
 <span data-ttu-id="7a54c-127">Enregistre les paramètres dans **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="7a54c-127">Saves the settings in **Registered Servers**.</span></span>  
  
  
