---
title: Gérer les modifications des vues de source de données et des sources de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- modifying data sources
- modifying data source views
- data source views [Analysis Services], schema updates
- data sources [Analysis Services], schema updates
ms.assetid: 928c9f63-365a-43fd-9bbd-78828cc7e54d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 0f558ce6aaf9e57576d5773322352d33b81a3392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698640"
---
# <a name="manage-changes-to-data-source-views-and-data-sources"></a><span data-ttu-id="09ef8-102">Gérer des modifications dans les vues de source de données et les sources de données</span><span class="sxs-lookup"><span data-stu-id="09ef8-102">Manage Changes to Data Source Views and Data Sources</span></span>
  <span data-ttu-id="09ef8-103">Lorsque l'Assistant Génération de schéma est exécuté à nouveau, il réutilise la même source de données et la même vue de source de données que lors de la génération initiale.</span><span class="sxs-lookup"><span data-stu-id="09ef8-103">When the Schema Generation Wizard is rerun, it reuses the same data source and data source view that it used for the original generation.</span></span> <span data-ttu-id="09ef8-104">Si vous ajoutez une source de données ou une vue de source de données, l'Assistant ne l'utilise pas.</span><span class="sxs-lookup"><span data-stu-id="09ef8-104">If you add a data source or a data source view, the wizard does not use it.</span></span> <span data-ttu-id="09ef8-105">Si vous supprimez la source de données ou la vue de source de données d'origine après la génération initiale, vous devez exécuter l'Assistant depuis le début.</span><span class="sxs-lookup"><span data-stu-id="09ef8-105">If you delete the original data source or data source view after the initial generation, you must run the wizard from the beginning.</span></span> <span data-ttu-id="09ef8-106">Toutes les options précédemment définies dans l'Assistant sont également supprimées.</span><span class="sxs-lookup"><span data-stu-id="09ef8-106">All previous settings in the wizard are also deleted.</span></span> <span data-ttu-id="09ef8-107">Tous les objets existants d'une base de données sous-jacente qui étaient liés à une source de données ou une vue de source de données supprimée sont traités comme des objets créés par l'utilisateur lorsque vous exécutez l'Assistant Génération de schéma la fois suivante.</span><span class="sxs-lookup"><span data-stu-id="09ef8-107">Any existing objects in an underlying database that were bound to a deleted data source or data source view are treated as user-created objects the next time you run the Schema Generation Wizard.</span></span>  
  
 <span data-ttu-id="09ef8-108">Si la vue de source de données ne reflète pas l'état réel de la base de données sous-jacente au moment de la génération, l'Assistant Génération de schéma risque de rencontrer des erreurs en générant le schéma pour la base de données de la zone de sujet.</span><span class="sxs-lookup"><span data-stu-id="09ef8-108">If the data source view does not reflect the actual state of the underlying database at the time of generation, the Schema Generation Wizard may encounter errors when it generates the schema for the subject area database.</span></span> <span data-ttu-id="09ef8-109">Par exemple, si la vue de source de données spécifie qu’une colonne a le type de données **int**, alors qu’il s’agit en fait du type **string**, l’Assistant Génération de schéma définit le type de données **INT** pour la clé étrangère afin de la faire correspondre à la vue de source de données, puis il ne parvient pas à créer la relation car le véritable type de données de cette colonne est **string**.</span><span class="sxs-lookup"><span data-stu-id="09ef8-109">For example, if the data source view specifies that the data type for a column is **int**, but data type for the column is actually **string**, the Schema Generation Wizard sets the data type for the foreign key to **INT** to match the data source view and then fails when it creates the relationship because the actual type is **string**.</span></span>  
  
 <span data-ttu-id="09ef8-110">D'un autre côté, si vous modifiez la chaîne de connexion à la source de données en spécifiant une base de données différente de celle de la génération précédente, aucune erreur ne se produit.</span><span class="sxs-lookup"><span data-stu-id="09ef8-110">On the other hand, if you change the data source connection string to a different database from the previous generation, no error is generated.</span></span> <span data-ttu-id="09ef8-111">La nouvelle base de données est utilisée, et aucune modification n'est apportée à la base de données précédente.</span><span class="sxs-lookup"><span data-stu-id="09ef8-111">The new database is used, and no change is made to the previous database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09ef8-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09ef8-112">See Also</span></span>  
 [<span data-ttu-id="09ef8-113">Présentation de la génération incrémentielle</span><span class="sxs-lookup"><span data-stu-id="09ef8-113">Understanding Incremental Generation</span></span>](understanding-incremental-generation.md)  
  
  
