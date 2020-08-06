---
title: Ajouter une table (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d713c432-db99-4983-acc1-52b0fdd58bd6
author: minewiskan
ms.author: owend
ms.openlocfilehash: a80c22c992a89ed2cb3db84809b47a7cd08cb514
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612484"
---
# <a name="add-a-table-ssas-tabular"></a><span data-ttu-id="ef3e2-102">Ajouter une table (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="ef3e2-102">Add a Table (SSAS Tabular)</span></span>
  <span data-ttu-id="ef3e2-103">Cette rubrique explique comment ajouter une table à partir d'une source de données dans laquelle vous avez précédemment importé des données dans votre modèle.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-103">This topic describes how to add a table from a data source from which you have previously imported data into your model.</span></span> <span data-ttu-id="ef3e2-104">Pour ajouter une table à partir de la même source de données, vous pouvez utiliser la connexion à la source de données existante.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-104">To add a table from the same data source, you can use the existing data source connection.</span></span> <span data-ttu-id="ef3e2-105">Il est recommandé d'utiliser toujours une connexion unique lorsque vous importez plusieurs tables à partir d'une source de données unique.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-105">It is recommended you always use a single connection when importing any number of tables from a single data source.</span></span>  
  
### <a name="to-add-a-table-from-an-existing-data-source"></a><span data-ttu-id="ef3e2-106">Pour ajouter une table à partir d'une source de données existante</span><span class="sxs-lookup"><span data-stu-id="ef3e2-106">To add a table from an existing data source</span></span>  
  
1.  <span data-ttu-id="ef3e2-107">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis sur **Connexions existantes**.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="ef3e2-108">Dans la page **Connexions existantes** , sélectionnez la connexion à la source de données qui contient la table à ajouter, puis cliquez sur **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-108">On the **Existing Connections** page, select the connection to the data source that has the table you want to add, and then click **Open**.</span></span>  
  
3.  <span data-ttu-id="ef3e2-109">Dans la page **Sélectionner des tables et des vues** , sélectionnez la table à partir de la source de données à ajouter à votre modèle.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-109">On the **Select Tables and Views** page, select the table from the data source you want to add to your model.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="ef3e2-110">La page **Sélectionner des tables et des vues** n’affiche pas les tables précédemment importées comme vérifiées.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-110">The **Select Tables and Views** page will not show tables that were previously imported as checked.</span></span>  <span data-ttu-id="ef3e2-111">Si vous sélectionnez une table qui a été précédemment importées au moyen de cette connexion, et si vous ne donnez pas à la table un nom convivial différent, un « 1 » sera ajouté au nom convivial.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-111">If you select a table that was previously imported using this connection, and you did not give the table a different friendly name, a 1 will be appended to the friendly name.</span></span> <span data-ttu-id="ef3e2-112">Vous n'avez pas besoin de resélectionner les tables qui ont été précédemment importées à l'aide de cette connexion.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-112">You do not need to re-select any tables that were previously imported by using this connection.</span></span>  
  
4.  <span data-ttu-id="ef3e2-113">Si nécessaire, utilisez **Afficher un aperçu et filtrer** pour sélectionner uniquement certaines colonnes ou appliquer des filtres aux données à importer.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-113">If necessary, use **Preview & Filter** to select only certain columns or apply filters to the data to be imported.</span></span>  
  
5.  <span data-ttu-id="ef3e2-114">Cliquez sur **Terminer** pour importer la nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-114">Click **Finish** to import the new table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ef3e2-115">Lorsque vous importez plusieurs tables simultanément à partir d'une seule source de données, les relations entre ces tables à la source sont automatiquement créées dans le modèle.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-115">When importing multiple tables at the same time from a single data source, any relationships between those tables at the source will automatically be created in the model.</span></span> <span data-ttu-id="ef3e2-116">Si vous ajoutez une table ultérieurement, toutefois, vous devrez peut-être créer manuellement des relations dans le modèle entre les tables récemment ajoutées et les tables précédemment importées.</span><span class="sxs-lookup"><span data-stu-id="ef3e2-116">When adding a table later; however, you may need to manually create relationships in the model between newly added tables and the tables that were previously imported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3e2-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef3e2-117">See Also</span></span>  
 <span data-ttu-id="ef3e2-118">[Importer des données &#40;&#41;tabulaire SSAS](../import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="ef3e2-118">[Import Data &#40;SSAS Tabular&#41;](../import-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="ef3e2-119">Supprimer une table &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="ef3e2-119">Delete a Table &#40;SSAS Tabular&#41;</span></span>](delete-a-table-ssas-tabular.md)  
  
  
