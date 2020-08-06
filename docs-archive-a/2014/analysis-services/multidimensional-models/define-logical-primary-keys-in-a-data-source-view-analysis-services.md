---
title: Définir des clés primaires logiques dans une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- removing logical primary keys
- logical primary keys [SQL Server]
- deleting logical primary keys
- data source views [Analysis Services], logical primary keys
ms.assetid: 172bc267-c637-4caa-bf55-0ba198d30b1e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 25092e5d754381c572dcdbfc03e5ee0f29c1df24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605837"
---
# <a name="define-logical-primary-keys-in-a-data-source-view-analysis-services"></a><span data-ttu-id="3d45a-102">Définir des clés primaires logiques dans une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="3d45a-102">Define Logical Primary Keys in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="3d45a-103">L'Assistant Vue de source de données et le Concepteur de vue de source de données définissent automatiquement une clé primaire pour une table ajoutée à une vue de source de données basée sur une table de base de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="3d45a-103">The Data Source View Wizard and Data Source View Designer automatically define a primary key for a table that is added to a data source view based on underlying database table.</span></span>  
  
 <span data-ttu-id="3d45a-104">Occasionnellement, vous pouvez définir manuellement une clé primaire dans une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="3d45a-104">Occasionally, you may need to manually define a primary key in the data source view.</span></span> <span data-ttu-id="3d45a-105">Par exemple, pour des raisons de performance ou de conception, les tables d'une source de données ne contiennent pas forcément de colonnes clés primaires définies de manière explicite.</span><span class="sxs-lookup"><span data-stu-id="3d45a-105">For example, for performance or design reasons, tables in a data source may not have explicitly defined primary key columns.</span></span> <span data-ttu-id="3d45a-106">Les vues et les requêtes nommées peuvent également omettre la colonne clé primaire d'une table.</span><span class="sxs-lookup"><span data-stu-id="3d45a-106">Named queries and views may also omit the primary key column for a table.</span></span> <span data-ttu-id="3d45a-107">Si une table, une vue ou une requête nommée ne contient pas de clé primaire physique définie, vous pouvez manuellement définir une clé primaire logique sur la table, la vue ou la requête nommée dans le Concepteur de vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="3d45a-107">If a table, view, or named query does not have a physical primary key defined, you can manually define a logical primary key on the table, view or named query in Data Source View Designer.</span></span>  
  
## <a name="set-a-logical-primary-key"></a><span data-ttu-id="3d45a-108">Définir une clé primaire logique</span><span class="sxs-lookup"><span data-stu-id="3d45a-108">Set a Logical Primary Key</span></span>  
 <span data-ttu-id="3d45a-109">Des clés primaires sont nécessaires dans [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] pour identifier de façon unique les enregistrements d’une table, pour identifier les colonnes clés dans les tables de dimension et pour prendre en charge les relations entre les tables, les vues et les requêtes nommées.</span><span class="sxs-lookup"><span data-stu-id="3d45a-109">Primary keys are required in [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] to uniquely identify records in a table, identify key columns in dimension tables and to support relationships between tables, views and named queries.</span></span> <span data-ttu-id="3d45a-110">Ces relations servent à construire des requêtes pour récupérer des données et des métadonnées dans les sources de données sous-jacentes et à tirer parti des fonctionnalités avancées de Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="3d45a-110">These relationships are used to construct queries for retrieving data and metadata from underlying data sources, and to take advantage of advanced business intelligence features.</span></span>  
  
 <span data-ttu-id="3d45a-111">Toutes les colonnes peuvent être utilisées pour la clé primaire logique, y compris un calcul nommé.</span><span class="sxs-lookup"><span data-stu-id="3d45a-111">Any column can be used for the logical primary key, including a named calculation.</span></span> <span data-ttu-id="3d45a-112">Lorsque vous créez une clé primaire logique, une contrainte unique est créée dans la vue de source de données et marquée comme contrainte de clé primaire.</span><span class="sxs-lookup"><span data-stu-id="3d45a-112">When you create a logical primary key, a unique constraint is created in the data source view and marked as a primary key constraint.</span></span> <span data-ttu-id="3d45a-113">Si la table sélectionnée contient une autre clé primaire logique, celle-ci est supprimée.</span><span class="sxs-lookup"><span data-stu-id="3d45a-113">Any other existing logical primary key specified in the selected table is deleted.</span></span>  
  
1.  <span data-ttu-id="3d45a-114">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet ou connectez-vous à la base de données qui contient la vue de source de données dans laquelle vous souhaitez définir une clé primaire logique.</span><span class="sxs-lookup"><span data-stu-id="3d45a-114">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project or connect to the database that contains the data source view in which you wish to set a logical primary key.</span></span>  
  
2.  <span data-ttu-id="3d45a-115">Dans l’Explorateur de solutions, développez le dossier **Vues des sources de données** , puis double-cliquez sur la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="3d45a-115">In Solution Explorer, expand the **Data Source Views** folder, then double-click the data source view.</span></span>  
  
     <span data-ttu-id="3d45a-116">Pour rechercher une table ou une vue, vous pouvez utiliser l’option **Rechercher une table** en cliquant sur le menu vue de **source de données** ou en cliquant avec le bouton droit dans une zone ouverte du volet **tables** ou **diagramme** .</span><span class="sxs-lookup"><span data-stu-id="3d45a-116">To locate a table or view, you can use the **Find Table** option by either clicking the **Data Source View**  menu or right-clicking in an open area of the **Tables** or **Diagram** panes.</span></span>  
  
3.  <span data-ttu-id="3d45a-117">Dans le volet **Tables** ou **Diagramme** , cliquez avec le bouton droit sur la ou les colonnes que vous souhaitez utiliser pour définir une clé primaire logique, puis cliquez sur **Définir la clé primaire logique**.</span><span class="sxs-lookup"><span data-stu-id="3d45a-117">In either the **Tables** or the **Diagram** pane, right-click the column or columns that you want to use to define a logical primary key, and then click **Set Logical Primary Key**.</span></span>  
  
     <span data-ttu-id="3d45a-118">L'option permettant de définir une clé primaire logique est disponible uniquement pour les tables qui ne possèdent pas de clé primaire.</span><span class="sxs-lookup"><span data-stu-id="3d45a-118">The option to set a logical primary key is available only for tables that do not have a primary key.</span></span>  
  
     <span data-ttu-id="3d45a-119">Notez qu'après avoir définir la clé, une icône de clé identifie les colonnes clés primaires.</span><span class="sxs-lookup"><span data-stu-id="3d45a-119">Notice that after you set the key, a key icon now identifies the primary key columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d45a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3d45a-120">See Also</span></span>  
 <span data-ttu-id="3d45a-121">[Vues de sources de données dans les modèles multidimensionnels](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="3d45a-121">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="3d45a-122">Définir des calculs nommés dans une vue de source de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3d45a-122">Define Named Calculations in a Data Source View &#40;Analysis Services&#41;</span></span>](define-named-calculations-in-a-data-source-view-analysis-services.md)  
  
  
