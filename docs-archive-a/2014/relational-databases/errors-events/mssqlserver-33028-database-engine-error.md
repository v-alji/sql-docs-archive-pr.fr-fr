---
title: MSSQLSERVER_33028 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33028 (Database Engine error)
ms.assetid: c5cec0e4-0bcd-4907-826f-e7d835cfcb37
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 555dcf0220793abc0e8af81b3f56867f9960c5f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604510"
---
# <a name="mssqlserver_33028"></a><span data-ttu-id="82bde-102">MSSQLSERVER_33028</span><span class="sxs-lookup"><span data-stu-id="82bde-102">MSSQLSERVER_33028</span></span>
    
## <a name="details"></a><span data-ttu-id="82bde-103">Détails</span><span class="sxs-lookup"><span data-stu-id="82bde-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82bde-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="82bde-104">Product Name</span></span>|<span data-ttu-id="82bde-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="82bde-105">SQL Server</span></span>|  
|<span data-ttu-id="82bde-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="82bde-106">Event ID</span></span>|<span data-ttu-id="82bde-107">33028</span><span class="sxs-lookup"><span data-stu-id="82bde-107">33028</span></span>|  
|<span data-ttu-id="82bde-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="82bde-108">Event Source</span></span>|<span data-ttu-id="82bde-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="82bde-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="82bde-110">Composant</span><span class="sxs-lookup"><span data-stu-id="82bde-110">Component</span></span>|<span data-ttu-id="82bde-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="82bde-111">SQLEngine</span></span>|  
|<span data-ttu-id="82bde-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="82bde-112">Symbolic Name</span></span>|<span data-ttu-id="82bde-113">SEC_CRYPTOPROV_CANTOPENSESSION</span><span class="sxs-lookup"><span data-stu-id="82bde-113">SEC_CRYPTOPROV_CANTOPENSESSION</span></span>|  
|<span data-ttu-id="82bde-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="82bde-114">Message Text</span></span>|<span data-ttu-id="82bde-115">Impossible d'ouvrir la session pour %S_MSG '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="82bde-115">Cannot open session for %S_MSG '%.\*ls'.</span></span> <span data-ttu-id="82bde-116">Code d'erreur du fournisseur : %d.</span><span class="sxs-lookup"><span data-stu-id="82bde-116">Provider error code: %d.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82bde-117">Explication</span><span class="sxs-lookup"><span data-stu-id="82bde-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="82bde-118">n’a pas pu ouvrir le fournisseur de services de chiffrement répertorié dans le message d’erreur.</span><span class="sxs-lookup"><span data-stu-id="82bde-118">was unable to open the cryptographic provider listed in the error message.</span></span> <span data-ttu-id="82bde-119">Le fournisseur de services de chiffrement a fourni le code d'erreur répertorié.</span><span class="sxs-lookup"><span data-stu-id="82bde-119">The cryptographic provider supplied the error code listed.</span></span> <span data-ttu-id="82bde-120">Il peut s'avérer nécessaire de contacter votre fournisseur de services de chiffrement pour plus d'informations sur l'erreur.</span><span class="sxs-lookup"><span data-stu-id="82bde-120">You may need to contact your cryptographic provider for more information about the error.</span></span>  
  
|<span data-ttu-id="82bde-121">Code d'erreur</span><span class="sxs-lookup"><span data-stu-id="82bde-121">Error code</span></span>|<span data-ttu-id="82bde-122">Description</span><span class="sxs-lookup"><span data-stu-id="82bde-122">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="82bde-123">0</span><span class="sxs-lookup"><span data-stu-id="82bde-123">0</span></span>|<span data-ttu-id="82bde-124">Réussite.</span><span class="sxs-lookup"><span data-stu-id="82bde-124">Success.</span></span> <span data-ttu-id="82bde-125">Aucune erreur.</span><span class="sxs-lookup"><span data-stu-id="82bde-125">No error.</span></span>|  
|<span data-ttu-id="82bde-126">1</span><span class="sxs-lookup"><span data-stu-id="82bde-126">1</span></span>|<span data-ttu-id="82bde-127">Échec.</span><span class="sxs-lookup"><span data-stu-id="82bde-127">Failure.</span></span> <span data-ttu-id="82bde-128">Une erreur non spécifiée ou inattendue s'est produite.</span><span class="sxs-lookup"><span data-stu-id="82bde-128">An unspecified or unexpected error occurred.</span></span> <span data-ttu-id="82bde-129">Aucune information supplémentaire n'est disponible.</span><span class="sxs-lookup"><span data-stu-id="82bde-129">Additional information is not available.</span></span>|  
|<span data-ttu-id="82bde-130">2</span><span class="sxs-lookup"><span data-stu-id="82bde-130">2</span></span>|<span data-ttu-id="82bde-131">Mémoire tampon insuffisante.</span><span class="sxs-lookup"><span data-stu-id="82bde-131">Insufficient Buffer.</span></span> <span data-ttu-id="82bde-132">Impossible d'allouer de l'espace au fournisseur de services de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="82bde-132">Space could not be allocated for the cryptographic provider.</span></span>|  
|<span data-ttu-id="82bde-133">3</span><span class="sxs-lookup"><span data-stu-id="82bde-133">3</span></span>|<span data-ttu-id="82bde-134">Non pris en charge.</span><span class="sxs-lookup"><span data-stu-id="82bde-134">Not Supported.</span></span> <span data-ttu-id="82bde-135">Le fournisseur de services de chiffrement n'est pas pris en charge par cette version.</span><span class="sxs-lookup"><span data-stu-id="82bde-135">The cryptographic provider is not supported by this release.</span></span> <span data-ttu-id="82bde-136">Sélectionnez-en un autre.</span><span class="sxs-lookup"><span data-stu-id="82bde-136">Select another cryptographic provider.</span></span>|  
|<span data-ttu-id="82bde-137">4</span><span class="sxs-lookup"><span data-stu-id="82bde-137">4</span></span>|<span data-ttu-id="82bde-138">Introuvable.</span><span class="sxs-lookup"><span data-stu-id="82bde-138">Not Found.</span></span> <span data-ttu-id="82bde-139">Le fournisseur de services de chiffrement spécifié est absent ou vous n'avez pas l'autorisation d'accéder aux fichiers.</span><span class="sxs-lookup"><span data-stu-id="82bde-139">The specified cryptographic provider is not present or you do not have authorization to access the files.</span></span>|  
|<span data-ttu-id="82bde-140">5</span><span class="sxs-lookup"><span data-stu-id="82bde-140">5</span></span>|<span data-ttu-id="82bde-141">Échec d'autorisation.</span><span class="sxs-lookup"><span data-stu-id="82bde-141">Authorization Failure.</span></span> <span data-ttu-id="82bde-142">Peut provenir de l'indication d'un mot de passe ou nom d'utilisateur incorrect lors de la création des informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="82bde-142">Can result from providing an incorrect password or username when creating the credential.</span></span> <span data-ttu-id="82bde-143">Peut être généré si les informations d'identification n'existent pas.</span><span class="sxs-lookup"><span data-stu-id="82bde-143">Can result if the credential does not exist.</span></span>|  
|<span data-ttu-id="82bde-144">6</span><span class="sxs-lookup"><span data-stu-id="82bde-144">6</span></span>|<span data-ttu-id="82bde-145">Argument non valide.</span><span class="sxs-lookup"><span data-stu-id="82bde-145">Invalid Argument.</span></span> <span data-ttu-id="82bde-146">Un argument non valide a été transmis au fournisseur de services de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="82bde-146">An invalid argument was passed to the cryptographic provider.</span></span>|  
  
## <a name="user-action"></a><span data-ttu-id="82bde-147">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="82bde-147">User Action</span></span>  
 <span data-ttu-id="82bde-148">Corrigez l'erreur ou contactez le fournisseur de services de chiffrement pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="82bde-148">Resolve the error, or contact the cryptographic provider for more information.</span></span>  
  
  
