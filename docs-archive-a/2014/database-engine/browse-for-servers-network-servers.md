---
title: Rechercher les serveurs (Serveurs réseau) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.browseservers.network.f1
ms.assetid: a59ffcd6-4b69-4c5c-9740-699ccb2183fb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ba5e4e5dd6d9a6541a98e0cb30229d7335bac24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611327"
---
# <a name="browse-for-servers-network-servers"></a><span data-ttu-id="06e7b-102">Parcourir les serveurs (Serveurs réseau)</span><span class="sxs-lookup"><span data-stu-id="06e7b-102">Browse for Servers (Network Servers)</span></span>
  <span data-ttu-id="06e7b-103">Quand vous vous connectez à un composant [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sans connaître le nom exact de l’instance [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], dans la zone **Nom du serveur**, cliquez sur **Parcourir** pour ouvrir la boîte de dialogue **Rechercher les serveurs**.</span><span class="sxs-lookup"><span data-stu-id="06e7b-103">If you are connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] component and you do not know the exact name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance, click **Browse for more** in the **Server name** box to open the **Browse for Servers** dialog box.</span></span>  
  
 <span data-ttu-id="06e7b-104">Cette boîte de dialogue est remplie par le service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser sur les ordinateurs serveurs.</span><span class="sxs-lookup"><span data-stu-id="06e7b-104">This dialog is populated by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service on the server computers.</span></span> <span data-ttu-id="06e7b-105">Plusieurs raisons peuvent expliquer pourquoi le nom d'une instance n'apparaît pas dans la liste :</span><span class="sxs-lookup"><span data-stu-id="06e7b-105">There are several reasons why the name of an instance might not appear in the list:</span></span>  
  
-   <span data-ttu-id="06e7b-106">Le service [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser ne fonctionne peut-être pas sur l'ordinateur qui exécute [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="06e7b-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service might not be running on the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="06e7b-107">Le port UDP 1434 est peut-être bloqué par un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="06e7b-107">UDP port 1434 might be blocked by a firewall.</span></span>  
  
-   <span data-ttu-id="06e7b-108">L’indicateur **HideInstance** est peut-être défini.</span><span class="sxs-lookup"><span data-stu-id="06e7b-108">The **HideInstance** flag might be set.</span></span>  
  
 <span data-ttu-id="06e7b-109">Pour vous connecter à une instance qui n'apparaît pas dans la liste, entrez une chaîne de connexion complète pour l'instance, y compris le numéro de port TCP/IP ou le nom des canaux nommés.</span><span class="sxs-lookup"><span data-stu-id="06e7b-109">To connect to an instance that does not appear in the list, type a full connection string for the instance, including the TCP/IP port number or the named pipes pipe name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="06e7b-110">Options</span><span class="sxs-lookup"><span data-stu-id="06e7b-110">Options</span></span>  
 <span data-ttu-id="06e7b-111">**Sélectionnez une instance de SQL Server sur le réseau pour votre connexion**</span><span class="sxs-lookup"><span data-stu-id="06e7b-111">**Select a SQL Server instance in the network for your connection**</span></span>  
 <span data-ttu-id="06e7b-112">Désignez le serveur auquel vous souhaitez vous connecter en cliquant sur l'instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] affichée dans l'arborescence.</span><span class="sxs-lookup"><span data-stu-id="06e7b-112">Designate the server you want to connect to by clicking on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance displayed in the tree.</span></span> <span data-ttu-id="06e7b-113">Vous pouvez afficher ou masquer des parties de l’arborescence en cliquant sur les nœuds marqués avec **+** un **-** symbole ou.</span><span class="sxs-lookup"><span data-stu-id="06e7b-113">You can show or hide portions of the tree view by clicking on the nodes marked with a **+** or **-** symbol.</span></span>  
  
  
