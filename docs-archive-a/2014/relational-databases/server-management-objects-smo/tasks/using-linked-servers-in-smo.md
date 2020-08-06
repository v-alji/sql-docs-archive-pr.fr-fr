---
title: Utilisation de serveurs liés dans SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- linked servers [SQL Server], SMO
ms.assetid: 0ea8837b-2596-4df1-b065-3bb717c9f22c
author: stevestein
ms.author: sstein
ms.openlocfilehash: 58804e2be1edfa685a57f56c173c77a50e0f9126
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601314"
---
# <a name="using-linked-servers-in-smo"></a><span data-ttu-id="a6f44-102">Utilisation de serveurs liés dans SMO</span><span class="sxs-lookup"><span data-stu-id="a6f44-102">Using Linked Servers in SMO</span></span>
  <span data-ttu-id="a6f44-103">Un serveur lié représente une source de données OLE DB sur un serveur distant.</span><span class="sxs-lookup"><span data-stu-id="a6f44-103">A linked server represents an OLE DB data source on a remote server.</span></span> <span data-ttu-id="a6f44-104">Les sources de données OLE DB distantes sont liées à l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-104">Remote OLE DB data sources are linked to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span>  
  
 <span data-ttu-id="a6f44-105">Les serveurs de base de données distants peuvent être liés à l’instance actuelle de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l’aide d’un fournisseur OLE DB.</span><span class="sxs-lookup"><span data-stu-id="a6f44-105">Remote database servers can be linked to the current instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using an OLE DB Provider.</span></span> <span data-ttu-id="a6f44-106">Dans SMO, les serveurs liés sont représentés par l'objet <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-106">In SMO, linked servers are represented by the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="a6f44-107">La propriété <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> référence une collection d'objets <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-107">The <xref:Microsoft.SqlServer.Management.Smo.LinkedServer.LinkedServerLogins%2A> property references a collection of <xref:Microsoft.SqlServer.Management.Smo.LinkedServerLogin> objects.</span></span> <span data-ttu-id="a6f44-108">Ces derniers stockent les informations d'identification requises pour établir une connexion avec le serveur lié.</span><span class="sxs-lookup"><span data-stu-id="a6f44-108">These store the logon credentials that are required to establish a connection with the linked server.</span></span>  
  
## <a name="ole-db-providers"></a><span data-ttu-id="a6f44-109">Fournisseurs OLE DB</span><span class="sxs-lookup"><span data-stu-id="a6f44-109">OLE-DB Providers</span></span>  
 <span data-ttu-id="a6f44-110">Dans SMO, les fournisseurs OLE DB installés sont représentés par une collection d'objets <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-110">In SMO, installed OLE-DB providers are represented by a collection of <xref:Microsoft.SqlServer.Management.Smo.OleDbProviderSettings> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6f44-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="a6f44-111">Example</span></span>  
 <span data-ttu-id="a6f44-112">Dans l'exemple de code suivant, vous devez sélectionner l'environnement, le modèle et le langage de programmation à utiliser pour créer votre application.</span><span class="sxs-lookup"><span data-stu-id="a6f44-112">For the following code example, you will have to select the programming environment, programming template and the programming language to create your application.</span></span> <span data-ttu-id="a6f44-113">Pour plus d’informations, consultez [créer un projet Visual Basic Smo dans Visual Studio .net](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) et [créer un projet Visual C&#35; Smo dans Visual Studio .net](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span><span class="sxs-lookup"><span data-stu-id="a6f44-113">For more information, see [Create a Visual Basic SMO Project in Visual Studio .NET](../../../database-engine/dev-guide/create-a-visual-basic-smo-project-in-visual-studio-net.md) and [Create a Visual C&#35; SMO Project in Visual Studio .NET](../how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md).</span></span>  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-basic"></a><span data-ttu-id="a6f44-114">Création d'un lien vers un serveur de fournisseur OLE DB en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6f44-114">Creating a link to an OLE-DB Provider Server in Visual Basic</span></span>  
 <span data-ttu-id="a6f44-115">L'exemple de code suivant montre comment créer un lien vers une source de données hétérogènes OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-115">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="a6f44-116">En spécifiant [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] comme nom de produit, les données sont accessibles sur le serveur lié à l’aide du [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] fournisseur de OLE DB client, qui est le fournisseur de OLE DB officiel pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="a6f44-116">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
<!-- TODO: review snippet reference  [!CODE [SMO How to#SMO_VBLinkedServers1](SMO How to#SMO_VBLinkedServers1)]  -->  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-visual-c"></a><span data-ttu-id="a6f44-117">Création d'un lien vers un serveur de fournisseur OLE DB en Visual C#</span><span class="sxs-lookup"><span data-stu-id="a6f44-117">Creating a link to an OLE-DB Provider Server in Visual C#</span></span>  
 <span data-ttu-id="a6f44-118">L'exemple de code suivant montre comment créer un lien vers une source de données hétérogènes OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-118">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="a6f44-119">En spécifiant [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] comme nom de produit, l'accès aux données sur le serveur lié s'effectue en utilisant le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client, qui est le fournisseur OLE DB officiel pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f44-119">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```csharp
//Connect to the local, default instance of SQL Server.   
{   
   Server srv = new Server();   
   //Create a linked server.   
   LinkedServer lsrv = default(LinkedServer);   
   lsrv = new LinkedServer(srv, "OLEDBSRV");   
   //When the product name is SQL Server the remaining properties are   
   //not required to be set.   
   lsrv.ProductName = "SQL Server";   
   lsrv.Create();   
}   
```  
  
## <a name="creating-a-link-to-an-ole-db-provider-server-in-powershell"></a><span data-ttu-id="a6f44-120">Création d'un lien vers un serveur de fournisseur OLE DB dans PowerShell</span><span class="sxs-lookup"><span data-stu-id="a6f44-120">Creating a link to an OLE-DB Provider Server in PowerShell</span></span>  
 <span data-ttu-id="a6f44-121">L'exemple de code suivant montre comment créer un lien vers une source de données hétérogènes OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à l'aide de l'objet <xref:Microsoft.SqlServer.Management.Smo.LinkedServer>.</span><span class="sxs-lookup"><span data-stu-id="a6f44-121">The code example shows how to create a link to a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] OLE DB, heterogeneous data source by using the <xref:Microsoft.SqlServer.Management.Smo.LinkedServer> object.</span></span> <span data-ttu-id="a6f44-122">En spécifiant [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] comme nom de produit, l'accès aux données sur le serveur lié s'effectue en utilisant le fournisseur OLE DB [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client, qui est le fournisseur OLE DB officiel pour [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a6f44-122">By specifying [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as the product name, data is accessed on the linked server by using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Client OLE DB Provider, which is the official OLE DB provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
```powershell
#Get a server object which corresponds to the default instance  
$svr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.Server  
  
#Create a linked server object which corresponds to an OLEDB type of SQL server product  
$lsvr = New-Object -TypeName Microsoft.SqlServer.Management.SMO.LinkedServer -ArgumentList $svr,"OLEDBSRV"  
  
#When the product name is SQL Server the remaining properties are not required to be set.
$lsvr.ProductName = "SQL Server"
  
#Create the Database Object  
$lsvr.Create()
```  
