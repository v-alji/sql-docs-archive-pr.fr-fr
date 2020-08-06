---
title: Améliorations des types de données de date et d’heure (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- date/time [OLE DB]
- OLE DB, date/time improvements
ms.assetid: 71614aaf-0fa4-4fe0-b522-68e2e0b66f43
author: rothja
ms.author: jroth
ms.openlocfilehash: 16bb9e98691aea829eb71a16ddabddb371d7bcf3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707483"
---
# <a name="date-and-time-improvements-ole-db"></a><span data-ttu-id="eebc1-102">Améliorations des types de données de date et d’heure (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="eebc1-102">Date and Time Improvements (OLE DB)</span></span>
  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="eebc1-103">introduit de nouveaux types de données de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="eebc1-103">introduces new date and time data types.</span></span> <span data-ttu-id="eebc1-104">Cette section décrit comment ces nouveaux types sont exposés en tant qu’extensions dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="eebc1-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="eebc1-105">Pour obtenir une vue d’ensemble de la [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prise en charge native client pour les nouveaux types de données de date et d’heure, consultez améliorations de la [date et](../native-client/features/date-and-time-improvements.md)de l’heure.</span><span class="sxs-lookup"><span data-stu-id="eebc1-105">For an overview of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="eebc1-106">Pour obtenir un exemple, voir [Utiliser les fonctionnalités de date et d’heure améliorées &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="eebc1-106">For a sample, see [Use Enhanced Date and Time Features &#40;OLE DB&#41;](../native-client-ole-db-how-to/use-enhanced-date-and-time-features-ole-db.md).</span></span>  
  
 <span data-ttu-id="eebc1-107">Pour plus d'informations sur les types de données de date et d'heure, consultez [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eebc1-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eebc1-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="eebc1-108">In This Section</span></span>  
 [<span data-ttu-id="eebc1-109">Prise en charge des types de données pour les améliorations de date et d’heure OLE DB</span><span class="sxs-lookup"><span data-stu-id="eebc1-109">Data Type Support for OLE DB Date and Time Improvements</span></span>](../../relational-databases/native-client-ole-db-date-time/data-type-support-for-ole-db-date-and-time-improvements.md)  
 <span data-ttu-id="eebc1-110">Fournit des informations sur les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] types OLE DB (Native Client) qui prennent en charge [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] les types de données de date et d’heure.</span><span class="sxs-lookup"><span data-stu-id="eebc1-110">Provides information about OLE DB ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client) types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="eebc1-111">Métadonnées &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="eebc1-111">Metadata &#40;OLE DB&#41;</span></span>](../../database-engine/dev-guide/metadata-ole-db.md)  
 <span data-ttu-id="eebc1-112">Contient des informations sur la structure DBBINDING,,, `ICommandWithParameters::GetParameterInfo` `ICommandWithParameters::SetParameterInfo` `IColumnsRowset::GetColumnsRowset` et I `ColumnsInfo::GetColumnInfo` . Fournit également des informations sur les mises à jour de OLE DB ensembles de lignes de schéma.</span><span class="sxs-lookup"><span data-stu-id="eebc1-112">Contains information about the DBBINDING structure, `ICommandWithParameters::GetParameterInfo`, `ICommandWithParameters::SetParameterInfo`, `IColumnsRowset::GetColumnsRowset`, and I`ColumnsInfo::GetColumnInfo`. Also provides information about updates to OLE DB schema rowsets.</span></span>  
  
 [<span data-ttu-id="eebc1-113">Liaisons et conversions &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="eebc1-113">Bindings and Conversions &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client-ole-db-date-time/conversions-ole-db.md)  
 <span data-ttu-id="eebc1-114">Décrit les règles de conversion entre le serveur et le client pour les types date nouveaux et existants.</span><span class="sxs-lookup"><span data-stu-id="eebc1-114">Describes the rules for conversion between server and client for both existing and new date types.</span></span>  
  
 [<span data-ttu-id="eebc1-115">Modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="eebc1-115">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="eebc1-116">Décrit les améliorations des types date/time pour prendre en charge les opérations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="eebc1-116">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="eebc1-117">Prise en charge des API OLE DB pour les améliorations de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="eebc1-117">OLE DB API Support for Date and Time Enhancements</span></span>](ole-db-api-support-for-date-and-time-enhancements.md)  
 <span data-ttu-id="eebc1-118">Décrit les API OLE DB qui prennent en charge les fonctionnalités améliorées des types date/time.</span><span class="sxs-lookup"><span data-stu-id="eebc1-118">Describes the OLE DB APIs that support enhanced date/time features.</span></span>  
  
 [<span data-ttu-id="eebc1-119">Comparabilité pour IRowsetFind</span><span class="sxs-lookup"><span data-stu-id="eebc1-119">Comparability for IRowsetFind</span></span>](../../relational-databases/native-client-ole-db-date-time/comparability-for-irowsetfind.md)  
 <span data-ttu-id="eebc1-120">Décrit les types date/time et `IRowsetFind`.</span><span class="sxs-lookup"><span data-stu-id="eebc1-120">Describes date/time types and `IRowsetFind`.</span></span>  
  
 [<span data-ttu-id="eebc1-121">Nouvelles fonctionnalités de date et d’heure avec des versions antérieures de SQL Server &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="eebc1-121">New Date and Time Features with Previous SQL Server Versions &#40;OLE DB&#41;</span></span>](new-date-and-time-features-with-previous-sql-server-versions-ole-db.md)  
 <span data-ttu-id="eebc1-122">Décrit le comportement attendu lorsqu'une application cliente qui utilise les fonctionnalités améliorées des types date et time communique avec une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], et lorsqu'un client compilé avec une version précédente de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client envoie des commandes à un serveur qui prend en charge les fonctionnalités améliorées des types date et time.</span><span class="sxs-lookup"><span data-stu-id="eebc1-122">Describes the expected behavior when a client application that uses enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eebc1-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eebc1-123">See Also</span></span>  
 [<span data-ttu-id="eebc1-124">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="eebc1-124">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
