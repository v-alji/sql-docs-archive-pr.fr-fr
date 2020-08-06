---
title: Création d’une application de pilote SQL Server Native Client ODBC | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, architecture
- SQL Server Native Client ODBC driver, creating applications
- ODBC function calls
- ODBC, header files
- ODBC applications
- ODBC applications, creating
- SQL Server Native Client ODBC driver, extensions
- applications [SQL Server Native Client]
- SQL Server Native Client ODBC driver, ODBC architecture
- extensions [ODBC]
- ODBC, driver extensions
- function calls [ODBC]
ms.assetid: c83c36e2-734e-4960-bc7e-92235910bc6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c8a1719f8b60885810d9b2f8a1f1023a7ffe6e47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706391"
---
# <a name="creating-a-sql-server-native-client-odbc-driver-application"></a><span data-ttu-id="60884-102">Création d'une application de pilote ODBC SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="60884-102">Creating a SQL Server Native Client ODBC Driver Application</span></span>
  <span data-ttu-id="60884-103">L'architecture ODBC possède quatre composants qui effectuent les fonctions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="60884-103">ODBC architecture has four components that perform the following functions.</span></span>  
  
|<span data-ttu-id="60884-104">Composant</span><span class="sxs-lookup"><span data-stu-id="60884-104">Component</span></span>|<span data-ttu-id="60884-105">Fonction</span><span class="sxs-lookup"><span data-stu-id="60884-105">Function</span></span>|  
|---------------|--------------|  
|<span data-ttu-id="60884-106">Application</span><span class="sxs-lookup"><span data-stu-id="60884-106">Application</span></span>|<span data-ttu-id="60884-107">Appelle les fonctions ODBC pour communiquer avec une source de données ODBC, soumet les instructions SQL et traite les jeux de résultats.</span><span class="sxs-lookup"><span data-stu-id="60884-107">Calls ODBC functions to communicate with an ODBC data source, submits SQL statements, and processes result sets.</span></span>|  
|<span data-ttu-id="60884-108">Gestionnaire de pilote</span><span class="sxs-lookup"><span data-stu-id="60884-108">Driver Manager</span></span>|<span data-ttu-id="60884-109">Gère la communication entre une application et tous les pilotes ODBC utilisés par cette application.</span><span class="sxs-lookup"><span data-stu-id="60884-109">Manages communication between an application and all ODBC drivers used by the application.</span></span>|  
|<span data-ttu-id="60884-110">Pilote</span><span class="sxs-lookup"><span data-stu-id="60884-110">Driver</span></span>|<span data-ttu-id="60884-111">Traite tous les appels des fonctions ODBC à partir de l'application, se connecte à une source de données, passe les instructions SQL de l'application à la source de données et retourne les résultats à l'application.</span><span class="sxs-lookup"><span data-stu-id="60884-111">Processes all ODBC function calls from the application, connects to a data source, passes SQL statements from the application to the data source, and returns results to the application.</span></span> <span data-ttu-id="60884-112">Si nécessaire, le pilote traduit des données ODBC SQL de l'application en données SQL natif utilisées par la source de données.</span><span class="sxs-lookup"><span data-stu-id="60884-112">If necessary, the driver translates ODBC SQL from the application to native SQL used by the data source.</span></span>|  
|<span data-ttu-id="60884-113">Source de données</span><span class="sxs-lookup"><span data-stu-id="60884-113">Data source</span></span>|<span data-ttu-id="60884-114">Contient toutes les informations dont un pilote a besoin pour accéder à une instance spécifique des données dans un SGBD.</span><span class="sxs-lookup"><span data-stu-id="60884-114">Contains all information a driver needs to access a specific instance of data in a DBMS.</span></span>|  
  
 <span data-ttu-id="60884-115">Une application qui utilise le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client pour communiquer avec une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] effectue les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="60884-115">An application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver to communicate with an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] performs the following tasks:</span></span>  
  
-   <span data-ttu-id="60884-116">Elle se connecte à une source de données.</span><span class="sxs-lookup"><span data-stu-id="60884-116">Connects with a data source</span></span>  
  
-   <span data-ttu-id="60884-117">Elle envoie les instructions SQL à la source de données.</span><span class="sxs-lookup"><span data-stu-id="60884-117">Sends SQL statements to the data source</span></span>  
  
-   <span data-ttu-id="60884-118">Elle traite les résultats des instructions provenant de la source de données.</span><span class="sxs-lookup"><span data-stu-id="60884-118">Processes the results of statements from the data source</span></span>  
  
-   <span data-ttu-id="60884-119">Elle traite les erreurs et les messages.</span><span class="sxs-lookup"><span data-stu-id="60884-119">Processes errors and messages</span></span>  
  
-   <span data-ttu-id="60884-120">Elle met un terme à la connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="60884-120">Terminates the connection to the data source</span></span>  
  
 <span data-ttu-id="60884-121">Une application plus complexe écrite pour le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client peut également effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="60884-121">A more complex application written for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver might also perform the following tasks:</span></span>  
  
-   <span data-ttu-id="60884-122">Utiliser des curseurs pour contrôler l'emplacement dans un jeu de résultats</span><span class="sxs-lookup"><span data-stu-id="60884-122">Use cursors to control location in a result set</span></span>  
  
-   <span data-ttu-id="60884-123">Demander des opérations de validation ou de restauration pour le contrôle des transactions</span><span class="sxs-lookup"><span data-stu-id="60884-123">Request commit or rollback operations for transaction control</span></span>  
  
-   <span data-ttu-id="60884-124">Effectuer des transactions distribuées qui impliquent deux serveurs ou plus</span><span class="sxs-lookup"><span data-stu-id="60884-124">Perform distributed transactions involving two or more servers</span></span>  
  
-   <span data-ttu-id="60884-125">Exécuter des procédures stockées sur le serveur distant</span><span class="sxs-lookup"><span data-stu-id="60884-125">Run stored procedures on the remote server</span></span>  
  
-   <span data-ttu-id="60884-126">Appeler des fonctions de catalogue pour obtenir des informations sur les attributs d'un jeu de résultats</span><span class="sxs-lookup"><span data-stu-id="60884-126">Call catalog functions to inquire about the attributes of a result set</span></span>  
  
-   <span data-ttu-id="60884-127">Effectuer des opérations de copie en bloc</span><span class="sxs-lookup"><span data-stu-id="60884-127">Perform bulk copy operations</span></span>  
  
-   <span data-ttu-id="60884-128">Gérer les opérations de données volumineuses (**varchar (max)**, **nvarchar (max)** et **varbinary (max)** colonnes)</span><span class="sxs-lookup"><span data-stu-id="60884-128">Manage large data (**varchar(max)**, **nvarchar(max)**, and **varbinary(max)** columns) operations</span></span>  
  
-   <span data-ttu-id="60884-129">Utiliser la logique de reconnexion pour faciliter le basculement lorsque la mise en miroir de bases de données est configurée</span><span class="sxs-lookup"><span data-stu-id="60884-129">Use reconnection logic to facilitate failover when database mirroring is configured</span></span>  
  
-   <span data-ttu-id="60884-130">Enregistrer des données de performances et des requêtes longues</span><span class="sxs-lookup"><span data-stu-id="60884-130">Log performance data and long-running queries</span></span>  
  
 <span data-ttu-id="60884-131">Pour effectuer des appels de fonction ODBC, une application C ou C++ doit inclure les fichiers d'en-tête sql.h, sqlext.h et sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="60884-131">To make ODBC function calls, a C or C++ application must include the sql.h, sqlext.h, and sqltypes.h header files.</span></span> <span data-ttu-id="60884-132">Pour effectuer des appels aux fonctions API du programme d'installation ODBC, une application doit inclure le fichier d'en-tête odbcinst.h.</span><span class="sxs-lookup"><span data-stu-id="60884-132">To make calls to the ODBC installer API functions, an application must include the odbcinst.h header file.</span></span> <span data-ttu-id="60884-133">Une application ODBC Unicode doit inclure le fichier d'en-tête sqlucode.h.</span><span class="sxs-lookup"><span data-stu-id="60884-133">A Unicode ODBC application must include the sqlucode.h header file.</span></span> <span data-ttu-id="60884-134">Les applications ODBC doivent être liées au fichier odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="60884-134">ODBC applications must be linked with the odbc32.lib file.</span></span> <span data-ttu-id="60884-135">Les applications ODBC qui appellent les fonctions API du programme d'installation ODBC doivent être liées au fichier odbccp32.lib.</span><span class="sxs-lookup"><span data-stu-id="60884-135">ODBC applications that call the ODBC installer API functions must be linked with the odbccp32.lib file.</span></span> <span data-ttu-id="60884-136">Ces fichiers sont inclus dans le Kit de développement Platform SDK de Windows.</span><span class="sxs-lookup"><span data-stu-id="60884-136">These files are included in the Windows Platform SDK.</span></span>  
  
 <span data-ttu-id="60884-137">De nombreux pilotes ODBC, y compris le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client, proposent des extensions ODBC spécifiques aux pilotes.</span><span class="sxs-lookup"><span data-stu-id="60884-137">Many ODBC drivers, including the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver, offer driver-specific ODBC extensions.</span></span> <span data-ttu-id="60884-138">Pour tirer parti des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] extensions spécifiques au pilote ODBC Native Client, une application doit inclure le fichier d’en-tête sqlncli. h.</span><span class="sxs-lookup"><span data-stu-id="60884-138">To take advantage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific extensions, an application should include the sqlncli.h header file.</span></span> <span data-ttu-id="60884-139">Ce fichier d'en-tête contient :</span><span class="sxs-lookup"><span data-stu-id="60884-139">This header file contains:</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="60884-140">Attributs de connexion spécifiques au pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="60884-140">Native Client ODBC driver-specific connection attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="60884-141">Attributs d’instruction spécifiques au pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="60884-141">Native Client ODBC driver-specific statement attributes.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="60884-142">Attributs de colonne spécifiques au pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="60884-142">Native Client ODBC driver-specific column attributes.</span></span>  
  
-   <span data-ttu-id="60884-143">Les types de données spécifiques à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60884-143">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific data types.</span></span>  
  
-   <span data-ttu-id="60884-144">Les types de données définis par l'utilisateur spécifiques à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60884-144">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific user-defined data types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="60884-145">Types de [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) spécifiques au pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="60884-145">Native Client ODBC driver-specific [SQLGetInfo](../../native-client-odbc-api/sqlgetinfo.md) types.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="60884-146">Champs de diagnostic du pilote ODBC Native Client.</span><span class="sxs-lookup"><span data-stu-id="60884-146">Native Client ODBC driver diagnostics fields.</span></span>  
  
-   <span data-ttu-id="60884-147">Les codes de fonction dynamique de diagnostic spécifiques à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60884-147">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific diagnostic dynamic function codes.</span></span>  
  
-   <span data-ttu-id="60884-148">Les définitions de type C/C++ pour les types de données C natifs spécifiques à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (retournées lorsque les colonnes ont créé une liaison avec le type de données C SQL_C_BINARY).</span><span class="sxs-lookup"><span data-stu-id="60884-148">C/C++ type definitions for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-specific native C data types (returned when columns bound to C data type SQL_C_BINARY).</span></span>  
  
-   <span data-ttu-id="60884-149">Tapez la définition pour la structure de données SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="60884-149">Type definition for the SQLPERF data structure.</span></span>  
  
-   <span data-ttu-id="60884-150">Copiez en bloc les macros et les prototypes pour prendre en charge l'utilisation d'API de copie en bloc par le biais d'une connexion ODBC.</span><span class="sxs-lookup"><span data-stu-id="60884-150">Bulk copy macros and prototypes to support bulk copy API usage through an ODBC connection.</span></span>  
  
-   <span data-ttu-id="60884-151">Appelez les fonctions API de métadonnées de requête distribuée pour obtenir les listes des serveurs liés et leurs catalogues.</span><span class="sxs-lookup"><span data-stu-id="60884-151">Call the distributed query metadata API functions for lists of linked servers and their catalogs.</span></span>  
  
 <span data-ttu-id="60884-152">Toute application ODBC C ou C++ qui utilise la fonctionnalité de copie en bloc du [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pilote ODBC Native Client doit être liée au fichier SQLNCLI11. lib.</span><span class="sxs-lookup"><span data-stu-id="60884-152">Any C or C++ ODBC application that uses the bulk copy feature of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver must be linked with the sqlncli11.lib file.</span></span> <span data-ttu-id="60884-153">Les applications qui appellent les fonctions API de métadonnées de requête distribuée doivent également être liées à sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="60884-153">Applications calling the distributed query metadata API functions must also be linked with sqlncli11.lib.</span></span> <span data-ttu-id="60884-154">Les fichiers sqlncli. h et SQLNCLI11. lib sont distribués dans le cadre des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] outils du développeur.</span><span class="sxs-lookup"><span data-stu-id="60884-154">The sqlncli.h and sqlncli11.lib files are distributed as part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] developer's tools.</span></span> <span data-ttu-id="60884-155">Les répertoires [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include et Lib doivent correspondre aux chemins d'accès INCLUDE et LIB du compilateur, comme suit :</span><span class="sxs-lookup"><span data-stu-id="60884-155">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Include and Lib directories should be in the compiler's INCLUDE and LIB paths as in the following:</span></span>  
  
```  
LIB=c:\Program Files\Microsoft Data Access SDK 2.8\Libs\x86\lib;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Lib;  
INCLUDE=c:\Program Files\Microsoft Data Access SDK 2.8\inc;C:\Program Files\Microsoft SQL Server\100\Tools\SDK\Include;  
```  
  
 <span data-ttu-id="60884-156">Une décision de conception à prendre tôt dans le processus de génération d'une application est de savoir si l'application doit avoir plusieurs appels ODBC en attente en même temps.</span><span class="sxs-lookup"><span data-stu-id="60884-156">One design decision made early in the process of building an application is whether the application needs to have multiple ODBC calls outstanding at the same time.</span></span> <span data-ttu-id="60884-157">Il existe deux méthodes de prise en charge des appels ODBC concurrents multiples ; elles sont décrites dans les autres rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="60884-157">There are two methods for supporting multiple concurrent ODBC calls, which are described in the remaining topics in this section.</span></span> <span data-ttu-id="60884-158">Pour plus d’informations, consultez [Guide de référence du programmeur ODBC](https://go.microsoft.com/fwlink/?LinkId=45250).</span><span class="sxs-lookup"><span data-stu-id="60884-158">For more information, see the [ODBC Programmer's Reference](https://go.microsoft.com/fwlink/?LinkId=45250).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="60884-159">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="60884-159">In This Section</span></span>  
  
-   [<span data-ttu-id="60884-160">Mode asynchrone et SQLCancel</span><span class="sxs-lookup"><span data-stu-id="60884-160">Asynchronous Mode and SQLCancel</span></span>](../../native-client-odbc-api/sqlcancel.md)  
  
-   [<span data-ttu-id="60884-161">Applications multithread</span><span class="sxs-lookup"><span data-stu-id="60884-161">Multithreaded Applications</span></span>](creating-a-driver-application-multithreaded-applications.md)  
  
## <a name="see-also"></a><span data-ttu-id="60884-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60884-162">See Also</span></span>  
 [<span data-ttu-id="60884-163">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="60884-163">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
