---
title: Annulation de commandes (XMLA) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- connections [XML for Analysis]
- associated connections [XML for Analysis]
- XML for Analysis, canceling
- associated sessions [XML for Analysis]
- canceling connections
- canceling commands
- canceling sessions
- SPID
- XMLA, canceling
- server process IDs [XML for Analysis]
- sessions [XML for Analysis]
ms.assetid: b59f8197-c33d-4e65-9022-848ccba540f5
author: minewiskan
ms.author: owend
ms.openlocfilehash: 003c70362c38ae1838b4679abf6485fa031a9143
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696260"
---
# <a name="canceling-commands-xmla"></a><span data-ttu-id="7334f-102">Annulation de commandes (XMLA)</span><span class="sxs-lookup"><span data-stu-id="7334f-102">Canceling Commands (XMLA)</span></span>
  <span data-ttu-id="7334f-103">En fonction des autorisations d’administration de l’utilisateur qui émet la commande, la commande [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) dans XML for Analysis (XMLA) peut annuler une commande sur une session, une session, une connexion, un processus serveur ou une session ou une connexion associée.</span><span class="sxs-lookup"><span data-stu-id="7334f-103">Depending on the administrative permissions of the user issuing the command, the [Cancel](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla) command in XML for Analysis (XMLA) can cancel a command on a session, a session, a connection, a server process, or an associated session or connection.</span></span>  
  
## <a name="canceling-commands"></a><span data-ttu-id="7334f-104">Annulation de commandes</span><span class="sxs-lookup"><span data-stu-id="7334f-104">Canceling Commands</span></span>  
 <span data-ttu-id="7334f-105">Un utilisateur peut annuler la commande en cours d'exécution dans le contexte de la session explicite active en envoyant une commande `Cancel` sans aucune propriété spécifiée.</span><span class="sxs-lookup"><span data-stu-id="7334f-105">A user can cancel the currently executing command within the context of the current explicit session by sending a `Cancel` command with no specified properties.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7334f-106">Une commande en cours d'exécution dans une session implicite ne peut pas être annulée par un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="7334f-106">A command running in an implicit session cannot be canceled by a user.</span></span>  
  
### <a name="canceling-batch-commands"></a><span data-ttu-id="7334f-107">Annulation de commandes Batch</span><span class="sxs-lookup"><span data-stu-id="7334f-107">Canceling Batch Commands</span></span>  
 <span data-ttu-id="7334f-108">Si un utilisateur annule une commande `Batch`, toutes les commandes qu'il reste à exécuter dans la commande `Batch` sont annulées.</span><span class="sxs-lookup"><span data-stu-id="7334f-108">If a user cancels a `Batch` command, then all remaining commands not yet executed within the `Batch` command are canceled.</span></span> <span data-ttu-id="7334f-109">Si la commande `Batch` était transactionnelle, les commandes qui ont été exécutées avant l'exécution de la commande `Cancel` sont annulées.</span><span class="sxs-lookup"><span data-stu-id="7334f-109">If the `Batch` command was transactional, any commands that were executed before the `Cancel` command runs are rolled back.</span></span>  
  
## <a name="canceling-sessions"></a><span data-ttu-id="7334f-110">Annulation de sessions</span><span class="sxs-lookup"><span data-stu-id="7334f-110">Canceling Sessions</span></span>  
 <span data-ttu-id="7334f-111">En spécifiant un identificateur de session pour une session explicite dans la propriété [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) de la `Cancel` commande, un administrateur de base de données ou un administrateur de serveur peut annuler une session, y compris la commande en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="7334f-111">By specifying a session identifier for an explicit session in the [SessionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a database administrator or server administrator can cancel a session, including the currently executing command.</span></span> <span data-ttu-id="7334f-112">Un administrateur de base de données ne peut annuler les sessions que pour les bases de données pour lesquelles il dispose d'autorisations administratives.</span><span class="sxs-lookup"><span data-stu-id="7334f-112">A database administrator can only cancel sessions for databases on which he or she has administrative permissions.</span></span>  
  
 <span data-ttu-id="7334f-113">Un administrateur de base de données peut récupérer les sessions actives pour une base de données spécifiée en récupérant l'ensemble de lignes de schéma DISCOVER_SESSIONS.</span><span class="sxs-lookup"><span data-stu-id="7334f-113">A database administrator can retrieve the active sessions for a specified database by retrieving the DISCOVER_SESSIONS schema rowset.</span></span> <span data-ttu-id="7334f-114">Pour récupérer l’ensemble de lignes de schéma DISCOVER_SESSIONS, l’administrateur de base de données utilise la `Discover` méthode XMLA et spécifie l’identificateur de base de données approprié pour la colonne de restriction SESSION_CURRENT_DATABASE dans la propriété [restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) de la `Discover` méthode.</span><span class="sxs-lookup"><span data-stu-id="7334f-114">To retrieve the DISCOVER_SESSIONS schema rowset, the database administrator uses the XMLA `Discover` method and specifies the appropriate database identifier for the SESSION_CURRENT_DATABASE restriction column in the [Restrictions](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/restrictions-element-xmla) property of the `Discover` method.</span></span>  
  
## <a name="canceling-connections"></a><span data-ttu-id="7334f-115">Annulation de connexions</span><span class="sxs-lookup"><span data-stu-id="7334f-115">Canceling Connections</span></span>  
 <span data-ttu-id="7334f-116">En spécifiant un identificateur de connexion dans la propriété [ID_de_connexion](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) de la `Cancel` commande, un administrateur de serveur peut annuler toutes les sessions associées à une connexion donnée, y compris toutes les commandes en cours d’exécution, et annuler la connexion.</span><span class="sxs-lookup"><span data-stu-id="7334f-116">By specifying a connection identifier in the [ConnectionID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/connectionid-element-xmla) property of the `Cancel` command, a server administrator can cancel all of the sessions associated with a given connection, including all running commands, and cancel the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7334f-117">Si l’instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne peut pas localiser et annuler les sessions associées à une connexion, par exemple lorsque la pompe de données ouvre plusieurs sessions tout en fournissant une connectivité http, l’instance ne peut pas annuler la connexion.</span><span class="sxs-lookup"><span data-stu-id="7334f-117">If the instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] cannot locate and cancel the sessions associated with a connection, such as when the data pump opens multiple sessions while providing HTTP connectivity, the instance cannot cancel the connection.</span></span> <span data-ttu-id="7334f-118">Si ce cas est rencontré pendant l'exécution d'une commande `Cancel`, une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="7334f-118">If this case is encountered during the execution of a `Cancel` command, an error occurs.</span></span>  
  
 <span data-ttu-id="7334f-119">Un administrateur de serveur peut récupérer les connexions actives pour une instance [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en récupérant l'ensemble de lignes de schéma DISCOVER_CONNECTIONS à l'aide de la méthode XMLA `Discover`.</span><span class="sxs-lookup"><span data-stu-id="7334f-119">A server administrator can retrieve the active connections for an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance by retrieving the DISCOVER_CONNECTIONS schema rowset using the XMLA `Discover` method.</span></span>  
  
## <a name="canceling-server-processes"></a><span data-ttu-id="7334f-120">Annulation de processus serveur</span><span class="sxs-lookup"><span data-stu-id="7334f-120">Canceling Server Processes</span></span>  
 <span data-ttu-id="7334f-121">En spécifiant un identificateur de processus serveur (SPID) dans la propriété [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) de la `Cancel` commande, un administrateur de serveur peut annuler les commandes associées à un SPID donné.</span><span class="sxs-lookup"><span data-stu-id="7334f-121">By specifying a server process identifier (SPID) in the [SPID](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/id-element-xmla) property of the `Cancel` command, a server administrator can cancel the commands associated with a given SPID.</span></span>  
  
## <a name="canceling-associated-sessions-and-connections"></a><span data-ttu-id="7334f-122">Annulation de sessions et de connexions associées</span><span class="sxs-lookup"><span data-stu-id="7334f-122">Canceling Associated Sessions and Connections</span></span>  
 <span data-ttu-id="7334f-123">Vous pouvez définir la propriété [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) sur true pour annuler les connexions, les sessions et les commandes associées à la connexion, à la session ou au SPID spécifié dans la `Cancel` commande.</span><span class="sxs-lookup"><span data-stu-id="7334f-123">You can set the [CancelAssociated](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cancelassociated-element-xmla) property to true to cancel the connections, sessions, and commands associated with the connection, session, or SPID specified in the `Cancel` command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7334f-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7334f-124">See Also</span></span>  
 <span data-ttu-id="7334f-125">[Méthode Discover &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span><span class="sxs-lookup"><span data-stu-id="7334f-125">[Discover Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) </span></span>  
 [<span data-ttu-id="7334f-126">Développement avec XMLA dans Analysis Services</span><span class="sxs-lookup"><span data-stu-id="7334f-126">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
