---
title: MSSQL_ENG020596 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG020596 error
ms.assetid: fa33627c-2e99-4be3-9424-52ab83446e07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b1c61f3683442e0d474ff36a65c89446dbd7bd1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614536"
---
# <a name="mssql_eng020596"></a><span data-ttu-id="83d8c-102">MSSQL_ENG020596</span><span class="sxs-lookup"><span data-stu-id="83d8c-102">MSSQL_ENG020596</span></span>
    
## <a name="message-details"></a><span data-ttu-id="83d8c-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="83d8c-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83d8c-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="83d8c-104">Product Name</span></span>|<span data-ttu-id="83d8c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="83d8c-105">SQL Server</span></span>|  
|<span data-ttu-id="83d8c-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="83d8c-106">Event ID</span></span>|<span data-ttu-id="83d8c-107">20596</span><span class="sxs-lookup"><span data-stu-id="83d8c-107">20596</span></span>|  
|<span data-ttu-id="83d8c-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="83d8c-108">Event Source</span></span>|<span data-ttu-id="83d8c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="83d8c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="83d8c-110">Composant</span><span class="sxs-lookup"><span data-stu-id="83d8c-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="83d8c-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="83d8c-111">Symbolic Name</span></span>||  
|<span data-ttu-id="83d8c-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="83d8c-112">Message Text</span></span>|<span data-ttu-id="83d8c-113">Seul '%1!' ou les membres de db_owner peuvent supprimer l'Agent anonyme.</span><span class="sxs-lookup"><span data-stu-id="83d8c-113">Only '%s' or members of db_owner can drop the anonymous agent.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="83d8c-114">Explication</span><span class="sxs-lookup"><span data-stu-id="83d8c-114">Explanation</span></span>  
 <span data-ttu-id="83d8c-115">Vous ne disposez pas des autorisations suffisantes pour supprimer l'agent pour l'abonnement anonyme.</span><span class="sxs-lookup"><span data-stu-id="83d8c-115">You do not have sufficient permissions to drop the agent for the anonymous subscription.</span></span> <span data-ttu-id="83d8c-116">Le nom de connexion utilisé lors de l’appel de [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) doit être un membre du rôle de serveur fixe **sysadmin** sur le serveur de distribution ou du rôle de base de données fixe **db_owner** dans la base de données de distribution, ou bien l’utilisateur doit être celui qui a initié la première exécution de l’agent.</span><span class="sxs-lookup"><span data-stu-id="83d8c-116">The login used when calling [sp_dropanonymousagent &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropanonymousagent-transact-sql) must be a member of the **sysadmin** fixed server role at the Distributor or **db_owner** fixed database role in the distribution database, or the user must be the one that initiated the first run of the agent.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="83d8c-117">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="83d8c-117">User Action</span></span>  
 <span data-ttu-id="83d8c-118">Connectez-vous avec les informations d'identification appropriées et exécutez **sp_dropanonymousagent**.</span><span class="sxs-lookup"><span data-stu-id="83d8c-118">Login with the appropriate credentials, and execute **sp_dropanonymousagent**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d8c-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83d8c-119">See Also</span></span>  
 [<span data-ttu-id="83d8c-120">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="83d8c-120">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
