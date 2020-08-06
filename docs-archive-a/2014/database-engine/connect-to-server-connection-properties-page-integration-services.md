---
title: Se connecter au serveur (page Propriétés de connexion) Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodts.connectionproperties.f1
- sql12.ssiseditserverregistration.connectionproperties.f1
ms.assetid: c2513dab-8415-4e0c-9475-6d4ab97fea7c
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 05f3d370a3f3a299bb90df53538b3fa3e90e28c4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707827"
---
# <a name="connect-to-server-connection-properties-page-integration-services"></a><span data-ttu-id="ae8ab-102">Se connecter au serveur (page Propriétés de connexion) Integration Services</span><span class="sxs-lookup"><span data-stu-id="ae8ab-102">Connect to Server (Connection Properties Page) Integration Services</span></span>
  <span data-ttu-id="ae8ab-103">Utilisez cet onglet pour afficher ou spécifier des options lors de la connexion [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ou [!INCLUDE[ssIS](../includes/ssis-md.md)] de l’inscription à des **serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-103">Use this tab to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] or registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**.</span></span> <span data-ttu-id="ae8ab-104">**Se connecter** et **Options** s’affichent uniquement dans cette boîte de dialogue lors d’une connexion.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-104">**Connect** and **Options** only appear in this dialog box when connecting.</span></span> <span data-ttu-id="ae8ab-105">**Tester** et **Enregistrer** s’affichent uniquement dans cette boîte de dialogue lors de l’inscription du [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae8ab-105">**Test** and **Save** only appear in this dialog box when registering [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae8ab-106">Options</span><span class="sxs-lookup"><span data-stu-id="ae8ab-106">Options</span></span>  
 <span data-ttu-id="ae8ab-107">**Numéro de port**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-107">**Port number**</span></span>  
 <span data-ttu-id="ae8ab-108">Entrez le numéro de port utilisé par [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae8ab-108">Enter the port number used by [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="ae8ab-109">**Délai d’expiration de la connexion**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-109">**Connection time-out**</span></span>  
 <span data-ttu-id="ae8ab-110">Entrez le nombre de secondes d’attente de l’établissement d’une connexion avant expiration du délai d’attente. La valeur par défaut est 15 secondes.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-110">Enter the number of seconds to wait for a connection to be established before timing out. The default value is 15 seconds.</span></span>  
  
 <span data-ttu-id="ae8ab-111">**Délai d’exécution**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-111">**Execution time-out**</span></span>  
 <span data-ttu-id="ae8ab-112">Entrez le nombre de secondes que peut prendre l'exécution d'une tâche sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-112">Enter the amount of time in seconds to wait before execution of a task is completed on the server.</span></span> <span data-ttu-id="ae8ab-113">La valeur par défaut est égale à zéro seconde, ce qui définit un délai d'attente illimité.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-113">The default value is zero seconds, which indicates there is no time-out.</span></span>  
  
 <span data-ttu-id="ae8ab-114">**Réinitialiser tout**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-114">**Reset All**</span></span>  
 <span data-ttu-id="ae8ab-115">Remplace toutes les valeurs de propriété de connexion entrées manuellement par les valeurs par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-115">Replace all manually entered connection property values with the default values.</span></span>  
  
 <span data-ttu-id="ae8ab-116">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-116">**Connect**</span></span>  
 <span data-ttu-id="ae8ab-117">Tente d'établir une connexion à l'aide des valeurs indiquées.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-117">Attempt a connection using the listed values.</span></span>  
  
 <span data-ttu-id="ae8ab-118">**Options**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-118">**Options**</span></span>  
 <span data-ttu-id="ae8ab-119">Cliquez sur cette option pour modifier l'apparence de la boîte de dialogue en masquant les options de connexion serveur supplémentaires, comme la mémorisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-119">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
 <span data-ttu-id="ae8ab-120">**Test**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-120">**Test**</span></span>  
 <span data-ttu-id="ae8ab-121">Quand vous inscrivez [!INCLUDE[ssIS](../includes/ssis-md.md)] dans **Serveurs inscrits**, cliquez ici pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-121">When registering [!INCLUDE[ssIS](../includes/ssis-md.md)] in **Registered Servers**, click to test the connection.</span></span>  
  
 <span data-ttu-id="ae8ab-122">**Save**</span><span class="sxs-lookup"><span data-stu-id="ae8ab-122">**Save**</span></span>  
 <span data-ttu-id="ae8ab-123">Enregistre les paramètres dans **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="ae8ab-123">Saves the settings in **Registered Servers**.</span></span>  
  
  
