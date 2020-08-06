---
title: Accès au contexte de requête dans les procédures stockées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- execution context [Analysis Services]
- stored procedures [Analysis Services], query context
- Context object
- query context [Analysis Services]
ms.assetid: bdc7dad8-2f22-4265-aba4-a3a451527840
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9da8ddb223ed03c0208fe524ea5cd7195a039c97
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694796"
---
# <a name="accessing-query-context-in-stored-procedures"></a><span data-ttu-id="a6ce2-102">Accès au contexte de requête dans les procédures stockées</span><span class="sxs-lookup"><span data-stu-id="a6ce2-102">Accessing Query Context in Stored Procedures</span></span>
  <span data-ttu-id="a6ce2-103">Le contexte d'exécution d'une procédure stockée est disponible à l'intérieur du code de cette procédure sous la forme de l'objet `Context` du modèle d'objet serveur ADOMD.NET.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-103">The execution context of a stored procedure is available within the code of the stored procedure as the `Context` object of the ADOMD.NET server object model.</span></span> <span data-ttu-id="a6ce2-104">Il s'agit d'un contexte en lecture seule qui ne peut pas être modifié par la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-104">This is a read-only context and cannot be modified by the stored procedure.</span></span> <span data-ttu-id="a6ce2-105">Les propriétés suivantes sont disponibles pour cet objet.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-105">The following properties are available on this object.</span></span>  
  
|<span data-ttu-id="a6ce2-106">Propriété</span><span class="sxs-lookup"><span data-stu-id="a6ce2-106">Property</span></span>|<span data-ttu-id="a6ce2-107">Type</span><span class="sxs-lookup"><span data-stu-id="a6ce2-107">Type</span></span>|<span data-ttu-id="a6ce2-108">Description</span><span class="sxs-lookup"><span data-stu-id="a6ce2-108">Description</span></span>|  
|--------------|----------|-----------------|  
|<span data-ttu-id="a6ce2-109">**CurrentCube**</span><span class="sxs-lookup"><span data-stu-id="a6ce2-109">**CurrentCube**</span></span>|<span data-ttu-id="a6ce2-110">Cube</span><span class="sxs-lookup"><span data-stu-id="a6ce2-110">Cube</span></span>|<span data-ttu-id="a6ce2-111">Cube du contexte de requête actuel.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-111">The cube for the current query context.</span></span>|  
|<span data-ttu-id="a6ce2-112">**CurrentDatabaseName**</span><span class="sxs-lookup"><span data-stu-id="a6ce2-112">**CurrentDatabaseName**</span></span>|<span data-ttu-id="a6ce2-113">String</span><span class="sxs-lookup"><span data-stu-id="a6ce2-113">String</span></span>|<span data-ttu-id="a6ce2-114">Identificateur de la base de données active.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-114">The identifier of the current database.</span></span>|  
|<span data-ttu-id="a6ce2-115">**CurrentConnection**</span><span class="sxs-lookup"><span data-stu-id="a6ce2-115">**CurrentConnection**</span></span>|<span data-ttu-id="a6ce2-116">Connexion</span><span class="sxs-lookup"><span data-stu-id="a6ce2-116">Connection</span></span>|<span data-ttu-id="a6ce2-117">Référence à l'objet de connexion dans le contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-117">A reference to the connection object in the current context.</span></span>|  
|<span data-ttu-id="a6ce2-118">**Réussite**</span><span class="sxs-lookup"><span data-stu-id="a6ce2-118">**Pass**</span></span>|<span data-ttu-id="a6ce2-119">Integer</span><span class="sxs-lookup"><span data-stu-id="a6ce2-119">Integer</span></span>|<span data-ttu-id="a6ce2-120">Numéro de test du contexte actuel.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-120">The pass number for the current context.</span></span>|  
  
 <span data-ttu-id="a6ce2-121">L'objet `Context` existe lorsque le modèle objet MDX (Multidimensional Expressions) est utilisé dans une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-121">The `Context` object exists when the Multidimensional Expressions (MDX) object model is used in a stored procedure.</span></span> <span data-ttu-id="a6ce2-122">Il n'est pas disponible lorsque le modèle objet MDX est utilisé sur un client.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-122">It is not available when the MDX object model is used on a client.</span></span> <span data-ttu-id="a6ce2-123">L'objet `Context` n'est ni explicitement transmis à la procédure stockée, ni explicitement renvoyé par celle-ci.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-123">The `Context` object is not explicitly passed to or returned by the stored procedure.</span></span> <span data-ttu-id="a6ce2-124">Il est disponible pendant l'exécution de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="a6ce2-124">It is available during the execution of the stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ce2-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6ce2-125">See Also</span></span>  
 <span data-ttu-id="a6ce2-126">[Gestion des assemblys de modèles multidimensionnels](../multidimensional-models/multidimensional-model-assemblies-management.md) </span><span class="sxs-lookup"><span data-stu-id="a6ce2-126">[Multidimensional Model Assemblies Management](../multidimensional-models/multidimensional-model-assemblies-management.md) </span></span>  
 [<span data-ttu-id="a6ce2-127">Définition de procédures stockées</span><span class="sxs-lookup"><span data-stu-id="a6ce2-127">Defining Stored Procedures</span></span>](../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
