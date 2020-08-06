---
title: Restrictions sur les connexions régulières et de contexte | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611121"
---
# <a name="restrictions-on-regular-and-context-connections"></a><span data-ttu-id="b7a4a-102">Restrictions applicables aux connexions normales et contextuelles</span><span class="sxs-lookup"><span data-stu-id="b7a4a-102">Restrictions on Regular and Context Connections</span></span>
  <span data-ttu-id="b7a4a-103">Cette rubrique décrit les restrictions associées au code qui s’exécute dans le [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] processus via le contexte et les connexions normales.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-103">This topic discusses the restrictions associated with code executing in the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] process through context and regular connections.</span></span>  
  
## <a name="restrictions-on-context-connections"></a><span data-ttu-id="b7a4a-104">Restrictions applicables aux connexions contextuelles</span><span class="sxs-lookup"><span data-stu-id="b7a4a-104">Restrictions on Context Connections</span></span>  
 <span data-ttu-id="b7a4a-105">Lorsque vous développez votre application, prenez en considération les restrictions suivantes qui s'appliquent aux connexions contextuelles :</span><span class="sxs-lookup"><span data-stu-id="b7a4a-105">When developing your application, take into account the following restrictions that apply to context connections:</span></span>  
  
-   <span data-ttu-id="b7a4a-106">Vous ne pouvez avoir qu'une seule connexion contextuelle ouverte à tout moment pour une connexion donnée.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-106">You can have only one context connection open at a given time for a given connection.</span></span> <span data-ttu-id="b7a4a-107">Si plusieurs instructions s'exécutent simultanément dans des connexions séparées, chacune d'elles peut obtenir sa propre connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-107">If you have multiple statements running concurrently in separate connections, each one of them can get their own context connection.</span></span> <span data-ttu-id="b7a4a-108">La restriction n'affecte pas les demandes simultanées à partir de connexions différentes ; elle affecte seulement une demande donnée sur une connexion donnée.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-108">The restriction does not affect concurrent requests from different connections; it only affects a given request on a given connection.</span></span>  
  
-   <span data-ttu-id="b7a4a-109">Multiple Active Result Sets (MARS) n'est pas pris en charge dans une connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-109">Multiple Active Result Sets (MARS) is not supported in a context connection.</span></span>  
  
-   <span data-ttu-id="b7a4a-110">La classe `SqlBulkCopy` ne fonctionne pas dans une connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-110">The `SqlBulkCopy` class does not operate in a context connection.</span></span>  
  
-   <span data-ttu-id="b7a4a-111">Le traitement par lot des mises à jour dans une connexion contextuelle n'est pas pris en charge</span><span class="sxs-lookup"><span data-stu-id="b7a4a-111">Update batching in a context connection is not supported</span></span>  
  
-   <span data-ttu-id="b7a4a-112">`SqlNotificationRequest` ne peut pas être utilisé avec les commandes qui s'exécutent contre une connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-112">`SqlNotificationRequest` cannot be used with commands that execute against a context connection.</span></span>  
  
-   <span data-ttu-id="b7a4a-113">L'annulation des commandes qui s'exécutent contre la connexion contextuelle n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-113">Canceling commands that are running against the context connection is not supported.</span></span> <span data-ttu-id="b7a4a-114">La méthode `SqlCommand.Cancel` ignore la demande silencieusement.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-114">The `SqlCommand.Cancel` method silently ignores the request.</span></span>  
  
-   <span data-ttu-id="b7a4a-115">Aucun autre mot clé de chaîne de connexion ne peut être utilisé lorsque vous utilisez « context connection=true ».</span><span class="sxs-lookup"><span data-stu-id="b7a4a-115">No other connection string keywords can be used when you use "context connection=true".</span></span>  
  
-   <span data-ttu-id="b7a4a-116">La propriété `SqlConnection.DataSource` retourne NULL si la chaîne de connexion pour le `SqlConnection` est « context connection=true », au lieu du nom de l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7a4a-116">The `SqlConnection.DataSource` property returns null if the connection string for the `SqlConnection` is "context connection=true", instead of the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b7a4a-117">La définition de la propriété `SqlCommand.CommandTimeout` n'a aucun effet lorsque la commande est exécutée contre une connexion contextuelle.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-117">Setting the `SqlCommand.CommandTimeout` property has no effect when the command is executed against a context connection.</span></span>  
  
## <a name="restrictions-on-regular-connections"></a><span data-ttu-id="b7a4a-118">Restrictions applicables aux connexions normales</span><span class="sxs-lookup"><span data-stu-id="b7a4a-118">Restrictions on Regular Connections</span></span>  
 <span data-ttu-id="b7a4a-119">Lorsque vous développez votre application, prenez en considération les restrictions suivantes qui s'appliquent aux connexions normales :</span><span class="sxs-lookup"><span data-stu-id="b7a4a-119">When developing your application, take into account the following restrictions that apply to regular connections:</span></span>  
  
-   <span data-ttu-id="b7a4a-120">L'exécution de commande asynchrone contre des serveurs internes n'est pas prise en charge.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-120">Asynchronous command execution against internal servers is not supported.</span></span> <span data-ttu-id="b7a4a-121">L'inclusion de « async=true » dans la chaîne de connexion d'une commande, suivie de l'exécution de cette commande, lève l'exception `System.NotSupportedException`.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-121">Including "async=true" in the connection string of a command, and then executing the command, results in `System.NotSupportedException` being thrown.</span></span> <span data-ttu-id="b7a4a-122">Le message suivant apparaît : « Le traitement asynchrone n'est pas pris en charge en cas d'exécution à l'intérieur du processus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ».</span><span class="sxs-lookup"><span data-stu-id="b7a4a-122">This message appears: "Asynchronous processing is not supported when running inside the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process."</span></span>  
  
-   <span data-ttu-id="b7a4a-123">L'objet `SqlDependency` n'est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="b7a4a-123">`SqlDependency` object is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a4a-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7a4a-124">See Also</span></span>  
 [<span data-ttu-id="b7a4a-125">Connexion contextuelle</span><span class="sxs-lookup"><span data-stu-id="b7a4a-125">Context Connection</span></span>](context-connection.md)  
  
  
