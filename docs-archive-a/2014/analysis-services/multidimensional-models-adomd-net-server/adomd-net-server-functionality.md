---
title: Fonctionnalités du serveur ADOMD.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- functionality [ADOMD.NET]
- ADOMD.NET, functionality
ms.assetid: b74c6957-3f64-4e09-aa09-d06ee93f82fa
author: minewiskan
ms.author: owend
ms.openlocfilehash: f00215c6bcc0104c920be29e0837288a469b252e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696279"
---
# <a name="adomdnet-server-functionality"></a><span data-ttu-id="a4d12-102">Fonctionnalités serveur ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="a4d12-102">ADOMD.NET Server Functionality</span></span>
  <span data-ttu-id="a4d12-103">Tous les objets serveur ADOMD.NET fournissent un accès en lecture seule aux données et aux métadonnées présentes sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="a4d12-103">All ADOMD.NET server objects provide read-only access to the data and metadata on the server.</span></span> <span data-ttu-id="a4d12-104">Pour récupérer les données et les métadonnées, vous devez utiliser le modèle d'objet serveur ADOMD.NET, car le modèle d'objet serveur ne prend pas en charge les ensembles de lignes de schéma.</span><span class="sxs-lookup"><span data-stu-id="a4d12-104">To retrieve data and metadata, you use the ADOMD.NET server object model as the server object model does not support schema rowsets.</span></span>  
  
 <span data-ttu-id="a4d12-105">Avec les objets serveur ADOMD.NET, vous pouvez créer une fonction définie par l’utilisateur (UDF) ou une procédure stockée pour [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a4d12-105">With ADOMD.NET server objects, you can create a user defined function (UDF) or a stored procedure for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="a4d12-106">Ces méthodes in-process sont appelées par l'intermédiaire d'instructions de requête créées dans des langages tels que MDX (Multidimensional Expressions), DMX (Data Mining Extensions) ou SQL.</span><span class="sxs-lookup"><span data-stu-id="a4d12-106">These in-process methods are called through query statements created in languages such as Multidimensional Expressions (MDX), Data Mining Extensions (DMX), or SQL.</span></span> <span data-ttu-id="a4d12-107">Ces méthodes in-process fournissent également des fonctionnalités supplémentaires sans les temps d'attente inhérents aux communications réseau.</span><span class="sxs-lookup"><span data-stu-id="a4d12-107">These in-process methods also provide added functionality without the latencies associated with network communications.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a4d12-108">L’objet [Microsoft. AnalysisServices. AdomdServer. AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) prend en charge uniquement DMX.</span><span class="sxs-lookup"><span data-stu-id="a4d12-108">The [Microsoft.AnalysisServices.AdomdServer.AdomdCommand](/previous-versions/sql/sql-server-2014/ms143286(v=sql.120)) object only supports DMX.</span></span>  
  
## <a name="what-is-a-udf"></a><span data-ttu-id="a4d12-109">Qu'est qu'une fonction définie par l'utilisateur ?</span><span class="sxs-lookup"><span data-stu-id="a4d12-109">What is a UDF?</span></span>  
 <span data-ttu-id="a4d12-110">Une fonction *définie* par l’un est une méthode qui présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4d12-110">A *UDF* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="a4d12-111">Vous pouvez appeler une fonction définie par l'utilisteur dans le contexte d'une requête.</span><span class="sxs-lookup"><span data-stu-id="a4d12-111">You can call the UDF in the context of a query.</span></span>  
  
-   <span data-ttu-id="a4d12-112">Une fonction définie par l'utilisateur peut prendre un nombre illimité de paramètres.</span><span class="sxs-lookup"><span data-stu-id="a4d12-112">The UDF can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="a4d12-113">Une fonction définie par l'utilisateur peut retourner divers types de données.</span><span class="sxs-lookup"><span data-stu-id="a4d12-113">The UDF can return various types of data.</span></span>  
  
 <span data-ttu-id="a4d12-114">L'exemple suivant utilise la fonction définie par l'utilisateur fictive `FinalSalesNumber` :</span><span class="sxs-lookup"><span data-stu-id="a4d12-114">The following example uses the fictional UDF, `FinalSalesNumber`:</span></span>  
  
```  
SELECT SalesPerson.Name ON ROWS,  
       FinalSalesNumber() ON COLUMNS  
FROM SalesModel  
```  
  
## <a name="what-is-a-stored-procedure"></a><span data-ttu-id="a4d12-115">Qu'est-ce qu'une procédure stockée ?</span><span class="sxs-lookup"><span data-stu-id="a4d12-115">What is a Stored Procedure?</span></span>  
 <span data-ttu-id="a4d12-116">Une *procédure stockée* est une méthode qui présente les caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a4d12-116">A *stored procedure* is a method that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="a4d12-117">Vous appelez une procédure stockée seule avec l’instruction MDX [Call](/sql/mdx/mdx-data-manipulation-call) .</span><span class="sxs-lookup"><span data-stu-id="a4d12-117">You call a stored procedure on its own with the MDX [CALL](/sql/mdx/mdx-data-manipulation-call) statement.</span></span>  
  
-   <span data-ttu-id="a4d12-118">Une procédure stockée peut prendre un nombre illimité de paramètres.</span><span class="sxs-lookup"><span data-stu-id="a4d12-118">A stored procedure can take any number of parameters.</span></span>  
  
-   <span data-ttu-id="a4d12-119">Une procédure stockée peut retourner un jeu de données, un `IDataReader` ou un résultat vide.</span><span class="sxs-lookup"><span data-stu-id="a4d12-119">A stored procedure can return a dataset, an `IDataReader`, or an empty result.</span></span>  
  
 <span data-ttu-id="a4d12-120">L'exemple suivant utilise la procédure stockée fictive `FinalSalesNumbers` :</span><span class="sxs-lookup"><span data-stu-id="a4d12-120">The following example uses the fictional stored procedure, `FinalSalesNumbers`:</span></span>  
  
```  
CALL FinalSalesNumbers()  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4d12-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4d12-121">See Also</span></span>  
 [<span data-ttu-id="a4d12-122">Programmation du serveur ADOMD.NET</span><span class="sxs-lookup"><span data-stu-id="a4d12-122">ADOMD.NET Server Programming</span></span>](https://docs.microsoft.com/bi-reference/adomd/multidimensional-models-adomd-net-server/adomd-net-server-programming)  
  
  
