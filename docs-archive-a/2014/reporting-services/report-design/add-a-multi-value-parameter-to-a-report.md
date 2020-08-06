---
title: Ajouter un paramètre à valeurs multiples sur un rapport | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 12ad0e77-4c28-4bbb-ab11-473ae89ec9f1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5269293b6a21f3b1d82eb6835efbd275e3be9620
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696439"
---
# <a name="add-a-multi-value-parameter-to-a-report"></a><span data-ttu-id="c4e65-102">Ajouter un paramètre à valeurs multiples sur un rapport</span><span class="sxs-lookup"><span data-stu-id="c4e65-102">Add a multi-value parameter to a Report</span></span>
  <span data-ttu-id="c4e65-103">Il est possible d'ajouter à un rapport un paramètre qui permet à l'utilisateur de sélectionner plus d'une valeur pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="c4e65-103">You can add a parameter to a report that allows the user to select more than one value for the parameter.</span></span>  
  
 <span data-ttu-id="c4e65-104">Il est possible de passer un paramètre à valeurs multiples dans le rapport, dans son URL.</span><span class="sxs-lookup"><span data-stu-id="c4e65-104">You can pass multiple parameter values to the report within the report URL.</span></span> <span data-ttu-id="c4e65-105">Pour obtenir un exemple d’URL contenant un paramètre à valeurs multiples, consultez [Passer un paramètre de rapport dans une URL](../pass-a-report-parameter-within-a-url.md).</span><span class="sxs-lookup"><span data-stu-id="c4e65-105">For a URL example includes a multi-value parameter, see [Pass a Report Parameter Within a URL](../pass-a-report-parameter-within-a-url.md).</span></span>  
  
 <span data-ttu-id="c4e65-106">Pour plus d’informations sur la façon de passer un paramètre à valeurs multiples dans une procédure stockée, consultez [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) sur le site mssqltips.com.</span><span class="sxs-lookup"><span data-stu-id="c4e65-106">For information on how to pass multiple parameter values to a stored procedure, see [Working With Multi-Select Parameters for SSRS Reports](https://go.microsoft.com/fwlink/?LinkId=321529) on mssqltips.com.</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="c4e65-107">Pour ajouter un paramètre à valeurs multiples</span><span class="sxs-lookup"><span data-stu-id="c4e65-107">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="c4e65-108">Dans le Générateur de rapports, ouvrez le rapport auquel vous souhaitez ajouter le paramètre à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="c4e65-108">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="c4e65-109">Cliquez avec le bouton droit sur le dataset du rapport, puis cliquez sur **Propriétés du dataset**.</span><span class="sxs-lookup"><span data-stu-id="c4e65-109">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="c4e65-110">Ajoutez une variable à la requête du dataset en modifiant le texte de la requête dans la zone **Requête** ou en ajoutant un filtre à l’aide du concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="c4e65-110">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="c4e65-111">Pour plus d’informations, consultez [Générer une requête dans le Concepteur de requêtes relationnelles &#40;Générateur de rapports et SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c4e65-111">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4e65-112">Le texte de la requête ne doit pas inclure l'instruction DECLARE pour la variable de requête.</span><span class="sxs-lookup"><span data-stu-id="c4e65-112">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4e65-113">Le texte de la variable de la requête doit inclure l'opérateur `IN`, comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="c4e65-113">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4e65-114">Si vous n’incluez pas les parenthèses autour de la variable comme indiqué ci-dessus, le rendu du rapport échoue et l’erreur « la variable scalaire doit être déclarée » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c4e65-114">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="c4e65-115">Un paramètre de dataset pour un dataset incorporé ou partagé est créé automatiquement pour la variable de la requête.</span><span class="sxs-lookup"><span data-stu-id="c4e65-115">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="c4e65-116">Un paramètre de rapport est créé automatiquement pour le paramètre du dataset.</span><span class="sxs-lookup"><span data-stu-id="c4e65-116">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="c4e65-117">Dans le volet **Données du rapport** , développez le nœud **Paramètres** , cliquez avec le bouton droit sur le paramètre de rapport créé automatiquement pour le paramètre de dataset, puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="c4e65-117">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="c4e65-118">Pour autoriser un utilisateur à sélectionner plusieurs valeurs pour le paramètre, sélectionnez **Autoriser les valeurs multiples** l’onglet **Général** .</span><span class="sxs-lookup"><span data-stu-id="c4e65-118">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="c4e65-119">(Facultatif) Sous l’onglet **Valeurs disponibles** , spécifiez la liste des valeurs disponibles visibles par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c4e65-119">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="c4e65-120">Une liste de valeurs disponibles limite les choix qu'un utilisateur peut faire aux valeurs valides pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="c4e65-120">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="c4e65-121">Le haut de liste commence par une fonctionnalité **Sélectionner tout** afin que l’utilisateur puisse sélectionner ou effacer toutes les valeurs d’un simple clic.</span><span class="sxs-lookup"><span data-stu-id="c4e65-121">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="c4e65-122">Si vous choisissez d'obtenir les valeurs disponibles pour le paramètre de rapport à partir d'une requête de dataset, assurez-vous de sélectionner un dataset qui ne contient pas la variable de requête associée au même paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="c4e65-122">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="c4e65-123">Pour plus d’informations, consultez [Ajouter, modifier ou supprimer les valeurs disponibles d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="c4e65-123">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
### <a name="to-add-a-multi-value-parameter"></a><span data-ttu-id="c4e65-124">Pour ajouter un paramètre à valeurs multiples</span><span class="sxs-lookup"><span data-stu-id="c4e65-124">To add a multi-value parameter</span></span>  
  
1.  <span data-ttu-id="c4e65-125">Dans le Générateur de rapports, ouvrez le rapport auquel vous souhaitez ajouter le paramètre à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="c4e65-125">In Report Builder, open the report that you want to add the multi-value parameter to.</span></span>  
  
2.  <span data-ttu-id="c4e65-126">Cliquez avec le bouton droit sur le dataset du rapport, puis cliquez sur **Propriétés du dataset**.</span><span class="sxs-lookup"><span data-stu-id="c4e65-126">Right-click the report dataset, and then click **Dataset Properties**</span></span>  
  
3.  <span data-ttu-id="c4e65-127">Ajoutez une variable à la requête du dataset en modifiant le texte de la requête dans la zone **Requête** ou en ajoutant un filtre à l’aide du concepteur de requêtes.</span><span class="sxs-lookup"><span data-stu-id="c4e65-127">Add a variable to the dataset query by either editing the query text in the **Query** box, or by adding a filter by using the query designer.</span></span> <span data-ttu-id="c4e65-128">Pour plus d’informations, consultez [Générer une requête dans le Concepteur de requêtes relationnelles &#40;Générateur de rapports et SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c4e65-128">For more information, see [Build a Query in the Relational Query Designer &#40;Report Builder and SSRS&#41;](../report-data/build-a-query-in-the-relational-query-designer-report-builder-and-ssrs.md).</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4e65-129">Le texte de la requête ne doit pas inclure l'instruction DECLARE pour la variable de requête.</span><span class="sxs-lookup"><span data-stu-id="c4e65-129">The query text must not include the DECLARE statement for the query variable.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4e65-130">Le texte de la variable de la requête doit inclure l'opérateur `IN`, comme indiqué dans l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="c4e65-130">The text for the query variable must include the `IN` operator, as shown in the following example.</span></span>  
  
    ```  
    WHERE  
      Production.ProductInventory.ProductID IN (@ProductID)  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c4e65-131">Si vous n’incluez pas les parenthèses autour de la variable comme indiqué ci-dessus, le rendu du rapport échoue et l’erreur « la variable scalaire doit être déclarée » s’affiche.</span><span class="sxs-lookup"><span data-stu-id="c4e65-131">If you don't include the parentheses around the variable as shown above, the report fails to render and the "must declare the scalar variable" error is displayed.</span></span>  
  
     <span data-ttu-id="c4e65-132">Un paramètre de dataset pour un dataset incorporé ou partagé est créé automatiquement pour la variable de la requête.</span><span class="sxs-lookup"><span data-stu-id="c4e65-132">A dataset parameter for an embedded dataset or a shared dataset is created automatically for the query variable.</span></span> <span data-ttu-id="c4e65-133">Un paramètre de rapport est créé automatiquement pour le paramètre du dataset.</span><span class="sxs-lookup"><span data-stu-id="c4e65-133">A report parameter is created automatically for the dataset parameter.</span></span>  
  
4.  <span data-ttu-id="c4e65-134">Dans le volet **Données du rapport** , développez le nœud **Paramètres** , cliquez avec le bouton droit sur le paramètre de rapport créé automatiquement pour le paramètre de dataset, puis cliquez sur **Propriétés du paramètre**.</span><span class="sxs-lookup"><span data-stu-id="c4e65-134">In the **Report Data** pane, expand the **Parameters** node, right-click the report parameter that was automatically created for the dataset parameter, and then click **Parameter Properties**.</span></span>  
  
5.  <span data-ttu-id="c4e65-135">Pour autoriser un utilisateur à sélectionner plusieurs valeurs pour le paramètre, sélectionnez **Autoriser les valeurs multiples** l’onglet **Général** .</span><span class="sxs-lookup"><span data-stu-id="c4e65-135">In the **General** tab, select **Allow multiple values** to allow a user to select more than one value for the parameter.</span></span>  
  
6.  <span data-ttu-id="c4e65-136">(Facultatif) Sous l’onglet **Valeurs disponibles** , spécifiez la liste des valeurs disponibles visibles par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c4e65-136">(Optionally) In the **Available** values tab, specify a list of available values to display to the user.</span></span>  
  
     <span data-ttu-id="c4e65-137">Une liste de valeurs disponibles limite les choix qu'un utilisateur peut faire aux valeurs valides pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="c4e65-137">An available values list limits the choices a user can make to only valid values for the parameter.</span></span> <span data-ttu-id="c4e65-138">Le haut de liste commence par une fonctionnalité **Sélectionner tout** afin que l’utilisateur puisse sélectionner ou effacer toutes les valeurs d’un simple clic.</span><span class="sxs-lookup"><span data-stu-id="c4e65-138">For multiple values, the top of list begins with a **Select All** feature so the user can select or clear all values with a single click.</span></span> <span data-ttu-id="c4e65-139">Si vous choisissez d'obtenir les valeurs disponibles pour le paramètre de rapport à partir d'une requête de dataset, assurez-vous de sélectionner un dataset qui ne contient pas la variable de requête associée au même paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="c4e65-139">If you choose to get the available values for the report parameter from a dataset query, be sure to select a dataset that does not contain the query variable that is associated with the same report parameter.</span></span>  
  
     <span data-ttu-id="c4e65-140">Pour plus d’informations, consultez [Ajouter, modifier ou supprimer les valeurs disponibles d’un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span><span class="sxs-lookup"><span data-stu-id="c4e65-140">For more information, see [Add, Change, or Delete Available Values for a Report Parameter &#40;Report Builder and SSRS&#41;](add-change-or-delete-available-values-for-a-report-parameter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e65-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4e65-141">See Also</span></span>  
 <span data-ttu-id="c4e65-142">[Ajouter des paramètres en cascade à un rapport &#40;Générateur de rapports et SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c4e65-142">[Add Cascading Parameters to a Report &#40;Report Builder and SSRS&#41;](add-cascading-parameters-to-a-report-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="c4e65-143">Ajouter, modifier ou supprimer un paramètre de rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c4e65-143">Add, Change, or Delete a Report Parameter &#40;Report Builder and SSRS&#41;</span></span>](add-change-or-delete-a-report-parameter-report-builder-and-ssrs.md)  
  
  
