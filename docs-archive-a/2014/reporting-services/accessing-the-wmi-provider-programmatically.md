---
title: Accès au fournisseur WMI par programmation | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
ms.assetid: 67bd266b-1484-4863-8152-060a993420a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6546d046fcd176eb5cc5fd462ea9a8a31c25b803
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611621"
---
# <a name="accessing-the-wmi-provider-programmatically"></a><span data-ttu-id="cf5a8-102">Accès au fournisseur WMI par programmation</span><span class="sxs-lookup"><span data-stu-id="cf5a8-102">Accessing the WMI Provider Programmatically</span></span>
  <span data-ttu-id="cf5a8-103">Cette rubrique est en cours d'élaboration.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-103">This topic is under construction.</span></span>  
  
## <a name="wmi-provider-overview"></a><span data-ttu-id="cf5a8-104">Vue d'ensemble du fournisseur WMI</span><span class="sxs-lookup"><span data-stu-id="cf5a8-104">WMI Provider Overview</span></span>  
 <span data-ttu-id="cf5a8-105">L’espace de noms utilisé pour obtenir des informations sur [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] dans les exemples de code contenus dans cette rubrique est **System.Management**, qui provient du [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf5a8-105">The namespace used to obtain information about [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] in the code samples shown in this topic is the **System.Management** namespace, found in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="cf5a8-106">L’espace de noms **System.Management** fournit un ensemble de classes de code managé par le biais desquelles les applications [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] peuvent accéder à des informations de gestion et les manipuler.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-106">The **System.Management** namespace provides a set of managed code classes through which [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] applications can access and manipulate management information.</span></span> <span data-ttu-id="cf5a8-107">Pour plus d’informations sur l’utilisation des classes WMI de Reporting Services à l’aide de l’espace de noms **System.Management**, consultez « Accès aux informations de gestion avec System.Management » dans le SDK [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cf5a8-107">For more information on using the Reporting Services WMI classes using the **System.Management** namespace, see "Accessing Management Information with System.Managment" in the [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
## <a name="finding-a-report-server-instance"></a><span data-ttu-id="cf5a8-108">Recherche d'une instance de serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="cf5a8-108">Finding a Report Server Instance</span></span>  
 <span data-ttu-id="cf5a8-109">La méthode privilégiée pour rechercher des informations sur vos installations de serveur de rapports consiste à énumérer la collection d'instances WMI.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-109">The preferred way of finding information on your report server installations is to enumerate through the WMI instance collection.</span></span> <span data-ttu-id="cf5a8-110">L'exemple suivant indique comment rechercher des propriétés sur chaque instance de serveur de rapports en créant une collection et en effectuant une boucle dans la collection pour afficher les propriétés.</span><span class="sxs-lookup"><span data-stu-id="cf5a8-110">The example below shows how to find properties on every report server instance by creating a collection, and looping through the collection to display the properties.</span></span>  
  
```vb  
Imports System  
Imports System.Management  
Imports System.IO  
  
Module Module1  
    Sub Main()  
        Const WmiNamespace As String = "\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\Admin"  
        Const WmiRSClass As String = _  
           "\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\admin:MSReportServer_ConfigurationSetting"  
  
        Dim serverClass As ManagementClass  
        Dim scope As ManagementScope  
        scope = New ManagementScope(WmiNamespace)  
        'Connect to the Reporting Services namespace.  
        scope.Connect()  
  
        'Create the server class.  
        serverClass = New ManagementClass(WmiRSClass)  
        'Connect to the management object.  
        serverClass.Get()  
        If serverClass Is Nothing Then Throw New Exception("No class found")  
  
        'Loop through the instances of the server class.  
        Dim instances As ManagementObjectCollection = serverClass.GetInstances()  
        Dim instance As ManagementObject  
        For Each instance In instances  
            Console.Out.WriteLine("Instance Detected")  
            Dim instProps As PropertyDataCollection = instance.Properties  
            Dim prop As PropertyData  
            For Each prop In instProps  
                Dim name As String = prop.Name  
                Dim val As Object = prop.Value  
                Console.Out.Write("Property Name: " + name)  
                If val Is Nothing Then  
                    Console.Out.WriteLine("     Value: <null>")  
                Else  
                    Console.Out.WriteLine("     Value: " + val.ToString())  
                End If  
            Next  
        Next  
  
        Console.WriteLine("--- Press any key ---")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Management;  
using System.IO;  
[assembly: CLSCompliant(true)]  
  
class Class1  
{  
    [STAThread]  
    static void Main(string[] args)  
    {  
        const string WmiNamespace = @"\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\Admin";  
        const string WmiRSClass =  
          @"\\<ServerName>\root\Microsoft\SqlServer\ReportServer\<InstanceName>\v10\admin:MSReportServer_ConfigurationSetting";  
        ManagementClass serverClass;  
        ManagementScope scope;  
        scope = new ManagementScope(WmiNamespace);  
  
        // Connect to the Reporting Services namespace.  
        scope.Connect();  
        // Create the server class.  
        serverClass = new ManagementClass(WmiRSClass);  
        // Connect to the management object.  
        serverClass.Get();  
        if (serverClass == null)  
            throw new Exception("No class found");  
  
        // Loop through the instances of the server class.  
        ManagementObjectCollection instances = serverClass.GetInstances();  
  
        foreach (ManagementObject instance in instances)  
        {  
            Console.Out.WriteLine("Instance Detected");  
            PropertyDataCollection instProps = instance.Properties;  
            foreach (PropertyData prop in instProps)  
            {  
                string name = prop.Name;  
                object val = prop.Value;  
                Console.Out.Write("Property Name: " + name);  
                if (val != null)  
                    Console.Out.WriteLine("     Value: " + val.ToString());  
                else  
                    Console.Out.WriteLine("     Value: <null>");  
            }  
        }  
        Console.WriteLine("\n--- Press any key ---");  
        Console.ReadKey();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf5a8-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cf5a8-111">See Also</span></span>  
 <span data-ttu-id="cf5a8-112">[Accéder au fournisseur WMI Reporting Services](tools/access-the-reporting-services-wmi-provider.md) </span><span class="sxs-lookup"><span data-stu-id="cf5a8-112">[Access the Reporting Services WMI Provider](tools/access-the-reporting-services-wmi-provider.md) </span></span>  
 [<span data-ttu-id="cf5a8-113">Fichier de configuration RSReportServer</span><span class="sxs-lookup"><span data-stu-id="cf5a8-113">RSReportServer Configuration File</span></span>](report-server/rsreportserver-config-configuration-file.md)  
  
  
