---
title: MSSQL_ENG014121 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014121 error
ms.assetid: c8595854-cce1-4566-ad64-d565555caded
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 04d4cbdd2197745d2d795814d88c4f7bc28eb90e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599923"
---
# <a name="mssql_eng014121"></a><span data-ttu-id="efaf0-102">MSSQL_ENG014121</span><span class="sxs-lookup"><span data-stu-id="efaf0-102">MSSQL_ENG014121</span></span>
    
## <a name="message-details"></a><span data-ttu-id="efaf0-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="efaf0-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efaf0-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="efaf0-104">Product Name</span></span>|<span data-ttu-id="efaf0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="efaf0-105">SQL Server</span></span>|  
|<span data-ttu-id="efaf0-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="efaf0-106">Event ID</span></span>|<span data-ttu-id="efaf0-107">14121</span><span class="sxs-lookup"><span data-stu-id="efaf0-107">14121</span></span>|  
|<span data-ttu-id="efaf0-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="efaf0-108">Event Source</span></span>|<span data-ttu-id="efaf0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="efaf0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="efaf0-110">Composant</span><span class="sxs-lookup"><span data-stu-id="efaf0-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="efaf0-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="efaf0-111">Symbolic Name</span></span>||  
|<span data-ttu-id="efaf0-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="efaf0-112">Message Text</span></span>|<span data-ttu-id="efaf0-113">Impossible de supprimer le distributeur '%s'.</span><span class="sxs-lookup"><span data-stu-id="efaf0-113">Could not drop the Distributor '%s'.</span></span> <span data-ttu-id="efaf0-114">Des bases de données de distribution sont associées à ce distributeur.</span><span class="sxs-lookup"><span data-stu-id="efaf0-114">This Distributor has associated distribution databases.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="efaf0-115">Explication</span><span class="sxs-lookup"><span data-stu-id="efaf0-115">Explanation</span></span>  
 <span data-ttu-id="efaf0-116">Une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est configurée en tant que serveur de distribution ne peut pas être supprimée du rôle Serveur de distribution car il y a des bases de données de distribution associées à l'instance.</span><span class="sxs-lookup"><span data-stu-id="efaf0-116">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is configured as a Distributor cannot be removed from the role of Distributor because there are distribution databases associated with the instance.</span></span> <span data-ttu-id="efaf0-117">Cette erreur se produit si vous tentez de supprimer une base de données de distribution qui est associée à un ou plusieurs serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="efaf0-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="efaf0-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="efaf0-118">User Action</span></span>  
 <span data-ttu-id="efaf0-119">Pour trouver les noms des serveurs de publication et des bases de données de distribution associées à ce serveur de distribution, exécutez [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) à partir d’une base de données sur le serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="efaf0-119">To find the names of any Publishers and distribution databases associated with this Distributor, execute [sp_helpdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-helpdistpublisher-transact-sql) from any database on the Distributor.</span></span>  
  
 <span data-ttu-id="efaf0-120">Exécutez [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) pour toutes les bases de données de distribution associées à ce serveur de distribution.</span><span class="sxs-lookup"><span data-stu-id="efaf0-120">Execute [sp_dropdistributiondb &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistributiondb-transact-sql) for any distribution databases associated with this Distributor.</span></span> <span data-ttu-id="efaf0-121">Quand toutes les associations de base de données de distribution sont supprimées, vous pouvez désactiver la distribution.</span><span class="sxs-lookup"><span data-stu-id="efaf0-121">After all distribution database associations are removed, you can disable distribution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efaf0-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="efaf0-122">See Also</span></span>  
 <span data-ttu-id="efaf0-123">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="efaf0-123">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="efaf0-124">Configurer la distribution</span><span class="sxs-lookup"><span data-stu-id="efaf0-124">Configure Distribution</span></span>](configure-distribution.md)  
  
  
