---
title: Présentation du modèle objet du composant Script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], object model
ms.assetid: 2a0aae82-39cc-4423-b09a-72d2f61033bd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a11556b00efc5749e8ddb895712d6c61f2459d8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604641"
---
# <a name="understanding-the-script-component-object-model"></a><span data-ttu-id="49bda-102">Présentation du modèle objet du composant Script</span><span class="sxs-lookup"><span data-stu-id="49bda-102">Understanding the Script Component Object Model</span></span>
  <span data-ttu-id="49bda-103">Comme indiqué dans [codage et débogage du composant Script] (.. /Extending-packages-Scripting/Data-Flow-script-Component/Coding-and-Debugging-the-script-Component.MD, le projet de composant script contient trois éléments de projet :</span><span class="sxs-lookup"><span data-stu-id="49bda-103">As discussed in [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md, the Script component project contains three project items:</span></span>

1.  <span data-ttu-id="49bda-104">L'élément `ScriptMain`, qui contient la classe `ScriptMain` dans laquelle vous écrivez votre code.</span><span class="sxs-lookup"><span data-stu-id="49bda-104">The `ScriptMain` item, which contains the `ScriptMain` class in which you write your code.</span></span> <span data-ttu-id="49bda-105">La classe `ScriptMain` hérite de la classe `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="49bda-105">The `ScriptMain` class inherits from the `UserComponent` class.</span></span>

2.  <span data-ttu-id="49bda-106">L'élément `ComponentWrapper`, qui contient la classe `UserComponent`, une instance de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> contenant les méthodes et les propriétés qui permettent de traiter les données et d'interagir avec le package.</span><span class="sxs-lookup"><span data-stu-id="49bda-106">The `ComponentWrapper` item, which contains the `UserComponent` class, an instance of <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> that contains the methods and properties that you will use to process data and to interact with the package.</span></span> <span data-ttu-id="49bda-107">L'élément `ComponentWrapper` contient également des classes de collection `Connections` et `Variables`.</span><span class="sxs-lookup"><span data-stu-id="49bda-107">The `ComponentWrapper` item also contains `Connections` and `Variables` collection classes.</span></span>

3.  <span data-ttu-id="49bda-108">L'élément `BufferWrapper`, qui contient des classes qui héritent de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> pour chaque entrée et sortie, et des propriétés typées pour chaque colonne.</span><span class="sxs-lookup"><span data-stu-id="49bda-108">The `BufferWrapper` item, which contains classes that inherits from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> for each input and output, and typed properties for each column.</span></span>

 <span data-ttu-id="49bda-109">Les objets, méthodes et propriétés présentés dans cette rubrique vous permettent d'écrire du code dans l'élément `ScriptMain`.</span><span class="sxs-lookup"><span data-stu-id="49bda-109">As you write your code in the `ScriptMain` item, you will use the objects, methods, and properties discussed in this topic.</span></span> <span data-ttu-id="49bda-110">Chaque composant n'utilise pas toutes les méthodes répertoriées ici ; cependant, lorsque ces méthodes sont utilisées, elles le sont dans l'ordre indiqué.</span><span class="sxs-lookup"><span data-stu-id="49bda-110">Each component will not use all the methods listed here; however, when used, they are used in the sequence shown.</span></span>

 <span data-ttu-id="49bda-111">La classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> ne contient pas de code d'implémentation pour les méthodes présentées dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="49bda-111">The <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class does not contain any implementation code for the methods discussed in this topic.</span></span> <span data-ttu-id="49bda-112">Il est donc inutile, mais sans conséquence, d'ajouter un appel à l'implémentation de la classe de base à votre propre implémentation de la méthode.</span><span class="sxs-lookup"><span data-stu-id="49bda-112">Therefore it is unnecessary, but harmless, to add a call to the base class implementation to your own implementation of the method.</span></span>

 <span data-ttu-id="49bda-113">Pour plus d’informations sur l’utilisation des méthodes et des propriétés de ces classes dans un type de composant Script particulier, consultez la section [Autres exemples de composants Script](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span><span class="sxs-lookup"><span data-stu-id="49bda-113">For information about how to use the methods and properties of these classes in a particular type of Script component, see the section [Additional Script Component Examples](../../extending-packages-scripting-data-flow-script-component-examples/additional-script-component-examples.md).</span></span> <span data-ttu-id="49bda-114">Les rubriques d'exemples contiennent également des exemples de code complets.</span><span class="sxs-lookup"><span data-stu-id="49bda-114">The example topics also contain complete code samples.</span></span>

## <a name="acquireconnections-method"></a><span data-ttu-id="49bda-115">Méthode AcquireConnections</span><span class="sxs-lookup"><span data-stu-id="49bda-115">AcquireConnections Method</span></span>
 <span data-ttu-id="49bda-116">Généralement, les sources et les destinations doivent se connecter à une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="49bda-116">Sources and destinations generally must connect to an external data source.</span></span> <span data-ttu-id="49bda-117">Substituez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> pour extraire la connexion ou les informations de connexion du gestionnaire de connexions approprié.</span><span class="sxs-lookup"><span data-stu-id="49bda-117">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to retrieve the connection or the connection information from the appropriate connection manager.</span></span>

 <span data-ttu-id="49bda-118">L'exemple suivant retourne `System.Data.SqlClient.SqlConnection` à partir d'un gestionnaire de connexions ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="49bda-118">The following example returns a `System.Data.SqlClient.SqlConnection` from an ADO.NET connection manager.</span></span>

```vb
Dim connMgr As IDTSConnectionManager100
Dim sqlConn As SqlConnection

Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    connMgr = Me.Connections.MyADONETConnection
    sqlConn = CType(connMgr.AcquireConnection(Nothing), SqlConnection)

End Sub
```

 <span data-ttu-id="49bda-119">L'exemple suivant retourne un chemin d'accès complet et un nom de fichier à partir d'un gestionnaire de connexions de fichiers plats, puis ouvre le fichier à l'aide de `System.IO.StreamReader`.</span><span class="sxs-lookup"><span data-stu-id="49bda-119">The following example returns a complete path and file name from a Flat File Connection Manager, and then opens the file by using a `System.IO.StreamReader`.</span></span>

```vb
Private textReader As StreamReader
Public Overrides Sub AcquireConnections(ByVal Transaction As Object)

    Dim connMgr As IDTSConnectionManager100 = _
        Me.Connections.MyFlatFileSrcConnectionManager
    Dim exportedAddressFile As String = _
        CType(connMgr.AcquireConnection(Nothing), String)
    textReader = New StreamReader(exportedAddressFile)

End Sub
```

## <a name="preexecute-method"></a><span data-ttu-id="49bda-120">Méthode PreExecute</span><span class="sxs-lookup"><span data-stu-id="49bda-120">PreExecute Method</span></span>
 <span data-ttu-id="49bda-121">Substituez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> lorsque vous devez effectuer un traitement une seule fois avant d'entamer le traitement des lignes de données.</span><span class="sxs-lookup"><span data-stu-id="49bda-121">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PreExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only before you start processing rows of data.</span></span> <span data-ttu-id="49bda-122">Par exemple, dans une destination, vous pouvez configurer la commande paramétrable que la destination utilise pour insérer chaque ligne de données dans la source de données.</span><span class="sxs-lookup"><span data-stu-id="49bda-122">For example, in a destination, you may want to configure the parameterized command that the destination will use to insert each row of data into the data source.</span></span>

```vb
    Dim sqlConn As SqlConnection
    Dim sqlCmd As SqlCommand
    Dim sqlParam As SqlParameter
...
    Public Overrides Sub PreExecute()

        sqlCmd = New SqlCommand("INSERT INTO Person.Address2(AddressID, City) " & _
            "VALUES(@addressid, @city)", sqlConn)
        sqlParam = New SqlParameter("@addressid", SqlDbType.Int)
        sqlCmd.Parameters.Add(sqlParam)
        sqlParam = New SqlParameter("@city", SqlDbType.NVarChar, 30)
        sqlCmd.Parameters.Add(sqlParam)

    End Sub
```

```csharp
SqlConnection sqlConn; 
SqlCommand sqlCmd; 
SqlParameter sqlParam; 

public override void PreExecute() 
{ 

    sqlCmd = new SqlCommand("INSERT INTO Person.Address2(AddressID, City) " + "VALUES(@addressid, @city)", sqlConn); 
    sqlParam = new SqlParameter("@addressid", SqlDbType.Int); 
    sqlCmd.Parameters.Add(sqlParam); 
    sqlParam = new SqlParameter("@city", SqlDbType.NVarChar, 30); 
    sqlCmd.Parameters.Add(sqlParam); 

}
```

## <a name="processing-inputs-and-outputs"></a><span data-ttu-id="49bda-123">Traitement des entrées et des sorties</span><span class="sxs-lookup"><span data-stu-id="49bda-123">Processing Inputs and Outputs</span></span>

### <a name="processing-inputs"></a><span data-ttu-id="49bda-124">Traitement des entrées</span><span class="sxs-lookup"><span data-stu-id="49bda-124">Processing Inputs</span></span>
 <span data-ttu-id="49bda-125">Les composants Script configurés en tant que transformations ou destinations possèdent une entrée.</span><span class="sxs-lookup"><span data-stu-id="49bda-125">Script components that are configured as transformations or destinations have one input.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="49bda-126">Composants fournis par l'élément de projet BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="49bda-126">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="49bda-127">Pour chaque entrée configurée, l'élément de projet `BufferWrapper` contient une classe qui dérive de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> et qui porte le même nom que l'entrée.</span><span class="sxs-lookup"><span data-stu-id="49bda-127">For each input that you have configured, the `BufferWrapper` project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the input.</span></span> <span data-ttu-id="49bda-128">Chaque classe de mémoire tampon d'entrée contient les propriétés, fonctions et méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="49bda-128">Each input buffer class contains the following properties, functions, and methods:</span></span>

-   <span data-ttu-id="49bda-129">Des propriétés d'accesseur typées et nommées pour chaque colonne d'entrée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="49bda-129">Named, typed accessor properties for each selected input column.</span></span> <span data-ttu-id="49bda-130">Ces propriétés sont en lecture seule ou en lecture/écriture selon le **Type d’utilisation** spécifié pour la colonne dans la page **Colonnes d’entrée** de l’**Éditeur de transformation de script**.</span><span class="sxs-lookup"><span data-stu-id="49bda-130">These properties are read-only or read/write depending on the **Usage Type** specified for the column on the **Input Columns** page of the **Script Transformation Editor**.</span></span>

-   <span data-ttu-id="49bda-131">Une propriété **\<column>_IsNull** pour chaque colonne d’entrée sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="49bda-131">A **\<column>_IsNull** property for each selected input column.</span></span> <span data-ttu-id="49bda-132">Cette propriété est également en lecture seule ou en lecture/écriture selon le **Type d’utilisation** spécifié pour la colonne.</span><span class="sxs-lookup"><span data-stu-id="49bda-132">This property is also read-only or read/write depending on the **Usage Type** specified for the column.</span></span>

-   <span data-ttu-id="49bda-133">Une méthode **DirectRowTo\<outputbuffer>** pour chaque sortie configurée.</span><span class="sxs-lookup"><span data-stu-id="49bda-133">A **DirectRowTo\<outputbuffer>** method for each configured output.</span></span> <span data-ttu-id="49bda-134">Vous utilisez ces méthodes lorsque vous filtrez des lignes vers l'une des multiples sorties dans le même `ExclusionGroup`.</span><span class="sxs-lookup"><span data-stu-id="49bda-134">You will use these methods when filtering rows to one of several outputs in the same `ExclusionGroup`.</span></span>

-   <span data-ttu-id="49bda-135">Une fonction `NextRow` pour récupérer la ligne d'entrée suivante et une fonction `EndOfRowset` pour déterminer si la dernière mémoire tampon de données a été traitée.</span><span class="sxs-lookup"><span data-stu-id="49bda-135">A `NextRow` function to get the next input row, and an `EndOfRowset` function to determine whether the last buffer of data has been processed.</span></span> <span data-ttu-id="49bda-136">Généralement, vous n'avez pas besoin de ces fonctions lorsque vous exécutez les méthodes de traitement d'entrée implémentées dans la classe de base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="49bda-136">You typically do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span> <span data-ttu-id="49bda-137">La section suivante fournit des informations supplémentaires sur la classe de base `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="49bda-137">The next section provides more information about the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="49bda-138">Composants fournis par l'élément de projet ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="49bda-138">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="49bda-139">L'élément de projet ComponentWrapper contient une classe nommée `UserComponent` dérivée de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="49bda-139">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="49bda-140">La classe `ScriptMain` dans laquelle vous écrivez votre code personnalisé dérive à son tour de `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="49bda-140">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="49bda-141">La classe `UserComponent` contient les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="49bda-141">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="49bda-142">Une implémentation substituée de la méthode `ProcessInput`.</span><span class="sxs-lookup"><span data-stu-id="49bda-142">An overridden implementation of the `ProcessInput` method.</span></span> <span data-ttu-id="49bda-143">Il s'agit de la méthode que le moteur de flux de données appelle au moment de l'exécution, juste après la méthode `PreExecute`. Elle peut être appelée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="49bda-143">This is the method that the data flow engine calls next at run time after the `PreExecute` method, and it may be called multiple times.</span></span> <span data-ttu-id="49bda-144">`ProcessInput`transfère le traitement à la méthode \*\* \<inputbuffer> _ProcessInput\*\* .</span><span class="sxs-lookup"><span data-stu-id="49bda-144">`ProcessInput` hands off processing to the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="49bda-145">La méthode `ProcessInput` recherche ensuite la fin de la mémoire tampon d'entrée et si elle la trouve, appelle la méthode `FinishOutputs` substituable et la méthode `MarkOutputsAsFinished` privée.</span><span class="sxs-lookup"><span data-stu-id="49bda-145">Then the `ProcessInput` method checks for the end of the input buffer and, if the end of the buffer has been reached, calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="49bda-146">Puis, la méthode `MarkOutputsAsFinished` appelle `SetEndOfRowset` sur la dernière mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="49bda-146">The `MarkOutputsAsFinished` method then calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="49bda-147">Une implémentation substituable de la méthode **\<inputbuffer>_ProcessInput**</span><span class="sxs-lookup"><span data-stu-id="49bda-147">An overridable implementation of the **\<inputbuffer>_ProcessInput** method.</span></span> <span data-ttu-id="49bda-148">Cette implémentation par défaut parcourt simplement chaque ligne d’entrée et appelle **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="49bda-148">This default implementation simply loops through each input row and calls **\<inputbuffer>_ProcessInputRow**.</span></span>

-   <span data-ttu-id="49bda-149">Une implémentation substituable de la méthode **\<inputbuffer>_ProcessInputRow**.</span><span class="sxs-lookup"><span data-stu-id="49bda-149">An overridable implementation of the **\<inputbuffer>_ProcessInputRow** method.</span></span> <span data-ttu-id="49bda-150">L'implémentation par défaut est vide.</span><span class="sxs-lookup"><span data-stu-id="49bda-150">The default implementation is empty.</span></span> <span data-ttu-id="49bda-151">Il s'agit normalement de la méthode que vous devez substituer pour écrire votre code de traitement de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="49bda-151">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="49bda-152">Opérations à effectuer par votre code personnalisé</span><span class="sxs-lookup"><span data-stu-id="49bda-152">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="49bda-153">Vous pouvez utiliser les méthodes suivantes pour traiter l'entrée dans la classe `ScriptMain` :</span><span class="sxs-lookup"><span data-stu-id="49bda-153">You can use the following methods to process input in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="49bda-154">Substituez **\<inputbuffer>_ProcessInputRow** pour traiter les données sur chaque ligne d’entrée lors de leur transfert.</span><span class="sxs-lookup"><span data-stu-id="49bda-154">Override **\<inputbuffer>_ProcessInputRow** to process the data in each input row as it passes through.</span></span>

-   <span data-ttu-id="49bda-155">Substituez **\<inputbuffer>_ProcessInput** uniquement si vous devez effectuer une autre opération pendant que vous parcourez les lignes d’entrée,</span><span class="sxs-lookup"><span data-stu-id="49bda-155">Override **\<inputbuffer>_ProcessInput** only if you have to do something additional while looping through input rows.</span></span> <span data-ttu-id="49bda-156">(Par exemple, vous devez tester pour que `EndOfRowset` effectue une autre action une fois que toutes les lignes ont été traitées.) Appelez \*\* \<inputbuffer> _ProcessInputRow\*\* pour effectuer le traitement de ligne.</span><span class="sxs-lookup"><span data-stu-id="49bda-156">(For example, you have to test for `EndOfRowset` to take some other action after all rows have been processed.) Call **\<inputbuffer>_ProcessInputRow** to perform the row processing.</span></span>

-   <span data-ttu-id="49bda-157">Substituez `FinishOutputs` si vous devez effectuer une opération sur les sorties avant leur fermeture.</span><span class="sxs-lookup"><span data-stu-id="49bda-157">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="49bda-158">La méthode `ProcessInput` garantit que ces méthodes sont appelées aux moments appropriés.</span><span class="sxs-lookup"><span data-stu-id="49bda-158">The `ProcessInput` method ensures that these methods are called at the appropriate times.</span></span>

### <a name="processing-outputs"></a><span data-ttu-id="49bda-159">Traitement des sorties</span><span class="sxs-lookup"><span data-stu-id="49bda-159">Processing Outputs</span></span>
 <span data-ttu-id="49bda-160">Les composants Script configurés en tant que sources ou transformations possèdent une ou plusieurs sorties.</span><span class="sxs-lookup"><span data-stu-id="49bda-160">Script components configured as sources or transformations have one or more outputs.</span></span>

#### <a name="what-the-bufferwrapper-project-item-provides"></a><span data-ttu-id="49bda-161">Composants fournis par l'élément de projet BufferWrapper</span><span class="sxs-lookup"><span data-stu-id="49bda-161">What the BufferWrapper Project Item Provides</span></span>
 <span data-ttu-id="49bda-162">Pour chaque sortie configurée, l'élément de projet BufferWrapper contient une classe qui dérive de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> et qui porte le même nom que la sortie.</span><span class="sxs-lookup"><span data-stu-id="49bda-162">For each output that you have configured, the BufferWrapper project item contains a class that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptBuffer> and has the same name as the output.</span></span> <span data-ttu-id="49bda-163">Chaque classe de mémoire tampon d'entrée contient les propriétés et méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="49bda-163">Each input buffer class contains the following properties and methods:</span></span>

-   <span data-ttu-id="49bda-164">Des propriétés d'accesseur nommées, typées et en écriture seule pour chaque colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="49bda-164">Named, typed, write-only accessor properties for each output column.</span></span>

-   <span data-ttu-id="49bda-165">Propriété \*\* \<column> _IsNull\*\* en écriture seule pour chaque colonne de sortie sélectionnée que vous pouvez utiliser pour affecter la valeur à la colonne `null` .</span><span class="sxs-lookup"><span data-stu-id="49bda-165">A write-only **\<column>_IsNull** property for each selected output column that you can use to set the column value to `null`.</span></span>

-   <span data-ttu-id="49bda-166">Une méthode `AddRow` pour ajouter une ligne vide à la mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="49bda-166">An `AddRow` method to add an empty new row to the output buffer.</span></span>

-   <span data-ttu-id="49bda-167">Une méthode `SetEndOfRowset` pour indiquer au moteur de flux de données qu'aucune mémoire tampon de données supplémentaires n'est attendue.</span><span class="sxs-lookup"><span data-stu-id="49bda-167">A `SetEndOfRowset` method to let the data flow engine know that no more buffers of data are expected.</span></span> <span data-ttu-id="49bda-168">Il existe également une fonction `EndOfRowset` pour déterminer si la mémoire tampon active est la dernière mémoire tampon de données.</span><span class="sxs-lookup"><span data-stu-id="49bda-168">There is also an `EndOfRowset` function to determine whether the current buffer is the last buffer of data.</span></span> <span data-ttu-id="49bda-169">En général, vous n’avez pas besoin de ces fonctions lorsque vous utilisez les méthodes de traitement d’entrée implémentées dans la `UserComponent` classe de base.</span><span class="sxs-lookup"><span data-stu-id="49bda-169">You generally do not need these functions when you use the input processing methods implemented in the `UserComponent` base class.</span></span>

#### <a name="what-the-componentwrapper-project-item-provides"></a><span data-ttu-id="49bda-170">Composants fournis par l'élément de projet ComponentWrapper</span><span class="sxs-lookup"><span data-stu-id="49bda-170">What the ComponentWrapper Project Item Provides</span></span>
 <span data-ttu-id="49bda-171">L'élément de projet ComponentWrapper contient une classe nommée `UserComponent` dérivée de <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span><span class="sxs-lookup"><span data-stu-id="49bda-171">The ComponentWrapper project item contains a class named `UserComponent` that derives from <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent>.</span></span> <span data-ttu-id="49bda-172">La classe `ScriptMain` dans laquelle vous écrivez votre code personnalisé dérive à son tour de `UserComponent`.</span><span class="sxs-lookup"><span data-stu-id="49bda-172">The `ScriptMain` class in which you write your custom code derives in turn from `UserComponent`.</span></span> <span data-ttu-id="49bda-173">La classe `UserComponent` contient les méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="49bda-173">The `UserComponent` class contains the following methods:</span></span>

-   <span data-ttu-id="49bda-174">Une implémentation substituée de la méthode `PrimeOutput`.</span><span class="sxs-lookup"><span data-stu-id="49bda-174">An overridden implementation of the `PrimeOutput` method.</span></span> <span data-ttu-id="49bda-175">Le moteur de flux de données appelle cette méthode avant `ProcessInput` au moment de l'exécution. La méthode est appelée une seule fois.</span><span class="sxs-lookup"><span data-stu-id="49bda-175">The data flow engine calls this method before `ProcessInput` at run time, and it is only called one time.</span></span> <span data-ttu-id="49bda-176">`PrimeOutput` fait appel à la méthode `CreateNewOutputRows` pour effectuer le traitement.</span><span class="sxs-lookup"><span data-stu-id="49bda-176">`PrimeOutput` hands off processing to the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="49bda-177">Puis, si le composant est une source (autrement dit, le composant ne possède pas d'entrée), `PrimeOutput` appelle la méthode `FinishOutputs` substituable et la méthode `MarkOutputsAsFinished` privée.</span><span class="sxs-lookup"><span data-stu-id="49bda-177">Then, if the component is a source (that is, the component has no inputs), `PrimeOutput` calls the overridable `FinishOutputs` method and the private `MarkOutputsAsFinished` method.</span></span> <span data-ttu-id="49bda-178">La méthode `MarkOutputsAsFinished` appelle `SetEndOfRowset` sur la dernière mémoire tampon de sortie.</span><span class="sxs-lookup"><span data-stu-id="49bda-178">The `MarkOutputsAsFinished` method calls `SetEndOfRowset` on the last output buffer.</span></span>

-   <span data-ttu-id="49bda-179">Une implémentation substituable de la méthode `CreateNewOutputRows`.</span><span class="sxs-lookup"><span data-stu-id="49bda-179">An overridable implementation of the `CreateNewOutputRows` method.</span></span> <span data-ttu-id="49bda-180">L'implémentation par défaut est vide.</span><span class="sxs-lookup"><span data-stu-id="49bda-180">The default implementation is empty.</span></span> <span data-ttu-id="49bda-181">Il s'agit normalement de la méthode que vous devez substituer pour écrire votre code de traitement de données personnalisé.</span><span class="sxs-lookup"><span data-stu-id="49bda-181">This is the method that you will normally override to write your custom data processing code.</span></span>

#### <a name="what-your-custom-code-should-do"></a><span data-ttu-id="49bda-182">Opérations à effectuer par votre code personnalisé</span><span class="sxs-lookup"><span data-stu-id="49bda-182">What Your Custom Code Should Do</span></span>
 <span data-ttu-id="49bda-183">Vous pouvez utiliser les méthodes suivantes pour traiter les sorties dans la classe `ScriptMain` :</span><span class="sxs-lookup"><span data-stu-id="49bda-183">You can use the following methods to process outputs in the `ScriptMain` class:</span></span>

-   <span data-ttu-id="49bda-184">Substituez `CreateNewOutputRows` uniquement lorsque vous pouvez ajouter et remplir des lignes de sortie avant de traiter des lignes d'entrée.</span><span class="sxs-lookup"><span data-stu-id="49bda-184">Override `CreateNewOutputRows` only when you can add and populate output rows before processing input rows.</span></span> <span data-ttu-id="49bda-185">Par exemple, vous pouvez utiliser `CreateNewOutputRows` dans une source, mais dans une transformation à sorties asynchrones, vous devez appeler `AddRow` pendant ou après le traitement des données d'entrée.</span><span class="sxs-lookup"><span data-stu-id="49bda-185">For example, you can use `CreateNewOutputRows` in a source, but in a transformation with asynchronous outputs, you should call `AddRow` during or after the processing of input data.</span></span>

-   <span data-ttu-id="49bda-186">Substituez `FinishOutputs` si vous devez effectuer une opération sur les sorties avant leur fermeture.</span><span class="sxs-lookup"><span data-stu-id="49bda-186">Override `FinishOutputs` if you have to do something to the outputs before they are closed.</span></span>

 <span data-ttu-id="49bda-187">La méthode `PrimeOutput` garantit que ces méthodes sont appelées aux moments appropriés.</span><span class="sxs-lookup"><span data-stu-id="49bda-187">The `PrimeOutput` method ensures that these methods are called at the appropriate times.</span></span>

## <a name="postexecute-method"></a><span data-ttu-id="49bda-188">Méthode PostExecute</span><span class="sxs-lookup"><span data-stu-id="49bda-188">PostExecute Method</span></span>
 <span data-ttu-id="49bda-189">Substituez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> lorsque vous devez effectuer un traitement une seule fois après avoir traité les lignes de données.</span><span class="sxs-lookup"><span data-stu-id="49bda-189">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.PostExecute%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class whenever you have processing that you must perform one time only after you have processed the rows of data.</span></span> <span data-ttu-id="49bda-190">Par exemple, dans une source, vous pouvez fermer `System.Data.SqlClient.SqlDataReader` qui vous a permis de charger des données dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="49bda-190">For example, in a source, you may want to close the `System.Data.SqlClient.SqlDataReader` that you have used to load data into the data flow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="49bda-191">La collection de `ReadWriteVariables` est uniquement disponible dans la méthode `PostExecute`.</span><span class="sxs-lookup"><span data-stu-id="49bda-191">The collection of `ReadWriteVariables` is available only in the `PostExecute` method.</span></span> <span data-ttu-id="49bda-192">Par conséquent, vous ne pouvez pas incrémenter directement la valeur d'une variable de package à mesure que vous traitez chaque ligne de données.</span><span class="sxs-lookup"><span data-stu-id="49bda-192">Therefore you cannot directly increment the value of a package variable as you process each row of data.</span></span> <span data-ttu-id="49bda-193">Incrémentez plutôt la valeur d'une variable locale, puis attribuez à la variable de package la valeur de la variable locale dans la méthode `PostExecute` une fois que toutes les données ont été traitées.</span><span class="sxs-lookup"><span data-stu-id="49bda-193">Instead, increment the value of a local variable, and set the value of the package variable to the value of the local variable in the `PostExecute` method after all data has been processed.</span></span>

## <a name="releaseconnections-method"></a><span data-ttu-id="49bda-194">Méthode ReleaseConnections</span><span class="sxs-lookup"><span data-stu-id="49bda-194">ReleaseConnections Method</span></span>
 <span data-ttu-id="49bda-195">Généralement, les sources et les destinations doivent se connecter à une source de données externe.</span><span class="sxs-lookup"><span data-stu-id="49bda-195">Sources and destinations typically must connect to an external data source.</span></span> <span data-ttu-id="49bda-196">Substituez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> de la classe de base <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> pour fermer et libérer la connexion que vous avez ouverte précédemment dans la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A>.</span><span class="sxs-lookup"><span data-stu-id="49bda-196">Override the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.ReleaseConnections%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent> base class to close and release the connection that you have opened previously in the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.AcquireConnections%2A> method.</span></span>

```vb
    Dim connMgr As IDTSConnectionManager100
...
    Public Overrides Sub ReleaseConnections()

        connMgr.ReleaseConnection(sqlConn)

    End Sub
```

```csharp
IDTSConnectionManager100 connMgr;

public override void ReleaseConnections()
{

    connMgr.ReleaseConnection(sqlConn);

}
```

<span data-ttu-id="49bda-197">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="49bda-197">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="49bda-198">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="49bda-198">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="49bda-199">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="49bda-199">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="49bda-200">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="49bda-200">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="49bda-201">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49bda-201">See Also</span></span>
 <span data-ttu-id="49bda-202">[Configuration du composant script dans l’éditeur de composant de script](configuring-the-script-component-in-the-script-component-editor.md) [codage et débogage du composant Script] (.. /extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span><span class="sxs-lookup"><span data-stu-id="49bda-202">[Configuring the Script Component in the Script Component Editor](configuring-the-script-component-in-the-script-component-editor.md) [Coding and Debugging the Script Component](../extending-packages-scripting/data-flow-script-component/coding-and-debugging-the-script-component.md</span></span>


