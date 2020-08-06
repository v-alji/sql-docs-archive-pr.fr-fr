---
title: Prise en charge des API OLE DB pour les améliorations de date et d’heure | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- OLE DB, date/time improvements
ms.assetid: e65c9253-bd99-4dc3-9cb8-7613f754c966
author: rothja
ms.author: jroth
ms.openlocfilehash: cdb17f0d2104373ea797ff9403cc417dfaa3d868
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612805"
---
# <a name="ole-db-api-support-for-date-and-time-enhancements"></a><span data-ttu-id="a68b5-102">Prise en charge des API OLE DB pour les améliorations de date et d’heure</span><span class="sxs-lookup"><span data-stu-id="a68b5-102">OLE DB API Support for Date and Time Enhancements</span></span>
  <span data-ttu-id="a68b5-103">Les API OLE DB suivantes prennent en charge les fonctionnalités de date/heure améliorées.</span><span class="sxs-lookup"><span data-stu-id="a68b5-103">The following OLE DB APIs support enhanced date/time features.</span></span>  
  
|<span data-ttu-id="a68b5-104">Fonction</span><span class="sxs-lookup"><span data-stu-id="a68b5-104">Function</span></span>|<span data-ttu-id="a68b5-105">Description</span><span class="sxs-lookup"><span data-stu-id="a68b5-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a68b5-106">IAccessor::CreateAccessor</span><span class="sxs-lookup"><span data-stu-id="a68b5-106">IAccessor::CreateAccessor</span></span>|<span data-ttu-id="a68b5-107">Un indicateur est ajouté dans la structure DBBINDING pour permettre aux applications de distinguer les valeurs `datetime`, `datetime2` et `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="a68b5-107">A flag is added in the DBBINDING structure to enable applications to discriminate between `datetime`, `datetime2`, and `smalldatetime` values.</span></span> <span data-ttu-id="a68b5-108">Pour plus d’informations, consultez [Métadonnées de paramètre et d'ensemble de lignes](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-108">For more information, see [Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="a68b5-109">IBCPSession::BCPColFmt</span><span class="sxs-lookup"><span data-stu-id="a68b5-109">IBCPSession::BCPColFmt</span></span>|<span data-ttu-id="a68b5-110">Pour plus d’informations, consultez [modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-110">For more information, see [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>|  
|<span data-ttu-id="a68b5-111">ICommandWithParameters::GetParameterInfo</span><span class="sxs-lookup"><span data-stu-id="a68b5-111">ICommandWithParameters::GetParameterInfo</span></span>|<span data-ttu-id="a68b5-112">Pour plus d’informations, consultez [Métadonnées de paramètre et d'ensemble de lignes](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-112">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="a68b5-113">ICommandWithParameters::SetParameterinfo</span><span class="sxs-lookup"><span data-stu-id="a68b5-113">ICommandWithParameters::SetParameterinfo</span></span>|<span data-ttu-id="a68b5-114">Pour plus d’informations, consultez [Métadonnées de paramètre et d'ensemble de lignes](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-114">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="a68b5-115">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="a68b5-115">IColumnsRowset::GetColumnsRowset</span></span>|<span data-ttu-id="a68b5-116">Pour plus d’informations, consultez [Métadonnées de paramètre et d'ensemble de lignes](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-116">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="a68b5-117">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="a68b5-117">IColumnsInfo::GetColumnInfo</span></span>|<span data-ttu-id="a68b5-118">Pour plus d’informations, consultez [Métadonnées de paramètre et d'ensemble de lignes](metadata-parameter-and-rowset.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-118">For more information, see[Parameter and Rowset Metadata](metadata-parameter-and-rowset.md).</span></span>|  
|<span data-ttu-id="a68b5-119">IDBSchemaRowset::GetRowset</span><span class="sxs-lookup"><span data-stu-id="a68b5-119">IDBSchemaRowset::GetRowset</span></span>|<span data-ttu-id="a68b5-120">Pour plus d’informations sur les ensembles de lignes de schéma affectés, consultez [Date et heure et ensembles de lignes de schéma](../native-client-ole-db-rowsets/rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-120">For details of the affected schema rowsets, see[Date and Time and Schema Rowsets](../native-client-ole-db-rowsets/rowsets.md).</span></span>|  
|<span data-ttu-id="a68b5-121">IRowsetFastLoad</span><span class="sxs-lookup"><span data-stu-id="a68b5-121">IRowsetFastLoad</span></span>|<span data-ttu-id="a68b5-122">Cette interface prend en charge les nouveaux types date/heure, mais aucune modification n'a été apportée à son interface.</span><span class="sxs-lookup"><span data-stu-id="a68b5-122">This interface supports the new date/time types, but there is no change to its interface.</span></span>|  
|<span data-ttu-id="a68b5-123">ITableDefinition::CreateTable</span><span class="sxs-lookup"><span data-stu-id="a68b5-123">ITableDefinition::CreateTable</span></span>|<span data-ttu-id="a68b5-124">Pour plus d’informations, consultez [Prise en charge des types de données pour les améliorations de date et d’heure OLE DB](data-type-support-for-ole-db-date-and-time-improvements.md).</span><span class="sxs-lookup"><span data-stu-id="a68b5-124">For more information, see [Data Type Support for OLE DB Date and Time Improvements](data-type-support-for-ole-db-date-and-time-improvements.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a68b5-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a68b5-125">See Also</span></span>  
 [<span data-ttu-id="a68b5-126">Améliorations des types de données de date et d’heure &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="a68b5-126">Date and Time Improvements &#40;OLE DB&#41;</span></span>](date-and-time-improvements-ole-db.md)  
  
  
