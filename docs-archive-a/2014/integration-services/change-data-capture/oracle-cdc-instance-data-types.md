---
title: Types de données d’instance Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 71d4ce02db89c1bfd11fe9a3a3535fc92fbc49fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695955"
---
# <a name="oracle-cdc-instance-data-types"></a><span data-ttu-id="6193a-102">Types de données d'instance Oracle CDC</span><span class="sxs-lookup"><span data-stu-id="6193a-102">Oracle CDC Instance Data Types</span></span>
  <span data-ttu-id="6193a-103">L'instance Oracle CDC prend en charge la plupart des types de données Oracle.</span><span class="sxs-lookup"><span data-stu-id="6193a-103">The Oracle CDC Instance supports most Oracle data types.</span></span> <span data-ttu-id="6193a-104">Les sections suivantes décrivent les types de données pris en charge et les types de données non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6193a-104">The following sections describe the supported data types and the non-supported data types.</span></span>  
  
## <a name="supported-data-types"></a><span data-ttu-id="6193a-105">Types de données pris en charge</span><span class="sxs-lookup"><span data-stu-id="6193a-105">Supported Data Types</span></span>  
 <span data-ttu-id="6193a-106">Le tableau suivant décrit les types de données Oracle qui peuvent être capturés et leur mappage par défaut aux types de données SQL Server dans les tables de modifications.</span><span class="sxs-lookup"><span data-stu-id="6193a-106">The following table describes the Oracle data types that can be captured and their default mapping to SQL Server data types in the change tables.</span></span> <span data-ttu-id="6193a-107">Lorsque vous ajoutez une instance de capture pour une table Oracle source, vous pouvez remplacer certains de ces mappages.</span><span class="sxs-lookup"><span data-stu-id="6193a-107">When adding a capture instance for a source Oracle table, you can override some of these mappings.</span></span>  
  
|<span data-ttu-id="6193a-108">Type de données de base de données Oracle</span><span class="sxs-lookup"><span data-stu-id="6193a-108">Oracle Database Data Type</span></span>|<span data-ttu-id="6193a-109">Type de données de SQL Server</span><span class="sxs-lookup"><span data-stu-id="6193a-109">SQL Server Data Type</span></span>|  
|-------------------------------|--------------------------|  
|<span data-ttu-id="6193a-110">BINARY_FLOAT</span><span class="sxs-lookup"><span data-stu-id="6193a-110">BINARY_FLOAT</span></span>|<span data-ttu-id="6193a-111">real</span><span class="sxs-lookup"><span data-stu-id="6193a-111">REAL</span></span>|  
|<span data-ttu-id="6193a-112">BINARY_DOUBLE</span><span class="sxs-lookup"><span data-stu-id="6193a-112">BINARY_DOUBLE</span></span>|<span data-ttu-id="6193a-113">FLOAT</span><span class="sxs-lookup"><span data-stu-id="6193a-113">FLOAT</span></span>|  
|<span data-ttu-id="6193a-114">CHAR</span><span class="sxs-lookup"><span data-stu-id="6193a-114">CHAR</span></span>|<span data-ttu-id="6193a-115">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="6193a-115">NVARCHAR</span></span>|  
|<span data-ttu-id="6193a-116">DATE</span><span class="sxs-lookup"><span data-stu-id="6193a-116">DATE</span></span>|<span data-ttu-id="6193a-117">DATETIME</span><span class="sxs-lookup"><span data-stu-id="6193a-117">DATETIME</span></span>|  
|<span data-ttu-id="6193a-118">FLOAT</span><span class="sxs-lookup"><span data-stu-id="6193a-118">FLOAT</span></span>|<span data-ttu-id="6193a-119">FLOAT</span><span class="sxs-lookup"><span data-stu-id="6193a-119">FLOAT</span></span>|  
|<span data-ttu-id="6193a-120">INT</span><span class="sxs-lookup"><span data-stu-id="6193a-120">INT</span></span>|<span data-ttu-id="6193a-121">NUMERIC (38)</span><span class="sxs-lookup"><span data-stu-id="6193a-121">NUMERIC (38)</span></span>|  
|<span data-ttu-id="6193a-122">INTERVAL</span><span class="sxs-lookup"><span data-stu-id="6193a-122">INTERVAL</span></span>|<span data-ttu-id="6193a-123">DATETIME</span><span class="sxs-lookup"><span data-stu-id="6193a-123">DATETIME</span></span>|  
|<span data-ttu-id="6193a-124">NCHAR</span><span class="sxs-lookup"><span data-stu-id="6193a-124">NCHAR</span></span>|<span data-ttu-id="6193a-125">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="6193a-125">NVARCHAR</span></span>|  
|<span data-ttu-id="6193a-126">NUMBER</span><span class="sxs-lookup"><span data-stu-id="6193a-126">NUMBER</span></span>|<span data-ttu-id="6193a-127">FLOAT</span><span class="sxs-lookup"><span data-stu-id="6193a-127">FLOAT</span></span>|  
|<span data-ttu-id="6193a-128">NAVARCHAR2</span><span class="sxs-lookup"><span data-stu-id="6193a-128">NAVARCHAR2</span></span>|<span data-ttu-id="6193a-129">NVARCHAR</span><span class="sxs-lookup"><span data-stu-id="6193a-129">NVARCHAR</span></span>|  
|<span data-ttu-id="6193a-130">RAW</span><span class="sxs-lookup"><span data-stu-id="6193a-130">RAW</span></span>|<span data-ttu-id="6193a-131">VARBINARY</span><span class="sxs-lookup"><span data-stu-id="6193a-131">VARBINARY</span></span>|  
|<span data-ttu-id="6193a-132">real</span><span class="sxs-lookup"><span data-stu-id="6193a-132">REAL</span></span>|<span data-ttu-id="6193a-133">FLOAT</span><span class="sxs-lookup"><span data-stu-id="6193a-133">FLOAT</span></span>|  
|<span data-ttu-id="6193a-134">timestamp</span><span class="sxs-lookup"><span data-stu-id="6193a-134">TIMESTAMP</span></span>|<span data-ttu-id="6193a-135">DATETIME2</span><span class="sxs-lookup"><span data-stu-id="6193a-135">DATETIME2</span></span>|  
|<span data-ttu-id="6193a-136">TIMESTAMP WITH TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="6193a-136">TIMESTAMP WITH TIME ZONE</span></span>|<span data-ttu-id="6193a-137">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="6193a-137">VARCHAR (37)</span></span>|  
|<span data-ttu-id="6193a-138">TIMESTAMP WITH LOCAL TIME ZONE</span><span class="sxs-lookup"><span data-stu-id="6193a-138">TIMESTAMP WITH LOCAL TIME ZONE</span></span>|<span data-ttu-id="6193a-139">VARCHAR (37)</span><span class="sxs-lookup"><span data-stu-id="6193a-139">VARCHAR (37)</span></span>|  
|<span data-ttu-id="6193a-140">VARCHAR2</span><span class="sxs-lookup"><span data-stu-id="6193a-140">VARCHAR2</span></span>|<span data-ttu-id="6193a-141">VARCHAR</span><span class="sxs-lookup"><span data-stu-id="6193a-141">VARCHAR</span></span>|  
|<span data-ttu-id="6193a-142">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="6193a-142">XMLTYPE</span></span>|<span data-ttu-id="6193a-143">NVARCHAR (MAX)</span><span class="sxs-lookup"><span data-stu-id="6193a-143">NVARCHAR (MAX)</span></span>|  
  
## <a name="non-supported-data-types"></a><span data-ttu-id="6193a-144">Types de données non pris en charge</span><span class="sxs-lookup"><span data-stu-id="6193a-144">Non-Supported Data Types</span></span>  
 <span data-ttu-id="6193a-145">Les tables Oracle sources avec des colonnes de types de données Oracle suivants ne peuvent pas être capturées.</span><span class="sxs-lookup"><span data-stu-id="6193a-145">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span> <span data-ttu-id="6193a-146">Les colonnes capturées avec ces types de données s'affichent en tant que colonnes NULL ; toutefois, une modification de leur valeur est indiquée dans le masque de modification des tables capturées.</span><span class="sxs-lookup"><span data-stu-id="6193a-146">Captured columns with these data types will show as null; however, a change in their value is indicated in the change mask of the captured tables.</span></span>  
  
-   <span data-ttu-id="6193a-147">LONG</span><span class="sxs-lookup"><span data-stu-id="6193a-147">LONG</span></span>  
  
-   <span data-ttu-id="6193a-148">XMLTYPE</span><span class="sxs-lookup"><span data-stu-id="6193a-148">XMLTYPE</span></span>  
  
-   <span data-ttu-id="6193a-149">BLOB</span><span class="sxs-lookup"><span data-stu-id="6193a-149">BLOB</span></span>  
  
-   <span data-ttu-id="6193a-150">CLOB</span><span class="sxs-lookup"><span data-stu-id="6193a-150">CLOB</span></span>  
  
 <span data-ttu-id="6193a-151">Les tables Oracle sources avec des colonnes de types de données Oracle suivants ne peuvent pas être capturées.</span><span class="sxs-lookup"><span data-stu-id="6193a-151">Source Oracle tables with columns of the following Oracle data types cannot be captured.</span></span>  
  
-   <span data-ttu-id="6193a-152">BFILE</span><span class="sxs-lookup"><span data-stu-id="6193a-152">BFILE</span></span>  
  
-   <span data-ttu-id="6193a-153">ROWID</span><span class="sxs-lookup"><span data-stu-id="6193a-153">ROWID</span></span>  
  
-   <span data-ttu-id="6193a-154">REF</span><span class="sxs-lookup"><span data-stu-id="6193a-154">REF</span></span>  
  
-   <span data-ttu-id="6193a-155">UROWID</span><span class="sxs-lookup"><span data-stu-id="6193a-155">UROWID</span></span>  
  
-   <span data-ttu-id="6193a-156">Table imbriquée</span><span class="sxs-lookup"><span data-stu-id="6193a-156">Nested Table</span></span>  
  
 <span data-ttu-id="6193a-157">Si les types de données suivants sont présents dans une table, ils empêchent le LogMinder d'obtenir les données de colonne de la table :</span><span class="sxs-lookup"><span data-stu-id="6193a-157">If the following data types are present in a table they will prevent the LogMinder from getting any data for any column of the table:</span></span>  
  
-   <span data-ttu-id="6193a-158">Types de données définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="6193a-158">User-defined data types</span></span>  
  
-   <span data-ttu-id="6193a-159">VARRAY</span><span class="sxs-lookup"><span data-stu-id="6193a-159">VARRAY</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6193a-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6193a-160">See Also</span></span>  
 <span data-ttu-id="6193a-161">[Concepteur de capture de données modifiées pour Oracle par Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span><span class="sxs-lookup"><span data-stu-id="6193a-161">[Change Data Capture Designer for Oracle by Attunity](change-data-capture-designer-for-oracle-by-attunity.md) </span></span>  
 [<span data-ttu-id="6193a-162">Instance CDC Oracle</span><span class="sxs-lookup"><span data-stu-id="6193a-162">The Oracle CDC Instance</span></span>](the-oracle-cdc-instance.md)  
  
  
