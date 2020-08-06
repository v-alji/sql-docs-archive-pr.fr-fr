---
title: Utiliser le suivi des modifications (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], making changes
- change tracking [SQL Server], troubleshooting
- updating data [SQL Server]
- troubleshooting [SQL Server], change tracking
- data changes [SQL Server]
- tracking data changes [SQL Server]
- data [SQL Server], changing
- change tracking [SQL Server], data restore
- change tracking [SQL Server], ensuring consistent results
- change tracking [SQL Server], handling changes
ms.assetid: 5aec22ce-ae6f-4048-8a45-59ed05f04dc5
author: rothja
ms.author: jroth
ms.openlocfilehash: bdb8205a789894caf8c8e2d3c3f491751757bab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613909"
---
# <a name="work-with-change-tracking-sql-server"></a><span data-ttu-id="95323-102">Utiliser le suivi des modifications (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="95323-102">Work with Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="95323-103">Les applications qui utilisent le suivi des modifications doivent être en mesure d'obtenir les modifications suivies, d'appliquer ces modifications à une autre banque de données et de mettre à jour la base de données source.</span><span class="sxs-lookup"><span data-stu-id="95323-103">Applications that use change tracking must be able to obtain tracked changes, apply these changes to another data store, and update the source database.</span></span> <span data-ttu-id="95323-104">Cette rubrique explique comment effectuer ces tâches et le rôle joué par le suivi des modifications lorsqu'un basculement se produit et qu'une base de données doit être restaurée à partir d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="95323-104">This topic describes how to perform these tasks, and also the role change tracking plays when a failover occurs and a database must be restored from a backup.</span></span>  
  
##  <a name="obtain-changes-by-using-change-tracking-functions"></a><a name="Obtain"></a> <span data-ttu-id="95323-105">Obtenir les modifications à l'aide des fonctions de suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="95323-105">Obtain Changes by Using Change Tracking Functions</span></span>  
 <span data-ttu-id="95323-106">Explique comment utiliser les fonctions de suivi des modifications pour obtenir des modifications et les informations sur les modifications apportées à une base de données.</span><span class="sxs-lookup"><span data-stu-id="95323-106">Describes how to use the change tracking functions to obtain changes and information about the changes that were made to a database.</span></span>  
  
### <a name="about-the-change-tracking-functions"></a><span data-ttu-id="95323-107">À propos des fonctions de suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="95323-107">About the Change Tracking Functions</span></span>  
 <span data-ttu-id="95323-108">Les applications peuvent utiliser les fonctions suivantes pour obtenir les modifications apportées à une base de données et les informations concernant ces modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-108">Applications can use the following functions to obtain the changes that are made in a database and information about the changes:</span></span>  
  
 <span data-ttu-id="95323-109">Fonction CHANGETABLE(CHANGES ...)</span><span class="sxs-lookup"><span data-stu-id="95323-109">CHANGETABLE(CHANGES ...) function</span></span>  
 <span data-ttu-id="95323-110">Cette fonction d'ensemble de lignes permet d'exécuter des requêtes d'informations de modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-110">This rowset function is used to query for change information.</span></span> <span data-ttu-id="95323-111">Elle interroge les données stockées dans les tables de suivi des modifications internes.</span><span class="sxs-lookup"><span data-stu-id="95323-111">The function queries the data stored in the internal change tracking tables.</span></span> <span data-ttu-id="95323-112">Elle renvoie un jeu de résultats qui contient les clés primaires des lignes qui ont changé, ainsi que d'autres informations de modification telles que l'opération, les colonnes mises à jour et la version de la ligne.</span><span class="sxs-lookup"><span data-stu-id="95323-112">The function returns a results set that contains the primary keys of rows that have changed together with other change information such as the operation, columns updated and version for the row.</span></span>  
  
 <span data-ttu-id="95323-113">La fonction CHANGETABLE(CHANGES ...) prend une dernière version de synchronisation comme argument.</span><span class="sxs-lookup"><span data-stu-id="95323-113">CHANGETABLE(CHANGES ...) takes a last synchronization version as an argument.</span></span> <span data-ttu-id="95323-114">La dernière version de synchronisation est obtenue à l'aide de la variable `@last_synchronization_version` .</span><span class="sxs-lookup"><span data-stu-id="95323-114">The last sychronization version is obtained using the `@last_synchronization_version` variable.</span></span> <span data-ttu-id="95323-115">La sémantique de la dernière version de synchronisation est la suivante :</span><span class="sxs-lookup"><span data-stu-id="95323-115">The semantics of the last synchronization version are as follows:</span></span>  
  
-   <span data-ttu-id="95323-116">Le client appelant a obtenu les modifications et connaît toutes les modifications jusqu'à la dernière version de synchronisation comprise.</span><span class="sxs-lookup"><span data-stu-id="95323-116">The calling client has obtained changes and knows about all changes up to and including the last synchronization version.</span></span>  
  
-   <span data-ttu-id="95323-117">La fonction CHANGETABLE(CHANGES ...) retourne par conséquent toutes les modifications qui se sont produites après la dernière version de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="95323-117">CHANGETABLE(CHANGES ...) will therefore return all changes that have occurred after the last synchronization version.</span></span>  
  
     <span data-ttu-id="95323-118">L’illustration suivante montre comment CHANGETABLE(CHANGES ...) est utilisée pour obtenir des modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-118">The following illustration shows how CHANGETABLE(CHANGES ...) is used to obtain changes.</span></span>  
  
     <span data-ttu-id="95323-119">![Exemple de résultat de requête du suivi des modifications](../../database-engine/media/queryoutput.gif "Exemple de résultat de requête du suivi des modifications")</span><span class="sxs-lookup"><span data-stu-id="95323-119">![Example of change tracking query output](../../database-engine/media/queryoutput.gif "Example of change tracking query output")</span></span>  
  
 <span data-ttu-id="95323-120">Fonction CHANGE_TRACKING_CURRENT_VERSION()</span><span class="sxs-lookup"><span data-stu-id="95323-120">CHANGE_TRACKING_CURRENT_VERSION() function</span></span>  
 <span data-ttu-id="95323-121">Permet d'obtenir la version actuelle qui sera utilisée la prochaine fois lorsque l'interrogation change.</span><span class="sxs-lookup"><span data-stu-id="95323-121">Is used to obtain the current version that will be used the next time when querying changes.</span></span> <span data-ttu-id="95323-122">Cette version représente la version de la dernière transaction validée.</span><span class="sxs-lookup"><span data-stu-id="95323-122">This version represents the version of the last committed transaction.</span></span>  
  
 <span data-ttu-id="95323-123">Fonction CHANGE_TRACKING_MIN_VALID_VERSION()</span><span class="sxs-lookup"><span data-stu-id="95323-123">CHANGE_TRACKING_MIN_VALID_VERSION()function</span></span>  
 <span data-ttu-id="95323-124">Permet d'obtenir la version valide minimale qu'un client doit avoir pour obtenir des résultats valides à partir de CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="95323-124">Is used to obtain the minimum valid version that a client can have and still obtain valid results from CHANGETABLE().</span></span> <span data-ttu-id="95323-125">Le client doit vérifier la dernière version de synchronisation par rapport à la valeur renvoyée par cette fonction.</span><span class="sxs-lookup"><span data-stu-id="95323-125">The client should check the last synchronization version against the value thatis returned by this function.</span></span> <span data-ttu-id="95323-126">Si la dernière version de synchronisation est inférieure à la version retournée par cette fonction, le client ne pourra pas obtenir de résultats valides de CHANGETABLE() et devra effectuer une réinitialisation.</span><span class="sxs-lookup"><span data-stu-id="95323-126">If the last synchronization version is less than the version returned by this function, the client will be unable to obtain valid results from CHANGETABLE() and will have to reinitialize.</span></span>  
  
### <a name="obtaining-initial-data"></a><span data-ttu-id="95323-127">Obtention des données initiales</span><span class="sxs-lookup"><span data-stu-id="95323-127">Obtaining Initial Data</span></span>  
 <span data-ttu-id="95323-128">Pour pouvoir obtenir des modifications pour la première fois, une application doit envoyer une requête afin d'obtenir les données initiales et la version de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="95323-128">Before an application can obtain changes for the first time, the application must send a query to obtain the initial data and the synchronization version.</span></span> <span data-ttu-id="95323-129">L'application doit obtenir les données appropriées directement à partir de la table, puis utiliser CHANGE_TRACKING_CURRENT_VERSION() pour obtenir la version initiale.</span><span class="sxs-lookup"><span data-stu-id="95323-129">The application must obtain the appropriate data directly from the table, and then use CHANGE_TRACKING_CURRENT_VERSION() to obtain the initial version.</span></span> <span data-ttu-id="95323-130">Cette version sera passée à CHANGETABLE (CHANGES ...) la première fois que des modifications seront obtenues.</span><span class="sxs-lookup"><span data-stu-id="95323-130">This version will be passed to CHANGETABLE(CHANGES ...) the first time that changes are obtained.</span></span>  
  
 <span data-ttu-id="95323-131">L'exemple suivant montre comment obtenir la version de synchronisation initiale et le jeu de données initial.</span><span class="sxs-lookup"><span data-stu-id="95323-131">The following example shows how to obtain the initial synchronization version and the initial data set.</span></span>  
  
```sql  
    -- Obtain the current synchronization version. This will be used next time that changes are obtained.  
    SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
    -- Obtain initial data set.  
    SELECT  
        P.ProductID, P.Name, P.ListPrice  
    FROM  
        SalesLT.Product AS P  
```  
  
### <a name="using-the-change-tracking-functions-to-obtain-changes"></a><span data-ttu-id="95323-132">Utilisation de fonctions de suivi des modifications pour obtenir des modifications</span><span class="sxs-lookup"><span data-stu-id="95323-132">Using the Change Tracking Functions to Obtain Changes</span></span>  
 <span data-ttu-id="95323-133">Pour obtenir les lignes modifiées d’une table ainsi que des informations sur les modifications, utilisez CHANGETABLE(CHANGES...). Par exemple, la requête suivante obtient les modifications pour la table `SalesLT.Product` .</span><span class="sxs-lookup"><span data-stu-id="95323-133">To obtain the changed rows for a table and information about the changes, use CHANGETABLE(CHANGES...). For example, the following query obtains changes for the `SalesLT.Product` table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, CT.SYS_CHANGE_OPERATION,  
    CT.SYS_CHANGE_COLUMNS, CT.SYS_CHANGE_CONTEXT  
FROM  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
  
```  
  
 <span data-ttu-id="95323-134">Habituellement, un client souhaite obtenir les données les plus récentes d'une ligne plutôt qu'uniquement les clés primaires de la ligne.</span><span class="sxs-lookup"><span data-stu-id="95323-134">Usually, a client will want to obtain the latest data for a row instead of only the primary keys for the row.</span></span> <span data-ttu-id="95323-135">Par conséquent, une application doit joindre les résultats de CHANGETABLE(CHANGES ...) aux données de la table utilisateur.</span><span class="sxs-lookup"><span data-stu-id="95323-135">Therefore, an application would join the results from CHANGETABLE(CHANGES ...) with the data in the user table.</span></span> <span data-ttu-id="95323-136">Par exemple, la requête suivante établit une jointure avec la table `SalesLT.Product` afin d'obtenir les valeurs des colonnes `Name` et `ListPrice` .</span><span class="sxs-lookup"><span data-stu-id="95323-136">For example, the following query joins with the `SalesLT.Product` table to obtain the values for the `Name` and `ListPrice` columns.</span></span> <span data-ttu-id="95323-137">Notez l'utilisation de `OUTER JOIN`.</span><span class="sxs-lookup"><span data-stu-id="95323-137">Note the use of `OUTER JOIN`.</span></span> <span data-ttu-id="95323-138">Cela est nécessaire afin de s'assurer que les informations relatives aux modifications sont retournées pour les lignes qui ont été supprimées de la table utilisateur.</span><span class="sxs-lookup"><span data-stu-id="95323-138">This is required to make sure that the change information is returned for those rows that have been deleted from the user table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
 <span data-ttu-id="95323-139">Pour obtenir la version à utiliser dans l'énumération de modification suivante, utilisez CHANGE_TRACKING_CURRENT_VERSION(), comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="95323-139">To obtain the version for use in the next change enumeration, use CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION()  
```  
  
 <span data-ttu-id="95323-140">Quand une application obtient des modifications, elle doit utiliser à la fois CHANGETABLE(CHANGES ...) et CHANGE_TRACKING_CURRENT_VERSION(), comme indiqué dans l’exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="95323-140">When an application obtains changes, it must use both CHANGETABLE(CHANGES...) and CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
-- Obtain the current synchronization version. This will be used the next time CHANGETABLE(CHANGES...) is called.  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
-- Obtain incremental changes by using the synchronization version obtained the last time the data was synchronized.  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
### <a name="version-numbers"></a><span data-ttu-id="95323-141">Numéros de versions</span><span class="sxs-lookup"><span data-stu-id="95323-141">Version Numbers</span></span>  
 <span data-ttu-id="95323-142">Une base de données pour laquelle le suivi des modifications est activé possède un compteur de version qui s'incrémente à mesure que des modifications sont apportées afin de modifier des tables faisant l'objet d'un suivi.</span><span class="sxs-lookup"><span data-stu-id="95323-142">A database that has change tracking enabled has a version counter that increases as changes are made to change tracked tables.</span></span> <span data-ttu-id="95323-143">Chaque ligne modifiée comporte un numéro de version associé.</span><span class="sxs-lookup"><span data-stu-id="95323-143">Each changed row has a version number that is associated with it.</span></span> <span data-ttu-id="95323-144">Lorsqu'une demande est envoyée à une application afin de connaître les modifications, une fonction fournissant un numéro de version est appelée.</span><span class="sxs-lookup"><span data-stu-id="95323-144">When a request is sent to an application to query for changes, a function is called that supplies a version number.</span></span> <span data-ttu-id="95323-145">La fonction retourne des informations à propos de toutes les modifications apportées depuis cette version.</span><span class="sxs-lookup"><span data-stu-id="95323-145">The function returns information about all the changes that have been made since that version.</span></span> <span data-ttu-id="95323-146">À certains égards, le concept de version de suivi des modifications est semblable au type de données `rowversion`.</span><span class="sxs-lookup"><span data-stu-id="95323-146">In some ways, change tracking version is similar in concept to the `rowversion` data type.</span></span>  
  
### <a name="validating-the-last-synchronized-version"></a><span data-ttu-id="95323-147">Validation de la dernière version synchronisée</span><span class="sxs-lookup"><span data-stu-id="95323-147">Validating the Last Synchronized Version</span></span>  
 <span data-ttu-id="95323-148">Les informations relatives aux modifications sont maintenues pour une durée limitée.</span><span class="sxs-lookup"><span data-stu-id="95323-148">Information about changes is maintained for a limited time.</span></span> <span data-ttu-id="95323-149">Cette durée est contrôlée par le paramètre CHANGE_RETENTION qui peut être spécifié dans le cadre d'ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="95323-149">The length of time is controlled by the CHANGE_RETENTION parameter that can be specified as part of the ALTER DATABASE.</span></span>  
  
 <span data-ttu-id="95323-150">Notez que la durée spécifiée pour CHANGE_RETENTION détermine la fréquence à laquelle toutes les applications doivent demander des modifications à la base de données.</span><span class="sxs-lookup"><span data-stu-id="95323-150">Be aware that the time specified for CHANGE_RETENTION determines how frequently all applications must request changes from the database.</span></span> <span data-ttu-id="95323-151">Si une application a une valeur de *last_synchronization_version* antérieure à la version de synchronisation minimale valide pour une table, cette application ne peut pas effectuer d’énumération de modification valide.</span><span class="sxs-lookup"><span data-stu-id="95323-151">If an application has a value for *last_synchronization_version* that is older than the minimum valid synchronization version for a table, that application cannot perform valid change enumeration.</span></span> <span data-ttu-id="95323-152">Cela est dû au fait que certaines informations de modification ont pu être nettoyées.</span><span class="sxs-lookup"><span data-stu-id="95323-152">This is because some change information might have been cleaned up.</span></span> <span data-ttu-id="95323-153">Avant d’obtenir des modifications à l’aide de CHANGETABLE(CHANGES ...), l’application doit valider la valeur de *last_synchronization_version* qu’elle prévoit de passer à CHANGETABLE(CHANGES ...). Si la valeur de *last_synchronization_version* n’est pas valide, cette application doit réinitialiser toutes les données.</span><span class="sxs-lookup"><span data-stu-id="95323-153">Before an application obtains changes by using CHANGETABLE(CHANGES ...), the application must validate the value for *last_synchronization_version* that it plans to pass to CHANGETABLE(CHANGES ...). If the value of *last_synchronization_version* is not valid, that application must reinitialize all the data.</span></span>  
  
 <span data-ttu-id="95323-154">L'exemple suivant montre vérifier la validité de la valeur de `last_synchronization_version` pour chaque table.</span><span class="sxs-lookup"><span data-stu-id="95323-154">The following example shows how to verify the validity of the value of `last_synchronization_version` for each table.</span></span>  
  
```sql  
-- Check individual table.  
IF (@last_synchronization_version < CHANGE_TRACKING_MIN_VALID_VERSION(  
                                   OBJECT_ID('SalesLT.Product')))  
BEGIN  
  -- Handle invalid version and do not enumerate changes.  
  -- Client must be reinitialized.  
END  
```  
  
 <span data-ttu-id="95323-155">Comme l'exemple suivant le montre, la validation de la valeur de `last_synchronization_version` peut être vérifiée par rapport à toutes les tables de la base de données.</span><span class="sxs-lookup"><span data-stu-id="95323-155">As the following example shows, the validity of the value of `last_synchronization_version` can be checked against all tables in the database.</span></span>  
  
```sql  
-- Check all tables with change tracking enabled  
IF EXISTS (  
  SELECT COUNT(*) FROM sys.change_tracking_tables  
  WHERE min_valid_version > @last_synchronization_version )  
BEGIN  
  -- Handle invalid version & do not enumerate changes  
  -- Client must be reinitialized  
END  
```  
  
### <a name="using-column-tracking"></a><span data-ttu-id="95323-156">Utilisation du suivi de colonne</span><span class="sxs-lookup"><span data-stu-id="95323-156">Using Column Tracking</span></span>  
 <span data-ttu-id="95323-157">Le suivi de colonne permet aux applications d'obtenir les données relatives uniquement aux colonnes qui ont changé, plutôt que la ligne entière.</span><span class="sxs-lookup"><span data-stu-id="95323-157">Column tracking enables applications to obtain the data for only the columns that have changed instead of the whole row.</span></span> <span data-ttu-id="95323-158">Par exemple, considérez le scénario dans lequel une table possède une ou plusieurs grandes colonnes qui sont rarement modifiées et d'autres colonnes qui changent fréquemment.</span><span class="sxs-lookup"><span data-stu-id="95323-158">For example, consider the scenario in which a table has one or more columns that are large, but rarely change; and also has other columns that frequently change.</span></span> <span data-ttu-id="95323-159">Sans le suivi de colonne, une application peut déterminer uniquement qu'une ligne a changé et elle doit synchroniser toutes les données, y compris celles des grandes colonnes.</span><span class="sxs-lookup"><span data-stu-id="95323-159">Without column tracking, an application can only determine that a row has changed and would have to synchronize all the data that includes the large column data.</span></span> <span data-ttu-id="95323-160">Grâce au suivi de colonne, une application peut déterminer si les données des grandes colonnes ont changé et synchroniser les données uniquement si elles ont changé.</span><span class="sxs-lookup"><span data-stu-id="95323-160">However, by using column tracking, an application can determine whether the large column data changed and only synchronize the data if it has changed.</span></span>  
  
 <span data-ttu-id="95323-161">Les informations de suivi de colonne apparaissent dans la colonne SYS_CHANGE_COLUMNS retournée par la fonction CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-161">Column tracking information appears in the SYS_CHANGE_COLUMNS column that is returned by the CHANGETABLE(CHANGES ...) function.</span></span>  
  
 <span data-ttu-id="95323-162">Le suivi de colonne peut être utilisé de sorte que NULL soit retourné pour une colonne qui n'a pas changé.</span><span class="sxs-lookup"><span data-stu-id="95323-162">Column tracking can be used so that NULL is returned for a column that has not changed.</span></span> <span data-ttu-id="95323-163">Si la colonne peut prendre la valeur NULL, une colonne séparée doit être retournée afin d'indiquer si la colonne a changé.</span><span class="sxs-lookup"><span data-stu-id="95323-163">If the column can be changed to NULL, a separate column must be returned to indicate whether the column changed.</span></span>  
  
 <span data-ttu-id="95323-164">Dans l'exemple suivant, la colonne `CT_ThumbnailPhoto` sera `NULL` si elle n'a pas changé.</span><span class="sxs-lookup"><span data-stu-id="95323-164">In the following example, the `CT_ThumbnailPhoto` column will be `NULL` if that column did not change.</span></span> <span data-ttu-id="95323-165">Elle pourrait également être `NULL` si elle a pris la valeur `NULL` ; l'application peut utiliser `CT_ThumbNailPhoto_Changed` afin de déterminer si la colonne a changé.</span><span class="sxs-lookup"><span data-stu-id="95323-165">This column could also be `NULL` because it was changed to `NULL` - the application can use the `CT_ThumbNailPhoto_Changed` column to determine whether the column changed.</span></span>  
  
```sql  
DECLARE @PhotoColumnId int = COLUMNPROPERTY(  
    OBJECT_ID('SalesLT.Product'),'ThumbNailPhoto', 'ColumnId')  
  
SELECT  
    CT.ProductID, P.Name, P.ListPrice, -- Always obtain values.  
    CASE  
           WHEN CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) = 1  
            THEN ThumbNailPhoto  
            ELSE NULL  
      END AS CT_ThumbNailPhoto,  
      CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) AS  
                                   CT_ThumbNailPhoto_Changed  
     CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
     CT.SYS_CHANGE_CONTEXT  
FROM  
     SalesLT.Product AS P  
INNER JOIN  
     CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
     P.ProductID = CT.ProductID AND  
     CT.SYS_CHANGE_OPERATION = 'U'  
```  
  
### <a name="obtaining-consistent-and-correct-results"></a><span data-ttu-id="95323-166">Obtention de résultats cohérents et corrects</span><span class="sxs-lookup"><span data-stu-id="95323-166">Obtaining Consistent and Correct Results</span></span>  
 <span data-ttu-id="95323-167">L'obtention des données modifiées pour une table requiert plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="95323-167">Obtaining the changed data for a table requires multiple steps.</span></span> <span data-ttu-id="95323-168">Sachez que des résultats incohérents ou incorrects peuvent être retournés si certains problèmes ne sont pas pris en compte et résolus.</span><span class="sxs-lookup"><span data-stu-id="95323-168">Be aware that inconsistent or incorrect results could be returned if certain issues are not considered and handled.</span></span>  
  
 <span data-ttu-id="95323-169">Par exemple, pour obtenir les modifications apportées à une table Sales et une table SalesOrders, une application doit effectuer les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="95323-169">For example, to obtain the changes that were made to a Sales table and SalesOrders table, an application would perform the following steps:</span></span>  
  
1.  <span data-ttu-id="95323-170">Valider la dernière version synchronisée à l'aide de CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="95323-170">Validate the last synchronized version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
2.  <span data-ttu-id="95323-171">Obtenir la version qui peut être utilisée pour obtenir les modifications lors de la prochaine interrogation à l'aide de CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="95323-171">Obtain the version that can be used to obtain change the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
3.  <span data-ttu-id="95323-172">Obtenez les modifications de la table Sales à l’aide de CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-172">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...).</span></span>  
  
4.  <span data-ttu-id="95323-173">Obtenez les modifications de la table SalesOrders à l’aide de CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-173">Obtain the changes for the SalesOrders table by using CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="95323-174">Deux processus qui se produisent dans la base de données peuvent affecter les résultats retournés par les étapes précédentes :</span><span class="sxs-lookup"><span data-stu-id="95323-174">Two processes are occurring in the database that can affect the results that are returned by the previous steps:</span></span>  
  
-   <span data-ttu-id="95323-175">Le processus de nettoyage s'exécute en arrière-plan et supprime les informations de suivi des modifications antérieures à la période de rétention spécifiée.</span><span class="sxs-lookup"><span data-stu-id="95323-175">The cleanup process runs in the background and removes change tracking information that is older than the specified retention period.</span></span>  
  
     <span data-ttu-id="95323-176">Le processus de nettoyage est un processus d'arrière-plan distinct qui utilise la période de rétention spécifiée lorsque vous configurez le suivi des modifications pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="95323-176">The cleanup process is a separate background process that uses the retention period that is specified when you configure change tracking for the database.</span></span> <span data-ttu-id="95323-177">Le problème réside dans le fait que le processus de nettoyage peut se produire entre la validation de la dernière version de synchronisation et l’appel à CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-177">The issue is that the cleanup process can occur in the time between when the last synchronization version was validated and when the call to CHANGETABLE(CHANGES...) is made.</span></span> <span data-ttu-id="95323-178">Une dernière version de synchronisation qui était juste valide peut ne plus l'être au moment où les modifications sont obtenues.</span><span class="sxs-lookup"><span data-stu-id="95323-178">A last synchronization version that was just valid might no longer be valid by the time the changes are obtained.</span></span> <span data-ttu-id="95323-179">Par conséquent, des résultats incorrects peuvent être retournés.</span><span class="sxs-lookup"><span data-stu-id="95323-179">Therefore, incorrect results might be returned.</span></span>  
  
-   <span data-ttu-id="95323-180">Des opérations DML sont en cours dans les tables Sales et SalesOrders, telles que les suivantes :</span><span class="sxs-lookup"><span data-stu-id="95323-180">Ongoing DML operations are occurring in the Sales and SalesOrders tables, such as the following operations:</span></span>  
  
    -   <span data-ttu-id="95323-181">Des modifications peuvent être apportées aux tables après que la version pour la prochaine fois a été obtenue à l'aide de CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="95323-181">Changes can be made to the tables after the version for next time has been obtained by using CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="95323-182">Par conséquent, le nombre de modifications retournées peut être plus important que prévu.</span><span class="sxs-lookup"><span data-stu-id="95323-182">Therefore, more changes can be returned than expected.</span></span>  
  
    -   <span data-ttu-id="95323-183">Une transaction pourrait être validée entre l'appel visant à obtenir les modifications de la table Sales et l'appel visant à obtenir les modifications de la table SalesOrders.</span><span class="sxs-lookup"><span data-stu-id="95323-183">A transaction could commit in the time between the call to obtain changes from the Sales table and the call to obtain changes from the SalesOrders table.</span></span> <span data-ttu-id="95323-184">Par conséquent, les résultats de la table SalesOrder pourraient avoir une valeur de clé étrangère qui n'existe pas dans la table Sales.</span><span class="sxs-lookup"><span data-stu-id="95323-184">Therefore, the results for the SalesOrder table could have foreign key value that does not exist in the Sales table.</span></span>  
  
 <span data-ttu-id="95323-185">Pour éviter de rencontrer les problèmes mentionnés ci-dessus, nous vous recommandons d'utiliser le niveau d'isolement d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-185">To overcome the previously listed challenges, we recommend that you use snapshot isolation.</span></span> <span data-ttu-id="95323-186">Cela contribue à garantir la cohérence des informations de modification et à éviter les conditions de concurrence liées à la tâche de nettoyage en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="95323-186">This will help to ensure consistency of change information and avoid race conditions that are related to the background cleanup task.</span></span> <span data-ttu-id="95323-187">Si vous n'utilisez pas de transactions d'instantané, le développement d'une application qui utilise le suivi des modifications peut nécessiter davantage d'efforts.</span><span class="sxs-lookup"><span data-stu-id="95323-187">If you do not use snapshot transactions, developing an application that uses change tracking could require significantly more effort.</span></span>  
  
#### <a name="using-snapshot-isolation"></a><span data-ttu-id="95323-188">Utilisation du niveau d'isolement d'instantané</span><span class="sxs-lookup"><span data-stu-id="95323-188">Using Snapshot Isolation</span></span>  
 <span data-ttu-id="95323-189">Le suivi des modifications a été conçu pour une bonne intégration au niveau d'isolement d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-189">Change tracking has been designed to work well with snapshot isolation.</span></span> <span data-ttu-id="95323-190">Le niveau d'isolement d'instantané doit être activé pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="95323-190">Snapshot isolation must be enabled for the database.</span></span> <span data-ttu-id="95323-191">Toutes les étapes requises pour obtenir des modifications doivent être incluses à l'intérieur d'une transaction d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-191">All the steps that are required to obtain changes must be included inside a snapshot transaction.</span></span> <span data-ttu-id="95323-192">Cela permet de s'assurer que toutes les modifications apportées aux données durant l'obtention de modifications seront invisibles aux requêtes à l'intérieur de la transaction d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-192">This will ensure that all changes that are made to data while obtaining changes will not be visible to the queries inside the snapshot transaction.</span></span>  
  
 <span data-ttu-id="95323-193">Pour obtenir des données à l'intérieur d'une transaction d'instantané, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="95323-193">To obtain data inside a snapshot transaction, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="95323-194">Définissez le niveau d'isolation de la transaction à « instantané » et démarrez une transaction.</span><span class="sxs-lookup"><span data-stu-id="95323-194">Set the transaction isolation level to snapshot and start a transaction.</span></span>  
  
2.  <span data-ttu-id="95323-195">Validez la dernière version de synchronisation à l'aide de CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="95323-195">Validate the last synchronization version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
3.  <span data-ttu-id="95323-196">Obtenez la version à utiliser lors de la prochaine interrogation à l'aide de CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="95323-196">Obtain the version to be used the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
4.  <span data-ttu-id="95323-197">Obtenez les modifications de la table Sales à l’aide de CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-197">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...)</span></span>  
  
5.  <span data-ttu-id="95323-198">Obtenez les modifications de la table SalesOrders à l’aide de CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-198">Obtain the changes for the Salesorders table by using CHANGETABLE(CHANGES ...)</span></span>  
  
6.  <span data-ttu-id="95323-199">Validez la transaction.</span><span class="sxs-lookup"><span data-stu-id="95323-199">Commit the transaction.</span></span>  
  
 <span data-ttu-id="95323-200">Quelques points à noter étant donné que toutes les étapes d'obtention de modifications ont lieu à l'intérieur d'une transaction d'instantané :</span><span class="sxs-lookup"><span data-stu-id="95323-200">Some points to remember as all steps to obtain changes are inside a snapshot transaction:</span></span>  
  
-   <span data-ttu-id="95323-201">Si le nettoyage se produit après la validation de la dernière version de synchronisation, les résultats de CHANGETABLE(CHANGES ...) seront tout de même valides, car les opérations de suppression effectuées par le nettoyage ne seront pas visibles à l’intérieur de la transaction.</span><span class="sxs-lookup"><span data-stu-id="95323-201">If cleanup occurs after the last synchronization version is validated, the results from CHANGETABLE(CHANGES ...) will still be valid as the delete operations performed by cleanup will not be visible inside the transaction.</span></span>  
  
-   <span data-ttu-id="95323-202">Toute modification apportée à la table Sales ou SalesOrders après l’obtention de la version de synchronisation suivante sera invisible et les appels à CHANGETABLE(CHANGES ...) ne retourneront jamais de modifications avec une version ultérieure à celle retournée par CHANGE_TRACKING_CURRENT_VERSION().</span><span class="sxs-lookup"><span data-stu-id="95323-202">Any changes that are made to the Sales table or the SalesOrders table after the next synchronization version is obtained will not be visible, and the calls to CHANGETABLE(CHANGES ...) will never return changes with a version later than that returned by CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="95323-203">La cohérence entre la table Sales et la table SalesOrders sera aussi maintenue, car les transactions validées entre les appels à CHANGETABLE(CHANGES ...) ne seront pas visibles.</span><span class="sxs-lookup"><span data-stu-id="95323-203">Consistency between the Sales table and the SalesOrders table will also be maintained, because the transactions that were committed in the time between calls to CHANGETABLE(CHANGES ...) will not be visible.</span></span>  
  
 <span data-ttu-id="95323-204">L'exemple ci-dessous montre comment le niveau d'isolement d'instantané est activé pour une base de données.</span><span class="sxs-lookup"><span data-stu-id="95323-204">The following example shows how snapshot isolation is enabled for a database.</span></span>  
  
```sql  
-- The database must be configured to enable snapshot isolation.  
ALTER DATABASE AdventureWorksLT  
    SET ALLOW_SNAPSHOT_ISOLATION ON;  
```  
  
 <span data-ttu-id="95323-205">Une transaction d'instantané est utilisée comme suit :</span><span class="sxs-lookup"><span data-stu-id="95323-205">A snapshot transaction is used as follows:</span></span>  
  
```sql  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
  -- Verify that version of the previous synchronization is valid.  
  -- Obtain the version to use next time.  
  -- Obtain changes.  
COMMIT TRAN  
```  
  
 <span data-ttu-id="95323-206">Pour plus d’informations sur les transactions d’instantanés, consultez [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="95323-206">For more information about snapshot transactions, see [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
#### <a name="alternatives-to-using-snapshot-isolation"></a><span data-ttu-id="95323-207">Alternatives à l'utilisation du niveau d'isolement d'instantané</span><span class="sxs-lookup"><span data-stu-id="95323-207">Alternatives to Using Snapshot Isolation</span></span>  
 <span data-ttu-id="95323-208">Il existe des alternatives à l'utilisation du niveau d'isolement d'instantané, mais elles nécessitent davantage de travail afin de s'assurer que toutes les spécifications d'applications sont satisfaites.</span><span class="sxs-lookup"><span data-stu-id="95323-208">There are alternatives to using snapshot isolation, but they require more work to make sure all application requirements are met.</span></span> <span data-ttu-id="95323-209">Pour vérifier que le paramètre *last_synchronization_version* est valide et qu’aucune donnée n’est supprimée par le processus de nettoyage avant l’obtention des modifications, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="95323-209">To make sure the *last_synchronization_version* is valid and data is not removed by the cleanup process before changes are obtained, do the following:</span></span>  
  
1.  <span data-ttu-id="95323-210">Vérifiez *last_synchronization_version* après les appels à CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="95323-210">Check *last_synchronization_version* after the calls to CHANGETABLE().</span></span>  
  
2.  <span data-ttu-id="95323-211">Vérifiez *last_synchronization_version* dans le cadre de chaque requête d’obtention de modifications à l’aide de CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="95323-211">Check *last_synchronization_version* as part of each query to obtain changes by using CHANGETABLE().</span></span>  
  
 <span data-ttu-id="95323-212">Des modifications peuvent se produire après l'obtention de la version de synchronisation pour l'énumération suivante.</span><span class="sxs-lookup"><span data-stu-id="95323-212">Changes can occur after the synchronization version for the next enumeration has been obtained.</span></span> <span data-ttu-id="95323-213">Il existe deux manières de gérer cette situation.</span><span class="sxs-lookup"><span data-stu-id="95323-213">There are two ways to handle this situation.</span></span> <span data-ttu-id="95323-214">L'option utilisée dépend de l'application et de la façon dont elle peut gérer les effets secondaires de chaque approche :</span><span class="sxs-lookup"><span data-stu-id="95323-214">The option that is used depends on the application and how it can handle the side-effects of each approach:</span></span>  
  
-   <span data-ttu-id="95323-215">Ignorer les modifications dont la version est ultérieure à la nouvelle version de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="95323-215">Ignore changes that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="95323-216">Cette approche a comme effet secondaire qu'une ligne nouvelle ou mise à jour est ignorée si elle a été créée ou mise à jour avant la nouvelle version de synchronisation, mais qu'elle a été mise à jour par la suite.</span><span class="sxs-lookup"><span data-stu-id="95323-216">This approach has the side effect that a new or updated row would be skipped if it was created or updated before the new synchronization version, but then updated afterward.</span></span> <span data-ttu-id="95323-217">S'il y a une nouvelle ligne, un problème d'intégrité référentielle peut se produire s'il existe une ligne dans une autre table créée qui référence la ligne omise.</span><span class="sxs-lookup"><span data-stu-id="95323-217">If there is a new row, a referential integrity problem might occur if there was a row in another table that was created that referenced the skipped row.</span></span> <span data-ttu-id="95323-218">S'il y a une ligne existante mise à jour, la ligne est ignorée et synchronisée uniquement la prochaine fois.</span><span class="sxs-lookup"><span data-stu-id="95323-218">If there is an updated existing row, the row will be skipped and not synchronized until the next time.</span></span>  
  
-   <span data-ttu-id="95323-219">Inclure toutes les modifications, même celles dont la version est ultérieure à la nouvelle version de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="95323-219">Include all changes, even those that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="95323-220">Les lignes qui ont une version ultérieure à la nouvelle version de synchronisation seront encore obtenues lors de la synchronisation suivante.</span><span class="sxs-lookup"><span data-stu-id="95323-220">The rows that have a version larger than the new synchronization version will be obtained again on the next synchronization.</span></span> <span data-ttu-id="95323-221">Cela doit être attendu et géré par l'application.</span><span class="sxs-lookup"><span data-stu-id="95323-221">This must be expected and handled by the application.</span></span>  
  
 <span data-ttu-id="95323-222">En plus des deux options précédentes, vous pouvez imaginer une approche qui combine ces deux options, selon l'opération.</span><span class="sxs-lookup"><span data-stu-id="95323-222">In addition to the previous two options, you can devise approach that combines both options, depending on the operation.</span></span> <span data-ttu-id="95323-223">Par exemple, vous pourriez souhaiter avoir une application pour laquelle il vaut mieux ignorer les modifications plus récentes que la version de synchronisation suivante dans laquelle la ligne a été créée ou supprimée, mais où les mises à jour ne sont pas ignorées.</span><span class="sxs-lookup"><span data-stu-id="95323-223">For example, you might want an application for which it is best to ignore changes newer than the next synchronization version in which the row was created or deleted, but updates are not ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="95323-224">Le choix de l'approche la mieux adaptée à l'application lorsque vous utilisez le suivi des modifications (ou tout mécanisme de suivi personnalisé) requiert une analyse approfondie.</span><span class="sxs-lookup"><span data-stu-id="95323-224">Choosing the approach that will work for the application when you are using change tracking (or any custom tracking mechanism), requires significant analysis.</span></span> <span data-ttu-id="95323-225">Il est par conséquent beaucoup plus simple d'utiliser le niveau d'isolement d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-225">Therefore, it is much simpler to use snapshot isolation.</span></span>  
  
##  <a name="how-change-tracking-handles-changes-to-a-database"></a><a name="Handles"></a><span data-ttu-id="95323-226">Comment Change Tracking gère les modifications apportées à une base de données</span><span class="sxs-lookup"><span data-stu-id="95323-226">How Change Tracking Handles Changes to a Database</span></span>  
 <span data-ttu-id="95323-227">Certaines applications qui utilisent le suivi des modifications effectuent une synchronisation bidirectionnelle avec une autre banque de données.</span><span class="sxs-lookup"><span data-stu-id="95323-227">Some applications that use change tracking perform two-way synchronization with another data store.</span></span> <span data-ttu-id="95323-228">Autrement dit, les modifications apportées à la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont mises à jour dans l'autre banque de données et les modifications apportées à l'autre banque sont mises à jour dans la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="95323-228">That is, changes that are made in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database are updated in the other data store, and changes that are made in the other store are updated in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="95323-229">Lorsqu'une application met à jour la base de données locale avec les modifications d'une autre banque de données, elle doit effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="95323-229">When an application updates the local database with changes from another data store, the application must perform the following operations:</span></span>  
  
-   <span data-ttu-id="95323-230">Recherche de conflits.</span><span class="sxs-lookup"><span data-stu-id="95323-230">Check for conflicts.</span></span>  
  
     <span data-ttu-id="95323-231">Un conflit se produit lorsque les mêmes données sont modifiées simultanément dans les deux banques de données.</span><span class="sxs-lookup"><span data-stu-id="95323-231">A conflict occurs when the same data is changed at the same time in both data stores.</span></span> <span data-ttu-id="95323-232">L'application doit être en mesure de vérifier s'il existe un conflit et d'obtenir suffisamment d'informations pour permettre la résolution du conflit.</span><span class="sxs-lookup"><span data-stu-id="95323-232">The application must be able to check for a conflict and obtain enough information to enable the conflict to be resolved.</span></span>  
  
-   <span data-ttu-id="95323-233">Stockage d'informations de contexte d'application.</span><span class="sxs-lookup"><span data-stu-id="95323-233">Store application context information.</span></span>  
  
     <span data-ttu-id="95323-234">L'application stocke des données qui contiennent les informations de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-234">The application stores data that has the change tracking information.</span></span> <span data-ttu-id="95323-235">Ces informations (ainsi que d'autres informations de suivi des modifications) sont disponibles lorsque les modifications sont obtenues à partir de la base de données locale.</span><span class="sxs-lookup"><span data-stu-id="95323-235">This information would be available together with other change tracking information when changes were obtained from the local database.</span></span> <span data-ttu-id="95323-236">Un exemple courant d'information contextuelle de ce type est un identificateur pour la banque de données qui était la source de la modification.</span><span class="sxs-lookup"><span data-stu-id="95323-236">A common example of this contextual information is an identifier for the data store that was the source of the change.</span></span>  
  
 <span data-ttu-id="95323-237">Pour effectuer les opérations précédentes, une application de synchronisation peut utiliser les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="95323-237">To perform the previous operations, a synchronization application can use the following functions:</span></span>  
  
-   <span data-ttu-id="95323-238">CHANGETABLE(VERSION...)</span><span class="sxs-lookup"><span data-stu-id="95323-238">CHANGETABLE(VERSION...)</span></span>  
  
     <span data-ttu-id="95323-239">Lorsqu'une application apporte des modifications, elle peut utiliser cette fonction pour vérifier s'il existe des conflits.</span><span class="sxs-lookup"><span data-stu-id="95323-239">When an application is making changes, it can use this function to check for conflicts.</span></span> <span data-ttu-id="95323-240">Cette fonction obtient les informations de suivi des modifications les plus récentes pour une ligne spécifiée dans une table sujette au suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-240">The function obtains the latest change tracking information for a specified row in a change tracked table.</span></span> <span data-ttu-id="95323-241">Les informations de suivi des modifications incluent la version de la dernière ligne modifiée.</span><span class="sxs-lookup"><span data-stu-id="95323-241">The change tracking information includes the version of the row that was last changed.</span></span> <span data-ttu-id="95323-242">Ces informations permettent à une application de déterminer si la ligne a été modifiée après la dernière synchronisation de l'application.</span><span class="sxs-lookup"><span data-stu-id="95323-242">This information enables an application to determine whether the row was changed after the last time that the application was synchronized.</span></span>  
  
-   <span data-ttu-id="95323-243">WITH CHANGE_TRACKING_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="95323-243">WITH CHANGE_TRACKING_CONTEXT</span></span>  
  
     <span data-ttu-id="95323-244">Une application peut utiliser cette clause pour stocker des données de contexte.</span><span class="sxs-lookup"><span data-stu-id="95323-244">An application can use this clause to store context data.</span></span>  
  
### <a name="checking-for-conflicts"></a><span data-ttu-id="95323-245">Recherche de conflits</span><span class="sxs-lookup"><span data-stu-id="95323-245">Checking for Conflicts</span></span>  
 <span data-ttu-id="95323-246">Dans un scénario de synchronisation bidirectionnelle, l'application cliente doit déterminer si une ligne n'a pas été mise à jour depuis la dernière obtention des modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-246">In a two-way synchronization scenario, the client application must determine whether a row has not been updated since the application last obtained the changes.</span></span>  
  
 <span data-ttu-id="95323-247">L’exemple suivant montre comment utiliser la fonction CHANGETABLE(VERSION ...) pour vérifier l’existence de conflits de la manière la plus efficace, sans requête distincte.</span><span class="sxs-lookup"><span data-stu-id="95323-247">The following example shows how to use the CHANGETABLE(VERSION ...) function to check for conflicts in the most efficient way, without a separate query.</span></span> <span data-ttu-id="95323-248">Dans l'exemple, `CHANGETABLE(VERSION ...)` détermine `SYS_CHANGE_VERSION` pour la ligne spécifiée par `@product id`.</span><span class="sxs-lookup"><span data-stu-id="95323-248">In the example, `CHANGETABLE(VERSION ...)` determines the `SYS_CHANGE_VERSION` for the row specified by `@product id`.</span></span> <span data-ttu-id="95323-249">`CHANGETABLE(CHANGES ...)` peut obtenir les mêmes informations, mais il est moins efficace.</span><span class="sxs-lookup"><span data-stu-id="95323-249">`CHANGETABLE(CHANGES ...)` can obtain the same information, but that would be less efficient.</span></span> <span data-ttu-id="95323-250">Si la valeur de `SYS_CHANGE_VERSION` pour la ligne est supérieure à la valeur de `@last_sync_version`, il existe un conflit.</span><span class="sxs-lookup"><span data-stu-id="95323-250">If the value of `SYS_CHANGE_VERSION` for the row is larger than the value of `@last_sync_version`, there is a conflict.</span></span> <span data-ttu-id="95323-251">En cas de conflit, la ligne ne sera pas mise à jour.</span><span class="sxs-lookup"><span data-stu-id="95323-251">If there is a conflict, the row will not be updated.</span></span> <span data-ttu-id="95323-252">Le contrôle `ISNULL()` est nécessaire car il se peut qu'il n'y ait aucune information de modification disponible pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="95323-252">The `ISNULL()` check is required because there might be no change information available for the row.</span></span> <span data-ttu-id="95323-253">Aucune information de modification n'existe si la ligne n'a pas été mise à jour depuis l'activation du suivi des modifications ou depuis le nettoyage des informations de modification.</span><span class="sxs-lookup"><span data-stu-id="95323-253">No change information would exist if the row had not been updated since change tracking was enabled or since the change information was cleaned up.</span></span>  
  
```sql  
-- Assumption: @last_sync_version has been validated.  
  
UPDATE  
    SalesLT.Product  
SET  
    ListPrice = @new_listprice  
FROM  
    SalesLT.Product AS P  
WHERE  
    ProductID = @product_id AND  
    @last_sync_version >= ISNULL (  
        SELECT CT.SYS_CHANGE_VERSION  
        FROM CHANGETABLE(VERSION SalesLT.Product,  
                        (ProductID), (P.ProductID)) AS CT),  
        0)  
```  
  
 <span data-ttu-id="95323-254">Le code suivant peut vérifier le nombre de lignes mises à jour et identifier davantage d'informations relatives au conflit.</span><span class="sxs-lookup"><span data-stu-id="95323-254">The following code can check the updated row count and can identify more information about the conflict.</span></span>  
  
```sql  
-- If the change cannot be made, find out more information.  
IF (@@ROWCOUNT = 0)  
BEGIN  
    -- Obtain the complete change information for the row.  
    SELECT  
        CT.SYS_CHANGE_VERSION, CT.SYS_CHANGE_CREATION_VERSION,  
        CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS  
    FROM  
        CHANGETABLE(CHANGES SalesLT.Product, @last_sync_version) AS CT  
    WHERE  
        CT.ProductID = @product_id;  
  
    -- Check CT.SYS_CHANGE_VERSION to verify that it really was a conflict.  
    -- Check CT.SYS_CHANGE_OPERATION to determine the type of conflict:  
    -- update-update or update-delete.  
    -- The row that is specified by @product_id might no longer exist   
    -- if it has been deleted.  
END  
```  
  
### <a name="setting-context-information"></a><span data-ttu-id="95323-255">Définition des informations de contexte</span><span class="sxs-lookup"><span data-stu-id="95323-255">Setting Context Information</span></span>  
 <span data-ttu-id="95323-256">Avec la clause WITH CHANGE_TRACKING_CONTEXT, une application peut stocker des informations de contexte avec les informations de modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-256">By using the WITH CHANGE_TRACKING_CONTEXT clause, an application can store context information together with the change information.</span></span> <span data-ttu-id="95323-257">Ces informations peuvent ensuite être obtenues à partir de la colonne SYS_CHANGE_CONTEXT retournée par CHANGETABLE(CHANGES ...).</span><span class="sxs-lookup"><span data-stu-id="95323-257">This information can then be obtained from the SYS_CHANGE_CONTEXT column that is returned by CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="95323-258">Les informations de contexte sont utilisées en général pour identifier la source des modifications.</span><span class="sxs-lookup"><span data-stu-id="95323-258">Context information is typically used to identify the source of the changes.</span></span> <span data-ttu-id="95323-259">Si la source de la modification peut être identifiée, ces informations peuvent être utilisées par une banque de données afin d'éviter d'obtenir les modifications lors de la synchronisation suivante.</span><span class="sxs-lookup"><span data-stu-id="95323-259">If the source of the change can be identified, that information can be used by a data store to avoid obtaining changes when it synchronizes again.</span></span>  
  
```sql  
  -- Try to update the row and check for a conflict.  
  WITH CHANGE_TRACKING_CONTEXT (@source_id)  
  UPDATE  
     SalesLT.Product  
  SET  
      ListPrice = @new_listprice  
  FROM  
      SalesLT.Product AS P  
  WHERE  
     ProductID = @product_id AND  
     @last_sync_version >= ISNULL (  
         (SELECT CT.SYS_CHANGE_VERSION FROM CHANGETABLE(VERSION SalesLT.Product,  
         (ProductID), (P.ProductID)) AS CT),  
         0)  
```  
  
### <a name="ensuring-consistent-and-correct-results"></a><span data-ttu-id="95323-260">Garantie de résultats cohérents et corrects</span><span class="sxs-lookup"><span data-stu-id="95323-260">Ensuring Consistent and Correct Results</span></span>  
 <span data-ttu-id="95323-261">Une application doit prendre en compte le processus de nettoyage lorsqu’elle valide la valeur de @last_sync_version.</span><span class="sxs-lookup"><span data-stu-id="95323-261">An application must consider the cleanup process when it validates the value of @last_sync_version.</span></span> <span data-ttu-id="95323-262">car des données peuvent avoir été supprimées après l'appel à CHANGE_TRACKING_MIN_VALID_VERSION() mais avant la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="95323-262">This is because data could have been removed after CHANGE_TRACKING_MIN_VALID_VERSION() was called, but before the update was made.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="95323-263">Nous vous recommandons d'utiliser le niveau d'isolement d'instantané et d'effectuer les modifications dans une transaction d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-263">We recommend that you use snapshot isolation and make the changes within a snapshot transaction.</span></span>  
  
```sql  
-- Prerequisite is to ensure ALLOW_SNAPSHOT_ISOLATION is ON for the database.  
  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
    -- Verify that last_sync_version is valid.  
    IF (@last_sync_version <  
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('SalesLT.Product')))  
    BEGIN  
       RAISERROR (N'Last_sync_version too old', 16, -1);  
    END  
    ELSE  
    BEGIN  
        -- Try to update the row.  
        -- Check @@ROWCOUNT and check for a conflict.  
    END  
COMMIT TRAN  
```  
  
> [!NOTE]  
>  <span data-ttu-id="95323-264">Il est possible que la ligne mise à jour dans le cadre de la transaction d'instantané ait été mise à jour dans une autre transaction après le démarrage de la transaction d'instantané.</span><span class="sxs-lookup"><span data-stu-id="95323-264">There is a possibility that the row being updated within the snapshot transaction could have been updated in another transaction after the snapshot transaction was started.</span></span> <span data-ttu-id="95323-265">Dans ce cas, un conflit de mise à jour du niveau d'isolement d'instantané se produit et provoque la fin de la transaction.</span><span class="sxs-lookup"><span data-stu-id="95323-265">In this case, a snapshot isolation update conflict will occur and lead to the transaction being terminated.</span></span> <span data-ttu-id="95323-266">Si cela se produit, réessayez d'effectuer la mise à jour.</span><span class="sxs-lookup"><span data-stu-id="95323-266">If this happens, retry the update.</span></span> <span data-ttu-id="95323-267">Cette tentative génère alors la détection d'un conflit de suivi des modifications et aucune ligne n'est modifiée.</span><span class="sxs-lookup"><span data-stu-id="95323-267">This will then lead to a change tracking conflict being detected and no rows being changed.</span></span>  
  
##  <a name="change-tracking-and-data-restore"></a><a name="DataRestore"></a><span data-ttu-id="95323-268">Change Tracking et restauration des données</span><span class="sxs-lookup"><span data-stu-id="95323-268">Change Tracking and Data Restore</span></span>  
 <span data-ttu-id="95323-269">Les applications qui nécessitent une synchronisation doivent considérer le cas où une base de données pour laquelle le suivi des modifications est activé rétablit une version antérieure des données.</span><span class="sxs-lookup"><span data-stu-id="95323-269">Applications that require synchronization must consider the case in which a database that has change tracking enabled reverts to an earlier version of the data.</span></span> <span data-ttu-id="95323-270">Ce cas peut se produire après la restauration d'une base de données à partir d'une sauvegarde, lors d'un basculement vers un miroir de base de données asynchrone ou lors d'un échec pendant l'utilisation de la copie des journaux de transaction.</span><span class="sxs-lookup"><span data-stu-id="95323-270">This can occur after a database is restored from a backup, when there is a failover to an asynchronous database mirror, or when there is a failure when using log shipping.</span></span> <span data-ttu-id="95323-271">Le scénario suivant illustre ce problème :</span><span class="sxs-lookup"><span data-stu-id="95323-271">The following scenario illustrates the issue:</span></span>  
  
1.  <span data-ttu-id="95323-272">La table T1 fait l'objet d'un suivi des modifications et sa version valide minimale est 50.</span><span class="sxs-lookup"><span data-stu-id="95323-272">Table T1 is change tracked, and the minimum valid version for table is 50.</span></span>  
  
2.  <span data-ttu-id="95323-273">Une application cliente synchronise les données à la version 100 et obtient des informations sur toutes les modifications entre les versions 50 et 100.</span><span class="sxs-lookup"><span data-stu-id="95323-273">A client application synchronizes data at version 100 and obtains information about all changes between versions 50 and 100.</span></span>  
  
3.  <span data-ttu-id="95323-274">Des modifications supplémentaires sont apportées à la table T1 après la version 100.</span><span class="sxs-lookup"><span data-stu-id="95323-274">Additional changes are made to table T1 after version 100.</span></span>  
  
4.  <span data-ttu-id="95323-275">À la version 120, une défaillance se produit et l'administrateur de la base de données restaure la base de données avec la perte de données.</span><span class="sxs-lookup"><span data-stu-id="95323-275">At version 120, there is a failure and the database administrator restores the database with data loss.</span></span> <span data-ttu-id="95323-276">Après l'opération de restauration, la table contient des données allant jusqu'à la version 70 et la version synchronisée minimale reste encore 50.</span><span class="sxs-lookup"><span data-stu-id="95323-276">After the restore operation, the table contains data up through version 70, and the minimum synchronized version is still 50.</span></span>  
  
     <span data-ttu-id="95323-277">Cela signifie que la banque de données synchronisée comporte des données qui n'existent plus dans la banque de données primaire.</span><span class="sxs-lookup"><span data-stu-id="95323-277">This means that the synchronized data store has data that no longer exists in the primary data store.</span></span>  
  
5.  <span data-ttu-id="95323-278">T1 est mise à jour de nombreuses fois,</span><span class="sxs-lookup"><span data-stu-id="95323-278">T1 is updated many times.</span></span> <span data-ttu-id="95323-279">ce qui porte la version actuelle à 130.</span><span class="sxs-lookup"><span data-stu-id="95323-279">This brings the current version to 130.</span></span>  
  
6.  <span data-ttu-id="95323-280">L'application cliente se synchronise de nouveau et fournit une dernière version synchronisée de 100.</span><span class="sxs-lookup"><span data-stu-id="95323-280">The client application synchronizes again and supplies a last-synchronized version of 100.</span></span> <span data-ttu-id="95323-281">Le client valide ce numéro avec succès parce que 100 est supérieur à 50.</span><span class="sxs-lookup"><span data-stu-id="95323-281">The client validates this number successfully because 100 is greater than 50.</span></span>  
  
     <span data-ttu-id="95323-282">Le client obtient les modifications entre les versions 100 et 130.</span><span class="sxs-lookup"><span data-stu-id="95323-282">The client obtains changes between version 100 and 130.</span></span> <span data-ttu-id="95323-283">À ce stade, le client n'est pas informé que les modifications entre 70 et 100 ne sont pas les mêmes qu'avant.</span><span class="sxs-lookup"><span data-stu-id="95323-283">At this point, the client is not aware that the changes between 70 and 100 are not the same as before.</span></span> <span data-ttu-id="95323-284">Les données sur le client et le serveur ne sont pas synchronisées.</span><span class="sxs-lookup"><span data-stu-id="95323-284">The data on the client and server are not synchronized.</span></span>  
  
 <span data-ttu-id="95323-285">Notez que si la base de données avait été récupérée à un point ultérieur à la version 100, il n'y aurait pas de problème de synchronisation.</span><span class="sxs-lookup"><span data-stu-id="95323-285">Note that if the database was recovered to a point after version 100, there would be no problems with synchronization.</span></span> <span data-ttu-id="95323-286">Le client et le serveur synchroniseraient correctement les données pendant l'intervalle de synchronisation suivant.</span><span class="sxs-lookup"><span data-stu-id="95323-286">The client and server would synchronize data correctly during the next synchronization interval.</span></span>  
  
 <span data-ttu-id="95323-287">Le suivi des modifications ne prend pas en charge la récupération d'une perte de données.</span><span class="sxs-lookup"><span data-stu-id="95323-287">Change tracking does not provide support for recovering from the loss of data.</span></span> <span data-ttu-id="95323-288">Toutefois, il existe deux possibilités pour détecter ces types de problèmes de synchronisation :</span><span class="sxs-lookup"><span data-stu-id="95323-288">However, there are two options for detecting these types of synchronization issues:</span></span>  
  
-   <span data-ttu-id="95323-289">Stockez un ID de version de la base de données sur le serveur, puis mettez à jour cette valeur chaque fois qu'une base de données est récupérée ou perd des données.</span><span class="sxs-lookup"><span data-stu-id="95323-289">Store a database version ID on the server, and update this value whenever a database is recovered or otherwise loses data.</span></span> <span data-ttu-id="95323-290">Chaque application cliente stocke l'ID et chaque client doit valider cet ID lorsqu'il synchronise des données.</span><span class="sxs-lookup"><span data-stu-id="95323-290">Each client application would store the ID, and each client would have to validate this ID when it synchronizes data.</span></span> <span data-ttu-id="95323-291">En cas de perte de données, les ID ne correspondront pas et les clients se réinitialiseront.</span><span class="sxs-lookup"><span data-stu-id="95323-291">If data loss occurs, the IDs will not match and the clients would reinitialize.</span></span> <span data-ttu-id="95323-292">Un inconvénient est que si la perte de données n'a pas dépassé la dernière limite synchronisée, le client risque d'effectuer une réinitialisation inutile.</span><span class="sxs-lookup"><span data-stu-id="95323-292">One drawback is if the data loss had not crossed the last synchronized boundary, the client might do unnecessary reinitialization.</span></span>  
  
-   <span data-ttu-id="95323-293">Lorsqu'un client interroge les modifications, enregistrez le numéro de version de la dernière synchronisation pour chaque client sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="95323-293">When a client queries for changes, record the last synchronization version number for each client on the server.</span></span> <span data-ttu-id="95323-294">En cas de problème avec les données, les derniers numéros de versions synchronisées ne correspondent pas.</span><span class="sxs-lookup"><span data-stu-id="95323-294">If there is a problem with the data, the last synchronized version numbers would not match.</span></span> <span data-ttu-id="95323-295">Ils indiquent qu'une réinitialisation est requise.</span><span class="sxs-lookup"><span data-stu-id="95323-295">This indicates that a reinitialization is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95323-296">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95323-296">See Also</span></span>  
 <span data-ttu-id="95323-297">[Suivi des modifications de données &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95323-297">[Track Data Changes &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="95323-298">[À propos du suivi des modifications &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95323-298">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="95323-299">[Gérer Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95323-299">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="95323-300">[Activer et désactiver les Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="95323-300">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="95323-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95323-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span></span>  
 <span data-ttu-id="95323-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95323-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span></span>  
 <span data-ttu-id="95323-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="95323-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span></span>  
 [<span data-ttu-id="95323-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="95323-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/with-change-tracking-context-transact-sql)  
  
  
