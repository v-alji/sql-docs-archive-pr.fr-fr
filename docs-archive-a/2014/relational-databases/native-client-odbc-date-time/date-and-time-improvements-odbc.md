---
title: Améliorations de la date et de l’heure (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- date/time [ODBC]
- ODBC, date/time improvements
ms.assetid: e31d5ca5-2103-498f-954c-1ee93e217186
author: rothja
ms.author: jroth
ms.openlocfilehash: 6ce8f906fc1949a80bfa8e5a541ecf1e83878775
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605389"
---
# <a name="date-and-time-improvements-odbc"></a><span data-ttu-id="2a3d0-102">Améliorations de la date et de l’heure (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2a3d0-102">Date and Time Improvements (ODBC)</span></span>
  [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="2a3d0-103">a introduit de nouveaux types de données de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-103">introduced new date and time data types.</span></span> <span data-ttu-id="2a3d0-104">Cette section décrit comment ces nouveaux types sont exposés en tant qu’extensions dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-104">This section describes how these new types are exposed as extensions in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="2a3d0-105">Pour obtenir une vue d’ensemble de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la prise en charge native client pour les nouveaux types de données de date et d’heure, consultez améliorations de la [date et](../native-client/features/date-and-time-improvements.md)de l’heure.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-105">For an overview of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client support for the new date and time data types, see [Date and Time Improvements](../native-client/features/date-and-time-improvements.md).</span></span> <span data-ttu-id="2a3d0-106">Pour obtenir un exemple illustrant la prise en charge de la date et de l’heure ODBC, consultez [utiliser les types de date et d’heure](../native-client-odbc-how-to/use-date-and-time-types.md).</span><span class="sxs-lookup"><span data-stu-id="2a3d0-106">For a sample demonstrating ODBC date/time support, see [Use Date and Time Types](../native-client-odbc-how-to/use-date-and-time-types.md).</span></span>  
  
 <span data-ttu-id="2a3d0-107">Pour plus d'informations sur les types de données de date et d'heure, consultez [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2a3d0-107">For more general information about date and time data types, see [datetime &#40;Transact-SQL&#41;](/sql/t-sql/data-types/datetime-transact-sql).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a3d0-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2a3d0-108">In This Section</span></span>  
 [<span data-ttu-id="2a3d0-109">Prise en charge des types de données pour les améliorations date/heure (ODBC)</span><span class="sxs-lookup"><span data-stu-id="2a3d0-109">Data Type Support for ODBC Date and Time Improvements</span></span>](../../relational-databases/native-client-odbc-date-time/data-type-support-for-odbc-date-and-time-improvements.md)  
 <span data-ttu-id="2a3d0-110">Fournit des informations sur les types ODBC qui prennent en charge les types de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de date et d'heure.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-110">Provides information about ODBC types that support [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] date and time data types.</span></span>  
  
 [<span data-ttu-id="2a3d0-111">Métadonnées &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2a3d0-111">Metadata &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/metadata-odbc.md)  
 <span data-ttu-id="2a3d0-112">Décrit les informations retournées dans le champ de descripteur de paramètre d'implémentation (IPD) et dans le champ de descripteur de ligne d'implémentation (IRD), ainsi que les métadonnées de colonne retournées par `SQLColumns` et `SQLProcedureColumns`.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-112">Describes information returned in the implementation parameter descriptor (IPD) and implementation row descriptor (IRD) fields, as well as column metadata returned by `SQLColumns` and `SQLProcedureColumns`.</span></span> <span data-ttu-id="2a3d0-113">Elle décrit également les métadonnées de type de données retournées par `SQLGetTypeInfo`.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-113">Also describes data type metadata returned by `SQLGetTypeInfo`.</span></span>  
  
 [<span data-ttu-id="2a3d0-114">conversions de type de données DateTime &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2a3d0-114">datetime Data Type Conversions &#40;ODBC&#41;</span></span>](datetime-data-type-conversions-odbc.md)  
 <span data-ttu-id="2a3d0-115">Décrit comment effectuer une conversion entre les valeurs datetime et datetimeoffset.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-115">Describes how to convert between datetime and datetimeoffset values.</span></span>  
  
 [<span data-ttu-id="2a3d0-116">Prise en charge sql_variant pour les types Date et Time</span><span class="sxs-lookup"><span data-stu-id="2a3d0-116">sql_variant Support for Date and Time Types</span></span>](sql-variant-support-for-date-and-time-types.md)  
 <span data-ttu-id="2a3d0-117">Décrit la prise en charge de la fonction SQL_VARIANT pour les fonctionnalités de date et heure améliorées.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-117">Describes SQL_VARIANT function support for enhanced date and time functionality.</span></span>  
  
 [<span data-ttu-id="2a3d0-118">Modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2a3d0-118">Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;</span></span>](../../relational-databases/native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)  
 <span data-ttu-id="2a3d0-119">Décrit les améliorations des types date/time pour prendre en charge les opérations de copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-119">Describes date/time enhancements to support bulk copy operations.</span></span>  
  
 [<span data-ttu-id="2a3d0-120">Comportement du type de date et d’heure amélioré avec les versions antérieures de SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2a3d0-120">Enhanced Date and Time Type Behavior with Previous SQL Server Versions &#40;ODBC&#41;</span></span>](enhanced-date-and-time-type-behavior-with-previous-sql-server-versions-odbc.md)  
 <span data-ttu-id="2a3d0-121">Décrit le comportement attendu lorsqu’une application cliente utilisant les fonctionnalités améliorées de date et d’heure communique avec une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , et lorsqu’un client compilé avec une version antérieure de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native client envoie des commandes à un serveur qui prend en charge les fonctionnalités de date et d’heure améliorées.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-121">Describes the expected behavior when a client application using enhanced date and time features communicates with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and when a client compiled with an older version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sends commands to a server that supports enhanced date and time features.</span></span>  
  
 [<span data-ttu-id="2a3d0-122">Prise en charge des fonctionnalités de date et heure améliorées par l’API ODBC</span><span class="sxs-lookup"><span data-stu-id="2a3d0-122">ODBC API Support for Enhanced Date and Time Features</span></span>](odbc-api-support-for-enhanced-date-and-time-features.md)  
 <span data-ttu-id="2a3d0-123">Répertorie les fonctions ODBC qui prennent en charge les fonctionnalités de date et heure améliorées.</span><span class="sxs-lookup"><span data-stu-id="2a3d0-123">Lists the ODBC functions that support enhanced date and time functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3d0-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2a3d0-124">See Also</span></span>  
 [<span data-ttu-id="2a3d0-125">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="2a3d0-125">SQL Server Native Client &#40;ODBC&#41;</span></span>](../../relational-databases/native-client/odbc/sql-server-native-client-odbc.md)  
  
  
