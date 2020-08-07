---
title: Création d’une source à l’aide du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], source components
- output columns [Integration Services]
- sources [Integration Services], components
ms.assetid: 547c4179-ea82-4265-8c6f-04a2aa77a3c0
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a352348f7f47157c5f2ec6d3ff01cea47de0ffb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610731"
---
# <a name="creating-a-source-with-the-script-component"></a><span data-ttu-id="68374-102">Création d'une source à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="68374-102">Creating a Source with the Script Component</span></span>
  <span data-ttu-id="68374-103">Les composants sources dans le flux d'un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permettent de charger des données à partir d'une source de données et de les transférer à des transformations et des destinations en aval.</span><span class="sxs-lookup"><span data-stu-id="68374-103">You use a source component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to load data from a data source to pass on to downstream transformations and destinations.</span></span> <span data-ttu-id="68374-104">En principe, vous vous connectez à la source de données via un gestionnaire de connexions existant.</span><span class="sxs-lookup"><span data-stu-id="68374-104">Ordinarily you connect to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="68374-105">Pour obtenir une vue d’ensemble du composant script, consultez [extension du workflow de données avec le composant Script] (. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="68374-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="68374-106">Le composant Script et le code d'infrastructure qu'il génère simplifient considérablement le processus qui consiste à développer un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="68374-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="68374-107">Toutefois, pour comprendre le fonctionnement du composant Script, il peut être utile de consulter les étapes de développement d'un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="68374-107">However, to understand how the Script component works, you may find it useful to read through the steps that are involved in developing a custom data flow component.</span></span> <span data-ttu-id="68374-108">Consultez la section [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) et plus particulièrement la rubrique [Développement d’un composant source personnalisé](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-108">See the section [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md), especially the topic [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md).</span></span>

## <a name="getting-started-with-a-source-component"></a><span data-ttu-id="68374-109">Mise en route d'un composant source</span><span class="sxs-lookup"><span data-stu-id="68374-109">Getting Started with a Source Component</span></span>
 <span data-ttu-id="68374-110">Lorsque vous ajoutez un composant Script au volet Flux de données du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)], la boîte de dialogue **Sélectionner le type de composant de script** s’ouvre et vous invite à sélectionner un script de type Source, Destination ou Transformation.</span><span class="sxs-lookup"><span data-stu-id="68374-110">When you add a Script component to the Data Flow pane of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a Source, Destination, or Transformation script.</span></span> <span data-ttu-id="68374-111">Dans cette boîte de dialogue, sélectionnez **Source**.</span><span class="sxs-lookup"><span data-stu-id="68374-111">In this dialog box, select **Source**.</span></span>

## <a name="configuring-a-source-component-in-metadata-design-mode"></a><span data-ttu-id="68374-112">Configuration d'un composant source en mode Création de métadonnées</span><span class="sxs-lookup"><span data-stu-id="68374-112">Configuring a Source Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="68374-113">Après avoir sélectionné l'option pour créer un composant source, vous pouvez configurer le composant à l'aide de l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-113">After selecting to create a source component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="68374-114">Pour plus d’informations, consultez [Configuration du composant Script dans l’éditeur de composant de script](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="68374-114">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="68374-115">Un composant source de flux de données ne possède pas d'entrée et prend en charge une ou plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="68374-115">A data flow source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="68374-116">La configuration des sorties du composant est l'une des étapes à exécuter en mode Création de métadonnées, à l'aide de l' **Éditeur de transformation de script**, avant d'écrire le script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="68374-116">Configuring the outputs for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

 <span data-ttu-id="68374-117">Vous pouvez également spécifier le langage de script en définissant la propriété **ScriptLanguage** dans la page **Script** de l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-117">You can also specify the script language by setting the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor**.</span></span>

> [!NOTE]
>  <span data-ttu-id="68374-118">Pour définir le langage de script par défaut des composants Script et des tâches de script, utilisez l'option **Langage de script** dans la page **Général** de la boîte de dialogue **Options** .</span><span class="sxs-lookup"><span data-stu-id="68374-118">To set the default script language for Script components and Script Tasks, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="68374-119">Pour plus d'informations, consultez [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="68374-119">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="68374-120">Ajout de gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="68374-120">Adding Connection Managers</span></span>
 <span data-ttu-id="68374-121">En principe, une composant source utilise un gestionnaire de connexions existant pour se connecter à la source de données à partir de laquelle il charge des données dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="68374-121">Ordinarily a source component uses an existing connection manager to connect to the data source from which it loads data into the data flow.</span></span> <span data-ttu-id="68374-122">Dans la page **Gestionnaires de connexions** de l' **Éditeur de transformation de script**, cliquez sur **Ajouter** pour ajouter le gestionnaire de connexions approprié.</span><span class="sxs-lookup"><span data-stu-id="68374-122">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="68374-123">Toutefois, un gestionnaire de connexions n'est qu'une unité pratique qui permet d'encapsuler et de stocker les informations dont il doit disposer pour se connecter à une source de données d'un type particulier.</span><span class="sxs-lookup"><span data-stu-id="68374-123">However, a connection manager is only a convenient unit that encapsulates and stores the information that it must have to connect to a data source of a particular type.</span></span> <span data-ttu-id="68374-124">Vous devez écrire votre propre code personnalisé pour charger ou enregistrer vos données et éventuellement ouvrir et fermer la connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="68374-124">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source also.</span></span>

 <span data-ttu-id="68374-125">Pour obtenir des informations générales sur l’utilisation des gestionnaires de connexions avec le composant Script, consultez [Connexion aux sources de données dans le composant Script](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-125">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="68374-126">Pour plus d’informations sur la page **Gestionnaires de connexions** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Gestionnaires de connexions&#41;](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="68374-126">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-outputs-and-output-columns"></a><span data-ttu-id="68374-127">Configuration des sorties et des colonnes de sortie</span><span class="sxs-lookup"><span data-stu-id="68374-127">Configuring Outputs and Output Columns</span></span>
 <span data-ttu-id="68374-128">Un composant source ne possède pas d'entrée et prend en charge une ou plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="68374-128">A source component has no inputs and supports one or more outputs.</span></span> <span data-ttu-id="68374-129">La page **Entrées et sorties** de l' **Éditeur de transformation de script**, montre qu'une seule sortie a été créée par défaut, mais qu'aucune colonne de sortie n'a été créée.</span><span class="sxs-lookup"><span data-stu-id="68374-129">On the **Inputs and Outputs** page of the **Script Transformation Editor**, a single output has been created by default, but no output columns have been created.</span></span> <span data-ttu-id="68374-130">Dans cette page de l'éditeur, vous pouvez avoir besoin ou envie de configurer les éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="68374-130">On this page of the editor, you may need or want to configure the following items.</span></span>

-   <span data-ttu-id="68374-131">Vous devez ajouter et configurer manuellement des colonnes de sortie pour chaque sortie.</span><span class="sxs-lookup"><span data-stu-id="68374-131">You must add and configure output columns manually for each output.</span></span> <span data-ttu-id="68374-132">Sélectionnez le dossier Colonnes de sortie pour chaque sortie, puis utilisez les boutons **Ajouter une colonne** et **Supprimer une colonne** pour gérer les colonnes de sortie de chaque sortie du composant source.</span><span class="sxs-lookup"><span data-stu-id="68374-132">Select the Output Columns folder for each output, and then use the **Add Column** and **Remove Column** buttons to manage the output columns for each output of the source component.</span></span> <span data-ttu-id="68374-133">Vous ferez ultérieurement référence aux colonnes de sortie dans le script par le nom que vous leur assignez dans cette page, à l'aide des propriétés d'accesseur typées, créées dans le code généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="68374-133">Later, you will refer to the output columns in your script by the names that you assign here, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="68374-134">Vous pouvez créer une ou plusieurs sorties supplémentaires, telles qu'une sortie d'erreur simulée pour les lignes qui contiennent des valeurs inattendues.</span><span class="sxs-lookup"><span data-stu-id="68374-134">You may want to create one or more additional outputs, such as a simulated error output for rows that contain unexpected values.</span></span> <span data-ttu-id="68374-135">Utilisez les boutons **Ajouter une sortie** et **Supprimer une sortie** pour gérer les sorties du composant source.</span><span class="sxs-lookup"><span data-stu-id="68374-135">Use the **Add Output** and **Remove Output** buttons to manage the outputs of the source component.</span></span> <span data-ttu-id="68374-136">Toutes les lignes d'entrée sont dirigées vers toutes les sorties disponibles, sauf si vous attribuez une valeur identique non nulle à la propriété `ExclusionGroup` de ces sorties, auquel cas vous pourrez diriger chaque ligne vers une seule de ces sorties partageant la même valeur `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="68374-136">All input rows are directed to all available outputs unless you also specify an identical non-zero value for the `ExclusionGroup` property of those outputs where you intend to direct each row to only one of the outputs that share the same `ExclusionGroup` value.</span></span> <span data-ttu-id="68374-137">La valeur entière particulière sélectionnée pour identifier `ExclusionGroup` n'a pas d'importance.</span><span class="sxs-lookup"><span data-stu-id="68374-137">The particular integer value selected to identify the `ExclusionGroup` is not significant.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="68374-138">Vous pouvez également utiliser une valeur de propriété `ExclusionGroup` non nulle avec une sortie unique lorsque vous ne souhaitez pas générer des sorties pour toutes les lignes.</span><span class="sxs-lookup"><span data-stu-id="68374-138">You can also use a non-zero `ExclusionGroup` property value with a single output when you do not want to output all rows.</span></span> <span data-ttu-id="68374-139">Dans ce cas, toutefois, vous devez appeler explicitement la méthode **DirectRowTo\<outputbuffer>** pour chaque ligne que vous souhaitez envoyer à la sortie.</span><span class="sxs-lookup"><span data-stu-id="68374-139">In this case, however, you must explicitly call the **DirectRowTo\<outputbuffer>** method for each row that you want to send to the output.</span></span>

-   <span data-ttu-id="68374-140">Vous pouvez assigner un nom convivial aux sorties.</span><span class="sxs-lookup"><span data-stu-id="68374-140">You may want to assign a friendly name to the outputs.</span></span> <span data-ttu-id="68374-141">Vous ferez ultérieurement référence aux sorties par leur nom dans le script, à l'aide des propriétés d'accesseur typées, créées dans le code généré automatiquement.</span><span class="sxs-lookup"><span data-stu-id="68374-141">Later, you will refer to the outputs by their names in your script, by using the typed accessor properties created for you in the auto-generated code.</span></span>

-   <span data-ttu-id="68374-142">Normalement, plusieurs sorties dans le même `ExclusionGroup` possèdent les mêmes colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="68374-142">Ordinarily multiple outputs in the same `ExclusionGroup` have the same output columns.</span></span> <span data-ttu-id="68374-143">Toutefois, si vous créez une sortie d'erreur simulée, vous pouvez ajouter des colonnes supplémentaires pour stocker les informations d'erreur.</span><span class="sxs-lookup"><span data-stu-id="68374-143">However, if you are creating a simulated error output, you may want to add more columns to store error information.</span></span> <span data-ttu-id="68374-144">Pour plus d’informations sur la manière dont le moteur de flux de données traite les lignes d’erreur, consultez [Utilisation de sorties d’erreur dans un composant de flux de données](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-144">For information about how the data flow engine processes error rows, see [Using Error Outputs in a Data Flow Component](../extending-packages-custom-objects/data-flow/using-error-outputs-in-a-data-flow-component.md).</span></span> <span data-ttu-id="68374-145">Dans le composant Script, vous devez cependant écrire votre propre code pour remplir les colonnes supplémentaires avec les informations d'erreur appropriées.</span><span class="sxs-lookup"><span data-stu-id="68374-145">In the Script component, however, you must write your own code to fill the additional columns with appropriate error information.</span></span> <span data-ttu-id="68374-146">Pour plus d’informations, consultez [Simulation d’une sortie d’erreur pour le composant Script](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-146">For more information, see [Simulating an Error Output for the Script Component](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md).</span></span>

 <span data-ttu-id="68374-147">Pour plus d’informations sur la page **Entrées et sorties** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Entrées et sorties&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="68374-147">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="68374-148">Ajout de variables</span><span class="sxs-lookup"><span data-stu-id="68374-148">Adding Variables</span></span>
 <span data-ttu-id="68374-149">S’il existe des variables dont vous souhaitez utiliser les valeurs dans votre script, vous pouvez les ajouter dans les `ReadOnlyVariables` champs de `ReadWriteVariables` propriété et de la page **script** de l **'éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-149">If there are any existing variables whose values you want to use in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="68374-150">Lorsque vous entrez plusieurs variables dans les champs de propriété, séparez les noms de variables par des virgules.</span><span class="sxs-lookup"><span data-stu-id="68374-150">When you enter multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="68374-151">Vous pouvez également entrer plusieurs variables en cliquant sur le bouton des points de suspension (**...**) en regard des `ReadOnlyVariables` `ReadWriteVariables` champs de propriété et et en sélectionnant variables dans la boîte de dialogue **Sélectionner des variables** .</span><span class="sxs-lookup"><span data-stu-id="68374-151">You can also enter multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields and selecting variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="68374-152">Pour obtenir des informations générales sur l’utilisation de variables avec le composant Script, consultez [Utilisation de variables dans le composant Script](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-152">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="68374-153">Pour plus d’informations sur la page **Script** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Script&#41;](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="68374-153">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-source-component-in-code-design-mode"></a><span data-ttu-id="68374-154">Script d'un composant source en mode Création de code</span><span class="sxs-lookup"><span data-stu-id="68374-154">Scripting a Source Component in Code-Design Mode</span></span>
 <span data-ttu-id="68374-155">Après avoir configuré les métadonnées du composant, ouvrez l’environnement de développement intégré [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) pour coder votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="68374-155">After you have configured the metadata for your component, open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE to code your custom script.</span></span> <span data-ttu-id="68374-156">Pour ouvrir VSTA, cliquez sur **Modifier le script** dans la page **Script** de l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-156">To open VSTA, click **Edit Script** on the **Script** page of the **Script Transformation Editor**.</span></span> <span data-ttu-id="68374-157">Vous pouvez écrire votre script à l’aide de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, selon le langage de script sélectionné pour la propriété **ScriptLanguage**.</span><span class="sxs-lookup"><span data-stu-id="68374-157">You can write your script by using either [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C#, depending on the script language selected for the **ScriptLanguage** property.</span></span>

 <span data-ttu-id="68374-158">Pour obtenir des informations importantes concernant tous les types de composants créés à l’aide du composant Script, consultez [Codage et débogage du composant Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-158">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="68374-159">Fonctionnement du code généré automatiquement</span><span class="sxs-lookup"><span data-stu-id="68374-159">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="68374-160">Lorsque vous ouvrez l'environnement de développement intégré VSTA après avoir créé et configuré un composant source, la classe `ScriptMain` modifiable apparaît dans l'éditeur de code.</span><span class="sxs-lookup"><span data-stu-id="68374-160">When you open the VSTA IDE after creating and configuring a source component, the editable `ScriptMain` class appears in the code editor.</span></span> <span data-ttu-id="68374-161">Vous pouvez écrire votre code personnalisé dans la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="68374-161">You write your custom code in the `ScriptMain` class.</span></span>

 <span data-ttu-id="68374-162">La classe `ScriptMain` inclut un stub pour la méthode `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="68374-162">The `ScriptMain` class includes a stub for the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="68374-163">`CreateNewOutputRows` est la méthode la plus importante d'un composant source.</span><span class="sxs-lookup"><span data-stu-id="68374-163">The `CreateNewOutputRows` is the most important method in a source component.</span></span>

 <span data-ttu-id="68374-164">Si vous ouvrez la fenêtre **Explorateur de projets** dans VSTA, vous pouvez voir que le composant script a également généré des éléments de projet et en lecture seule `BufferWrapper` `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="68374-164">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="68374-165">La classe `ScriptMain` hérite de la classe `UserComponent` dans l'élément de projet `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="68374-165">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="68374-166">Au moment de l'exécution, le moteur de flux de données appelle la méthode `PrimeOutput` dans la classe `UserComponent`, qui remplace la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> de la classe parente <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="68374-166">At run time, the data flow engine invokes the `PrimeOutput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponentHost.PrimeOutput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="68374-167">La méthode `PrimeOutput` appelle à son tour les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="68374-167">The `PrimeOutput` method in turn calls the following methods:</span></span>

1.  <span data-ttu-id="68374-168">La méthode `CreateNewOutputRows`, que vous substituez dans `ScriptMain` pour ajouter des lignes de la source de données aux mémoires tampons de sortie, initialement vides.</span><span class="sxs-lookup"><span data-stu-id="68374-168">The `CreateNewOutputRows` method, which you override in `ScriptMain` to add rows from the data source to the output buffers, which are empty at first.</span></span>

2.  <span data-ttu-id="68374-169">La méthode `FinishOutputs`, vide par défaut.</span><span class="sxs-lookup"><span data-stu-id="68374-169">The `FinishOutputs` method, which is empty by default.</span></span> <span data-ttu-id="68374-170">Substituez cette méthode dans `ScriptMain` pour effectuer les traitements requis pour terminer l'opération de sortie.</span><span class="sxs-lookup"><span data-stu-id="68374-170">Override this method in `ScriptMain` to perform any processing that is required to complete the output.</span></span>

3.  <span data-ttu-id="68374-171">La méthode `MarkOutputsAsFinished` privée, qui appelle la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> de la classe parente <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> pour indiquer au moteur de flux que l'opération de sortie est terminée.</span><span class="sxs-lookup"><span data-stu-id="68374-171">The private `MarkOutputsAsFinished` method, which calls the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer.SetEndOfRowset%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> parent class to indicate to the data flow engine that the output is finished.</span></span> <span data-ttu-id="68374-172">Vous n'avez pas besoin d'appeler `SetEndOfRowset` de manière explicite dans votre propre code.</span><span class="sxs-lookup"><span data-stu-id="68374-172">You do not have to call `SetEndOfRowset` explicitly in your own code.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="68374-173">Écriture du code personnalisé</span><span class="sxs-lookup"><span data-stu-id="68374-173">Writing Your Custom Code</span></span>
 <span data-ttu-id="68374-174">Pour achever la création d'un composant source personnalisé, vous pouvez écrire le script dans les méthodes suivantes disponibles dans la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="68374-174">To finish creating a custom source component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="68374-175">Substituez la méthode `AcquireConnections` pour vous connecter à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="68374-175">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="68374-176">Extrayez l'objet de connexion, ou les informations de connexion requises, du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="68374-176">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="68374-177">Substituez la méthode `PreExecute` pour charger des données, si vous pouvez charger toutes les donnée sources en même temps.</span><span class="sxs-lookup"><span data-stu-id="68374-177">Override the `PreExecute` method to load data, if you can load all the source data at the same time.</span></span> <span data-ttu-id="68374-178">Par exemple, vous pouvez exécuter `SqlCommand` sur une connexion [!INCLUDE[vstecado](../../includes/vstecado-md.md)] à une base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et charger en même temps toutes les données sources dans `SqlDataReader`.</span><span class="sxs-lookup"><span data-stu-id="68374-178">For example, you can execute a `SqlCommand` against an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and load all the source data at the same time into a `SqlDataReader`.</span></span> <span data-ttu-id="68374-179">Si vous devez charger les données sources une ligne à la fois, (par exemple, lors de la lecture d'un fichier texte) vous pouvez charger les données pendant que vous parcourez les lignes dans `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="68374-179">If you must load the source data one row at a time (for example, when reading a text file), you can load the data as you loop through rows in `CreateNewOutputRows`.</span></span>

3.  <span data-ttu-id="68374-180">Utilisez la méthode `CreateNewOutputRows` substituée pour ajouter de nouvelles lignes aux mémoires tampons de sortie vides et remplir les valeurs de chaque colonne dans les nouvelles lignes de sortie.</span><span class="sxs-lookup"><span data-stu-id="68374-180">Use the overridden `CreateNewOutputRows` method to add new rows to the empty output buffers and to fill in the values of each column in the new output rows.</span></span> <span data-ttu-id="68374-181">Utilisez la méthode `AddRow` de chaque mémoire tampon de sortie pour ajouter une nouvelle ligne vide, puis définissez les valeurs de chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="68374-181">Use the `AddRow` method of each output buffer to add an empty new row, and then set the values of each column.</span></span> <span data-ttu-id="68374-182">En général, vous pouvez copier les valeurs des colonnes chargées à partir de la source externe.</span><span class="sxs-lookup"><span data-stu-id="68374-182">Typically you copy values from the columns loaded from the external source.</span></span>

4.  <span data-ttu-id="68374-183">Substituez la méthode `PostExecute` pour terminer le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="68374-183">Override the `PostExecute` method to finish processing the data.</span></span> <span data-ttu-id="68374-184">Par exemple, vous pouvez fermer `SqlDataReader` qui vous a permis de charger des données.</span><span class="sxs-lookup"><span data-stu-id="68374-184">For example, you can close the `SqlDataReader` that you used to load data.</span></span>

5.  <span data-ttu-id="68374-185">Substituez la méthode `ReleaseConnections` pour vous déconnecter de la source de données externe, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="68374-185">Override the `ReleaseConnections` method to disconnect from the external data source, if required.</span></span>

## <a name="examples"></a><span data-ttu-id="68374-186">Exemples</span><span class="sxs-lookup"><span data-stu-id="68374-186">Examples</span></span>
 <span data-ttu-id="68374-187">Les exemples suivants montrent le code personnalisé requis dans la classe `ScriptMain` pour créer un composant source.</span><span class="sxs-lookup"><span data-stu-id="68374-187">The following examples demonstrate the custom code that is required in the `ScriptMain` class to create a source component.</span></span>

> [!NOTE]
>  <span data-ttu-id="68374-188">Ces exemples utilisent la table **Person. Address** dans l' `AdventureWorks` exemple de base de données et transmettent ses première et quatrième colonnes, les colonnes **intAddressID** et **nvarchar (30) City** , par le biais du workflow de données.</span><span class="sxs-lookup"><span data-stu-id="68374-188">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **intAddressID** and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="68374-189">Les mêmes données sont utilisées dans les exemples de source, transformation et destination de cette section.</span><span class="sxs-lookup"><span data-stu-id="68374-189">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="68374-190">Des conditions préalables et des hypothèses supplémentaires sont documentées pour chaque exemple.</span><span class="sxs-lookup"><span data-stu-id="68374-190">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-source-example"></a><span data-ttu-id="68374-191">Exemple de source ADO.NET</span><span class="sxs-lookup"><span data-stu-id="68374-191">ADO.NET Source Example</span></span>
 <span data-ttu-id="68374-192">Cet exemple montre un composant source qui utilise un gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existant pour charger les données d’une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="68374-192">This example demonstrates a source component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to load data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table into the data flow.</span></span>

 <span data-ttu-id="68374-193">Si vous souhaitez exécuter cet exemple de code, vous devez configurer le package et le composant comme suit :</span><span class="sxs-lookup"><span data-stu-id="68374-193">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="68374-194">Créez un gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] qui utilise le fournisseur `SqlClient` pour se connecter à la base de données `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="68374-194">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="68374-195">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que source.</span><span class="sxs-lookup"><span data-stu-id="68374-195">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

3.  <span data-ttu-id="68374-196">Ouvrez l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-196">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="68374-197">Dans la page **Entrées et sorties** , renommez la sortie par défaut avec un nom plus descriptif, tel que **MyAddressOutput**, puis ajoutez et configurez les deux colonnes de sortie, **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="68374-197">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**, and add and configure the two output columns, **AddressID** and **City**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="68374-198">N'oubliez pas de remplacer le type de données de la colonne de sortie de ville **City** par DT_WSTR.</span><span class="sxs-lookup"><span data-stu-id="68374-198">Be sure to change the data type of the **City** output column to DT_WSTR.</span></span>

4.  <span data-ttu-id="68374-199">Dans la page **Gestionnaires de connexions**, ajoutez ou créez le gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] et attribuez-lui un nom, par exemple **MyADONETConnection**.</span><span class="sxs-lookup"><span data-stu-id="68374-199">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager and give it a name such as **MyADONETConnection**.</span></span>

5.  <span data-ttu-id="68374-200">Dans la page **Script** , cliquez sur **Modifier le script** , puis entrez le script suivant.</span><span class="sxs-lookup"><span data-stu-id="68374-200">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="68374-201">Ensuite, fermez l'environnement de développement de script et l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-201">Then close the script development environment and the **Script Transformation Editor**.</span></span>

6.  <span data-ttu-id="68374-202">Créez et configurez un composant de destination, comme une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou l’exemple de composant de destination présenté dans [Création d’une destination à l’aide du composant Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), qui attend les colonnes **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="68374-202">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md), that expects the **AddressID** and **City** columns.</span></span> <span data-ttu-id="68374-203">Puis, connectez le composant source à la destination.</span><span class="sxs-lookup"><span data-stu-id="68374-203">Then connect the source component to the destination.</span></span> <span data-ttu-id="68374-204">(Vous pouvez connecter une source directement à une destination sans aucune transformation.) Vous pouvez créer une table de destination en exécutant la [!INCLUDE[tsql](../../includes/tsql-md.md)] commande suivante dans la `AdventureWorks` base de données :</span><span class="sxs-lookup"><span data-stu-id="68374-204">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

7.  <span data-ttu-id="68374-205">Exécutez l’exemple.</span><span class="sxs-lookup"><span data-stu-id="68374-205">Run the sample.</span></span>

    ```vb
    Imports System.Data.SqlClient
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Dim connMgr As IDTSConnectionManager100
        Dim sqlConn As SqlConnection
        Dim sqlReader As SqlDataReader

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            connMgr = Me.Connections.MyADONETConnection
            sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

        End Sub

        Public Overrides Sub PreExecute()

            Dim cmd As New SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn)
            sqlReader = cmd.ExecuteReader

        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Do While sqlReader.Read
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = sqlReader.GetInt32(0)
                    .City = sqlReader.GetString(1)
                End With
            Loop

        End Sub

        Public Overrides Sub PostExecute()

            sqlReader.Close()

        End Sub

        Public Overrides Sub ReleaseConnections()

            connMgr.ReleaseConnection(sqlConn)

        End Sub

    End Class
    ```

    ```csharp
    using System.Data.SqlClient;
    public class ScriptMain:
        UserComponent

    {
        IDTSConnectionManager100 connMgr;
        SqlConnection sqlConn;
        SqlDataReader sqlReader;

        public override void AcquireConnections(object Transaction)
        {
            connMgr = this.Connections.MyADONETConnection;
            sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {

            SqlCommand cmd = new SqlCommand("SELECT AddressID, City, StateProvinceID FROM Person.Address", sqlConn);
            sqlReader = cmd.ExecuteReader();

        }

        public override void CreateNewOutputRows()
        {

            while (sqlReader.Read())
            {
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = sqlReader.GetInt32(0);
                    MyAddressOutputBuffer.City = sqlReader.GetString(1);
                }
            }

        }

        public override void PostExecute()
        {

            sqlReader.Close();

        }

        public override void ReleaseConnections()
        {

            connMgr.ReleaseConnection(sqlConn);

        }

    }
    ```

### <a name="flat-file-source-example"></a><span data-ttu-id="68374-206">Exemple de source de fichier plat</span><span class="sxs-lookup"><span data-stu-id="68374-206">Flat File Source Example</span></span>
 <span data-ttu-id="68374-207">Cet exemple montre un composant source qui utilise un gestionnaire de connexions de fichiers plats existant pour charger les données d'un fichier plat dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="68374-207">This example demonstrates a source component that uses an existing Flat File connection manager to load data from a flat file into the data flow.</span></span> <span data-ttu-id="68374-208">Vous pouvez créer des données sources de fichier plat en les exportant de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68374-208">The flat file source data is created by exporting it from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>

 <span data-ttu-id="68374-209">Si vous souhaitez exécuter cet exemple de code, vous devez configurer le package et le composant comme suit :</span><span class="sxs-lookup"><span data-stu-id="68374-209">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="68374-210">Utilisez l' [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Assistant importation et exportation pour exporter la table **Person. Address** de l' `AdventureWorks` exemple de base de données vers un fichier plat délimité par des virgules.</span><span class="sxs-lookup"><span data-stu-id="68374-210">Use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Import and Export Wizard to export the **Person.Address** table from the `AdventureWorks` sample database to a comma-delimited flat file.</span></span> <span data-ttu-id="68374-211">Cet exemple utilise le nom de fichier ExportedAddresses.txt.</span><span class="sxs-lookup"><span data-stu-id="68374-211">This sample uses the file name ExportedAddresses.txt.</span></span>

2.  <span data-ttu-id="68374-212">Créez un gestionnaire de connexions de fichiers plats qui se connecte au fichier de données exporté.</span><span class="sxs-lookup"><span data-stu-id="68374-212">Create a Flat File connection manager that connects to the exported data file.</span></span>

3.  <span data-ttu-id="68374-213">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que source.</span><span class="sxs-lookup"><span data-stu-id="68374-213">Add a new Script component to the Data Flow designer surface and configure it as a source.</span></span>

4.  <span data-ttu-id="68374-214">Ouvrez l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-214">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="68374-215">Dans la page **Entrées et sorties** , renommez la sortie par défaut avec un nom plus descriptif, tel que **MyAddressOutput**.</span><span class="sxs-lookup"><span data-stu-id="68374-215">On the **Inputs and Outputs** page, rename the default output with a more descriptive name such as **MyAddressOutput**.</span></span> <span data-ttu-id="68374-216">Ajoutez et configurez les deux colonnes de sortie, **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="68374-216">Add and configure the two output columns, **AddressID** and **City**.</span></span>

5.  <span data-ttu-id="68374-217">Dans la page **Gestionnaires de connexions** , ajoutez ou créez le gestionnaire de connexions de fichiers plats, en lui attribuant un nom descriptif, tel que **MyFlatFileSrcConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="68374-217">On the **Connection Managers** page, add or create the Flat File connection manager, using a descriptive name such as **MyFlatFileSrcConnectionManager**.</span></span>

6.  <span data-ttu-id="68374-218">Dans la page **Script** , cliquez sur **Modifier le script** , puis entrez le script suivant.</span><span class="sxs-lookup"><span data-stu-id="68374-218">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="68374-219">Ensuite, fermez l'environnement de développement de script et l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="68374-219">Then close the script development environment and the **Script Transformation Editor**.</span></span>

7.  <span data-ttu-id="68374-220">Créez et configurez un composant de destination, comme une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou l’exemple de composant de destination présenté dans [Création d’une destination à l’aide du composant Script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="68374-220">Create and configure a destination component, such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, or the sample destination component demonstrated in [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="68374-221">Puis, connectez le composant source à la destination.</span><span class="sxs-lookup"><span data-stu-id="68374-221">Then connect the source component to the destination.</span></span> <span data-ttu-id="68374-222">(Vous pouvez connecter une source directement à une destination sans aucune transformation.) Vous pouvez créer une table de destination en exécutant la [!INCLUDE[tsql](../../includes/tsql-md.md)] commande suivante dans la `AdventureWorks` base de données :</span><span class="sxs-lookup"><span data-stu-id="68374-222">(You can connect a source directly to a destination without any transformations.) You can create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

8.  <span data-ttu-id="68374-223">Exécutez l’exemple.</span><span class="sxs-lookup"><span data-stu-id="68374-223">Run the sample.</span></span>

    ```vb
    Imports System.IO
    ...
    Public Class ScriptMain
        Inherits UserComponent

        Private textReader As StreamReader
        Private exportedAddressFile As String

        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

            Dim connMgr As IDTSConnectionManager100 = _
                Me.Connections.MyFlatFileSrcConnectionManager
            exportedAddressFile = _
                CType(connMgr.AcquireConnection(Nothing), String)

        End Sub

        Public Overrides Sub PreExecute()
            MyBase.PreExecute()
            textReader = New StreamReader(exportedAddressFile)
        End Sub

        Public Overrides Sub CreateNewOutputRows()

            Dim nextLine As String
            Dim columns As String()

            Dim delimiters As Char()
            delimiters = ",".ToCharArray

            nextLine = textReader.ReadLine
            Do While nextLine IsNot Nothing
                columns = nextLine.Split(delimiters)
                With MyAddressOutputBuffer
                    .AddRow()
                    .AddressID = columns(0)
                    .City = columns(3)
                End With
                nextLine = textReader.ReadLine
            Loop

        End Sub

        Public Overrides Sub PostExecute()
            MyBase.PostExecute()
            textReader.Close()

        End Sub

    End Class
    ```

    ```csharp
    using System.IO;
    public class ScriptMain:
        UserComponent

    {
        private StreamReader textReader;
        private string exportedAddressFile;

        public override void AcquireConnections(object Transaction)
        {

            IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileSrcConnectionManager;
            exportedAddressFile = (string)connMgr.AcquireConnection(null);

        }

        public override void PreExecute()
        {
            base.PreExecute();
            textReader = new StreamReader(exportedAddressFile);
        }

        public override void CreateNewOutputRows()
        {

            string nextLine;
            string[] columns;

            char[] delimiters;
            delimiters = ",".ToCharArray();

            nextLine = textReader.ReadLine();
            while (nextLine != null)
            {
                columns = nextLine.Split(delimiters);
                {
                    MyAddressOutputBuffer.AddRow();
                    MyAddressOutputBuffer.AddressID = columns[0];
                    MyAddressOutputBuffer.City = columns[3];
                }
                nextLine = textReader.ReadLine();
            }

        }

        public override void PostExecute()
        {

            base.PostExecute();
            textReader.Close();

        }

    }
    ```

<span data-ttu-id="68374-224">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="68374-224">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="68374-225">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="68374-225">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="68374-226">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="68374-226">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="68374-227">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="68374-227">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="68374-228">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="68374-228">See Also</span></span>
 <span data-ttu-id="68374-229">[Création d’une destination à l’aide du composant script](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [développement d’un composant source personnalisé](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span><span class="sxs-lookup"><span data-stu-id="68374-229">[Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) [Developing a Custom Source Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-source-component.md)</span></span>


