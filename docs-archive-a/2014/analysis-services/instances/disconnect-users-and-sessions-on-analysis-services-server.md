---
title: Déconnecter des utilisateurs et des sessions sur Analysis Services Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ending user activity [Analysis Services]
- connections [Analysis Services]
- sessions [Analysis Services]
ms.assetid: 3b0145a2-f21d-4dd0-a09e-83afeb2ff4a9
author: minewiskan
ms.author: owend
ms.openlocfilehash: bac20b663b0a65902c70e7a3c3bfe3f27b7bf061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698790"
---
# <a name="disconnect-users-and-sessions-on-analysis-services-server"></a><span data-ttu-id="6bb30-102">Déconnecter des utilisateurs et sessions sur un serveur Analysis Services</span><span class="sxs-lookup"><span data-stu-id="6bb30-102">Disconnect Users and Sessions on Analysis Services Server</span></span>
  <span data-ttu-id="6bb30-103">Un administrateur de [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] peut vouloir arrêter l'activité des utilisateurs dans le cadre de la gestion de la charge de travail.</span><span class="sxs-lookup"><span data-stu-id="6bb30-103">An administrator of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] may want to end user activity as part of workload management.</span></span> <span data-ttu-id="6bb30-104">Pour cela, vous devez annuler les sessions et les connexions.</span><span class="sxs-lookup"><span data-stu-id="6bb30-104">You do this by canceling sessions and connections.</span></span> <span data-ttu-id="6bb30-105">Les sessions peuvent être formées automatiquement lorsqu'une requête est exécutée (implicite) ou nommées au moment de la création par l'administrateur (explicite).</span><span class="sxs-lookup"><span data-stu-id="6bb30-105">Sessions can be formed automatically when a query is run (implicit), or named at the time of creation by the administrator (explicit).</span></span> <span data-ttu-id="6bb30-106">Les connexions sont des conduits ouverts par lesquels les requêtes peuvent être exécutées.</span><span class="sxs-lookup"><span data-stu-id="6bb30-106">Connections are open conduits over which queries can be run.</span></span> <span data-ttu-id="6bb30-107">Les sessions et les connexions peuvent être terminées pendant qu'elles sont actives.</span><span class="sxs-lookup"><span data-stu-id="6bb30-107">Both sessions and connections can be ended while they are active.</span></span> <span data-ttu-id="6bb30-108">Par exemple, un administrateur peut vouloir terminer le processus de traitement d'une session si le traitement dure trop longtemps ou si l'administrateur n'est pas sûr que la commande en cours d'exécution a été écrite correctement.</span><span class="sxs-lookup"><span data-stu-id="6bb30-108">For example, an administrator may want to end processing for a session if the processing is taking too long or if some doubt has arisen as to whether the command being executed was written correctly.</span></span>  
  
## <a name="ending-sessions-and-connections"></a><span data-ttu-id="6bb30-109">Arrêt des sessions et des connexions</span><span class="sxs-lookup"><span data-stu-id="6bb30-109">Ending Sessions and Connections</span></span>  
 <span data-ttu-id="6bb30-110">Pour gérer les sessions et les connexions, vous pouvez utiliser des vues de gestion dynamique (DMV) et XMLA :</span><span class="sxs-lookup"><span data-stu-id="6bb30-110">To manage sessions and connections, you can use Dynamic Management Views (DMVs) and XMLA:</span></span>  
  
1.  <span data-ttu-id="6bb30-111">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à une instance d'Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="6bb30-111">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to an Analysis Services instance.</span></span>  
  
2.  <span data-ttu-id="6bb30-112">Collez l'une des requêtes DMV suivantes dans une fenêtre de requête MDX pour obtenir la liste de toutes les sessions, connexions et commandes qui s'exécutent actuellement :</span><span class="sxs-lookup"><span data-stu-id="6bb30-112">Paste any one of the following DMV queries in an MDX query window to get a list of all sessions, connections, and commands that are currently executing:</span></span>  
  
     `Select * from $System.Discover_Sessions`  
  
     `Select * from $System.Discover_Connections`  
  
     `Select * from $System.Discover_Commands`  
  
3.  <span data-ttu-id="6bb30-113">Appuyez sur F5 pour exécuter la requête.</span><span class="sxs-lookup"><span data-stu-id="6bb30-113">Press F5 to execute the query.</span></span>  
  
     <span data-ttu-id="6bb30-114">La requête DMV renvoie des informations relatives à la session et à la connexion sous la forme d'un tableau, facilitant ainsi la lecture et la copie des données qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="6bb30-114">The DMV query returns session and connection information in a tabular result set that is easier read and copy from.</span></span>  
  
 <span data-ttu-id="6bb30-115">Gardez la fenêtre de requête ouverte.</span><span class="sxs-lookup"><span data-stu-id="6bb30-115">Keep the query window open.</span></span> <span data-ttu-id="6bb30-116">Dans la prochaine étape, vous retournerez à cette page pour copier les SPID de la session de laquelle vous voulez vous déconnecter.</span><span class="sxs-lookup"><span data-stu-id="6bb30-116">In the next step, you will want to return to this page to copy the SPIDs of the session you want to disconnect.</span></span>  
  
 <span data-ttu-id="6bb30-117">Pour terminer une session, ouvrez une deuxième fenêtre de requête XMLA.</span><span class="sxs-lookup"><span data-stu-id="6bb30-117">To end a session, open a second XMLA query window.</span></span>  
  
1.  <span data-ttu-id="6bb30-118">Collez la syntaxe suivante dans une fenêtre de requête MDX, en remplaçant l'espace réservé ConnectionID, SessionID ou SPID par une valeur valide copiée dans l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="6bb30-118">Paste the following syntax into an MDX query window, replacing the ConnectionID, SessionID, or SPID placeholder with a valid value copied from the previous step.</span></span>  
  
    ```  
    <Cancel xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">  
  
       <ConnectionID>111</ConnectionID>  
       <SessionID>222</SessionID>  
       <SPID>333</SPID>  
  
    <CancelAssociated>1</CancelAssociated>  
    </Cancel>  
  
    ```  
  
2.  <span data-ttu-id="6bb30-119">Appuyez sur F5 pour exécuter la commande d'annulation.</span><span class="sxs-lookup"><span data-stu-id="6bb30-119">Press F5 to execute the cancel command.</span></span>  
  
 <span data-ttu-id="6bb30-120">Le fait d'arrêter une connexion annule toutes les sessions et SPID, et ferme la session hôte.</span><span class="sxs-lookup"><span data-stu-id="6bb30-120">Ending a connection cancels all sessions and SPIDs, closing the host session.</span></span>  
  
 <span data-ttu-id="6bb30-121">L'arrêt d'une session arrête toutes les commandes (SPID) qui sont en cours d'exécution dans le cadre de cette session.</span><span class="sxs-lookup"><span data-stu-id="6bb30-121">Ending a session stops all commands (SPIDs) that are running as part of that session.</span></span>  
  
 <span data-ttu-id="6bb30-122">L'arrêt d'un SPID annule la commande correspondante.</span><span class="sxs-lookup"><span data-stu-id="6bb30-122">Ending a SPID cancels a particular commend.</span></span>  
  
 <span data-ttu-id="6bb30-123">Dans de rares cas, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ne fermera pas la connexion s’il n’arrive pas à effectuer le suivi de toutes les sessions et tous les SPID associés à la connexion (par exemple quand plusieurs sessions sont ouvertes dans un scénario HTTP).</span><span class="sxs-lookup"><span data-stu-id="6bb30-123">In rare cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will not close a connection if it cannot track all the sessions and SPIDs associated with the connection (for example, when multiple sessions are open in an HTTP scenario).</span></span>  
  
 <span data-ttu-id="6bb30-124">Pour plus d’informations sur le code XMLA mentionné dans cette rubrique, consultez [Méthode Execute &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) et [Élément Cancel &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="6bb30-124">For more information about the XMLA referenced in this topic, see [Execute Method &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) and [Cancel Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/cancel-element-xmla).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bb30-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6bb30-125">See Also</span></span>  
 <span data-ttu-id="6bb30-126">[Gestion des connexions et des sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span><span class="sxs-lookup"><span data-stu-id="6bb30-126">[Managing Connections and Sessions &#40;XMLA&#41;](../multidimensional-models-scripting-language-assl-xmla/managing-connections-and-sessions-xmla.md) </span></span>  
 <span data-ttu-id="6bb30-127">[Élément BeginSession &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="6bb30-127">[BeginSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/beginsession-element-xmla) </span></span>  
 <span data-ttu-id="6bb30-128">[Élément EndSession &#40;&#41;XMLA](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="6bb30-128">[EndSession Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/endsession-element-xmla) </span></span>  
 [<span data-ttu-id="6bb30-129">Élément Session &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="6bb30-129">Session Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-headers/session-element-xmla)  
  
  
