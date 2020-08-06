---
title: Options d’articles pour la réplication transactionnelle | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], transactional replication options
- transactional replication, article options
ms.assetid: 3469b185-0ea5-4690-a71c-717230d886b6
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1cc13a3d11e35ed47eac4ff401fb8b7cb607b32b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610592"
---
# <a name="article-options-for-transactional-replication"></a><span data-ttu-id="a0bde-102">Options d'articles pour la réplication transactionnelle</span><span class="sxs-lookup"><span data-stu-id="a0bde-102">Article Options for Transactional Replication</span></span>
  <span data-ttu-id="a0bde-103">Il existe un certain nombre d'options pour les articles dans les publications transactionnelles.</span><span class="sxs-lookup"><span data-stu-id="a0bde-103">There are a number of options for articles in transactional publications.</span></span> <span data-ttu-id="a0bde-104">Avec la réplication transactionnelle, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="a0bde-104">With transactional replication, you can do the following:</span></span>  
  
-   <span data-ttu-id="a0bde-105">Spécifier comment les changements sont propagés du serveur de publication vers les Abonnés.</span><span class="sxs-lookup"><span data-stu-id="a0bde-105">Specify how changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="a0bde-106">Pour plus d’informations, consultez [Spécifier le mode de propagation des modifications des articles transactionnels](transactional-articles-specify-how-changes-are-propagated.md).</span><span class="sxs-lookup"><span data-stu-id="a0bde-106">For more information, see [Specify How Changes Are Propagated for Transactional Articles](transactional-articles-specify-how-changes-are-propagated.md).</span></span>  
  
-   <span data-ttu-id="a0bde-107">Spécifier que l'exécution d'une procédure stockée doit être répliquée.</span><span class="sxs-lookup"><span data-stu-id="a0bde-107">Specify that the execution of a stored procedure be replicated.</span></span> <span data-ttu-id="a0bde-108">Ceci est particulièrement utile lors de la réplication des résultats de procédures stockées de maintenance qui affectent de gros volumes de données.</span><span class="sxs-lookup"><span data-stu-id="a0bde-108">This is useful in replicating the results of maintenance-oriented stored procedures that affect large amounts of data.</span></span> <span data-ttu-id="a0bde-109">Pour plus d’informations, consultez [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span><span class="sxs-lookup"><span data-stu-id="a0bde-109">For more information, see [Publishing Stored Procedure Execution in Transactional Replication](publishing-stored-procedure-execution-in-transactional-replication.md).</span></span>  
  
-   <span data-ttu-id="a0bde-110">Spécifier les options de schéma, par exemple si les contraintes et déclencheurs sont copiés sur l'Abonné.</span><span class="sxs-lookup"><span data-stu-id="a0bde-110">Specify schema options, such as whether constraints and triggers are copied to the Subscriber.</span></span> <span data-ttu-id="a0bde-111">Pour plus d’informations, consultez [Spécifier des options de schéma](../publish/specify-schema-options.md).</span><span class="sxs-lookup"><span data-stu-id="a0bde-111">For more information, see [Specify Schema Options](../publish/specify-schema-options.md).</span></span>  
  
-   <span data-ttu-id="a0bde-112">Utiliser des filtres de lignes et des filtres de colonnes.</span><span class="sxs-lookup"><span data-stu-id="a0bde-112">Use row filters and column filters.</span></span> <span data-ttu-id="a0bde-113">Le filtrage des articles d'une table vous permet de créer des partitions de données à publier.</span><span class="sxs-lookup"><span data-stu-id="a0bde-113">Filtering table articles enables you to create partitions of data to be published.</span></span> <span data-ttu-id="a0bde-114">Pour plus d’informations, consultez [Filtrer des données publiées](../publish/filter-published-data.md).</span><span class="sxs-lookup"><span data-stu-id="a0bde-114">For more information, see [Filter Published Data](../publish/filter-published-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bde-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a0bde-115">See Also</span></span>  
 [<span data-ttu-id="a0bde-116">Publier des données et des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="a0bde-116">Publish Data and Database Objects</span></span>](../publish/publish-data-and-database-objects.md)  
  
  
