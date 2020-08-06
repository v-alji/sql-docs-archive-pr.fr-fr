---
title: MSSQL_ENG014120 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- MSSQL_ENG014120 error
ms.assetid: 6b169a3b-30da-4981-b998-b52d61811572
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e7f3484d9344a203ca8c44fee6b79605163ea069
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599922"
---
# <a name="mssql_eng014120"></a><span data-ttu-id="613bc-102">MSSQL_ENG014120</span><span class="sxs-lookup"><span data-stu-id="613bc-102">MSSQL_ENG014120</span></span>
    
## <a name="message-details"></a><span data-ttu-id="613bc-103">Détails du message</span><span class="sxs-lookup"><span data-stu-id="613bc-103">Message Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="613bc-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="613bc-104">Product Name</span></span>|<span data-ttu-id="613bc-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="613bc-105">SQL Server</span></span>|  
|<span data-ttu-id="613bc-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="613bc-106">Event ID</span></span>|<span data-ttu-id="613bc-107">14120</span><span class="sxs-lookup"><span data-stu-id="613bc-107">14120</span></span>|  
|<span data-ttu-id="613bc-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="613bc-108">Event Source</span></span>|<span data-ttu-id="613bc-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="613bc-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="613bc-110">Composant</span><span class="sxs-lookup"><span data-stu-id="613bc-110">Component</span></span>|[!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]|  
|<span data-ttu-id="613bc-111">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="613bc-111">Symbolic Name</span></span>||  
|<span data-ttu-id="613bc-112">Texte du message</span><span class="sxs-lookup"><span data-stu-id="613bc-112">Message Text</span></span>|<span data-ttu-id="613bc-113">Impossible de supprimer la base de données de distribution '%s'.</span><span class="sxs-lookup"><span data-stu-id="613bc-113">Could not drop the distribution database '%s'.</span></span> <span data-ttu-id="613bc-114">La base de données de distribution est associée à un éditeur.</span><span class="sxs-lookup"><span data-stu-id="613bc-114">This distributor database is associated with a Publisher.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="613bc-115">Explication</span><span class="sxs-lookup"><span data-stu-id="613bc-115">Explanation</span></span>  
 <span data-ttu-id="613bc-116">La base de données de distribution stocke les métadonnées et les données d'historique pour tous les types de réplications, et les transactions pour la réplication transactionnelle.</span><span class="sxs-lookup"><span data-stu-id="613bc-116">The distribution database stores metadata and history data for all types of replication and transactions for transactional replication.</span></span> <span data-ttu-id="613bc-117">Cette erreur se produit si vous tentez de supprimer une base de données de distribution qui est associée à un ou plusieurs serveurs de publication.</span><span class="sxs-lookup"><span data-stu-id="613bc-117">This error occurs if you attempt to drop a distribution database that is associated with one or more Publishers.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="613bc-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="613bc-118">User Action</span></span>  
 <span data-ttu-id="613bc-119">Pour supprimer une base de données de distribution, vous devez d'abord supprimer l'association entre le serveur de distribution et le serveur de publication.</span><span class="sxs-lookup"><span data-stu-id="613bc-119">To drop a distribution database you must first drop the association between the Distributor and the Publisher.</span></span> <span data-ttu-id="613bc-120">Pour plus d’informations, consultez [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="613bc-120">For more information, see [sp_dropdistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-dropdistpublisher-transact-sql).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="613bc-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="613bc-121">See Also</span></span>  
 <span data-ttu-id="613bc-122">[Guide de référence des erreurs et des événements &#40;réplication&#41;](errors-and-events-reference-replication.md) </span><span class="sxs-lookup"><span data-stu-id="613bc-122">[Errors and Events Reference &#40;Replication&#41;](errors-and-events-reference-replication.md) </span></span>  
 [<span data-ttu-id="613bc-123">Configurer la distribution</span><span class="sxs-lookup"><span data-stu-id="613bc-123">Configure Distribution</span></span>](configure-distribution.md)  
  
  
