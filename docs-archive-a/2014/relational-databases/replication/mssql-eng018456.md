---
title: MSSQL_ENG018456 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG018456 error
ms.assetid: 3daa8144-d81f-445a-b6c3-4bb3e9fd1526
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b05ca549781215e0c4f247110fee87f6def56f04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702787"
---
# <a name="mssql_eng018456"></a><span data-ttu-id="655ea-102">MSSQL_ENG018456</span><span class="sxs-lookup"><span data-stu-id="655ea-102">MSSQL_ENG018456</span></span>
    
## <a name="message-details"></a><span data-ttu-id="655ea-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="655ea-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="655ea-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="655ea-104">Product Name</span></span>|<span data-ttu-id="655ea-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="655ea-105">SQL Server</span></span>|  
|<span data-ttu-id="655ea-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="655ea-106">Event ID</span></span>|<span data-ttu-id="655ea-107">18456</span><span class="sxs-lookup"><span data-stu-id="655ea-107">18456</span></span>|  
|<span data-ttu-id="655ea-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="655ea-108">Event Source</span></span>|<span data-ttu-id="655ea-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="655ea-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="655ea-110">Composant</span><span class="sxs-lookup"><span data-stu-id="655ea-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="655ea-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="655ea-111">Symbolic Name</span></span>||  
|<span data-ttu-id="655ea-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="655ea-112">Message Text</span></span>|<span data-ttu-id="655ea-113">Échec de la connexion pour l’utilisateur '%.\*ls'.%.\*ls</span><span class="sxs-lookup"><span data-stu-id="655ea-113">Login failed for user '%.\*ls'.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="655ea-114">Explication</span><span class="sxs-lookup"><span data-stu-id="655ea-114">Explanation</span></span>  
 <span data-ttu-id="655ea-115">L'erreur MSSQL_ENG018456 se produit chaque fois qu'une tentative de connexion échoue.</span><span class="sxs-lookup"><span data-stu-id="655ea-115">Error MSSQL_ENG018456 is raised whenever a login attempt fails.</span></span> <span data-ttu-id="655ea-116">Si le message d'erreur inclut le compte **distributor_admin** (Échec de la connexion pour l'utilisateur 'distributor_admin'.), le problème vient d'un compte utilisé par la réplication.</span><span class="sxs-lookup"><span data-stu-id="655ea-116">If the error message includes the account **distributor_admin** (Login failed for user 'distributor_admin'.), the issue is with an account used by replication.</span></span> <span data-ttu-id="655ea-117">La réplication crée un serveur distant, **repl_distributor**, qui permet la communication entre le serveur de distribution et le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="655ea-117">Replication creates a remote server, **repl_distributor**, which allows communication between the Distributor and Publisher.</span></span> <span data-ttu-id="655ea-118">Le nom de connexion **distributor_admin** est associé à ce serveur distant et doit avoir un mot de passe valide.</span><span class="sxs-lookup"><span data-stu-id="655ea-118">The login **distributor_admin** is associated with this remote server and must have a valid password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="655ea-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="655ea-119">User Action</span></span>  
 <span data-ttu-id="655ea-120">Assurez-vous que vous avez spécifié un mot de passe pour ce compte.</span><span class="sxs-lookup"><span data-stu-id="655ea-120">Ensure that you have specified a password for this account.</span></span> <span data-ttu-id="655ea-121">Pour plus d’informations, consultez [Protéger le serveur de distribution](security/secure-the-distributor.md).</span><span class="sxs-lookup"><span data-stu-id="655ea-121">For more information, see [Secure the Distributor](security/secure-the-distributor.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="655ea-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="655ea-122">See Also</span></span>  
 [<span data-ttu-id="655ea-123">Guide de référence des erreurs et des événements &#40;réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="655ea-123">Errors and Events Reference &#40;Replication&#41;</span></span>](errors-and-events-reference-replication.md)  
  
  
