---
title: Se connecter au serveur (page Connexion) — Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connecttodtsserver.login.f1
- sql12.swb.connecttodts.login.f1
ms.assetid: 402c2de4-f4ea-40b0-909f-3ddf3bd59950
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 285518f4a1f3d9180d2c3c07a41bf75a00ea3593
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707819"
---
# <a name="connect-to-server-login-page-integration-services"></a><span data-ttu-id="b52d6-102">Se connecter au serveur (page Connexion) Integration Services</span><span class="sxs-lookup"><span data-stu-id="b52d6-102">Connect to Server (Login Page) Integration Services</span></span>
  <span data-ttu-id="b52d6-103">Utilisez cet onglet pour afficher ou spécifier les options suivantes lors de la connexion à [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b52d6-103">Use this tab to view or specify the following options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b52d6-104">Options</span><span class="sxs-lookup"><span data-stu-id="b52d6-104">Options</span></span>  
 <span data-ttu-id="b52d6-105">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="b52d6-105">**Server type**</span></span>  
 <span data-ttu-id="b52d6-106">Lorsque vous inscrivez un serveur depuis l'Explorateur d'objets, sélectionnez le type de serveur pour vous connecter à : [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services.</span><span class="sxs-lookup"><span data-stu-id="b52d6-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="b52d6-107">Le reste de la boîte de dialogue affiche uniquement les options s'appliquant au type de serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b52d6-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="b52d6-108">Lors de l’inscription d’un serveur de la liste Serveurs inscrits, la zone **Type de serveur** est en lecture seule et indique le type de serveur affiché dans le composant Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="b52d6-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="b52d6-109">Pour inscrire un autre type de serveur, sélectionnez [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services dans la barre d'outils Serveurs inscrits avant de commencer l'inscription d'un nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="b52d6-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="b52d6-110">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="b52d6-110">**Server name**</span></span>  
 <span data-ttu-id="b52d6-111">Sélectionnez le serveur auquel vous connecter.</span><span class="sxs-lookup"><span data-stu-id="b52d6-111">Select the server to connect to.</span></span> <span data-ttu-id="b52d6-112">La dernière instance de serveur à laquelle une connexion a été établie est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="b52d6-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b52d6-113">N’utilisez pas *\<servername>* \\ *\<instancename>* , car [!INCLUDE[ssIS](../includes/ssis-md.md)] ne prend pas en charge plusieurs instances sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b52d6-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="b52d6-114">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="b52d6-114">**Authentication**</span></span>  
 <span data-ttu-id="b52d6-115">Seule l'authentification [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52d6-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="b52d6-116">Le mode d’authentification Windows permet à l’utilisateur de se connecter au moyen d’un compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="b52d6-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="b52d6-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="b52d6-117">**User name**</span></span>  
 <span data-ttu-id="b52d6-118">Cette option n'est pas disponible car seule l'authentification Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52d6-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="b52d6-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b52d6-119">**Password**</span></span>  
 <span data-ttu-id="b52d6-120">Cette option n'est pas disponible car seule l'authentification Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52d6-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="b52d6-121">**Mémoriser le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="b52d6-121">**Remember password**</span></span>  
 <span data-ttu-id="b52d6-122">Cette option n'est pas disponible car seule l'authentification Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b52d6-122">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="b52d6-123">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="b52d6-123">**Connect**</span></span>  
 <span data-ttu-id="b52d6-124">Établit la connexion au serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b52d6-124">Connect to the server selected above.</span></span>  
  
 <span data-ttu-id="b52d6-125">**Options**</span><span class="sxs-lookup"><span data-stu-id="b52d6-125">**Options**</span></span>  
 <span data-ttu-id="b52d6-126">Cliquez sur cette option pour modifier l'apparence de la boîte de dialogue en masquant les options de connexion serveur supplémentaires, comme la mémorisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="b52d6-126">Click to change the dialog and hide the additional server connection options, such as remembering the password.</span></span>  
  
  
