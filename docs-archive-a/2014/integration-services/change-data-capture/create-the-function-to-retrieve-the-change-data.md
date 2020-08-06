---
title: Créer la fonction de récupération des données modifiées | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- incremental load [Integration Services],creating function
ms.assetid: 55dd0946-bd67-4490-9971-12dfb5b9de94
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cc1d5af0a64225aca4ff54570ad6504d25d62812
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707731"
---
# <a name="create-the-function-to-retrieve-the-change-data"></a><span data-ttu-id="59adf-102">Créer la fonction de récupération des données modifiées</span><span class="sxs-lookup"><span data-stu-id="59adf-102">Create the Function to Retrieve the Change Data</span></span>
  <span data-ttu-id="59adf-103">Une fois que vous avez terminé le flux de contrôle d’un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui effectue un chargement incrémentiel des données modifiées, la tâche suivante consiste à créer une fonction table qui récupère les données modifiées.</span><span class="sxs-lookup"><span data-stu-id="59adf-103">After completing the control flow for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package that performs an incremental load of change data, the next task is to create a table-valued function that retrieves the change data.</span></span> <span data-ttu-id="59adf-104">Vous ne devez créer cette fonction qu'une seule fois avant le premier chargement incrémentiel.</span><span class="sxs-lookup"><span data-stu-id="59adf-104">You only have to create this function one time before the first incremental load.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59adf-105">La création d'une fonction de récupération des données modifiées est la deuxième étape du processus de création d'un package qui effectue un chargement incrémentiel des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="59adf-105">The creation of a function to retrieve the change data is the second step in the process of creating a package that performs an incremental load of change data.</span></span> <span data-ttu-id="59adf-106">Pour obtenir une description du processus global de la création de ce package, consultez [Capture de données modifiées &#40;SSIS&#41;](change-data-capture-ssis.md).</span><span class="sxs-lookup"><span data-stu-id="59adf-106">For a description of the overall process for creating this package, see [Change Data Capture &#40;SSIS&#41;](change-data-capture-ssis.md).</span></span>  
  
## <a name="design-considerations-for-change-data-capture-functions"></a><span data-ttu-id="59adf-107">Considérations relatives à la conception de fonctions de capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="59adf-107">Design Considerations for Change Data Capture Functions</span></span>  
 <span data-ttu-id="59adf-108">Pour récupérer des données modifiées, un composant source dans le flux de données du package appelle l'une des fonctions de requête de capture de données modifiées suivantes :</span><span class="sxs-lookup"><span data-stu-id="59adf-108">To retrieve change data, a source component in the data flow of the package calls one of the following change data capture query functions:</span></span>  
  
-   <span data-ttu-id="59adf-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** Pour cette requête, la ligne unique renvoyée pour chaque mise à jour contient l’état final de chaque ligne modifiée.</span><span class="sxs-lookup"><span data-stu-id="59adf-109">**cdc.fn_cdc_get_net_changes_<capture_instance>** For this query, the single row returned for each update contains the final state of each changed row.</span></span> <span data-ttu-id="59adf-110">Dans la plupart des cas, vous n'avez besoin que des données retournées par une requête des modifications nettes.</span><span class="sxs-lookup"><span data-stu-id="59adf-110">In most cases, you only need the data returned by a query for net changes.</span></span> <span data-ttu-id="59adf-111">Pour plus d’informations, consultez [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59adf-111">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
-   <span data-ttu-id="59adf-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** Cette requête renvoie toutes les modifications qui se sont produites dans chaque ligne au cours de l’intervalle de capture.</span><span class="sxs-lookup"><span data-stu-id="59adf-112">**cdc.fn_cdc_get_all_changes_<capture_instance>** This query returns all the changes that have occurred in each row during the capture interval.</span></span> <span data-ttu-id="59adf-113">Pour plus d’informations, consultez [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59adf-113">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="59adf-114">Le composant source prend ensuite les résultats retournés par la fonction et les passe aux transformations et aux destinations en aval qui appliquent les données modifiées à la destination finale.</span><span class="sxs-lookup"><span data-stu-id="59adf-114">The source component then takes the results returned by the function and passes them to downstream transformations and destinations, which apply the change data to the final destination.</span></span>  
  
 <span data-ttu-id="59adf-115">Toutefois, un composant source [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ne peut pas appeler directement ces fonctions de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="59adf-115">However, an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component cannot call these change data capture functions directly.</span></span> <span data-ttu-id="59adf-116">Un composant source [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] nécessite des métadonnées sur les colonnes retournées par la requête.</span><span class="sxs-lookup"><span data-stu-id="59adf-116">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component requires metadata about the columns that the query returns.</span></span> <span data-ttu-id="59adf-117">Les fonctions de capture de données modifiées ne définissent pas les colonnes de leur table de sortie.</span><span class="sxs-lookup"><span data-stu-id="59adf-117">The change data capture functions do not define the columns of their output table.</span></span> <span data-ttu-id="59adf-118">Ces fonctions ne retournent donc pas suffisamment de métadonnées pour un composant source [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59adf-118">Thus, these functions do not return sufficient metadata for an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
 <span data-ttu-id="59adf-119">Utilisez plutôt une fonction wrapper table car ce type de fonction définit explicitement les colonnes de sa table de sortie dans sa clause RETURNS.</span><span class="sxs-lookup"><span data-stu-id="59adf-119">Instead, you use a table-valued wrapper function because this kind of function explicitly defines the columns of its output table in its RETURNS clause.</span></span> <span data-ttu-id="59adf-120">Cette définition explicite de colonnes fournit les métadonnées nécessaires à un composant source [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59adf-120">This explicit definition of columns provides the metadata that an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component needs.</span></span> <span data-ttu-id="59adf-121">Vous devez créer cette fonction pour chaque table pour laquelle vous souhaitez récupérer des données modifiées.</span><span class="sxs-lookup"><span data-stu-id="59adf-121">You have to create this function for each table for which you want to retrieve change data.</span></span>  
  
 <span data-ttu-id="59adf-122">Vous disposez de deux options pour créer une fonction wrapper table qui appelle la fonction de requête de capture de données modifiées :</span><span class="sxs-lookup"><span data-stu-id="59adf-122">You have two options for creating the table-valued wrapper function that calls the change data capture query function:</span></span>  
  
-   <span data-ttu-id="59adf-123">Vous pouvez appeler la procédure stockée système **sys.sp_cdc_generate_wrapper_function** pour créer les fonctions table pour vous.</span><span class="sxs-lookup"><span data-stu-id="59adf-123">You can call the **sys.sp_cdc_generate_wrapper_function** system stored procedure to create the table-valued functions for you.</span></span>  
  
-   <span data-ttu-id="59adf-124">Vous pouvez écrire votre propre fonction table en utilisant les indications et l'exemple donnés dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="59adf-124">You can write your own table-valued function by using the guidelines and the example in this topic.</span></span>  
  
## <a name="calling-a-stored-procedure-to-create-the-table-valued-function"></a><span data-ttu-id="59adf-125">Appel d'une procédure stockée pour créer la fonction table</span><span class="sxs-lookup"><span data-stu-id="59adf-125">Calling a Stored Procedure to Create the Table-valued Function</span></span>  
 <span data-ttu-id="59adf-126">La méthode la plus rapide et la plus facile pour créer les fonctions table dont vous avez besoin consiste à appeler la procédure stockée système **sys.sp_cdc_generate_wrapper_function** .</span><span class="sxs-lookup"><span data-stu-id="59adf-126">The quickest and easiest way to create the table-valued functions that you need is to call the **sys.sp_cdc_generate_wrapper_function** system stored procedure.</span></span> <span data-ttu-id="59adf-127">Cette procédure stockée génère des scripts permettant de créer des fonctions wrapper spécifiquement conçues pour répondre aux besoins d'un composant source [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59adf-127">This stored procedure generates scripts to create wrapper functions that are designed specifically to meet the needs of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] source component.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="59adf-128">La procédure stockée système **sys.sp_cdc_generate_wrapper_function** ne crée pas directement les fonctions wrapper.</span><span class="sxs-lookup"><span data-stu-id="59adf-128">The **sys.sp_cdc_generate_wrapper_function** system stored procedure does not directly create the wrapper functions.</span></span> <span data-ttu-id="59adf-129">À la place, elle génère les scripts CREATE pour les fonctions wrapper.</span><span class="sxs-lookup"><span data-stu-id="59adf-129">Instead, the stored procedure generates the CREATE scripts for the wrapper functions.</span></span> <span data-ttu-id="59adf-130">Le développeur doit exécuter les scripts CREATE que la procédure stockée génère avant qu'un package de chargement incrémentiel puisse appeler les fonctions wrapper.</span><span class="sxs-lookup"><span data-stu-id="59adf-130">The developer must run the CREATE scripts that the stored procedure generates before an incremental load package can call the wrapper functions.</span></span>  
  
 <span data-ttu-id="59adf-131">Pour maîtriser l'utilisation de cette procédure stockée système, vous devez comprendre ce qu'elle fait, les scripts qu'elle génère et les fonctions wrapper que les scripts créent.</span><span class="sxs-lookup"><span data-stu-id="59adf-131">To understand how to use this system stored procedure, you should understand what the procedure does, what scripts the procedure generates, and what wrapper functions the scripts create.</span></span>  
  
### <a name="understanding-and-using-the-stored-procedure"></a><span data-ttu-id="59adf-132">Présentation et utilisation de la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="59adf-132">Understanding and Using the Stored Procedure</span></span>  
 <span data-ttu-id="59adf-133">La procédure stockée système **sys.sp_cdc_generate_wrapper_function** génère des scripts permettant de créer des fonctions wrapper utilisées par les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="59adf-133">The **sys.sp_cdc_generate_wrapper_function** system stored procedure generates scripts to create wrapper functions for use by [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
 <span data-ttu-id="59adf-134">Les premières lignes de la définition de la procédure stockée sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="59adf-134">Here are the first few lines of the definition of the stored procedure:</span></span>  
  
 `CREATE PROCEDURE sys.sp_cdc_generate_wrapper_function`  
  
 `(`  
  
 `@capture_instance sysname = null`  
  
 `@closed_high_end_point bit = 1,`  
  
 `@column_list = null,`  
  
 `@update_flag_list = null`  
  
 `)`  
  
 <span data-ttu-id="59adf-135">Tous les paramètres de la procédure stockée sont facultatifs.</span><span class="sxs-lookup"><span data-stu-id="59adf-135">All the parameters for the stored procedure are optional.</span></span> <span data-ttu-id="59adf-136">Si vous appelez la procédure stockée sans fournir des valeurs pour chacun des paramètres, elle crée des fonctions wrapper pour toutes les instances de capture auxquelles vous avez accès.</span><span class="sxs-lookup"><span data-stu-id="59adf-136">If you call the stored procedure without supplying values for any of the parameters, the stored procedure creates wrapper functions for all the capture instances to which you have access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="59adf-137">Pour plus d'informations sur la syntaxe de cette procédure stockée et ses paramètres, consultez [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59adf-137">For more information about the syntax of this stored procedure and its parameters, see [sys.sp_cdc_generate_wrapper_function &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sys-sp-cdc-generate-wrapper-function-transact-sql).</span></span>  
  
 <span data-ttu-id="59adf-138">La procédure stockée génère systématiquement une fonction wrapper pour retourner toutes les modifications de chaque instance de capture.</span><span class="sxs-lookup"><span data-stu-id="59adf-138">The stored procedure always generates a wrapper function to return all changes from each capture instance.</span></span> <span data-ttu-id="59adf-139">Si le *@supports_net_changes* paramètre a été défini lors de la création de l’instance de capture, la procédure stockée génère également une fonction wrapper pour retourner les modifications nettes de chaque instance de capture applicable.</span><span class="sxs-lookup"><span data-stu-id="59adf-139">If the *@supports_net_changes* parameter was set when the capture instance was created, the stored procedure also generates a wrapper function to return net changes from each applicable capture instance.</span></span>  
  
 <span data-ttu-id="59adf-140">La procédure stockée retourne un jeu de résultats à deux colonnes :</span><span class="sxs-lookup"><span data-stu-id="59adf-140">The stored procedure returns a result set with two columns:</span></span>  
  
-   <span data-ttu-id="59adf-141">Le nom de la fonction wrapper générée par la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="59adf-141">The name of the wrapper function that the stored procedure has generated.</span></span> <span data-ttu-id="59adf-142">Cette procédure stockée dérive le nom de fonction du nom de l'instance de capture.</span><span class="sxs-lookup"><span data-stu-id="59adf-142">This stored procedure derives the function name from the name of the capture instance name.</span></span> <span data-ttu-id="59adf-143">(Le nom de la fonction est « fn_all_changes_ » suivi du nom de l'instance de capture.</span><span class="sxs-lookup"><span data-stu-id="59adf-143">(The function name is 'fn_all_changes_' followed by the capture instance name.</span></span> <span data-ttu-id="59adf-144">Le préfixe utilisé pour la fonction de suivi des modifications nettes, s'il est créé, est « fn_net_changes_ ».)</span><span class="sxs-lookup"><span data-stu-id="59adf-144">The prefix used for the net changes function, if it is created, is 'fn_net_changes_'.)</span></span>  
  
-   <span data-ttu-id="59adf-145">L'instruction CREATE pour la fonction wrapper.</span><span class="sxs-lookup"><span data-stu-id="59adf-145">The CREATE statement for the wrapper function.</span></span>  
  
### <a name="understanding-and-using-the-scripts-created-by-the-stored-procedure"></a><span data-ttu-id="59adf-146">Présentation et utilisation des scripts créés par la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="59adf-146">Understanding and Using the Scripts Created by the Stored Procedure</span></span>  
 <span data-ttu-id="59adf-147">En général, un développeur utilise une instruction INSERT...EXEC pour appeler la procédure stockée **sys.sp_cdc_generate_wrapper_function** et enregistrer les scripts qu'elle crée dans une table temporaire.</span><span class="sxs-lookup"><span data-stu-id="59adf-147">Typically, a developer would use an INSERT...EXEC statement to call the **sys.sp_cdc_generate_wrapper_function** stored procedure and save the scripts that the stored procedure creates to a temporary table.</span></span> <span data-ttu-id="59adf-148">Chaque script peut ensuite être sélectionné et exécuté individuellement afin de créer la fonction wrapper correspondante.</span><span class="sxs-lookup"><span data-stu-id="59adf-148">Each script could then be individually selected and run to create the corresponding wrapper function.</span></span> <span data-ttu-id="59adf-149">Toutefois, un développeur peut également utiliser un jeu de commandes SQL pour exécuter l'ensemble des scripts CREATE, tel qu'indiqué dans l'exemple de code suivant :</span><span class="sxs-lookup"><span data-stu-id="59adf-149">However, a developer could also use one set of SQL commands to run all the CREATE scripts, as shown in the following sample code:</span></span>  
  
```  
create table #wrapper_functions  
      (function_name sysname, create_stmt nvarchar(max))  
insert into #wrapper_functions  
exec sys.sp_cdc_generate_wrapper_function  
  
declare @stmt nvarchar(max)  
declare #hfunctions cursor local fast_forward for   
      select create_stmt from #wrapper_functions  
open #hfunctions  
fetch #hfunctions into @stmt  
while (@@fetch_status <> -1)  
begin  
      exec sp_executesql @stmt  
      fetch #hfunctions into @stmt  
end  
close #hfunctions  
deallocate #hfunctions  
```  
  
### <a name="understanding-and-using-the-functions-created-by-the-stored-procedure"></a><span data-ttu-id="59adf-150">Présentation et utilisation des fonctions créées par la procédure stockée</span><span class="sxs-lookup"><span data-stu-id="59adf-150">Understanding and Using the Functions Created by the Stored Procedure</span></span>  
 <span data-ttu-id="59adf-151">Pour parcourir systématiquement la chronologie des données de modification capturées, les fonctions wrapper générées s’attendent à ce que le *@end_time* paramètre d’un intervalle soit le *@start_time* paramètre de l’intervalle suivant.</span><span class="sxs-lookup"><span data-stu-id="59adf-151">To systematically walk the timeline of captured change data, the generated wrapper functions expect that the *@end_time* parameter for one interval will be the *@start_time* parameter for the subsequent interval.</span></span> <span data-ttu-id="59adf-152">Lorsque cette convention est suivie, les fonctions wrapper générées peuvent effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="59adf-152">When this convention is followed, the generated wrapper functions can do the following tasks:</span></span>  
  
-   <span data-ttu-id="59adf-153">Mapper les valeurs de date/d'heure aux valeurs LSN utilisées en interne.</span><span class="sxs-lookup"><span data-stu-id="59adf-153">Map the date/time values to the LSN values that are used internally.</span></span>  
  
-   <span data-ttu-id="59adf-154">Garantir qu'aucune donnée n'est perdue ou répétée.</span><span class="sxs-lookup"><span data-stu-id="59adf-154">Ensure that no data is lost or repeated.</span></span>  
  
 <span data-ttu-id="59adf-155">Pour simplifier l'interrogation de l'ensemble des lignes d'une table de modifications, les fonctions wrapper générées prennent également en charge les conventions suivantes :</span><span class="sxs-lookup"><span data-stu-id="59adf-155">To make querying for all rows of a change table simpler, the generated wrapper functions also support the following conventions:</span></span>  
  
-   <span data-ttu-id="59adf-156">Si le paramètre @start_time est Null, les fonctions wrapper utilisent la valeur LSN la plus basse dans l’instance de capture comme limite inférieure de la requête.</span><span class="sxs-lookup"><span data-stu-id="59adf-156">If the @start_time parameter is null, the wrapper functions use the lowest LSN value in the capture instance as the lower bound of the query.</span></span>  
  
-   <span data-ttu-id="59adf-157">Si le paramètre @end_time est Null, les fonctions wrapper utilisent la valeur LSN la plus élevée dans l’instance de capture comme limite supérieure de la requête.</span><span class="sxs-lookup"><span data-stu-id="59adf-157">If the @end_time parameter is null, the wrapper functions use the highest LSN value in the capture instance as the upper bound of the query.</span></span>  
  
 <span data-ttu-id="59adf-158">La plupart des utilisateurs doivent être en mesure d'utiliser les fonctions wrapper que la procédure stockée système **sys.sp_cdc_generate_wrapper_function** crée sans modification.</span><span class="sxs-lookup"><span data-stu-id="59adf-158">Most users should be able to use the wrapper functions that the **sys.sp_cdc_generate_wrapper_function** system stored procedure creates without modification.</span></span> <span data-ttu-id="59adf-159">Toutefois, pour personnaliser les fonctions wrapper, vous devez personnaliser les scripts CREATE avant de les exécuter.</span><span class="sxs-lookup"><span data-stu-id="59adf-159">However, to customize the wrapper functions, you have to customize the CREATE scripts before you run the scripts.</span></span>  
  
 <span data-ttu-id="59adf-160">Lorsque votre package appelle les fonctions wrapper, il doit fournir des valeurs pour trois paramètres.</span><span class="sxs-lookup"><span data-stu-id="59adf-160">When your package calls the wrapper functions, the package must supply values for three parameters.</span></span> <span data-ttu-id="59adf-161">Ceux-ci sont similaires aux trois paramètres que les fonctions de capture de données modifiées utilisent.</span><span class="sxs-lookup"><span data-stu-id="59adf-161">These three parameters are like the three parameters that the change data capture functions use.</span></span> <span data-ttu-id="59adf-162">Ces trois paramètres sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="59adf-162">These three parameters are as follows:</span></span>  
  
-   <span data-ttu-id="59adf-163">La valeur de date/d'heure de début et celle de date/d'heure de fin de l'intervalle.</span><span class="sxs-lookup"><span data-stu-id="59adf-163">The starting date/time value and the ending date/time value for the interval.</span></span> <span data-ttu-id="59adf-164">Lorsque les fonctions wrapper utilisent des valeurs de date/d'heure comme points pour l'intervalle de requête, les fonctions de capture de données modifiées utilisent deux valeurs LSN comme points de fin.</span><span class="sxs-lookup"><span data-stu-id="59adf-164">While the wrapper functions use date/time values as the end points for the query interval, the change data capture functions use two LSN values as the end points.</span></span>  
  
-   <span data-ttu-id="59adf-165">Le filtre de lignes.</span><span class="sxs-lookup"><span data-stu-id="59adf-165">The row filter.</span></span> <span data-ttu-id="59adf-166">Pour les fonctions wrapper et les fonctions de capture de données modifiées, le *@row_filter_option* paramètre est le même.</span><span class="sxs-lookup"><span data-stu-id="59adf-166">For both the wrapper functions and the change data capture functions, the *@row_filter_option* parameter is the same.</span></span> <span data-ttu-id="59adf-167">Pour plus d’informations, consultez [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) et [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59adf-167">For more information, see [cdc.fn_cdc_get_all_changes_&#60;capture_instance&#62;  &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-all-changes-capture-instance-transact-sql) and [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
 <span data-ttu-id="59adf-168">Le jeu de résultats retourné par les fonctions wrapper inclut les données suivantes :</span><span class="sxs-lookup"><span data-stu-id="59adf-168">The result set returned by the wrapper functions includesthe following data:</span></span>  
  
-   <span data-ttu-id="59adf-169">Toutes les colonnes de données modifiées requises.</span><span class="sxs-lookup"><span data-stu-id="59adf-169">All of the requested columns of change data.</span></span>  
  
-   <span data-ttu-id="59adf-170">Une colonne appelée __CDC_OPERATION qui utilise un champ à un ou deux caractères qui identifie l'opération associée à la ligne.</span><span class="sxs-lookup"><span data-stu-id="59adf-170">A column named __CDC_OPERATION that uses a one- or two-character field to identify the operation that is associated with the row.</span></span> <span data-ttu-id="59adf-171">Les valeurs valides de ce champ sont les suivantes : « I » pour insert (insertion), « D » pour delete (suppression), « UO » pour update old values (mise à jour des anciennes valeurs) et « UN » pour update new values (mise à jour des nouvelles valeurs).</span><span class="sxs-lookup"><span data-stu-id="59adf-171">The valid values for this field are as follows: 'I' for insert, 'D' for delete, 'UO' for update old values, and 'UN' for update new values.</span></span>  
  
-   <span data-ttu-id="59adf-172">Mettre à jour les indicateurs, lorsque vous les demandez, qui apparaissent sous la forme de colonnes de bits après le code d’opération et dans l’ordre spécifié dans le *@update_flag_list* paramètre.</span><span class="sxs-lookup"><span data-stu-id="59adf-172">Update flags, when you request them, that appear as bit columns after the operation code and in the order that is specified in the *@update_flag_list* parameter.</span></span> <span data-ttu-id="59adf-173">Ces colonnes sont nommées en ajoutant « _uflag » au nom de colonne associé.</span><span class="sxs-lookup"><span data-stu-id="59adf-173">These columns are named by appending '_uflag' to the associated column name.</span></span>  
  
 <span data-ttu-id="59adf-174">Si votre package appelle une fonction wrapper qui interroge toutes les modifications, elle retourne également les colonnes __CDC_STARTLSN et \__CDC_SEQVAL.</span><span class="sxs-lookup"><span data-stu-id="59adf-174">If your package calls a wrapper function that queries for all changes, the wrapper function also returns the columns, __CDC_STARTLSN and \__CDC_SEQVAL.</span></span> <span data-ttu-id="59adf-175">Ces deux colonnes deviennent les première et deuxième colonnes, respectivement, du jeu de résultats.</span><span class="sxs-lookup"><span data-stu-id="59adf-175">These two columns become the first and second columns, respectively, of the result set.</span></span> <span data-ttu-id="59adf-176">La fonction wrapper trie également le jeu de résultats en fonction de ces deux colonnes.</span><span class="sxs-lookup"><span data-stu-id="59adf-176">The wrapper function also sorts the result set based on these two columns.</span></span>  
  
## <a name="writing-your-own-table-value-function"></a><span data-ttu-id="59adf-177">Écriture de votre propre fonction table</span><span class="sxs-lookup"><span data-stu-id="59adf-177">Writing Your Own Table-Value Function</span></span>  
 <span data-ttu-id="59adf-178">Vous pouvez également utiliser [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] pour écrire votre propre fonction wrapper table qui appelle la fonction de requête de capture de données modifiées et qui stocke la fonction wrapper table dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="59adf-178">You can also use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to write your own table-valued wrapper function that calls the change data capture query function, and store the table-valued wrapper function in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="59adf-179">Pour plus d’informations sur la création d’une fonction Transact-SQL, consultez [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59adf-179">For more information about how to create a Transact-SQL function, see [CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql).</span></span>  
  
 <span data-ttu-id="59adf-180">L'exemple suivant définit une fonction table qui récupère les modifications d'une table Customer pour l'intervalle de modification spécifié.</span><span class="sxs-lookup"><span data-stu-id="59adf-180">The following example defines a table-valued function that retrieves changes from a Customer table for the specified change interval.</span></span> <span data-ttu-id="59adf-181">Cette fonction utilise des fonctions de capture de données modifiées pour mapper les valeurs `datetime` aux valeurs binaires de numéros séquentiels dans le journal que les tables de modifications utilisent en interne.</span><span class="sxs-lookup"><span data-stu-id="59adf-181">This function uses change data capture functions to map the `datetime` values to the binary log sequence number (LSN) values that the change tables use internally.</span></span> <span data-ttu-id="59adf-182">Cette fonction gère également plusieurs conditions spéciales :</span><span class="sxs-lookup"><span data-stu-id="59adf-182">This function also handles several special conditions:</span></span>  
  
-   <span data-ttu-id="59adf-183">Lorsqu'une valeur NULL est passée pour l'heure de début, cette fonction utilise la valeur correspondante à la première heure disponible.</span><span class="sxs-lookup"><span data-stu-id="59adf-183">When a null value is passed for the starting time, this function uses the earliest available value.</span></span>  
  
-   <span data-ttu-id="59adf-184">Lorsqu'une valeur NULL est passée pour l'heure de fin, cette fonction utilise la valeur correspondante à la dernière heure disponible.</span><span class="sxs-lookup"><span data-stu-id="59adf-184">When a null value is passed for the ending time, this function uses the latest available value.</span></span>  
  
-   <span data-ttu-id="59adf-185">Lorsque le numéro séquentiel dans le journal de début est égal au numéro séquentiel dans le journal de fin, ce qui indique habituellement qu'il n'y a pas d'enregistrements pour l'intervalle sélectionné, cette fonction se ferme.</span><span class="sxs-lookup"><span data-stu-id="59adf-185">When the starting LSN is equal to the ending LSN, which usually indicates that there are no records for the selected interval, this function exits.</span></span>  
  
### <a name="example-of-a-table-value-function-that-queries-for-change-data"></a><span data-ttu-id="59adf-186">Exemple d'une fonction table qui interroge les données modifiées</span><span class="sxs-lookup"><span data-stu-id="59adf-186">Example of a Table-Value Function that Queries for Change Data</span></span>  
  
```  
CREATE function CDCSample.uf_Customer (  
     @start_time datetime  
    ,@end_time datetime  
)  
returns @Customer table (  
     CustomerID int  
    ,TerritoryID int  
    ,CustomerType nchar(1)  
    ,rowguid uniqueidentifier  
    ,ModifiedDate datetime  
    ,CDC_OPERATION varchar(1)  
) as  
begin  
    declare @from_lsn binary(10), @to_lsn binary(10)  
  
    if (@start_time is null)  
        select @from_lsn = sys.fn_cdc_get_min_lsn('Customer')  
    else  
        select @from_lsn = sys.fn_cdc_increment_lsn(sys.fn_cdc_map_time_to_lsn('largest less than or equal',@start_time))  
  
    if (@end_time is null)  
        select @to_lsn = sys.fn_cdc_get_max_lsn()  
    else  
        select @to_lsn = sys.fn_cdc_map_time_to_lsn('largest less than or equal',@end_time)  
  
    if (@from_lsn = sys.fn_cdc_increment_lsn(@to_lsn))  
        return  
  
    -- Query for change data  
    insert into @Customer  
    select   
        CustomerID,      
        TerritoryID,   
        CustomerType,   
        rowguid,   
        ModifiedDate,   
        case __$operation  
                when 1 then 'D'  
                when 2 then 'I'  
                when 4 then 'U'  
                else null  
         end as CDC_OPERATION  
    from   
        cdc.fn_cdc_get_net_changes_Customer(@from_lsn, @to_lsn, 'all')  
  
    return  
end   
go  
  
```  
  
### <a name="retrieving-additional-metadata-with-the-change-data"></a><span data-ttu-id="59adf-187">Récupération de métadonnées supplémentaires avec les données modifiées</span><span class="sxs-lookup"><span data-stu-id="59adf-187">Retrieving Additional Metadata with the Change Data</span></span>  
 <span data-ttu-id="59adf-188">Même si la fonction table créée par l’utilisateur et présentée plus haut utilise uniquement la colonne **__$operation**, la fonction **cdc.fn_cdc_get_net_changes_<capture_instance>** renvoie quatre colonnes de métadonnées pour chaque ligne de modification.</span><span class="sxs-lookup"><span data-stu-id="59adf-188">Although the user-created table-valued function shown earlier uses only the **__$operation** column, the **cdc.fn_cdc_get_net_changes_<capture_instance>** function returns four columns of metadata for each change row.</span></span> <span data-ttu-id="59adf-189">Si vous souhaitez utiliser ces valeurs dans votre flux de données, vous pouvez les retourner en tant que colonnes supplémentaires à partir de la fonction wrapper table.</span><span class="sxs-lookup"><span data-stu-id="59adf-189">If you want to use these values in your data flow, you can return them as additional columns from the table-valued wrapper function.</span></span>  
  
|<span data-ttu-id="59adf-190">Nom de la colonne</span><span class="sxs-lookup"><span data-stu-id="59adf-190">Column name</span></span>|<span data-ttu-id="59adf-191">Type de données</span><span class="sxs-lookup"><span data-stu-id="59adf-191">Data type</span></span>|<span data-ttu-id="59adf-192">Description</span><span class="sxs-lookup"><span data-stu-id="59adf-192">Description</span></span>|  
|-----------------|---------------|-----------------|  
|<span data-ttu-id="59adf-193">**__$start_lsn**</span><span class="sxs-lookup"><span data-stu-id="59adf-193">**__$start_lsn**</span></span>|`binary(10)`|<span data-ttu-id="59adf-194">Numéro séquentiel dans le journal associé à la transaction de validation de la modification.</span><span class="sxs-lookup"><span data-stu-id="59adf-194">LSN associated with the commit transaction for the change.</span></span><br /><br /> <span data-ttu-id="59adf-195">Toutes les modifications validées dans la même transaction partagent le même numéro séquentiel dans le journal de validation.</span><span class="sxs-lookup"><span data-stu-id="59adf-195">All changes committed in the same transaction share the same commit LSN.</span></span> <span data-ttu-id="59adf-196">Par exemple, si une opération de mise à jour sur la table source modifie deux lignes différentes, la table de modifications contient quatre lignes (deux avec les anciennes valeurs et deux avec les nouvelles valeurs), chacune avec la même valeur **__$start_lsn** .</span><span class="sxs-lookup"><span data-stu-id="59adf-196">For example, if an update operation on the source table modifies two different rows, the change table will contain four rows (two with the old values and two with the new values), each with the same **__$start_lsn** value.</span></span>|  
|<span data-ttu-id="59adf-197">**__$seqval**</span><span class="sxs-lookup"><span data-stu-id="59adf-197">**__$seqval**</span></span>|`binary(10)`|<span data-ttu-id="59adf-198">Valeur de classement utilisée pour classer les modifications de ligne dans une transaction.</span><span class="sxs-lookup"><span data-stu-id="59adf-198">Sequence value that is used to order the row changes in a transaction.</span></span>|  
|<span data-ttu-id="59adf-199">**__$operation**</span><span class="sxs-lookup"><span data-stu-id="59adf-199">**__$operation**</span></span>|`int`|<span data-ttu-id="59adf-200">Opération de langage de manipulation de données associée à la modification.</span><span class="sxs-lookup"><span data-stu-id="59adf-200">The data manipulation language (DML) operation associated with the change.</span></span> <span data-ttu-id="59adf-201">Il peut s'agir d'une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="59adf-201">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="59adf-202">1 = suppression</span><span class="sxs-lookup"><span data-stu-id="59adf-202">1 = delete</span></span><br /><br /> <span data-ttu-id="59adf-203">2 = insertion</span><span class="sxs-lookup"><span data-stu-id="59adf-203">2 = insert</span></span><br /><br /> <span data-ttu-id="59adf-204">3 = mise à jour (valeurs avant l'opération de mise à jour)</span><span class="sxs-lookup"><span data-stu-id="59adf-204">3 = update (Values before the update operation.)</span></span><br /><br /> <span data-ttu-id="59adf-205">4 = mise à jour (valeurs après l'opération de mise à jour)</span><span class="sxs-lookup"><span data-stu-id="59adf-205">4 = update (Values after the update operation.)</span></span>|  
|<span data-ttu-id="59adf-206">**__$update_mask**</span><span class="sxs-lookup"><span data-stu-id="59adf-206">**__$update_mask**</span></span>|`varbinary(128)`|<span data-ttu-id="59adf-207">Masque de bits basé sur les ordinaux de colonne de la table de modifications identifiant les colonnes modifiées.</span><span class="sxs-lookup"><span data-stu-id="59adf-207">A bitmask that is based on the column ordinals of the change table identifying those columns that changed.</span></span> <span data-ttu-id="59adf-208">Vous pouvez examiner cette valeur pour déterminer les colonnes qui ont été modifiées.</span><span class="sxs-lookup"><span data-stu-id="59adf-208">You could examine this value if you had to determine which columns have changed.</span></span>|  
|**\<captured source table columns>**|<span data-ttu-id="59adf-209">varie</span><span class="sxs-lookup"><span data-stu-id="59adf-209">varies</span></span>|<span data-ttu-id="59adf-210">Les colonnes restantes retournées par la fonction sont les colonnes de la table source qui ont été identifiées comme colonnes capturées lorsque l'instance de capture a été créée.</span><span class="sxs-lookup"><span data-stu-id="59adf-210">The remaining columns returned by the function are the columns from the source table that were identified as captured columns when the capture instance was created.</span></span> <span data-ttu-id="59adf-211">Si aucune colonne n'a été spécifiée à l'origine dans la liste des colonnes capturées, toutes les colonnes de la table source sont retournées.</span><span class="sxs-lookup"><span data-stu-id="59adf-211">If no columns were originally specified in the captured column list, all columns in the source table are returned.</span></span>|  
  
 <span data-ttu-id="59adf-212">Pour plus d’informations, consultez [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="59adf-212">For more information, see [cdc.fn_cdc_get_net_changes_&#60;capture_instance&#62; &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/cdc-fn-cdc-get-net-changes-capture-instance-transact-sql).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="59adf-213">étape suivante</span><span class="sxs-lookup"><span data-stu-id="59adf-213">Next Step</span></span>  
 <span data-ttu-id="59adf-214">Après avoir créé la fonction table qui interroge les données modifiées, l'étape suivante consiste à commencer à concevoir le flux de données dans le package.</span><span class="sxs-lookup"><span data-stu-id="59adf-214">After you have created the table-valued function that queries for change data, the next step is to start designing the data flow in the package.</span></span>  
  
 <span data-ttu-id="59adf-215">**Rubrique suivante :** [Récupérer et comprendre les données modifiées](retrieve-and-understand-the-change-data.md)</span><span class="sxs-lookup"><span data-stu-id="59adf-215">**Next topic:** [Retrieve and Understand the Change Data](retrieve-and-understand-the-change-data.md)</span></span>  
  
  
