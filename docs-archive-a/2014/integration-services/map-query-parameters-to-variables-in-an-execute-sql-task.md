---
title: Mapper des paramètres de requête à des variables dans une tâche d’exécution SQL | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- queries [Integration Services], parameter mapping
- parameterized SQL commands [Integration Services]
- parameters [Integration Services]
- mapping query parameters to variables [Integration Services]
- Execute SQL task [Integration Services]
- variables [Integration Services], mapping parameters to
ms.assetid: 6a164349-dfcf-4995-80bc-d4e7aee52a83
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8511d70b40f2934680e1cb790763045c04e8204a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604614"
---
# <a name="map-query-parameters-to-variables-in-an-execute-sql-task"></a><span data-ttu-id="db247-102">Mapper des paramètres de requête à des variables dans une tâche d'exécution SQL</span><span class="sxs-lookup"><span data-stu-id="db247-102">Map Query Parameters to Variables in an Execute SQL Task</span></span>

  <span data-ttu-id="db247-103">Cette rubrique décrit la façon d'utiliser une instruction SQL paramétrable dans la tâche d'exécution SQL et de créer des mappages entre des variables et les paramètres de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="db247-103">This topic describes how to use a parameterized SQL statement in the Execute SQL task and create mappings between variables and the parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="db247-104">Pour en savoir plus sur la tâche d’exécution SQL, les marqueurs de paramètres et les noms de paramètres que vous utilisez avec différents types de connexions, consultez [Tâche d’exécution de requêtes SQL](control-flow/execute-sql-task.md) et [Paramètres et codes de retour dans la tâche d’exécution SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="db247-104">To learn more about the Execute SQL task, the parameter markers, and parameter names you use with different connection types, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
### <a name="to-map-a-query-parameter-to-a-variable"></a><span data-ttu-id="db247-105">Pour mapper un paramètre de requête à une variable</span><span class="sxs-lookup"><span data-stu-id="db247-105">To map a query parameter to a variable</span></span>  
  
1.  <span data-ttu-id="db247-106">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="db247-106">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package you want to work with.</span></span>  
  
2.  <span data-ttu-id="db247-107">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="db247-107">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="db247-108">Cliquez sur l'onglet **Flux de contrôle** .</span><span class="sxs-lookup"><span data-stu-id="db247-108">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="db247-109">Si le package ne contient pas déjà une tâche d'exécution SQL, ajoutez-en une au flux de contrôle du package.</span><span class="sxs-lookup"><span data-stu-id="db247-109">If the package does not already include an Execute SQL task, add one to the control flow of the package.</span></span> <span data-ttu-id="db247-110">Pour plus d’informations, consultez [Ajouter ou supprimer une tâche ou un conteneur dans un workflow de contrôle](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span><span class="sxs-lookup"><span data-stu-id="db247-110">For more information, see [Add or Delete a Task or a Container in a Control Flow](control-flow/add-or-delete-a-task-or-a-container-in-a-control-flow.md)</span></span>  
  <span data-ttu-id="db247-111">.</span><span class="sxs-lookup"><span data-stu-id="db247-111">.</span></span>  
  
5.  <span data-ttu-id="db247-112">Double-cliquez sur la tâche d'exécution SQL.</span><span class="sxs-lookup"><span data-stu-id="db247-112">Double-click the Execute SQL task.</span></span>  
  
6.  <span data-ttu-id="db247-113">Indiquez une commande SQL paramétrable de l'une des manières suivantes :</span><span class="sxs-lookup"><span data-stu-id="db247-113">Provide a parameterized SQL command in one of the following ways:</span></span>  
  
    -   <span data-ttu-id="db247-114">Utilisez l’entrée directe et tapez la commande SQL dans la propriété SQLStatement.</span><span class="sxs-lookup"><span data-stu-id="db247-114">Use direct input and type the SQL command in the SQLStatement property.</span></span>  
  
    -   <span data-ttu-id="db247-115">Utilisez l’entrée directe, cliquez sur **Générer la requête**, puis créez une commande SQL à l’aide des outils graphiques fournis par le Générateur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="db247-115">Use direct input, click **Build Query**, and then create an SQL command using the graphical tools that the Query Builder provides.</span></span>  
  
    -   <span data-ttu-id="db247-116">Utilisez un fichier de connexion, puis référencez le fichier contenant la commande SQL.</span><span class="sxs-lookup"><span data-stu-id="db247-116">Use a file connection and then reference the file that contains the SQL command.</span></span>  
  
    -   <span data-ttu-id="db247-117">Utilisez une variable, puis référencez la variable contenant la commande SQL.</span><span class="sxs-lookup"><span data-stu-id="db247-117">Use a variable and then reference the variable that contains the SQL command.</span></span>  
  
     <span data-ttu-id="db247-118">Les marqueurs de paramètres que vous utilisez dans les instructions SQL paramétrables sont liés au type de connexion que la tâche d'exécution SQL utilise.</span><span class="sxs-lookup"><span data-stu-id="db247-118">The parameter markers that you use in parameterized SQL statements depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="db247-119">Type de connexion</span><span class="sxs-lookup"><span data-stu-id="db247-119">Connection type</span></span>|<span data-ttu-id="db247-120">Marqueur de paramètre</span><span class="sxs-lookup"><span data-stu-id="db247-120">Parameter marker</span></span>|  
    |---------------------|----------------------|  
    |<span data-ttu-id="db247-121">ADO</span><span class="sxs-lookup"><span data-stu-id="db247-121">ADO</span></span>|<span data-ttu-id="db247-122">?</span><span class="sxs-lookup"><span data-stu-id="db247-122">?</span></span>|  
    |<span data-ttu-id="db247-123">ADO.NET et SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="db247-123">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="db247-124">ODBC</span><span class="sxs-lookup"><span data-stu-id="db247-124">ODBC</span></span>|<span data-ttu-id="db247-125">?</span><span class="sxs-lookup"><span data-stu-id="db247-125">?</span></span>|  
    |<span data-ttu-id="db247-126">EXCEL et OLE DB</span><span class="sxs-lookup"><span data-stu-id="db247-126">EXCEL and OLE DB</span></span>|<span data-ttu-id="db247-127">?</span><span class="sxs-lookup"><span data-stu-id="db247-127">?</span></span>|  
  
     <span data-ttu-id="db247-128">Le tableau suivant présente des exemples de la commande SELECT par type de gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="db247-128">The following table lists examples of the SELECT command by connection manager type.</span></span> <span data-ttu-id="db247-129">Les paramètres fournissent les valeurs de filtre dans les clauses WHERE.</span><span class="sxs-lookup"><span data-stu-id="db247-129">Parameters provide the filter values in the WHERE clauses.</span></span> <span data-ttu-id="db247-130">Les exemples utilisent la commande SELECT pour retourner les produits de la table **Product** dans [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] qui ont un **ProductID** supérieur et inférieur aux valeurs spécifiées par deux paramètres.</span><span class="sxs-lookup"><span data-stu-id="db247-130">The examples use SELECT to return products from the **Product** table in [!INCLUDE[ssSampleDBUserInputNonLocal](../includes/sssampledbuserinputnonlocal-md.md)] that have a **ProductID** greater than and less than the values specified by two parameters.</span></span>  
  
    |<span data-ttu-id="db247-131">Type de connexion</span><span class="sxs-lookup"><span data-stu-id="db247-131">Connection type</span></span>|<span data-ttu-id="db247-132">Syntaxe SELECT</span><span class="sxs-lookup"><span data-stu-id="db247-132">SELECT syntax</span></span>|  
    |---------------------|-------------------|  
    |<span data-ttu-id="db247-133">EXCEL, ODBC et OLEDB</span><span class="sxs-lookup"><span data-stu-id="db247-133">EXCEL, ODBC, and OLEDB</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |<span data-ttu-id="db247-134">ADO</span><span class="sxs-lookup"><span data-stu-id="db247-134">ADO</span></span>|`SELECT* FROM Production.Product WHERE ProductId > ? AND ProductID < ?`|  
    |[!INCLUDE[vstecado](../includes/vstecado-md.md)]|`SELECT* FROM Production.Product WHERE ProductId > @parmMinProductID AND ProductID < @parmMaxProductID`|  
  
     <span data-ttu-id="db247-135">Pour obtenir des exemples d’utilisation des paramètres avec des procédures stockées, consultez [Paramètres et codes de retour dans la tâche d’exécution SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="db247-135">For examples of using parameters with stored procedures, see [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
7.  <span data-ttu-id="db247-136">Cliquez sur **Mappage de paramètre**.</span><span class="sxs-lookup"><span data-stu-id="db247-136">Click **Parameter Mapping**.</span></span>  
  
8.  <span data-ttu-id="db247-137">Pour ajouter un mappage de paramètre, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="db247-137">To add a parameter mapping, click **Add**.</span></span>  
  
9. <span data-ttu-id="db247-138">Fournissez un nom dans la zone **Nom du paramètre** .</span><span class="sxs-lookup"><span data-stu-id="db247-138">Provide a name in the **Parameter Name** box.</span></span>  
  
     <span data-ttu-id="db247-139">Les noms de paramètres que vous utilisez sont liés au type de connexion que la tâche d'exécution SQL utilise.</span><span class="sxs-lookup"><span data-stu-id="db247-139">The parameter names that you use depend on the connection type that the Execute SQL task uses.</span></span>  
  
    |<span data-ttu-id="db247-140">Type de connexion</span><span class="sxs-lookup"><span data-stu-id="db247-140">Connection type</span></span>|<span data-ttu-id="db247-141">Nom du paramètre</span><span class="sxs-lookup"><span data-stu-id="db247-141">Parameter name</span></span>|  
    |---------------------|--------------------|  
    |<span data-ttu-id="db247-142">ADO</span><span class="sxs-lookup"><span data-stu-id="db247-142">ADO</span></span>|<span data-ttu-id="db247-143">Param1, Param2, ...</span><span class="sxs-lookup"><span data-stu-id="db247-143">Param1, Param2, ...</span></span>|  
    |<span data-ttu-id="db247-144">ADO.NET et SQLMOBILE</span><span class="sxs-lookup"><span data-stu-id="db247-144">ADO.NET and SQLMOBILE</span></span>|@\<parameter name>|  
    |<span data-ttu-id="db247-145">ODBC</span><span class="sxs-lookup"><span data-stu-id="db247-145">ODBC</span></span>|<span data-ttu-id="db247-146">1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="db247-146">1, 2, 3, ...</span></span>|  
    |<span data-ttu-id="db247-147">EXCEL et OLE DB</span><span class="sxs-lookup"><span data-stu-id="db247-147">EXCEL and OLE DB</span></span>|<span data-ttu-id="db247-148">0, 1, 2, 3, ...</span><span class="sxs-lookup"><span data-stu-id="db247-148">0, 1, 2, 3, ...</span></span>|  
  
10. <span data-ttu-id="db247-149">Dans la liste **Nom de variable** , sélectionnez une variable.</span><span class="sxs-lookup"><span data-stu-id="db247-149">From the **Variable Name** list, select a variable.</span></span> <span data-ttu-id="db247-150">Pour plus d’informations, consultez [Ajouter, supprimer, modifier l’étendue de la variable définie par l’utilisateur dans un package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="db247-150">For more information, see [Add, Delete, Change Scope of User-Defined Variable in a Package](../../2014/integration-services/add-delete-change-scope-of-user-defined-variable-in-a-package.md).</span></span>  
  
11. <span data-ttu-id="db247-151">Dans la liste **Direction** , indiquez si le paramètre est une entrée, une sortie ou une valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="db247-151">In the **Direction** list, specify if the parameter is an input, an output, or a return value.</span></span>  
  
12. <span data-ttu-id="db247-152">Dans la liste **Type de données** , définissez le type de données du paramètre.</span><span class="sxs-lookup"><span data-stu-id="db247-152">In the **Data Type** list, set the data type of the parameter.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="db247-153">Le type de données du paramètre doit être compatible avec le type de données de la variable.</span><span class="sxs-lookup"><span data-stu-id="db247-153">The data type of the parameter must be compatible with the data type of the variable.</span></span>  
  
13. <span data-ttu-id="db247-154">Répétez les étapes 8 à 11 pour chaque paramètre de l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="db247-154">Repeat steps 8 through 11 for each parameter in the SQL statement.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="db247-155">L'ordre de mappage des paramètres doit être identique à leur ordre d'apparition dans l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="db247-155">The order of parameter mappings must be the same as the order in which the parameters appear in the SQL statement.</span></span>  
  
14. <span data-ttu-id="db247-156">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db247-156">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db247-157">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db247-157">See Also</span></span>  
 <span data-ttu-id="db247-158">[Tâche d’exécution SQL](control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="db247-158">[Execute SQL Task](control-flow/execute-sql-task.md) </span></span>  
 <span data-ttu-id="db247-159">[Paramètres et codes de retour dans la tâche d’exécution SQL](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="db247-159">[Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md) </span></span>  
 [<span data-ttu-id="db247-160">Variables Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="db247-160">Integration Services &#40;SSIS&#41; Variables</span></span>](integration-services-ssis-variables.md)  
  
  
