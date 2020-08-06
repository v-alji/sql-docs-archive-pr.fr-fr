---
title: Prise en charge des requêtes distribuées dans les ensembles de lignes de schéma | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
author: rothja
ms.author: jroth
ms.openlocfilehash: 48b57bbf40590f8ad5c049268f25fe66d2f94357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602102"
---
# <a name="distributed-query-support-in-schema-rowsets"></a><span data-ttu-id="1aa06-102">Prise en charge des requêtes distribuées dans les ensembles de lignes de schéma</span><span class="sxs-lookup"><span data-stu-id="1aa06-102">Distributed Query Support in Schema Rowsets</span></span>
  <span data-ttu-id="1aa06-103">Pour prendre en charge [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] les requêtes distribuées, l' [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] interface **IDBSchemaRowset** du fournisseur OLE DB Native Client retourne des métadonnées sur les serveurs liés.</span><span class="sxs-lookup"><span data-stu-id="1aa06-103">To support [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider **IDBSchemaRowset** interface returns metadata on linked servers.</span></span>  
  
 <span data-ttu-id="1aa06-104">Si la propriété DBPROPSET_SQLSERVERSESSION SSPROP_QUOTEDCATALOGNAMES est VARIANT_TRUE, un identificateur entre guillemets peut être spécifié pour le nom de catalogue (par exemple "my.catalog").</span><span class="sxs-lookup"><span data-stu-id="1aa06-104">If the DBPROPSET_SQLSERVERSESSION property SSPROP_QUOTEDCATALOGNAMES is VARIANT_TRUE, a quoted identifier can be specified for the catalog name (for example "my.catalog").</span></span> <span data-ttu-id="1aa06-105">Lors de la restriction de la sortie de l’ensemble de lignes de schéma par catalogue, le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client reconnaît un nom en deux parties contenant le serveur lié et le nom du catalogue.</span><span class="sxs-lookup"><span data-stu-id="1aa06-105">When restricting schema rowset output by catalog, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes a two-part name containing the linked server and catalog name.</span></span> <span data-ttu-id="1aa06-106">Pour les ensembles de lignes de schéma dans le tableau ci-dessous, en spécifiant un nom de catalogue en deux parties comme _linked_server_**.** _Catalog_ limite la sortie au catalogue applicable du serveur lié nommé.</span><span class="sxs-lookup"><span data-stu-id="1aa06-106">For the schema rowsets in the table below, specifying a two-part catalog name as _linked_server_**.**_catalog_ restricts output to the applicable catalog of the named linked server.</span></span>  
  
|<span data-ttu-id="1aa06-107">Ensemble de lignes de schéma</span><span class="sxs-lookup"><span data-stu-id="1aa06-107">Schema rowset</span></span>|<span data-ttu-id="1aa06-108">Restriction de catalogue</span><span class="sxs-lookup"><span data-stu-id="1aa06-108">Catalog restriction</span></span>|  
|-------------------|-------------------------|  
|<span data-ttu-id="1aa06-109">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="1aa06-109">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="1aa06-110">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1aa06-110">CATALOG_NAME</span></span>|  
|<span data-ttu-id="1aa06-111">DBSCHEMA_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="1aa06-111">DBSCHEMA_COLUMNS</span></span>|<span data-ttu-id="1aa06-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-112">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="1aa06-113">DBSCHEMA_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="1aa06-113">DBSCHEMA_PRIMARY_KEYS</span></span>|<span data-ttu-id="1aa06-114">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-114">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="1aa06-115">DBSCHEMA_TABLES</span><span class="sxs-lookup"><span data-stu-id="1aa06-115">DBSCHEMA_TABLES</span></span>|<span data-ttu-id="1aa06-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-116">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="1aa06-117">DBSCHEMA_FOREIGN_KEYS</span><span class="sxs-lookup"><span data-stu-id="1aa06-117">DBSCHEMA_FOREIGN_KEYS</span></span>|<span data-ttu-id="1aa06-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span></span>|  
|<span data-ttu-id="1aa06-119">DBSCHEMA_INDEXES</span><span class="sxs-lookup"><span data-stu-id="1aa06-119">DBSCHEMA_INDEXES</span></span>|<span data-ttu-id="1aa06-120">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-120">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="1aa06-121">DBSCHEMA_COLUMN_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="1aa06-121">DBSCHEMA_COLUMN_PRIVILEGES</span></span>|<span data-ttu-id="1aa06-122">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-122">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="1aa06-123">DBSCHEMA_TABLE_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="1aa06-123">DBSCHEMA_TABLE_PRIVILEGES</span></span>|<span data-ttu-id="1aa06-124">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1aa06-124">TABLE_CATALOG</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="1aa06-125">Pour restreindre un ensemble de lignes de schéma à tous les catalogues d’un serveur lié, utilisez la syntaxe *serveur_lié* (où le point séparateur fait partie de la spécification du nom).</span><span class="sxs-lookup"><span data-stu-id="1aa06-125">To restrict a schema rowset to all catalogs from a linked server, use the syntax *linked_server* (where the period separator is part of the name specification).</span></span> <span data-ttu-id="1aa06-126">Cette syntaxe équivaut à spécifier NULL pour la restriction du nom de catalogue ; elle est également utilisée lorsque le serveur lié indique une source de données qui ne prend pas en charge les catalogues.</span><span class="sxs-lookup"><span data-stu-id="1aa06-126">This syntax is equivalent to specifying NULL for the catalog name restriction and is also used when the linked server indicates a data source that does not support catalogs.</span></span>  
  
 <span data-ttu-id="1aa06-127">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client définit l’ensemble de lignes de schéma LinkedServers, en renvoyant une liste de sources de données OLE DB inscrites en tant que serveurs liés.</span><span class="sxs-lookup"><span data-stu-id="1aa06-127">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the schema rowset LINKEDSERVERS, returning a list of OLE DB data sources registered as linked servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aa06-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1aa06-128">See Also</span></span>  
 <span data-ttu-id="1aa06-129">[Prise en charge des ensembles de lignes de schéma &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="1aa06-129">[Schema Rowset Support &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span></span>  
 [<span data-ttu-id="1aa06-130">Ensemble de lignes LINKEDSERVERS &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1aa06-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span></span>](schema-rowsets-linkedservers-rowset.md)  
  
  
