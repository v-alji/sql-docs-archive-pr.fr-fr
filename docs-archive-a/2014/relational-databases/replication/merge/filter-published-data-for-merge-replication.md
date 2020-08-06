---
title: Filtrer des données publiées en vue de la réplication de fusion | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication [SQL Server replication], filtering published data
- replication [SQL Server], filtering published data
ms.assetid: 46c5023d-7a3b-4455-becc-e159fcb5d6c4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ad9ad45a64f57a6bef8255373180ea943af9893f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599950"
---
# <a name="filter-published-data-for-merge-replication"></a><span data-ttu-id="60e16-102">Filtrer des données publiées en vue de la réplication de fusion</span><span class="sxs-lookup"><span data-stu-id="60e16-102">Filter Published Data for Merge Replication</span></span>
  <span data-ttu-id="60e16-103">Outre les filtres de lignes statiques et les filtres de colonnes que vous pouvez définir dans les autres types de réplications, la réplication de fusion vous offre des filtres de lignes paramétrés et des filtres de jointure.</span><span class="sxs-lookup"><span data-stu-id="60e16-103">In addition to the static row filters and column filters you can define with other types of replication, merge replication offers parameterized row filters and join filters.</span></span> <span data-ttu-id="60e16-104">Pour plus d’informations sur les filtres de lignes statiques et les filtres de colonnes, consultez [Filtrer les données publiées](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="60e16-104">For more information about static row filters and column filters, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
 <span data-ttu-id="60e16-105">La réplication de fusion est utilisée dans de nombreuses applications qui prennent en charge les utilisateurs mobiles ; ces applications gèrent en général un grand nombre d'abonnements, chacun recevant un jeu de données spécifique.</span><span class="sxs-lookup"><span data-stu-id="60e16-105">Merge replication is used in many applications that support mobile users; these applications usually have a large number of subscriptions with each subscription receiving a unique data set.</span></span> <span data-ttu-id="60e16-106">Les filtres paramétrés combinés aux filtres de jointure permettent à un administrateur de configurer une publication (ou tout au plus un petit nombre de publications) et néanmoins de fournir aux utilisateurs des jeux de données différents, ce qui réduit la charge de gestion que nécessiterait la création de nombreuses publications.</span><span class="sxs-lookup"><span data-stu-id="60e16-106">Parameterized filters combined with join filters allow an administrator to set up one publication (or at most a small number of publications) and yet provide different data sets to users, reducing the management overhead introduced by creating multiple publications.</span></span>  
  
-   <span data-ttu-id="60e16-107">Les filtres paramétrés permettent d'envoyer des partitions de données différentes à des Abonnés différents sans nécessiter la création de publications multiples.</span><span class="sxs-lookup"><span data-stu-id="60e16-107">Parameterized filters allow different partitions of data to be sent to different Subscribers without requiring multiple publications to be created.</span></span> <span data-ttu-id="60e16-108">Par exemple, une table peut être filtrée de telle sorte que les données concernant un représentant donné ne soient répliquées que vers ce représentant.</span><span class="sxs-lookup"><span data-stu-id="60e16-108">For example, a table can be filtered so that data for a given sales representative is replicated only to that representative.</span></span> <span data-ttu-id="60e16-109">Les filtres paramétrés proposent diverses options qui vous permettent de personnaliser le filtrage afin d'optimiser les performances et de mieux répondre à vos besoins en matière de données et d'applications.</span><span class="sxs-lookup"><span data-stu-id="60e16-109">Parameterized filters have a variety of options that allow you to tailor filtering to optimize performance and best match your data and application requirements.</span></span> <span data-ttu-id="60e16-110">Pour plus d'informations, voir [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span><span class="sxs-lookup"><span data-stu-id="60e16-110">For more information, see [Parameterized Row Filters](parameterized-filters-parameterized-row-filters.md).</span></span>  
  
-   <span data-ttu-id="60e16-111">Les filtres de jointure sont en général associés aux filtres paramétrés pour étendre le filtrage aux tables connexes (ils peuvent aussi être associés aux filtres statiques).</span><span class="sxs-lookup"><span data-stu-id="60e16-111">Join filters are typically used in conjunction with parameterized filters to extend filtering to related tables (they can also be used in conjunction with static filters).</span></span> <span data-ttu-id="60e16-112">Par exemple, un représentant détient en général des données dans d'autres tables, comme les tables de clients et de commandes.</span><span class="sxs-lookup"><span data-stu-id="60e16-112">For example, the sales representative typically has data in other tables such as customer and order tables.</span></span> <span data-ttu-id="60e16-113">Ces données peuvent être filtrées pour que ce représentant ne reçoive que les données relatives à ses clients et aux commandes de ses clients.</span><span class="sxs-lookup"><span data-stu-id="60e16-113">This data can be filtered so the sales representative receives only the data on her customers and her customers' orders.</span></span> <span data-ttu-id="60e16-114">Pour plus d’informations, voir [Join Filters](join-filters.md).</span><span class="sxs-lookup"><span data-stu-id="60e16-114">For more information, see [Join Filters](join-filters.md).</span></span>  
  
 <span data-ttu-id="60e16-115">Aucun filtre ne doit inclure le `rowguidcol` utilisé par la réplication pour identifier les lignes.</span><span class="sxs-lookup"><span data-stu-id="60e16-115">A filter must not include the `rowguidcol` used by replication to identify rows.</span></span> <span data-ttu-id="60e16-116">Par défaut, il s'agit de la colonne ajoutée lorsque vous avez configuré la réplication de fusion et qui a pour nom **rowguid**.</span><span class="sxs-lookup"><span data-stu-id="60e16-116">By default this is the column added at the time you set up merge replication and is named **rowguid**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e16-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60e16-117">See Also</span></span>  
 [<span data-ttu-id="60e16-118">Publier des données et des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="60e16-118">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
