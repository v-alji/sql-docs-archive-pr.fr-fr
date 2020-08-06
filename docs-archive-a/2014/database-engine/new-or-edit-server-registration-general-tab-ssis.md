---
title: Nouvelle inscription de serveur ou modifier l’inscription du serveur (onglet général) (SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.general.dts.f1
ms.assetid: b586b736-344b-4e42-83ee-96f66ad433a5
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 4968c3f98b8bab5b2e641e6fb1e30a6d682f9b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613612"
---
# <a name="new-or-edit-server-registration-general-tab-ssis"></a><span data-ttu-id="68ed6-102">Nouvelle inscription de serveur ou Modifier les propriétés d'inscription du serveur (onglet Général) (SSIS)</span><span class="sxs-lookup"><span data-stu-id="68ed6-102">New or Edit Server Registration (General Tab) (SSIS)</span></span>
  <span data-ttu-id="68ed6-103">Cet onglet vous permet de spécifier des options lors de l'inscription de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68ed6-103">Use this tab to specify options when registering [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="68ed6-104">Pour accéder à cette page, dans Serveurs inscrits, cliquez sur **Integration Services** dans la barre d’outils **Serveurs inscrits** , cliquez avec le bouton droit sur un groupe de serveurs inscrits quelconque, pointez sur **Nouveau**, puis cliquez sur **Inscription du serveur**.</span><span class="sxs-lookup"><span data-stu-id="68ed6-104">To access this page, in Registered Servers, click **Integration Services** on the **Registered Servers** toolbar, right-click any registered servers group, point to **New**, and then click **Server Registration**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="68ed6-105">Options</span><span class="sxs-lookup"><span data-stu-id="68ed6-105">Options</span></span>  
 <span data-ttu-id="68ed6-106">**Type de serveur**</span><span class="sxs-lookup"><span data-stu-id="68ed6-106">**Server type**</span></span>  
 <span data-ttu-id="68ed6-107">Quand un serveur est inscrit dans Serveurs inscrits, la zone **Type de serveur** est en lecture seule et concorde avec le type de serveur affiché dans Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="68ed6-107">When a server is registered in Registered Servers, the **Server type** box is read-only, and it matches the type of server displayed in Registered Servers.</span></span> <span data-ttu-id="68ed6-108">Pour inscrire un autre type de serveur, cliquez sur **Moteur de base de données**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition** ou **Integration Services** dans la barre d'outils **Serveurs inscrits** avant de commencer à inscrire un nouveau serveur.</span><span class="sxs-lookup"><span data-stu-id="68ed6-108">To register a different type of server, click **Database Engine**, **Analysis Server**, **Reporting Services**, **SQL Server Compact** **Edition**, or **Integration Services** on the **Registered Servers** toolbar before starting to register a new server.</span></span>  
  
 <span data-ttu-id="68ed6-109">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="68ed6-109">**Server name**</span></span>  
 <span data-ttu-id="68ed6-110">Sélectionnez le serveur auquel vous souhaitez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="68ed6-110">Select the server to which to connect.</span></span> <span data-ttu-id="68ed6-111">Le dernier serveur avec lequel une connexion a été établie apparaît par défaut.</span><span class="sxs-lookup"><span data-stu-id="68ed6-111">The server last connected to is displayed by default.</span></span>  
  
 <span data-ttu-id="68ed6-112">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="68ed6-112">**Authentication**</span></span>  
 <span data-ttu-id="68ed6-113">Le mode d'authentification Windows permet à l'utilisateur de se connecter au moyen d'un compte d'utilisateur [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="68ed6-113">Windows Authentication mode allows a user to connect through a [!INCLUDE[msCoName](../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="68ed6-114">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="68ed6-114">**User name**</span></span>  
 <span data-ttu-id="68ed6-115">Cette option n'est pas disponible dans cette version.</span><span class="sxs-lookup"><span data-stu-id="68ed6-115">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="68ed6-116">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="68ed6-116">**Password**</span></span>  
 <span data-ttu-id="68ed6-117">Cette option n'est pas disponible dans cette version.</span><span class="sxs-lookup"><span data-stu-id="68ed6-117">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="68ed6-118">**Mémoriser le mot de passe**</span><span class="sxs-lookup"><span data-stu-id="68ed6-118">**Remember password**</span></span>  
 <span data-ttu-id="68ed6-119">Cette option n'est pas disponible dans cette version.</span><span class="sxs-lookup"><span data-stu-id="68ed6-119">This option is not available in this release.</span></span>  
  
 <span data-ttu-id="68ed6-120">**Nom du serveur inscrit**</span><span class="sxs-lookup"><span data-stu-id="68ed6-120">**Registered server name**</span></span>  
 <span data-ttu-id="68ed6-121">Nom qui doit apparaître dans **Serveurs inscrits**.</span><span class="sxs-lookup"><span data-stu-id="68ed6-121">The name you want to appear in **Registered Servers**.</span></span> <span data-ttu-id="68ed6-122">Ce nom ne doit pas correspondre à celui de la zone **Nom du serveur** .</span><span class="sxs-lookup"><span data-stu-id="68ed6-122">This name does not have to match the **Server name** box.</span></span>  
  
 <span data-ttu-id="68ed6-123">**Description du serveur inscrit**</span><span class="sxs-lookup"><span data-stu-id="68ed6-123">**Registered server description**</span></span>  
 <span data-ttu-id="68ed6-124">Entrez une description facultative du serveur.</span><span class="sxs-lookup"><span data-stu-id="68ed6-124">Enter an optional description of the server.</span></span>  
  
 <span data-ttu-id="68ed6-125">**Test**</span><span class="sxs-lookup"><span data-stu-id="68ed6-125">**Test**</span></span>  
 <span data-ttu-id="68ed6-126">Cliquez sur cette option pour tester la connexion au serveur sélectionné dans la zone **Nom du serveur**.</span><span class="sxs-lookup"><span data-stu-id="68ed6-126">Click to test the connection to the server selected in **Server name**.</span></span>  
  
 <span data-ttu-id="68ed6-127">**Save**</span><span class="sxs-lookup"><span data-stu-id="68ed6-127">**Save**</span></span>  
 <span data-ttu-id="68ed6-128">Cliquez sur ce bouton pour enregistrer les paramètres des serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="68ed6-128">Click to save the Registered Servers settings.</span></span>  
  
  
