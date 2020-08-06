---
title: Paramètres de la requête, boîte de dialogue (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdtsql.chm:69645
- vdt.dlgbox.definequeryparameters
ms.assetid: 31cdaee2-d7cd-4d64-a45f-924b27e8b1f0
author: stevestein
ms.author: sstein
ms.openlocfilehash: 76052876ad2899fc959aa7fc49f4299e08bac713
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697363"
---
# <a name="query-parameters-dialog-box-visual-database-tools"></a><span data-ttu-id="ac68a-102">Paramètres de la requête, boîte de dialogue (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="ac68a-102">Query Parameters Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="ac68a-103">Cette boîte de dialogue permet d'entrer des valeurs pour les paramètres définis dans la requête.</span><span class="sxs-lookup"><span data-stu-id="ac68a-103">This dialog allows you to enter values for the parameters defined in the query.</span></span> <span data-ttu-id="ac68a-104">Elle apparaît lorsque vous exécutez une requête qui contient des paramètres qui exigent une entrée de l'utilisateur final au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="ac68a-104">This dialog box appears when you execute a query that contains parameters that require end-user input at run time.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ac68a-105">Options</span><span class="sxs-lookup"><span data-stu-id="ac68a-105">Options</span></span>  
 <span data-ttu-id="ac68a-106">**Nom**</span><span class="sxs-lookup"><span data-stu-id="ac68a-106">**Name**</span></span>  
 <span data-ttu-id="ac68a-107">Énumère les paramètres définis pour la requête en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="ac68a-107">Lists the parameters defined for the query being executed.</span></span> <span data-ttu-id="ac68a-108">Si la requête contient des paramètres nommés, les noms apparaissent dans la liste.</span><span class="sxs-lookup"><span data-stu-id="ac68a-108">If the query contains named parameters, the names appear in the list.</span></span> <span data-ttu-id="ac68a-109">Si la requête contient des paramètres sans nom, les noms des paramètres définis par le système sont répertoriés pour chaque paramètre dans la requête.</span><span class="sxs-lookup"><span data-stu-id="ac68a-109">If the query contains unnamed parameters, system-defined parameter names are listed for each parameter in the query.</span></span>  
  
 <span data-ttu-id="ac68a-110">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="ac68a-110">**Value**</span></span>  
 <span data-ttu-id="ac68a-111">Entrez la valeur de chaque paramètre énuméré sous **Nom**.</span><span class="sxs-lookup"><span data-stu-id="ac68a-111">Enter the value for each parameter listed under **Name**.</span></span> <span data-ttu-id="ac68a-112">La dernière valeur utilisée apparaît comme valeur par défaut du paramètre.</span><span class="sxs-lookup"><span data-stu-id="ac68a-112">The value used most recently appears as the default parameter value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac68a-113">Exemple</span><span class="sxs-lookup"><span data-stu-id="ac68a-113">Example</span></span>  
 <span data-ttu-id="ac68a-114">La requête suivante dans le volet SQL ouvre la boite de dialogue Paramètres de la requête lorsqu'elle est exécutée dans la base de données [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ac68a-114">The following query in the SQL Pane, opens the Query Parameters dialog box when executed in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT   FirstName, LastName  
FROM    Person.Person AS Lastname  
WHERE   (LastName = @Param1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ac68a-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ac68a-115">See Also</span></span>  
 [<span data-ttu-id="ac68a-116">Requête avec des paramètres &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="ac68a-116">Query with Parameters &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
