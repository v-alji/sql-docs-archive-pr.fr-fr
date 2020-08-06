---
title: Gestion des exceptions SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- SMO [SQL Server], exceptions
- exceptions [SMO]
- SQL Server Management Objects, exceptions
- inner exceptions [SMO]
ms.assetid: 4c725ff2-6588-44ca-b86a-87979e164153
author: stevestein
ms.author: sstein
ms.openlocfilehash: f4ae9e475a019c9bf874ee3f8365f3f3ac8e19d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613938"
---
# <a name="handling-smo-exceptions"></a><span data-ttu-id="5a283-102">Gestion des exceptions SMO</span><span class="sxs-lookup"><span data-stu-id="5a283-102">Handling SMO Exceptions</span></span>
  <span data-ttu-id="5a283-103">En code managé, des exceptions sont levées lorsqu'une erreur se produit.</span><span class="sxs-lookup"><span data-stu-id="5a283-103">In managed code, exceptions are thrown when an error occurs.</span></span> <span data-ttu-id="5a283-104">Les méthodes et propriétés SMO ne signalent ni la réussite ni l'échec dans la valeur de retour.</span><span class="sxs-lookup"><span data-stu-id="5a283-104">SMO methods and properties do not report success or failure in the return value.</span></span> <span data-ttu-id="5a283-105">Au lieu de cela, les exceptions peuvent être interceptées et gérées par un gestionnaire d'exceptions.</span><span class="sxs-lookup"><span data-stu-id="5a283-105">Instead, exceptions can be caught and handled by an exception handler.</span></span>  
  
 <span data-ttu-id="5a283-106">Il existe différentes classes d'exceptions SMO.</span><span class="sxs-lookup"><span data-stu-id="5a283-106">Different exception classes exist in the SMO.</span></span> <span data-ttu-id="5a283-107">Les informations sur l'exception peuvent être extraites des propriétés d'exception telles que la propriété `Message` qui donne un message texte concernant l'exception.</span><span class="sxs-lookup"><span data-stu-id="5a283-107">Information about the exception can be extracted from the exception properties such as the `Message` property that gives a text message about the exception.</span></span>  
  
 <span data-ttu-id="5a283-108">Les instructions de gestion des exceptions sont spécifiques au langage de programmation.</span><span class="sxs-lookup"><span data-stu-id="5a283-108">The exception handling statements are specific to the programming language.</span></span> <span data-ttu-id="5a283-109">Par exemple, dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic, il s'agit de l'instruction `Catch`.</span><span class="sxs-lookup"><span data-stu-id="5a283-109">For example, in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic it is the `Catch` statement.</span></span>  
  
## <a name="inner-exceptions"></a><span data-ttu-id="5a283-110">Exceptions internes</span><span class="sxs-lookup"><span data-stu-id="5a283-110">Inner Exceptions</span></span>  
 <span data-ttu-id="5a283-111">Les exceptions peuvent être générales ou spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5a283-111">Exceptions can either be general or specific.</span></span> <span data-ttu-id="5a283-112">Les exceptions générales contiennent un jeu d'exceptions spécifiques.</span><span class="sxs-lookup"><span data-stu-id="5a283-112">General exceptions contain a set of specific exceptions.</span></span> <span data-ttu-id="5a283-113">Plusieurs instructions `Catch` peuvent être utilisées pour gérer les erreurs anticipées et faire passer les erreurs restantes au code de gestion des exceptions générales.</span><span class="sxs-lookup"><span data-stu-id="5a283-113">Several `Catch` statements can be used to handle anticipated errors and let remaining errors fall through to general exception handling code.</span></span> <span data-ttu-id="5a283-114">Les exceptions se produisent souvent dans une séquence en cascade.</span><span class="sxs-lookup"><span data-stu-id="5a283-114">Exceptions often occur in a cascading sequence.</span></span> <span data-ttu-id="5a283-115">Il arrive fréquemment qu'une exception SMO soit provoquée par une exception SQL.</span><span class="sxs-lookup"><span data-stu-id="5a283-115">Frequently, an SMO exception might have been caused by an SQL exception.</span></span> <span data-ttu-id="5a283-116">Pour le savoir, utilisez successivement la propriété `InnerException` pour déterminer l'exception d'origine ayant provoqué l'exception finale de niveau supérieur.</span><span class="sxs-lookup"><span data-stu-id="5a283-116">The way to detect this is to use the `InnerException` property successively to determine the original exception that caused the final, top-level exception.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a283-117">L' `SQLException` exception est déclarée dans l’espace de noms **System. Data. SqlClient** .</span><span class="sxs-lookup"><span data-stu-id="5a283-117">The `SQLException` exception is declared in the **System.Data.SqlClient** namespace.</span></span>  
  
 <span data-ttu-id="5a283-118">![Diagramme illustrant les niveaux à partir desquels une exception s'est produite](../../../database-engine/dev-guide/media/exception-flow.gif "Diagramme illustrant les niveaux à partir desquels une exception s'est produite")</span><span class="sxs-lookup"><span data-stu-id="5a283-118">![A diagram that shows the levels from which an excp](../../../database-engine/dev-guide/media/exception-flow.gif "A diagram that shows the levels from which an excp")</span></span>  
  
 <span data-ttu-id="5a283-119">Le diagramme affiche le flux d'exceptions à travers les couches de l'application.</span><span class="sxs-lookup"><span data-stu-id="5a283-119">The diagram shows the flow of exceptions through the layers of the application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a283-120">Exemple</span><span class="sxs-lookup"><span data-stu-id="5a283-120">Example</span></span>  
 <span data-ttu-id="5a283-121">Pour utiliser un exemple de code qui est fourni, vous devrez choisir l'environnement de programmation, le modèle de programmation et le langage de programmation dans lequel créer votre application.</span><span class="sxs-lookup"><span data-stu-id="5a283-121">To use any code example that is provided, you will have to choose the programming environment, the programming template, and the programming language in which to create your application.</span></span> <span data-ttu-id="5a283-122">Pour plus d’informations, consultez [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) ou [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="5a283-122">For more information, see [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md) or [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="catching-an-exception-in-visual-basic"></a><span data-ttu-id="5a283-123">Interception d'une exception en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a283-123">Catching an Exception in Visual Basic</span></span>  
 <span data-ttu-id="5a283-124">Cet exemple de code montre comment utiliser l'instruction [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]`Try...Catch...Finally` pour intercepter une exception SMO.</span><span class="sxs-lookup"><span data-stu-id="5a283-124">This code example shows how to use the `Try...Catch...Finally`[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] statement to catch a SMO exception.</span></span> <span data-ttu-id="5a283-125">Toutes les exceptions SMO possèdent le type SmoException et sont répertoriées dans la référence SMO.</span><span class="sxs-lookup"><span data-stu-id="5a283-125">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="5a283-126">La séquence d'exceptions internes est affichée pour indiquer la racine de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="5a283-126">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="5a283-127">Pour plus d'informations, consultez la documentation [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="5a283-127">For more information, see the [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] .NET documentation.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBExceptions1](SMO How to#SMO_VBExceptions1)]  -->  
  
## <a name="catching-an-exception-in-visual-c"></a><span data-ttu-id="5a283-128">Interception d'une exception en Visual C#</span><span class="sxs-lookup"><span data-stu-id="5a283-128">Catching an Exception in Visual C#</span></span>  
 <span data-ttu-id="5a283-129">Cet exemple de code montre comment utiliser l'instruction Visual C# `Try...Catch...Finally` pour intercepter une exception SMO.</span><span class="sxs-lookup"><span data-stu-id="5a283-129">This code example shows how to use the `Try...Catch...Finally` Visual C# statement to catch a SMO exception.</span></span> <span data-ttu-id="5a283-130">Toutes les exceptions SMO possèdent le type SmoException et sont répertoriées dans la référence SMO.</span><span class="sxs-lookup"><span data-stu-id="5a283-130">All SMO exceptions have the type SmoException, and are listed in the SMO reference.</span></span> <span data-ttu-id="5a283-131">La séquence d'exceptions internes est affichée pour indiquer la racine de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="5a283-131">The sequence of inner exceptions is displayed to show the root of the error.</span></span> <span data-ttu-id="5a283-132">Pour plus d'informations, consultez la documentation Visual C#.</span><span class="sxs-lookup"><span data-stu-id="5a283-132">For more information, see the Visual C# documentation.</span></span>  
  
```  
{   
//This sample requires the Microsoft.SqlServer.Management.Smo.Agent namespace to be included.   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define an Operator object variable by supplying the parent SQL Agent and the name arguments in the constructor.   
//Note that the Operator type requires [] parenthesis to differentiate it from a Visual Basic key word.   
op = new Operator(srv.JobServer, "Test_Operator");   
op.Create();   
//Start exception handling.   
try {   
    //Create the operator again to cause an SMO exception.   
    OperatorCategory opx;   
    opx = new OperatorCategory(srv.JobServer, "Test_Operator");   
    opx.Create();   
}   
//Catch the SMO exception   
catch (SmoException smoex) {   
    Console.WriteLine("This is an SMO Exception");   
   //Display the SMO exception message.   
   Console.WriteLine(smoex.Message);   
   //Display the sequence of non-SMO exceptions that caused the SMO exception.   
   Exception ex;   
   ex = smoex.InnerException;   
   while (!object.ReferenceEquals(ex.InnerException, (null))) {   
      Console.WriteLine(ex.InnerException.Message);   
      ex = ex.InnerException;   
    }   
    }   
   //Catch other non-SMO exceptions.   
   catch (Exception ex) {   
      Console.WriteLine("This is not an SMO exception.");   
}   
}  
```  
  
  
