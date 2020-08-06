---
title: Codage d’un énumérateur ForEach personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- custom foreach enumerators [Integration Services], coding
ms.assetid: 279cf6de-d06f-40e7-b8ca-569310449f36
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2b7e6c16124f4682dbdc98f602417bf8f68ce099
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602904"
---
# <a name="coding-a-custom-foreach-enumerator"></a><span data-ttu-id="28fbc-102">Codage d'un énumérateur Foreach personnalisé</span><span class="sxs-lookup"><span data-stu-id="28fbc-102">Coding a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="28fbc-103">Après avoir créé une classe qui hérite de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, puis appliqué l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> à cette classe, vous devez substituer l'implémentation des propriétés et des méthodes de la classe de base afin de fournir vos fonctionnalités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="28fbc-103">After you have created a class that inherits from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, and applied the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class, you must override the implementation of the properties and methods of the base class to provide your custom functionality.</span></span>  
  
 <span data-ttu-id="28fbc-104">Pour obtenir un exemple fonctionnel d’un énumérateur personnalisé, consultez [Développement d’une interface utilisateur pour un énumérateur ForEach personnalisé](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span><span class="sxs-lookup"><span data-stu-id="28fbc-104">For a working sample of a custom enumerator, see [Developing a User Interface for a Custom ForEach Enumerator](developing-a-user-interface-for-a-custom-foreach-enumerator.md).</span></span>  
  
## <a name="initializing-the-enumerator"></a><span data-ttu-id="28fbc-105">Initialisation de l'énumérateur</span><span class="sxs-lookup"><span data-stu-id="28fbc-105">Initializing the Enumerator</span></span>  
 <span data-ttu-id="28fbc-106">Vous pouvez substituer la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> pour mettre en cache des références aux gestionnaires de connexions définis dans le package et des références à l'interface d'événements qui vous permet de déclencher des erreurs, des avertissements et des messages d'information.</span><span class="sxs-lookup"><span data-stu-id="28fbc-106">You can override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.InitializeForEachEnumerator%2A> method to cache references to the connection managers defined in the package, and to cache references to the events interface that you can use to raise errors, warnings, and informational messages.</span></span>  
  
## <a name="validating-the-enumerator"></a><span data-ttu-id="28fbc-107">Validation de l'énumérateur</span><span class="sxs-lookup"><span data-stu-id="28fbc-107">Validating the Enumerator</span></span>  
 <span data-ttu-id="28fbc-108">Substituez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> pour vérifier que l'énumérateur est correctement configuré.</span><span class="sxs-lookup"><span data-stu-id="28fbc-108">You override the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> method to verify that the enumerator is correctly configured.</span></span> <span data-ttu-id="28fbc-109">Si la méthode retourne `Failure`, l'énumérateur et le package dans lequel il est contenu ne seront pas exécutés.</span><span class="sxs-lookup"><span data-stu-id="28fbc-109">If the method returns `Failure`, the enumerator and the package that contains the enumerator will not be executed.</span></span> <span data-ttu-id="28fbc-110">L'implémentation de cette méthode est propre à chaque énumérateur, mais si l'énumérateur utilise des objets <xref:Microsoft.SqlServer.Dts.Runtime.Variable> ou <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager>, vous devez ajouter du code pour vérifier que ces objets existent dans les collections fournies à la méthode.</span><span class="sxs-lookup"><span data-stu-id="28fbc-110">The implementation of this method is specific to each enumerator, but if the enumerator relies on <xref:Microsoft.SqlServer.Dts.Runtime.Variable> or <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> objects, you should add code to verify that these objects exist in the collections that are provided to the method.</span></span>  
  
 <span data-ttu-id="28fbc-111">L'exemple de code suivant montre une implémentation de <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> qui recherche une variable spécifiée dans une propriété de l'énumérateur.</span><span class="sxs-lookup"><span data-stu-id="28fbc-111">The following code example demonstrates an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.Validate%2A> that checks for a variable specified in a property of the enumerator.</span></span>  
  
```csharp  
private string variableNameValue;  
  
public string VariableName  
{  
    get{ return this.variableNameValue; }  
    set{ this.variableNameValue = value; }  
}  
  
public override DTSExecResult Validate(Connections connections, VariableDispenser variableDispenser, IDTSInfoEvents infoEvents, IDTSLogging log)  
{  
    if (!variableDispenser.Contains(this.variableNameValue))  
    {  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + this.variableNameValue + " does not exist in the collection.", "", 0);  
            return DTSExecResult.Failure;  
    }  
    return DTSExecResult.Success;  
}  
```  
  
```vb  
Private variableNameValue As String  
  
Public Property VariableName() As String  
    Get   
         Return Me.variableNameValue  
    End Get  
    Set (ByVal Value As String)   
         Me.variableNameValue = value  
    End Set  
End Property  
  
Public Overrides Function Validate(ByVal connections As Connections, ByVal variableDispenser As VariableDispenser, ByVal infoEvents As IDTSInfoEvents, ByVal log As IDTSLogging) As DTSExecResult  
    If Not variableDispenser.Contains(Me.variableNameValue) Then  
        infoEvents.FireError(0, "MyEnumerator", "The Variable " + Me.variableNameValue + " does not exist in the collection.", "", 0)  
            Return DTSExecResult.Failure  
    End If  
    Return DTSExecResult.Success  
End Function  
```  
  
## <a name="returning-the-collection"></a><span data-ttu-id="28fbc-112">Retour de la collection</span><span class="sxs-lookup"><span data-stu-id="28fbc-112">Returning the Collection</span></span>  
 <span data-ttu-id="28fbc-113">Au moment de l’exécution, le conteneur <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> appelle la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> de l’énumérateur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="28fbc-113">During execution, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="28fbc-114">Dans cette méthode, l'énumérateur crée et remplit sa collection d'éléments, puis retourne la collection.</span><span class="sxs-lookup"><span data-stu-id="28fbc-114">In this method, the enumerator creates and populates its collection of items, and then returns the collection.</span></span> <span data-ttu-id="28fbc-115">Le conteneur <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> itère ensuite les éléments dans la collection et exécute son flux de contrôle pour chacun d'eux.</span><span class="sxs-lookup"><span data-stu-id="28fbc-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates the items in the collection, and executes its control flow for each item in the collection.</span></span>  
  
 <span data-ttu-id="28fbc-116">L'exemple suivant présente une implémentation de <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> qui retourne un tableau d'entiers aléatoires.</span><span class="sxs-lookup"><span data-stu-id="28fbc-116">The following example shows an implementation of <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> that returns an array of random integers.</span></span>  
  
```csharp  
public override object GetEnumerator()  
{  
    ArrayList numbers = new ArrayList();  
  
    Random randomNumber = new Random(DateTime.Now);  
  
    for( int x=0; x < 100; x++ )  
        numbers.Add( randomNumber.Next());  
  
    return numbers;  
}  
```  
  
```vb  
Public Overrides Function GetEnumerator() As Object  
    Dim numbers As ArrayList =  New ArrayList()   
  
    Dim randomNumber As Random =  New Random(DateTime.Now)   
  
        Dim x As Integer  
        For  x = 0 To  100- 1  Step  x + 1  
        numbers.Add(randomNumber.Next())  
        Next  
  
    Return numbers  
End Function  
```  
  
<span data-ttu-id="28fbc-117">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="28fbc-117">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="28fbc-118">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="28fbc-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="28fbc-119">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="28fbc-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="28fbc-120">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="28fbc-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28fbc-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="28fbc-121">See Also</span></span>  
 <span data-ttu-id="28fbc-122">[Création d’un énumérateur foreach personnalisé](creating-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="28fbc-122">[Creating a Custom Foreach Enumerator](creating-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="28fbc-123">Développement d'une interface utilisateur pour un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="28fbc-123">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
