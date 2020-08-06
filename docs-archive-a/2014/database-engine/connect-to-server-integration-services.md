---
title: Se connecter au serveur (Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.dtsserver.f1
ms.assetid: 5be897bd-f36c-4c6a-a91a-13d0d016f8b6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 8821018c45fdd77c4b3b896afc47b8f5b425af88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707823"
---
# <a name="connect-to-server-integration-services"></a><span data-ttu-id="f05d3-102">Se connecter au serveur (Integration Services)</span><span class="sxs-lookup"><span data-stu-id="f05d3-102">Connect to Server (Integration Services)</span></span>
  <span data-ttu-id="f05d3-103">Utilisez cette boîte de dialogue pour afficher ou spécifier des options de connexion à [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05d3-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="f05d3-104">Options</span><span class="sxs-lookup"><span data-stu-id="f05d3-104">Options</span></span>  
 <span data-ttu-id="f05d3-105">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="f05d3-105">**Server type**</span></span>  
 <span data-ttu-id="f05d3-106">Lorsque vous inscrivez un serveur depuis l'Explorateur d'objets, sélectionnez le type de serveur pour vous connecter à : [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services.</span><span class="sxs-lookup"><span data-stu-id="f05d3-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="f05d3-107">Le reste de la boîte de dialogue affiche uniquement les options s'appliquant au type de serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f05d3-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="f05d3-108">Lorsque vous inscrivez un serveur à partir de Serveurs inscrits, la zone Type de serveur est en lecture seule et correspond au type de serveur affiché dans le composant Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="f05d3-108">When registering a server from Registered Servers, the Server type box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="f05d3-109">Pour inscrire un autre type de serveur, sélectionnez [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services dans la barre d'outils Serveurs inscrits avant de commencer l'inscription d'un nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="f05d3-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="f05d3-110">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="f05d3-110">**Server name**</span></span>  
 <span data-ttu-id="f05d3-111">Sélectionnez le serveur auquel vous connecter.</span><span class="sxs-lookup"><span data-stu-id="f05d3-111">Select the server to connect to.</span></span> <span data-ttu-id="f05d3-112">La dernière instance de serveur à laquelle une connexion a été établie est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="f05d3-112">The server instance last connected to is displayed by default.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f05d3-113">N’utilisez pas *\<servername>* \\ *\<instancename>* , car [!INCLUDE[ssIS](../includes/ssis-md.md)] ne prend pas en charge plusieurs instances sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="f05d3-113">Do not use *\<servername>*\\*\<instancename>*, because [!INCLUDE[ssIS](../includes/ssis-md.md)] does not support multiple instances on a computer.</span></span>  
  
 <span data-ttu-id="f05d3-114">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="f05d3-114">**Authentication**</span></span>  
 <span data-ttu-id="f05d3-115">Seule l'authentification [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05d3-115">Only [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span> <span data-ttu-id="f05d3-116">Le mode d’authentification Windows permet à l’utilisateur de se connecter au moyen d’un compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="f05d3-116">Windows Authentication mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="f05d3-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="f05d3-117">**User name**</span></span>  
 <span data-ttu-id="f05d3-118">Cette option n'est pas disponible car seule l'authentification Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05d3-118">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="f05d3-119">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="f05d3-119">**Password**</span></span>  
 <span data-ttu-id="f05d3-120">Cette option n'est pas disponible car seule l'authentification Windows est disponible pour [!INCLUDE[ssIS](../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f05d3-120">This option is not available because only Windows Authentication is available for [!INCLUDE[ssIS](../includes/ssis-md.md)].</span></span>  
  
 <span data-ttu-id="f05d3-121">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="f05d3-121">**Connect**</span></span>  
 <span data-ttu-id="f05d3-122">Cliquez sur cette option pour vous connecter au serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="f05d3-122">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="f05d3-123">**Options**</span><span class="sxs-lookup"><span data-stu-id="f05d3-123">**Options**</span></span>  
 <span data-ttu-id="f05d3-124">Cliquez ici pour afficher des options supplémentaires de connexion au serveur, comme l'inscription d'un serveur et la mémorisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="f05d3-124">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
