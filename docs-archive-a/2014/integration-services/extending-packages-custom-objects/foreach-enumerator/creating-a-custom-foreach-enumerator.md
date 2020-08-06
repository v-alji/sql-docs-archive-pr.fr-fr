---
title: Création d’un énumérateur ForEach personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom foreach enumerators [Integration Services], creating
ms.assetid: 050e8455-2ed0-4b6d-b3ea-4e80e6c28487
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d99970d466aa53d25a80f0600f1fce7819e94956
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602902"
---
# <a name="creating-a-custom-foreach-enumerator"></a><span data-ttu-id="cccf5-102">Création d'un énumérateur Foreach personnalisé</span><span class="sxs-lookup"><span data-stu-id="cccf5-102">Creating a Custom Foreach Enumerator</span></span>
  <span data-ttu-id="cccf5-103">Les étapes de création d'un énumérateur Foreach personnalisé sont semblables aux étapes de création de tout autre objet personnalisé pour [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="cccf5-103">The steps involved in creating a custom foreach enumerator are similar to the steps for creating any other custom object for [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="cccf5-104">Créer une classe qui hérite de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="cccf5-104">Create a new class that inherits from the base class.</span></span> <span data-ttu-id="cccf5-105">Pour un énumérateur Foreach, la classe de base est <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span><span class="sxs-lookup"><span data-stu-id="cccf5-105">For a foreach enumerator, the base class is <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>.</span></span>  
  
-   <span data-ttu-id="cccf5-106">Appliquer l'attribut qui identifie le type d'objet auprès de la classe.</span><span class="sxs-lookup"><span data-stu-id="cccf5-106">Apply the attribute that identifies the type of object to the class.</span></span> <span data-ttu-id="cccf5-107">Pour un énumérateur Foreach, l'attribut est <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cccf5-107">For a foreach enumerator, the attribute is <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute>.</span></span>  
  
-   <span data-ttu-id="cccf5-108">Substituer l'implémentation des méthodes et des propriétés de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="cccf5-108">Override the implementation of the base class's methods and properties.</span></span> <span data-ttu-id="cccf5-109">Pour un énumérateur Foreach, l'élément le plus important est la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="cccf5-109">For a foreach enumerator, the most important is the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method.</span></span>  
  
-   <span data-ttu-id="cccf5-110">Développer éventuellement une interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="cccf5-110">Optionally, develop a custom user interface.</span></span> <span data-ttu-id="cccf5-111">Pour un énumérateur Foreach, cette opération requiert une classe qui implémente l'interface <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI>.</span><span class="sxs-lookup"><span data-stu-id="cccf5-111">For a foreach enumerator, this requires a class that implements the <xref:Microsoft.SqlServer.Dts.Runtime.IDTSForEachEnumeratorUI> interface.</span></span>  
  
 <span data-ttu-id="cccf5-112">Un énumérateur personnalisé est hébergé par le conteneur <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop>.</span><span class="sxs-lookup"><span data-stu-id="cccf5-112">A custom enumerator is hosted by the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container.</span></span> <span data-ttu-id="cccf5-113">Au moment de l'exécution, le conteneur <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> appelle la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> de l'énumérateur personnalisé.</span><span class="sxs-lookup"><span data-stu-id="cccf5-113">At run time, the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> container calls the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator.GetEnumerator%2A> method of the custom enumerator.</span></span> <span data-ttu-id="cccf5-114">L'énumérateur personnalisé retourne un objet qui implémente l'interface `IEnumerable`, tel qu'un `ArrayList`.</span><span class="sxs-lookup"><span data-stu-id="cccf5-114">The custom enumerator returns an object that implements the `IEnumerable` interface, such as an `ArrayList`.</span></span> <span data-ttu-id="cccf5-115"><xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> parcourt ensuite chaque élément de la collection, fournit la valeur de l'élément actuel au flux de contrôle au moyen d'une variable définie par l'utilisateur et exécute le flux de contrôle dans le conteneur.</span><span class="sxs-lookup"><span data-stu-id="cccf5-115">The <xref:Microsoft.SqlServer.Dts.Runtime.ForEachLoop> then iterates over each element in the collection, provides the value of the current element to the control flow through a user-defined variable, and executes the control flow in the container.</span></span>  
  
## <a name="getting-started-with-a-custom-foreach-enumerator"></a><span data-ttu-id="cccf5-116">Mise en route d'un énumérateur Foreach personnalisé</span><span class="sxs-lookup"><span data-stu-id="cccf5-116">Getting Started with a Custom ForEach Enumerator</span></span>  
  
### <a name="creating-projects-and-classes"></a><span data-ttu-id="cccf5-117">Création de projets et de classes</span><span class="sxs-lookup"><span data-stu-id="cccf5-117">Creating Projects and Classes</span></span>  
 <span data-ttu-id="cccf5-118">Comme tous les énumérateurs Foreach managés dérivent de la classe de base <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator>, la première étape de création d'un énumérateur Foreach personnalisé consiste à créer un projet Bibliothèque de classes dans votre langage de programmation managé par défaut et créer une classe qui hérite de la classe de base.</span><span class="sxs-lookup"><span data-stu-id="cccf5-118">Because all managed foreach enumerators derive from the <xref:Microsoft.SqlServer.Dts.Runtime.ForEachEnumerator> base class, the first step when you create a custom foreach enumerator is to create a class library project in your preferred managed programming language and create a class that inherits from the base class.</span></span> <span data-ttu-id="cccf5-119">Dans cette classe dérivée, vous devez substituer les méthodes et les propriétés de la classe de base pour implémenter vos fonctionnalités personnalisées.</span><span class="sxs-lookup"><span data-stu-id="cccf5-119">In this derived class you will override the methods and properties of the base class to implement your custom functionality.</span></span>  
  
 <span data-ttu-id="cccf5-120">Dans la même solution, créez un deuxième projet Bibliothèque de classes pour l'interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="cccf5-120">In the same solution, create a second class library project for the custom user interface.</span></span> <span data-ttu-id="cccf5-121">Il est recommandé d'utiliser un assembly distinct pour l'interface utilisateur afin de faciliter le déploiement car vous pouvez ainsi mettre à jour et redéployer l'énumérateur Foreach ou son interface utilisateur de manière indépendante.</span><span class="sxs-lookup"><span data-stu-id="cccf5-121">A separate assembly for the user interface is recommended for ease of deployment because it allows you to update and redeploy the foreach enumerator or its user interface independently.</span></span>  
  
 <span data-ttu-id="cccf5-122">Configurez les deux projets pour qu'ils signent les assemblys qui seront créés au moment de la génération à l'aide d'un fichier de clé de nom fort.</span><span class="sxs-lookup"><span data-stu-id="cccf5-122">Configure both projects to sign the assemblies that will be generated at build time by using a strong name key file.</span></span>  
  
### <a name="applying-the-dtsforeachenumerator-attribute"></a><span data-ttu-id="cccf5-123">Application de l'attribut DtsForEachEnumerator</span><span class="sxs-lookup"><span data-stu-id="cccf5-123">Applying the DtsForEachEnumerator Attribute</span></span>  
 <span data-ttu-id="cccf5-124">Appliquez l'attribut <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> à la classe que vous avez créée pour l'identifier en tant qu'énumérateur Foreach.</span><span class="sxs-lookup"><span data-stu-id="cccf5-124">Apply the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute> attribute to the class that you have created to identify it as a foreach enumerator.</span></span> <span data-ttu-id="cccf5-125">Cet attribut fournit des informations au moment de la conception, telles que le nom et la description de l'énumérateur Foreach.</span><span class="sxs-lookup"><span data-stu-id="cccf5-125">This attribute provides design-time information such as the name and description of the foreach enumerator.</span></span> <span data-ttu-id="cccf5-126">La `Name` propriété s’affiche dans la liste déroulante des énumérateurs disponibles sous l’onglet **collection** de la boîte de dialogue **éditeur de boucle foreach** .</span><span class="sxs-lookup"><span data-stu-id="cccf5-126">The `Name` property appears in the dropdown list of available enumerators on the **Collection** tab of the **Foreach Loop Editor** dialog box.</span></span>  
  
 <span data-ttu-id="cccf5-127">Utilisez la propriété <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> pour lier l'énumérateur Foreach à son interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="cccf5-127">Use the <xref:Microsoft.SqlServer.Dts.Runtime.DtsForEachEnumeratorAttribute.UITypeName%2A> property to link the foreach enumerator to its custom user interface.</span></span> <span data-ttu-id="cccf5-128">Pour obtenir le jeton de clé publique requis pour cette propriété, vous pouvez utiliser **sn.exe -t** de manière à afficher le jeton de clé publique du fichier de paire de clés (.snk) que vous voulez utiliser pour signer l’assembly de l’interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="cccf5-128">To obtain the public key token that is required for this property, you an use **sn.exe -t** to display the public key token from the key pair (.snk) file that you intend to use to sign the user interface assembly.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.SqlServer.Dts.Runtime  
Namespace Microsoft.Samples.SqlServer.Dts  
    <DtsForEachEnumerator(DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")> _   
    Public Class MyEnumerator  
     Inherits ForEachEnumerator  
        'Insert code here.  
    End Class  
End Namespace  
```  
  
```csharp  
using System;  
using Microsoft.SqlServer.Dts.Runtime;  
namespace Microsoft.Samples.SqlServer.Dts  
{  
    [DtsForEachEnumerator( DisplayName = "MyEnumerator", Description="A sample custom enumerator", UITypeName="FullyQualifiedTypeName,AssemblyName,Version=1.00.000.00,Culture=Neutral,PublicKeyToken=<publickeytoken>")]  
    public class MyEnumerator : ForEachEnumerator  
    {  
        //Insert code here.  
    }  
}  
```  
  
## <a name="building-deploying-and-debugging-a-custom-enumerator"></a><span data-ttu-id="cccf5-129">Génération, déploiement et débogage d'un énumérateur personnalisé</span><span class="sxs-lookup"><span data-stu-id="cccf5-129">Building, Deploying, and Debugging a Custom Enumerator</span></span>  
 <span data-ttu-id="cccf5-130">Les étapes pour générer, déployer et déboguer un énumérateur Foreach personnalisé dans [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sont très semblables aux étapes requises pour les autres types d'objets personnalisés.</span><span class="sxs-lookup"><span data-stu-id="cccf5-130">The steps for building, deploying, and debugging a custom foreach enumerator in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] are very similar to the steps required for other types of custom objects.</span></span> <span data-ttu-id="cccf5-131">Pour plus d’informations, consultez [Génération, déploiement et débogage d’objets personnalisés](../building-deploying-and-debugging-custom-objects.md).</span><span class="sxs-lookup"><span data-stu-id="cccf5-131">For more information, see [Building, Deploying, and Debugging Custom Objects](../building-deploying-and-debugging-custom-objects.md).</span></span>  
  
<span data-ttu-id="cccf5-132">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="cccf5-132">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="cccf5-133">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="cccf5-133">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="cccf5-134">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="cccf5-134">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="cccf5-135">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="cccf5-135">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cccf5-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cccf5-136">See Also</span></span>  
 <span data-ttu-id="cccf5-137">[Codage d’un énumérateur foreach personnalisé](coding-a-custom-foreach-enumerator.md) </span><span class="sxs-lookup"><span data-stu-id="cccf5-137">[Coding a Custom Foreach Enumerator](coding-a-custom-foreach-enumerator.md) </span></span>  
 [<span data-ttu-id="cccf5-138">Développement d'une interface utilisateur pour un énumérateur ForEach personnalisé</span><span class="sxs-lookup"><span data-stu-id="cccf5-138">Developing a User Interface for a Custom ForEach Enumerator</span></span>](developing-a-user-interface-for-a-custom-foreach-enumerator.md)  
  
  
