---
title: MSSQLSERVER_107 | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 107 (Database Engine error)
ms.assetid: f33f514c-56aa-42e2-841b-e91244da90e2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: b9388bbda6f00b1aafd02caee1b6a7b8387564f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612399"
---
# <a name="mssqlserver_107"></a><span data-ttu-id="5a4cb-102">MSSQLSERVER_107</span><span class="sxs-lookup"><span data-stu-id="5a4cb-102">MSSQLSERVER_107</span></span>
    
## <a name="details"></a><span data-ttu-id="5a4cb-103">Détails</span><span class="sxs-lookup"><span data-stu-id="5a4cb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a4cb-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="5a4cb-104">Product Name</span></span>|<span data-ttu-id="5a4cb-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a4cb-105">SQL Server</span></span>|  
|<span data-ttu-id="5a4cb-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="5a4cb-106">Event ID</span></span>|<span data-ttu-id="5a4cb-107">107</span><span class="sxs-lookup"><span data-stu-id="5a4cb-107">107</span></span>|  
|<span data-ttu-id="5a4cb-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="5a4cb-108">Event Source</span></span>|<span data-ttu-id="5a4cb-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a4cb-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a4cb-110">Composant</span><span class="sxs-lookup"><span data-stu-id="5a4cb-110">Component</span></span>|<span data-ttu-id="5a4cb-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a4cb-111">SQLEngine</span></span>|  
|<span data-ttu-id="5a4cb-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="5a4cb-112">Symbolic Name</span></span>|<span data-ttu-id="5a4cb-113">P_NOCORRMATCH</span><span class="sxs-lookup"><span data-stu-id="5a4cb-113">P_NOCORRMATCH</span></span>|  
|<span data-ttu-id="5a4cb-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="5a4cb-114">Message Text</span></span>|<span data-ttu-id="5a4cb-115">Le préfixe de colonne '%.\*ls' ne correspond ni au nom de table ni au nom d'alias utilisés dans la requête.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-115">The column prefix '%.\*ls' does not match with a table name or alias name used in the query.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a4cb-116">Explication</span><span class="sxs-lookup"><span data-stu-id="5a4cb-116">Explanation</span></span>  
 <span data-ttu-id="5a4cb-117">La liste de sélection de la requête contient un astérisque (\*) incorrectement qualifié avec un préfixe de colonne.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-117">The select list of the query contains an asterisk (\*) that is incorrectly qualified with a column prefix.</span></span> <span data-ttu-id="5a4cb-118">Cette erreur peut être retournée dans les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="5a4cb-118">This error can be returned under the following conditions:</span></span>  
  
-   <span data-ttu-id="5a4cb-119">Le préfixe de colonne ne correspond à aucun nom de table ou d'alias utilisé dans la requête.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-119">The column prefix does not correspond to any table or alias name used in the query.</span></span> <span data-ttu-id="5a4cb-120">Par exemple, l'instruction suivante utilise un nom d'alias (`T1`) en tant que préfixe de colonne, mais l'alias n'est pas défini dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-120">For example, the following statement uses an alias name (`T1`) as a column prefix, but the alias is not defined in the FROM clause.</span></span>  
  
    ```  
    SELECT T1.* FROM dbo.ErrorLog;  
    ```  
  
-   <span data-ttu-id="5a4cb-121">Un nom de table est spécifié en tant que préfixe de colonne alors qu'un nom d'alias pour la table est fourni dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-121">A table name is specified as a column prefix when an alias name for the table is supplied in the FROM clause.</span></span> <span data-ttu-id="5a4cb-122">Par exemple, l'instruction suivante utilise le nom de table `ErrorLog` en tant que préfixe de colonne ; toutefois, la table a un alias (`T1`) défini dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-122">For example, the following statement uses the table name `ErrorLog` as the column prefix; however, the table has an alias (`T1`) defined in the FROM clause.</span></span>  
  
    ```  
    SELECT ErrorLog.* FROM dbo.ErrorLog AS T1;  
    ```  
  
     <span data-ttu-id="5a4cb-123">Si un alias a été fourni pour un nom de table dans la clause FROM, seul cet alias peut être utilisé pour préfixer des colonnes de la table.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-123">If an alias has been provided for a table name in the FROM clause, you can only use the alias to prefix columns from the table.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a4cb-124">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="5a4cb-124">User Action</span></span>  
 <span data-ttu-id="5a4cb-125">Faites correspondre les préfixes de colonnes aux noms de tables ou d'alias spécifiés dans la clause FROM de la requête.</span><span class="sxs-lookup"><span data-stu-id="5a4cb-125">Match the column prefixes against the table names or alias names specified in the FROM clause of the query.</span></span> <span data-ttu-id="5a4cb-126">Par exemple, les instructions ci-dessus peuvent être corrigées comme suit :</span><span class="sxs-lookup"><span data-stu-id="5a4cb-126">For example, the statements above can be corrected as follows:</span></span>  
  
```  
SELECT T1.* FROM dbo.ErrorLog AS T1;  
```  
  
 <span data-ttu-id="5a4cb-127">or</span><span class="sxs-lookup"><span data-stu-id="5a4cb-127">or</span></span>  
  
```  
SELECT ErrorLog.* FROM dbo.ErrorLog;  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a4cb-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a4cb-128">See Also</span></span>  
 [<span data-ttu-id="5a4cb-129">MSSQLSERVER_4104</span><span class="sxs-lookup"><span data-stu-id="5a4cb-129">MSSQLSERVER_4104</span></span>](mssqlserver-4104-database-engine-error.md)  
  
  
