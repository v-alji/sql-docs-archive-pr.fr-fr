---
title: Connexion aux sources de données dans la tâche de script | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- connections [Integration Services], scripts
- Integration Services packages, connections
- connection managers [Integration Services], scripts
- scripts [Integration Services], connections
- SSIS packages, connections
- packages [Integration Services], connections
- Script task [Integration Services], connections
- Connections property
- SQL Server Integration Services packages, connections
- SSIS Script task, connections
ms.assetid: 9c008380-715b-455b-9da7-22572d67c388
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c8374271c7972498361a83e4bbe87ad12265827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700050"
---
# <a name="connecting-to-data-sources-in-the-script-task"></a><span data-ttu-id="0cd7b-102">Connexion à des sources de données dans la tâche de script</span><span class="sxs-lookup"><span data-stu-id="0cd7b-102">Connecting to Data Sources in the Script Task</span></span>
  <span data-ttu-id="0cd7b-103">Les gestionnaires de connexions fournissent un accès à des sources de données qui ont été configurées dans le package.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-103">Connection managers provide access to data sources that have been configured in the package.</span></span> <span data-ttu-id="0cd7b-104">Pour plus d’informations, consultez [Connexions Integration Services &#40;SSIS&#41;](../../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="0cd7b-104">For more information, see [Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
 <span data-ttu-id="0cd7b-105">La tâche de script peut accéder à ces gestionnaires de connexions via la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> de l’objet**Dts**.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-105">The Script task can access these connection managers through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property of the **Dts** object.</span></span> <span data-ttu-id="0cd7b-106">Chaque gestionnaire de connexions compris dans la collection <xref:Microsoft.SqlServer.Dts.Runtime.Connections> stocke des informations sur la manière d'établir une connexion à la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-106">Each connection manager in the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection stores information about how to connect to the underlying data source.</span></span>  
  
 <span data-ttu-id="0cd7b-107">Lorsque vous appelez la méthode <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> d'un gestionnaire de connexions, le gestionnaire de connexions se connecte à la source de données, s'il n'est pas déjà connecté, puis renvoie la connexion ou les informations de connexion appropriées que vous devez utiliser dans le code de votre tâche de script.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-107">When you call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a connection manager, the connection manager connects to the data source, if it is not already connected, and returns the appropriate connection or connection information for you to use in your Script task code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0cd7b-108">Vous devez connaître le type de connexion renvoyé par le gestionnaire de connexions avant d’appeler `AcquireConnection` .</span><span class="sxs-lookup"><span data-stu-id="0cd7b-108">You must know the type of connection returned by the connection manager before calling `AcquireConnection`.</span></span> <span data-ttu-id="0cd7b-109">Étant donné que la tâche de script a `Option Strict` activé, vous devez effectuer un cast de la connexion, qui est retournée en tant que type `Object`, vers le type de connexion approprié avant de pouvoir l'utiliser.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-109">Because the Script task has `Option Strict` enabled, you must cast the connection, which is returned as type `Object`, to the appropriate connection type before you can use it.</span></span>  
  
 <span data-ttu-id="0cd7b-110">Vous pouvez utiliser la méthode <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> de la collection <xref:Microsoft.SqlServer.Dts.Runtime.Connections> renvoyée par la propriété <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> pour rechercher une connexion existante avant d'utiliser la connexion dans votre code.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-110">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property to look for an existing connection before using the connection in your code.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0cd7b-111">Vous ne pouvez pas appeler la méthode AcquireConnection des gestionnaires de connexions qui renvoient des objets non managés, tels que le gestionnaire de connexions OLE DB et le gestionnaire de connexions Excel, dans le code managé d’une tâche de script.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-111">You cannot call the AcquireConnection method of connection managers that return unmanaged objects, such as the OLE DB connection manager and the Excel connection manager, in the managed code of a Script task.</span></span> <span data-ttu-id="0cd7b-112">Toutefois, vous pouvez lire la propriété ConnectionString de ces gestionnaires de connexions et vous connecter directement à la source de données dans votre code en utilisant la chaîne de connexion avec un `OledbConnection` de l’espace de noms **System. Data. OleDb** .</span><span class="sxs-lookup"><span data-stu-id="0cd7b-112">However, you can read the ConnectionString property of these connection managers, and connect to the data source directly in your code by using the connection string with an `OledbConnection` from the **System.Data.OleDb** namespace.</span></span>  
>   
>  <span data-ttu-id="0cd7b-113">Si vous devez appeler la méthode AcquireConnection d’un gestionnaire de connexions qui retourne un objet non managé, utilisez un gestionnaire de connexions [!INCLUDE[vstecado](../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cd7b-113">If you must call the AcquireConnection method of a connection manager that returns an unmanaged object, use an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager.</span></span> <span data-ttu-id="0cd7b-114">Lorsque vous configurez le gestionnaire de connexions [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] afin d'utiliser un fournisseur OLE DB, il se connecte en utilisant le fournisseur de données [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] pour OLE DB.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-114">When you configure the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager to use an OLE DB provider, it connects by using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB.</span></span> <span data-ttu-id="0cd7b-115">Dans ce cas, la méthode AcquireConnection retourne un `System.Data.OleDb.OleDbConnection` au lieu d’un objet non managé.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-115">In this case, the AcquireConnection method returns a `System.Data.OleDb.OleDbConnection` instead of an unmanaged object.</span></span> <span data-ttu-id="0cd7b-116">Pour configurer un gestionnaire de connexions [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] en vue de son utilisation avec une source de données Excel, sélectionnez le fournisseur [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB pour Jet, spécifiez un fichier Excel, puis entrez `Excel 8.0` (pour Excel 97 et versions ultérieures) comme valeur **Propriétés étendues** dans la page **Tout** de la boîte de dialogue **Gestionnaire de connexions**.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-116">To configure an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager for use with an Excel data source, select the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB Provider for Jet, specify an Excel file, and enter `Excel 8.0` (for Excel 97 and later) as the value of **Extended Properties** on the **All** page of the **Connection Manager** dialog box.</span></span>  
  
## <a name="connections-example"></a><span data-ttu-id="0cd7b-117">Exemple de connexions</span><span class="sxs-lookup"><span data-stu-id="0cd7b-117">Connections Example</span></span>  
 <span data-ttu-id="0cd7b-118">L'exemple suivant montre comment accéder aux gestionnaires de connexions à partir de la tâche de script.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-118">The following example demonstrates how to access connection managers from within the Script task.</span></span> <span data-ttu-id="0cd7b-119">Il est supposé dans l’exemple que vous avez créé et configuré un gestionnaire de connexions [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] nommé **Connexion ADO.NET test** et un gestionnaire de connexions de fichiers plats nommé **Connexion de fichiers plats test**.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-119">The sample assumes that you have created and configured an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager named **Test ADO.NET Connection** and a Flat File connection manager named **Test Flat File Connection**.</span></span> <span data-ttu-id="0cd7b-120">Notez que le gestionnaire de connexions [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] retourne un objet `SqlConnection` que vous pouvez utiliser immédiatement pour vous connecter à la source de données.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-120">Note that the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager returns a `SqlConnection` object that you can use immediately to connect to the data source.</span></span> <span data-ttu-id="0cd7b-121">Le gestionnaire de connexions de fichiers plats, en revanche, retourne uniquement une chaîne qui contient le chemin d'accès et le nom du fichier.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-121">The Flat File connection manager, on the other hand, returns only a string that contains the path and file name.</span></span> <span data-ttu-id="0cd7b-122">Vous devez utiliser les méthodes de l'espace de noms `System.IO` pour ouvrir et utiliser le fichier plat.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-122">You must use methods from the `System.IO` namespace to open and work with the flat file.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myADONETConnection As SqlClient.SqlConnection  
    myADONETConnection = _  
        DirectCast(Dts.Connections("Test ADO.NET Connection").AcquireConnection(Dts.Transaction), _  
        SqlClient.SqlConnection)  
    MsgBox(myADONETConnection.ConnectionString, _  
        MsgBoxStyle.Information, "ADO.NET Connection")  
  
    Dim myFlatFileConnection As String  
    myFlatFileConnection = _  
        DirectCast(Dts.Connections("Test Flat File Connection").AcquireConnection(Dts.Transaction), _  
        String)  
    MsgBox(myFlatFileConnection, MsgBoxStyle.Information, "Flat File Connection")  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
  
public class ScriptMain  
{  
  
        public void Main()  
        {  
            SqlConnection myADONETConnection = new SqlConnection();  
            myADONETConnection = (SqlConnection)(Dts.Connections["Test ADO.NET Connection"].AcquireConnection(Dts.Transaction)as SqlConnection);  
            MessageBox.Show(myADONETConnection.ConnectionString, "ADO.NET Connection");  
  
            string myFlatFileConnection;  
            myFlatFileConnection = (string)(Dts.Connections["Test Flat File Connection"].AcquireConnection(Dts.Transaction) as String);  
            MessageBox.Show(myFlatFileConnection, "Flat File Connection");  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
  
```  
  
<span data-ttu-id="0cd7b-123">![Icône de Integration Services (petite)](../../media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="0cd7b-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0cd7b-124">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="0cd7b-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0cd7b-125">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="0cd7b-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0cd7b-126">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="0cd7b-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd7b-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cd7b-127">See Also</span></span>  
 <span data-ttu-id="0cd7b-128">[Integration Services &#40;les connexions de&#41; SSIS](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="0cd7b-128">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="0cd7b-129">Créer des gestionnaires de connexions</span><span class="sxs-lookup"><span data-stu-id="0cd7b-129">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
