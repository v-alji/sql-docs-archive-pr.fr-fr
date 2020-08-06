---
title: MSSQLSERVER_1462 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1462 (Database Engine error)
ms.assetid: 680e9c1c-a9d6-4765-b601-956d0a83324c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 704b847bde2d7b4da9da91b4b24bfe2b9e2afa07
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612903"
---
# <a name="mssqlserver_1462"></a><span data-ttu-id="985da-102">MSSQLSERVER_1462</span><span class="sxs-lookup"><span data-stu-id="985da-102">MSSQLSERVER_1462</span></span>
    
## <a name="details"></a><span data-ttu-id="985da-103">Détails</span><span class="sxs-lookup"><span data-stu-id="985da-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="985da-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="985da-104">Product Name</span></span>|<span data-ttu-id="985da-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="985da-105">SQL Server</span></span>|  
|<span data-ttu-id="985da-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="985da-106">Event ID</span></span>|<span data-ttu-id="985da-107">1462</span><span class="sxs-lookup"><span data-stu-id="985da-107">1462</span></span>|  
|<span data-ttu-id="985da-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="985da-108">Event Source</span></span>|<span data-ttu-id="985da-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="985da-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="985da-110">Composant</span><span class="sxs-lookup"><span data-stu-id="985da-110">Component</span></span>|<span data-ttu-id="985da-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="985da-111">SQLEngine</span></span>|  
|<span data-ttu-id="985da-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="985da-112">Symbolic Name</span></span>|<span data-ttu-id="985da-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span><span class="sxs-lookup"><span data-stu-id="985da-113">DBM_DISABLED_DUE_TO_FAILED_REDO</span></span>|  
|<span data-ttu-id="985da-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="985da-114">Message Text</span></span>|<span data-ttu-id="985da-115">La mise en miroir de bases de données est désactivée en raison de l'échec du rétablissement d'une opération précédente.</span><span class="sxs-lookup"><span data-stu-id="985da-115">Database mirroring is disabled due to a failed redo operation.</span></span> <span data-ttu-id="985da-116">Impossible de reprendre.</span><span class="sxs-lookup"><span data-stu-id="985da-116">Unable to resume.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="985da-117">Explication</span><span class="sxs-lookup"><span data-stu-id="985da-117">Explanation</span></span>  
 <span data-ttu-id="985da-118">La mise en miroir de bases de données n'a pas pu rétablir un enregistrement de journal sur l'instance miroir.</span><span class="sxs-lookup"><span data-stu-id="985da-118">Database mirroring failed to redo a log record on the mirror.</span></span>  
  
### <a name="possible-causes"></a><span data-ttu-id="985da-119">Causes possibles</span><span class="sxs-lookup"><span data-stu-id="985da-119">Possible Causes</span></span>  
 <span data-ttu-id="985da-120">La cause la plus probable est qu'une opération d'ajout de fichier a été effectuée sur la base de données principale, mais qu'elle a ensuite échoué sur la base de données miroir car les noms de fichiers ou les structures de répertoires ne sont pas les mêmes sur le serveur principal et le serveur miroir.</span><span class="sxs-lookup"><span data-stu-id="985da-120">The most likely cause is that an add-file operation completed on the principal database but then failed on the mirror database because file names or directory structures differ on the principal server and mirror server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="985da-121">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="985da-121">User Action</span></span>  
 <span data-ttu-id="985da-122">Consultez le journal des erreurs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour connaître la cause de cette erreur.</span><span class="sxs-lookup"><span data-stu-id="985da-122">Look in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log for the cause of this error.</span></span> <span data-ttu-id="985da-123">Essayez de résoudre le problème et de reprendre la mise en miroir de la base de données.</span><span class="sxs-lookup"><span data-stu-id="985da-123">Try to resolve the cause and resume mirroring on the database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="985da-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="985da-124">See Also</span></span>  
 [<span data-ttu-id="985da-125">Résoudre des problèmes de configuration de mise en miroir de bases de données &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="985da-125">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](../../database-engine/database-mirroring/troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
