---
title: Ensemble de lignes LINKEDSERVERS (OLE DB) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- LINKEDSERVERS rowset
- enumerating data sources [OLE DB]
ms.assetid: 2633fd8a-65e7-498d-9aed-8e4b1cca2381
author: rothja
ms.author: jroth
ms.openlocfilehash: 80eded31ebae744e272757a53a7fd1f4b56bf358
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602100"
---
# <a name="linkedservers-rowset-ole-db"></a><span data-ttu-id="53b42-102">Ensemble de lignes LINKEDSERVERS (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="53b42-102">LINKEDSERVERS Rowset (OLE DB)</span></span>
  <span data-ttu-id="53b42-103">L’ensemble de lignes **LINKEDSERVERS** énumère les sources de données de l’organisation qui peuvent participer aux requêtes distribuées [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="53b42-103">The **LINKEDSERVERS** rowset enumerates organization data sources that can participate in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries.</span></span>  
  
 <span data-ttu-id="53b42-104">L'ensemble de lignes **LINKEDSERVERS** contient les colonnes suivantes.</span><span class="sxs-lookup"><span data-stu-id="53b42-104">The **LINKEDSERVERS** rowset contains the following columns.</span></span>  
  
|<span data-ttu-id="53b42-105">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="53b42-105">Column name</span></span>|<span data-ttu-id="53b42-106">Indicateur de type</span><span class="sxs-lookup"><span data-stu-id="53b42-106">Type indicator</span></span>|<span data-ttu-id="53b42-107">Description</span><span class="sxs-lookup"><span data-stu-id="53b42-107">Description</span></span>|  
|-----------------|--------------------|-----------------|  
|<span data-ttu-id="53b42-108">SVR_NAME</span><span class="sxs-lookup"><span data-stu-id="53b42-108">SVR_NAME</span></span>|<span data-ttu-id="53b42-109">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="53b42-109">DBTYPE_WSTR</span></span>|<span data-ttu-id="53b42-110">Nom d'un serveur lié.</span><span class="sxs-lookup"><span data-stu-id="53b42-110">Name of a linked server.</span></span>|  
|<span data-ttu-id="53b42-111">SVR_PRODUCT</span><span class="sxs-lookup"><span data-stu-id="53b42-111">SVR_PRODUCT</span></span>|<span data-ttu-id="53b42-112">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="53b42-112">DBTYPE_WSTR</span></span>|<span data-ttu-id="53b42-113">Fabricant ou autre nom identifiant le type de banque de données représenté par le nom du serveur lié.</span><span class="sxs-lookup"><span data-stu-id="53b42-113">Manufacturer or other name identifying the type of data store represented by the name of the linked server.</span></span>|  
|<span data-ttu-id="53b42-114">SVR_PROVIDERNAME</span><span class="sxs-lookup"><span data-stu-id="53b42-114">SVR_PROVIDERNAME</span></span>|<span data-ttu-id="53b42-115">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="53b42-115">DBTYPE_WSTR</span></span>|<span data-ttu-id="53b42-116">Nom convivial du fournisseur OLE DB utilisé pour consommer les données du serveur.</span><span class="sxs-lookup"><span data-stu-id="53b42-116">Friendly name of the OLE DB provider used to consume data from the server.</span></span>|  
|<span data-ttu-id="53b42-117">SVR_DATASOURCE</span><span class="sxs-lookup"><span data-stu-id="53b42-117">SVR_DATASOURCE</span></span>|<span data-ttu-id="53b42-118">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="53b42-118">DBTYPE_WSTR</span></span>|<span data-ttu-id="53b42-119">Chaîne OLE DB DBPROP_INIT_DATASOURCE utilisée pour acquérir une source de données à partir du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="53b42-119">OLE DB DBPROP_INIT_DATASOURCE string used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="53b42-120">SVR_PROVIDERSTRING</span><span class="sxs-lookup"><span data-stu-id="53b42-120">SVR_PROVIDERSTRING</span></span>|<span data-ttu-id="53b42-121">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="53b42-121">DBTYPE_WSTR</span></span>|<span data-ttu-id="53b42-122">Valeur OLE DB DBPROP_INIT_PROVIDERSTRING utilisée pour acquérir une source de données à partir du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="53b42-122">OLE DB DBPROP_INIT_PROVIDERSTRING value used to acquire a data source from the provider.</span></span>|  
|<span data-ttu-id="53b42-123">SVR_LOCATION</span><span class="sxs-lookup"><span data-stu-id="53b42-123">SVR_LOCATION</span></span>|<span data-ttu-id="53b42-124">DBTYPE_WSTR</span><span class="sxs-lookup"><span data-stu-id="53b42-124">DBTYPE_WSTR</span></span>|<span data-ttu-id="53b42-125">Chaîne OLE DB DBPROP_INIT_LOCATION utilisée pour acquérir une source de données à partir du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="53b42-125">OLE DB DBPROP_INIT_LOCATION string used to acquire a data source from the provider.</span></span>|  
  
 <span data-ttu-id="53b42-126">L'ensemble de lignes est trié sur SRV_NAME et une restriction unique est prise en charge sur SRV_NAME.</span><span class="sxs-lookup"><span data-stu-id="53b42-126">The rowset is sorted on SRV_NAME and a single restriction is supported on SRV_NAME.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b42-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="53b42-127">See Also</span></span>  
 [<span data-ttu-id="53b42-128">Prise en charge des ensembles de lignes de schéma &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="53b42-128">Schema Rowset Support &#40;OLE DB&#41;</span></span>](schema-rowset-support-ole-db.md)  
  
  
