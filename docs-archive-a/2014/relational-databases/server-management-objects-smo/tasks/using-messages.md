---
title: Utilisation des messages | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- messages [SMO]
ms.assetid: 4037a866-4826-4c1f-890c-e7e3658adf13
author: stevestein
ms.author: sstein
ms.openlocfilehash: 53b2e0fa4be2dfd53cdd8f4f0cacb7ae0bd79edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613392"
---
# <a name="using-messages"></a><span data-ttu-id="e52ca-102">Utilisation de messages</span><span class="sxs-lookup"><span data-stu-id="e52ca-102">Using Messages</span></span>
  <span data-ttu-id="e52ca-103">Dans SMO, les messages système sont représentés par l'objet <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> qui appartient à l'objet `Server`.</span><span class="sxs-lookup"><span data-stu-id="e52ca-103">In SMO, system messages are represented by the <xref:Microsoft.SqlServer.Management.Smo.SystemMessageCollection> object that belongs to the `Server` object.</span></span> <span data-ttu-id="e52ca-104">Comme les messages système ne peuvent pas être modifiés, les propriétés d'objet `SystemMessage` sont en lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e52ca-104">Because the system messages cannot be modified, `SystemMessage` object properties are read-only.</span></span>  
  
 <span data-ttu-id="e52ca-105">Les messages définis par l'utilisateur sont représentés par programme dans SMO par l'objet <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection>.</span><span class="sxs-lookup"><span data-stu-id="e52ca-105">User-defined messages are represented programmatically in SMO by the <xref:Microsoft.SqlServer.Management.Smo.UserDefinedMessageCollection> object.</span></span> <span data-ttu-id="e52ca-106">Les messages définis par l'utilisateur existants peuvent être découverts en parcourant la collection.</span><span class="sxs-lookup"><span data-stu-id="e52ca-106">Existing user-defined messages can be discovered by iterating through the collection.</span></span> <span data-ttu-id="e52ca-107">Les nouveaux messages définis par l'utilisateur peuvent être créés par instanciation d'un nouvel objet `UserDefinedMessage` et définition des propriétés appropriées.</span><span class="sxs-lookup"><span data-stu-id="e52ca-107">New user-defined messages can be created by instantiating a new `UserDefinedMessage` object and setting the appropriate properties.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e52ca-108">Exemples</span><span class="sxs-lookup"><span data-stu-id="e52ca-108">Examples</span></span>  
 <span data-ttu-id="e52ca-109">Dans les exemples de code suivants, vous devez sélectionner l'environnement, le modèle et le langage de programmation à utiliser pour créer votre application.</span><span class="sxs-lookup"><span data-stu-id="e52ca-109">For the following code examples, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="e52ca-110">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) et [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="e52ca-110">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="finding-a-particular-system-message-in-visual-basic"></a><span data-ttu-id="e52ca-111">Recherche d'un message système particulier en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e52ca-111">Finding a Particular System Message in Visual Basic</span></span>  
 <span data-ttu-id="e52ca-112">L'exemple de code montre comment identifier un message système par son numéro d'ID et afficher le message.</span><span class="sxs-lookup"><span data-stu-id="e52ca-112">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBMessages1](SMO How to#SMO_VBMessages1)]  -->  
  
## <a name="finding-a-particular-system-message-in-visual-c"></a><span data-ttu-id="e52ca-113">Recherche d'un message système particulier en Visual C#</span><span class="sxs-lookup"><span data-stu-id="e52ca-113">Finding a Particular System Message in Visual C#</span></span>  
 <span data-ttu-id="e52ca-114">L'exemple de code montre comment identifier un message système par son numéro d'ID et afficher le message.</span><span class="sxs-lookup"><span data-stu-id="e52ca-114">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```csharp
{  
            //Connect to the local, default instance of SQL Server.   
            Server srv = new Server();  
            //Reference an existing system message using the   
            //ItemByIdAndLanguage method.   
            SystemMessage msg = default(SystemMessage);  
            msg = srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
        }  
```  
  
## <a name="finding-a-particular-system-message-in-powershell"></a><span data-ttu-id="e52ca-115">Recherche d'un message système particulier dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="e52ca-115">Finding a Particular System Message in PowerShell</span></span>  
 <span data-ttu-id="e52ca-116">L'exemple de code montre comment identifier un message système par son numéro d'ID et afficher le message.</span><span class="sxs-lookup"><span data-stu-id="e52ca-116">The code example shows how to identify a system message by ID number and display the message.</span></span>  
  
```powershell
# Set the path context to the local, default instance of SQL Server.  
CD \sql\localhost\  
$srv = Get-Item default  
  
#Get the message 14126 in US English and display it  
$msg = $srv.SystemMessages.ItemByIdAndLanguage(14126, "us_english")  
$msg.ID.ToString() + " "+ $msg.Text  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-basic"></a><span data-ttu-id="e52ca-117">Ajout d'un nouveau message défini par l'utilisateur en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e52ca-117">Adding a New User-Defined Message in Visual Basic</span></span>  
 <span data-ttu-id="e52ca-118">L'exemple de code montre comment créer un message défini par l'utilisateur avec un ID supérieur à 50000.</span><span class="sxs-lookup"><span data-stu-id="e52ca-118">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```vb
Dim mysrv As Server  
mysrv = New Server  
Dim udm As UserDefinedMessage  
udm = New UserDefinedMessage(mysrv, 50003, "us_english", 16, "Test message")  
udm.Create()  
```  
  
## <a name="adding-a-new-user-defined-message-in-visual-c"></a><span data-ttu-id="e52ca-119">Ajout d'un nouveau message défini par l'utilisateur en Visual C#</span><span class="sxs-lookup"><span data-stu-id="e52ca-119">Adding a New User-Defined Message in Visual C#</span></span>  
 <span data-ttu-id="e52ca-120">L'exemple de code montre comment créer un message défini par l'utilisateur avec un ID supérieur à 50000.</span><span class="sxs-lookup"><span data-stu-id="e52ca-120">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```csharp
{
            Server mysrv = new Server();  
  
            UserDefinedMessage udm = new UserDefinedMessage(mysrv, 50030, "us_english",16, "Test message");  
            udm.Create();  
             UserDefinedMessage  msg = mysrv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
            //Display the message ID and text.   
            Console.WriteLine(msg.ID.ToString() + " " + msg.Text);  
  
        }  
```  
  
## <a name="adding-a-new-user-defined-message-in-powershell"></a><span data-ttu-id="e52ca-121">Ajout d'un nouveau message défini par l'utilisateur dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="e52ca-121">Adding a New User-Defined Message in PowerShell</span></span>
 <span data-ttu-id="e52ca-122">L'exemple de code montre comment créer un message défini par l'utilisateur avec un ID supérieur à 50000.</span><span class="sxs-lookup"><span data-stu-id="e52ca-122">The code example demonstrates how to create a user-defined message with an ID greater than 50000.</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$srv = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a new message
$udm = New-Object -TypeName Microsoft.SqlServer.Management.SMO.UserDefinedMessage -ArgumentList `  
$srv, 50030, "us_english", 16, "Test message"  
$udm.Create()  
$msg = $srv.UserDefinedMessages.ItemByIdAndLanguage(50030, "us_english");  
$msg  
```  
