---
title: Sécurité de la réplication sur Internet | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- security [SQL Server replication], Internet
- Internet [SQL Server replication], security
ms.assetid: 25b7af05-2721-4b24-9083-fb671e8bf4e0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 47408b2b9559d33da4563c6fc9560d20338ee01d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708167"
---
# <a name="securing-replication-over-the-internet"></a><span data-ttu-id="a6213-102">Sécurité de la réplication sur Internet</span><span class="sxs-lookup"><span data-stu-id="a6213-102">Securing Replication Over the Internet</span></span>
  <span data-ttu-id="a6213-103">La réplication sur Internet est une solution souple, notamment pour les Abonnés itinérants, à condition qu'elle soit configurée correctement afin d'assurer une sécurité adaptée.</span><span class="sxs-lookup"><span data-stu-id="a6213-103">Replication over the Internet can provide flexibility, particularly for mobile Subscribers, but you must configure Internet replication appropriately to ensure adequate security.</span></span> <span data-ttu-id="a6213-104">Pour partager des informations sur Internet en toute sécurité,[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommande l'utilisation de l'une des deux techniques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a6213-104">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] recommends using one of two techniques for securely sharing information over the Internet:</span></span>  
  
-   <span data-ttu-id="a6213-105">le réseau privé virtuel (VPN, Virtual Private Network) ;</span><span class="sxs-lookup"><span data-stu-id="a6213-105">Virtual private network (VPN)</span></span>  
  
-   <span data-ttu-id="a6213-106">l'option de synchronisation Web pour la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="a6213-106">The Web synchronization option for merge replication</span></span>  
  
## <a name="virtual-private-network"></a><span data-ttu-id="a6213-107">Réseau privé virtuel</span><span class="sxs-lookup"><span data-stu-id="a6213-107">Virtual Private Network</span></span>  
 <span data-ttu-id="a6213-108">Les réseaux privés virtuels fournissent une méthode en couche simple et sécurisée pour répliquer des données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur Internet.</span><span class="sxs-lookup"><span data-stu-id="a6213-108">Virtual private networks provide a simple and secure layered approach to replicating [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data over the Internet.</span></span> <span data-ttu-id="a6213-109">La connexion au réseau privé virtuel via Internet fonctionne, sur le plan logique, comme une liaison de réseau étendu (WAN, Wide Area Network) entre les sites.</span><span class="sxs-lookup"><span data-stu-id="a6213-109">The VPN connection over the Internet logically operates as a Wide Area Network (WAN) link between the sites.</span></span>  
  
 <span data-ttu-id="a6213-110">Ce processus n'est possible qu'en établissant une connexion tunnel pour l'utilisateur via Internet ou tout autre réseau public à l'aide d'un protocole tel que le protocole [!INCLUDE[msCoName](../../../includes/msconame-md.md)] PPTP (Point-to-Point Tunneling Protocol), disponible dans le système d'exploitation [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000, ou le protocole L2TP (Layer Two Tunneling Protocol), disponible dans le système d'exploitation Windows 2000.</span><span class="sxs-lookup"><span data-stu-id="a6213-110">This is achieved by allowing the user to tunnel through the Internet or another public network using a protocol such as [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Point-to-Point Tunneling Protocol (PPTP) available with the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows NT version 4.0 or [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows 2000 operating system, or Layer Two Tunneling Protocol (L2TP) available with the Windows 2000 operating system.</span></span> <span data-ttu-id="a6213-111">Ce processus offre la sécurité et des fonctionnalités similaires à celles qui sont disponibles dans un réseau privé.</span><span class="sxs-lookup"><span data-stu-id="a6213-111">This process provides security and features similar to those available in a private network.</span></span>  
  
 <span data-ttu-id="a6213-112">Pour plus d'informations sur la configuration d'un réseau privé virtuel (VPN), consultez la documentation [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="a6213-112">For more information about setting up a VPN, see the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
## <a name="web-synchronization-through-iis"></a><span data-ttu-id="a6213-113">Synchronisation Web par le biais d'IIS</span><span class="sxs-lookup"><span data-stu-id="a6213-113">Web Synchronization Through IIS</span></span>  
 <span data-ttu-id="a6213-114">L'option de synchronisation Web pour la réplication de fusion permet de répliquer des données via le protocole HTTPS, ce qui peut être une méthode de réplication des données pratique via un pare-feu.</span><span class="sxs-lookup"><span data-stu-id="a6213-114">The web synchronization option for merge replication provides the ability to replicate data using the HTTPS protocol, which can be a convenient approach to replicating data through a firewall.</span></span> <span data-ttu-id="a6213-115">Pour plus d’informations sur la sécurité de la synchronisation web, consultez [Configurer la synchronisation web](../configure-web-synchronization.md) et [Architecture de la sécurité pour la synchronisation web](security-architecture-for-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="a6213-115">For more information, see [Configure Web Synchronization](../configure-web-synchronization.md) and [Security Architecture for Web Synchronization](security-architecture-for-web-synchronization.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6213-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6213-116">See Also</span></span>  
 <span data-ttu-id="a6213-117">[Replication Security Best Practices](replication-security-best-practices.md) </span><span class="sxs-lookup"><span data-stu-id="a6213-117">[Replication Security Best Practices](replication-security-best-practices.md) </span></span>  
 [<span data-ttu-id="a6213-118">Sécurité Réplication SQL Server</span><span class="sxs-lookup"><span data-stu-id="a6213-118">SQL Server Replication Security</span></span>](view-and-modify-replication-security-settings.md)  
  
  
