---
title: Créer un jeu d’collections personnalisé qui utilise le type de collecteur requête T-SQL générique (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- T-SQL Query collector type
- collection sets [SQL Server], creating custom
ms.assetid: 6b06db5b-cfdc-4ce0-addd-ec643460605b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ab21ad5fd65556dec639fd5ca6999d23e2de673b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611829"
---
# <a name="create-a-custom-collection-set-that-uses-the-generic-t-sql-query-collector-type-transact-sql"></a><span data-ttu-id="d7ad6-102">Créer un jeu d'éléments de collecte personnalisé qui utilise le type de collecteur Requête T-SQL générique (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d7ad6-102">Create a Custom Collection Set That Uses the Generic T-SQL Query Collector Type (Transact-SQL)</span></span>
  <span data-ttu-id="d7ad6-103">Vous pouvez créer un jeu d'éléments de collecte personnalisé avec des éléments de collecte qui utilisent le type de collecteur Requête T-SQL générique à l'aide des procédures stockées fournies avec le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-103">You can create a custom collection set with collection items that use the Generic T-SQL Query collector type by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="d7ad6-104">Accomplir cette tâche implique l'utilisation de l'éditeur de requête dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour effectuer les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="d7ad6-104">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedures:</span></span>  
  
-   <span data-ttu-id="d7ad6-105">Configurer les planifications de téléchargement.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-105">Configure upload schedules.</span></span>  
  
-   <span data-ttu-id="d7ad6-106">Définir et créer le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-106">Define and create the collection set.</span></span>  
  
-   <span data-ttu-id="d7ad6-107">Définir et créer un élément de collecte.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-107">Define and create a collection item.</span></span>  
  
-   <span data-ttu-id="d7ad6-108">Vérifier que le jeu d'éléments de collecte et les éléments de collecte existent.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-108">Verify that the collection set and collection items exist.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7ad6-109">Avant de créer un jeu d'éléments de collecte personnalisé, vous devez configurer des paramètres de collecte de données.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-109">Before you create a custom collection set, you must configure data collection parameters.</span></span> <span data-ttu-id="d7ad6-110">Pour plus d’informations, consultez [Configurer des paramètres de collecte de données &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="d7ad6-110">For more information, see [Configure Data Collection Parameters &#40;Transact-SQL&#41;](configure-data-collection-parameters-transact-sql.md).</span></span>  
  
### <a name="define-and-create-the-collection-set"></a><span data-ttu-id="d7ad6-111">Définir et créer le jeu d'éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="d7ad6-111">Define and create the collection set</span></span>  
  
1.  <span data-ttu-id="d7ad6-112">Définissez un nouveau jeu d'éléments de collecte à l'aide de la procédure stockée sp_syscollector_create_collection_set.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-112">Define a new collection set using the sp_syscollector_create_collection_set stored procedure.</span></span>  
  
    ```  
    USE msdb;  
    DECLARE @collection_set_id int;  
    DECLARE @collection_set_uid uniqueidentifier;  
    EXEC sp_syscollector_create_collection_set   
        @name=N'DMV Test 1',   
        @collection_mode=0,   
        @description=N'This is a test collection set',   
        @logging_level=1,   
        @days_until_expiration=14,   
        @schedule_name=N'CollectorSchedule_Every_15min',   
        @collection_set_id=@collection_set_id OUTPUT,   
        @collection_set_uid=@collection_set_uid OUTPUT;  
    SELECT @collection_set_id, @collection_set_uid;  
    ```  
  
     <span data-ttu-id="d7ad6-113">Le mode de collecte peut être défini à 0 (avec mise en cache) ou à 1 (sans mise en cache).</span><span class="sxs-lookup"><span data-stu-id="d7ad6-113">The collection mode can be set to either 0 (cached) or to 1 (non-cached).</span></span>  
  
     <span data-ttu-id="d7ad6-114">Le niveau de journalisation peut être défini sur 0, 1 ou 2.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-114">The logging level can be set to 0, 1 or 2.</span></span>  
  
     <span data-ttu-id="d7ad6-115">Les planifications préconfigurées suivantes sont fournies avec le collecteur de données :</span><span class="sxs-lookup"><span data-stu-id="d7ad6-115">The following preconfigured schedules are provided with the data collector:</span></span>  
  
    -   <span data-ttu-id="d7ad6-116">CollectorSchedule_Every_5min</span><span class="sxs-lookup"><span data-stu-id="d7ad6-116">CollectorSchedule_Every_5min</span></span>  
  
    -   <span data-ttu-id="d7ad6-117">CollectorSchedule_Every_10min</span><span class="sxs-lookup"><span data-stu-id="d7ad6-117">CollectorSchedule_Every_10min</span></span>  
  
    -   <span data-ttu-id="d7ad6-118">CollectorSchedule_Every_15min</span><span class="sxs-lookup"><span data-stu-id="d7ad6-118">CollectorSchedule_Every_15min</span></span>  
  
    -   <span data-ttu-id="d7ad6-119">CollectorSchedule_Every_30min</span><span class="sxs-lookup"><span data-stu-id="d7ad6-119">CollectorSchedule_Every_30min</span></span>  
  
    -   <span data-ttu-id="d7ad6-120">CollectorSchedule_Every_60min</span><span class="sxs-lookup"><span data-stu-id="d7ad6-120">CollectorSchedule_Every_60min</span></span>  
  
    -   <span data-ttu-id="d7ad6-121">CollectorSchedule_Every_6h</span><span class="sxs-lookup"><span data-stu-id="d7ad6-121">CollectorSchedule_Every_6h</span></span>  
  
     <span data-ttu-id="d7ad6-122">Si vous ne souhaitez pas utiliser l'une des planifications fournies, vous pouvez en créer une et vous en servir pour le jeu d'éléments de collecte.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-122">If you do not want to use one of the schedules that are provided, you can create a new schedule and use it for the collection set.</span></span> <span data-ttu-id="d7ad6-123">Pour plus d’informations, consultez [Créer des planifications et les attacher à des travaux](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="d7ad6-123">For more information, see [Create and Attach Schedules to Jobs](../../ssms/agent/create-and-attach-schedules-to-jobs.md).</span></span>  
  
### <a name="define-and-create-a-collection-item"></a><span data-ttu-id="d7ad6-124">Définir et créer un élément de collecte</span><span class="sxs-lookup"><span data-stu-id="d7ad6-124">Define and create a collection item</span></span>  
  
1.  <span data-ttu-id="d7ad6-125">Le nouvel élément de collecte étant basé sur un type de collecteur générique déjà installé, vous pouvez exécuter le code suivant pour définir le GUID de sorte qu'il corresponde au type de collecteur Requête T-SQL générique.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-125">Because the new collection item is based on a generic collector type that is already installed, you can run the following code to set the GUID to correspond to the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    DECLARE @collector_type_uid uniqueidentifier;  
    SELECT @collector_type_uid = collector_type_uid FROM [msdb].[dbo].[syscollector_collector_types]   
    WHERE name = N'Generic T-SQL Query Collector Type';  
    DECLARE @collection_item_id int;  
    ```  
  
2.  <span data-ttu-id="d7ad6-126">Utilisez la procédure stockée sp_syscollector_create_collection_item pour créer l'élément de collecte.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-126">Use the sp_syscollector_create_collection_item stored procedure to create the collection item.</span></span> <span data-ttu-id="d7ad6-127">Déclarez le schéma de l'élément de collecte de manière à ce qu'il soit mappé au schéma requis pour le type de collecteur Requête T-SQL générique.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-127">Declare the schema for the collection item so it maps to the schema that is required for the Generic T-SQL Query collector type.</span></span>  
  
    ```sql  
    EXEC sp_syscollector_create_collection_item   
        @name=N'Query Stats - Test 1',   
        @parameters=N'  
            <ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
            <Query>  
            <Value>SELECT * FROM sys.dm_exec_query_stats</Value>  
            <OutputTable>dm_exec_query_stats</OutputTable>  
            </Query>  
            </ns:TSQLQueryCollector>',   
        @collection_item_id=@collection_item_id OUTPUT,   
        @frequency=5,   
        @collection_set_id=@collection_set_id,   
        @collector_type_uid=@collector_type_uid;  
    SELECT @collection_item_id;  
    ```  
  
### <a name="verify-that-the-new-collection-set-and-collection-item-exist"></a><span data-ttu-id="d7ad6-128">Vérifier que le nouveau jeu d'éléments de collecte et l'élément de collecte existent</span><span class="sxs-lookup"><span data-stu-id="d7ad6-128">Verify that the new collection set and collection item exist</span></span>  
  
1.  <span data-ttu-id="d7ad6-129">Avant de démarrer le nouveau jeu d'éléments de collecte, exécutez la requête suivante pour vérifier que le nouveau jeu d'éléments de collecte et son élément de collecte ont été créés.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-129">Before starting the new collection set, run the following query to verify that the new collection set and its collection item have been created.</span></span>  
  
    ```sql  
    USE msdb;  
    SELECT * FROM syscollector_collection_sets;  
    SELECT * FROM syscollector_collection_items;  
    GO  
    ```  
  
     <span data-ttu-id="d7ad6-130">Vous pouvez également procéder à un contrôle visuel dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d7ad6-130">You can also do a visual check in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d7ad6-131">Dans l’Explorateur d’objets, développez le nœud **Gestion** , puis développez **Collecte de données**.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-131">In Object Explorer, expand the **Management** node, and then expand **Data Collection**.</span></span> <span data-ttu-id="d7ad6-132">Le nouveau jeu d'éléments de collecte s'affiche.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-132">The new collection set will be displayed.</span></span> <span data-ttu-id="d7ad6-133">Le cercle rouge sur l'icône du jeu d'éléments de collecte indique que ce dernier est arrêté.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-133">The red circle icon for the collection set indicates that the collection set is stopped.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7ad6-134">Exemple</span><span class="sxs-lookup"><span data-stu-id="d7ad6-134">Example</span></span>  
 <span data-ttu-id="d7ad6-135">L'exemple de code suivant combine les exemples documentés dans les étapes précédentes.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-135">The following code sample combines the examples that are documented in the previous steps.</span></span> <span data-ttu-id="d7ad6-136">Notez que la fréquence de collecte définie pour l'élément de collecte (5 secondes) est ignorée, car le mode de collecte du jeu d'éléments de collecte est défini sur 0, ce qui correspond au mode avec mise en cache.</span><span class="sxs-lookup"><span data-stu-id="d7ad6-136">Note that the collection frequency that is set for the collection item (5 seconds) is ignored because the collection set collection mode is set to 0, which is cached mode.</span></span> <span data-ttu-id="d7ad6-137">Pour plus d'informations, consultez [Data Collection](data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="d7ad6-137">For more information, see [Data Collection](data-collection.md).</span></span>  
  
```sql  
USE msdb;  
  
DECLARE @collection_set_id int;  
DECLARE @collection_set_uid uniqueidentifier  
  
EXEC dbo.sp_syscollector_create_collection_set  
    @name = N'DMV Stats Test 1',  
    @collection_mode = 0,  
    @description = N'This is a test collection set',  
    @logging_level=1,  
    @days_until_expiration = 14,  
    @schedule_name=N'CollectorSchedule_Every_15min',  
    @collection_set_id = @collection_set_id OUTPUT,  
    @collection_set_uid = @collection_set_uid OUTPUT;  
SELECT @collection_set_id,@collection_set_uid;  
  
DECLARE @collector_type_uid uniqueidentifier;  
SELECT @collector_type_uid = collector_type_uid FROM syscollector_collector_types   
WHERE name = N'Generic T-SQL Query Collector Type';  
  
DECLARE @collection_item_id int;  
EXEC sp_syscollector_create_collection_item  
@name= N'Query Stats - Test 1',  
@parameters=N'  
<ns:TSQLQueryCollector xmlns:ns="DataCollectorType">  
<Query>  
  <Value>select * from sys.dm_exec_query_stats</Value>  
  <OutputTable>dm_exec_query_stats</OutputTable>  
</Query>  
 </ns:TSQLQueryCollector>',  
    @collection_item_id = @collection_item_id OUTPUT,  
    @frequency = 5, -- This parameter is ignored in cached mode  
    @collection_set_id = @collection_set_id,  
    @collector_type_uid = @collector_type_uid;  
SELECT @collection_item_id;  
  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7ad6-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d7ad6-138">See Also</span></span>  
 <span data-ttu-id="d7ad6-139">[Procédures stockées du collecteur de données &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d7ad6-139">[Data Collector Stored Procedures &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql) </span></span>  
 <span data-ttu-id="d7ad6-140">[Gérer les planifications](../../ssms/agent/manage-schedules.md) </span><span class="sxs-lookup"><span data-stu-id="d7ad6-140">[Manage Schedules](../../ssms/agent/manage-schedules.md) </span></span>  
 [<span data-ttu-id="d7ad6-141">Démarrer ou arrêter un jeu d’éléments de collecte</span><span class="sxs-lookup"><span data-stu-id="d7ad6-141">Start or Stop a Collection Set</span></span>](start-or-stop-a-collection-set.md)  
  
  
