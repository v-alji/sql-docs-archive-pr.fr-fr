---
title: Connexion à une source de données (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- checking connection states
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- SQLBrowseConnect function
- ODBC applications, connections
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLConnect function
- SQLDriveConnect function
- verifying connection states
- SQL Server Native Client ODBC driver, data sources
- SQL Server Native Client ODBC driver, connections
ms.assetid: ae30dd1d-06ae-452b-9618-8fd8cd7ba074
author: rothja
ms.author: jroth
ms.openlocfilehash: 25ce5954e45bb8070b5e99d8ebb7bfa9ad149c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605394"
---
# <a name="connecting-to-a-data-source-odbc"></a><span data-ttu-id="29e55-102">Connexion à une source de données (ODBC)</span><span class="sxs-lookup"><span data-stu-id="29e55-102">Connecting to a Data Source (ODBC)</span></span>
  <span data-ttu-id="29e55-103">Après avoir alloué des handles d'environnement et de connexion et avoir défini tous les attributs de connexion, l'application se connecte à la source de données ou au pilote.</span><span class="sxs-lookup"><span data-stu-id="29e55-103">After allocating environment and connection handles and setting any connection attributes, the application connects to the data source or driver.</span></span> <span data-ttu-id="29e55-104">Trois fonctions vous permettent de vous connecter :</span><span class="sxs-lookup"><span data-stu-id="29e55-104">There are three functions you can use to connect:</span></span>  
  
-   <span data-ttu-id="29e55-105">**SQLConnect**</span><span class="sxs-lookup"><span data-stu-id="29e55-105">**SQLConnect**</span></span>  
  
-   <span data-ttu-id="29e55-106">**SQLDriverConnect**</span><span class="sxs-lookup"><span data-stu-id="29e55-106">**SQLDriverConnect**</span></span>  
  
-   <span data-ttu-id="29e55-107">**SQLBrowseConnect**</span><span class="sxs-lookup"><span data-stu-id="29e55-107">**SQLBrowseConnect**</span></span>  
  
 <span data-ttu-id="29e55-108">Pour plus d’informations sur l’établissement de connexions à une source de données, y compris les différentes options de chaîne de connexion disponibles, consultez [utilisation de mots clés de chaîne de connexion avec SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="29e55-108">For more information about making connections to a data source, including the various connection string options available, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
## <a name="sqlconnect"></a><span data-ttu-id="29e55-109">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="29e55-109">SQLConnect</span></span>  
 <span data-ttu-id="29e55-110">**SQLConnect** est la fonction de connexion la plus simple.</span><span class="sxs-lookup"><span data-stu-id="29e55-110">**SQLConnect** is the simplest connection function.</span></span> <span data-ttu-id="29e55-111">Elle accepte trois paramètres : un nom de source de données, un ID d'utilisateur et un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="29e55-111">It accepts three parameters: a data source name, a user ID, and a password.</span></span> <span data-ttu-id="29e55-112">Utilisez **SQLConnect** lorsque ces trois paramètres contiennent toutes les informations nécessaires pour se connecter à la base de données.</span><span class="sxs-lookup"><span data-stu-id="29e55-112">Use **SQLConnect** when these three parameters contain all the information needed to connect to the database.</span></span> <span data-ttu-id="29e55-113">Pour ce faire, générez une liste de sources de données à l’aide de **SQLDataSources**; demander à l’utilisateur une source de données, un ID d’utilisateur et un mot de passe ; puis appelez **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="29e55-113">To do this, build a list of data sources using **SQLDataSources**; prompt the user for a data source, user ID, and password; and then call **SQLConnect**.</span></span>  
  
 <span data-ttu-id="29e55-114">**SQLConnect** suppose qu’un nom de source de données, un ID d’utilisateur et un mot de passe sont suffisants pour se connecter à une source de données et que la source de données ODBC contient toutes les autres informations dont le pilote ODBC a besoin pour établir la connexion.</span><span class="sxs-lookup"><span data-stu-id="29e55-114">**SQLConnect** assumes that a data source name, user ID, and password are sufficient to connect to a data source and that the ODBC data source contains all other information the ODBC driver needs to make the connection.</span></span> <span data-ttu-id="29e55-115">Contrairement à [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) et [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** n’utilise pas de chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="29e55-115">Unlike [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) and [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** does not use a connection string.</span></span>  
  
## <a name="sqldriverconnect"></a><span data-ttu-id="29e55-116">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="29e55-116">SQLDriverConnect</span></span>  
 <span data-ttu-id="29e55-117">**SQLDriverConnect** est utilisé lorsque plus d’informations que le nom de la source de données, l’ID d’utilisateur et le mot de passe sont requis.</span><span class="sxs-lookup"><span data-stu-id="29e55-117">**SQLDriverConnect** is used when more information than the data source name, user ID, and password is required.</span></span> <span data-ttu-id="29e55-118">L’un des paramètres de **SQLDriverConnect** est une chaîne de connexion contenant des informations spécifiques au pilote.</span><span class="sxs-lookup"><span data-stu-id="29e55-118">One of the parameters to **SQLDriverConnect** is a connection string containing driver-specific information.</span></span> <span data-ttu-id="29e55-119">Vous pouvez utiliser **SQLDriverConnect** au lieu de **SQLConnect** pour les raisons suivantes :</span><span class="sxs-lookup"><span data-stu-id="29e55-119">You might use **SQLDriverConnect** instead of **SQLConnect** for the following reasons:</span></span>  
  
-   <span data-ttu-id="29e55-120">Pour fournir des informations spécifiques au pilote lors de la connexion.</span><span class="sxs-lookup"><span data-stu-id="29e55-120">To specify driver-specific information at connect time.</span></span>  
  
-   <span data-ttu-id="29e55-121">Pour demander que le pilote invite l'utilisateur à fournir des informations sur la connexion.</span><span class="sxs-lookup"><span data-stu-id="29e55-121">To request that the driver prompt the user for connection information.</span></span>  
  
-   <span data-ttu-id="29e55-122">Pour se connecter sans le recours à une source de données ODBC.</span><span class="sxs-lookup"><span data-stu-id="29e55-122">To connect without using an ODBC data source.</span></span>  
  
 <span data-ttu-id="29e55-123">La chaîne de connexion **SQLDriverConnect** contient une série de paires mot clé-valeur qui spécifient toutes les informations de connexion prises en charge par un pilote ODBC.</span><span class="sxs-lookup"><span data-stu-id="29e55-123">The **SQLDriverConnect** connection string contains a series of keyword-value pairs that specify all connection information supported by an ODBC driver.</span></span> <span data-ttu-id="29e55-124">Chaque pilote prend en charge les mots clés ODBC standard (DSN, FILEDSN, DRIVER, UID, PWD et SAVEFILE) en plus des mots clés spécifiques au pilote pour toutes les informations de connexion prises en charge par le pilote.</span><span class="sxs-lookup"><span data-stu-id="29e55-124">Each driver supports the standard ODBC keywords (DSN, FILEDSN, DRIVER, UID, PWD, and SAVEFILE) in addition to driver-specific keywords for all connection information supported by the driver.</span></span> <span data-ttu-id="29e55-125">**SQLDriverConnect** peut être utilisé pour se connecter sans source de données.</span><span class="sxs-lookup"><span data-stu-id="29e55-125">**SQLDriverConnect** can be used to connect without a data source.</span></span> <span data-ttu-id="29e55-126">Par exemple, une application conçue pour établir une connexion sans DSN à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut appeler **SQLDriverConnect** avec une chaîne de connexion qui définit l’ID de connexion, le mot de passe, la bibliothèque réseau, le nom du serveur auquel se connecter et la base de données par défaut à utiliser.</span><span class="sxs-lookup"><span data-stu-id="29e55-126">For example, an application that is designed to make a "DSN-less" connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can call **SQLDriverConnect** with a connection string that defines the login ID, password, network library, server name to connect to, and default database to use.</span></span>  
  
 <span data-ttu-id="29e55-127">Lorsque vous utilisez **SQLDriverConnect**, il existe deux options pour inviter l’utilisateur à entrer les informations de connexion nécessaires :</span><span class="sxs-lookup"><span data-stu-id="29e55-127">When using **SQLDriverConnect**, there are two options for prompting the user for any needed connection information:</span></span>  
  
-   <span data-ttu-id="29e55-128">Boîte de dialogue d'application</span><span class="sxs-lookup"><span data-stu-id="29e55-128">Application dialog box</span></span>  
  
     <span data-ttu-id="29e55-129">Vous pouvez créer une boîte de dialogue d’application qui demande des informations de connexion, puis appelle **SQLDriverConnect** avec un handle de fenêtre null et *DriverCompletion* défini sur SQL_DRIVER_NOPROMPT.</span><span class="sxs-lookup"><span data-stu-id="29e55-129">You can create an application dialog box that prompts for connection information, and then calls **SQLDriverConnect** with a NULL window handle and *DriverCompletion* set to SQL_DRIVER_NOPROMPT.</span></span> <span data-ttu-id="29e55-130">Ces paramètres empêchent le pilote ODBC d'ouvrir sa propre boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="29e55-130">These parameter settings prevent the ODBC driver from opening its own dialog box.</span></span> <span data-ttu-id="29e55-131">Cette méthode est employée lorsqu'il est vital de contrôler l'interface utilisateur de l'application.</span><span class="sxs-lookup"><span data-stu-id="29e55-131">This method is used when it is important to control the user interface of the application.</span></span>  
  
-   <span data-ttu-id="29e55-132">Boîte de dialogue du pilote</span><span class="sxs-lookup"><span data-stu-id="29e55-132">Driver dialog box</span></span>  
  
     <span data-ttu-id="29e55-133">Vous pouvez coder l’application pour transmettre un handle de fenêtre valide à **SQLDriverConnect** et définir le paramètre *DriverCompletion* sur SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT ou SQL_DRIVER_COMPLETE_REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="29e55-133">You can code the application to pass a valid window handle to **SQLDriverConnect** and set the *DriverCompletion* parameter to SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT, or SQL_DRIVER_COMPLETE_REQUIRED.</span></span> <span data-ttu-id="29e55-134">Le pilote génère ensuite une boîte de dialogue pour inviter l'utilisateur à fournir les informations de connexion.</span><span class="sxs-lookup"><span data-stu-id="29e55-134">The driver then generates a dialog box to prompt the user for connection information.</span></span> <span data-ttu-id="29e55-135">Cette méthode simplifie le code de l'application.</span><span class="sxs-lookup"><span data-stu-id="29e55-135">This method simplifies the application code.</span></span>  
  
## <a name="sqlbrowseconnect"></a><span data-ttu-id="29e55-136">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="29e55-136">SQLBrowseConnect</span></span>  
 <span data-ttu-id="29e55-137">**SQLBrowseConnect**, comme **SQLDriverConnect**, utilise une chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="29e55-137">**SQLBrowseConnect**, like **SQLDriverConnect**, uses a connection string.</span></span> <span data-ttu-id="29e55-138">Toutefois, en utilisant **SQLBrowseConnect**, une application peut construire une chaîne de connexion complète de manière itérative avec la source de données au moment de l’exécution.</span><span class="sxs-lookup"><span data-stu-id="29e55-138">However, by using **SQLBrowseConnect**, an application can construct a complete connection string iteratively with the data source at run time.</span></span> <span data-ttu-id="29e55-139">L'application peut alors réaliser deux tâches :</span><span class="sxs-lookup"><span data-stu-id="29e55-139">This allows the application to do two things:</span></span>  
  
-   <span data-ttu-id="29e55-140">Créer ses propres boîtes de dialogue pour demander ces informations et conserver ainsi le contrôle de son interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29e55-140">Build its own dialog boxes to prompt for this information, thereby retaining control over its user interface.</span></span>  
  
-   <span data-ttu-id="29e55-141">Parcourir le système à la recherche de sources de données qu'un pilote en particulier peut exploiter, et ce éventuellement en plusieurs étapes.</span><span class="sxs-lookup"><span data-stu-id="29e55-141">Browse the system for data sources that can be used by a particular driver, possibly in several steps.</span></span>  
  
     <span data-ttu-id="29e55-142">Par exemple, l'utilisateur peut d'abord rechercher des serveurs sur le réseau, puis après avoir choisi un serveur, recherchez sur ce dernier des bases de données auxquelles le pilote peut accéder.</span><span class="sxs-lookup"><span data-stu-id="29e55-142">For example, the user might first browse the network for servers and, after choosing a server, browse the server for databases accessible by the driver.</span></span>  
  
 <span data-ttu-id="29e55-143">Lorsque **SQLBrowseConnect** termine une connexion réussie, il retourne une chaîne de connexion qui peut être utilisée lors des appels suivants à **SQLDriverConnect**.</span><span class="sxs-lookup"><span data-stu-id="29e55-143">When **SQLBrowseConnect** completes a successful connection, it returns a connection string that can be used on subsequent calls to **SQLDriverConnect**.</span></span>  
  
 <span data-ttu-id="29e55-144">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client retourne toujours SQL_SUCCESS_WITH_INFO sur un **SQLConnect**, **SQLDriverConnect**ou **SQLBrowseConnect**réussi.</span><span class="sxs-lookup"><span data-stu-id="29e55-144">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver always returns SQL_SUCCESS_WITH_INFO on a successful **SQLConnect**, **SQLDriverConnect**, or **SQLBrowseConnect**.</span></span> <span data-ttu-id="29e55-145">Quand une application ODBC appelle **SQLGetDiagRec** après l’obtention de SQL_SUCCESS_WITH_INFO, elle peut recevoir les messages suivants :</span><span class="sxs-lookup"><span data-stu-id="29e55-145">When an ODBC application calls **SQLGetDiagRec** after getting SQL_SUCCESS_WITH_INFO, it can receive the following messages:</span></span>  
  
 <span data-ttu-id="29e55-146">5701</span><span class="sxs-lookup"><span data-stu-id="29e55-146">5701</span></span>  
 <span data-ttu-id="29e55-147">Indique que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a placé le contexte de l'utilisateur dans la base de données par défaut définie dans la source de données ou dans la base de données par défaut définie pour l'ID de connexion employé dans la connexion si la source de données ne disposait pas d'une base de données par défaut.</span><span class="sxs-lookup"><span data-stu-id="29e55-147">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] put the user's context into the default database defined in the data source, or into the default database defined for the login ID used in the connection if the data source did not have a default database.</span></span>  
  
 <span data-ttu-id="29e55-148">5703</span><span class="sxs-lookup"><span data-stu-id="29e55-148">5703</span></span>  
 <span data-ttu-id="29e55-149">Indique la langue utilisée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="29e55-149">Indicates the language being used on the server.</span></span>  
  
 <span data-ttu-id="29e55-150">L'exemple ci-dessous affiche le message retourné par l'administrateur système lorsqu'une connexion est réussie  :</span><span class="sxs-lookup"><span data-stu-id="29e55-150">The following example shows the message returned on a successful connection by the system administrator:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 5701,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed database context to 'pubs'."  
szSqlState = "01000", *pfNativeError = 5703,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed language setting to 'us_english'."  
```  
  
 <span data-ttu-id="29e55-151">Vous pouvez ignorer les messages 5701 et 5703 ; ils sont fournis uniquement à titre d'information.</span><span class="sxs-lookup"><span data-stu-id="29e55-151">You can ignore messages 5701 and 5703; they are only informational.</span></span> <span data-ttu-id="29e55-152">En revanche, n'ignorez pas le code de retour SQL_SUCCESS_WITH_INFO car des messages autres que 5701 ou 5703 peuvent être retournés.</span><span class="sxs-lookup"><span data-stu-id="29e55-152">You should not, however, ignore a SQL_SUCCESS_WITH_INFO return code because messages other than 5701 or 5703 may be returned.</span></span> <span data-ttu-id="29e55-153">Par exemple, si un pilote se connecte à un serveur exécutant une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avec des procédures stockées de catalogue obsolètes, l’une des erreurs retournées via **SQLGetDiagRec** après une SQL_SUCCESS_WITH_INFO est la suivante :</span><span class="sxs-lookup"><span data-stu-id="29e55-153">For example, if a driver connects to a server running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with outdated catalog stored procedures, one of the errors returned through **SQLGetDiagRec** after a SQL_SUCCESS_WITH_INFO is:</span></span>  
  
```  
SqlState:   01000  
pfNative:   0  
szErrorMsg: "[Microsoft][SQL Server Native Client]The ODBC  
            catalog stored procedures installed on server  
            my65server are version 06.50.0193; version 07.00.0205  
            or later is required to ensure proper operation.  
            Please contact your system administrator."  
```  
  
 <span data-ttu-id="29e55-154">La fonction de gestion des erreurs d’une application pour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connexions doit appeler **SQLGetDiagRec** jusqu’à ce qu’elle retourne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="29e55-154">The error handling function of an application for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections should call **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="29e55-155">Il doit ensuite agir sur tous les messages autres que ceux avec un code *pfNative* de 5701 ou 5703.</span><span class="sxs-lookup"><span data-stu-id="29e55-155">It should then act on any messages other than the ones with a *pfNative* code of 5701 or 5703.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e55-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29e55-156">See Also</span></span>  
 [<span data-ttu-id="29e55-157">Communication avec SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="29e55-157">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
