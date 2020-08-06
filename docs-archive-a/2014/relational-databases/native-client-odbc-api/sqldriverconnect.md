---
title: SQLDriverConnect | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: rothja
ms.author: jroth
ms.openlocfilehash: 40691dfb381883b59155607fb56f4933820e3e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705116"
---
# <a name="sqldriverconnect"></a><span data-ttu-id="8ef76-102">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="8ef76-102">SQLDriverConnect</span></span>
  <span data-ttu-id="8ef76-103">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client définit des attributs de connexion qui remplacent ou améliorent les mots clés de chaînes de connexion.</span><span class="sxs-lookup"><span data-stu-id="8ef76-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines connection attributes that either replace or enhance connection-string keywords.</span></span> <span data-ttu-id="8ef76-104">Plusieurs mots clés de chaînes de connexion ont des valeurs par défaut définies par le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="8ef76-104">Several connection-string keywords have default values specified by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
 <span data-ttu-id="8ef76-105">Pour obtenir la liste des mots clés disponibles dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client, consultez [utilisation de mots clés de chaîne de connexion avec SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="8ef76-105">For a list of the keywords available in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="8ef76-106">Pour plus d’informations sur les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] attributs de connexion et les comportements par défaut du pilote, consultez [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="8ef76-106">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection attributes and driver default behaviors, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="8ef76-107">Pour plus d’informations sur les mots clés de chaîne de connexion valides pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, consultez [utilisation de mots clés de chaîne de connexion avec SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="8ef76-107">For a discussion of connection string keywords that are valid for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="8ef76-108">Quand la `SQLDriverConnect` valeur du paramètre *DriverCompletion* est SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE ou SQL_DRIVER_COMPLETE_REQUIRED, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pilote ODBC Native Client récupère les valeurs des mots clés dans la boîte de dialogue affichée.</span><span class="sxs-lookup"><span data-stu-id="8ef76-108">When the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE, or SQL_DRIVER_COMPLETE_REQUIRED, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver retrieves keyword values from the displayed dialog box.</span></span> <span data-ttu-id="8ef76-109">Si la valeur de mot clé est transmise à la chaîne de connexion et si l'utilisateur ne modifie pas la valeur pour le mot clé dans la boîte de dialogue, le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client utilise la valeur issue de la chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="8ef76-109">If the keyword value is passed in the connection string and the user does not alter the value for the keyword in the dialog box, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses the value from the connection string.</span></span> <span data-ttu-id="8ef76-110">Si la valeur n'est pas définie dans la chaîne de connexion et si l'utilisateur ne procède à aucune affectation dans la boîte de dialogue, le pilote utilise la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="8ef76-110">If the value is not set in the connection string and the user makes no assignment in the dialog box, the driver uses the default.</span></span>  
  
 <span data-ttu-id="8ef76-111">`SQLDriverConnect`un *WindowHandle* valide doit être donné lorsque toute valeur *DriverCompletion* nécessite (ou peut nécessiter) l’affichage de la boîte de dialogue de connexion du pilote.</span><span class="sxs-lookup"><span data-stu-id="8ef76-111">`SQLDriverConnect` must be given a valid *WindowHandle* when any *DriverCompletion* value requires (or could require) the display of the driver's connection dialog box.</span></span> <span data-ttu-id="8ef76-112">Un handle non valide retourne SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="8ef76-112">An invalid handle returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="8ef76-113">Spécifiez le mot clé DRIVER ou DSN.</span><span class="sxs-lookup"><span data-stu-id="8ef76-113">Specify either the DRIVER or DSN keywords.</span></span> <span data-ttu-id="8ef76-114">ODBC indique que, de ces deux mots clés, un pilote utilise celui qui est situé le plus à gauche et ignore l'autre si les deux sont spécifiés.</span><span class="sxs-lookup"><span data-stu-id="8ef76-114">ODBC states that a driver uses the leftmost of these two keywords and ignores the other if both are specified.</span></span> <span data-ttu-id="8ef76-115">Si DRIVER est spécifié ou est le plus à gauche des deux, et que la `SQLDriverConnect` valeur du paramètre *DriverCompletion* est SQL_DRIVER_NOPROMPT, le mot clé Server et une valeur appropriée sont requis.</span><span class="sxs-lookup"><span data-stu-id="8ef76-115">If DRIVER is specified, or is the leftmost of the two, and the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT, the SERVER keyword and an appropriate value are required.</span></span>  
  
 <span data-ttu-id="8ef76-116">Lorsque SQL_DRIVER_NOPROMPT est spécifié, les mots clés d'authentification utilisateur doivent être fournis avec des valeurs.</span><span class="sxs-lookup"><span data-stu-id="8ef76-116">When SQL_DRIVER_NOPROMPT is specified, user authentication keywords must be present with values.</span></span> <span data-ttu-id="8ef76-117">Le pilote garantit que la chaîne « Trusted_Connection=yes » ou les mots clés UID et PWD à la fois sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="8ef76-117">The driver ensures that either the string "Trusted_Connection=yes" or both the UID and PWD keywords are present.</span></span>  
  
 <span data-ttu-id="8ef76-118">Si la valeur du paramètre *DriverCompletion* est SQL_DRIVER_NOPROMPT ou SQL_DRIVER_COMPLETE_REQUIRED et que la langue ou la base de données provient de la chaîne de connexion et que l’une ou l’autre n’est pas valide, `SQLDriverConnect` retourne SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="8ef76-118">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the connection string and either is invalid, `SQLDriverConnect` returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="8ef76-119">Si la valeur du paramètre *DriverCompletion* est SQL_DRIVER_NOPROMPT ou SQL_DRIVER_COMPLETE_REQUIRED et que la langue ou la base de données provient des définitions de source de données ODBC et que l’une ou l’autre n’est pas valide, `SQLDriverConnect` utilise la langue ou la base de données par défaut pour l’ID utilisateur spécifié et retourne SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="8ef76-119">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the ODBC data source definitions and either is invalid, `SQLDriverConnect` uses the default language or database for the specified user ID and returns SQL_SUCCESS_WITH_INFO.</span></span>  
  
 <span data-ttu-id="8ef76-120">Si la valeur du paramètre *DriverCompletion* est SQL_DRIVER_COMPLETE ou SQL_DRIVER_PROMPT et si la langue ou la base de données n’est pas valide, `SQLDriverConnect` réaffiche la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="8ef76-120">If the *DriverCompletion* parameter value is SQL_DRIVER_COMPLETE or SQL_DRIVER_PROMPT and if the language or database is invalid, `SQLDriverConnect` redisplays the dialog box.</span></span>  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="8ef76-121">SQLDriverConnect prend en charge les fonctionnalités de récupération d'urgence, haute disponibilité</span><span class="sxs-lookup"><span data-stu-id="8ef76-121">SQLDriverConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="8ef76-122">Pour plus d’informations sur l’utilisation `SQLDriverConnect` de pour se connecter à un [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, consultez [SQL Server Native Client la prise en charge de la haute disponibilité et de la récupération d’urgence](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8ef76-122">For more information about using `SQLDriverConnect` to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a><span data-ttu-id="8ef76-123">Prise en charge de SQLDriverConnect pour les noms de principaux du service (SPN)</span><span class="sxs-lookup"><span data-stu-id="8ef76-123">SQLDriverConnect Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="8ef76-124">SQLDDriverConnect utilise la boîte de dialogue de connexion ODBC boîte invite est activée.</span><span class="sxs-lookup"><span data-stu-id="8ef76-124">SQLDDriverConnect will use the ODBC Login dialog boxwhen prompting is enabled.</span></span> <span data-ttu-id="8ef76-125">Celle-ci vous permet d'entrer des SPN à la fois pour le serveur principal et pour le partenaire de basculement.</span><span class="sxs-lookup"><span data-stu-id="8ef76-125">This allows SPNs to be entered for both the principal server and its failover partner.</span></span>  
  
 <span data-ttu-id="8ef76-126">SQLDriverConnect acceptera les nouveaux mots clés de chaîne `ServerSPN` de connexion et et `FailoverPartnerSPN` reconnaîtra les nouveaux attributs de connexion SQL_COPT_SS_SERVER_SPN et SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span><span class="sxs-lookup"><span data-stu-id="8ef76-126">SQLDriverConnect will accept the new connection string keywords `ServerSPN` and `FailoverPartnerSPN`, and will recognize the new connection attributes SQL_COPT_SS_SERVER_SPN and SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span></span>  
  
 <span data-ttu-id="8ef76-127">Lorsqu'une valeur d'attribut de connexion est définie plus d'une fois, toute valeur définie par programme à priorité sur la valeur d'un DSN et sur toute valeur dans une chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="8ef76-127">When a connection attribute value is specified more than once, a value that is set programmatically takes precedence over the value in a DSN and a value in a connection string.</span></span> <span data-ttu-id="8ef76-128">Une valeur dans un DSN est prioritaire par rapport à une valeur dans une chaîne de connexion.</span><span class="sxs-lookup"><span data-stu-id="8ef76-128">A value in a DSN takes precedence over a value in a connection string.</span></span>  
  
 <span data-ttu-id="8ef76-129">Lors de l'ouverture d'une connexion, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client définit SQL_COPT_SS_MUTUALLY_AUTHENTICATED et SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD sur la méthode d'authentification employée pour ouvrir la connexion.</span><span class="sxs-lookup"><span data-stu-id="8ef76-129">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span>  
  
 <span data-ttu-id="8ef76-130">Pour plus d’informations sur les SPN, consultez [noms de principal du Service &#40;spn&#41; dans connexions clientes &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="8ef76-130">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8ef76-131">Exemples</span><span class="sxs-lookup"><span data-stu-id="8ef76-131">Examples</span></span>  
 <span data-ttu-id="8ef76-132">L’appel suivant illustre la quantité de données minimale requise pour `SQLDriverConnect` :</span><span class="sxs-lookup"><span data-stu-id="8ef76-132">The following call illustrates the least amount of data required for `SQLDriverConnect`:</span></span>  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 <span data-ttu-id="8ef76-133">Les chaînes de connexion suivantes illustrent les données minimales requises lorsque la valeur du paramètre *DriverCompletion* est SQL_DRIVER_NOPROMPT :</span><span class="sxs-lookup"><span data-stu-id="8ef76-133">The following connection strings illustrate minimum required data when the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT:</span></span>  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ef76-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ef76-134">See Also</span></span>  
 <span data-ttu-id="8ef76-135">[Fonction SQLDriverConnect](https://go.microsoft.com/fwlink/?LinkId=59340) </span><span class="sxs-lookup"><span data-stu-id="8ef76-135">[SQLDriverConnect Function](https://go.microsoft.com/fwlink/?LinkId=59340) </span></span>  
 <span data-ttu-id="8ef76-136">[Détails de l’implémentation de l’API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="8ef76-136">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="8ef76-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8ef76-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="8ef76-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="8ef76-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="8ef76-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="8ef76-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
