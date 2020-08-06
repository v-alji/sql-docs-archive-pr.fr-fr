---
title: Propriétés des protocoles clients (onglet ordre) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: stevestein
ms.author: sstein
ms.openlocfilehash: a367cff3495389d1a707ed108ba75e1e736538b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697328"
---
# <a name="client-protocols-properties-order-tab"></a><span data-ttu-id="5a47f-102">Propriétés de protocoles clients (onglet Ordre)</span><span class="sxs-lookup"><span data-stu-id="5a47f-102">Client Protocols Properties (Order Tab)</span></span>
  <span data-ttu-id="5a47f-103">La page **Ordre**de la boîte de dialogue **Propriétés de protocoles clients** vous permet d’afficher et d’activer les protocoles clients.</span><span class="sxs-lookup"><span data-stu-id="5a47f-103">Use the **Order**page on the **Client Protocols Properties** dialog box to view and enable the client protocols.</span></span>  
  
 <span data-ttu-id="5a47f-104">Cliquez sur un protocole, puis sur **Activer** ou **Désactiver** pour déplacer le protocole sélectionné vers la liste **Protocoles désactivés** ou **Protocoles activés** .</span><span class="sxs-lookup"><span data-stu-id="5a47f-104">Click a protocol, and then click **Enable** or **Disable** to move the selected protocol to the **Disabled Protocols** or **Enabled Protocols** list.</span></span>  
  
 <span data-ttu-id="5a47f-105">Les protocoles sont essayés dans l'ordre dans lequel ils sont répertoriés, en commençant par le premier de la liste. Déplacez les protocoles vers le haut ou vers le bas dans la liste **Protocoles activés** , en cliquant sur les flèches haut et bas.</span><span class="sxs-lookup"><span data-stu-id="5a47f-105">Protocols are tried in the order listed, attempting to connect using the top protocol first, and then the second listed protocol, etc. Move protocols up or down the **Enabled Protocols** list, by clicking the up arrow and down arrow buttons.</span></span> <span data-ttu-id="5a47f-106">Lors de l’établissement d’une connexion à [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d’un client installé sur cet ordinateur, le protocole **Mémoire partagée** est toujours essayé en premier, s’il est activé.</span><span class="sxs-lookup"><span data-stu-id="5a47f-106">When connecting to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer, the **Shared Memory** protocol will always be tried first, if enabled.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a47f-107">Ces paramètres ne sont pas utilisés par SqlClient [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="5a47f-107">These settings are not used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient.</span></span> <span data-ttu-id="5a47f-108">L'ordre des protocoles pour SqlClient .NET commence par TCP, puis viennent les canaux nommés, qui ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="5a47f-108">The protocol order for .NET SqlClient is first TCP, and then named pipes, which cannot be changed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="5a47f-109">Options</span><span class="sxs-lookup"><span data-stu-id="5a47f-109">Options</span></span>  
 <span data-ttu-id="5a47f-110">**Protocoles désactivés**</span><span class="sxs-lookup"><span data-stu-id="5a47f-110">**Disabled Protocols**</span></span>  
 <span data-ttu-id="5a47f-111">Répertorie les protocoles installés mais actuellement non utilisés.</span><span class="sxs-lookup"><span data-stu-id="5a47f-111">Lists protocols which are installed but are not currently used.</span></span>  
  
 <span data-ttu-id="5a47f-112">**Protocoles activés**</span><span class="sxs-lookup"><span data-stu-id="5a47f-112">**Enabled Protocols**</span></span>  
 <span data-ttu-id="5a47f-113">Répertorie les protocoles disponibles pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les clients sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="5a47f-113">Lists protocols which are available for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this computer.</span></span>  
  
 **>**  
 <span data-ttu-id="5a47f-114">Active le protocole affiché en surbrillance dans la zone **Protocoles désactivés** , en le déplaçant vers la zone **Protocoles activés** .</span><span class="sxs-lookup"><span data-stu-id="5a47f-114">Enables the currently highlighted protocol in the **Disabled Protocols** box, moving it to the **Enabled Protocols** box.</span></span>  
  
 **\<**  
 <span data-ttu-id="5a47f-115">Désactive le protocole affiché en surbrillance dans la zone **Protocoles activés** , en le déplaçant vers la zone **Protocoles désactivés** .</span><span class="sxs-lookup"><span data-stu-id="5a47f-115">Disables the currently highlighted protocol in the **Enabled Protocols** box, moving it to the **Disabled Protocols** box.</span></span>  
  
 <span data-ttu-id="5a47f-116">Flèche haut</span><span class="sxs-lookup"><span data-stu-id="5a47f-116">Up arrow</span></span>  
 <span data-ttu-id="5a47f-117">Déplace le protocole affiché en surbrillance vers le haut de la liste.</span><span class="sxs-lookup"><span data-stu-id="5a47f-117">Moves the highlighted protocol up in the list.</span></span> <span data-ttu-id="5a47f-118">Cela vous permet d'augmenter la priorité avec laquelle la Net-Library essaie d'utiliser le protocole sélectionné pour les connexions.</span><span class="sxs-lookup"><span data-stu-id="5a47f-118">This allows you to increase the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="5a47f-119">Flèche bas</span><span class="sxs-lookup"><span data-stu-id="5a47f-119">Down arrow</span></span>  
 <span data-ttu-id="5a47f-120">Déplace le protocole affiché en surbrillance vers le bas de la liste.</span><span class="sxs-lookup"><span data-stu-id="5a47f-120">Moves the highlighted protocol down in the list.</span></span> <span data-ttu-id="5a47f-121">Cela vous permet de diminuer la priorité avec laquelle la Net-Library essaie d'utiliser le protocole sélectionné pour les connexions.</span><span class="sxs-lookup"><span data-stu-id="5a47f-121">This allows you to decrease the priority in which the Net-Library will attempt to use the selected protocol for connections.</span></span>  
  
 <span data-ttu-id="5a47f-122">**Activer le protocole de mémoire partagée**</span><span class="sxs-lookup"><span data-stu-id="5a47f-122">**Enable Shared Memory Protocol**</span></span>  
 <span data-ttu-id="5a47f-123">Lors de l’établissement d’une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à partir d’un client installé sur cet ordinateur, active le protocole de mémoire partagée qui est toujours essayé en premier (s’il est activé).</span><span class="sxs-lookup"><span data-stu-id="5a47f-123">Enables the shared memory protocol which is always tried first (if enabled), when connecting to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from a client on that computer.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a47f-124">Si le protocole est spécifié par le biais d'un préfixe ou à l'intérieur de la chaîne de connexion, seul le protocole spécifié est essayé.</span><span class="sxs-lookup"><span data-stu-id="5a47f-124">If the protocol is specified through a prefix or as part of the connection string, only the specified protocol is attempted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a47f-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a47f-125">See Also</span></span>  
 [<span data-ttu-id="5a47f-126">Choix d’un protocole réseau</span><span class="sxs-lookup"><span data-stu-id="5a47f-126">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
