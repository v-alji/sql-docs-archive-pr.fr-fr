---
title: MSSQLSERVER_2519 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2519 (Database Engine error)
ms.assetid: 8dc6ad98-5db8-4c88-8dea-6d455e63b839
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c8577b07586553f4b03714cd31451ac755faf824
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600979"
---
# <a name="mssqlserver_2519"></a><span data-ttu-id="feda3-102">MSSQLSERVER_2519</span><span class="sxs-lookup"><span data-stu-id="feda3-102">MSSQLSERVER_2519</span></span>
    
## <a name="details"></a><span data-ttu-id="feda3-103">Détails</span><span class="sxs-lookup"><span data-stu-id="feda3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="feda3-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="feda3-104">Product Name</span></span>|<span data-ttu-id="feda3-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="feda3-105">SQL Server</span></span>|  
|<span data-ttu-id="feda3-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="feda3-106">Event ID</span></span>|<span data-ttu-id="feda3-107">2519</span><span class="sxs-lookup"><span data-stu-id="feda3-107">2519</span></span>|  
|<span data-ttu-id="feda3-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="feda3-108">Event Source</span></span>|<span data-ttu-id="feda3-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="feda3-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="feda3-110">Composant</span><span class="sxs-lookup"><span data-stu-id="feda3-110">Component</span></span>|<span data-ttu-id="feda3-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="feda3-111">SQLEngine</span></span>|  
|<span data-ttu-id="feda3-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="feda3-112">Symbolic Name</span></span>|<span data-ttu-id="feda3-113">DBCC_NO_EXPRESSION_EVALUATOR</span><span class="sxs-lookup"><span data-stu-id="feda3-113">DBCC_NO_EXPRESSION_EVALUATOR</span></span>|  
|<span data-ttu-id="feda3-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="feda3-114">Message Text</span></span>|<span data-ttu-id="feda3-115">Impossible de vérifier les colonnes calculées et les types définis par l'utilisateur pour l'ID d'objet O_ID (objet « O_NAME ») car l'évaluateur d'expression interne n'a pas pu être initialisé.</span><span class="sxs-lookup"><span data-stu-id="feda3-115">Computed columns and user-defined types cannot be checked for object ID O_ID (object "O_NAME") because the internal expression evaluator could not be initialized.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="feda3-116">Explication</span><span class="sxs-lookup"><span data-stu-id="feda3-116">Explanation</span></span>  
 <span data-ttu-id="feda3-117">Ce message d'information indique que le processeur de requêtes n'a pas pu fournir à DBCC un objet interne pour permettre l'évaluation de colonnes calculées et de types clr (common language runtime) définis par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="feda3-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for the evaluation of computed columns and common language runtime (CLR) user-defined types.</span></span> <span data-ttu-id="feda3-118">Cela signifie que l'exactitude des colonnes calculées et des types clr définis par l'utilisateur ne sera pas vérifiée et que ceux-ci ne seront pas utilisés lorsque DBCC vérifiera la cohérence entre les index et les tables de base.</span><span class="sxs-lookup"><span data-stu-id="feda3-118">This means that computed columns and CLR user-defined types will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="feda3-119">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="feda3-119">User Action</span></span>  
 <span data-ttu-id="feda3-120">None</span><span class="sxs-lookup"><span data-stu-id="feda3-120">None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="feda3-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="feda3-121">See Also</span></span>  
 [<span data-ttu-id="feda3-122">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="feda3-122">MSSQLSERVER_2518</span></span>](mssqlserver-2518-database-engine-error.md)  
  
  
