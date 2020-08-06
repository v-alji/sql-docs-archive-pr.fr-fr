---
title: Inscrire un serveur connecté
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.f1
helpviewer_keywords:
- Registered Servers [SQL Server], register connected servers
- connected server registrations [SQL Server]
ms.assetid: 77deb5f5-0f80-484f-8b8b-29afa67ec18f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1d337d2da7d305165307745fb02526e37b53bbd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603764"
---
# <a name="register-a-connected-server-sql-server-management-studio"></a><span data-ttu-id="cca10-102">Inscrire un serveur connecté (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="cca10-102">Register a Connected Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="cca10-103">Cette rubrique explique comment inscrire des serveurs dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cca10-103">This topic describes how to register servers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="cca10-104">Lors de l'inscription du serveur, vous pouvez enregistrer les informations de connexion relatives aux serveurs auxquels vous accédez fréquemment.</span><span class="sxs-lookup"><span data-stu-id="cca10-104">By registering the server, you can save the connection information for servers that you access frequently.</span></span> <span data-ttu-id="cca10-105">Un serveur peut être inscrit avant la connexion ou au moment de la connexion depuis l'Explorateur d'objets.</span><span class="sxs-lookup"><span data-stu-id="cca10-105">A server can be registered before connecting, or at the time of connection from Object Explorer.</span></span>  
  
 <span data-ttu-id="cca10-106">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="cca10-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="cca10-107">**Pour inscrire un serveur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="cca10-107">**To register a server, using:**</span></span>  
  
     [<span data-ttu-id="cca10-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cca10-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="cca10-109">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="cca10-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-register-a-connected-server"></a><span data-ttu-id="cca10-110">Pour inscrire un serveur connecté</span><span class="sxs-lookup"><span data-stu-id="cca10-110">To register a connected server</span></span>  
  
1.  <span data-ttu-id="cca10-111">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur un serveur auquel vous êtes déjà connecté, puis cliquez sur **Inscrire**.</span><span class="sxs-lookup"><span data-stu-id="cca10-111">In Object Explorer, right-click a server to which you already are connected, and then click **Register**.</span></span>  
  
     <span data-ttu-id="cca10-112">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="cca10-112">**Server name**</span></span>  
     <span data-ttu-id="cca10-113">Entrez le nom que vous souhaitez donner au serveur inscrit.</span><span class="sxs-lookup"><span data-stu-id="cca10-113">Enter the name you want to use for the registered server.</span></span> <span data-ttu-id="cca10-114">L'inscription d'un serveur local ou distant à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] vous permet de stocker les informations relatives à la connexion au serveur pour des connexions futures.</span><span class="sxs-lookup"><span data-stu-id="cca10-114">Registering a local or remote server using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lets you store the server connection information for future connections.</span></span> <span data-ttu-id="cca10-115">La valeur par défaut de ce champ est le nom du serveur entré lors de la connexion à celui-ci.</span><span class="sxs-lookup"><span data-stu-id="cca10-115">This field defaults to the server name entered when you were connecting to the server.</span></span> <span data-ttu-id="cca10-116">Vous pouvez conserver ce nom ou entrer un autre nom plus convivial.</span><span class="sxs-lookup"><span data-stu-id="cca10-116">You can retain this server name or enter another easy-to-use name for the server.</span></span>  
  
     <span data-ttu-id="cca10-117">**Description du serveur**</span><span class="sxs-lookup"><span data-stu-id="cca10-117">**Server description**</span></span>  
     <span data-ttu-id="cca10-118">Entrez une description facultative du serveur.</span><span class="sxs-lookup"><span data-stu-id="cca10-118">Enter an optional description of the server.</span></span> <span data-ttu-id="cca10-119">Le nombre maximal de caractères autorisé est 250.</span><span class="sxs-lookup"><span data-stu-id="cca10-119">The maximum number of characters allowed is 250.</span></span>  
  
     <span data-ttu-id="cca10-120">**Sélectionnez un groupe de serveurs**</span><span class="sxs-lookup"><span data-stu-id="cca10-120">**Select a server group**</span></span>  
     <span data-ttu-id="cca10-121">Sélectionnez le groupe de serveurs dans lequel vous souhaitez enregistrer l'inscription du serveur.</span><span class="sxs-lookup"><span data-stu-id="cca10-121">Select the server group where you want to save the server registration.</span></span>  
  
     <span data-ttu-id="cca10-122">**Nouveau groupe**</span><span class="sxs-lookup"><span data-stu-id="cca10-122">**New Group**</span></span>  
     <span data-ttu-id="cca10-123">Cliquez sur cette option pour ouvrir la boîte de dialogue **Nouveau groupe** et créer un nouveau groupe de serveurs pour le serveur inscrit.</span><span class="sxs-lookup"><span data-stu-id="cca10-123">Click to launch the **New Group** dialog box, where you can create a new server group for the registered server.</span></span>  
  
     <span data-ttu-id="cca10-124">**Save**</span><span class="sxs-lookup"><span data-stu-id="cca10-124">**Save**</span></span>  
     <span data-ttu-id="cca10-125">Cliquez sur ce bouton pour enregistrer les informations entrées et créer un serveur inscrit.</span><span class="sxs-lookup"><span data-stu-id="cca10-125">Click to save the information you have entered and create a registered server.</span></span>  
  
  
