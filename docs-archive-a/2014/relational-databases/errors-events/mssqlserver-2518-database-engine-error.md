---
title: MSSQLSERVER_2518 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 2518 (Database Engine error)
ms.assetid: 54a13abc-4c33-43f0-b55d-e2e74a1381c8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 5f5517458c1014d7830c4813b95e1120bef452e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603537"
---
# <a name="mssqlserver_2518"></a><span data-ttu-id="f40ef-102">MSSQLSERVER_2518</span><span class="sxs-lookup"><span data-stu-id="f40ef-102">MSSQLSERVER_2518</span></span>
    
## <a name="details"></a><span data-ttu-id="f40ef-103">Détails</span><span class="sxs-lookup"><span data-stu-id="f40ef-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f40ef-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="f40ef-104">Product Name</span></span>|<span data-ttu-id="f40ef-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f40ef-105">SQL Server</span></span>|  
|<span data-ttu-id="f40ef-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="f40ef-106">Event ID</span></span>|<span data-ttu-id="f40ef-107">2518</span><span class="sxs-lookup"><span data-stu-id="f40ef-107">2518</span></span>|  
|<span data-ttu-id="f40ef-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="f40ef-108">Event Source</span></span>|<span data-ttu-id="f40ef-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f40ef-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f40ef-110">Composant</span><span class="sxs-lookup"><span data-stu-id="f40ef-110">Component</span></span>|<span data-ttu-id="f40ef-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f40ef-111">SQLEngine</span></span>|  
|<span data-ttu-id="f40ef-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="f40ef-112">Symbolic Name</span></span>|<span data-ttu-id="f40ef-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span><span class="sxs-lookup"><span data-stu-id="f40ef-113">DBCC_NO_EXPRESSION_EVAL_CLR_DISABLED</span></span>|  
|<span data-ttu-id="f40ef-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="f40ef-114">Message Text</span></span>|<span data-ttu-id="f40ef-115">ID d’objet O_ID (objet « O_NAME ») : impossible de vérifier les colonnes calculées et les types définis par l’utilisateur pour cet objet, parce que le CLR (Common Language Runtime) est désactivé.</span><span class="sxs-lookup"><span data-stu-id="f40ef-115">Object ID O_ID (object "O_NAME"): Computed columns and user-defined types cannot be checked for this object because the common language runtime (CLR) is disabled.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f40ef-116">Explication</span><span class="sxs-lookup"><span data-stu-id="f40ef-116">Explanation</span></span>  
 <span data-ttu-id="f40ef-117">Ce message présenté à titre d'information indique que le processeur de requêtes n'a pas pu fournir à DBCC un objet interne autorisant l'évaluation des colonnes calculées et des types définis par l'utilisateur CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="f40ef-117">This informational message indicates that the query processor could not provide DBCC with an internal object to allow for computed columns and common language runtime (CLR) user-defined types to be evaluated.</span></span> <span data-ttu-id="f40ef-118">Ce problème est survenu parce que l'une des colonnes impliquait le CLR ; or ce dernier n'est pas activé.</span><span class="sxs-lookup"><span data-stu-id="f40ef-118">This problem occurred because one of the columns involved the CLR, but the CLR is not enabled.</span></span> <span data-ttu-id="f40ef-119">L'objet interne couvre toutes les colonnes.</span><span class="sxs-lookup"><span data-stu-id="f40ef-119">The internal object covers all columns.</span></span> <span data-ttu-id="f40ef-120">Par conséquent, l'impossibilité d'évaluer une seule colonne empêche la création de l'objet interne.</span><span class="sxs-lookup"><span data-stu-id="f40ef-120">Therefore, the inability to evaluate a single column prevents creating the internal object.</span></span> <span data-ttu-id="f40ef-121">Cela signifie qu'il sera impossible de vérifier si les colonnes calculées sont correctes ou de les utiliser lorsque DBCC vérifiera la cohérence entre les index et les tables de base.</span><span class="sxs-lookup"><span data-stu-id="f40ef-121">This means that computed columns will not be checked for correctness or be used when DBCC checks the consistency between indexes and base tables.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f40ef-122">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="f40ef-122">User Action</span></span>  
 <span data-ttu-id="f40ef-123">Activez le CLR et exécutez de nouveau l'instruction DBCC.</span><span class="sxs-lookup"><span data-stu-id="f40ef-123">Enable CLR and rerun the DBCC statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f40ef-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f40ef-124">See Also</span></span>  
 [<span data-ttu-id="f40ef-125">Activation de l’intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="f40ef-125">Enabling CLR Integration</span></span>](../clr-integration/clr-integration-enabling.md)  
  
  
