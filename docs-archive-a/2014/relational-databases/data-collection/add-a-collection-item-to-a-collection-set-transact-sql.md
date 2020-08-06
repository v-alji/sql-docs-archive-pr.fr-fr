---
title: Ajouter un élément de collecte à un jeu d’éléments de collecte (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- collection items [SQL Server]
- collection sets [SQL Server], adding items
ms.assetid: 9fe6454e-8c0e-4b50-937b-d9871b20fd13
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0b21508761bdfbaf8918242b074f78203c1bcaed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614640"
---
# <a name="add-a-collection-item-to-a-collection-set-transact-sql"></a><span data-ttu-id="0bac3-102">Ajouter un élément de collecte à un jeu d'éléments de collecte (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="0bac3-102">Add a Collection Item to a Collection Set (Transact-SQL)</span></span>
  <span data-ttu-id="0bac3-103">Vous pouvez ajouter un élément de collecte à un jeu d'éléments de collecte existant à l'aide des procédures stockées fournies avec le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="0bac3-103">You can add a collection item to an existing collection set using the stored procedures that are provided with the data collector.</span></span>  
  
 <span data-ttu-id="0bac3-104">Effectuez les étapes suivantes à l'aide de l'éditeur de requête dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bac3-104">Carry out the following steps using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
### <a name="add-a-collection-item-to-a-collection-set"></a><span data-ttu-id="0bac3-105">Ajouter un élément de collecte à un jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="0bac3-105">Add a collection item to a collection set</span></span>  
  
1.  <span data-ttu-id="0bac3-106">Arrêtez le jeu d’éléments de collecte auquel vous souhaitez ajouter l’élément en exécutant la procédure stockée **sp_syscollector_stop_collection_set** .</span><span class="sxs-lookup"><span data-stu-id="0bac3-106">Stop the collection set that you want to add the item to by running the **sp_syscollector_stop_collection_set** stored procedure.</span></span> <span data-ttu-id="0bac3-107">Par exemple, pour arrêter un jeu d'éléments de collecte nommé « Test Collection Set », exécutez les instructions suivantes :</span><span class="sxs-lookup"><span data-stu-id="0bac3-107">For example, to stop a collection set that is named "Test Collection Set", run the following statements:</span></span>  
  
    ```sql  
    USE msdb  
    DECLARE @csid int  
    SELECT @csid = collection_set_id  
    FROM syscollector_collection_sets  
    WHERE name = 'Test Collection Set'  
    SELECT @csid  
    EXEC dbo.sp_syscollector_stop_collection_set @collection_set_id = @csid  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="0bac3-108">Vous pouvez également arrêter le jeu d'éléments de collecte en utilisant l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bac3-108">You can also stop the collection set by using Object Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0bac3-109">Pour plus d’informations, consultez [Démarrer ou arrêter un jeu d’éléments de collecte](start-or-stop-a-collection-set.md).</span><span class="sxs-lookup"><span data-stu-id="0bac3-109">For more information, see [Start or Stop a Collection Set](start-or-stop-a-collection-set.md).</span></span>  
  
2.  <span data-ttu-id="0bac3-110">Déclarez le jeu d'éléments de collecte auquel vous souhaitez ajouter l'élément de collecte.</span><span class="sxs-lookup"><span data-stu-id="0bac3-110">Declare the collection set that you want to add the collection item to.</span></span> <span data-ttu-id="0bac3-111">Le code suivant fournit un exemple de la façon dont déclarer l'ID du jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="0bac3-111">The following code provides an example of how to declare the collection set ID.</span></span>  
  
    ```sql  
    DECLARE @collection_set_id_1 int  
    SELECT @collection_set_id_1 = collection_set_id FROM [msdb].[dbo].[syscollector_collection_sets]  
    WHERE name = N'Test Collection Set'; -- name of collection set  
    ```  
  
3.  <span data-ttu-id="0bac3-112">Déclarez le type de collecteur.</span><span class="sxs-lookup"><span data-stu-id="0bac3-112">Declare the collector type.</span></span> <span data-ttu-id="0bac3-113">Le code suivant fournit un exemple de la façon dont déclarer le type de collecteur Requête T-SQL générique.</span><span class="sxs-lookup"><span data-stu-id="0bac3-113">The following code provides an example of how to declare the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid_1 uniqueidentifier  
    SELECT @collector_type_uid_1 = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
       WHERE name = N'Generic T-SQL Query Collector Type';  
    ```  
  
     <span data-ttu-id="0bac3-114">Vous pouvez exécuter le code suivant pour obtenir la liste des types de collecteurs installés :</span><span class="sxs-lookup"><span data-stu-id="0bac3-114">You can run the following code to obtain a list of the installed collector types:</span></span>  
  
    ```sql  
    USE msdb  
    SELECT * from syscollector_collector_types  
    GO  
    ```  
  
4.  <span data-ttu-id="0bac3-115">Exécutez la procédure stockée **sp_syscollector_create_collection_item** pour créer l’élément de collecte.</span><span class="sxs-lookup"><span data-stu-id="0bac3-115">Run the **sp_syscollector_create_collection_item** stored procedure to create the collection item.</span></span> <span data-ttu-id="0bac3-116">Vous devez déclarer le schéma de l'élément de collecte de manière à ce qu'il soit mappé au schéma requis pour le type de collecteur voulu.</span><span class="sxs-lookup"><span data-stu-id="0bac3-116">You must declare the schema for the collection item so that it maps to the required schema for the desired collector type.</span></span> <span data-ttu-id="0bac3-117">L'exemple suivant utilise le schéma d'entrée Requête T-SQL générique.</span><span class="sxs-lookup"><span data-stu-id="0bac3-117">The following example uses the Generic T-SQL Query input schema.</span></span>  
  
    ```sql  
    DECLARE @collection_item_id int;  
    EXEC [msdb].[dbo].[sp_syscollector_create_collection_item]   
    @name=N'OS Wait Stats', --name of collection item  
    @parameters=N'  
    <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
     <Query>  
      <Value>select * from sys.dm_os_wait_stats</Value>  
      <OutputTable>os_wait_stats</OutputTable>  
    </Query>  
    </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 60,  
    @collection_set_id = @collection_set_id_1, --- Provides the collection set ID number  
    @collector_type_uid = @collector_type_uid_1 -- Provides the collector type UID  
    SELECT @collection_item_id     
    ```  
  
5.  <span data-ttu-id="0bac3-118">Avant de démarrer le jeu d'éléments de collecte mis à jour, exécutez la requête suivante pour vérifier que le nouvel élément de collecte a été créé :</span><span class="sxs-lookup"><span data-stu-id="0bac3-118">Before starting the updated collection set, run the following query to verify that the new collection item has been created:</span></span>  
  
    ```xaml  
    USE msdb  
    SELECT * from syscollector_collection_sets  
    SELECT * from syscollector_collection_items  
    GO  
    ```  
  
     <span data-ttu-id="0bac3-119">Les jeux d’éléments de collecte et leurs éléments de collecte figurent sous l’onglet **Résultats** .</span><span class="sxs-lookup"><span data-stu-id="0bac3-119">The collection sets and their collection items are displayed in the **Results** tab.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bac3-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0bac3-120">See Also</span></span>  
 <span data-ttu-id="0bac3-121">[Créer un jeu d’éléments de collecte personnalisé qui utilise le type de collecteur Requête T-SQL générique &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span><span class="sxs-lookup"><span data-stu-id="0bac3-121">[Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type &#40;Transact-SQL&#41;](create-custom-collection-set-generic-t-sql-query-collector-type.md) </span></span>  
 [<span data-ttu-id="0bac3-122">Procédures stockées du collecteur de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0bac3-122">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
