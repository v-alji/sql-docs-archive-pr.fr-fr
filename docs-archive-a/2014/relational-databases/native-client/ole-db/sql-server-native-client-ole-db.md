---
title: SQL Server Native Client (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, about SQL Server Native Client OLE DB provider
- OLE DB, SQL Server Native Client OLE DB provider
- data access [SQL Server Native Client], OLE DB
- SQLNCLI, OLE DB
- OLE DB
- SQL Server Native Client OLE DB provider
- SQL Server Native Client, OLE DB
ms.assetid: da846da4-ec19-4a4f-81fb-7d5a2b2bf80a
author: rothja
ms.author: jroth
ms.openlocfilehash: 46b948eb1d075edc6000849dcb2d18ea372809d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603962"
---
# <a name="sql-server-native-client-ole-db"></a><span data-ttu-id="8c7a8-102">SQL Server Native Client (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="8c7a8-102">SQL Server Native Client (OLE DB)</span></span>
  <span data-ttu-id="8c7a8-103">Le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est une API COM de bas niveau qui est utilisée pour accéder aux données.</span><span class="sxs-lookup"><span data-stu-id="8c7a8-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a low-level COM API that is used for accessing data.</span></span> <span data-ttu-id="8c7a8-104">Le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est recommandé pour développer des outils, des utilitaires ou des composants de bas niveau qui ont besoin de performances élevées.</span><span class="sxs-lookup"><span data-stu-id="8c7a8-104">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is recommended for developing tools, utilities, or low-level components that need high performance.</span></span> <span data-ttu-id="8c7a8-105">Le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client est un fournisseur natif de hautes performances qui accède directement au protocole TDS (Tabular Data Stream) [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c7a8-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is a native, high performance provider that accesses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Tabular Data Stream (TDS) protocol directly.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="8c7a8-106">Native Client fournit la prise en charge OLE DB aux applications qui se connectent à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c7a8-106">Native Client provides OLE DB support to applications connecting to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8c7a8-107">Le [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client est un fournisseur conforme à la version 2,0 de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="8c7a8-107">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider is an OLE DB version 2.0-compliant provider.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c7a8-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="8c7a8-108">In This Section</span></span>  
  
-   [<span data-ttu-id="8c7a8-109">Création d'une application de fournisseur OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8c7a8-109">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](../../native-client-ole-db-provider/creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
-   [<span data-ttu-id="8c7a8-110">Objets source de données &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-110">Data Source Objects &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-source-objects/data-source-objects-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-111">Commandes</span><span class="sxs-lookup"><span data-stu-id="8c7a8-111">Commands</span></span>](../../native-client-ole-db-commands/commands.md)  
  
-   [<span data-ttu-id="8c7a8-112">Ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="8c7a8-112">Rowsets</span></span>](../../native-client-ole-db-rowsets/rowsets.md)  
  
-   [<span data-ttu-id="8c7a8-113">Procédures stockées</span><span class="sxs-lookup"><span data-stu-id="8c7a8-113">Stored Procedures</span></span>](stored-procedures.md)  
  
-   [<span data-ttu-id="8c7a8-114">Objets BLOB et OLE</span><span class="sxs-lookup"><span data-stu-id="8c7a8-114">BLOBs and OLE Objects</span></span>](../../native-client-ole-db-blobs/blobs-and-ole-objects.md)  
  
-   [<span data-ttu-id="8c7a8-115">Tables et index</span><span class="sxs-lookup"><span data-stu-id="8c7a8-115">Tables and Indexes</span></span>](../../native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
-   [<span data-ttu-id="8c7a8-116">Types de données &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-116">Data Types &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-data-types/data-types-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-117">Prise en charge des ensembles de lignes de schéma &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-117">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-118">Paramètres table &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-118">Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-119">Améliorations des types de données de date et d’heure &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-119">Date and Time Improvements &#40;OLE DB&#41;</span></span>](../../native-client-ole-db-date-time/date-and-time-improvements-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-120">Types CLR de grande taille définis par l’utilisateur &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-120">Large CLR User-Defined Types &#40;OLE DB&#41;</span></span>](large-clr-user-defined-types-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-121">Prise en charge FILESTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-121">FILESTREAM Support &#40;OLE DB&#41;</span></span>](filestream-support-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-122">Transactions</span><span class="sxs-lookup"><span data-stu-id="8c7a8-122">Transactions</span></span>](../../native-client-ole-db-transactions/transactions.md)  
  
-   [<span data-ttu-id="8c7a8-123">Erreurs</span><span class="sxs-lookup"><span data-stu-id="8c7a8-123">Errors</span></span>](../../native-client-ole-db-errors/errors.md)  
  
-   [<span data-ttu-id="8c7a8-124">Noms de principaux du service &#40;noms SPN&#41; dans les connexions clientes &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-124">Service Principal Names &#40;SPNs&#41; in Client Connections &#40;OLE DB&#41;</span></span>](service-principal-names-spns-in-client-connections-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-125">Prise en charge des colonnes éparses &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-125">Sparse Columns Support &#40;OLE DB&#41;</span></span>](sparse-columns-support-ole-db.md)  
  
-   [<span data-ttu-id="8c7a8-126">SQL Server Native Client &#40;OLE DB référence de&#41;</span><span class="sxs-lookup"><span data-stu-id="8c7a8-126">SQL Server Native Client &#40;OLE DB&#41; Reference</span></span>](../../native-client-ole-db-interfaces/sql-server-native-client-ole-db-interfaces.md)  
  
-   [<span data-ttu-id="8c7a8-127">Rubriques de procédures liées à OLE DB</span><span class="sxs-lookup"><span data-stu-id="8c7a8-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c7a8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c7a8-128">See Also</span></span>  
 [<span data-ttu-id="8c7a8-129">Programmation de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="8c7a8-129">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
