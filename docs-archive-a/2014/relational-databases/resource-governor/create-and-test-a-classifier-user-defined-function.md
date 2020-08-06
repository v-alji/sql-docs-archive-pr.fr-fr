---
title: Créer et tester une fonction classifieur définie par l’utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, classifier function create
- classifier function [SQL Server], test
- classifier function [SQL Server], create
- Resource Governor, classifier function test
ms.assetid: 7866b3c9-385b-40c6-aca5-32d3337032be
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1b8e5371762e38cf2b3ac8c1d506b467dcfa7e3c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699414"
---
# <a name="create-and-test-a-classifier-user-defined-function"></a><span data-ttu-id="9b793-102">Créer et tester une fonction classifieur définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b793-102">Create and Test a Classifier User-Defined Function</span></span>
  <span data-ttu-id="9b793-103">Cette rubrique indique comment créer et tester une fonction définie par l'utilisateur classifieur (UDF).</span><span class="sxs-lookup"><span data-stu-id="9b793-103">This topic shows how to create and test a classifier user-defined function (UDF).</span></span> <span data-ttu-id="9b793-104">Les étapes impliquent l’exécution d’instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] dans l’Éditeur de requêtes [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b793-104">The steps involve executing [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Query Editor.</span></span>  
  
 <span data-ttu-id="9b793-105">L'exemple de la procédure suivante illustre les possibilités de création d'une fonction définie par l'utilisateur classifieur assez complexe.</span><span class="sxs-lookup"><span data-stu-id="9b793-105">The example shown in the following procedure illustrates the possibilities for creating a fairly complex classifier user-defined function.</span></span>  
  
 <span data-ttu-id="9b793-106">Dans notre exemple :</span><span class="sxs-lookup"><span data-stu-id="9b793-106">In our example:</span></span>  
  
-   <span data-ttu-id="9b793-107">Un pool de ressources (pProductionProcessing) et un groupe de charges de travail (gProductionProcessing) sont créés pour le traitement de la production pendant une plage temporelle spécifiée.</span><span class="sxs-lookup"><span data-stu-id="9b793-107">A resource pool (pProductionProcessing) and workload group (gProductionProcessing) are created for production processing during a specified time range.</span></span>  
  
-   <span data-ttu-id="9b793-108">Un pool de ressources (pOffHoursProcessing) et un groupe de charges de travail (gOffHoursProcessing) sont créés pour gérer les connexions qui ne répondent pas aux besoins du traitement de production.</span><span class="sxs-lookup"><span data-stu-id="9b793-108">A resource pool (pOffHoursProcessing) and workload group (gOffHoursProcessing) are created for handling connections that do not meet the requirements for production processing.</span></span>  
  
-   <span data-ttu-id="9b793-109">Une table (TblClassificationTimeTable) est créée dans la base de données master afin de contenir les heures de début et de fin qui peuvent être évaluées par rapport à une heure de connexion.</span><span class="sxs-lookup"><span data-stu-id="9b793-109">A table (TblClassificationTimeTable) is created in master to hold start and end times that can be evaluated against a login time.</span></span> <span data-ttu-id="9b793-110">Cette table doit être créée dans la base de données master car Resource Governor utilise la liaison de schéma pour les fonctions classifieur.</span><span class="sxs-lookup"><span data-stu-id="9b793-110">This must be created in master because Resource Governor uses schema binding for classifier functions.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9b793-111">Il est recommandé de ne pas stocker de grandes tables fréquemment mises à jour dans la base de données master.</span><span class="sxs-lookup"><span data-stu-id="9b793-111">As a best practice, you should not store large, frequently updated tables in master.</span></span>  
  
 <span data-ttu-id="9b793-112">La fonction classifieur étend le temps de connexion.</span><span class="sxs-lookup"><span data-stu-id="9b793-112">The classifier function extends the login time.</span></span> <span data-ttu-id="9b793-113">Une fonction trop complexe peut provoquer l'expiration des délais d'attente de connexion ou ralentir les connexions rapides.</span><span class="sxs-lookup"><span data-stu-id="9b793-113">An overly complex function can cause logins to time out or slow down fast connections.</span></span>  
  
### <a name="to-create-the-classifier-user-defined-function"></a><span data-ttu-id="9b793-114">Pour créer la fonction classifieur définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9b793-114">To create the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="9b793-115">Créez et configurez les nouveaux pools de ressources et groupes de charges de travail.</span><span class="sxs-lookup"><span data-stu-id="9b793-115">Create and configure the new resource pools and workload groups.</span></span> <span data-ttu-id="9b793-116">Affectez chaque groupe de charge de travail au pool de ressources approprié.</span><span class="sxs-lookup"><span data-stu-id="9b793-116">Assign each workload group to the appropriate resource pool.</span></span>  
  
    ```  
    --- Create a resource pool for production processing  
    --- and set limits.  
    USE master  
    GO  
    CREATE RESOURCE POOL pProductionProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 100,  
         MIN_CPU_PERCENT = 50  
    )  
    GO  
    --- Create a workload group for production processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gProductionProcessing  
    WITH  
    (  
         IMPORTANCE = MEDIUM  
    )  
    --- Assign the workload group to the production processing  
    --- resource pool.  
    USING pProductionProcessing  
    GO  
    --- Create a resource pool for off-hours processing  
    --- and set limits.  
  
    CREATE RESOURCE POOL pOffHoursProcessing  
    WITH  
    (  
         MAX_CPU_PERCENT = 50,  
         MIN_CPU_PERCENT = 0  
    )  
    GO  
    --- Create a workload group for off-hours processing  
    --- and configure the relative importance.  
    CREATE WORKLOAD GROUP gOffHoursProcessing  
    WITH  
    (  
         IMPORTANCE = LOW  
    )  
    --- Assign the workload group to the off-hours processing  
    --- resource pool.  
    USING pOffHoursProcessing  
    GO  
    ```  
  
2.  <span data-ttu-id="9b793-117">Mettez à jour la configuration en mémoire.</span><span class="sxs-lookup"><span data-stu-id="9b793-117">Update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
3.  <span data-ttu-id="9b793-118">Créez une table et définissez les heures de début et de fin pour la plage temporelle de traitement de production.</span><span class="sxs-lookup"><span data-stu-id="9b793-118">Create a table and define the start and end times for the production processing time range.</span></span>  
  
    ```  
    USE master  
    GO  
    CREATE TABLE tblClassificationTimeTable  
    (  
         strGroupName     sysname          not null,  
         tStartTime       time              not null,  
         tEndTime         time              not null  
    )  
    GO  
    --- Add time values that the classifier will use to  
    --- determine the workload group for a session.  
    INSERT into tblClassificationTimeTable VALUES('gProductionProcessing', '6:35 AM', '6:15 PM')  
    go  
    ```  
  
4.  <span data-ttu-id="9b793-119">Créez la fonction classifieur qui utilise des fonctions d'heure et des valeurs qui peuvent être évaluées par rapport aux heures figurant dans la table de recherche.</span><span class="sxs-lookup"><span data-stu-id="9b793-119">Create the classifier function that uses time functions and values that can be evaluated against the times in the lookup table.</span></span> <span data-ttu-id="9b793-120">Pour plus d’informations sur l’utilisation des tables de recherche dans une fonction classifieur, consultez la section « Meilleures pratiques recommandées pour l’utilisation de tables de recherche dans une fonction classifieur » dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="9b793-120">For information about using Lookup Tables in a classifier function, see "Best practices for using Lookup Tables in a classifier function" in this topic.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="9b793-121">introduit un jeu étendu de types de données et de fonctions de date et d’heure.</span><span class="sxs-lookup"><span data-stu-id="9b793-121">introduced an expanded set of date and time data types and functions.</span></span> <span data-ttu-id="9b793-122">Pour plus d’informations, consultez [Types de données et fonctions de date et d’heure &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9b793-122">For more information, see [Date and Time Data Types and Functions &#40;Transact-SQL&#41;](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql).</span></span>  
  
    ```  
    CREATE FUNCTION fnTimeClassifier()  
    RETURNS sysname  
    WITH SCHEMABINDING  
    AS  
    BEGIN  
         DECLARE @strGroup sysname  
         DECLARE @loginTime time  
         SET @loginTime = CONVERT(time,GETDATE())  
         SELECT TOP 1 @strGroup = strGroupName  
              FROM dbo.tblClassificationTimeTable  
              WHERE tStartTime <= @loginTime and tEndTime >= @loginTime  
         IF(@strGroup is not null)  
         BEGIN  
              RETURN @strGroup  
         END  
    --- Use the default workload group if there is no match  
    --- on the lookup.  
         RETURN N'gOffHoursProcessing'  
    END  
    GO  
    ```  
  
5.  <span data-ttu-id="9b793-123">Inscrivez la fonction classifieur et mettez à jour la configuration en mémoire.</span><span class="sxs-lookup"><span data-stu-id="9b793-123">Register the classifier function and update the in-memory configuration.</span></span>  
  
    ```  
    ALTER RESOURCE GOVERNOR with (CLASSIFIER_FUNCTION = dbo.fnTimeClassifier)  
    ALTER RESOURCE GOVERNOR RECONFIGURE  
    GO  
    ```  
  
### <a name="to-verify-the-resource-pools-workload-groups-and-the-classifier-user-defined-function"></a><span data-ttu-id="9b793-124">Pour vérifier les pools de ressources, les groupes de charges de travail et la fonction définie par l'utilisateur classifieur</span><span class="sxs-lookup"><span data-stu-id="9b793-124">To verify the resource pools, workload groups, and the classifier user-defined function</span></span>  
  
1.  <span data-ttu-id="9b793-125">Obtenez la configuration de pool de ressources et de groupe de charges de travail à l'aide de la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="9b793-125">Obtain the resource pool and workload group configuration by using the following query.</span></span>  
  
    ```  
    USE master  
    SELECT * FROM sys.resource_governor_resource_pools  
    SELECT * FROM sys.resource_governor_workload_groups  
    GO  
    ```  
  
2.  <span data-ttu-id="9b793-126">Vérifiez que la fonction classifieur existe et qu'elle est activée en utilisant les requêtes suivantes.</span><span class="sxs-lookup"><span data-stu-id="9b793-126">Verify that the classifier function exists and is enabled by using the following queries.</span></span>  
  
    ```  
    --- Get the classifier function Id and state (enabled).  
    SELECT * FROM sys.resource_governor_configuration  
    GO  
    --- Get the classifer function name and the name of the schema  
    --- that it is bound to.  
    SELECT   
          object_schema_name(classifier_function_id) AS [schema_name],  
          object_name(classifier_function_id) AS [function_name]  
    FROM sys.dm_resource_governor_configuration  
  
    ```  
  
3.  <span data-ttu-id="9b793-127">Obtenez les données d'exécution actuelles pour les pools de ressources et groupes de charges de travail en utilisant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="9b793-127">Obtain the current runtime data for the resource pools and workload groups by using the following query.</span></span>  
  
    ```  
    SELECT * FROM sys.dm_resource_governor_resource_pools  
    SELECT * FROM sys.dm_resource_governor_workload_groups  
    GO  
    ```  
  
4.  <span data-ttu-id="9b793-128">Déterminez quelles sessions se trouvent dans chaque de groupe en utilisant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="9b793-128">Find out what sessions are in each group by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, CAST(g.name as nvarchar(20)), s.session_id, s.login_time, CAST(s.host_name as nvarchar(20)), CAST(s.program_name AS nvarchar(20))  
              FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
              ON g.group_id = s.group_id  
    ORDER BY g.name  
    GO  
    ```  
  
5.  <span data-ttu-id="9b793-129">Déterminez quelles demandes se trouvent dans chaque groupe en utilisant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="9b793-129">Find out which requests are in each group by using the following query.</span></span>  
  
    ```  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
                ON g.group_id = r.group_id  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
6.  <span data-ttu-id="9b793-130">Déterminez quelles demandes s'exécutent dans la fonction classifieur en utilisant la requête suivante.</span><span class="sxs-lookup"><span data-stu-id="9b793-130">Find out what requests are running in the classifier by using the following query.</span></span>  
  
    ```  
    SELECT s.group_id, g.name, s.session_id, s.login_time, s.host_name, s.program_name   
               FROM sys.dm_exec_sessions s  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = s.group_id  
                     AND 'preconnect' = s.status  
    ORDER BY g.name  
    GO  
  
    SELECT r.group_id, g.name, r.status, r.session_id, r.request_id, r.start_time, r.command, r.sql_handle, t.text   
               FROM sys.dm_exec_requests r  
         INNER JOIN sys.dm_resource_governor_workload_groups g  
               ON g.group_id = r.group_id  
                     AND 'preconnect' = r.status  
         CROSS APPLY sys.dm_exec_sql_text(r.sql_handle) AS t  
    ORDER BY g.name  
    GO  
    ```  
  
### <a name="best-practices-for-using-lookup-tables-in-a-classifier-function"></a><span data-ttu-id="9b793-131">Meilleures pratiques recommandées pour l'utilisation de tables de recherche dans une fonction classifieur</span><span class="sxs-lookup"><span data-stu-id="9b793-131">Best practices for using Lookup Tables in a classifier function</span></span>  
  
1.  <span data-ttu-id="9b793-132">N'utilisez pas de table de recherche sauf en cas d'absolue nécessité.</span><span class="sxs-lookup"><span data-stu-id="9b793-132">Do not use a lookup table unless it is absolutely necessary.</span></span> <span data-ttu-id="9b793-133">Si vous devez utiliser une table de recherche, vous pouvez la coder de façon irréversible dans la fonction elle-même ; toutefois, cette action doit être équilibrée avec la complexité et les modifications dynamiques de la fonction classifieur.</span><span class="sxs-lookup"><span data-stu-id="9b793-133">If you need to use a lookup table, it can be hard coded into the function itself; however, this needs to be balanced with the complexity and dynamic changes of the classifier function.</span></span>  
  
2.  <span data-ttu-id="9b793-134">Limitez les E/S effectuées pour les tables de recherche.</span><span class="sxs-lookup"><span data-stu-id="9b793-134">Limit the I/O performed for lookup tables.</span></span>  
  
    1.  <span data-ttu-id="9b793-135">Utilisez TOP 1 pour ne retourner qu'une seule ligne.</span><span class="sxs-lookup"><span data-stu-id="9b793-135">Use the TOP 1 to return only one row.</span></span>  
  
    2.  <span data-ttu-id="9b793-136">Réduisez le nombre de lignes présentes dans la table.</span><span class="sxs-lookup"><span data-stu-id="9b793-136">Minimize the number of rows in the table.</span></span>  
  
    3.  <span data-ttu-id="9b793-137">Faites en sorte que toutes les lignes de la table s'affichent sur une seule page ou sur un petit nombre de pages.</span><span class="sxs-lookup"><span data-stu-id="9b793-137">Make all rows of the table exist on a single page, or a small number of pages.</span></span>  
  
    4.  <span data-ttu-id="9b793-138">Vérifiez que les lignes trouvées à l'aide des opérations de recherche d'index utilisent autant de colonnes de recherche que possible.</span><span class="sxs-lookup"><span data-stu-id="9b793-138">Confirm that rows found using the Index Seek operations use as many seeking columns as possible.</span></span>  
  
    5.  <span data-ttu-id="9b793-139">Dénormalisez une seule table si vous envisagez d'utiliser plusieurs tables comportant des jointures.</span><span class="sxs-lookup"><span data-stu-id="9b793-139">De-normalize to a single table if you are considering using multiple tables with joins.</span></span>  
  
3.  <span data-ttu-id="9b793-140">Empêchez tout blocage sur la table de recherche.</span><span class="sxs-lookup"><span data-stu-id="9b793-140">Prevent blocking on the lookup table.</span></span>  
  
    1.  <span data-ttu-id="9b793-141">Utilisez l'indicateur `NOLOCK` pour empêcher tout blocage ou utilisez `SET LOCK_TIMEOUT` dans la fonction avec une valeur maximale de 1 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="9b793-141">Use the `NOLOCK` hint to prevent blocking or use `SET LOCK_TIMEOUT` in the function with a maximum value of 1000 milliseconds.</span></span>  
  
    2.  <span data-ttu-id="9b793-142">Les tables doivent exister dans la base de données master.</span><span class="sxs-lookup"><span data-stu-id="9b793-142">Table(s) must exist in the master database.</span></span> <span data-ttu-id="9b793-143">(La base de données master est la seule base de données dont la récupération est garantie lorsque les ordinateurs clients essaient de se connecter.)</span><span class="sxs-lookup"><span data-stu-id="9b793-143">(The master database is the only database that is guaranteed to be recovered when the client computers attempt to connect).</span></span>  
  
    3.  <span data-ttu-id="9b793-144">Qualifiez toujours entièrement le nom de la table avec le schéma.</span><span class="sxs-lookup"><span data-stu-id="9b793-144">Always fully-qualify the table name with the schema.</span></span> <span data-ttu-id="9b793-145">Le nom de la base de données n'est pas nécessaire dans la mesure où il doit s'agir de la base de données master.</span><span class="sxs-lookup"><span data-stu-id="9b793-145">The database name is not necessary since it has to be the master database.</span></span>  
  
    4.  <span data-ttu-id="9b793-146">Pas de déclencheurs sur la table.</span><span class="sxs-lookup"><span data-stu-id="9b793-146">No triggers on the table.</span></span>  
  
    5.  <span data-ttu-id="9b793-147">Si vous effectuer une mise à jour du contenu de la table, veillez à utiliser une transaction de niveau d'isolement d'instantané afin d'éviter que l'enregistreur ne bloque les lecteurs.</span><span class="sxs-lookup"><span data-stu-id="9b793-147">If you are updating the table contents, make sure to use a snapshot isolation level transaction to prevent Writer blocking Readers.</span></span> <span data-ttu-id="9b793-148">Notez que l'utilisation de l'indicateur `NOLOCK` doit également réduire cet effet.</span><span class="sxs-lookup"><span data-stu-id="9b793-148">Note that using the `NOLOCK` hint should also mitigate this.</span></span>  
  
    6.  <span data-ttu-id="9b793-149">Si possible, désactivez la fonction classifieur lorsque vous modifiez le contenu de la table.</span><span class="sxs-lookup"><span data-stu-id="9b793-149">If possible, disable the classifier function when changing the table contents.</span></span>  
  
        > [!WARNING]  
        >  <span data-ttu-id="9b793-150">Nous vous recommandons vivement d'appliquer ces meilleures pratiques.</span><span class="sxs-lookup"><span data-stu-id="9b793-150">We highly recommend following these best practices.</span></span> <span data-ttu-id="9b793-151">Si des problèmes vous empêchent de les mettre en œuvre, nous vous recommandons de contacter le suport technique de Microsoft afin de d'éviter d'éventuels problèmes futurs.</span><span class="sxs-lookup"><span data-stu-id="9b793-151">If there are issues that prevent you from following the best practices, we recommend that you contact Microsoft Support so that you can proactively prevent any future problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b793-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b793-152">See Also</span></span>  
 <span data-ttu-id="9b793-153">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="9b793-153">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="9b793-154">[Activer Resource Governor](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="9b793-154">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="9b793-155">[Pool de ressources de Resource Governor](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="9b793-155">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="9b793-156">[Groupe de charge de travail de Resource Governor](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="9b793-156">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="9b793-157">[Configurer le gouverneur de ressources à l'aide d'un modèle](configure-resource-governor-using-a-template.md) </span><span class="sxs-lookup"><span data-stu-id="9b793-157">[Configure Resource Governor Using a Template](configure-resource-governor-using-a-template.md) </span></span>  
 <span data-ttu-id="9b793-158">[Afficher les propriétés de Resource Governor](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="9b793-158">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="9b793-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b793-159">[ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-resource-governor-transact-sql) </span></span>  
 <span data-ttu-id="9b793-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b793-160">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="9b793-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b793-161">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="9b793-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9b793-162">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="9b793-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9b793-163">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
