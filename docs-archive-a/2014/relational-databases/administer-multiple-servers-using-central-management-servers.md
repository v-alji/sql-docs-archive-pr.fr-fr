---
title: Administrer plusieurs serveurs à l’aide de serveurs de gestion centralisée | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- central management server
- multiserver administration [SQL Server]
- master servers [SQL Server], central management servers
- target configuration [SQL Server]
- server configuration [SQL Server]
ms.assetid: 427911a7-57d4-4542-8846-47c3267a5d9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3906165b595f6faa15812f70377a3bc0f550e52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699839"
---
# <a name="administer-multiple-servers-using-central-management-servers"></a><span data-ttu-id="df80d-102">Administrer plusieurs serveurs à l'aide de serveurs de gestion centralisée</span><span class="sxs-lookup"><span data-stu-id="df80d-102">Administer Multiple Servers Using Central Management Servers</span></span>
  <span data-ttu-id="df80d-103">Vous pouvez administrer plusieurs serveurs en désignant des serveurs de gestion centralisée et en créant des groupes de serveurs.</span><span class="sxs-lookup"><span data-stu-id="df80d-103">You can administer multiple servers by designating Central Management Servers and creating server groups.</span></span>  
  
## <a name="benefits-of-central-management-servers-and-server-groups"></a><span data-ttu-id="df80d-104">Avantages des serveurs de gestion centralisée et des groupes de serveurs</span><span class="sxs-lookup"><span data-stu-id="df80d-104">Benefits of Central Management Servers and Server Groups</span></span>  
 <span data-ttu-id="df80d-105">Une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] désignée comme serveur de gestion centralisée gère des groupes de serveurs qui contiennent les informations de connexion pour une ou plusieurs instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df80d-105">An instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is designated as a Central Management Server maintains server groups that contain the connection information for one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="df80d-106">Les instructions [!INCLUDE[tsql](../includes/tsql-md.md)] et les stratégies de la Gestion basée sur des stratégies peuvent être exécutées simultanément sur des groupes de serveurs.</span><span class="sxs-lookup"><span data-stu-id="df80d-106">[!INCLUDE[tsql](../includes/tsql-md.md)] statements and Policy-Based Management policies can be executed at the same time against server groups.</span></span> <span data-ttu-id="df80d-107">Vous pouvez également consulter les fichiers journaux de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] sur les instances gérées via un serveur de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="df80d-107">You can also view the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] log files on instances that are managed through a Central Management Server.</span></span> <span data-ttu-id="df80d-108">Les versions de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] antérieures à [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] ne peuvent pas être désignées comme serveurs de gestion centralisée.</span><span class="sxs-lookup"><span data-stu-id="df80d-108">Versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] cannot be designated as a Central Management Server.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="df80d-109">Les instructions peuvent également être exécutées sur des groupes de serveurs locaux dans Serveurs inscrits.</span><span class="sxs-lookup"><span data-stu-id="df80d-109">statements can also be executed against local server groups in Registered Servers.</span></span>  
  
### <a name="related-tasks"></a><span data-ttu-id="df80d-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="df80d-110">Related Tasks</span></span>  
 <span data-ttu-id="df80d-111">Pour créer un serveur de gestion centralisée et des groupes de serveurs, utilisez la fenêtre **Serveurs inscrits** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df80d-111">To create a Central Management Server and server groups, use the **Registered Servers** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="df80d-112">Notez que le serveur de gestion centralisée ne peut pas être membre d'un groupe qu'il gère.</span><span class="sxs-lookup"><span data-stu-id="df80d-112">Note that the Central Management Server cannot be a member of a group that it maintains.</span></span> <span data-ttu-id="df80d-113">Pour plus d’informations sur la création de serveurs de gestion centralisée et de groupes de serveurs, consultez [Créer un serveur de gestion centralisée et un groupe de serveurs &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="df80d-113">For more information about how to create Central Management Servers and server groups, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df80d-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df80d-114">See Also</span></span>  
 [<span data-ttu-id="df80d-115">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="df80d-115">Administer Servers by Using Policy-Based Management</span></span>](policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
