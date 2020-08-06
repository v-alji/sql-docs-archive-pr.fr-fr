---
title: MSSQLSERVER_33085 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33085 (Database Engine error)
ms.assetid: c27b8d1d-668a-4ba8-8b61-25a5ebbc5485
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8d774ab115c2d0ddbbd7b35c7e32db17e39fcb2e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604508"
---
# <a name="mssqlserver_33085"></a><span data-ttu-id="5454f-102">MSSQLSERVER_33085</span><span class="sxs-lookup"><span data-stu-id="5454f-102">MSSQLSERVER_33085</span></span>
    
## <a name="details"></a><span data-ttu-id="5454f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5454f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5454f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5454f-104">Product Name</span></span>|<span data-ttu-id="5454f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5454f-105">SQL Server</span></span>|  
|<span data-ttu-id="5454f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5454f-106">Event ID</span></span>|<span data-ttu-id="5454f-107">33085</span><span class="sxs-lookup"><span data-stu-id="5454f-107">33085</span></span>|  
|<span data-ttu-id="5454f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5454f-108">Event Source</span></span>|<span data-ttu-id="5454f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5454f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5454f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5454f-110">Component</span></span>|<span data-ttu-id="5454f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5454f-111">SQLEngine</span></span>|  
|<span data-ttu-id="5454f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5454f-112">Symbolic Name</span></span>|<span data-ttu-id="5454f-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5454f-113">SEC_CRYPTOPROVE_METHOD_CANNOT_FOUND</span></span>|  
|<span data-ttu-id="5454f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5454f-114">Message Text</span></span>|<span data-ttu-id="5454f-115">Une ou plusieurs méthodes restent introuvables dans la bibliothèque du fournisseur de services de chiffrement '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="5454f-115">One or more methods cannot be found in cryptographic provider library '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5454f-116">Explication</span><span class="sxs-lookup"><span data-stu-id="5454f-116">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="5454f-117">n’a pas pu utiliser le fournisseur de services de chiffrement répertorié dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="5454f-117">was unable to use the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="5454f-118">Le fournisseur de services de chiffrement n'a pas pris en charge une méthode requise.</span><span class="sxs-lookup"><span data-stu-id="5454f-118">The cryptographic provider did not support a required method.</span></span> <span data-ttu-id="5454f-119">L'état de l'erreur indique quelle méthode était introuvable.</span><span class="sxs-lookup"><span data-stu-id="5454f-119">The state of the error indicates which method was not found.</span></span>  
  
|<span data-ttu-id="5454f-120">State</span><span class="sxs-lookup"><span data-stu-id="5454f-120">State</span></span>|<span data-ttu-id="5454f-121">Description</span><span class="sxs-lookup"><span data-stu-id="5454f-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5454f-122">1</span><span class="sxs-lookup"><span data-stu-id="5454f-122">1</span></span>|<span data-ttu-id="5454f-123">SqlCryptInitializeProvider</span><span class="sxs-lookup"><span data-stu-id="5454f-123">SqlCryptInitializeProvider</span></span>|  
|<span data-ttu-id="5454f-124">2</span><span class="sxs-lookup"><span data-stu-id="5454f-124">2</span></span>|<span data-ttu-id="5454f-125">SqlCryptFreeProvider</span><span class="sxs-lookup"><span data-stu-id="5454f-125">SqlCryptFreeProvider</span></span>|  
|<span data-ttu-id="5454f-126">3</span><span class="sxs-lookup"><span data-stu-id="5454f-126">3</span></span>|<span data-ttu-id="5454f-127">SqlCryptOpenSession</span><span class="sxs-lookup"><span data-stu-id="5454f-127">SqlCryptOpenSession</span></span>|  
|<span data-ttu-id="5454f-128">4</span><span class="sxs-lookup"><span data-stu-id="5454f-128">4</span></span>|<span data-ttu-id="5454f-129">SqlCryptCloseSession</span><span class="sxs-lookup"><span data-stu-id="5454f-129">SqlCryptCloseSession</span></span>|  
|<span data-ttu-id="5454f-130">5</span><span class="sxs-lookup"><span data-stu-id="5454f-130">5</span></span>|<span data-ttu-id="5454f-131">SqlCryptGetProviderInfo</span><span class="sxs-lookup"><span data-stu-id="5454f-131">SqlCryptGetProviderInfo</span></span>|  
|<span data-ttu-id="5454f-132">6</span><span class="sxs-lookup"><span data-stu-id="5454f-132">6</span></span>|<span data-ttu-id="5454f-133">SqlCryptGetNextAlgorithmId</span><span class="sxs-lookup"><span data-stu-id="5454f-133">SqlCryptGetNextAlgorithmId</span></span>|  
|<span data-ttu-id="5454f-134">7</span><span class="sxs-lookup"><span data-stu-id="5454f-134">7</span></span>|<span data-ttu-id="5454f-135">SqlCryptGetAlgorithmInfo</span><span class="sxs-lookup"><span data-stu-id="5454f-135">SqlCryptGetAlgorithmInfo</span></span>|  
|<span data-ttu-id="5454f-136">8</span><span class="sxs-lookup"><span data-stu-id="5454f-136">8</span></span>|<span data-ttu-id="5454f-137">SqlCryptCreateKey</span><span class="sxs-lookup"><span data-stu-id="5454f-137">SqlCryptCreateKey</span></span>|  
|<span data-ttu-id="5454f-138">9</span><span class="sxs-lookup"><span data-stu-id="5454f-138">9</span></span>|<span data-ttu-id="5454f-139">SqlCryptDropKey</span><span class="sxs-lookup"><span data-stu-id="5454f-139">SqlCryptDropKey</span></span>|  
|<span data-ttu-id="5454f-140">10</span><span class="sxs-lookup"><span data-stu-id="5454f-140">10</span></span>|<span data-ttu-id="5454f-141">SqlCryptGetNextKeyId</span><span class="sxs-lookup"><span data-stu-id="5454f-141">SqlCryptGetNextKeyId</span></span>|  
|<span data-ttu-id="5454f-142">11</span><span class="sxs-lookup"><span data-stu-id="5454f-142">11</span></span>|<span data-ttu-id="5454f-143">SqlCryptGetKeyInfoByKeyId</span><span class="sxs-lookup"><span data-stu-id="5454f-143">SqlCryptGetKeyInfoByKeyId</span></span>|  
|<span data-ttu-id="5454f-144">12</span><span class="sxs-lookup"><span data-stu-id="5454f-144">12</span></span>|<span data-ttu-id="5454f-145">SqlCryptGetKeyInfoByThumb</span><span class="sxs-lookup"><span data-stu-id="5454f-145">SqlCryptGetKeyInfoByThumb</span></span>|  
|<span data-ttu-id="5454f-146">13</span><span class="sxs-lookup"><span data-stu-id="5454f-146">13</span></span>|<span data-ttu-id="5454f-147">SqlCryptGetKeyInfoByName</span><span class="sxs-lookup"><span data-stu-id="5454f-147">SqlCryptGetKeyInfoByName</span></span>|  
|<span data-ttu-id="5454f-148">14</span><span class="sxs-lookup"><span data-stu-id="5454f-148">14</span></span>|<span data-ttu-id="5454f-149">SqlCryptExportKey</span><span class="sxs-lookup"><span data-stu-id="5454f-149">SqlCryptExportKey</span></span>|  
|<span data-ttu-id="5454f-150">15</span><span class="sxs-lookup"><span data-stu-id="5454f-150">15</span></span>|<span data-ttu-id="5454f-151">SqlCryptImportKey</span><span class="sxs-lookup"><span data-stu-id="5454f-151">SqlCryptImportKey</span></span>|  
|<span data-ttu-id="5454f-152">16</span><span class="sxs-lookup"><span data-stu-id="5454f-152">16</span></span>|<span data-ttu-id="5454f-153">SqlCryptEncrypt</span><span class="sxs-lookup"><span data-stu-id="5454f-153">SqlCryptEncrypt</span></span>|  
|<span data-ttu-id="5454f-154">17</span><span class="sxs-lookup"><span data-stu-id="5454f-154">17</span></span>|<span data-ttu-id="5454f-155">SqlCryptDecrypt</span><span class="sxs-lookup"><span data-stu-id="5454f-155">SqlCryptDecrypt</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="5454f-156">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5454f-156">User Action</span></span>  
 <span data-ttu-id="5454f-157">Contactez le fournisseur de services de chiffrement pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="5454f-157">Contact the cryptographic provider for more information.</span></span>  
  
  
