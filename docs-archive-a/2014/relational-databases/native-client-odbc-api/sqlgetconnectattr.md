---
title: SQLGetConnectAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetConnectAttr function
ms.assetid: 26e4e69a-44fd-45e3-b47a-ae39184f041b
author: rothja
ms.author: jroth
ms.openlocfilehash: f82a0fb71103e811b36280f9722c160791023e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599999"
---
# <a name="sqlgetconnectattr"></a><span data-ttu-id="801f9-102">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="801f9-102">SQLGetConnectAttr</span></span>
  <span data-ttu-id="801f9-103">Le pilote ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client définit des attributs de connexion spécifiques au pilote.</span><span class="sxs-lookup"><span data-stu-id="801f9-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines driver-specific connection attributes.</span></span> <span data-ttu-id="801f9-104">Certains des attributs sont disponibles pour `SQLGetConnectAttr` , et la fonction est utilisée pour signaler leurs paramètres actuels.</span><span class="sxs-lookup"><span data-stu-id="801f9-104">Some of the attributes are available to `SQLGetConnectAttr`, and the function is used to report their current settings.</span></span> <span data-ttu-id="801f9-105">Les valeurs indiquées pour ces attributs ne sont pas garanties tant qu'une connexion n'a pas été établie ou que l'attribut n'a pas été défini à l'aide de [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="801f9-105">The values reported for these attributes are not guaranteed until after a connection has been made or the attribute has been set using [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="801f9-106">Cette rubrique dresse la liste des attributs accessibles en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="801f9-106">This topic lists the read only attributes.</span></span> <span data-ttu-id="801f9-107">Pour plus d'informations sur les autres attributs de connexion spécifiques au pilote de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC, consultez [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="801f9-107">For information about the other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific connection attributes, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="sql_copt_ss_connection_dead"></a><span data-ttu-id="801f9-108">SQL_COPT_SS_CONNECTION_DEAD</span><span class="sxs-lookup"><span data-stu-id="801f9-108">SQL_COPT_SS_CONNECTION_DEAD</span></span>  
 <span data-ttu-id="801f9-109">L'attribut SQL_COPT_SS_CONNECTION_DEAD signale l'état d'une connexion à un serveur.</span><span class="sxs-lookup"><span data-stu-id="801f9-109">The SQL_COPT_SS_CONNECTION_DEAD attribute reports the state of a connection to a server.</span></span> <span data-ttu-id="801f9-110">Le pilote interroge le réseau afin de connaître l'état actuel de la connexion.</span><span class="sxs-lookup"><span data-stu-id="801f9-110">The driver queries the network for the current state of the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="801f9-111">L'attribut de connexion ODBC standard SQL_ATTR_CONNECTION_DEAD retourne l'état le plus récent de la connexion.</span><span class="sxs-lookup"><span data-stu-id="801f9-111">The standard ODBC connection attribute SQL_ATTR_CONNECTION_DEAD returns the most recent state of the connection.</span></span> <span data-ttu-id="801f9-112">Cela peut ne pas être l'état actuel de la connexion.</span><span class="sxs-lookup"><span data-stu-id="801f9-112">This might not be the current connection state.</span></span>  
  
|<span data-ttu-id="801f9-113">Valeur</span><span class="sxs-lookup"><span data-stu-id="801f9-113">Value</span></span>|<span data-ttu-id="801f9-114">Description</span><span class="sxs-lookup"><span data-stu-id="801f9-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="801f9-115">SQL_CD_TRUE</span><span class="sxs-lookup"><span data-stu-id="801f9-115">SQL_CD_TRUE</span></span>|<span data-ttu-id="801f9-116">La connexion au serveur a été perdue.</span><span class="sxs-lookup"><span data-stu-id="801f9-116">The connection to the server has been lost.</span></span>|  
|<span data-ttu-id="801f9-117">SQL_CD_FALSE</span><span class="sxs-lookup"><span data-stu-id="801f9-117">SQL_CD_FALSE</span></span>|<span data-ttu-id="801f9-118">La connexion est ouverte et disponible pour le traitement d'instruction.</span><span class="sxs-lookup"><span data-stu-id="801f9-118">The connection is open and available for statement processing.</span></span>|  
  
## <a name="sql_copt_ss_client_connection_id"></a><span data-ttu-id="801f9-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span><span class="sxs-lookup"><span data-stu-id="801f9-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span></span>  
 <span data-ttu-id="801f9-120">L'attribut SQL_COPT_SS_CLIENT_CONNECTION_ID récupère l'ID de connexion client, qui peut ensuite être utilisé pour localiser :</span><span class="sxs-lookup"><span data-stu-id="801f9-120">The SQL_COPT_SS_CLIENT_CONNECTION_ID attribute retrieves the client connection ID, which can then be used to locate:</span></span>  
  
-   <span data-ttu-id="801f9-121">Les informations de diagnostic dans le journal XEvents, si cette option est activée.</span><span class="sxs-lookup"><span data-stu-id="801f9-121">Diagnostic information in the XEvents log, when enabled.</span></span>  
  
-   <span data-ttu-id="801f9-122">Les informations d'erreur de connexion dans la mémoire tampon en anneau de connexion.</span><span class="sxs-lookup"><span data-stu-id="801f9-122">Connection error information in the connection ring buffer.</span></span>  
  
-   <span data-ttu-id="801f9-123">Les informations de diagnostic dans les journaux de suivi d'accès aux données, si cette option est activée.</span><span class="sxs-lookup"><span data-stu-id="801f9-123">Diagnostic information in the data access tracing logs, when enabled.</span></span>  
  
 <span data-ttu-id="801f9-124">Pour plus d’informations, consultez [accès aux informations de diagnostic dans le journal des événements étendus](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="801f9-124">For more information, see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
|<span data-ttu-id="801f9-125">Valeur</span><span class="sxs-lookup"><span data-stu-id="801f9-125">Value</span></span>|<span data-ttu-id="801f9-126">Description</span><span class="sxs-lookup"><span data-stu-id="801f9-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="801f9-127">SQL_ERROR</span><span class="sxs-lookup"><span data-stu-id="801f9-127">SQL_ERROR</span></span>|<span data-ttu-id="801f9-128">La connexion a échoué.</span><span class="sxs-lookup"><span data-stu-id="801f9-128">The connection failed.</span></span>|  
|<span data-ttu-id="801f9-129">SQL_SUCCESS</span><span class="sxs-lookup"><span data-stu-id="801f9-129">SQL_SUCCESS</span></span>|<span data-ttu-id="801f9-130">La connexion a abouti.</span><span class="sxs-lookup"><span data-stu-id="801f9-130">The connection succeeded.</span></span> <span data-ttu-id="801f9-131">L'ID de connexion client se trouve dans le tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="801f9-131">The client connection ID will be found in the output buffer.</span></span>|  
  
## <a name="sql_copt_ss_perf_data"></a><span data-ttu-id="801f9-132">SQL_COPT_SS_PERF_DATA</span><span class="sxs-lookup"><span data-stu-id="801f9-132">SQL_COPT_SS_PERF_DATA</span></span>  
 <span data-ttu-id="801f9-133">L'attribut SQL_COPT_SS_PERF_DATA retourne un pointeur vers une structure SQLPERF contenant les statistiques actuelles de performances de pilote.</span><span class="sxs-lookup"><span data-stu-id="801f9-133">The SQL_COPT_SS_PERF_DATA attribute returns a pointer to a SQLPERF structure containing the current driver performance statistics.</span></span> <span data-ttu-id="801f9-134">`SQLGetConnectAttr`retourne la valeur NULL si la journalisation des performances n’est pas activée.</span><span class="sxs-lookup"><span data-stu-id="801f9-134">`SQLGetConnectAttr` will return NULL if performance logging is not enabled.</span></span> <span data-ttu-id="801f9-135">Les statistiques dans la structure SQLPERF ne sont pas mises à jour de manière dynamique par le pilote.</span><span class="sxs-lookup"><span data-stu-id="801f9-135">The statistics in the SQLPERF structure are not dynamically updated by the driver.</span></span> <span data-ttu-id="801f9-136">Appelez `SQLGetConnectAttr` chaque fois que les statistiques de performances doivent être actualisées.</span><span class="sxs-lookup"><span data-stu-id="801f9-136">Call `SQLGetConnectAttr` each time the performance statistics need to be refreshed.</span></span>  
  
|<span data-ttu-id="801f9-137">Valeur</span><span class="sxs-lookup"><span data-stu-id="801f9-137">Value</span></span>|<span data-ttu-id="801f9-138">Description</span><span class="sxs-lookup"><span data-stu-id="801f9-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="801f9-139">NULL</span><span class="sxs-lookup"><span data-stu-id="801f9-139">NULL</span></span>|<span data-ttu-id="801f9-140">L'enregistrement des performances n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="801f9-140">Performance logging is not enabled.</span></span>|  
|<span data-ttu-id="801f9-141">Toute autre valeur</span><span class="sxs-lookup"><span data-stu-id="801f9-141">Any other value</span></span>|<span data-ttu-id="801f9-142">Pointeur vers une structure SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="801f9-142">A pointer to a SQLPERF structure.</span></span>|  
  
## <a name="sql_copt_ss_perf_query"></a><span data-ttu-id="801f9-143">SQL_COPT_SS_PERF_QUERY</span><span class="sxs-lookup"><span data-stu-id="801f9-143">SQL_COPT_SS_PERF_QUERY</span></span>  
 <span data-ttu-id="801f9-144">L'attribut SQL_COPT_SS_PERF_QUERY retourne TRUE si l'enregistrement des longues requêtes est activé.</span><span class="sxs-lookup"><span data-stu-id="801f9-144">The SQL_COPT_SS_PERF_QUERY attribute returns TRUE if logging of long running queries is enabled.</span></span> <span data-ttu-id="801f9-145">La demande retourne FALSE si l'enregistrement des requêtes n'est pas actif.</span><span class="sxs-lookup"><span data-stu-id="801f9-145">The request returns FALSE if query logging is not active.</span></span>  
  
## <a name="sql_copt_ss_user_data"></a><span data-ttu-id="801f9-146">SQL_COPT_SS_USER_DATA</span><span class="sxs-lookup"><span data-stu-id="801f9-146">SQL_COPT_SS_USER_DATA</span></span>  
 <span data-ttu-id="801f9-147">L'attribut SQL_COPT_SS_USER_DATA extrait le pointeur de données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="801f9-147">The SQL_COPT_SS_USER_DATA attribute retrieves the user-data pointer.</span></span> <span data-ttu-id="801f9-148">Les données utilisateur sont stockées dans la mémoire détenue par le client et enregistrées par connexion.</span><span class="sxs-lookup"><span data-stu-id="801f9-148">User data is stored in client-owned memory and recorded per connection.</span></span> <span data-ttu-id="801f9-149">Si le pointeur de données utilisateur n'a pas été défini, SQL_UD_NOTSET, un pointeur NULL, est retourné.</span><span class="sxs-lookup"><span data-stu-id="801f9-149">If the user-data pointer has not been set, SQL_UD_NOTSET, a NULL pointer, is returned.</span></span>  
  
|<span data-ttu-id="801f9-150">Valeur</span><span class="sxs-lookup"><span data-stu-id="801f9-150">Value</span></span>|<span data-ttu-id="801f9-151">Description</span><span class="sxs-lookup"><span data-stu-id="801f9-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="801f9-152">SQL_UD_NOTSET</span><span class="sxs-lookup"><span data-stu-id="801f9-152">SQL_UD_NOTSET</span></span>|<span data-ttu-id="801f9-153">Aucun pointeur de données utilisateur n'est défini.</span><span class="sxs-lookup"><span data-stu-id="801f9-153">No user-data pointer is set.</span></span>|  
|<span data-ttu-id="801f9-154">Toute autre valeur</span><span class="sxs-lookup"><span data-stu-id="801f9-154">Any other value</span></span>|<span data-ttu-id="801f9-155">Pointeur vers les données utilisateur.</span><span class="sxs-lookup"><span data-stu-id="801f9-155">A pointer to the user data.</span></span>|  
  
## <a name="sqlgetconnectattr-support-for-service-principal-names-spns"></a><span data-ttu-id="801f9-156">Prise en charge de SQLGetConnectAttr pour les noms de principaux du service (SPN)</span><span class="sxs-lookup"><span data-stu-id="801f9-156">SQLGetConnectAttr Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="801f9-157">SQLGetConnectAttr peut être utilisé pour interroger la valeur des nouveaux attributs de connexion SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED et SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span><span class="sxs-lookup"><span data-stu-id="801f9-157">SQLGetConnectAttr can be used to query the value of the new connection attributes SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span></span> <span data-ttu-id="801f9-158">(Sqlgetconnectoption, peut également être utilisé pour interroger ces valeurs.)</span><span class="sxs-lookup"><span data-stu-id="801f9-158">(SQLGetConnectOption can also be used to query these values.)</span></span>  
  
 <span data-ttu-id="801f9-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD est disponible uniquement pour les connexions ouvertes qui utilisent l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="801f9-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD is only available for open connections that use Windows Authentication.</span></span>  
  
 <span data-ttu-id="801f9-160">Si SQL_COPT_SS_SERVER_SPN ou SQL_COPT_SS_FAILOVER_PARTNER n'a pas été défini, la valeur par défaut (une chaîne vide) est retournée.</span><span class="sxs-lookup"><span data-stu-id="801f9-160">If SQL_COPT_SS_SERVER_SPN or SQL_COPT_SS_FAILOVER_PARTNER has not been set, the default value (an empty string) is returned.</span></span>  
  
 <span data-ttu-id="801f9-161">Pour plus d’informations sur les SPN, consultez [noms de principal du Service &#40;spn&#41; dans connexions clientes &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="801f9-161">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801f9-162">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="801f9-162">See Also</span></span>  
 <span data-ttu-id="801f9-163">[SQLGetConnectAttr fonction)](https://go.microsoft.com/fwlink/?LinkId=59347) </span><span class="sxs-lookup"><span data-stu-id="801f9-163">[SQLGetConnectAttr Function](https://go.microsoft.com/fwlink/?LinkId=59347) </span></span>  
 <span data-ttu-id="801f9-164">[Détails de l’implémentation de l’API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="801f9-164">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="801f9-165">[DÉFINIR QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="801f9-165">[SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span></span>  
 <span data-ttu-id="801f9-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="801f9-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="801f9-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="801f9-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="801f9-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="801f9-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
