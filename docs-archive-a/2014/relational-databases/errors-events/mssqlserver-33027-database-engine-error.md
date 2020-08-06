---
title: MSSQLSERVER_33027 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f6bb461b42b66368224fffd2c14f9b4da61abf5b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604511"
---
# <a name="mssqlserver_33027"></a><span data-ttu-id="b2166-102">MSSQLSERVER_33027</span><span class="sxs-lookup"><span data-stu-id="b2166-102">MSSQLSERVER_33027</span></span>
    
## <a name="details"></a><span data-ttu-id="b2166-103">Détails</span><span class="sxs-lookup"><span data-stu-id="b2166-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2166-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="b2166-104">Product Name</span></span>|<span data-ttu-id="b2166-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="b2166-105">SQL Server</span></span>|  
|<span data-ttu-id="b2166-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="b2166-106">Event ID</span></span>|<span data-ttu-id="b2166-107">33027</span><span class="sxs-lookup"><span data-stu-id="b2166-107">33027</span></span>|  
|<span data-ttu-id="b2166-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="b2166-108">Event Source</span></span>|<span data-ttu-id="b2166-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="b2166-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="b2166-110">Composant</span><span class="sxs-lookup"><span data-stu-id="b2166-110">Component</span></span>|<span data-ttu-id="b2166-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="b2166-111">SQLEngine</span></span>|  
|<span data-ttu-id="b2166-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="b2166-112">Symbolic Name</span></span>|<span data-ttu-id="b2166-113">SEC_CRYPTOPROV_CANTLOADDLL</span><span class="sxs-lookup"><span data-stu-id="b2166-113">SEC_CRYPTOPROV_CANTLOADDLL</span></span>|  
|<span data-ttu-id="b2166-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="b2166-114">Message Text</span></span>|<span data-ttu-id="b2166-115">Impossible de charger le fournisseur de services de chiffrement '%.\*ls' en raison d'une signature Authenticode non valide ou d'un chemin d'accès non valide.</span><span class="sxs-lookup"><span data-stu-id="b2166-115">Failed to load cryptographic provider '%.\*ls' due to an invalid Authenticode signature or invalid file path.</span></span> <span data-ttu-id="b2166-116">Recherchez d'autres défaillances dans les messages précédents.</span><span class="sxs-lookup"><span data-stu-id="b2166-116">Check previous messages for other failures.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b2166-117">Explication</span><span class="sxs-lookup"><span data-stu-id="b2166-117">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b2166-118">n’a pas pu utiliser le fournisseur de services de chiffrement répertorié dans le message d’erreur, parce que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n’a pas pu charger la DLL.</span><span class="sxs-lookup"><span data-stu-id="b2166-118">was unable to use the cryptographic provider listed in the error message, because [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] could not load the DLL.</span></span> <span data-ttu-id="b2166-119">Soit c'est le nom, soit c'est la signature Authenticode qui n'est pas valide.</span><span class="sxs-lookup"><span data-stu-id="b2166-119">Either the name is invalid or the Authenticode signature is invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b2166-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="b2166-120">User Action</span></span>  
 <span data-ttu-id="b2166-121">Vérifiez que le fichier existe et que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est autorisé à accéder à cet emplacement.</span><span class="sxs-lookup"><span data-stu-id="b2166-121">Check that the file is present and that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has permission to access that location.</span></span> <span data-ttu-id="b2166-122">Recherchez d'autres messages à ce sujet dans le journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="b2166-122">Check the error log for additional related messages.</span></span> <span data-ttu-id="b2166-123">Sinon, contactez le fournisseur de services de chiffrement pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="b2166-123">Otherwise, contact the cryptographic provider for more information.</span></span>  
  
  
