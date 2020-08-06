---
title: MSSQLSERVER_15517 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15517 (Database Engine error)
ms.assetid: f94287f5-129f-4c52-9d34-62b996088001
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b8e66e211faf03e1457953d0292e711cde1798ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612901"
---
# <a name="mssqlserver_15517"></a><span data-ttu-id="e77e1-102">MSSQLSERVER_15517</span><span class="sxs-lookup"><span data-stu-id="e77e1-102">MSSQLSERVER_15517</span></span>
    
## <a name="details"></a><span data-ttu-id="e77e1-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e77e1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e77e1-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e77e1-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="e77e1-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e77e1-105">Event ID</span></span>|<span data-ttu-id="e77e1-106">15517</span><span class="sxs-lookup"><span data-stu-id="e77e1-106">15517</span></span>|  
|<span data-ttu-id="e77e1-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e77e1-107">Event Source</span></span>|<span data-ttu-id="e77e1-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e77e1-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e77e1-109">Composant</span><span class="sxs-lookup"><span data-stu-id="e77e1-109">Component</span></span>|<span data-ttu-id="e77e1-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e77e1-110">SQLEngine</span></span>|  
|<span data-ttu-id="e77e1-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e77e1-111">Symbolic Name</span></span>|<span data-ttu-id="e77e1-112">SEC_CANNOTEXECUTEASUSER</span><span class="sxs-lookup"><span data-stu-id="e77e1-112">SEC_CANNOTEXECUTEASUSER</span></span>|  
|<span data-ttu-id="e77e1-113">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e77e1-113">Message Text</span></span>|<span data-ttu-id="e77e1-114">Exécution impossible en tant que principal de la base de données car le principal «*principal*» n’existe pas, ce type de principal n’autorise pas l’emprunt d’identité ou vous n’avez pas l’autorisation requise.</span><span class="sxs-lookup"><span data-stu-id="e77e1-114">Cannot execute as the database principal because the principal "*principal*" does not exist, this type of principal cannot be impersonated, or you do not have permission.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="e77e1-115">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e77e1-115">User Action</span></span>  
 <span data-ttu-id="e77e1-116">Utilisez le nom d'un principal existant ou obtenez l'autorisation IMPERSONATE sur ce principal.</span><span class="sxs-lookup"><span data-stu-id="e77e1-116">Use the name of an existing principal or get the IMPERSONATE permission on that principal.</span></span>  
  
 <span data-ttu-id="e77e1-117">15517 peut également se produire après un attachement et une restauration de base de données par quelqu'un d'autre que le propriétaire d'origine de la base de données.</span><span class="sxs-lookup"><span data-stu-id="e77e1-117">15517 can also occur after performing an attach and restore of a database by someone other than the original database owner.</span></span> <span data-ttu-id="e77e1-118">Pour résoudre cette erreur, remplacez le db_owner par une connexion sur votre serveur, en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e77e1-118">To resolve this error, change the db_owner to a login on your server, by running the following command:</span></span>  
  
```  
ALTER AUTHORIZATION ON DATABASE:: DBName TO [NewLogin]  
```  
  
## <a name="see-also"></a><span data-ttu-id="e77e1-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e77e1-119">See Also</span></span>  
 [<span data-ttu-id="e77e1-120">OLTP en mémoire &#40;Optimisation en mémoire&#41;</span><span class="sxs-lookup"><span data-stu-id="e77e1-120">In-Memory OLTP &#40;In-Memory Optimization&#41;</span></span>](../in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
  
