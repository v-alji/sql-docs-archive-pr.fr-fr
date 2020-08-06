---
title: Informations sur le serveur Web | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.webserverinformation.f1
ms.assetid: 86d72275-45c7-459f-98cf-f5a366ed279c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7b461ed26b3e234f083add3312e256e164efc9b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603921"
---
# <a name="web-server-information"></a><span data-ttu-id="cbae0-102">Informations sur le serveur Web</span><span class="sxs-lookup"><span data-stu-id="cbae0-102">Web Server Information</span></span>
  <span data-ttu-id="cbae0-103">Les informations sur le serveur Web sont nécessaires pour pouvoir utiliser l'option de synchronisation Web pour la réplication de fusion.</span><span class="sxs-lookup"><span data-stu-id="cbae0-103">Web server information is required to use the Web synchronization option for merge replication.</span></span> <span data-ttu-id="cbae0-104">Pour obtenir des informations sur la configuration de la synchronisation Web, consultez [Configurer la synchronisation Web](configure-web-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="cbae0-104">For information about configuring Web synchronization, see [Configure Web Synchronization](configure-web-synchronization.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="cbae0-105">Options</span><span class="sxs-lookup"><span data-stu-id="cbae0-105">Options</span></span>  
 <span data-ttu-id="cbae0-106">**Adresse du serveur Web**</span><span class="sxs-lookup"><span data-stu-id="cbae0-106">**Web server address**</span></span>  
 <span data-ttu-id="cbae0-107">Si vous avez spécifié une adresse de serveur web dans la page **Capture instantanée FTP et Internet** de la boîte de dialogue **Propriétés de publication**, elle figure dans la zone de texte comme adresse par défaut.</span><span class="sxs-lookup"><span data-stu-id="cbae0-107">If you specified a Web server address in the **FTP Snapshot andInternet** page of the **Publication Properties** dialog box, it appears in this text box as a default.</span></span> <span data-ttu-id="cbae0-108">Acceptez cette adresse ou entrez une adresse de serveur Web qualifiée complète pour le serveur [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) qui synchronise cet abonnement.</span><span class="sxs-lookup"><span data-stu-id="cbae0-108">Either accept the default or enter a fully qualified Web server address for the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Information Services (IIS) server that synchronizes this subscription.</span></span>  
  
 <span data-ttu-id="cbae0-109">**Procédure de connexion de chaque Abonné au serveur Web**</span><span class="sxs-lookup"><span data-stu-id="cbae0-109">**How will each Subscriber connect to the Web server?**</span></span>  
 <span data-ttu-id="cbae0-110">Spécifiez le type d'authentification à utiliser pour la connexion au serveur Web.</span><span class="sxs-lookup"><span data-stu-id="cbae0-110">Specify the type of authentication used to connect to the Web server.</span></span> <span data-ttu-id="cbae0-111">Il est recommandé d'utiliser l'authentification de base pour les connexions au serveur IIS avec SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="cbae0-111">It is recommended to use Basic Authentication for connections to the IIS server in conjunction with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="cbae0-112">Si vous sélectionnez I'authentification de base, entrez la connexion et le mot de passe à utiliser pour se connecter de l'Abonné au serveur IIS.</span><span class="sxs-lookup"><span data-stu-id="cbae0-112">If you select Basic Authentication, enter the login and password that will be used to connect from the Subscriber to the IIS server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbae0-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cbae0-113">See Also</span></span>  
 <span data-ttu-id="cbae0-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span><span class="sxs-lookup"><span data-stu-id="cbae0-114">[Create a Pull Subscription](create-a-pull-subscription.md) </span></span>  
 <span data-ttu-id="cbae0-115">[Afficher et modifier les propriétés d’un abonnement par extraction](view-and-modify-pull-subscription-properties.md) </span><span class="sxs-lookup"><span data-stu-id="cbae0-115">[View and Modify Pull Subscription Properties](view-and-modify-pull-subscription-properties.md) </span></span>  
 <span data-ttu-id="cbae0-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="cbae0-116">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 <span data-ttu-id="cbae0-117">[S’abonner aux Publications](subscribe-to-publications.md) </span><span class="sxs-lookup"><span data-stu-id="cbae0-117">[Subscribe to Publications](subscribe-to-publications.md) </span></span>  
 [<span data-ttu-id="cbae0-118">Synchronisation web pour la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="cbae0-118">Web Synchronization for Merge Replication</span></span>](web-synchronization-for-merge-replication.md)  
  
  
