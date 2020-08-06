---
title: Configuration du client Distributed Replay | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: ccf03e32-6bd9-43c0-b9b6-9fe0d9163339
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 53124029483c25ed7894b279283e1de02c647350
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614360"
---
# <a name="distributed-replay-client-configuration"></a><span data-ttu-id="db0df-102">Configuration de Distributed Replay Client</span><span class="sxs-lookup"><span data-stu-id="db0df-102">Distributed Replay Client Configuration</span></span>
  <span data-ttu-id="db0df-103">Utilisez la page **Configuration de Distributed Replay Client** de l’Assistant Installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour spécifier les utilisateurs auxquels vous voulez accorder des autorisations administratives sur le service Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="db0df-103">Use the **Distributed Replay Client Configuration** page of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the users you want to grant administrative permissions to for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="db0df-104">Les utilisateurs qui disposent d'autorisations administratives ont un accès illimité au service Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="db0df-104">Users that have administrative permissions will have unlimited access to the Distributed Replay client service.</span></span>  
  
## <a name="options"></a><span data-ttu-id="db0df-105">Options</span><span class="sxs-lookup"><span data-stu-id="db0df-105">Options</span></span>  
 <span data-ttu-id="db0df-106">**Nom du contrôleur**</span><span class="sxs-lookup"><span data-stu-id="db0df-106">**Controller Name**</span></span>  
 <span data-ttu-id="db0df-107">Il s’agit d’un paramètre facultatif, et la valeur par défaut est \<*blank*> .</span><span class="sxs-lookup"><span data-stu-id="db0df-107">This is an optional parameter, and the default value is \<*blank*>.</span></span>  
  
 <span data-ttu-id="db0df-108">Entrez le nom du contrôleur avec lequel l'ordinateur client communiquera pour le service Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="db0df-108">Enter the name of the controller that the client computer will communicate with for the Distributed Replay client service.</span></span> <span data-ttu-id="db0df-109">Notez les points suivants :</span><span class="sxs-lookup"><span data-stu-id="db0df-109">Note the following:</span></span>  
  
-   <span data-ttu-id="db0df-110">Le nom doit être un nom de domaine complet (FQDN).</span><span class="sxs-lookup"><span data-stu-id="db0df-110">The name must be a fully qualified domain name (FQDN).</span></span> <span data-ttu-id="db0df-111">Par exemple, un hôte appelé server1 dans la hiérarchie de produits au sein de Microsoft peut avoir un nom de domaine complet server1.products.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="db0df-111">For example, a host called server1 in the products hierarchy at Microsoft may have an FQDN of server1.products.microsoft.com.</span></span>  
  
-   <span data-ttu-id="db0df-112">Si vous avez déjà configuré un contrôleur, entrez son nom lors de la configuration de chaque client.</span><span class="sxs-lookup"><span data-stu-id="db0df-112">If you have already set up a controller, enter the name of the controller while configuring each client.</span></span>  
  
-   <span data-ttu-id="db0df-113">Si vous n'avez pas encore configuré de contrôleur, vous n'êtes pas obligé de fournir le nom du contrôleur.</span><span class="sxs-lookup"><span data-stu-id="db0df-113">If you have net yet set up a controller, you can leave the controller name blank.</span></span> <span data-ttu-id="db0df-114">Toutefois, vous devez entrer manuellement le nom du contrôleur dans le fichier de **configuration du client** .</span><span class="sxs-lookup"><span data-stu-id="db0df-114">However, you must manually enter the controller name in the **client configuration** file.</span></span>  
  
 <span data-ttu-id="db0df-115">**Répertoire de travail**</span><span class="sxs-lookup"><span data-stu-id="db0df-115">**Working Directory**</span></span>  
 <span data-ttu-id="db0df-116">Spécifiez le répertoire de travail du service Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="db0df-116">Specify the working directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="db0df-117">Le répertoire de travail par défaut est \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span><span class="sxs-lookup"><span data-stu-id="db0df-117">The default working directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\WorkingDir\\.</span></span>  
  
 <span data-ttu-id="db0df-118">**Répertoire des résultats**</span><span class="sxs-lookup"><span data-stu-id="db0df-118">**Result Directory**</span></span>  
 <span data-ttu-id="db0df-119">Spécifiez le répertoire des résultats du service Distributed Replay Client.</span><span class="sxs-lookup"><span data-stu-id="db0df-119">Specify the result directory for the Distributed Replay client service.</span></span>  
  
 <span data-ttu-id="db0df-120">Le répertoire des résultats par défaut est \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span><span class="sxs-lookup"><span data-stu-id="db0df-120">The default result directory is \<*drive letter*>:\Program Files\\[!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\DReplayClient\ResultDir\\.</span></span>  
  
  
