---
title: Utilitaire tablediff | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- comparing data
- tablediff utility
- tables [SQL Server replication]
- table comparisons [SQL Server]
- command prompt utilities [SQL Server], tablediff
- troubleshooting [SQL Server replication], non-convergence
- non-convergence [SQL Server]
ms.assetid: 3c3cb865-7a4d-4d66-98f2-5935e28929fc
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0a23465a7d2c7db53475a6dca81a8471a3b78b50
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704540"
---
# <a name="tablediff-utility"></a><span data-ttu-id="4af48-102">tablediff (utilitaire)</span><span class="sxs-lookup"><span data-stu-id="4af48-102">tablediff Utility</span></span>
  <span data-ttu-id="4af48-103">L’utilitaire **tablediff** sert à comparer les données dans deux tables et à identifier une non-convergence. Il est particulièrement utile pour résoudre des problèmes de non-convergence dans une topologie de réplication.</span><span class="sxs-lookup"><span data-stu-id="4af48-103">The **tablediff** utility is used to compare the data in two tables for non-convergence, and is particularly useful for troubleshooting non-convergence in a replication topology.</span></span> <span data-ttu-id="4af48-104">Cet utilitaire peut être employé à partir de l'invite de commandes ou dans un fichier de commandes pour effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="4af48-104">This utility can be used from the command prompt or in a batch file to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4af48-105">Une comparaison ligne par ligne entre une table source dans une instance de [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] agissant comme serveur de publication de réplication et la table de destination dans une ou plusieurs instances de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] agissant comme abonnés de réplication.</span><span class="sxs-lookup"><span data-stu-id="4af48-105">A row by row comparison between a source table in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as a replication Publisher and the destination table at one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] acting as replication Subscribers.</span></span>  
  
-   <span data-ttu-id="4af48-106">Comparaison rapide se limitant à la comparaison du nombre de lignes et du schéma.</span><span class="sxs-lookup"><span data-stu-id="4af48-106">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
-   <span data-ttu-id="4af48-107">Comparaisons au niveau des colonnes.</span><span class="sxs-lookup"><span data-stu-id="4af48-107">Perform column-level comparisons.</span></span>  
  
-   <span data-ttu-id="4af48-108">Génération d'un script [!INCLUDE[tsql](../includes/tsql-md.md)] pour corriger les différences sur le serveur de destination afin de mettre en convergence les tables source et de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-108">Generate a [!INCLUDE[tsql](../includes/tsql-md.md)] script to fix discrepancies at the destination server to bring the source and destination tables into convergence.</span></span>  
  
-   <span data-ttu-id="4af48-109">Consignation des résultats dans un fichier de sortie ou dans une table de la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-109">Log results to an output file or into a table in the destination database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af48-110">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="4af48-110">Syntax</span></span>  
  
```  
  
      tablediff   
[ -? ] |   
{  
        -sourceserversource_server_name[\instance_name]  
        -sourcedatabasesource_database-sourcetablesource_table_name   
    [ -sourceschemasource_schema_name ]  
    [ -sourcepasswordsource_password ]  
    [ -sourceusersource_login ]  
    [ -sourcelocked ]  
        -destinationserverdestination_server_name[\instance_name]  
        -destinationdatabasesubscription_database-destinationtabledestination_table   
    [ -destinationschemadestination_schema_name ]  
    [ -destinationpassworddestination_password ]  
    [ -destinationuserdestination_login ]  
    [ -destinationlocked ]  
    [ -blarge_object_bytes ]   
    [ -bfnumber_of_statements ]   
    [ -c ]   
    [ -dt ]   
    [ -ettable_name ]   
    [ -f [ file_name ] ]   
    [ -ooutput_file_name ]   
    [ -q ]   
    [ -rcnumber_of_retries ]   
    [ -riretry_interval ]   
    [ -strict ]  
    [ -tconnection_timeouts ]   
}  
```  
  
## <a name="arguments"></a><span data-ttu-id="4af48-111">Arguments</span><span class="sxs-lookup"><span data-stu-id="4af48-111">Arguments</span></span>  
 <span data-ttu-id="4af48-112">[ **-?**</span><span class="sxs-lookup"><span data-stu-id="4af48-112">[ **-?**</span></span> <span data-ttu-id="4af48-113">]</span><span class="sxs-lookup"><span data-stu-id="4af48-113">]</span></span>  
 <span data-ttu-id="4af48-114">Retour de la liste des paramètres pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4af48-114">Returns the list of supported parameters.</span></span>  
  
 <span data-ttu-id="4af48-115">**-SourceServer** *source_server_name*[ **\\** _instance_name_]</span><span class="sxs-lookup"><span data-stu-id="4af48-115">**-sourceserver** *source_server_name*[**\\**_instance_name_]</span></span>  
 <span data-ttu-id="4af48-116">Nom du serveur source.</span><span class="sxs-lookup"><span data-stu-id="4af48-116">Is the name of the source server.</span></span> <span data-ttu-id="4af48-117">Spécifiez le _ \_ \_ nom du serveur source_ pour l’instance par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-117">Specify _source\_server\_name_ for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4af48-118">Spécifiez le nom de l’instance du _ \_ \_ nom du serveur source_ **\\** _ \_ _ pour une instance nommée de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-118">Specify _source\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4af48-119">**-sourcedatabase** *source_database*</span><span class="sxs-lookup"><span data-stu-id="4af48-119">**-sourcedatabase** *source_database*</span></span>  
 <span data-ttu-id="4af48-120">Nom de la base de données source.</span><span class="sxs-lookup"><span data-stu-id="4af48-120">Is the name of the source database.</span></span>  
  
 <span data-ttu-id="4af48-121">**-sourcetable** *source_table_name*</span><span class="sxs-lookup"><span data-stu-id="4af48-121">**-sourcetable** *source_table_name*</span></span>  
 <span data-ttu-id="4af48-122">Nom de la table source en cours de vérification.</span><span class="sxs-lookup"><span data-stu-id="4af48-122">Is the name of the source table being checked.</span></span>  
  
 <span data-ttu-id="4af48-123">**-sourceschema** *source_schema_name*</span><span class="sxs-lookup"><span data-stu-id="4af48-123">**-sourceschema** *source_schema_name*</span></span>  
 <span data-ttu-id="4af48-124">Propriétaire du schéma de la table source.</span><span class="sxs-lookup"><span data-stu-id="4af48-124">The schema owner of the source table.</span></span> <span data-ttu-id="4af48-125">Par défaut, le propriétaire de la table est supposé être dbo.</span><span class="sxs-lookup"><span data-stu-id="4af48-125">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="4af48-126">**-sourcepassword** *source_password*</span><span class="sxs-lookup"><span data-stu-id="4af48-126">**-sourcepassword** *source_password*</span></span>  
 <span data-ttu-id="4af48-127">Mot de passe de la connexion utilisée pour la connexion au serveur source avec l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-127">Is the password for the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4af48-128">Lorsque cela est possible, fournissez les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="4af48-128">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="4af48-129">Si vous devez enregistrer les informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="4af48-129">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="4af48-130">**-sourceuser** *source_login*</span><span class="sxs-lookup"><span data-stu-id="4af48-130">**-sourceuser** *source_login*</span></span>  
 <span data-ttu-id="4af48-131">Connexion employée pour établir la connexion au serveur source avec l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-131">Is the login used to connect to the source server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="4af48-132">Si *source_login* n’est pas fourni, l’authentification Windows est employée lors de la connexion au serveur source.</span><span class="sxs-lookup"><span data-stu-id="4af48-132">If *source_login* is not supplied, then Windows Authentication is used when connecting to the source server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="4af48-133">**-sourcelocked**</span><span class="sxs-lookup"><span data-stu-id="4af48-133">**-sourcelocked**</span></span>  
 <span data-ttu-id="4af48-134">Durant la comparaison, la table source est verrouillée à l'aide des indicateurs de table TABLOCK et HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="4af48-134">The source table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="4af48-135">**-DestinationServer** *destination_server_name*[ **\\** _ \_ nom_de l’instance]</span><span class="sxs-lookup"><span data-stu-id="4af48-135">**-destinationserver** *destination_server_name*[**\\**_instance\_name_]</span></span>  
 <span data-ttu-id="4af48-136">Nom du serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-136">Is the name of the destination server.</span></span> <span data-ttu-id="4af48-137">Spécifiez *destination_server_name* pour l’instance par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4af48-137">Specify *destination_server_name* for the default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="4af48-138">Spécifiez le nom de l’instance du _ \_ \_ nom du serveur de destination_ **\\** pour une instance nommée de_ \_ _ [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-138">Specify _destination\_server\_name_**\\**_instance\_name_ for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4af48-139">**-destinationdatabase** *subscription_database*</span><span class="sxs-lookup"><span data-stu-id="4af48-139">**-destinationdatabase** *subscription_database*</span></span>  
 <span data-ttu-id="4af48-140">Nom de la base de données de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-140">Is the name of the destination database.</span></span>  
  
 <span data-ttu-id="4af48-141">**-destinationtable** *destination_table*</span><span class="sxs-lookup"><span data-stu-id="4af48-141">**-destinationtable** *destination_table*</span></span>  
 <span data-ttu-id="4af48-142">Nom de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-142">Is the name of the destination table.</span></span>  
  
 <span data-ttu-id="4af48-143">**-destinationschema** *destination_schema_name*</span><span class="sxs-lookup"><span data-stu-id="4af48-143">**-destinationschema** *destination_schema_name*</span></span>  
 <span data-ttu-id="4af48-144">Le propriétaire du schéma de la table de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-144">The schema owner of the destination table.</span></span> <span data-ttu-id="4af48-145">Par défaut, le propriétaire de la table est supposé être dbo.</span><span class="sxs-lookup"><span data-stu-id="4af48-145">By default, the table owner is assumed to be dbo.</span></span>  
  
 <span data-ttu-id="4af48-146">**-destinationpassword** *destination_password*</span><span class="sxs-lookup"><span data-stu-id="4af48-146">**-destinationpassword** *destination_password*</span></span>  
 <span data-ttu-id="4af48-147">Mot de passe de la connexion utilisée pour établir une connexion au serveur de destination avec l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-147">Is the password for the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="4af48-148">Lorsque cela est possible, fournissez les informations d'identification au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="4af48-148">When possible, supply security credentials at runtime.</span></span> <span data-ttu-id="4af48-149">Si vous devez enregistrer les informations d'identification dans un fichier de script, vous devez sécuriser le fichier pour empêcher un accès non autorisé.</span><span class="sxs-lookup"><span data-stu-id="4af48-149">If you must store credentials in a script file, you should secure the file to prevent unauthorized access.</span></span>  
  
 <span data-ttu-id="4af48-150">**-destinationuser** *destination_login*</span><span class="sxs-lookup"><span data-stu-id="4af48-150">**-destinationuser** *destination_login*</span></span>  
 <span data-ttu-id="4af48-151">Connexion employée pour établir la connexion au serveur de destination avec l’authentification [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-151">Is the login used to connect to the destination server using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="4af48-152">Si *destination_login* n’est pas fourni, l’authentification Windows est employée lors de la connexion au serveur.</span><span class="sxs-lookup"><span data-stu-id="4af48-152">If *destination_login* is not supplied, then Windows Authentication is used when connecting to the server.</span></span> [!INCLUDE[ssNoteWinAuthentication](../includes/ssnotewinauthentication-md.md)]  
  
 <span data-ttu-id="4af48-153">**-destinationlocked**</span><span class="sxs-lookup"><span data-stu-id="4af48-153">**-destinationlocked**</span></span>  
 <span data-ttu-id="4af48-154">Durant la comparaison, la table de destination est verrouillée à l'aide des indicateurs de table TABLOCK et HOLDLOCK.</span><span class="sxs-lookup"><span data-stu-id="4af48-154">The destination table is locked during the comparison using the TABLOCK and HOLDLOCK table hints.</span></span>  
  
 <span data-ttu-id="4af48-155">**-b** *large_object_bytes*</span><span class="sxs-lookup"><span data-stu-id="4af48-155">**-b** *large_object_bytes*</span></span>  
 <span data-ttu-id="4af48-156">Nombre d'octets à comparer pour des colonnes de types de données d'objet volumineuses, notamment : `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` et `varbinary(max)`.</span><span class="sxs-lookup"><span data-stu-id="4af48-156">Is the number of bytes to compare for large object data type columns, which includes: `text`, `ntext`, `image`, `varchar(max)`, `nvarchar(max)` and `varbinary(max)`.</span></span> <span data-ttu-id="4af48-157">*large_object_bytes* a comme valeur par défaut la taille de la colonne.</span><span class="sxs-lookup"><span data-stu-id="4af48-157">*large_object_bytes* defaults to the size of the column.</span></span> <span data-ttu-id="4af48-158">Toutes les données au-dessus de *large_object_bytes* ne sont pas comparées.</span><span class="sxs-lookup"><span data-stu-id="4af48-158">Any data above *large_object_bytes* will not be compared.</span></span>  
  
 <span data-ttu-id="4af48-159">**-bf**  *number_of_statements*</span><span class="sxs-lookup"><span data-stu-id="4af48-159">**-bf**  *number_of_statements*</span></span>  
 <span data-ttu-id="4af48-160">Nombre d’instructions [!INCLUDE[tsql](../includes/tsql-md.md)] à écrire dans le fichier de script [!INCLUDE[tsql](../includes/tsql-md.md)] actuel lorsque l’option **-f** est utilisée.</span><span class="sxs-lookup"><span data-stu-id="4af48-160">Is the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements to write to the current [!INCLUDE[tsql](../includes/tsql-md.md)] script file when the **-f** option is used.</span></span> <span data-ttu-id="4af48-161">Quand le nombre d’instructions [!INCLUDE[tsql](../includes/tsql-md.md)] dépasse *number_of_statements*, un fichier de script [!INCLUDE[tsql](../includes/tsql-md.md)] est créé.</span><span class="sxs-lookup"><span data-stu-id="4af48-161">When the number of [!INCLUDE[tsql](../includes/tsql-md.md)] statements exceeds *number_of_statements*, a new [!INCLUDE[tsql](../includes/tsql-md.md)] script file is created.</span></span>  
  
 <span data-ttu-id="4af48-162">**-c**</span><span class="sxs-lookup"><span data-stu-id="4af48-162">**-c**</span></span>  
 <span data-ttu-id="4af48-163">Compare les différences au niveau des colonnes.</span><span class="sxs-lookup"><span data-stu-id="4af48-163">Compare column-level differences.</span></span>  
  
 <span data-ttu-id="4af48-164">**-dt**</span><span class="sxs-lookup"><span data-stu-id="4af48-164">**-dt**</span></span>  
 <span data-ttu-id="4af48-165">Supprime la table de résultats spécifiée par *table_name*si la table existe déjà.</span><span class="sxs-lookup"><span data-stu-id="4af48-165">Drop the result table specified by *table_name*, if the table already exists.</span></span>  
  
 <span data-ttu-id="4af48-166">**-et** *table_name*</span><span class="sxs-lookup"><span data-stu-id="4af48-166">**-et** *table_name*</span></span>  
 <span data-ttu-id="4af48-167">Spécifie le nom de la table de résultats à créer.</span><span class="sxs-lookup"><span data-stu-id="4af48-167">Specifies the name of the result table to create.</span></span> <span data-ttu-id="4af48-168">Si cette table existe déjà, **-DT** doit être utilisé, sinon l’opération échoue.</span><span class="sxs-lookup"><span data-stu-id="4af48-168">If this table already exists, **-DT** must be used or the operation will fail.</span></span>  
  
 <span data-ttu-id="4af48-169">**-f** [ *file_name* ]</span><span class="sxs-lookup"><span data-stu-id="4af48-169">**-f** [ *file_name* ]</span></span>  
 <span data-ttu-id="4af48-170">Génère un script [!INCLUDE[tsql](../includes/tsql-md.md)] pour mettre la table sur le serveur de destination en convergence avec la table sur le serveur source.</span><span class="sxs-lookup"><span data-stu-id="4af48-170">Generates a [!INCLUDE[tsql](../includes/tsql-md.md)] script to bring the table at the destination server into convergence with the table at the source server.</span></span> <span data-ttu-id="4af48-171">Vous pouvez éventuellement spécifier un nom et un chemin d'accès pour le fichier de script [!INCLUDE[tsql](../includes/tsql-md.md)] généré.</span><span class="sxs-lookup"><span data-stu-id="4af48-171">You can optionally specify a name and path for the generated [!INCLUDE[tsql](../includes/tsql-md.md)] script file.</span></span> <span data-ttu-id="4af48-172">Si *file_name* n’est pas spécifié, le fichier de script [!INCLUDE[tsql](../includes/tsql-md.md)] est créé dans le répertoire où l’utilitaire est exécuté.</span><span class="sxs-lookup"><span data-stu-id="4af48-172">If *file_name* is not specified, the [!INCLUDE[tsql](../includes/tsql-md.md)] script file is generated in the directory where the utility runs.</span></span>  
  
 <span data-ttu-id="4af48-173">**-o** *output_file_name*</span><span class="sxs-lookup"><span data-stu-id="4af48-173">**-o** *output_file_name*</span></span>  
 <span data-ttu-id="4af48-174">Nom complet et chemin d'accès du fichier de sortie.</span><span class="sxs-lookup"><span data-stu-id="4af48-174">Is the full name and path of the output file.</span></span>  
  
 <span data-ttu-id="4af48-175">**-q**</span><span class="sxs-lookup"><span data-stu-id="4af48-175">**-q**</span></span>  
 <span data-ttu-id="4af48-176">Comparaison rapide se limitant à la comparaison du nombre de lignes et du schéma.</span><span class="sxs-lookup"><span data-stu-id="4af48-176">Perform a fast comparison by only comparing row counts and schema.</span></span>  
  
 <span data-ttu-id="4af48-177">**-rc** *number_of_retries*</span><span class="sxs-lookup"><span data-stu-id="4af48-177">**-rc** *number_of_retries*</span></span>  
 <span data-ttu-id="4af48-178">Nombre de fois où l'utilitaire retente une opération qui a échoué.</span><span class="sxs-lookup"><span data-stu-id="4af48-178">Number of times that the utility retries a failed operation.</span></span>  
  
 <span data-ttu-id="4af48-179">**-ri**  *retry_interval*</span><span class="sxs-lookup"><span data-stu-id="4af48-179">**-ri**  *retry_interval*</span></span>  
 <span data-ttu-id="4af48-180">Intervalle, en secondes, d'attente entre les tentatives.</span><span class="sxs-lookup"><span data-stu-id="4af48-180">Interval, in seconds, to wait between retries.</span></span>  
  
 <span data-ttu-id="4af48-181">**-strict**</span><span class="sxs-lookup"><span data-stu-id="4af48-181">**-strict**</span></span>  
 <span data-ttu-id="4af48-182">Les schémas source et de destination sont comparés de manière stricte.</span><span class="sxs-lookup"><span data-stu-id="4af48-182">Source and destination schema are strictly compared.</span></span>  
  
 <span data-ttu-id="4af48-183">**-t** *connection_timeouts*</span><span class="sxs-lookup"><span data-stu-id="4af48-183">**-t** *connection_timeouts*</span></span>  
 <span data-ttu-id="4af48-184">Définit le délai d'attente de connexion, en secondes, pour les connexions au serveur source et au serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-184">Sets the connection timeout period, in seconds, for connections to the source server and destination server.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4af48-185">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="4af48-185">Return Value</span></span>  
  
|<span data-ttu-id="4af48-186">Valeur</span><span class="sxs-lookup"><span data-stu-id="4af48-186">Value</span></span>|<span data-ttu-id="4af48-187">Description</span><span class="sxs-lookup"><span data-stu-id="4af48-187">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4af48-188">**0**</span><span class="sxs-lookup"><span data-stu-id="4af48-188">**0**</span></span>|<span data-ttu-id="4af48-189">Succès</span><span class="sxs-lookup"><span data-stu-id="4af48-189">Success</span></span>|  
|<span data-ttu-id="4af48-190">**1**</span><span class="sxs-lookup"><span data-stu-id="4af48-190">**1**</span></span>|<span data-ttu-id="4af48-191">Erreur critique</span><span class="sxs-lookup"><span data-stu-id="4af48-191">Critical error</span></span>|  
|<span data-ttu-id="4af48-192">**2**</span><span class="sxs-lookup"><span data-stu-id="4af48-192">**2**</span></span>|<span data-ttu-id="4af48-193">Tables différentes</span><span class="sxs-lookup"><span data-stu-id="4af48-193">Table differences</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4af48-194">Notes</span><span class="sxs-lookup"><span data-stu-id="4af48-194">Remarks</span></span>  
 <span data-ttu-id="4af48-195">L’utilitaire **tablediff** ne peut pas être utilisé avec des serveurs non- [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4af48-195">The **tablediff** utility cannot be used with non-[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] servers.</span></span>  
  
 <span data-ttu-id="4af48-196">Les tables comprenant des colonnes de types de données `sql_variant` ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="4af48-196">Tables with `sql_variant` data type columns are not supported.</span></span>  
  
 <span data-ttu-id="4af48-197">Par défaut, l’utilitaire **tablediff** prend en charge les mappages de types de données suivants entre les colonnes source et de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-197">By default, the **tablediff** utility supports the following data type mappings between source and destination columns.</span></span>  
  
|<span data-ttu-id="4af48-198">Type de données sources</span><span class="sxs-lookup"><span data-stu-id="4af48-198">Source data type</span></span>|<span data-ttu-id="4af48-199">Type de données de destination</span><span class="sxs-lookup"><span data-stu-id="4af48-199">Destination data type</span></span>|  
|----------------------|---------------------------|  
|`tinyint`|<span data-ttu-id="4af48-200">`smallint`, `int` ou `bigint`</span><span class="sxs-lookup"><span data-stu-id="4af48-200">`smallint`, `int`, or `bigint`</span></span>|  
|`smallint`|<span data-ttu-id="4af48-201">`int` ou `bigint`</span><span class="sxs-lookup"><span data-stu-id="4af48-201">`int` or `bigint`</span></span>|  
|`int`|`bigint`|  
|`timestamp`|`varbinary`|  
|`varchar(max)`|`text`|  
|`nvarchar(max)`|`ntext`|  
|`varbinary(max)`|`image`|  
|`text`|`varchar(max)`|  
|`ntext`|`nvarchar(max)`|  
|`image`|`varbinary(max)`|  
  
 <span data-ttu-id="4af48-202">Utilisez l’option **-strict** pour interdire ces mappages et effectuer une validation stricte.</span><span class="sxs-lookup"><span data-stu-id="4af48-202">Use the **-strict** option to disallow these mappings and perform a strict validation.</span></span>  
  
 <span data-ttu-id="4af48-203">La table source de la comparaison doit contenir au moins une colonne de clé primaire, d'identité ou ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="4af48-203">The source table in the comparison must contain at least one primary key, identity, or ROWGUID column.</span></span> <span data-ttu-id="4af48-204">Quand vous utilisez l’option **-strict** , la table de destination doit également contenir une colonne de clé primaire, d’identité ou ROWGUID.</span><span class="sxs-lookup"><span data-stu-id="4af48-204">When you use the **-strict** option, the destination table must also have a primary key, identity, or ROWGUID column.</span></span>  
  
 <span data-ttu-id="4af48-205">Le script [!INCLUDE[tsql](../includes/tsql-md.md)] généré pour faire converger la table de destination n'inclut pas les types de données suivants :</span><span class="sxs-lookup"><span data-stu-id="4af48-205">The [!INCLUDE[tsql](../includes/tsql-md.md)] script generated to bring the destination table into convergence does not include the following data types:</span></span>  
  
-   `varchar(max)`  
  
-   `nvarchar(max)`  
  
-   `varbinary(max)`  
  
-   `timestamp`  
  
-   <span data-ttu-id="4af48-206">**xml**</span><span class="sxs-lookup"><span data-stu-id="4af48-206">**xml**</span></span>  
  
-   `text`  
  
-   `ntext`  
  
-   `image`  
  
## <a name="permissions"></a><span data-ttu-id="4af48-207">Autorisations</span><span class="sxs-lookup"><span data-stu-id="4af48-207">Permissions</span></span>  
 <span data-ttu-id="4af48-208">Pour comparer les tables, vous avez besoin des autorisations SELECT ALL sur les objets de table comparés.</span><span class="sxs-lookup"><span data-stu-id="4af48-208">To compare tables, you need SELECT ALL permissions on the table objects being compared.</span></span>  
  
 <span data-ttu-id="4af48-209">Pour utiliser l’option **-et** , vous devez être membre du rôle de base de données fixe db_owner, ou au moins disposer de l’autorisation CREATE TABLE dans la base de données d’abonnement et de l’autorisation ALTER sur le schéma du propriétaire de destination sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-209">To use the **-et** option, you must be a member of the db_owner fixed database role, or at least have CREATE TABLE permission in the subscription database and ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="4af48-210">Pour utiliser l’option **-dt** , vous devez être membre du rôle de base de données fixe db_owner ou disposer au moins de l’autorisation ALTER sur le schéma du propriétaire de destination sur le serveur de destination.</span><span class="sxs-lookup"><span data-stu-id="4af48-210">To use the **-dt** option, you must be a member of the db_owner fixed database role, or at least have ALTER permission on the destination owner schema at the destination server.</span></span>  
  
 <span data-ttu-id="4af48-211">Pour utiliser l’option **-o** ou **-f** , vous devez disposer d’autorisations d’écriture sur l’emplacement du répertoire de fichiers spécifié.</span><span class="sxs-lookup"><span data-stu-id="4af48-211">To use the **-o** or **-f** options, you must have write permissions to the specified file directory location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af48-212">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4af48-212">See Also</span></span>  
 [<span data-ttu-id="4af48-213">Comparer des tables répliquées pour identifier les différences &#40;programmation de réplication&#41;</span><span class="sxs-lookup"><span data-stu-id="4af48-213">Compare Replicated Tables for Differences &#40;Replication Programming&#41;</span></span>](../relational-databases/replication/administration/compare-replicated-tables-for-differences-replication-programming.md)  
  
  
