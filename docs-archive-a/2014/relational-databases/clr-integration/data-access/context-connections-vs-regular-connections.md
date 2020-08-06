---
title: Connexions régulières et contextuelles | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: a1dead02-be88-4b16-8cb2-db1284856764
author: rothja
ms.author: jroth
ms.openlocfilehash: ce531129099a8f4908bdc4b29920696d4ba3c505
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614658"
---
# <a name="regular-vs-context-connections"></a><span data-ttu-id="776c6-102">Connexions normales et Connexions contextuelles</span><span class="sxs-lookup"><span data-stu-id="776c6-102">Regular vs. Context Connections</span></span>
  <span data-ttu-id="776c6-103">Si vous vous connectez à un serveur distant, utilisez toujours des connexions normales plutôt que des connexions contextuelles.</span><span class="sxs-lookup"><span data-stu-id="776c6-103">If you are connecting to a remote server, always use regular connections rather than context connections.</span></span> <span data-ttu-id="776c6-104">Si vous devez vous connecter au même serveur sur lequel la procédure stockée ou la fonction est en cours d'exécution, utilisez la connexion contextuelle dans la majorité des cas.</span><span class="sxs-lookup"><span data-stu-id="776c6-104">If you need to connect to the same server on which the stored procedure or function is running, use the context connection in most cases.</span></span> <span data-ttu-id="776c6-105">Ceci présente des avantages, notamment l'exécution dans le même espace de transaction et la non-obligation de s'authentifier à nouveau.</span><span class="sxs-lookup"><span data-stu-id="776c6-105">This has benefits such as running in the same transaction space and not having to reauthenticate.</span></span>  
  
 <span data-ttu-id="776c6-106">Qui plus est, le recours aux connexions contextuelles produit généralement de meilleures performances et garantit une utilisation plus réduite des ressources.</span><span class="sxs-lookup"><span data-stu-id="776c6-106">Additionally, using the context connection typically results in better performance and less resource usage.</span></span> <span data-ttu-id="776c6-107">La connexion de contexte est une connexion en mode in-process uniquement. elle peut donc contacter le serveur « directement » en contournant le protocole réseau et les couches de transport pour envoyer des instructions Transact-SQL et recevoir des résultats.</span><span class="sxs-lookup"><span data-stu-id="776c6-107">The context connection is an in-process-only connection, so it can contact the server "directly" by bypassing the network protocol and transport layers to send Transact-SQL statements and receive results.</span></span> <span data-ttu-id="776c6-108">Le processus d'authentification est également ignoré.</span><span class="sxs-lookup"><span data-stu-id="776c6-108">The authentication process is bypassed, as well.</span></span> <span data-ttu-id="776c6-109">La figure suivante présente les composants principaux du fournisseur managé `SqlClient` et explique également comment les divers composants interagissent l'un avec l'autre lors de l'utilisation d'une connexion normale et de la connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="776c6-109">The following figure shows the primary components of the `SqlClient` managed provider, as well as how the different components interact with each other when using a regular connection, and when using the context connection.</span></span>  
  
 <span data-ttu-id="776c6-110">![Chemins de code d'un contexte et connexion normale.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Chemins de code d'un contexte et connexion normale.")</span><span class="sxs-lookup"><span data-stu-id="776c6-110">![Code paths of a context and a regular connnection.](../../../database-engine/dev-guide/media/clrintdataaccess.gif "Code paths of a context and a regular connnection.")</span></span>  
  
 <span data-ttu-id="776c6-111">La connexion contextuelle suit un chemin de code plus court et implique moins de composants. Vous pouvez donc vous attendre à des demandes et des résultats circulant vers et depuis le serveur plus rapidement qu'avec une connexion normale.</span><span class="sxs-lookup"><span data-stu-id="776c6-111">The context connection follows a shorter code path and involves fewer components, so you can expect requests and results to get to and from the server faster than in a regular connection.</span></span> <span data-ttu-id="776c6-112">Le temps d'exécution des requêtes sur le serveur est le même pour les connexions normales et contextuelles.</span><span class="sxs-lookup"><span data-stu-id="776c6-112">Query execution time on the server is the same for context and regular connections.</span></span>  
  
 <span data-ttu-id="776c6-113">Dans certains cas, vous devrez peut-être ouvrir une connexion normale distincte sur le même serveur.</span><span class="sxs-lookup"><span data-stu-id="776c6-113">There are some cases in which you may need to open a separate regular connection to the same server.</span></span> <span data-ttu-id="776c6-114">Par exemple, certaines restrictions s’appliquent à l’utilisation de la connexion contextuelle, décrite dans [restrictions sur les connexions régulières et de contexte](context-connections-and-regular-connections-restrictions.md).</span><span class="sxs-lookup"><span data-stu-id="776c6-114">For example, there are certain restrictions on using the context connection, described in [Restrictions on Regular and Context Connections](context-connections-and-regular-connections-restrictions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="776c6-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="776c6-115">See Also</span></span>  
 [<span data-ttu-id="776c6-116">Connexion contextuelle</span><span class="sxs-lookup"><span data-stu-id="776c6-116">Context Connection</span></span>](context-connection.md)  
  
  
