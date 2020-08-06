---
title: Définir les valeurs des paramètres après le déploiement du projet | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c9dcca4d-f1a0-45ec-b078-f4d372589baf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 39572594e429b61de0641c6e6929e84105138f1f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709752"
---
# <a name="set-parameter-values-after-the-project-is-deployed"></a><span data-ttu-id="e98e5-102">Définir des valeurs de paramètres après le déploiement du projet</span><span class="sxs-lookup"><span data-stu-id="e98e5-102">Set Parameter Values After the Project Is Deployed</span></span>
  <span data-ttu-id="e98e5-103">L'Assistant Déploiement vous permet de définir des valeurs de paramètre par défaut du serveur lorsque vous déployez votre projet dans le catalogue.</span><span class="sxs-lookup"><span data-stu-id="e98e5-103">The Deployment Wizard allows you to set server default parameter values when you deploy your project to the catalog.</span></span> <span data-ttu-id="e98e5-104">Une fois votre projet dans le catalogue, vous pouvez utiliser l'Explorateur d'objets SQL Server Management Studio (SSMS) ou Transact-SQL pour définir les valeurs par défaut du serveur.</span><span class="sxs-lookup"><span data-stu-id="e98e5-104">After your project is in the catalog, you can use SQL Server Management Studio (SSMS) Object Explorer or Transact-SQL to set server default values.</span></span>  
  
### <a name="to-set-server-defaults-with-ssms-object-explorer"></a><span data-ttu-id="e98e5-105">Pour définir les valeurs par défaut du serveur avec l'Explorateur d'objets SSMS :</span><span class="sxs-lookup"><span data-stu-id="e98e5-105">To set server defaults with SSMS Object Explorer:</span></span>  
  
1.  <span data-ttu-id="e98e5-106">Sélectionnez le projet sous le nœud **Integration Services**, puis cliquez dessus avec le bouton droit.</span><span class="sxs-lookup"><span data-stu-id="e98e5-106">Select and right-click the project under the **Integration Services** node.</span></span>  
  
2.  <span data-ttu-id="e98e5-107">Cliquez sur **Propriétés** pour ouvrir la fenêtre de dialogue **Propriétés du projet** .</span><span class="sxs-lookup"><span data-stu-id="e98e5-107">Click **Properties** to open the **Project Properties** dialog window.</span></span>  
  
3.  <span data-ttu-id="e98e5-108">Ouvrez la page des paramètres en cliquant sur **Paramètres** sous **Sélectionner une page**.</span><span class="sxs-lookup"><span data-stu-id="e98e5-108">Open the parameters page by clicking **Parameters** under **Select a page**.</span></span>  
  
4.  <span data-ttu-id="e98e5-109">Sélectionnez le paramètre souhaité dans la liste **Paramètres** .</span><span class="sxs-lookup"><span data-stu-id="e98e5-109">Select the desired parameter in the **Parameters** list.</span></span> <span data-ttu-id="e98e5-110">Remarque : la colonne **Conteneur** permet de faire la distinction entre les paramètres du projet et les paramètres du package.</span><span class="sxs-lookup"><span data-stu-id="e98e5-110">Note: The **Container** column helps distinguish project parameters from package parameters.</span></span>  
  
5.  <span data-ttu-id="e98e5-111">Dans la colonne **Valeur** , spécifiez la valeur de paramètre du serveur par défaut souhaitée.</span><span class="sxs-lookup"><span data-stu-id="e98e5-111">In the **Value** column, specify the desired server default parameter value.</span></span>  
  
 <span data-ttu-id="e98e5-112">Pour définir les paramètres par défaut du serveur avec Transact-SQL, utilisez la procédure stockée [catalog.set_object_parameter_value &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="e98e5-112">To set server defaults with Transact-SQL, use the [catalog.set_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-set-object-parameter-value-ssisdb-database) stored procedure.</span></span> <span data-ttu-id="e98e5-113">Pour afficher les valeurs par défaut actuelles du serveur, interrogez la vue [catalog.object_parameters &#40;base de données SSISDB&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="e98e5-113">To view current server defaults, query the [catalog.object_parameters &#40;SSISDB Database&#41;](/sql/integration-services/system-views/catalog-object-parameters-ssisdb-database) view.</span></span> <span data-ttu-id="e98e5-114">Pour effacer une valeur par défaut du serveur, utilisez la procédure stockée [catalog.clear_object_parameter_value &#40;base de données SSISDB&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database).</span><span class="sxs-lookup"><span data-stu-id="e98e5-114">To clear a server default value, use the [catalog.clear_object_parameter_value &#40;SSISDB Database&#41;](/sql/integration-services/system-stored-procedures/catalog-clear-object-parameter-value-ssisdb-database) stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e98e5-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e98e5-115">See Also</span></span>  
 [<span data-ttu-id="e98e5-116">Paramètres de&#41; Integration Services &#40;SSIS</span><span class="sxs-lookup"><span data-stu-id="e98e5-116">Integration Services &#40;SSIS&#41; Parameters</span></span>](integration-services-ssis-package-and-project-parameters.md)  
  
  
