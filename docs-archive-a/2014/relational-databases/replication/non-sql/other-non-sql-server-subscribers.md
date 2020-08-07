---
title: Autres abonnés non-SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- non-SQL Server Subscribers, other types
ms.assetid: 96b8beb9-38e8-4ce4-97ca-c0f8656b73b4
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3849ca717e82bcf1bed5769190c9f898209a454a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599896"
---
# <a name="other-non-sql-server-subscribers"></a><span data-ttu-id="04f68-102">Autres abonnés non SQL Server</span><span class="sxs-lookup"><span data-stu-id="04f68-102">Other Non-SQL Server Subscribers</span></span>
  <span data-ttu-id="04f68-103">Pour obtenir la liste des Abonnés non[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pris en charge par [!INCLUDE[msCoName](../../../includes/msconame-md.md)], consultez [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="04f68-103">For a list of non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers supported by [!INCLUDE[msCoName](../../../includes/msconame-md.md)], see [Non-SQL Server Subscribers](non-sql-server-subscribers.md).</span></span> <span data-ttu-id="04f68-104">Cette rubrique propose des informations sur la configuration requise des pilotes ODBC et des fournisseurs OLE DB.</span><span class="sxs-lookup"><span data-stu-id="04f68-104">This topic includes information about requirements for ODBC drivers and OLE DB providers.</span></span>  
  
## <a name="odbc-driver-requirements"></a><span data-ttu-id="04f68-105">Configuration requise des pilotes ODBC</span><span class="sxs-lookup"><span data-stu-id="04f68-105">ODBC Driver Requirements</span></span>  
 <span data-ttu-id="04f68-106">Le pilote ODBC :</span><span class="sxs-lookup"><span data-stu-id="04f68-106">The ODBC driver:</span></span>  
  
-   <span data-ttu-id="04f68-107">doit être conforme à ODBC niveau 1 ;</span><span class="sxs-lookup"><span data-stu-id="04f68-107">Must be ODBC level-1 compliant.</span></span>  
  
-   <span data-ttu-id="04f68-108">doit être thread-safe et adapté à l'architecture de processeur (Intel® ou Alpha) et à la plateforme (32 ou 64 bits) sur lesquelles s'exécute le serveur de distribution [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ;</span><span class="sxs-lookup"><span data-stu-id="04f68-108">Must be thread-safe, and for the processor architecture (Intel or Alpha) and platform (32 bit or 64 bit) on which the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Distributor runs.</span></span>  
  
-   <span data-ttu-id="04f68-109">doit être capable d'exécuter des transactions ;</span><span class="sxs-lookup"><span data-stu-id="04f68-109">Must be transaction capable.</span></span>  
  
-   <span data-ttu-id="04f68-110">doit prendre en charge le langage de définition de données (DDL - Data Definition Language) ;</span><span class="sxs-lookup"><span data-stu-id="04f68-110">Must support the Data Definition Language (DDL).</span></span>  
  
-   <span data-ttu-id="04f68-111">ne peut pas être en lecture seule ;</span><span class="sxs-lookup"><span data-stu-id="04f68-111">Cannot be read-only.</span></span>  
  
-   <span data-ttu-id="04f68-112">doit prendre en charge les noms de table longs, tels que **MSreplication_subscriptions**.</span><span class="sxs-lookup"><span data-stu-id="04f68-112">Must support long table names such as **MSreplication_subscriptions**.</span></span>  
  
## <a name="replicating-using-ole-db-interfaces"></a><span data-ttu-id="04f68-113">Réplication à l'aide d'interfaces OLE DB</span><span class="sxs-lookup"><span data-stu-id="04f68-113">Replicating Using OLE DB Interfaces</span></span>  
 <span data-ttu-id="04f68-114">Les fournisseurs OLE DB doivent prendre en charge les objets suivants pour la réplication transactionnelle :</span><span class="sxs-lookup"><span data-stu-id="04f68-114">OLE DB providers must support these objects for transactional replication:</span></span>  
  
-   <span data-ttu-id="04f68-115">Objet**DataSource**</span><span class="sxs-lookup"><span data-stu-id="04f68-115">**DataSource** object</span></span>  
  
-   <span data-ttu-id="04f68-116">Objet**Session**</span><span class="sxs-lookup"><span data-stu-id="04f68-116">**Session** object</span></span>  
  
-   <span data-ttu-id="04f68-117">Objet**Command**</span><span class="sxs-lookup"><span data-stu-id="04f68-117">**Command** object</span></span>  
  
-   <span data-ttu-id="04f68-118">Objet**Rowset**</span><span class="sxs-lookup"><span data-stu-id="04f68-118">**Rowset** object</span></span>  
  
-   <span data-ttu-id="04f68-119">Objet**Error**</span><span class="sxs-lookup"><span data-stu-id="04f68-119">**Error** object</span></span>  
  
### <a name="datasource-object-interfaces"></a><span data-ttu-id="04f68-120">Interfaces de l'objet DataSource</span><span class="sxs-lookup"><span data-stu-id="04f68-120">DataSource Object Interfaces</span></span>  
 <span data-ttu-id="04f68-121">Les interfaces suivantes sont nécessaires pour se connecter à une source de données :</span><span class="sxs-lookup"><span data-stu-id="04f68-121">The following interfaces are required to connect to a data source:</span></span>  
  
-   `IDBInitialize`  
  
-   `IDBCreateSession`  
  
-   `IDBProperties`  
  
 <span data-ttu-id="04f68-122">Si le fournisseur prend en charge l’interface **IDBInfo**, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilise cette interface pour extraire des informations, telles que le caractère identificateur entre guillemets, la longueur maximale des instructions SQL et le nombre maximal de caractères que peuvent compter les noms de tables et de colonnes.</span><span class="sxs-lookup"><span data-stu-id="04f68-122">If the provider supports the **IDBInfo** interface, [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses the interface to retrieve information such as the quoted identifier character, maximum SQL statement length, and maximum number of characters in table and column names.</span></span>  
  
### <a name="session-object-interfaces"></a><span data-ttu-id="04f68-123">Interfaces de l'objet Session</span><span class="sxs-lookup"><span data-stu-id="04f68-123">Session Object Interfaces</span></span>  
 <span data-ttu-id="04f68-124">Les interfaces suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="04f68-124">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="04f68-125">**IDBCreateCommand**</span><span class="sxs-lookup"><span data-stu-id="04f68-125">**IDBCreateCommand**</span></span>  
  
-   <span data-ttu-id="04f68-126">**ITransaction**</span><span class="sxs-lookup"><span data-stu-id="04f68-126">**ITransaction**</span></span>  
  
-   <span data-ttu-id="04f68-127">**ITransactionLocal**</span><span class="sxs-lookup"><span data-stu-id="04f68-127">**ITransactionLocal**</span></span>  
  
-   <span data-ttu-id="04f68-128">**IDBSchemaRowset**</span><span class="sxs-lookup"><span data-stu-id="04f68-128">**IDBSchemaRowset**</span></span>  
  
### <a name="command-object-interfaces"></a><span data-ttu-id="04f68-129">Interfaces de l'objet Command</span><span class="sxs-lookup"><span data-stu-id="04f68-129">Command Object Interfaces</span></span>  
 <span data-ttu-id="04f68-130">Les interfaces suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="04f68-130">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="04f68-131">**ICommand**</span><span class="sxs-lookup"><span data-stu-id="04f68-131">**ICommand**</span></span>  
  
-   <span data-ttu-id="04f68-132">**ICommandProperties**</span><span class="sxs-lookup"><span data-stu-id="04f68-132">**ICommandProperties**</span></span>  
  
-   <span data-ttu-id="04f68-133">**ICommandText**</span><span class="sxs-lookup"><span data-stu-id="04f68-133">**ICommandText**</span></span>  
  
-   <span data-ttu-id="04f68-134">**ICommandPrepare**</span><span class="sxs-lookup"><span data-stu-id="04f68-134">**ICommandPrepare**</span></span>  
  
-   <span data-ttu-id="04f68-135">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="04f68-135">**IColumnsInfo**</span></span>  
  
-   <span data-ttu-id="04f68-136">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="04f68-136">**IAccessor**</span></span>  
  
-   <span data-ttu-id="04f68-137">**ICommandWithParameters**</span><span class="sxs-lookup"><span data-stu-id="04f68-137">**ICommandWithParameters**</span></span>  
  
 <span data-ttu-id="04f68-138">**IAccessor** est nécessaire pour créer des accesseurs de paramètre.</span><span class="sxs-lookup"><span data-stu-id="04f68-138">**IAccessor** is necessary to create parameter accessors.</span></span> <span data-ttu-id="04f68-139">Si le fournisseur prend en charge **ColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] utilise cette interface pour déterminer si une colonne est une colonne d’identité.</span><span class="sxs-lookup"><span data-stu-id="04f68-139">If the provider supports **IColumnRowset**, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] uses that interface to determine whether a column is an identity column.</span></span>  
  
### <a name="rowset-object-interfaces"></a><span data-ttu-id="04f68-140">Interfaces de l'objet Rowset</span><span class="sxs-lookup"><span data-stu-id="04f68-140">Rowset Object Interfaces</span></span>  
 <span data-ttu-id="04f68-141">Les interfaces suivantes sont nécessaires :</span><span class="sxs-lookup"><span data-stu-id="04f68-141">The following interfaces are required:</span></span>  
  
-   <span data-ttu-id="04f68-142">**IRowset**</span><span class="sxs-lookup"><span data-stu-id="04f68-142">**IRowset**</span></span>  
  
-   <span data-ttu-id="04f68-143">**IAccessor**</span><span class="sxs-lookup"><span data-stu-id="04f68-143">**IAccessor**</span></span>  
  
-   <span data-ttu-id="04f68-144">**IColumnsInfo**</span><span class="sxs-lookup"><span data-stu-id="04f68-144">**IColumnsInfo**</span></span>  
  
 <span data-ttu-id="04f68-145">Une application doit ouvrir un ensemble de lignes sur une table répliquée ayant été créée dans la base de données d'abonnement.</span><span class="sxs-lookup"><span data-stu-id="04f68-145">An application should open a rowset on a replicated table that is created in the subscription database.</span></span> <span data-ttu-id="04f68-146">**IColumnsInfo** et **IAccessor** sont nécessaires pour accéder aux données de l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="04f68-146">**IColumnsInfo** and **IAccessor** are needed to access data in the rowset.</span></span>  
  
### <a name="error-object-interfaces"></a><span data-ttu-id="04f68-147">Interfaces de l'objet Error</span><span class="sxs-lookup"><span data-stu-id="04f68-147">Error Object Interfaces</span></span>  
 <span data-ttu-id="04f68-148">Utilisez les interfaces suivantes pour gérer les erreurs :</span><span class="sxs-lookup"><span data-stu-id="04f68-148">Use the following interfaces to manage errors:</span></span>  
  
-   <span data-ttu-id="04f68-149">**IErrorRecords**</span><span class="sxs-lookup"><span data-stu-id="04f68-149">**IErrorRecords**</span></span>  
  
-   <span data-ttu-id="04f68-150">**IErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="04f68-150">**IErrorInfo**</span></span>  
  
 <span data-ttu-id="04f68-151">Utilisez **ISQLErrorInfo** si elle est prise en charge par le fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="04f68-151">Use **ISQLErrorInfo** if it is supported by the OLE DB provider.</span></span>  
  
 <span data-ttu-id="04f68-152">Pour plus d'informations, reportez-vous à la documentation qui accompagne votre fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="04f68-152">For more information about the OLE DB provider, see the documentation supplied with your OLE DB provider.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f68-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="04f68-153">See Also</span></span>  
 [<span data-ttu-id="04f68-154">Non-SQL Server Subscribers</span><span class="sxs-lookup"><span data-stu-id="04f68-154">Non-SQL Server Subscribers</span></span>](non-sql-server-subscribers.md)  
  
  
