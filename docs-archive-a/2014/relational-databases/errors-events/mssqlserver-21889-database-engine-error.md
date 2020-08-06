---
title: MSSQLSERVER_21889 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 21889 (Database Engine error)
ms.assetid: ae199540-7986-4cc2-b782-cd22793236d3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c152a542550d7b81af880545f526037baeb4644e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702928"
---
# <a name="mssqlserver_21889"></a><span data-ttu-id="25bcc-102">MSSQLSERVER_21889</span><span class="sxs-lookup"><span data-stu-id="25bcc-102">MSSQLSERVER_21889</span></span>
    
## <a name="details"></a><span data-ttu-id="25bcc-103">Détails</span><span class="sxs-lookup"><span data-stu-id="25bcc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25bcc-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="25bcc-104">Product Name</span></span>|<span data-ttu-id="25bcc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="25bcc-105">SQL Server</span></span>|  
|<span data-ttu-id="25bcc-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="25bcc-106">Event ID</span></span>|<span data-ttu-id="25bcc-107">21889</span><span class="sxs-lookup"><span data-stu-id="25bcc-107">21889</span></span>|  
|<span data-ttu-id="25bcc-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="25bcc-108">Event Source</span></span>|<span data-ttu-id="25bcc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="25bcc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="25bcc-110">Composant</span><span class="sxs-lookup"><span data-stu-id="25bcc-110">Component</span></span>|<span data-ttu-id="25bcc-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="25bcc-111">SQLEngine</span></span>|  
|<span data-ttu-id="25bcc-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="25bcc-112">Symbolic Name</span></span>|<span data-ttu-id="25bcc-113">SQLErrorNum21889</span><span class="sxs-lookup"><span data-stu-id="25bcc-113">SQLErrorNum21889</span></span>|  
|<span data-ttu-id="25bcc-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="25bcc-114">Message Text</span></span>|<span data-ttu-id="25bcc-115">L'instance '%s' de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas un serveur de publication de réplication.</span><span class="sxs-lookup"><span data-stu-id="25bcc-115">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' is not a replication publisher.</span></span> <span data-ttu-id="25bcc-116">Exécutez `sp_adddistributor` sur l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] '%s' avec le serveur de distribution '%s' afin de permettre à l'instance d'héberger la base de données de publication '%s'.</span><span class="sxs-lookup"><span data-stu-id="25bcc-116">Run `sp_adddistributor` on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance '%s' with distributor '%s' in order to enable the instance to host the publishing database '%s'.</span></span> <span data-ttu-id="25bcc-117">Veillez à spécifier la même connexion et mot de passe que ceux utilisés pour le serveur de publication d'origine.</span><span class="sxs-lookup"><span data-stu-id="25bcc-117">Make certain to specify the same login and password as that used for the original publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="25bcc-118">Explication</span><span class="sxs-lookup"><span data-stu-id="25bcc-118">Explanation</span></span>  
 <span data-ttu-id="25bcc-119">Afin d'héberger la base de données du serveur de publication, l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit être un serveur de publication de réplication.</span><span class="sxs-lookup"><span data-stu-id="25bcc-119">In order to host the publisher database, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be a replication publisher.</span></span> <span data-ttu-id="25bcc-120">`sp_validate_redirected_publisher` appelle `sp_helpdistributor` sur le serveur distant pour déterminer si le serveur est un serveur de publication de réplication.</span><span class="sxs-lookup"><span data-stu-id="25bcc-120">`sp_validate_redirected_publisher` calls `sp_helpdistributor` at the remote server to determine whether the server is a replication publisher.</span></span> <span data-ttu-id="25bcc-121">Cette erreur est retournée lorsque l'exécution de la procédure stockée `sp_helpdistributor` indique que l'instance cible de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas un serveur de publication de réplication.</span><span class="sxs-lookup"><span data-stu-id="25bcc-121">This error is returned when execution of the stored procedure `sp_helpdistributor` indicates that the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not a replication publisher.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="25bcc-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="25bcc-122">User Action</span></span>  
 <span data-ttu-id="25bcc-123">Exécutez `sp_adddistributor` dans l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui héberge la base de données du serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="25bcc-123">Execute `sp_adddistributor` at the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the publisher database.</span></span> <span data-ttu-id="25bcc-124">Lors de l'exécution de `sp_adddistributor`, spécifiez le serveur de distribution correct.</span><span class="sxs-lookup"><span data-stu-id="25bcc-124">When running `sp_adddistributor`, specify the correct distributor.</span></span> <span data-ttu-id="25bcc-125">Utilisez la même valeur pour le *@password* paramètre que celle utilisée lors de la `sp_adddistributor` première exécution sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="25bcc-125">Use the same value for the *@password* parameter as that used when `sp_adddistributor` was initially run at the distributor.</span></span>  
  
  
