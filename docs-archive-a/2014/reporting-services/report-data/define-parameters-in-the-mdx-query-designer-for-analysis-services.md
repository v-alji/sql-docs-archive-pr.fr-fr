---
title: Définir des paramètres dans le concepteur de requêtes MDX pour Analysis Services (Générateur de rapports et SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6b2b05fc0122eb25a7a0799f7b47b1b99486a28c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710248"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a><span data-ttu-id="13ec0-102">Définir des paramètres dans le Concepteur de requêtes MDX pour Analysis Services (Générateur de rapports et SSRS)</span><span class="sxs-lookup"><span data-stu-id="13ec0-102">Define Parameters in the MDX Query Designer for Analysis Services (Report Builder and SSRS)</span></span>
  <span data-ttu-id="13ec0-103">Pour paramétrer une requête MDX pour une source de données [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , vous devez ajouter un paramètre de requête à la requête.</span><span class="sxs-lookup"><span data-stu-id="13ec0-103">To parameterize an MDX query for an [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source, you must add a query parameter to the query.</span></span> <span data-ttu-id="13ec0-104">Dans le Concepteur de requêtes MDX, vous pouvez ajouter un paramètre de requête à la fois en mode Création et en mode Requête en spécifiant un filtre.</span><span class="sxs-lookup"><span data-stu-id="13ec0-104">In the MDX query designer, you can add a query parameter in both Design mode and Query mode by specifying a filter.</span></span> <span data-ttu-id="13ec0-105">Après avoir défini la requête avec un paramètre de requête, Reporting Services crée automatiquement un paramètre de rapport et un dataset pour fournir la liste des valeurs valides.</span><span class="sxs-lookup"><span data-stu-id="13ec0-105">After you define the query with a query parameter, Reporting Services automatically creates a report parameter and a dataset to provide the list of valid values.</span></span> <span data-ttu-id="13ec0-106">Cela permet à un utilisateur de spécifier une valeur transmise directement à la requête.</span><span class="sxs-lookup"><span data-stu-id="13ec0-106">This enables a user to specify a value that is passed directly to the query.</span></span>

> [!NOTE]
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]

### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a><span data-ttu-id="13ec0-107">Pour définir un paramètre de requête dans MDX en mode Création</span><span class="sxs-lookup"><span data-stu-id="13ec0-107">To define a query parameter in MDX in Design mode</span></span>

1.  <span data-ttu-id="13ec0-108">Dans le volet Données du rapport, cliquez avec le bouton droit sur un dataset créé à partir d’un type de source de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], puis cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="13ec0-108">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="13ec0-109">Le Concepteur de requêtes MDX s'ouvre en mode Création.</span><span class="sxs-lookup"><span data-stu-id="13ec0-109">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="13ec0-110">Faites glisser une dimension vers la zone de filtre et placez-la sur la première cellule de la colonne **Dimension** .</span><span class="sxs-lookup"><span data-stu-id="13ec0-110">Drag a dimension to the filter area and drop it on the first cell in the **Dimension** column.</span></span>

3.  <span data-ttu-id="13ec0-111">Dans la colonne **Hiérarchie** , choisissez une valeur dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13ec0-111">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

4.  <span data-ttu-id="13ec0-112">Dans la colonne **Opérateur** , choisissez un opérateur pour la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13ec0-112">In the **Operator** column, choose an operator for the drop-down list.</span></span>

5.  <span data-ttu-id="13ec0-113">Dans la colonne **Expression de filtre** , sélectionnez des valeurs individuelles dans la liste déroulante ou cliquez sur le membre **All** pour choisir toutes les valeurs.</span><span class="sxs-lookup"><span data-stu-id="13ec0-113">In the **Filter Expression** column, select individual values from the drop-down list, or click the **All** member to choose all values.</span></span>

6.  <span data-ttu-id="13ec0-114">Dans la colonne **Paramètres** , activez la case à cocher pour créer un paramètre de rapport.</span><span class="sxs-lookup"><span data-stu-id="13ec0-114">In the **Parameters** column, select the check box to create a report parameter.</span></span>

7.  <span data-ttu-id="13ec0-115">Cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="13ec0-115">Click **Run**.</span></span>

     <span data-ttu-id="13ec0-116">Après avoir exécuté la requête, cliquez sur **Création** dans la barre d'outils pour basculer en mode Requête et afficher la requête MDX créée.</span><span class="sxs-lookup"><span data-stu-id="13ec0-116">After you run the query, click **Design** on the toolbar to toggle to Query mode to view the MDX query that was created.</span></span> <span data-ttu-id="13ec0-117">Ne modifiez pas le texte de la requête en mode Requête si vous souhaitez continuer à utiliser le mode Création pour développer la requête.</span><span class="sxs-lookup"><span data-stu-id="13ec0-117">Do not change the query text in Query mode if you want to continue to use Design mode to develop the query.</span></span> <span data-ttu-id="13ec0-118">Pour rebasculer en mode Création, cliquez sur **Création** .</span><span class="sxs-lookup"><span data-stu-id="13ec0-118">Click **Design** to toggle back to Design mode.</span></span>

8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="13ec0-119">Dans le volet des données de rapport, développez le nœud Paramètres pour afficher le paramètre de rapport créé automatiquement pour le filtre.</span><span class="sxs-lookup"><span data-stu-id="13ec0-119">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="13ec0-120">Pour afficher le dataset qui fournit des valeurs disponibles pour le paramètre de rapport, cliquez avec le bouton droit sur tout espace vide dans le volet des données de rapport, puis cliquez sur **Afficher les datasets masqués**.</span><span class="sxs-lookup"><span data-stu-id="13ec0-120">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="13ec0-121">Le volet des données de rapport affiche tous les datasets dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="13ec0-121">The Report Data pane displays all datasets in the report.</span></span>

### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a><span data-ttu-id="13ec0-122">Pour définir un paramètre de requête dans MDX en mode Requête</span><span class="sxs-lookup"><span data-stu-id="13ec0-122">To define a query parameter in MDX in Query mode</span></span>

1.  <span data-ttu-id="13ec0-123">Dans le volet Données du rapport, cliquez avec le bouton droit sur un dataset créé à partir d’un type de source de données [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)], puis cliquez sur **Requête**.</span><span class="sxs-lookup"><span data-stu-id="13ec0-123">In the Report Data pane, right-click on a dataset created from a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] data source type, and then click **Query**.</span></span> <span data-ttu-id="13ec0-124">Le Concepteur de requêtes MDX s'ouvre en mode Création.</span><span class="sxs-lookup"><span data-stu-id="13ec0-124">The MDX query designer opens in Design mode.</span></span>

2.  <span data-ttu-id="13ec0-125">Dans la barre d'outils, cliquez sur **Création** pour passer au mode Requête.</span><span class="sxs-lookup"><span data-stu-id="13ec0-125">On the toolbar, click **Design** to toggle to Query mode.</span></span>

3.  <span data-ttu-id="13ec0-126">Dans la barre d’outils du Concepteur de requêtes MDX, cliquez sur **Paramètres de la requête** (![Icône de la boîte de dialogue Paramètres de la requête](../../analysis-services/media/iconqueryparameter.gif "Icône de la boîte de dialogue Paramètres de la requête")).</span><span class="sxs-lookup"><span data-stu-id="13ec0-126">On the MDX query designer toolbar, click **Query Parameters** (![Icon for the Query Parameters dialog box](../../analysis-services/media/iconqueryparameter.gif "Icon for the Query Parameters dialog box")).</span></span> <span data-ttu-id="13ec0-127">La boîte de dialogue Paramètres de la requête s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="13ec0-127">The Query Parameters dialog box opens.</span></span>

4.  <span data-ttu-id="13ec0-128">Dans la colonne **paramètre** , cliquez sur **\<Enter Parameter>** , puis tapez le nom d’un paramètre.</span><span class="sxs-lookup"><span data-stu-id="13ec0-128">In the **Parameter** column, click **\<Enter Parameter>**, and then type the name of a parameter.</span></span>

5.  <span data-ttu-id="13ec0-129">Dans la colonne **Dimension** , choisissez une valeur dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13ec0-129">In the **Dimension** column, choose a value from the drop-down list.</span></span>

6.  <span data-ttu-id="13ec0-130">Dans la colonne **Hiérarchie** , choisissez une valeur dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="13ec0-130">In the **Hierarchy** column, choose a value from the drop-down list.</span></span>

7.  <span data-ttu-id="13ec0-131">Dans la colonne **Valeurs multiples** , activez la case à cocher pour créer un paramètre à valeurs multiples.</span><span class="sxs-lookup"><span data-stu-id="13ec0-131">In the **Multiple values** column, select the check box to create a multivalue parameter.</span></span>

8.  <span data-ttu-id="13ec0-132">Dans la colonne **Par défaut** , dans la liste déroulante, sélectionnez une valeur unique ou plusieurs valeurs selon votre choix de l’étape 5.</span><span class="sxs-lookup"><span data-stu-id="13ec0-132">In the **Default** column, from the drop-down list, select a single value or multiple values depending on your choice in step 5.</span></span>

9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

10. <span data-ttu-id="13ec0-133">Dans la barre d'outils du Concepteur de requêtes, cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="13ec0-133">On the query designer toolbar, click **Run**.</span></span>

11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]

     <span data-ttu-id="13ec0-134">Dans le volet des données de rapport, développez le nœud Paramètres pour afficher le paramètre de rapport créé automatiquement pour le filtre.</span><span class="sxs-lookup"><span data-stu-id="13ec0-134">In the Report Data pane, expand the Parameters node to display the report parameter that was automatically created for the filter.</span></span>

     <span data-ttu-id="13ec0-135">Pour afficher le dataset qui fournit des valeurs disponibles pour le paramètre de rapport, cliquez avec le bouton droit sur tout espace vide dans le volet des données de rapport, puis cliquez sur **Afficher les datasets masqués**.</span><span class="sxs-lookup"><span data-stu-id="13ec0-135">To view the dataset that provides available values for the report parameter, right-click any blank area in the Report Data pane, and then click **Show Hidden Datasets**.</span></span> <span data-ttu-id="13ec0-136">Le volet des données de rapport affiche tous les datasets dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="13ec0-136">The Report Data pane displays all datasets in the report.</span></span>

## <a name="see-also"></a><span data-ttu-id="13ec0-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13ec0-137">See Also</span></span>
 <span data-ttu-id="13ec0-138">[Type de connexion Analysis Services pour mdx &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services interface utilisateur du concepteur de requêtes MDX](analysis-services-mdx-query-designer-user-interface.md)</span><span class="sxs-lookup"><span data-stu-id="13ec0-138">[Analysis Services Connection Type for MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md) [Analysis Services MDX Query Designer User Interface](analysis-services-mdx-query-designer-user-interface.md)</span></span>


