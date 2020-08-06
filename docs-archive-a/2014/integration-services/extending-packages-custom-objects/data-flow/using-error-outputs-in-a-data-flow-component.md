---
title: Utilisation de sorties d’erreur dans un composant de flux de données | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- errors [Integration Services], alternative outputs
- synchronous error outputs [Integration Services]
- alternative error outputs [Integration Services]
- custom data flow components [Integration Services], error outputs
- data flow components [Integration Services], error outputs
- populating error columns [Integration Services]
- redirecting error output [Integration Services]
- error outputs [Integration Services]
- asynchronous error outputs [Integration Services]
ms.assetid: a2a3e7c8-1de2-45b3-97fb-60415d3b0934
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a05a41065c52fadbe7f7fc065771727310e58149
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600149"
---
# <a name="using-error-outputs-in-a-data-flow-component"></a><span data-ttu-id="585f3-102">Utilisation de sorties d'erreur dans un composant de flux de données</span><span class="sxs-lookup"><span data-stu-id="585f3-102">Using Error Outputs in a Data Flow Component</span></span>
  <span data-ttu-id="585f3-103">Il est possible d'ajouter des objets <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> spéciaux appelés sorties d'erreur à des composants afin de permettre à un composant de rediriger les lignes qu'il ne parvient pas à traiter pendant l'exécution.</span><span class="sxs-lookup"><span data-stu-id="585f3-103">Special <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100> objects called error outputs can be added to components to let the component redirect rows that it cannot process during execution.</span></span> <span data-ttu-id="585f3-104">Les problèmes qu'un composant peut rencontrer sont en général classés en tant qu'erreurs ou troncations et sont propres à chaque composant.</span><span class="sxs-lookup"><span data-stu-id="585f3-104">The problems a component may encounter are generally categorized as errors or truncations, and are specific to each component.</span></span> <span data-ttu-id="585f3-105">Les composants qui fournissent des sorties d'erreur offrent à leurs utilisateurs la flexibilité de gérer les conditions d'erreur en filtrant les lignes d'erreur du jeu de résultats, en provoquant l'échec du composant lorsqu'un problème se produit ou en ignorant des erreurs afin de continuer.</span><span class="sxs-lookup"><span data-stu-id="585f3-105">Components that provide error outputs give users of the component the flexibility to handle error conditions by filtering error rows out of the result set, by failing the component when a problem occurs, or by ignoring errors and continuing.</span></span>  
  
 <span data-ttu-id="585f3-106">Pour implémenter et prendre en charge les sorties d'erreur dans un composant, vous devez d'abord attribuer à la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.UsesDispositions%2A> du composant la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="585f3-106">To implement and support error outputs in a component, you must first set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.UsesDispositions%2A> property of the component to `true`.</span></span> <span data-ttu-id="585f3-107">Ensuite, vous devez ajouter une sortie au composant dont la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> a pour valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="585f3-107">Then you must add an output to the component that has its <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> property set to `true`.</span></span> <span data-ttu-id="585f3-108">Enfin, le composant doit contenir un code qui redirige les lignes vers la sortie d'erreur lorsque des erreurs ou troncations se produisent.</span><span class="sxs-lookup"><span data-stu-id="585f3-108">Finally, the component must contain code that redirects rows to the error output when errors or truncations occur.</span></span> <span data-ttu-id="585f3-109">Cette rubrique couvre ces trois étapes et explique les différences entre les sorties d'erreur synchrones et asynchrones.</span><span class="sxs-lookup"><span data-stu-id="585f3-109">This topic covers these three steps and explains the differences between synchronous and asynchronous error outputs.</span></span>  
  
## <a name="creating-an-error-output"></a><span data-ttu-id="585f3-110">Création d'une sortie d'erreur</span><span class="sxs-lookup"><span data-stu-id="585f3-110">Creating an Error Output</span></span>  
 <span data-ttu-id="585f3-111">Vous créez une sortie d'erreur en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100.New%2A> de la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.OutputCollection%2A>, puis en attribuant à la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> de la nouvelle sortie la valeur `true`.</span><span class="sxs-lookup"><span data-stu-id="585f3-111">You create an error output by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputCollection100.New%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.OutputCollection%2A>, and then setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.IsErrorOut%2A> property of the new output to `true`.</span></span> <span data-ttu-id="585f3-112">Si la sortie est asynchrone, vous n'avez rien d'autre à lui faire.</span><span class="sxs-lookup"><span data-stu-id="585f3-112">If the output is asynchronous, nothing else must be done to the output.</span></span> <span data-ttu-id="585f3-113">Si la sortie est synchrone, et qu'il existe une autre sortie synchrone avec la même entrée, vous devez également définir les propriétés <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExclusionGroup%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A>.</span><span class="sxs-lookup"><span data-stu-id="585f3-113">If the output is synchronous, and there is another output that is synchronous to the same input, you must also set the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.ExclusionGroup%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutput100.SynchronousInputID%2A> properties.</span></span> <span data-ttu-id="585f3-114">Ces deux propriétés doivent avoir les mêmes valeurs que l'autre sortie synchrone avec la même entrée.</span><span class="sxs-lookup"><span data-stu-id="585f3-114">Both properties should have the same values as the other output that is synchronous to the same input.</span></span> <span data-ttu-id="585f3-115">Si ces propriétés ne sont pas définies sur une valeur différente de zéro, les lignes fournies par l'entrée sont envoyées aux deux sorties synchrones avec l'entrée.</span><span class="sxs-lookup"><span data-stu-id="585f3-115">If these properties are not set to a non-zero value, the rows provided by the input are sent to both outputs that are synchronous to the input.</span></span>  
  
 <span data-ttu-id="585f3-116">Lorsqu'un composant rencontre une erreur ou troncation pendant l'exécution, il continue selon les paramètres des propriétés <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ErrorRowDisposition%2A> et <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.TruncationRowDisposition%2A> de l'entrée ou la sortie, ou de l'entrée ou la colonne de sortie, dans laquelle l'erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="585f3-116">When a component encounters an error or truncation during execution, it proceeds based on the settings of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.ErrorRowDisposition%2A> and <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSInput100.TruncationRowDisposition%2A> properties of the input or output, or input or output column, where the error occurred.</span></span> <span data-ttu-id="585f3-117">La valeur de ces propriétés doit être définie par défaut sur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSRowDisposition.RD_NotUsed>.</span><span class="sxs-lookup"><span data-stu-id="585f3-117">The value of these properties should be set by default to <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.DTSRowDisposition.RD_NotUsed>.</span></span> <span data-ttu-id="585f3-118">Lorsque la sortie d'erreur du composant est connectée à un composant en aval, cette propriété est définie par l'utilisateur du composant et permet à l'utilisateur de contrôler la manière dont le composant gère l'erreur ou la troncation.</span><span class="sxs-lookup"><span data-stu-id="585f3-118">When the error output of the component is connected to a downstream component, this property is set by the user of the component and lets the user control how the component handles the error or truncation.</span></span>  
  
## <a name="populating-error-columns"></a><span data-ttu-id="585f3-119">Remplissage de colonnes d'erreur</span><span class="sxs-lookup"><span data-stu-id="585f3-119">Populating Error Columns</span></span>  
 <span data-ttu-id="585f3-120">Lorsqu'une sortie d'erreur est créée, la tâche de flux de données ajoute automatiquement deux colonnes à la collection de colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="585f3-120">When an error output is created, the data flow task automatically adds two columns to the output column collection.</span></span> <span data-ttu-id="585f3-121">Ces colonnes sont utilisées par les composants pour spécifier l'ID de la colonne qui a provoqué l'erreur ou la troncation, puis pour fournir le code d'erreur spécifique au composant.</span><span class="sxs-lookup"><span data-stu-id="585f3-121">These columns are used by components to specify the ID of the column that caused the error or truncation, and to provide the component-specific error code.</span></span> <span data-ttu-id="585f3-122">Ces colonnes sont générées automatiquement, mais les valeurs qu'elles contiennent doivent être définies par le composant.</span><span class="sxs-lookup"><span data-stu-id="585f3-122">These columns are generated automatically, but the values contained in the columns must be set by the component.</span></span>  
  
 <span data-ttu-id="585f3-123">La méthode utilisée pour définir les valeurs de ces colonnes varie selon que la sortie d'erreur est synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="585f3-123">The method used to set the values of these columns depends on whether the error output is synchronous or asynchronous.</span></span> <span data-ttu-id="585f3-124">Les composants avec des sorties synchrones appellent la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>, décrite de manière plus approfondie dans la section suivante, puis fournissent le code d'erreur et les valeurs de colonnes d'erreur en tant que paramètres.</span><span class="sxs-lookup"><span data-stu-id="585f3-124">Components with synchronous outputs call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method, discussed in more detail in the next section, and provide the error code and error column values as parameters.</span></span> <span data-ttu-id="585f3-125">Les composants avec des sorties asynchrones ont deux possibilités pour définir les valeurs de ces colonnes.</span><span class="sxs-lookup"><span data-stu-id="585f3-125">Components with asynchronous outputs have two choices for setting the values of these columns.</span></span> <span data-ttu-id="585f3-126">Ils peuvent soit appeler la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> du tampon de sortie et fournir les valeurs, soit localiser les colonnes d'erreur dans le tampon à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> et définir directement les valeurs des colonnes.</span><span class="sxs-lookup"><span data-stu-id="585f3-126">They can either call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method of the output buffer and supply the values, or locate the error columns in the buffer by using <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSBufferManager100.FindColumnByLineageID%2A> and set the values for the columns directly.</span></span> <span data-ttu-id="585f3-127">Toutefois, puisque les noms des colonnes ou leur emplacement dans la collection de colonnes de sortie peuvent avoir été modifiés, la seconde méthode risque de ne pas être fiable.</span><span class="sxs-lookup"><span data-stu-id="585f3-127">However, because the names of the columns may have been changed, or their location in the output column collection may have been modified, the latter method may not be reliable.</span></span> <span data-ttu-id="585f3-128">La méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> définit automatiquement les valeurs dans ces colonnes d'erreur sans avoir à les localiser manuellement.</span><span class="sxs-lookup"><span data-stu-id="585f3-128">The <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method automatically sets the values in these error columns without having to locate them manually.</span></span>  
  
 <span data-ttu-id="585f3-129">Si vous devez obtenir la description d'erreur qui correspond à un code d'erreur spécifique, vous pouvez utiliser la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> de l'interface <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>, disponible via la propriété <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> du composant.</span><span class="sxs-lookup"><span data-stu-id="585f3-129">If you need to obtain the error description that corresponds to a specific error code, you can use the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.GetErrorDescription%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface, available through the component's <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.ComponentMetaData%2A> property.</span></span>  
  
 <span data-ttu-id="585f3-130">Les exemples de code suivants présentent un composant qui possède une entrée et deux sorties, dont une sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="585f3-130">The following code examples show a component that has an input and two outputs, including an error output.</span></span> <span data-ttu-id="585f3-131">Le premier exemple indique comment créer une sortie d'erreur synchrone avec l'entrée.</span><span class="sxs-lookup"><span data-stu-id="585f3-131">The first example shows how to create an error output that is synchronous to the input.</span></span> <span data-ttu-id="585f3-132">Le second exemple indique comment créer une sortie d'erreur asynchrone.</span><span class="sxs-lookup"><span data-stu-id="585f3-132">The second example shows how to create an error output that is asynchronous.</span></span>  
  
```csharp  
public override void ProvideComponentProperties()  
{  
    // Specify that the component has an error output.  
    ComponentMetaData.UsesDispositions = true;  
    // Create the input.  
    IDTSInput100 input = ComponentMetaData.InputCollection.New();  
    input.Name = "Input";  
    input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed;  
    input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution.";  
  
    // Create the default output.  
    IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
    output.Name = "Output";  
    output.SynchronousInputID = input.ID;  
    output.ExclusionGroup = 1;  
  
    // Create the error output.  
    IDTSOutput100 errorOutput = ComponentMetaData.OutputCollection.New();  
    errorOutput.IsErrorOut = true;  
    errorOutput.Name = "ErrorOutput";  
    errorOutput.SynchronousInputID = input.ID;  
    errorOutput.ExclusionGroup = 1;  
  
}  
```  
  
```vb  
Public  Overrides Sub ProvideComponentProperties()   
  
 ' Specify that the component has an error output.  
 ComponentMetaData.UsesDispositions = True   
  
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New   
  
 ' Create the input.  
 input.Name = "Input"   
 input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed   
 input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution."   
  
 ' Create the default output.  
 Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 output.Name = "Output"   
 output.SynchronousInputID = input.ID   
 output.ExclusionGroup = 1   
  
 ' Create the error output.  
 Dim errorOutput As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 errorOutput.IsErrorOut = True   
 errorOutput.Name = "ErrorOutput"   
 errorOutput.SynchronousInputID = input.ID   
 errorOutput.ExclusionGroup = 1   
  
End Sub  
```  
  
 <span data-ttu-id="585f3-133">L'exemple de code suivant crée une sortie d'erreur asynchrone.</span><span class="sxs-lookup"><span data-stu-id="585f3-133">The following code example creates an error output that is asynchronous.</span></span>  
  
```csharp  
public override void ProvideComponentProperties()  
{  
    // Specify that the component has an error output.  
    ComponentMetaData.UsesDispositions = true;  
  
    // Create the input.  
    IDTSInput100 input = ComponentMetaData.InputCollection.New();  
    input.Name = "Input";  
    input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed;  
    input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution.";  
  
    // Create the default output.  
    IDTSOutput100 output = ComponentMetaData.OutputCollection.New();  
    output.Name = "Output";  
  
    // Create the error output.  
    IDTSOutput100 errorOutput = ComponentMetaData.OutputCollection.New();  
    errorOutput.Name = "ErrorOutput";  
    errorOutput.IsErrorOut = true;  
}  
```  
  
```vb  
Public  Overrides Sub ProvideComponentProperties()   
  
 ' Specify that the component has an error output.  
 ComponentMetaData.UsesDispositions = True   
  
 ' Create the input.  
 Dim input As IDTSInput100 = ComponentMetaData.InputCollection.New   
  
 ' Create the default output.  
 input.Name = "Input"   
 input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed   
 input.ErrorOrTruncationOperation = "A string describing the possible error or truncation that may occur during execution."   
  
 ' Create the error output.  
 Dim output As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 output.Name = "Output"   
 Dim errorOutput As IDTSOutput100 = ComponentMetaData.OutputCollection.New   
 errorOutput.Name = "ErrorOutput"   
 errorOutput.IsErrorOut = True   
  
End Sub  
```  
  
## <a name="redirecting-a-row-to-an-error-output"></a><span data-ttu-id="585f3-134">Redirection d'une ligne vers une sortie d'erreur</span><span class="sxs-lookup"><span data-stu-id="585f3-134">Redirecting a Row to an Error Output</span></span>  
 <span data-ttu-id="585f3-135">Après avoir ajouté une sortie d'erreur à un composant, vous devez fournir un code qui gère les conditions d'erreur ou de troncation propres au composant et qui redirige les lignes d'erreur ou de troncation vers la sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="585f3-135">After adding an error output to a component, you must provide code that handles the error or truncation conditions specific to the component and redirects the error or truncation rows to the error output.</span></span> <span data-ttu-id="585f3-136">Vous pouvez procéder de deux manières pour cela, selon que la sortie d'erreur est synchrone ou asynchrone.</span><span class="sxs-lookup"><span data-stu-id="585f3-136">You can do this in two ways, depending on whether the error output is synchronous or asynchronous.</span></span>  
  
### <a name="redirecting-a-row-with-synchronous-outputs"></a><span data-ttu-id="585f3-137">Redirection d'une ligne avec des sorties synchrones</span><span class="sxs-lookup"><span data-stu-id="585f3-137">Redirecting a Row with Synchronous Outputs</span></span>  
 <span data-ttu-id="585f3-138">Les lignes sont envoyées aux sorties synchrones en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> de la classe <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="585f3-138">Rows are sent to synchronous outputs by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer> class.</span></span> <span data-ttu-id="585f3-139">L'appel de méthode inclut en tant que paramètres l'ID de la sortie d'erreur, le code d'erreur défini par le composant et l'index de la colonne que le composant n'a pas pu traiter.</span><span class="sxs-lookup"><span data-stu-id="585f3-139">The method call includes as parameters the ID of the error output, the component-defined error code, and the index of the column that the component was unable to process.</span></span>  
  
 <span data-ttu-id="585f3-140">L'exemple de code suivant montre comment diriger une ligne dans un tampon vers une sortie d'erreur synchrone à l'aide de la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="585f3-140">The following code example demonstrates how to direct a row in a buffer to a synchronous error output using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.DirectErrorRow%2A> method.</span></span>  
  
```csharp  
public override void ProcessInput(int inputID, PipelineBuffer buffer)  
{  
        IDTSInput100 input = ComponentMetaData.InputCollection.GetObjectByID(inputID);  
  
        // This code sample assumes the component has two outputs, one the default,  
        // the other the error output. If the errorOutputIndex returned from GetErrorOutputInfo  
        // is 0, then the default output is the second output in the collection.  
        int defaultOutputID = -1;  
        int errorOutputID = -1;  
        int errorOutputIndex = -1;  
  
        GetErrorOutputInfo(ref errorOutputID,ref errorOutputIndex);  
  
        if (errorOutputIndex == 0)  
            defaultOutputID = ComponentMetaData.OutputCollection[1].ID;  
        else  
            defaultOutputID = ComponentMetaData.OutputCollection[0].ID;  
  
        while (buffer.NextRow())  
        {  
            try  
            {  
                // TODO: Implement code to process the columns in the buffer row.  
  
                // Ideally, your code should detect potential exceptions before they occur, rather  
                // than having a generic try/catch block such as this.   
                // However, because the error or truncation implementation is specific to each component,  
                // this sample focuses on actually directing the row, and not a single error or truncation.  
  
                // Unless an exception occurs, direct the row to the default   
                buffer.DirectRow(defaultOutputID);  
            }  
            catch  
            {  
                // Yes, has the user specified to redirect the row?  
                if (input.ErrorRowDisposition == DTSRowDisposition.RD_RedirectRow)  
                {  
                    // Yes, direct the row to the error output.  
                    // TODO: Add code to include the errorColumnIndex.  
                    buffer.DirectErrorRow(errorOutputID, 0, errorColumnIndex);  
                }  
                else if (input.ErrorRowDisposition == DTSRowDisposition.RD_FailComponent || input.ErrorRowDisposition == DTSRowDisposition.RD_NotUsed)  
                {  
                    // No, the user specified to fail the component, or the error row disposition was not set.  
                    throw new Exception("An error occurred, and the DTSRowDisposition is either not set, or is set to fail component.");  
                }  
                else  
                {  
                    // No, the user specified to ignore the failure so   
                    // direct the row to the default output.  
                    buffer.DirectRow(defaultOutputID);  
                }  
  
            }  
        }  
}  
```  
  
```vb  
Public  Overrides Sub ProcessInput(ByVal inputID As Integer, ByVal buffer As PipelineBuffer)   
   Dim input As IDTSInput100 = ComponentMetaData.InputCollection.GetObjectByID(inputID)   
  
   ' This code sample assumes the component has two outputs, one the default,  
   ' the other the error output. If the errorOutputIndex returned from GetErrorOutputInfo  
   ' is 0, then the default output is the second output in the collection.  
   Dim defaultOutputID As Integer = -1   
   Dim errorOutputID As Integer = -1   
   Dim errorOutputIndex As Integer = -1   
  
   GetErrorOutputInfo(errorOutputID, errorOutputIndex)   
  
   If errorOutputIndex = 0 Then   
     defaultOutputID = ComponentMetaData.OutputCollection(1).ID   
   Else   
     defaultOutputID = ComponentMetaData.OutputCollection(0).ID   
   End If   
  
   While buffer.NextRow   
     Try   
       ' TODO: Implement code to process the columns in the buffer row.  
  
       ' Ideally, your code should detect potential exceptions before they occur, rather  
       ' than having a generic try/catch block such as this.   
       ' However, because the error or truncation implementation is specific to each component,  
       ' this sample focuses on actually directing the row, and not a single error or truncation.  
  
       ' Unless an exception occurs, direct the row to the default   
       buffer.DirectRow(defaultOutputID)   
     Catch   
       ' Yes, has the user specified to redirect the row?  
       If input.ErrorRowDisposition = DTSRowDisposition.RD_RedirectRow Then   
         ' Yes, direct the row to the error output.  
         ' TODO: Add code to include the errorColumnIndex.  
         buffer.DirectErrorRow(errorOutputID, 0, errorColumnIndex)   
       Else   
         If input.ErrorRowDisposition = DTSRowDisposition.RD_FailComponent OrElse input.ErrorRowDisposition = DTSRowDisposition.RD_NotUsed Then   
           ' No, the user specified to fail the component, or the error row disposition was not set.  
           Throw New Exception("An error occurred, and the DTSRowDisposition is either not set, or is set to fail component.")   
         Else   
           ' No, the user specified to ignore the failure so   
           ' direct the row to the default output.  
           buffer.DirectRow(defaultOutputID)   
         End If   
       End If   
     End Try   
   End While   
End Sub  
```  
  
### <a name="redirecting-a-row-with-asynchronous-outputs"></a><span data-ttu-id="585f3-141">Redirection d'une ligne avec des sorties asynchrones</span><span class="sxs-lookup"><span data-stu-id="585f3-141">Redirecting a Row with Asynchronous Outputs</span></span>  
 <span data-ttu-id="585f3-142">Au lieu de diriger des lignes vers une sortie, comme cela est fait avec des sorties d'erreur synchrones, les composants avec des sorties asynchrones envoient une ligne vers une sortie d'erreur en ajoutant explicitement une ligne à la sortie <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span><span class="sxs-lookup"><span data-stu-id="585f3-142">Instead of directing rows to an output, as is done with synchronous error outputs, components with asynchronous outputs send a row to an error output by explicitly adding a row to the output <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer>.</span></span> <span data-ttu-id="585f3-143">L'implémentation d'un composant qui utilise des sorties d'erreur asynchrones implique d'ajouter à la sortie d'erreur des colonnes fournies aux composants en aval et de mettre en cache le tampon de sortie pour la sortie d'erreur fournie au composant pendant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A>.</span><span class="sxs-lookup"><span data-stu-id="585f3-143">Implementing a component that uses asynchronous error outputs requires adding columns to the error output that are provided to downstream components, and caching the output buffer for the error output that is provided to the component during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PrimeOutput%2A> method.</span></span> <span data-ttu-id="585f3-144">L’implémentation d’un composant à sorties asynchrones est décrite en détail dans la rubrique [Développement d’un composant de transformation personnalisé à sorties asynchrones](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span><span class="sxs-lookup"><span data-stu-id="585f3-144">The details of implementing a component with asynchronous outputs are covered in detail in the topic [Developing a Custom Transformation Component with Asynchronous Outputs](../../extending-packages-custom-objects-data-flow-types/developing-a-custom-transformation-component-with-asynchronous-outputs.md).</span></span> <span data-ttu-id="585f3-145">Si les colonnes ne sont pas ajoutées explicitement à la sortie d'erreur, la ligne du tampon ajoutée au tampon de sortie contient uniquement les deux colonnes d'erreur.</span><span class="sxs-lookup"><span data-stu-id="585f3-145">If columns are not explicitly added to the error output, the buffer row that is added to the output buffer contains only the two error columns.</span></span>  
  
 <span data-ttu-id="585f3-146">Pour envoyer une ligne vers une sortie d'erreur asynchrone, vous devez ajouter une ligne au tampon de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="585f3-146">To send a row to an asynchronous error output, you must add a row to the error output buffer.</span></span> <span data-ttu-id="585f3-147">Parfois, une ligne peut avoir déjà été ajoutée au tampon de sortie sans erreur et vous devez la supprimer en utilisant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RemoveRow%2A>.</span><span class="sxs-lookup"><span data-stu-id="585f3-147">Sometimes, a row may have already been added to the non-error output buffer and you must remove this row by using the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.RemoveRow%2A> method.</span></span> <span data-ttu-id="585f3-148">Ensuite, vous définissez les valeurs des colonnes du tampon de sortie, et enfin, vous appelez la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> pour fournir le code d'erreur propre au composant et la valeur de la colonne d'erreur.</span><span class="sxs-lookup"><span data-stu-id="585f3-148">Next you set the output buffer columns values, and finally, you call the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method to provide the component-specific error code and the error column value.</span></span>  
  
 <span data-ttu-id="585f3-149">L'exemple suivant montre comment utiliser une sortie d'erreur pour un composant avec des sorties asynchrones.</span><span class="sxs-lookup"><span data-stu-id="585f3-149">The following example demonstrates how to use an error output for a component with asynchronous outputs.</span></span> <span data-ttu-id="585f3-150">Lorsque l'erreur simulée se produit, le composant ajoute une ligne au tampon de sortie d'erreur, copie les valeurs ajoutées précédemment au tampon de sortie sans erreur vers le tampon de sortie d'erreur, supprime la ligne ajoutée au tampon de sortie sans erreur et, enfin, définit le code d'erreur et les valeurs des colonnes d'erreur en appelant la méthode <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A>.</span><span class="sxs-lookup"><span data-stu-id="585f3-150">When the simulated error occurs, the component adds a row to the error output buffer, copies the values that were previously added to the non-error output buffer to the error output buffer, removes the row that was added to the non-error output buffer, and, finally, sets the error code and error column values by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineBuffer.SetErrorInfo%2A> method.</span></span>  
  
```csharp  
int []columnIndex;  
int errorOutputID = -1;  
int errorOutputIndex = -1;  
  
public override void PreExecute()  
{  
    IDTSOutput100 defaultOutput = null;  
  
    this.GetErrorOutputInfo(ref errorOutputID, ref errorOutputIndex);  
    foreach (IDTSOutput100 output in ComponentMetaData.OutputCollection)  
    {  
        if (output.ID != errorOutputID)  
            defaultOutput = output;  
    }  
  
    columnIndex = new int[defaultOutput.OutputColumnCollection.Count];  
  
    for(int col =0 ; col < defaultOutput.OutputColumnCollection.Count; col++)  
    {  
        IDTSOutputColumn100 column = defaultOutput.OutputColumnCollection[col];  
        columnIndex[col] = BufferManager.FindColumnByLineageID(defaultOutput.Buffer, column.LineageID);  
    }  
}  
  
public override void PrimeOutput(int outputs, int[] outputIDs, PipelineBuffer[] buffers)  
{  
    for( int x=0; x < outputs; x++ )  
    {  
        if (outputIDs[x] == errorOutputID)  
            this.errorBuffer = buffers[x];  
        else  
            this.defaultBuffer = buffers[x];  
    }  
  
    int rows = 100;  
  
    Random random = new Random(System.DateTime.Now.Millisecond);  
  
    for (int row = 0; row < rows; row++)  
    {  
        try  
        {  
            defaultBuffer.AddRow();  
  
            for (int x = 0; x < columnIndex.Length; x++)  
                defaultBuffer[columnIndex[x]] = random.Next();  
  
            // Simulate an error.  
            if ((row % 2) == 0)  
                throw new Exception("A simulated error.");  
        }  
        catch  
        {  
            // Add a row to the error buffer.  
            errorBuffer.AddRow();  
  
            // Get the values from the default buffer  
            // and copy them to the error buffer.  
            for (int x = 0; x < columnIndex.Length; x++)  
                errorBuffer[columnIndex[x]] = defaultBuffer[columnIndex[x]];  
  
            // Set the error information.  
            errorBuffer.SetErrorInfo(errorOutputID, 1, 0);  
  
            // Remove the row that was added to the default buffer.  
            defaultBuffer.RemoveRow();  
        }  
    }  
  
    if (defaultBuffer != null)  
        defaultBuffer.SetEndOfRowset();  
  
    if (errorBuffer != null)  
        errorBuffer.SetEndOfRowset();  
}  
```  
  
```vb  
Private columnIndex As Integer()   
Private errorOutputID As Integer = -1   
Private errorOutputIndex As Integer = -1   
  
Public  Overrides Sub PreExecute()   
 Dim defaultOutput As IDTSOutput100 = Nothing   
 Me.GetErrorOutputInfo(errorOutputID, errorOutputIndex)   
 For Each output As IDTSOutput100 In ComponentMetaData.OutputCollection   
   If Not (output.ID = errorOutputID) Then   
     defaultOutput = output   
   End If   
 Next   
 columnIndex = New Integer(defaultOutput.OutputColumnCollection.Count) {}   
 Dim col As Integer = 0   
 While col < defaultOutput.OutputColumnCollection.Count   
   Dim column As IDTSOutputColumn100 = defaultOutput.OutputColumnCollection(col)   
   columnIndex(col) = BufferManager.FindColumnByLineageID(defaultOutput.Buffer, column.LineageID)   
   System.Math.Min(System.Threading.Interlocked.Increment(col),col-1)   
 End While   
End Sub   
  
Public  Overrides Sub PrimeOutput(ByVal outputs As Integer, ByVal outputIDs As Integer(), ByVal buffers As PipelineBuffer())   
 Dim x As Integer = 0   
 While x < outputs   
   If outputIDs(x) = errorOutputID Then   
     Me.errorBuffer = buffers(x)   
   Else   
     Me.defaultBuffer = buffers(x)   
   End If   
   System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
 End While   
 Dim rows As Integer = 100   
 Dim random As Random = New Random(System.DateTime.Now.Millisecond)   
 Dim row As Integer = 0   
 While row < rows   
   Try   
     defaultBuffer.AddRow   
     Dim x As Integer = 0   
     While x < columnIndex.Length   
       defaultBuffer(columnIndex(x)) = random.Next   
       System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
     End While   
     ' Simulate an error.  
     If (row Mod 2) = 0 Then   
       Throw New Exception("A simulated error.")   
     End If   
   Catch   
     ' Add a row to the error buffer.  
     errorBuffer.AddRow   
     ' Get the values from the default buffer  
     ' and copy them to the error buffer.  
     Dim x As Integer = 0   
     While x < columnIndex.Length   
       errorBuffer(columnIndex(x)) = defaultBuffer(columnIndex(x))   
       System.Math.Min(System.Threading.Interlocked.Increment(x),x-1)   
     End While   
     ' Set the error information.  
     errorBuffer.SetErrorInfo(errorOutputID, 1, 0)   
     ' Remove the row that was added to the default buffer.  
     defaultBuffer.RemoveRow   
   End Try   
   System.Math.Min(System.Threading.Interlocked.Increment(row),row-1)   
 End While   
 If Not (defaultBuffer Is Nothing) Then   
   defaultBuffer.SetEndOfRowset   
 End If   
 If Not (errorBuffer Is Nothing) Then   
   errorBuffer.SetEndOfRowset   
 End If   
End Sub  
```  
  
<span data-ttu-id="585f3-151">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="585f3-151">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="585f3-152">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="585f3-152">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="585f3-153">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="585f3-153">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="585f3-154">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="585f3-154">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="585f3-155">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="585f3-155">See Also</span></span>  
 <span data-ttu-id="585f3-156">[Gestion des erreurs dans les données](../../data-flow/error-handling-in-data.md) </span><span class="sxs-lookup"><span data-stu-id="585f3-156">[Error Handling in Data](../../data-flow/error-handling-in-data.md) </span></span>  
 [<span data-ttu-id="585f3-157">Utilisation de sorties d’erreur</span><span class="sxs-lookup"><span data-stu-id="585f3-157">Using Error Outputs</span></span>](using-error-outputs-in-a-data-flow-component.md)  
  
  
