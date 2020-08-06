---
title: MSSQLSERVER_102 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 102 (Database Engine error)
ms.assetid: 264dc1a2-c8a0-4c89-b5f6-951baf950299
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 18c330b8d6a534ca11e2ad2c03f89793f8c832e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600993"
---
# <a name="mssqlserver_102"></a><span data-ttu-id="97321-102">MSSQLSERVER_102</span><span class="sxs-lookup"><span data-stu-id="97321-102">MSSQLSERVER_102</span></span>
    
## <a name="details"></a><span data-ttu-id="97321-103">Détails</span><span class="sxs-lookup"><span data-stu-id="97321-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="97321-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="97321-104">Product Name</span></span>|<span data-ttu-id="97321-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="97321-105">SQL Server</span></span>|  
|<span data-ttu-id="97321-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="97321-106">Event ID</span></span>|<span data-ttu-id="97321-107">102</span><span class="sxs-lookup"><span data-stu-id="97321-107">102</span></span>|  
|<span data-ttu-id="97321-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="97321-108">Event Source</span></span>|<span data-ttu-id="97321-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="97321-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="97321-110">Composant</span><span class="sxs-lookup"><span data-stu-id="97321-110">Component</span></span>|<span data-ttu-id="97321-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="97321-111">SQLEngine</span></span>|  
|<span data-ttu-id="97321-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="97321-112">Symbolic Name</span></span>|<span data-ttu-id="97321-113">P_SYNTAXERR2</span><span class="sxs-lookup"><span data-stu-id="97321-113">P_SYNTAXERR2</span></span>|  
|<span data-ttu-id="97321-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="97321-114">Message Text</span></span>|<span data-ttu-id="97321-115">Syntaxe incorrecte près de '%.\*ls'.</span><span class="sxs-lookup"><span data-stu-id="97321-115">Incorrect syntax near '%.\*ls'.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="97321-116">Explication</span><span class="sxs-lookup"><span data-stu-id="97321-116">Explanation</span></span>  
 <span data-ttu-id="97321-117">Indique une erreur de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="97321-117">Indicates a syntax error.</span></span> <span data-ttu-id="97321-118">Aucune information supplémentaire n'est disponible, car l'erreur empêche le [!INCLUDE[ssDE](../../includes/ssde-md.md)] de traiter l'instruction.</span><span class="sxs-lookup"><span data-stu-id="97321-118">Additional information is not available because the error prevents the [!INCLUDE[ssDE](../../includes/ssde-md.md)] from processing the statement.</span></span>  
  
 <span data-ttu-id="97321-119">Cela peut être dû à une tentative de création d'une clé symétrique à l'aide du chiffrement RC4 ou RC4_128 déconseillé, hors du mode compatibilité 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="97321-119">Can be caused by attempting to create a symmetric key using the deprecated RC4 or RC4_128 encryption, when not in 90 or 100 compatibility mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="97321-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="97321-120">User Action</span></span>  
 <span data-ttu-id="97321-121">Recherchez l'instruction [!INCLUDE[tsql](../../includes/tsql-md.md)] pour les erreurs de syntaxe.</span><span class="sxs-lookup"><span data-stu-id="97321-121">Search the [!INCLUDE[tsql](../../includes/tsql-md.md)] statement for syntax errors.</span></span>  
  
 <span data-ttu-id="97321-122">Si vous créez une clé symétrique à l'aide de RC4 ou RC4_128, sélectionnez un chiffrement plus récent, par exemple un des algorithmes AES.</span><span class="sxs-lookup"><span data-stu-id="97321-122">If creating a symmetric key using the RC4 or RC4_128, select a newer encryption such as one of the AES algorithms.</span></span> <span data-ttu-id="97321-123">(Recommandé.) Si vous devez utiliser RC4, utilisez ALTER DATABASE SET COMPATIBILITY_LEVEL pour définir la base de données au niveau de compatibilité 90 ou 100.</span><span class="sxs-lookup"><span data-stu-id="97321-123">(Recommended.) If you must use RC4, use ALTER DATABASE SET COMPATIBILITY_LEVEL to set the database to compatibility level 90 or 100.</span></span> <span data-ttu-id="97321-124">(Non recommandé.)</span><span class="sxs-lookup"><span data-stu-id="97321-124">(Not recommended.)</span></span>  
  
  
