---
title: bcp_getcolfmt | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_getcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_getcolfmt function
ms.assetid: f8bdada5-7b2d-4475-8c98-f93e9d77b130
author: rothja
ms.author: jroth
ms.openlocfilehash: aabc811a5aa0babe5119c4ef0ed0e649586d73cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603510"
---
# <a name="bcp_getcolfmt"></a><span data-ttu-id="076ac-102">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="076ac-102">bcp_getcolfmt</span></span>
  <span data-ttu-id="076ac-103">Utilisé pour rechercher la valeur de la propriété de format de colonne.</span><span class="sxs-lookup"><span data-stu-id="076ac-103">Used to find the column format property value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="076ac-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="076ac-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_getcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbvalue,  
INT*   
pcbLen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="076ac-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="076ac-105">Arguments</span></span>  
 <span data-ttu-id="076ac-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="076ac-106">*hdbc*</span></span>  
 <span data-ttu-id="076ac-107">Handle de connexion ODBC compatible avec la copie en bloc.</span><span class="sxs-lookup"><span data-stu-id="076ac-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="076ac-108">*case*</span><span class="sxs-lookup"><span data-stu-id="076ac-108">*field*</span></span>  
 <span data-ttu-id="076ac-109">Numéro de colonne pour lequel la propriété est extraite.</span><span class="sxs-lookup"><span data-stu-id="076ac-109">Is the column number for which the property is retrieved.</span></span>  
  
 <span data-ttu-id="076ac-110">*property*</span><span class="sxs-lookup"><span data-stu-id="076ac-110">*property*</span></span>  
 <span data-ttu-id="076ac-111">L'une des constantes de propriété.</span><span class="sxs-lookup"><span data-stu-id="076ac-111">Is one of the property constants.</span></span>  
  
 <span data-ttu-id="076ac-112">*pValue*</span><span class="sxs-lookup"><span data-stu-id="076ac-112">*pValue*</span></span>  
 <span data-ttu-id="076ac-113">Pointeur vers la mémoire tampon de laquelle la valeur de la propriété doit être extraite.</span><span class="sxs-lookup"><span data-stu-id="076ac-113">Is the pointer to the buffer from which to retrieve the property value.</span></span>  
  
 <span data-ttu-id="076ac-114">*cbValue*</span><span class="sxs-lookup"><span data-stu-id="076ac-114">*cbValue*</span></span>  
 <span data-ttu-id="076ac-115">Taille de la mémoire tampon de propriété, en octets.</span><span class="sxs-lookup"><span data-stu-id="076ac-115">Is the length of the property buffer in bytes.</span></span>  
  
 <span data-ttu-id="076ac-116">*pcbLen*</span><span class="sxs-lookup"><span data-stu-id="076ac-116">*pcbLen*</span></span>  
 <span data-ttu-id="076ac-117">Pointeur vers la longueur des données retournées dans la mémoire tampon de propriété.</span><span class="sxs-lookup"><span data-stu-id="076ac-117">Pointer to length of the data that is being returned in the property buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="076ac-118">Retours</span><span class="sxs-lookup"><span data-stu-id="076ac-118">Returns</span></span>  
 <span data-ttu-id="076ac-119">SUCCEED ou FAIL.</span><span class="sxs-lookup"><span data-stu-id="076ac-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="076ac-120">Notes</span><span class="sxs-lookup"><span data-stu-id="076ac-120">Remarks</span></span>  
 <span data-ttu-id="076ac-121">Les valeurs de la propriété de format de colonne sont répertoriées dans la rubrique [bcp_setcolfmt](bcp-setcolfmt.md) .</span><span class="sxs-lookup"><span data-stu-id="076ac-121">Column format property values are listed in the [bcp_setcolfmt](bcp-setcolfmt.md) topic.</span></span> <span data-ttu-id="076ac-122">Ces valeurs sont définies en appelant la fonction **bcp_setcolfmt** . La fonction **bcp_getcolfmt** est utilisée pour rechercher la valeur de la propriété de format de colonne.</span><span class="sxs-lookup"><span data-stu-id="076ac-122">The column format property values are set by calling the **bcp_setcolfmt** function, and the **bcp_getcolfmt** function is used to find the column format property value.</span></span>  
  
 <span data-ttu-id="076ac-123">Des changements de comportement peuvent être observés lors de la connexion à un serveur [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (ou version ultérieure), par rapport aux versions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] antérieures.</span><span class="sxs-lookup"><span data-stu-id="076ac-123">Behavior changes may be observed when connecting to a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (or later) server computer, compared to earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions.</span></span> <span data-ttu-id="076ac-124">Pour plus d’informations, consultez [Découverte des métadonnées](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="076ac-124">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="bcp_getcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="076ac-125">Prise en charge  par bcp_getcolfmt des fonctionnalités de date et heure améliorées</span><span class="sxs-lookup"><span data-stu-id="076ac-125">bcp_getcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="076ac-126">Les types utilisés avec la `BCP_FMT_TYPE` propriété pour les types date/heure sont les mêmes que ceux spécifiés dans les [modifications de copie en bloc pour les types de date et d’heure améliorés &#40;OLE DB et ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="076ac-126">The types used with the `BCP_FMT_TYPE` property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="076ac-127">Pour plus d’informations, consultez améliorations de la [date et de l’heure &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="076ac-127">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="076ac-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="076ac-128">See Also</span></span>  
 [<span data-ttu-id="076ac-129">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="076ac-129">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
