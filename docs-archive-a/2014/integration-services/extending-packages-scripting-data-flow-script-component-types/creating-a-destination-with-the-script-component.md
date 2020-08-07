---
title: Création d’une destination à l’aide du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], destination components
- destinations [Integration Services], components
- input columns [Integration Services]
ms.assetid: 214e22e8-7e7d-4876-b690-c138e5721b81
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1245dde111b24d1c37e2c5550d236c97126ee725
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611913"
---
# <a name="creating-a-destination-with-the-script-component"></a><span data-ttu-id="edada-102">Création d'une destination à l'aide du composant Script</span><span class="sxs-lookup"><span data-stu-id="edada-102">Creating a Destination with the Script Component</span></span>
  <span data-ttu-id="edada-103">Les composants de destination dans le flux de données d'un package [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] permettent d'enregistrer des données provenant de sources et de transformations en amont dans une source de données.</span><span class="sxs-lookup"><span data-stu-id="edada-103">You use a destination component in the data flow of an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package to save data received from upstream sources and transformations to a data source.</span></span> <span data-ttu-id="edada-104">En principe, le composant de destination se connecte à la source de données via un gestionnaire de connexions existant.</span><span class="sxs-lookup"><span data-stu-id="edada-104">Ordinarily the destination component connects to the data source through an existing connection manager.</span></span>

 <span data-ttu-id="edada-105">Pour obtenir une vue d’ensemble du composant script, consultez [extension du workflow de données avec le composant Script] (. /extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span><span class="sxs-lookup"><span data-stu-id="edada-105">For an overview of the Script component, see [Extending the Data Flow with the Script Component](../extending-packages-scripting/data-flow-script-component/extending-the-data-flow-with-the-script-component.md.</span></span>

 <span data-ttu-id="edada-106">Le composant Script et le code d'infrastructure qu'il génère simplifient considérablement le processus qui consiste à développer un composant de flux de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="edada-106">The Script component and the infrastructure code that it generates for you simplify significantly the process of developing a custom data flow component.</span></span> <span data-ttu-id="edada-107">Toutefois, pour comprendre le fonctionnement du composant Script, il peut être utile de lire les étapes permettant de développer des composants de flux de données personnalisés dans la section [Développement d’un composant de flux de données personnalisé](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) et plus particulièrement [Développement d’un composant de destination personnalisé](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span><span class="sxs-lookup"><span data-stu-id="edada-107">However, to understand how the Script component works, you may find it useful to read through the steps for developing a custom data flow components in the [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md) section, and especially [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md).</span></span>

## <a name="getting-started-with-a-destination-component"></a><span data-ttu-id="edada-108">Mise en route d'un composant de destination</span><span class="sxs-lookup"><span data-stu-id="edada-108">Getting Started with a Destination Component</span></span>
 <span data-ttu-id="edada-109">Lorsque vous ajoutez un composant Script à l’onglet Flux de données du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)], la boîte de dialogue **Sélectionner le type de composant de script** s’ouvre et vous invite à sélectionner un script de type **Source**, **Destination** ou **Transformation**.</span><span class="sxs-lookup"><span data-stu-id="edada-109">When you add a Script component to the Data Flow tab of [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, the **Select Script Component Type** dialog box opens and prompts you to select a **Source**, **Destination**, or **Transformation** script.</span></span> <span data-ttu-id="edada-110">Dans cette boîte de dialogue, sélectionnez **Destination**.</span><span class="sxs-lookup"><span data-stu-id="edada-110">In this dialog box, select **Destination**.</span></span>

 <span data-ttu-id="edada-111">Ensuite, connectez la sortie d'une transformation au composant de destination dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edada-111">Next, connect the output of a transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="edada-112">À des fins de test, vous pouvez connecter directement une source à une destination sans transformation.</span><span class="sxs-lookup"><span data-stu-id="edada-112">For testing, you can connect a source directly to a destination without any transformations.</span></span>

## <a name="configuring-a-destination-component-in-metadata-design-mode"></a><span data-ttu-id="edada-113">Configuration d'un composant de destination en mode Création de métadonnées</span><span class="sxs-lookup"><span data-stu-id="edada-113">Configuring a Destination Component in Metadata-Design Mode</span></span>
 <span data-ttu-id="edada-114">Après avoir sélectionné l’option de création d’un composant de destination, configurez le composant dans l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="edada-114">After you select the option to create a destination component, you configure the component by using the **Script Transformation Editor**.</span></span> <span data-ttu-id="edada-115">Pour plus d’informations, consultez [Configuration du composant Script dans l’éditeur de composant de script](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span><span class="sxs-lookup"><span data-stu-id="edada-115">For more information, see [Configuring the Script Component in the Script Component Editor](../extending-packages-scripting/data-flow-script-component/configuring-the-script-component-in-the-script-component-editor.md).</span></span>

 <span data-ttu-id="edada-116">Pour sélectionner le langage de script qui sera utilisé par le composant Script, vous devez définir la propriété **ScriptLanguage** dans la page **Script** de la boîte de dialogue **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="edada-116">To select the script language that the Script destination will use, you set the **ScriptLanguage** property on the **Script** page of the **Script Transformation Editor** dialog box.</span></span>

> [!NOTE]
>  <span data-ttu-id="edada-117">Pour définir le langage de script par défaut du composant Script, utilisez l’option **Langage de script** dans la page **Général** de la boîte de dialogue **Options**.</span><span class="sxs-lookup"><span data-stu-id="edada-117">To set the default scripting language for the Script component, use the **Scripting language** option on the **General** page of the **Options** dialog box.</span></span> <span data-ttu-id="edada-118">Pour plus d'informations, consultez [General Page](../general-page-of-integration-services-designers-options.md).</span><span class="sxs-lookup"><span data-stu-id="edada-118">For more information, see [General Page](../general-page-of-integration-services-designers-options.md).</span></span>

 <span data-ttu-id="edada-119">Un composant de destination de flux de données possède une entrée et aucune sortie.</span><span class="sxs-lookup"><span data-stu-id="edada-119">A data flow destination component has one input and no outputs.</span></span> <span data-ttu-id="edada-120">La configuration de l’entrée du composant est l’une des étapes à exécuter en mode Création des métadonnées, à l’aide de l’**Éditeur de transformation de script**, avant d’écrire le script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="edada-120">Configuring the input for the component is one of the steps that you must complete in metadata design mode, by using the **Script Transformation Editor**, before you write your custom script.</span></span>

### <a name="adding-connection-managers"></a><span data-ttu-id="edada-121">Ajout de gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="edada-121">Adding Connection Managers</span></span>
 <span data-ttu-id="edada-122">En principe, une composant de destination utilise un gestionnaire de connexions existant pour se connecter à la source de données dans laquelle il enregistre les données du flux de données.</span><span class="sxs-lookup"><span data-stu-id="edada-122">Ordinarily a destination component uses an existing connection manager to connect to the data source to which it saves data from the data flow.</span></span> <span data-ttu-id="edada-123">Dans la page **Gestionnaires de connexions** de l' **Éditeur de transformation de script**, cliquez sur **Ajouter** pour ajouter le gestionnaire de connexions approprié.</span><span class="sxs-lookup"><span data-stu-id="edada-123">On the **Connection Managers** page of the **Script Transformation Editor**, click **Add** to add the appropriate connection manager.</span></span>

 <span data-ttu-id="edada-124">Toutefois, un gestionnaire de connexions n'est qu'une unité pratique qui permet d'encapsuler et de stocker les informations requises pour se connecter à une source de données d'un type particulier.</span><span class="sxs-lookup"><span data-stu-id="edada-124">However, a connection manager is just a convenient unit that encapsulates and stores the information that is required to connect to a data source of a particular type.</span></span> <span data-ttu-id="edada-125">Vous devez écrire votre propre code personnalisé pour charger ou enregistrer vos données et éventuellement ouvrir et fermer la connexion à la source de données.</span><span class="sxs-lookup"><span data-stu-id="edada-125">You must write your own custom code to load or save your data, and possibly to open and close the connection to the data source.</span></span>

 <span data-ttu-id="edada-126">Pour obtenir des informations générales sur l’utilisation des gestionnaires de connexions avec le composant Script, consultez [Connexion aux sources de données dans le composant Script](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="edada-126">For general information about how to use connection managers with the Script component, see [Connecting to Data Sources in the Script Component](../extending-packages-scripting/data-flow-script-component/connecting-to-data-sources-in-the-script-component.md).</span></span>

 <span data-ttu-id="edada-127">Pour plus d’informations sur la page **Gestionnaires de connexions** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Gestionnaires de connexions&#41;](../script-transformation-editor-connection-managers-page.md).</span><span class="sxs-lookup"><span data-stu-id="edada-127">For more information about the **Connection Managers** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Connection Managers Page&#41;](../script-transformation-editor-connection-managers-page.md).</span></span>

### <a name="configuring-inputs-and-input-columns"></a><span data-ttu-id="edada-128">Configuration d'entrées et de colonnes d'entrée</span><span class="sxs-lookup"><span data-stu-id="edada-128">Configuring Inputs and Input Columns</span></span>
 <span data-ttu-id="edada-129">Un composant de destination possède une entrée et aucune sortie.</span><span class="sxs-lookup"><span data-stu-id="edada-129">A destination component has one input and no outputs.</span></span>

 <span data-ttu-id="edada-130">Dans la page **Colonnes d’entrée** de l’**Éditeur de transformation de script**, la liste des colonnes affiche les colonnes disponibles dans la sortie du composant en amont du flux de données.</span><span class="sxs-lookup"><span data-stu-id="edada-130">On the **Input Columns** page of the **Script Transformation Editor**, the column list shows the available columns from the output of the upstream component in the data flow.</span></span> <span data-ttu-id="edada-131">Sélectionnez les colonnes à enregistrer.</span><span class="sxs-lookup"><span data-stu-id="edada-131">Select the columns that you want to save.</span></span>

 <span data-ttu-id="edada-132">Pour plus d’informations sur la page **Colonnes d’entrée** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Colonnes d’entrée&#41;](../script-transformation-editor-input-columns-page.md).</span><span class="sxs-lookup"><span data-stu-id="edada-132">For more information about the **Input Columns** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Input Columns Page&#41;](../script-transformation-editor-input-columns-page.md).</span></span>

 <span data-ttu-id="edada-133">La page **Entrées et sorties** de l’**Éditeur de transformation de script** affiche une seule entrée que vous pouvez renommer.</span><span class="sxs-lookup"><span data-stu-id="edada-133">The **Inputs and Outputs** page of the **Script Transformation Editor** shows a single input, which you can rename.</span></span> <span data-ttu-id="edada-134">La propriété d'accesseur créée dans le code généré automatiquement vous permet de référencer l'entrée dans le script par son nom.</span><span class="sxs-lookup"><span data-stu-id="edada-134">You will refer to the input by its name in your script by using the accessor property created in the auto-generated code.</span></span>

 <span data-ttu-id="edada-135">Pour plus d’informations sur la page **Entrées et sorties** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Entrées et sorties&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span><span class="sxs-lookup"><span data-stu-id="edada-135">For more information about the **Inputs and Outputs** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Inputs and Outputs Page&#41;](../script-transformation-editor-inputs-and-outputs-page.md).</span></span>

### <a name="adding-variables"></a><span data-ttu-id="edada-136">Ajout de variables</span><span class="sxs-lookup"><span data-stu-id="edada-136">Adding Variables</span></span>
 <span data-ttu-id="edada-137">Si vous souhaitez utiliser des variables existantes dans votre script, vous pouvez les ajouter dans les `ReadOnlyVariables` champs de propriété et dans `ReadWriteVariables` la page **script** de l **'éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="edada-137">If you want to use existing variables in your script, you can add them in the `ReadOnlyVariables` and `ReadWriteVariables` property fields on the **Script** page of the **Script Transformation Editor**.</span></span>

 <span data-ttu-id="edada-138">Lorsque vous ajoutez plusieurs variables dans les champs de propriété, séparez les noms de variables par des virgules.</span><span class="sxs-lookup"><span data-stu-id="edada-138">When you add multiple variables in the property fields, separate the variable names by commas.</span></span> <span data-ttu-id="edada-139">Vous pouvez également sélectionner plusieurs variables en cliquant sur le bouton des points de suspension (**...**) en regard des `ReadOnlyVariables` `ReadWriteVariables` champs de propriété et, puis en sélectionnant les variables dans la boîte de dialogue **Sélectionner des variables** .</span><span class="sxs-lookup"><span data-stu-id="edada-139">You can also select multiple variables by clicking the ellipsis (**...**) button next to the `ReadOnlyVariables` and `ReadWriteVariables` property fields, and then selecting the variables in the **Select variables** dialog box.</span></span>

 <span data-ttu-id="edada-140">Pour obtenir des informations générales sur l’utilisation de variables avec le composant Script, consultez [Utilisation de variables dans le composant Script](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="edada-140">For general information about how to use variables with the Script component, see [Using Variables in the Script Component](../extending-packages-scripting/data-flow-script-component/using-variables-in-the-script-component.md).</span></span>

 <span data-ttu-id="edada-141">Pour plus d’informations sur la page **Script** de l’**Éditeur de transformation de script**, consultez [Éditeur de transformation de script &#40;page Script&#41;](../script-transformation-editor-script-page.md).</span><span class="sxs-lookup"><span data-stu-id="edada-141">For more information about the **Script** page of the **Script Transformation Editor**, see [Script Transformation Editor &#40;Script Page&#41;](../script-transformation-editor-script-page.md).</span></span>

## <a name="scripting-a-destination-component-in-code-design-mode"></a><span data-ttu-id="edada-142">Script d'un composant de destination en mode Création de code</span><span class="sxs-lookup"><span data-stu-id="edada-142">Scripting a Destination Component in Code-Design Mode</span></span>
 <span data-ttu-id="edada-143">Après avoir configuré les métadonnées du composant, vous pouvez écrire votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="edada-143">After you have configured the metadata for your component, you can write your custom script.</span></span> <span data-ttu-id="edada-144">Dans l’**Éditeur de transformation de script**, dans la page **Script**, cliquez sur **Modifier le script** pour ouvrir l’environnement de développement intégré [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) où vous pouvez ajouter votre script personnalisé.</span><span class="sxs-lookup"><span data-stu-id="edada-144">In the **Script Transformation Editor**, on the **Script** page, click **Edit Script** to open the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) IDE where you can add your custom script.</span></span> <span data-ttu-id="edada-145">Le langage de script utilisé varie selon que vous avez sélectionné [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# comme langage de script pour la propriété **ScriptLanguage** dans la page **Script**.</span><span class="sxs-lookup"><span data-stu-id="edada-145">The scripting language that you use depends on whether you selected [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual Basic or [!INCLUDE[msCoName](../../includes/msconame-md.md)] Visual C# as the script language for the **ScriptLanguage** property on the **Script** page.</span></span>

 <span data-ttu-id="edada-146">Pour obtenir des informations importantes concernant tous les types de composants créés à l’aide du composant Script, consultez [Codage et débogage du composant Script](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span><span class="sxs-lookup"><span data-stu-id="edada-146">For important information that applies to all kinds of components created by using the Script component, see [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md).</span></span>

### <a name="understanding-the-auto-generated-code"></a><span data-ttu-id="edada-147">Fonctionnement du code généré automatiquement</span><span class="sxs-lookup"><span data-stu-id="edada-147">Understanding the Auto-generated Code</span></span>
 <span data-ttu-id="edada-148">Lorsque vous ouvrez l'environnement de développement intégré VSTA après avoir créé et configuré un composant de destination, la classe `ScriptMain` modifiable apparaît dans l'éditeur de code avec un stub pour la méthode `ProcessInputRow`.</span><span class="sxs-lookup"><span data-stu-id="edada-148">When you open the VSTA IDE after you create and configuring a destination component, the editable `ScriptMain` class appears in the code editor with a stub for the `ProcessInputRow` method.</span></span> <span data-ttu-id="edada-149">La classe `ScriptMain` est l'emplacement où vous allez écrire votre code personnalisé, et `ProcessInputRow` est la méthode la plus importante d'un composant de destination.</span><span class="sxs-lookup"><span data-stu-id="edada-149">The `ScriptMain` class is where you will write your custom code, and `ProcessInputRow` is the most important method in a destination component.</span></span>

 <span data-ttu-id="edada-150">Si vous ouvrez la fenêtre **Explorateur de projets** dans VSTA, vous pouvez voir que le composant script a également généré des éléments de projet et en lecture seule `BufferWrapper` `ComponentWrapper` .</span><span class="sxs-lookup"><span data-stu-id="edada-150">If you open the **Project Explorer** window in VSTA, you can see that the Script component has also generated read-only `BufferWrapper` and `ComponentWrapper` project items.</span></span> <span data-ttu-id="edada-151">La classe `ScriptMain` hérite de la classe `UserComponent` dans l'élément de projet `ComponentWrapper`.</span><span class="sxs-lookup"><span data-stu-id="edada-151">The `ScriptMain` class inherits from `UserComponent` class in the `ComponentWrapper` project item.</span></span>

 <span data-ttu-id="edada-152">Au moment de l'exécution, le moteur de flux de données appelle la méthode `ProcessInput` dans la classe `UserComponent`, qui remplace la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> de la classe parente <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="edada-152">At run time, the data flow engine invokes the `ProcessInput` method in the `UserComponent` class, which overrides the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ProcessInput%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> parent class.</span></span> <span data-ttu-id="edada-153">La méthode `ProcessInput` parcourt à son tour les lignes du tampon d'entrée et appelle la méthode `ProcessInputRow` une fois pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="edada-153">The `ProcessInput` method in turn loops through the rows in the input buffer and calls the `ProcessInputRow` method one time for each row.</span></span>

### <a name="writing-your-custom-code"></a><span data-ttu-id="edada-154">Écriture du code personnalisé</span><span class="sxs-lookup"><span data-stu-id="edada-154">Writing Your Custom Code</span></span>
 <span data-ttu-id="edada-155">Pour terminer de créer un composant de destination personnalisé, vous pouvez écrire le script dans les méthodes suivantes disponibles dans la classe `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="edada-155">To finish creating a custom destination component, you may want to write script in the following methods available in the `ScriptMain` class.</span></span>

1.  <span data-ttu-id="edada-156">Substituez la méthode `AcquireConnections` pour vous connecter à la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="edada-156">Override the `AcquireConnections` method to connect to the external data source.</span></span> <span data-ttu-id="edada-157">Extrayez l'objet de connexion, ou les informations de connexion requises, du gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="edada-157">Extract the connection object, or the required connection information, from the connection manager.</span></span>

2.  <span data-ttu-id="edada-158">Substituez la méthode `PreExecute` pour vous préparer à enregistrer les données.</span><span class="sxs-lookup"><span data-stu-id="edada-158">Override the `PreExecute` method to prepare to save the data.</span></span> <span data-ttu-id="edada-159">Par exemple, vous pouvez créer et configurer un `SqlCommand` et ses paramètres dans cette méthode.</span><span class="sxs-lookup"><span data-stu-id="edada-159">For example, you may want to create and configure a `SqlCommand` and its parameters in this method.</span></span>

3.  <span data-ttu-id="edada-160">Utilisez la méthode `ProcessInputRow` substituée pour copier chaque ligne d'entrée vers la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="edada-160">Use the overridden `ProcessInputRow` method to copy each input row to the external data source.</span></span> <span data-ttu-id="edada-161">Par exemple, pour une destination [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], vous pouvez copier les valeurs de colonne dans les paramètres de `SqlCommand` et exécuter la commande une fois pour chaque ligne.</span><span class="sxs-lookup"><span data-stu-id="edada-161">For example, for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] destination, you can copy the column values into the parameters of a `SqlCommand` and execute the command one time for each row.</span></span> <span data-ttu-id="edada-162">Pour une destination de fichier plat, vous pouvez écrire les valeurs de chaque colonne dans `StreamWriter`, en séparant les valeurs par le délimiteur de colonne.</span><span class="sxs-lookup"><span data-stu-id="edada-162">For a flat file destination, you can write the values for each column to a `StreamWriter`, separating the values by the column delimiter.</span></span>

4.  <span data-ttu-id="edada-163">Substituez la méthode `PostExecute` pour vous déconnecter de la source de données externe, le cas échéant, et pour effectuer toute autre opération de nettoyage nécessaire.</span><span class="sxs-lookup"><span data-stu-id="edada-163">Override the `PostExecute` method to disconnect from the external data source, if required, and to perform any other required cleanup.</span></span>

## <a name="examples"></a><span data-ttu-id="edada-164">Exemples</span><span class="sxs-lookup"><span data-stu-id="edada-164">Examples</span></span>
 <span data-ttu-id="edada-165">Les exemples suivants présentent le code requis dans la classe `ScriptMain` pour créer un composant de destination.</span><span class="sxs-lookup"><span data-stu-id="edada-165">The examples that follow demonstrate code that is required in the `ScriptMain` class to create a destination component.</span></span>

> [!NOTE]
>  <span data-ttu-id="edada-166">Ces exemples utilisent la table **Person. Address** dans l' `AdventureWorks` exemple de base de données et transmettent ses première et quatrième colonnes, les colonnes **int \* AddressID**\* et **nvarchar (30) City** , par le biais du Workflow.</span><span class="sxs-lookup"><span data-stu-id="edada-166">These examples use the **Person.Address** table in the `AdventureWorks` sample database and pass its first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, through the data flow.</span></span> <span data-ttu-id="edada-167">Les mêmes données sont utilisées dans les exemples de source, transformation et destination de cette section.</span><span class="sxs-lookup"><span data-stu-id="edada-167">The same data is used in the source, transformation, and destination samples in this section.</span></span> <span data-ttu-id="edada-168">Des conditions préalables et des hypothèses supplémentaires sont documentées pour chaque exemple.</span><span class="sxs-lookup"><span data-stu-id="edada-168">Additional prerequisites and assumptions are documented for each example.</span></span>

### <a name="adonet-destination-example"></a><span data-ttu-id="edada-169">Exemple de destination ADO.NET</span><span class="sxs-lookup"><span data-stu-id="edada-169">ADO.NET Destination Example</span></span>
 <span data-ttu-id="edada-170">Cet exemple montre un composant de destination qui utilise un gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] existant pour enregistrer des données du flux de données dans une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edada-170">This example demonstrates a destination component that uses an existing [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager to save data from the data flow into a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>

 <span data-ttu-id="edada-171">Si vous souhaitez exécuter cet exemple de code, vous devez configurer le package et le composant comme suit :</span><span class="sxs-lookup"><span data-stu-id="edada-171">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="edada-172">Créez un gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] qui utilise le fournisseur `SqlClient` pour se connecter à la base de données `AdventureWorks`.</span><span class="sxs-lookup"><span data-stu-id="edada-172">Create an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager that uses the `SqlClient` provider to connect to the `AdventureWorks` database.</span></span>

2.  <span data-ttu-id="edada-173">Créez une table de destination en exécutant la commande [!INCLUDE[tsql](../../includes/tsql-md.md)] suivante dans la base de données `AdventureWorks` :</span><span class="sxs-lookup"><span data-stu-id="edada-173">Create a destination table by running the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command in the `AdventureWorks` database:</span></span>

    ```
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,
        [City] [nvarchar](30) NOT NULL)
    ```

3.  <span data-ttu-id="edada-174">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que destination.</span><span class="sxs-lookup"><span data-stu-id="edada-174">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

4.  <span data-ttu-id="edada-175">Connectez la sortie d'une source ou transformation en amont au composant de destination dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edada-175">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="edada-176">(Vous pouvez connecter une source directement à une destination sans aucune transformation.) Cette sortie doit fournir les données de la table **Person. Address** de l' `AdventureWorks` exemple de base de données qui contient au moins les colonnes **AddressID** et **City** .</span><span class="sxs-lookup"><span data-stu-id="edada-176">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database that contains at least the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="edada-177">Ouvrez l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="edada-177">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="edada-178">Dans la page **Colonnes d’entrée**, sélectionnez les colonnes d’entrée **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="edada-178">On the **Input Columns** page, select the **AddressID** and **City** input columns.</span></span>

6.  <span data-ttu-id="edada-179">Dans la page **Entrées et sorties**, renommez l’entrée en lui attribuant un nom plus descriptif, comme **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="edada-179">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>

7.  <span data-ttu-id="edada-180">Dans la page **Gestionnaires de connexions**, ajoutez ou créez le gestionnaire de connexions [!INCLUDE[vstecado](../../includes/vstecado-md.md)] et attribuez-lui un nom, par exemple **MyADONETConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="edada-180">On the **Connection Managers** page, add or create the [!INCLUDE[vstecado](../../includes/vstecado-md.md)] connection manager with a name such as **MyADONETConnectionManager**.</span></span>

8.  <span data-ttu-id="edada-181">Dans la page **Script** , cliquez sur **Modifier le script** , puis entrez le script suivant.</span><span class="sxs-lookup"><span data-stu-id="edada-181">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="edada-182">Ensuite, fermez l'environnement de développement de script.</span><span class="sxs-lookup"><span data-stu-id="edada-182">Then close the script development environment.</span></span>

9. <span data-ttu-id="edada-183">Fermez l’**Éditeur de transformation de script** et exécutez l’exemple.</span><span class="sxs-lookup"><span data-stu-id="edada-183">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.Data.SqlClient
...
Public Class ScriptMain
    Inherits UserComponent

    Dim connMgr As IDTSConnectionManager100
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        connMgr = Me.Connections.MyADONETConnectionManager
        sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

    End Sub

    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)
        With sqlCmd
            .Parameters("@addressid").Value = Row.AddressID
            .Parameters("@city").Value = Row.City
            .ExecuteNonQuery()
        End With
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
    SqlCommand sqlCmd;
    SqlParameter sqlParam;

    public override void AcquireConnections(object Transaction)
    {

        connMgr = this.Connections.MyADONETConnectionManager;
        sqlConn = (SqlConnection)connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " +
            "VALUES(@addressid, @city)", sqlConn);
        sqlParam = new SqlParameter("@addressid", SqlDbType.Int);
        sqlCmd.Parameters.Add(sqlParam);
        sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30);
        sqlCmd.Parameters.Add(sqlParam);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {
        {
            sqlCmd.Parameters["@addressid"].Value = Row.AddressID;
            sqlCmd.Parameters["@city"].Value = Row.City;
            sqlCmd.ExecuteNonQuery();
        }
    }

    public override void ReleaseConnections()
    {

        connMgr.ReleaseConnection(sqlConn);

    }

}
```

### <a name="flat-file-destination-example"></a><span data-ttu-id="edada-184">Exemple de destination de fichier plat</span><span class="sxs-lookup"><span data-stu-id="edada-184">Flat File Destination Example</span></span>
 <span data-ttu-id="edada-185">Cet exemple montre un composant de destination qui utilise un gestionnaire de connexions de fichiers plats existant pour enregistrer des données du flux de données dans un fichier plat.</span><span class="sxs-lookup"><span data-stu-id="edada-185">This example demonstrates a destination component that uses an existing Flat File connection manager to save data from the data flow to a flat file.</span></span>

 <span data-ttu-id="edada-186">Si vous souhaitez exécuter cet exemple de code, vous devez configurer le package et le composant comme suit :</span><span class="sxs-lookup"><span data-stu-id="edada-186">If you want to run this sample code, you must configure the package and the component as follows:</span></span>

1.  <span data-ttu-id="edada-187">Créez un gestionnaire de connexions de fichiers plats qui se connecte à un fichier de destination.</span><span class="sxs-lookup"><span data-stu-id="edada-187">Create a Flat File connection manager that connects to a destination file.</span></span> <span data-ttu-id="edada-188">Si le fichier n'existe pas, le composant de destination le crée.</span><span class="sxs-lookup"><span data-stu-id="edada-188">The file does not have to exist; the destination component will create it.</span></span> <span data-ttu-id="edada-189">Configurez le fichier de destination en tant que fichier délimité par des virgules qui contient les colonnes **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="edada-189">Configure the destination file as a comma-delimited file that contains the **AddressID** and **City** columns.</span></span>

2.  <span data-ttu-id="edada-190">Ajoutez un nouveau composant Script à l'aire du concepteur de flux de données et configurez-le en tant que destination.</span><span class="sxs-lookup"><span data-stu-id="edada-190">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>

3.  <span data-ttu-id="edada-191">Connectez la sortie d'une source ou transformation en amont au composant de destination dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)].</span><span class="sxs-lookup"><span data-stu-id="edada-191">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="edada-192">(Vous pouvez connecter une source directement à une destination sans aucune transformation.) Cette sortie doit fournir les données de la table **Person. Address** de l' `AdventureWorks` exemple de base de données et doit contenir au moins les colonnes **AddressID** et **City** .</span><span class="sxs-lookup"><span data-stu-id="edada-192">(You can connect a source directly to a destination without any transformations.) This output should provide data from the **Person.Address** table of the `AdventureWorks` sample database, and should contain at least the **AddressID** and **City** columns.</span></span>

4.  <span data-ttu-id="edada-193">Ouvrez l' **Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="edada-193">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="edada-194">Dans la page **Colonnes d’entrée**, sélectionnez les colonnes **AddressID** et **City**.</span><span class="sxs-lookup"><span data-stu-id="edada-194">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>

5.  <span data-ttu-id="edada-195">Dans la page **Entrées et sorties**, renommez l’entrée en lui attribuant un nom plus descriptif, comme **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="edada-195">On the **Inputs and Outputs** page, rename the input with a more descriptive name, such as **MyAddressInput**.</span></span>

6.  <span data-ttu-id="edada-196">Dans la page **Gestionnaires de connexions**, ajoutez ou créez le gestionnaire de connexions de fichiers plats et attribuez-lui un nom descriptif, par exemple **MyFlatFileDestConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="edada-196">On the **Connection Managers** page, add or create the Flat File connection manager with a descriptive name such as **MyFlatFileDestConnectionManager**.</span></span>

7.  <span data-ttu-id="edada-197">Dans la page **Script** , cliquez sur **Modifier le script** , puis entrez le script suivant.</span><span class="sxs-lookup"><span data-stu-id="edada-197">On the **Script** page, click **Edit Script** and enter the script that follows.</span></span> <span data-ttu-id="edada-198">Ensuite, fermez l'environnement de développement de script.</span><span class="sxs-lookup"><span data-stu-id="edada-198">Then close the script development environment.</span></span>

8.  <span data-ttu-id="edada-199">Fermez l’**Éditeur de transformation de script** et exécutez l’exemple.</span><span class="sxs-lookup"><span data-stu-id="edada-199">Close the **Script Transformation Editor** and run the sample.</span></span>

```vb
Imports System.IO
...
Public Class ScriptMain
    Inherits UserComponent

    Dim copiedAddressFile As String
    Private textWriter As StreamWriter
    Private columnDelimiter As String = ","

    Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

        Dim connMgr As IDTSConnectionManager100 = _
            Me.Connections.MyFlatFileDestConnectionManager
        copiedAddressFile = CType(connMgr.AcquireConnection(Nothing), String)

    End Sub

    Public Overrides Sub PreExecute()

        textWriter = New StreamWriter(copiedAddressFile, False)

    End Sub

    Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)

        With textWriter
            If Not Row.AddressID_IsNull Then
                .Write(Row.AddressID)
            End If
            .Write(columnDelimiter)
            If Not Row.City_IsNull Then
                .Write(Row.City)
            End If
            .WriteLine()
        End With

    End Sub

    Public Overrides Sub PostExecute()

        textWriter.Close()

    End Sub

End Class
```

```csharp
using System.IO;
public class ScriptMain:
    UserComponent

{
    string copiedAddressFile;
    private StreamWriter textWriter;
    private string columnDelimiter = ",";

    public override void AcquireConnections(object Transaction)
    {

        IDTSConnectionManager100 connMgr = this.Connections.MyFlatFileDestConnectionManager;
        copiedAddressFile = (string) connMgr.AcquireConnection(null);

    }

    public override void PreExecute()
    {

        textWriter = new StreamWriter(copiedAddressFile, false);

    }

    public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)
    {

        {
            if (!Row.AddressID_IsNull)
            {
                textWriter.Write(Row.AddressID);
            }
            textWriter.Write(columnDelimiter);
            if (!Row.City_IsNull)
            {
                textWriter.Write(Row.City);
            }
            textWriter.WriteLine();
        }

    }

    public override void PostExecute()
    {

        textWriter.Close();

    }

}
```

<span data-ttu-id="edada-200">![Icône de Integration Services (petite)](../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="edada-200">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="edada-201">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="edada-201">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="edada-202">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="edada-202">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="edada-203">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="edada-203">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="edada-204">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="edada-204">See Also</span></span>
 <span data-ttu-id="edada-205">[Création d’une source avec le composant script](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [développement d’un composant de destination personnalisé](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span><span class="sxs-lookup"><span data-stu-id="edada-205">[Creating a Source with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-source-with-the-script-component.md) [Developing a Custom Destination Component](../extending-packages-custom-objects-data-flow-types/developing-a-custom-destination-component.md)</span></span>


