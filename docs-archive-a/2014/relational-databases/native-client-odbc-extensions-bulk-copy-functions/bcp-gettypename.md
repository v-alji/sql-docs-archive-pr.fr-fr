---
title: bcp_gettypename | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_gettypename
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_gettypename function
ms.assetid: 65f036d1-f60e-4b8a-97b3-76fccf0dfed4
author: rothja
ms.author: jroth
ms.openlocfilehash: b2d92498b9d863fa2cb700ec4d88868c0984c4d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603509"
---
# <a name="bcp_gettypename"></a><span data-ttu-id="33175-102">bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="33175-102">bcp_gettypename</span></span>
  <span data-ttu-id="33175-103">Retourne le nom de type de SQL pour un jeton de type BCP spécifié.</span><span class="sxs-lookup"><span data-stu-id="33175-103">Returns the SQL type name for a specified BCP type token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33175-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="33175-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_gettypename (  
INT   
token  
,  
DBBOOL   
fIsMaxType  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="33175-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="33175-105">Arguments</span></span>  
 <span data-ttu-id="33175-106">*token*</span><span class="sxs-lookup"><span data-stu-id="33175-106">*token*</span></span>  
 <span data-ttu-id="33175-107">Valeur indiquant un jeton de type BCP.</span><span class="sxs-lookup"><span data-stu-id="33175-107">A value indicating a BCP type token.</span></span>  
  
 <span data-ttu-id="33175-108">*case*</span><span class="sxs-lookup"><span data-stu-id="33175-108">*field*</span></span>  
 <span data-ttu-id="33175-109">Indique si le jeton demandé possède le type max.</span><span class="sxs-lookup"><span data-stu-id="33175-109">Indicates if token requested is a max type.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="33175-110">Retours</span><span class="sxs-lookup"><span data-stu-id="33175-110">Returns</span></span>  
 <span data-ttu-id="33175-111">Chaîne contenant le nom de type SQL qui correspond au type BCP.</span><span class="sxs-lookup"><span data-stu-id="33175-111">A string containing the SQL type name corresponding to the BCP type.</span></span> <span data-ttu-id="33175-112">Si un type BCP non valide est spécifié, une chaîne vide est retournée.</span><span class="sxs-lookup"><span data-stu-id="33175-112">If an invalid BCP type is specified, an empty string is returned..</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33175-113">Notes</span><span class="sxs-lookup"><span data-stu-id="33175-113">Remarks</span></span>  
 <span data-ttu-id="33175-114">Les jetons de type de BCP sont définis dans le fichier d'en-tête sqlncli.h et la bibliothèque sqlncli11.lib.</span><span class="sxs-lookup"><span data-stu-id="33175-114">The BCP type tokens are defined in the sqlncli.h header file and the sqlncli11.lib library.</span></span>  
  
 <span data-ttu-id="33175-115">Le tableau suivant spécifie les types BCP possibles, s'ils sont ou pas de type max et la sortie attendue.</span><span class="sxs-lookup"><span data-stu-id="33175-115">The table below specifies the possible BCP types, whether or not they are max types, and the expected output.</span></span>  
  
|<span data-ttu-id="33175-116">Nom du type BCP</span><span class="sxs-lookup"><span data-stu-id="33175-116">BCP type name</span></span>|<span data-ttu-id="33175-117">MaxType</span><span class="sxs-lookup"><span data-stu-id="33175-117">MaxType</span></span>|<span data-ttu-id="33175-118">Output</span><span class="sxs-lookup"><span data-stu-id="33175-118">Output</span></span>|  
|-------------------|-------------|------------|  
|`SQLDECIMAL`|<span data-ttu-id="33175-119">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-119">Either</span></span>|<span data-ttu-id="33175-120">**decimal**</span><span class="sxs-lookup"><span data-stu-id="33175-120">**decimal**</span></span>|  
|`SQLNUMERIC`|<span data-ttu-id="33175-121">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-121">Either</span></span>|<span data-ttu-id="33175-122">**numeric**</span><span class="sxs-lookup"><span data-stu-id="33175-122">**numeric**</span></span>|  
|`SQLINT1`|<span data-ttu-id="33175-123">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-123">Either</span></span>|<span data-ttu-id="33175-124">**tinyint**</span><span class="sxs-lookup"><span data-stu-id="33175-124">**tinyint**</span></span>|  
|`SQLINT2`|<span data-ttu-id="33175-125">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-125">Either</span></span>|<span data-ttu-id="33175-126">**smallint**</span><span class="sxs-lookup"><span data-stu-id="33175-126">**smallint**</span></span>|  
|`SQLINT4`|<span data-ttu-id="33175-127">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-127">Either</span></span>|<span data-ttu-id="33175-128">**int**</span><span class="sxs-lookup"><span data-stu-id="33175-128">**int**</span></span>|  
|`SQLMONEY`|<span data-ttu-id="33175-129">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-129">Either</span></span>|<span data-ttu-id="33175-130">**money**</span><span class="sxs-lookup"><span data-stu-id="33175-130">**money**</span></span>|  
|`SQLFLT8`|<span data-ttu-id="33175-131">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-131">Either</span></span>|<span data-ttu-id="33175-132">**float**</span><span class="sxs-lookup"><span data-stu-id="33175-132">**float**</span></span>|  
|`SQLDATETIME`|<span data-ttu-id="33175-133">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-133">Either</span></span>|<span data-ttu-id="33175-134">**datetime**</span><span class="sxs-lookup"><span data-stu-id="33175-134">**datetime**</span></span>|  
|`SQLBITN`|<span data-ttu-id="33175-135">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-135">Either</span></span>|<span data-ttu-id="33175-136">**bit-null**</span><span class="sxs-lookup"><span data-stu-id="33175-136">**bit-null**</span></span>|  
|`SQLBIT`|<span data-ttu-id="33175-137">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-137">Either</span></span>|<span data-ttu-id="33175-138">**bit**</span><span class="sxs-lookup"><span data-stu-id="33175-138">**bit**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="33175-139">Non</span><span class="sxs-lookup"><span data-stu-id="33175-139">No</span></span>|<span data-ttu-id="33175-140">**char**</span><span class="sxs-lookup"><span data-stu-id="33175-140">**char**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="33175-141">Non</span><span class="sxs-lookup"><span data-stu-id="33175-141">No</span></span>|<span data-ttu-id="33175-142">**char**</span><span class="sxs-lookup"><span data-stu-id="33175-142">**char**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="33175-143">Non</span><span class="sxs-lookup"><span data-stu-id="33175-143">No</span></span>|<span data-ttu-id="33175-144">**varchar**</span><span class="sxs-lookup"><span data-stu-id="33175-144">**varchar**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="33175-145">Non</span><span class="sxs-lookup"><span data-stu-id="33175-145">No</span></span>|<span data-ttu-id="33175-146">**varchar**</span><span class="sxs-lookup"><span data-stu-id="33175-146">**varchar**</span></span>|  
|`SQLTEXT`|<span data-ttu-id="33175-147">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-147">Either</span></span>|<span data-ttu-id="33175-148">**text**</span><span class="sxs-lookup"><span data-stu-id="33175-148">**text**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="33175-149">Non</span><span class="sxs-lookup"><span data-stu-id="33175-149">No</span></span>|<span data-ttu-id="33175-150">**binary**</span><span class="sxs-lookup"><span data-stu-id="33175-150">**binary**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="33175-151">Non</span><span class="sxs-lookup"><span data-stu-id="33175-151">No</span></span>|<span data-ttu-id="33175-152">**Binaire**</span><span class="sxs-lookup"><span data-stu-id="33175-152">**Binary**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="33175-153">Non</span><span class="sxs-lookup"><span data-stu-id="33175-153">No</span></span>|<span data-ttu-id="33175-154">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="33175-154">**Varbinary**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="33175-155">Non</span><span class="sxs-lookup"><span data-stu-id="33175-155">No</span></span>|<span data-ttu-id="33175-156">**Varbinary**</span><span class="sxs-lookup"><span data-stu-id="33175-156">**Varbinary**</span></span>|  
|`SQLIMAGE`|<span data-ttu-id="33175-157">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-157">Either</span></span>|<span data-ttu-id="33175-158">**Image**</span><span class="sxs-lookup"><span data-stu-id="33175-158">**Image**</span></span>|  
|`SQLINTN`|<span data-ttu-id="33175-159">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-159">Either</span></span>|<span data-ttu-id="33175-160">**int-null**</span><span class="sxs-lookup"><span data-stu-id="33175-160">**int-null**</span></span>|  
|`SQLDATETIMN`|<span data-ttu-id="33175-161">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-161">Either</span></span>|<span data-ttu-id="33175-162">**datetime-null**</span><span class="sxs-lookup"><span data-stu-id="33175-162">**datetime-null**</span></span>|  
|`SQLMONEYN`|<span data-ttu-id="33175-163">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-163">Either</span></span>|<span data-ttu-id="33175-164">**money-null**</span><span class="sxs-lookup"><span data-stu-id="33175-164">**money-null**</span></span>|  
|`SQLFLTN`|<span data-ttu-id="33175-165">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-165">Either</span></span>|<span data-ttu-id="33175-166">**float-null**</span><span class="sxs-lookup"><span data-stu-id="33175-166">**float-null**</span></span>|  
|`SQLAOPSUM`|<span data-ttu-id="33175-167">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-167">Either</span></span>|<span data-ttu-id="33175-168">**SUM**</span><span class="sxs-lookup"><span data-stu-id="33175-168">**Sum**</span></span>|  
|`SQLAOPAVG`|<span data-ttu-id="33175-169">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-169">Either</span></span>|<span data-ttu-id="33175-170">**Avg**</span><span class="sxs-lookup"><span data-stu-id="33175-170">**Avg**</span></span>|  
|`SQLAOPCNT`|<span data-ttu-id="33175-171">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-171">Either</span></span>|<span data-ttu-id="33175-172">**Count**</span><span class="sxs-lookup"><span data-stu-id="33175-172">**Count**</span></span>|  
|`SQLAOPMIN`|<span data-ttu-id="33175-173">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-173">Either</span></span>|<span data-ttu-id="33175-174">**Min**</span><span class="sxs-lookup"><span data-stu-id="33175-174">**Min**</span></span>|  
|`SQLAOPMAX`|<span data-ttu-id="33175-175">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-175">Either</span></span>|<span data-ttu-id="33175-176">**Max**</span><span class="sxs-lookup"><span data-stu-id="33175-176">**Max**</span></span>|  
|`SQLDATETIM4`|<span data-ttu-id="33175-177">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-177">Either</span></span>|<span data-ttu-id="33175-178">**smalldatetime**</span><span class="sxs-lookup"><span data-stu-id="33175-178">**smalldatetime**</span></span>|  
|`SQLMONEY4`|<span data-ttu-id="33175-179">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-179">Either</span></span>|<span data-ttu-id="33175-180">**Smallmoney**</span><span class="sxs-lookup"><span data-stu-id="33175-180">**Smallmoney**</span></span>|  
|`SQLFLT4`|<span data-ttu-id="33175-181">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-181">Either</span></span>|<span data-ttu-id="33175-182">**Non**</span><span class="sxs-lookup"><span data-stu-id="33175-182">**Real**</span></span>|  
|`SQLUNIQUEID`|<span data-ttu-id="33175-183">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-183">Either</span></span>|<span data-ttu-id="33175-184">**uniqueidentifier**</span><span class="sxs-lookup"><span data-stu-id="33175-184">**uniqueidentifier**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="33175-185">Non</span><span class="sxs-lookup"><span data-stu-id="33175-185">No</span></span>|<span data-ttu-id="33175-186">**NCHAR**</span><span class="sxs-lookup"><span data-stu-id="33175-186">**Nchar**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="33175-187">Non</span><span class="sxs-lookup"><span data-stu-id="33175-187">No</span></span>|<span data-ttu-id="33175-188">**Nvarchar**</span><span class="sxs-lookup"><span data-stu-id="33175-188">**Nvarchar**</span></span>|  
|`SQLNTEXT`|<span data-ttu-id="33175-189">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-189">Either</span></span>|<span data-ttu-id="33175-190">**Text**</span><span class="sxs-lookup"><span data-stu-id="33175-190">**Ntext**</span></span>|  
|`SQLVARIANT`|<span data-ttu-id="33175-191">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-191">Either</span></span>|<span data-ttu-id="33175-192">**sql_variant**</span><span class="sxs-lookup"><span data-stu-id="33175-192">**sql_variant**</span></span>|  
|`SQLINT8`|<span data-ttu-id="33175-193">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-193">Either</span></span>|<span data-ttu-id="33175-194">**Comportant**</span><span class="sxs-lookup"><span data-stu-id="33175-194">**Bigint**</span></span>|  
|`SQLCHARACTER`|<span data-ttu-id="33175-195">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-195">Yes</span></span>|<span data-ttu-id="33175-196">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-196">**varchar(max)**</span></span>|  
|`SQLBIGCHAR`|<span data-ttu-id="33175-197">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-197">Yes</span></span>|<span data-ttu-id="33175-198">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-198">**varchar(max)**</span></span>|  
|`SQLBIGVARCHAR`|<span data-ttu-id="33175-199">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-199">Yes</span></span>|<span data-ttu-id="33175-200">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-200">**varchar(max)**</span></span>|  
|`SQLVARCHAR`|<span data-ttu-id="33175-201">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-201">Yes</span></span>|<span data-ttu-id="33175-202">**varchar(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-202">**varchar(max)**</span></span>|  
|`SQLBINARY`|<span data-ttu-id="33175-203">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-203">Yes</span></span>|<span data-ttu-id="33175-204">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-204">**varbinary(max)**</span></span>|  
|`SQLBIGBINARY`|<span data-ttu-id="33175-205">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-205">Yes</span></span>|<span data-ttu-id="33175-206">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-206">**varbinary(max)**</span></span>|  
|`SQLBIGVARBINARY`|<span data-ttu-id="33175-207">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-207">Yes</span></span>|<span data-ttu-id="33175-208">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-208">**varbinary(max)**</span></span>|  
|`SQLVARBINARY`|<span data-ttu-id="33175-209">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-209">Yes</span></span>|<span data-ttu-id="33175-210">**varbinary(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-210">**varbinary(max)**</span></span>|  
|`SQLNCHAR`|<span data-ttu-id="33175-211">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-211">Yes</span></span>|<span data-ttu-id="33175-212">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-212">**nvarchar(max)**</span></span>|  
|`SQLNVARCHAR`|<span data-ttu-id="33175-213">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-213">Yes</span></span>|<span data-ttu-id="33175-214">**nvarchar(max)**</span><span class="sxs-lookup"><span data-stu-id="33175-214">**nvarchar(max)**</span></span>|  
|`SQLXML`|<span data-ttu-id="33175-215">Oui</span><span class="sxs-lookup"><span data-stu-id="33175-215">Yes</span></span>|<span data-ttu-id="33175-216">**Xml**</span><span class="sxs-lookup"><span data-stu-id="33175-216">**Xml**</span></span>|  
|`SQLUDT`|<span data-ttu-id="33175-217">Vous pouvez soit utiliser</span><span class="sxs-lookup"><span data-stu-id="33175-217">Either</span></span>|<span data-ttu-id="33175-218">**Assorti**</span><span class="sxs-lookup"><span data-stu-id="33175-218">**Udt**</span></span>|  
  
## <a name="bcp_gettypename-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="33175-219">Prise en charge des fonctionnalités de date et heure améliorées par bcp_gettypename</span><span class="sxs-lookup"><span data-stu-id="33175-219">bcp_gettypename Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="33175-220">Les valeurs de paramètre de jeton pour les types date/time sont décrites dans la colonne « type dans sqlncli. h » de la table dans les [modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="33175-220">The token parameter values for date/time types are described in the "Type in sqlncli.h" column of the table in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span> <span data-ttu-id="33175-221">La valeur retournée est dans la ligne correspondante de la colonne « Type de stockage de fichier ».</span><span class="sxs-lookup"><span data-stu-id="33175-221">The returned value is in the corresponding row of the "File storage type" column.</span></span>  
  
 <span data-ttu-id="33175-222">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="33175-222">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33175-223">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="33175-223">See Also</span></span>  
 [<span data-ttu-id="33175-224">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="33175-224">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
