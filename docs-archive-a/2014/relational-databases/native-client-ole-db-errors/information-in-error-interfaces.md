---
title: Informations dans les interfaces d'erreur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612798"
---
# <a name="information-in-error-interfaces"></a><span data-ttu-id="48345-102">Informations dans les interfaces d'erreur</span><span class="sxs-lookup"><span data-stu-id="48345-102">Information in Error Interfaces</span></span>
  <span data-ttu-id="48345-103">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client signale des informations d’erreur et d’État dans les interfaces d’erreur définies par l’OLE DB **IErrorInfo**, **IErrorRecords**et **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="48345-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reports some error and status information in the OLE DB-defined error interfaces **IErrorInfo**, **IErrorRecords**, and **ISQLErrorInfo**.</span></span>  
  
 <span data-ttu-id="48345-104">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge les fonctions membres **IErrorInfo** comme suit.</span><span class="sxs-lookup"><span data-stu-id="48345-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IErrorInfo** member functions as follows.</span></span>  
  
|<span data-ttu-id="48345-105">Fonction membre</span><span class="sxs-lookup"><span data-stu-id="48345-105">Member function</span></span>|<span data-ttu-id="48345-106">Description</span><span class="sxs-lookup"><span data-stu-id="48345-106">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="48345-107">**GetDescription**</span><span class="sxs-lookup"><span data-stu-id="48345-107">**GetDescription**</span></span>|<span data-ttu-id="48345-108">Chaîne du message d'erreur descriptive.</span><span class="sxs-lookup"><span data-stu-id="48345-108">Descriptive error message string.</span></span>|  
|<span data-ttu-id="48345-109">**GetGUID**</span><span class="sxs-lookup"><span data-stu-id="48345-109">**GetGUID**</span></span>|<span data-ttu-id="48345-110">GUID de l'interface ayant défini l'erreur.</span><span class="sxs-lookup"><span data-stu-id="48345-110">GUID of the interface that defined the error.</span></span>|  
|<span data-ttu-id="48345-111">**GetHelpContext**</span><span class="sxs-lookup"><span data-stu-id="48345-111">**GetHelpContext**</span></span>|<span data-ttu-id="48345-112">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="48345-112">Not supported.</span></span> <span data-ttu-id="48345-113">Retourne toujours zéro.</span><span class="sxs-lookup"><span data-stu-id="48345-113">Always returns zero.</span></span>|  
|<span data-ttu-id="48345-114">**GetHelpFile**</span><span class="sxs-lookup"><span data-stu-id="48345-114">**GetHelpFile**</span></span>|<span data-ttu-id="48345-115">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="48345-115">Not supported.</span></span> <span data-ttu-id="48345-116">Retourne toujours la valeur Null.</span><span class="sxs-lookup"><span data-stu-id="48345-116">Always returns NULL.</span></span>|  
|<span data-ttu-id="48345-117">**GetSource**</span><span class="sxs-lookup"><span data-stu-id="48345-117">**GetSource**</span></span>|<span data-ttu-id="48345-118">Chaîne « Microsoft SQL Server Native Client ».</span><span class="sxs-lookup"><span data-stu-id="48345-118">String "Microsoft SQL Server Native Client".</span></span>|  
  
 <span data-ttu-id="48345-119">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge les fonctions membres **IErrorRecords** disponibles à l’utilisateur comme suit.</span><span class="sxs-lookup"><span data-stu-id="48345-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports consumer-available **IErrorRecords** member functions as follows.</span></span>  
  
|<span data-ttu-id="48345-120">Fonction membre</span><span class="sxs-lookup"><span data-stu-id="48345-120">Member function</span></span>|<span data-ttu-id="48345-121">Description</span><span class="sxs-lookup"><span data-stu-id="48345-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="48345-122">**GetBasicErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="48345-122">**GetBasicErrorInfo**</span></span>|<span data-ttu-id="48345-123">Remplit une structure ERRORINFO avec des informations de base sur une erreur.</span><span class="sxs-lookup"><span data-stu-id="48345-123">Fills an ERRORINFO structure with basic information about an error.</span></span> <span data-ttu-id="48345-124">Une structure ERRORINFO contient des membres qui identifient la valeur de retour HRESULT pour l'erreur, ainsi que le fournisseur et l'interface auxquels l'erreur s'applique.</span><span class="sxs-lookup"><span data-stu-id="48345-124">An ERRORINFO structure contains members that identify the HRESULT return value for the error, and the provider and interface to which the error applies.</span></span>|  
|<span data-ttu-id="48345-125">**GetCustomErrorObject**</span><span class="sxs-lookup"><span data-stu-id="48345-125">**GetCustomErrorObject**</span></span>|<span data-ttu-id="48345-126">Retourne une référence sur les interfaces **ISQLErrorInfo** et [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span><span class="sxs-lookup"><span data-stu-id="48345-126">Returns a reference on interfaces **ISQLErrorInfo,** and [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span>|  
|<span data-ttu-id="48345-127">**GetErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="48345-127">**GetErrorInfo**</span></span>|<span data-ttu-id="48345-128">Retourne une référence sur une interface **IErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="48345-128">Returns a reference on an **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="48345-129">**GetErrorParameters**</span><span class="sxs-lookup"><span data-stu-id="48345-129">**GetErrorParameters**</span></span>|<span data-ttu-id="48345-130">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client ne retourne pas de paramètres au consommateur par le biais de **GetErrorParameters**.</span><span class="sxs-lookup"><span data-stu-id="48345-130">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not return parameters to the consumer through **GetErrorParameters**.</span></span>|  
|<span data-ttu-id="48345-131">**GetRecordCount**</span><span class="sxs-lookup"><span data-stu-id="48345-131">**GetRecordCount**</span></span>|<span data-ttu-id="48345-132">Nombre d'enregistrements d'erreur disponibles.</span><span class="sxs-lookup"><span data-stu-id="48345-132">Count of error records available.</span></span>|  
  
 <span data-ttu-id="48345-133">Le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client prend en charge les paramètres **ISQLErrorInfo :: GetSQLInfo** comme suit.</span><span class="sxs-lookup"><span data-stu-id="48345-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ISQLErrorInfo::GetSQLInfo** parameters as follows.</span></span>  
  
|<span data-ttu-id="48345-134">Paramètre</span><span class="sxs-lookup"><span data-stu-id="48345-134">Parameter</span></span>|<span data-ttu-id="48345-135">Description</span><span class="sxs-lookup"><span data-stu-id="48345-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48345-136">*pbstrSQLState*</span><span class="sxs-lookup"><span data-stu-id="48345-136">*pbstrSQLState*</span></span>|<span data-ttu-id="48345-137">Retourne une valeur SQLSTATE pour l'erreur.</span><span class="sxs-lookup"><span data-stu-id="48345-137">Returns a SQLSTATE value for the error.</span></span> <span data-ttu-id="48345-138">Les valeurs SQLSTATE sont définies dans les spécifications SQL-92, ODBC et ISO SQL, et API.</span><span class="sxs-lookup"><span data-stu-id="48345-138">SQLSTATE values are defined in the SQL-92, ODBC and ISO SQL, and API specifications.</span></span> <span data-ttu-id="48345-139">Ni [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ni le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur OLE DB Native Client ne définisssent des valeurs SQLSTATE spécifiques à l’implémentation.</span><span class="sxs-lookup"><span data-stu-id="48345-139">Neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defined implementation-specific SQLSTATE values.</span></span>|  
|<span data-ttu-id="48345-140">*plNativeError*</span><span class="sxs-lookup"><span data-stu-id="48345-140">*plNativeError*</span></span>|<span data-ttu-id="48345-141">Retourne le numéro d’erreur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de **master.dbo.sysmessages** s’il est disponible.</span><span class="sxs-lookup"><span data-stu-id="48345-141">Returns the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number from **master.dbo.sysmessages** when available.</span></span> <span data-ttu-id="48345-142">Des erreurs natives sont disponibles après une tentative réussie d’initialisation d’une [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] source de données de fournisseur OLE DB Native Client.</span><span class="sxs-lookup"><span data-stu-id="48345-142">Native errors are available after a successful attempt to initialize a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source.</span></span> <span data-ttu-id="48345-143">Avant la tentative, le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fournisseur de OLE DB Native Client retourne toujours zéro.</span><span class="sxs-lookup"><span data-stu-id="48345-143">Prior to the attempt, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider always returns zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48345-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48345-144">See Also</span></span>  
 [<span data-ttu-id="48345-145">Erreurs</span><span class="sxs-lookup"><span data-stu-id="48345-145">Errors</span></span>](errors.md)  
  
  
