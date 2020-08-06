---
title: Définir les propriétés d’un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], properties
ms.assetid: 73000ef6-52a2-4dec-8320-0e79acf0c2c5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1fd045ba076eed2d65d801015b881a477976f5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613071"
---
# <a name="set-the-properties-of-a-data-flow-component"></a><span data-ttu-id="0b3a5-102">Définir les propriétés d’un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="0b3a5-102">Set the Properties of a Data Flow Component</span></span>
  <span data-ttu-id="0b3a5-103">Pour définir les propriétés de composants de flux de données, qui incluent des sources, des destinations et des transformations, utilisez l'une des fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b3a5-103">To set the properties of data flow components, which include sources, destinations, and transformations, use one of the following features:</span></span>  
  
-   <span data-ttu-id="0b3a5-104">Les éditeurs de composants fournis par [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-104">The component editors that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] provides.</span></span> <span data-ttu-id="0b3a5-105">Ces éditeurs ne peuvent être utilisés que pour définir les propriétés personnalisées de chaque composant de flux de données.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-105">These editors include only the custom properties of each data flow component.</span></span>  
  
-   <span data-ttu-id="0b3a5-106">La fenêtre **Propriétés** énumère les propriétés personnalisées définies au niveau du composant pour chaque élément, ainsi que les propriétés communes à tous les éléments du flux de données.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-106">The **Properties** window lists the component-level custom properties of each element, as well as the properties common to all data flow elements.</span></span>  
  
-   <span data-ttu-id="0b3a5-107">La boîte de dialogue **Éditeur avancé** permet d’accéder aux propriétés personnalisées pour chaque composant.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-107">The **Advanced Editor** dialog box provides access to custom properties for each component.</span></span> <span data-ttu-id="0b3a5-108">La boîte de dialogue **Éditeur avancé** permet aussi d’accéder aux propriétés communes à l’ensemble des composants de flux de données, à savoir les propriétés des entrées, des sorties, des sorties d’erreurs, des colonnes et des colonnes externes.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-108">The **Advanced Editor** dialog box also provides access to the properties common to all data flow components-the properties of inputs, outputs, error outputs, columns, and external columns.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-a-component-editor"></a><span data-ttu-id="0b3a5-109">Pour définir les propriétés d'un composant de flux de données à l'aide d'un éditeur de composant</span><span class="sxs-lookup"><span data-stu-id="0b3a5-109">To set the properties of a data flow component by using a component editor</span></span>  
  
1.  <span data-ttu-id="0b3a5-110">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-110">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0b3a5-111">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-111">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b3a5-112">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la tâche de flux de données qui contient le flux de données et le composant dont vous voulez afficher ou modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-112">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow with the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="0b3a5-113">Double-cliquez sur le composant du flux de données.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-113">Double-click the data flow component.</span></span>  
  
5.  <span data-ttu-id="0b3a5-114">Dans l'éditeur de composant, affichez ou modifiez les valeurs des propriétés, puis fermez l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-114">In the component editor, view or modify the property values, and then close the editor.</span></span>  
  
6.  <span data-ttu-id="0b3a5-115">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-115">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-properties-window"></a><span data-ttu-id="0b3a5-116">Pour définir les propriétés d'un composant de flux de données à l'aide de la fenêtre Propriétés</span><span class="sxs-lookup"><span data-stu-id="0b3a5-116">To set the properties of a data flow component by using the Properties window</span></span>  
  
1.  <span data-ttu-id="0b3a5-117">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-117">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0b3a5-118">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-118">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b3a5-119">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la tâche de flux de données qui contient le composant dont vous voulez afficher ou modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-119">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component whose properties you want to view and modify.</span></span>  
  
4.  <span data-ttu-id="0b3a5-120">Cliquez avec le bouton droit sur le composant du flux de données, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-120">Right-click the data flow component, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0b3a5-121">Affichez ou modifiez les valeurs des propriétés, puis fermez la fenêtre **Propriétés** .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-121">View or modify the property values, and then close the **Properties** window.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b3a5-122">De nombreuses propriétés sont en lecture seule et ne peuvent donc pas être modifiées.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-122">Many properties are read-only, and cannot be modified.</span></span>  
  
6.  <span data-ttu-id="0b3a5-123">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-123">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
### <a name="to-set-the-properties-of-a-data-flow-component-by-using-the-advanced-editor"></a><span data-ttu-id="0b3a5-124">Pour définir les propriétés d'un composant de flux de données à l'aide de l'éditeur avancé</span><span class="sxs-lookup"><span data-stu-id="0b3a5-124">To set the properties of a data flow component by using the Advanced Editor</span></span>  
  
1.  <span data-ttu-id="0b3a5-125">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-125">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="0b3a5-126">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-126">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="0b3a5-127">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la tâche de flux de données qui contient le composant à afficher ou à modifier.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-127">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the component you want to view or modify.</span></span>  
  
4.  <span data-ttu-id="0b3a5-128">Dans le concepteur de flux de données, cliquez avec le bouton droit sur le composant du flux de données, puis cliquez sur **Afficher l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-128">In the data flow designer, right-click the data flow component, and then click **Show Advanced Editor**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="0b3a5-129">Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les composants de flux de données qui prennent en charge plusieurs entrées ne peuvent pas utiliser **l’éditeur avancé**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-129">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data flow components that support multiple inputs cannot use the **Advanced Editor**.</span></span>  
  
5.  <span data-ttu-id="0b3a5-130">Dans la boîte de dialogue **Éditeur avancé** , procédez de l’une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="0b3a5-130">In the **Advanced Editor** dialog box, do any of the following steps:</span></span>  
  
    -   <span data-ttu-id="0b3a5-131">Pour afficher et spécifier la connexion utilisée par le composant, cliquez sur l’onglet **Gestionnaires de connexions** .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-131">To view and specify the connection that the component uses, click the **Connection Managers** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0b3a5-132">L’onglet **Gestionnaire de connexions** est accessible uniquement aux composants de flux de données qui utilisent des gestionnaires de connexions pour se connecter à des sources de données telles que des fichiers et des bases de données.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-132">The **Connection Managers** tab is available only to data flow components that use connection managers to connect to data sources such as files and databases</span></span>  
  
    -   <span data-ttu-id="0b3a5-133">Pour afficher et modifier les propriétés au niveau du composant, cliquez sur l’onglet **Propriétés du composant** .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-133">To view and modify component-level properties, click the **Component Properties** tab.</span></span>  
  
    -   <span data-ttu-id="0b3a5-134">Pour afficher et modifier les mappages entre des colonnes externes et la sortie disponible, cliquez sur l’onglet **Mappage de colonnes** .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-134">To view and modify mappings between external columns and the available output, click the **Column Mappings** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0b3a5-135">L’onglet **Mappage de colonnes** est disponible uniquement pendant l’affichage ou la modification des sources et des destinations.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-135">The **Column Mappings** tab is available only when viewing or editing sources or destinations.</span></span>  
  
    -   <span data-ttu-id="0b3a5-136">Pour afficher la liste des colonnes d’entrée disponibles et mettre à jour le nom des colonnes de sortie, cliquez sur l’onglet **Colonnes d’entrée** .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-136">To view a list of the available input columns and to update the names of output columns, click the **Input Columns** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0b3a5-137">L'onglet Colonnes d'entrée est disponible uniquement en cas d'utilisation de transformations ou de destinations.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-137">The Input Columns tab is available only when working with transformations or destinations.</span></span> <span data-ttu-id="0b3a5-138">Pour plus d’informations, consultez [Transformations Integration Services](transformations/integration-services-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="0b3a5-138">For more information, see [Integration Services Transformations](transformations/integration-services-transformations.md).</span></span>  
  
    -   <span data-ttu-id="0b3a5-139">Pour afficher et modifier les propriétés des entrées, des sorties, des sorties d’erreur et les propriétés des colonnes qu’elles contiennent, cliquez sur l’onglet **Propriétés d’entrée et de sortie** .</span><span class="sxs-lookup"><span data-stu-id="0b3a5-139">To view and modify the properties of inputs, outputs, and error outputs, and the properties of the columns they contain, click the **Input and Output Properties** tab.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="0b3a5-140">Les sources ne comportent pas d'entrées.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-140">Sources have no inputs.</span></span> <span data-ttu-id="0b3a5-141">Les destinations ne comportent pas de sorties, sauf pour une sortie d'erreur facultative.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-141">Destinations have no outputs, except for an optional error output.</span></span>  
  
6.  <span data-ttu-id="0b3a5-142">Affichez ou modifiez les valeurs des propriétés.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-142">View or modify the property values.</span></span>  
  
7.  <span data-ttu-id="0b3a5-143">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-143">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="0b3a5-144">Pour enregistrer le package mis à jour, dans le menu **Fichier** , cliquez sur **Enregistrer les éléments sélectionnés**.</span><span class="sxs-lookup"><span data-stu-id="0b3a5-144">To save the updated package, on the **File** menu, click **Save Selected Items**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b3a5-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b3a5-145">See Also</span></span>  
 [<span data-ttu-id="0b3a5-146">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="0b3a5-146">Integration Services Transformations</span></span>](transformations/integration-services-transformations.md)  
  
  
