---
title: Se connecter au serveur (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.connection.login.analysisserver.f1
ms.assetid: 7e277d22-8d4b-422e-8882-7c5dd7a6d915
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: b3530f38534e09ef19e77293880129274dfc211b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694703"
---
# <a name="connect-to-server-analysis-services"></a><span data-ttu-id="ce287-102">Se connecter au serveur (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="ce287-102">Connect to Server (Analysis Services)</span></span>
  <span data-ttu-id="ce287-103">Utilisez cette boîte de dialogue pour afficher ou spécifier des options de connexion à [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce287-103">Use this dialog to view or specify options when connecting to [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="ce287-104">Options</span><span class="sxs-lookup"><span data-stu-id="ce287-104">Options</span></span>  
 <span data-ttu-id="ce287-105">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="ce287-105">**Server type**</span></span>  
 <span data-ttu-id="ce287-106">Lorsque vous inscrivez un serveur depuis l'Explorateur d'objets, sélectionnez le type de serveur pour vous connecter à : [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services.</span><span class="sxs-lookup"><span data-stu-id="ce287-106">When registering a server from Object Explorer, select the type of server to connect to: [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services.</span></span> <span data-ttu-id="ce287-107">Le reste de la boîte de dialogue affiche uniquement les options s'appliquant au type de serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ce287-107">The rest of the dialog shows only the options that apply to the selected server type.</span></span> <span data-ttu-id="ce287-108">Lors de l’inscription d’un serveur de la liste Serveurs inscrits, la zone **Type de serveur** est en lecture seule et indique le type de serveur affiché dans le composant Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="ce287-108">When registering a server from Registered Servers, the **Server type** box is read-only, and matches the type of server displayed in the Registered Servers component.</span></span> <span data-ttu-id="ce287-109">Pour inscrire un autre type de serveur, sélectionnez [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services ou Integration Services dans la barre d'outils Serveurs inscrits avant de commencer l'inscription d'un nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="ce287-109">To register a different type of server, select [!INCLUDE[ssDE](../includes/ssde-md.md)], Analysis Services, Reporting Services, or Integration Services from the Registered Servers toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="ce287-110">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="ce287-110">**Server name**</span></span>  
 <span data-ttu-id="ce287-111">Sélectionnez l'instance de serveur à laquelle se connecter.</span><span class="sxs-lookup"><span data-stu-id="ce287-111">Select the server instance to connect to.</span></span> <span data-ttu-id="ce287-112">La dernière instance de serveur à laquelle une connexion a été établie est affichée par défaut.</span><span class="sxs-lookup"><span data-stu-id="ce287-112">The server instance last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="ce287-113">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="ce287-113">**Authentication**</span></span>  
 <span data-ttu-id="ce287-114">Les modes d'authentification suivants sont pris en charge lors de la connexion à une instance d'Analysis Services : Authentification [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ce287-114">The following authentication modes are supported when connecting to an instance of Analysis Services: [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows Authentication.</span></span>  
  
 <span data-ttu-id="ce287-115">**Mode d'authentification Windows (authentification Windows)**</span><span class="sxs-lookup"><span data-stu-id="ce287-115">**Windows Authentication Mode (Windows Authentication)**</span></span>  
 <span data-ttu-id="ce287-116">Le mode **d’authentification Windows** permet à un utilisateur de se connecter via un compte d’utilisateur Windows.</span><span class="sxs-lookup"><span data-stu-id="ce287-116">**Windows Authentication** mode allows a user to connect through a Windows user account.</span></span>  
  
 <span data-ttu-id="ce287-117">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="ce287-117">**User name**</span></span>  
 <span data-ttu-id="ce287-118">Cette option n'est pas disponible dans cette version.</span><span class="sxs-lookup"><span data-stu-id="ce287-118">This option is not available in this release.</span></span> <span data-ttu-id="ce287-119">Entrez le nom d'utilisateur avec lequel se connecter.</span><span class="sxs-lookup"><span data-stu-id="ce287-119">Enter the user name to connect with.</span></span> <span data-ttu-id="ce287-120">Cette option est disponible uniquement si vous avez choisi de vous connecter via l' **Authentification Windows**.</span><span class="sxs-lookup"><span data-stu-id="ce287-120">This option is only available if you have selected to connect using **Windows Authentication**.</span></span>  
  
 <span data-ttu-id="ce287-121">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="ce287-121">**Password**</span></span>  
 <span data-ttu-id="ce287-122">Cette option n'est pas disponible dans cette version.</span><span class="sxs-lookup"><span data-stu-id="ce287-122">This option is not available in this release.</span></span> <span data-ttu-id="ce287-123">Entrez le mot de passe utilisé avec la connexion.</span><span class="sxs-lookup"><span data-stu-id="ce287-123">Enter the password for the login.</span></span> <span data-ttu-id="ce287-124">Ce mot de passe ne peut être modifié que si vous avez choisi la connexion avec l'authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce287-124">This option is only editable if you have selected to connect using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="ce287-125">**Connexion**</span><span class="sxs-lookup"><span data-stu-id="ce287-125">**Connect**</span></span>  
 <span data-ttu-id="ce287-126">Cliquez sur cette option pour vous connecter au serveur sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ce287-126">Click to connect to the server selected above.</span></span>  
  
 <span data-ttu-id="ce287-127">**Options**</span><span class="sxs-lookup"><span data-stu-id="ce287-127">**Options**</span></span>  
 <span data-ttu-id="ce287-128">Cliquez ici pour afficher des options supplémentaires de connexion au serveur, comme l'inscription d'un serveur et la mémorisation du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ce287-128">Click to display additional server connection options, such as registering a server and remembering the password.</span></span>  
  
  
