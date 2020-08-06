---
title: Associer un paramètre de requête à un paramètre de rapport (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- queries [Reporting Services], parameters
- parameters [Reporting Services], queries
ms.assetid: 6d297e1a-ff71-472a-addc-349e863092b5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f65aa36e8910378d68963c8c9990518b661025ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697575"
---
# <a name="associate-a-query-parameter-with-a-report-parameter-report-builder-and-ssrs"></a><span data-ttu-id="6ad73-102">Associer un paramètre de requête à un paramètre de rapport (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="6ad73-102">Associate a Query Parameter with a Report Parameter (Report Builder and SSRS)</span></span>
  <span data-ttu-id="6ad73-103">Lorsque vous définissez une requête de dataset qui contient une variable de requête, la commande de requête est analysée.</span><span class="sxs-lookup"><span data-stu-id="6ad73-103">When you define a dataset query that contains a query variable, the query command is parsed.</span></span> <span data-ttu-id="6ad73-104">Pour chaque variable de requête, un paramètre de dataset et un paramètre de rapport correspondants sont créés.</span><span class="sxs-lookup"><span data-stu-id="6ad73-104">For each query variable, a corresponding dataset parameter and report parameter are created.</span></span> <span data-ttu-id="6ad73-105">Le paramètre de dataset, à son tour, pointe aussi sur le paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="6ad73-105">The dataset parameter points to the report parameter.</span></span> <span data-ttu-id="6ad73-106">Cela permet à un utilisateur d'entrer une valeur qui passe directement à la requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-106">This enables a user to enter a value that passes directly to the query.</span></span> <span data-ttu-id="6ad73-107">Chaque fois que vous modifiez la commande de requête, le même processus a lieu.</span><span class="sxs-lookup"><span data-stu-id="6ad73-107">Each time you edit the query command, the same process takes place.</span></span>  
  
 <span data-ttu-id="6ad73-108">Si vous renommez un paramètre de rapport qui est lié à un paramètre de requête, vous devez lier manuellement les paramètres de requête au paramètre de rapport renommé à l'aide de la procédure de cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="6ad73-108">If you rename a report parameter that is bound to a query parameter, you need to manually link the query parameters to the renamed report parameter by using the procedure in this topic.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-associate-a-query-parameter-with-a-report-parameter"></a><span data-ttu-id="6ad73-109">Pour associer un paramètre de requête à un paramètre de rapport</span><span class="sxs-lookup"><span data-stu-id="6ad73-109">To associate a query parameter with a report parameter</span></span>  
  
1.  <span data-ttu-id="6ad73-110">Dans le volet Données du rapport, cliquez avec le bouton droit sur le dataset, cliquez sur **Propriétés du dataset**, puis sur **Paramètres**.</span><span class="sxs-lookup"><span data-stu-id="6ad73-110">In the Report Data pane, right-click the dataset, click **Dataset Properties**, and then click **Parameters**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="6ad73-111"> Si le volet des données de rapport n’est pas visible, cliquez sur l’option **Données du rapport** du menu **Affichage** .</span><span class="sxs-lookup"><span data-stu-id="6ad73-111">If the Report Data pane is not visible, click **Report Data** on the **View** menu.</span></span>  
  
2.  <span data-ttu-id="6ad73-112">Dans la colonne **Nom du paramètre**, recherchez le nom du paramètre de requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-112">In the column **Parameter Name**, find the name of the query parameter.</span></span> <span data-ttu-id="6ad73-113">Les noms de paramètres sont automatiquement renseignés en fonction de la requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-113">Parameter names are automatically populated based on the query.</span></span> <span data-ttu-id="6ad73-114">Chaque fois que vous modifiez la requête, la requête est examinée à la recherche de nouveaux paramètres de requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-114">Every time you change the query, the query is checked for new query parameters.</span></span> <span data-ttu-id="6ad73-115">Les paramètres de requête que vous créez manuellement ne sont pas modifiés lorsque la requête change.</span><span class="sxs-lookup"><span data-stu-id="6ad73-115">Query parameters that you create manually are not changed when the query changes.</span></span>  
  
    -   <span data-ttu-id="6ad73-116">Dans **Nom du paramètre**, recherchez le nom du paramètre de requête tel qu’il existe dans la requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-116">In **Parameter Name**, find the query parameter name as it exists in the query.</span></span> <span data-ttu-id="6ad73-117">Vous pouvez également ajouter manuellement un nouveau paramètre de requête et entrer un nom.</span><span class="sxs-lookup"><span data-stu-id="6ad73-117">You can also manually add a new query parameter and enter a name.</span></span>  
  
    -   <span data-ttu-id="6ad73-118">Dans **Valeur du paramètre**, tapez ou sélectionnez une expression qui correspond à la valeur à passer au paramètre de requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-118">In **Parameter Value**, type or select an expression that evaluates to the value to pass to the query parameter.</span></span> <span data-ttu-id="6ad73-119">Il s'agit en général du nom du paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="6ad73-119">This is typically the name of the report parameter.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="6ad73-120">Vous n'êtes pas limité aux paramètres de rapport comme valeurs pour les paramètres de requête.</span><span class="sxs-lookup"><span data-stu-id="6ad73-120">You are not limited to report parameters as values for a query parameter.</span></span> <span data-ttu-id="6ad73-121">Vous pouvez utiliser n'importe quelle expression qui correspond à une valeur possible pour les paramètres.</span><span class="sxs-lookup"><span data-stu-id="6ad73-121">You can use any expression that evaluates to a value for the parameter value.</span></span>  
  
3.  <span data-ttu-id="6ad73-122">Répétez l'étape 2 pour indiquer des paramètres de requête supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="6ad73-122">Repeat step 2 for additional query parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ad73-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ad73-123">See Also</span></span>  
 <span data-ttu-id="6ad73-124">[Datasets incorporés dans le rapport et datasets partagés &#40;Générateur de rapports et SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6ad73-124">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6ad73-125">Concept des paramètres de rapport &#40;Générateur de rapports et SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="6ad73-125">Report Parameters Concept &#40;Report Builder and SSRS&#41;</span></span>](../report-design/report-parameters-concepts-report-builder-and-ssrs.md)  
  
  
