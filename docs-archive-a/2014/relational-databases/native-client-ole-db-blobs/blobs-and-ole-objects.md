---
title: Objets BLOB et OLE | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BLOBs, OLE objects
- BLOBs
- storage object [OLE DB]
- SQL Server Native Client OLE DB provider, BLOBs
- large data, OLE objects
ms.assetid: 767fa2f6-9cd2-436f-add5-e760bed29a58
author: rothja
ms.author: jroth
ms.openlocfilehash: 15f8b4915ba9b05a5be19854a2e27a2e8ff3a346
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709284"
---
# <a name="blobs-and-ole-objects"></a><span data-ttu-id="4b803-102">Objets BLOB et OLE</span><span class="sxs-lookup"><span data-stu-id="4b803-102">BLOBs and OLE Objects</span></span>
  <span data-ttu-id="4b803-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose l’interface **ISequentialStream** pour prendre en charge l’accès des consommateurs aux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types de données **ntext**, **Text**, **image**, **varchar (max)**, **nvarchar (max)**, **varbinary (max)** et XML en tant qu’objets BLOB (Binary Large Object).</span><span class="sxs-lookup"><span data-stu-id="4b803-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **ISequentialStream** interface to support consumer access to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **ntext**, **text**, **image**, **varchar(max)**, **nvarchar(max)**, **varbinary(max)**, and xml data types as binary large objects (BLOBs).</span></span> <span data-ttu-id="4b803-104">La méthode **Read** sur **ISequentialStream** permet au consommateur de récupérer un grand nombre de données en blocs maniables.</span><span class="sxs-lookup"><span data-stu-id="4b803-104">The **Read** method on **ISequentialStream** lets the consumer retrieve much data in manageable chunks.</span></span>  
  
 <span data-ttu-id="4b803-105">Pour obtenir un exemple illustrant cette fonctionnalité, consultez [Définir des données volumineuses &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="4b803-105">For a sample demonstrating this feature, see [Set Large Data &#40;OLE DB&#41;](../native-client-ole-db-how-to/set-large-data-ole-db.md).</span></span>  
  
 <span data-ttu-id="4b803-106">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client peut utiliser une interface **IStorage** implémentée par le consommateur lorsque le consommateur fournit le pointeur d’interface dans un accesseur lié pour la modification des données.</span><span class="sxs-lookup"><span data-stu-id="4b803-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can use a consumer-implemented **IStorage** interface when the consumer provides the interface pointer in an accessor bound for data modification.</span></span>  
  
 <span data-ttu-id="4b803-107">Pour les types de données de valeur élevée, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client vérifie les hypothèses de taille de type dans les interfaces **IROWSET** et DDL.</span><span class="sxs-lookup"><span data-stu-id="4b803-107">For large value data types, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider checks for type size assumptions in **IRowset** and DDL interfaces.</span></span> <span data-ttu-id="4b803-108">Les colonnes avec des types de données **varchar**, **nvarchar**et **varbinary** dont la taille maximale est définie sur illimité sont représentées en tant que IsLong via les ensembles de lignes de schéma et les interfaces qui retournent des types de données de colonne.</span><span class="sxs-lookup"><span data-stu-id="4b803-108">Columns with **varchar**, **nvarchar**, and **varbinary** data types with max size set to unlimited will be represented as ISLONG through the schema rowsets and interfaces returning column data types.</span></span>  
  
 <span data-ttu-id="4b803-109">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client expose les types **varchar (max)**, **varbinary (max)** et **nvarchar (max)** comme DBTYPE_STR, DBTYPE_BYTES et DBTYPE_WSTR respectivement.</span><span class="sxs-lookup"><span data-stu-id="4b803-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **varchar(max)**, **varbinary(max)** and **nvarchar(max)** types as DBTYPE_STR, DBTYPE_BYTES and DBTYPE_WSTR respectively.</span></span>  
  
 <span data-ttu-id="4b803-110">Pour travailler avec ces types une application possède les options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4b803-110">To work with these types an application has the following options:</span></span>  
  
-   <span data-ttu-id="4b803-111">Lier comme type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span><span class="sxs-lookup"><span data-stu-id="4b803-111">Bind as the type (DBTYPE_STR, DBTYPE_BYTES, DBTYPE_WSTR).</span></span> <span data-ttu-id="4b803-112">Si la mémoire tampon n'est pas assez grande il s'ensuit une troncation, exactement comme pour ces types dans les précédentes versions (bien que de plus grandes valeurs soient maintenant disponibles).</span><span class="sxs-lookup"><span data-stu-id="4b803-112">If the buffer is not big enough truncation will occur, exactly as for these types in previous releases (although larger values are now available).</span></span>  
  
-   <span data-ttu-id="4b803-113">Lier comme type et spécifier également DBTYPE_BYREF.</span><span class="sxs-lookup"><span data-stu-id="4b803-113">Bind as the type and also specify DBTYPE_BYREF.</span></span>  
  
-   <span data-ttu-id="4b803-114">Lier comme DBTYPE_IUNKNOWN et utiliser la diffusion en continu.</span><span class="sxs-lookup"><span data-stu-id="4b803-114">Bind as DBTYPE_IUNKNOWN and use streaming.</span></span>  
  
 <span data-ttu-id="4b803-115">En cas de liaison à DBTYPE_IUNKNOWN, la fonctionnalité de flux ISequentialStream est utilisée.</span><span class="sxs-lookup"><span data-stu-id="4b803-115">If bound to DBTYPE_IUNKNOWN, ISequentialStream stream functionality is used.</span></span> <span data-ttu-id="4b803-116">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge la liaison des paramètres de sortie comme DBTYPE_IUNKNOWN pour les types de données de valeur élevée afin de faciliter les scénarios dans lesquels une procédure stockée retourne ces types de données comme valeurs de retour qui seront exposées comme DBTYPE_IUNKNOWN au client.</span><span class="sxs-lookup"><span data-stu-id="4b803-116">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports binding output parameters as DBTYPE_IUNKNOWN for large value data types to facilitate scenarios where a stored procedure returns these data types as return values which will be exposed as DBTYPE_IUNKNOWN to the client.</span></span>  
  
## <a name="storage-object-limitations"></a><span data-ttu-id="4b803-117">Limitations des objets de stockage</span><span class="sxs-lookup"><span data-stu-id="4b803-117">Storage Object Limitations</span></span>  
  
-   <span data-ttu-id="4b803-118">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client ne peut prendre en charge qu’un seul objet de stockage ouvert.</span><span class="sxs-lookup"><span data-stu-id="4b803-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider can support only a single open storage object.</span></span> <span data-ttu-id="4b803-119">Les tentatives d’ouverture de plusieurs objets de stockage (pour obtenir une référence sur plusieurs pointeurs d’interface **ISequentialStream**) retournent DBSTATUS_E_CANTCREATE.</span><span class="sxs-lookup"><span data-stu-id="4b803-119">Attempts to open more than one storage object (to get a reference on more than one **ISequentialStream** interface pointer) return DBSTATUS_E_CANTCREATE.</span></span>  
  
-   <span data-ttu-id="4b803-120">Dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client, la valeur par défaut de la propriété DBPROP_BLOCKINGSTORAGEOBJECTS en lecture seule est VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="4b803-120">In the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, the default value of the DBPROP_BLOCKINGSTORAGEOBJECTS read-only property is VARIANT_TRUE.</span></span> <span data-ttu-id="4b803-121">Cela signifie que si un objet de stockage est actif, certaines méthodes (autres que celles sur les objets de stockage) échouent avec E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="4b803-121">This indicates that if a storage object is active, some methods (other than those on the storage objects) will fail with E_UNEXPECTED.</span></span>  
  
-   <span data-ttu-id="4b803-122">La longueur des données présentées par un objet de stockage implémenté par le consommateur doit être connue du [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client lorsque l’accesseur de ligne qui fait référence à l’objet de stockage est créé.</span><span class="sxs-lookup"><span data-stu-id="4b803-122">The length of data presented by a consumer-implemented storage object must be made known to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider when the row accessor that references the storage object is created.</span></span> <span data-ttu-id="4b803-123">Le consommateur doit lier un indicateur de longueur dans la structure DBBINDING utilisée pour la création de l'accesseur.</span><span class="sxs-lookup"><span data-stu-id="4b803-123">The consumer must bind a length indicator in the DBBINDING structure used for accessor creation.</span></span>  
  
-   <span data-ttu-id="4b803-124">Si une ligne contient plus d’une valeur de données volumineuse et que DBPROP_ACCESSORDER n’est pas DBPROPVAL_AO_RANDOM, le consommateur doit utiliser un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ensemble de lignes pris en charge par le curseur du fournisseur Native Client OLE DB pour récupérer des données de ligne ou traiter toutes les valeurs de données volumineuses avant de récupérer d’autres valeurs de ligne.</span><span class="sxs-lookup"><span data-stu-id="4b803-124">If a row contains more than a single large data value and DBPROP_ACCESSORDER is not DBPROPVAL_AO_RANDOM, the consumer must either use a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider cursor-supported rowset to retrieve row data or process all large data values before retrieving other row values.</span></span> <span data-ttu-id="4b803-125">Si DBPROP_ACCESSORDER est DBPROPVAL_AO_RANDOM, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client met en cache tous les types de données XML en tant qu’objets BLOB (Binary Large Object) afin qu’ils soient accessibles dans n’importe quel ordre.</span><span class="sxs-lookup"><span data-stu-id="4b803-125">If DBPROP_ACCESSORDER is DBPROPVAL_AO_RANDOM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider caches all the xml data types as binary large objects (BLOBs) so that it can be accessed in any order.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4b803-126">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="4b803-126">In This Section</span></span>  
  
-   [<span data-ttu-id="4b803-127">Obtention de données volumineuses</span><span class="sxs-lookup"><span data-stu-id="4b803-127">Getting Large Data</span></span>](getting-large-data.md)  
  
-   [<span data-ttu-id="4b803-128">Définition de données volumineuses</span><span class="sxs-lookup"><span data-stu-id="4b803-128">Setting Large Data</span></span>](setting-large-data.md)  
  
-   [<span data-ttu-id="4b803-129">Prise en charge de la diffusion en continu pour les paramètres de sortie BLOB</span><span class="sxs-lookup"><span data-stu-id="4b803-129">Streaming Support for BLOB Output Parameters</span></span>](streaming-support-for-blob-output-parameters.md)  
  
## <a name="see-also"></a><span data-ttu-id="4b803-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4b803-130">See Also</span></span>  
 <span data-ttu-id="4b803-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="4b803-131">[SQL Server Native Client &#40;OLE DB&#41;](../native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 [<span data-ttu-id="4b803-132">Utilisation de types de valeur élevée</span><span class="sxs-lookup"><span data-stu-id="4b803-132">Using Large Value Types</span></span>](../native-client/features/using-large-value-types.md)  
  
  
