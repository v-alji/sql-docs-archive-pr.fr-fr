---
title: Utilisation de l’accès URL dans une application Windows | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Windows applications [Reporting Services]
- Web Browser controls [Reporting Services]
- Windows Forms [Reporting Services]
- browser controls [Reporting Services]
- URL access [Reporting Services], Windows applications
ms.assetid: a4b222e5-0cbd-409c-92c4-046a674db8ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8f8b901481b1d6fcc3cdd8626b43cd3a69174c1a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703960"
---
# <a name="using-url-access-in-a-windows-application"></a><span data-ttu-id="337dc-102">Utilisation de l'accès URL dans une application Windows</span><span class="sxs-lookup"><span data-stu-id="337dc-102">Using URL Access in a Windows Application</span></span>
  <span data-ttu-id="337dc-103">Même si l'accès URL à un serveur de rapports est optimisé pour un environnement Web, vous pouvez également utiliser l'accès URL pour incorporer des rapports [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] dans une application [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="337dc-103">Although URL access to a report server is optimized for a Web environment, you can also use URL access to embed [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] reports into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application.</span></span> <span data-ttu-id="337dc-104">Toutefois, l'accès URL qui nécessite des Windows Forms requiert toujours l'utilisation de la technologie du navigateur Web.</span><span class="sxs-lookup"><span data-stu-id="337dc-104">However, URL access that involves Windows Forms still requires that you use Web browser technology.</span></span> <span data-ttu-id="337dc-105">Vous pouvez utiliser les scénarios d'intégration suivants avec l'accès URL et les Windows Forms :</span><span class="sxs-lookup"><span data-stu-id="337dc-105">You can use the following integration scenarios with URL access and Windows Forms:</span></span>  
  
-   <span data-ttu-id="337dc-106">Afficher un rapport dans une application Windows Form en démarrant un navigateur Web par programme.</span><span class="sxs-lookup"><span data-stu-id="337dc-106">Display a report from a Windows Form application by starting a Web browser programmatically.</span></span>  
  
-   <span data-ttu-id="337dc-107">Utiliser le contrôle <xref:System.Windows.Forms.WebBrowser> sur un Windows Form pour afficher un rapport.</span><span class="sxs-lookup"><span data-stu-id="337dc-107">Use the <xref:System.Windows.Forms.WebBrowser> control on a Windows Form to display a report.</span></span>  
  
## <a name="starting-internet-explorer-from-a-windows-form"></a><span data-ttu-id="337dc-108">Démarrage d'Internet Explorer à partir d'un Windows Form</span><span class="sxs-lookup"><span data-stu-id="337dc-108">Starting Internet Explorer from a Windows Form</span></span>  
 <span data-ttu-id="337dc-109">Vous pouvez utiliser la classe <xref:System.Diagnostics.Process> pour accéder à un processus qui s'exécute sur un ordinateur.</span><span class="sxs-lookup"><span data-stu-id="337dc-109">You can use the <xref:System.Diagnostics.Process> class to access a process that is running on a computer.</span></span> <span data-ttu-id="337dc-110">La <xref:System.Diagnostics.Process> classe est une [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construction utile pour démarrer, arrêter, contrôler et surveiller des applications.</span><span class="sxs-lookup"><span data-stu-id="337dc-110">The <xref:System.Diagnostics.Process> class is a useful [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] construct for starting, stopping, controlling, and monitoring applications.</span></span> <span data-ttu-id="337dc-111">Pour consulter un rapport spécifique dans votre base de données du serveur de rapports, vous pouvez démarrer le processus **IExplore**, en passant l’URL au rapport.</span><span class="sxs-lookup"><span data-stu-id="337dc-111">To view a specific report in your report server database, you can start the **IExplore** process, passing in the URL to the report.</span></span> <span data-ttu-id="337dc-112">L'exemple de code suivant peut être utilisé pour démarrer [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer et passer une URL de rapport spécifique lorsque l'utilisateur clique sur un bouton dans un Windows Form.</span><span class="sxs-lookup"><span data-stu-id="337dc-112">The following code example can be used to start [!INCLUDE[msCoName](../../includes/msconame-md.md)] Internet Explorer and pass a specific report URL when the user clicks a button on a Windows Form.</span></span>  
  
```vb  
Private Sub viewReportButton_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles viewReportButton.Click  
   ' Build the URL access string based on values supplied by a user  
   Dim url As String = serverUrlTextBox.Text + "?" & reportPathTextBox.Text & _  
   "&rs:Command=Render" & "&rs:Format=HTML4.0"  
  
   ' If the user does not select the toolbar check box,  
   ' turn the toolbar off in the HTML Viewer  
   If toolbarCheckBox.Checked = False Then  
      url += "&rc:Toolbar=False"  
   End If  
   ' load report in the Web browser  
   Try  
      System.Diagnostics.Process.Start("IExplore", url)  
   Catch  
      MessageBox.Show("The system could not start the specified report using Internet Explorer.", _  
      "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error)  
   End Try  
End Sub 'viewReportButton_Click  
```  
  
```csharp  
// Sample click event for a Button control on a Windows Form  
private void viewReportButton_Click(object sender, System.EventArgs e)  
{  
   // Build the URL access string based on values supplied by a user  
   string url = serverUrlTextBox.Text + "?" + reportPathTextBox.Text +  
      "&rs:Command=Render" + "&rs:Format=HTML4.0";  
  
   // If the user does not check the toolbar check box,  
   // turn the toolbar off in the HTML Viewer  
   if (toolbarCheckBox.Checked == false)  
      url += "&rc:Toolbar=False";  
  
   // load report in the Web browser  
   try  
   {  
      System.Diagnostics.Process.Start("IExplore", url);  
   }  
  
   catch (Exception)  
   {  
      MessageBox.Show(  
         "The system could not open the specified report using Internet Explorer.",   
         "An error has occurred", MessageBoxButtons.OK, MessageBoxIcon.Error);  
   }  
}  
```  
  
## <a name="embedding-a-browser-control-on-a-windows-form"></a><span data-ttu-id="337dc-113">Incorporation d'un contrôle de navigateur Web sur un Windows Form</span><span class="sxs-lookup"><span data-stu-id="337dc-113">Embedding a Browser Control on a Windows Form</span></span>  
 <span data-ttu-id="337dc-114">Si vous ne souhaitez pas consulter votre rapport dans un navigateur Web externe, vous pouvez incorporer de façon transparente un navigateur Web dans le cadre de votre Windows Form à l'aide du contrôle <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="337dc-114">If you do not want to view your report in an external Web browser, you can embed a Web browser seamlessly as part of your Windows Form using the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  
  
###### <a name="to-add-the-webbrowser-control-to-your-windows-form"></a><span data-ttu-id="337dc-115">Pour ajouter le contrôle WebBrowser à votre Windows Form</span><span class="sxs-lookup"><span data-stu-id="337dc-115">To add the WebBrowser control to your Windows Form</span></span>  
  
1.  <span data-ttu-id="337dc-116">Créez une nouvelle application Windows dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] ou [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="337dc-116">Create a new Windows application in either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[csprcs](../../includes/csprcs-md.md)] or [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
2.  <span data-ttu-id="337dc-117">Localisez le contrôle <xref:System.Windows.Forms.WebBrowser> dans la boîte de dialogue **Boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="337dc-117">Locate the <xref:System.Windows.Forms.WebBrowser> control in the **Toolbox** Dialog Box.</span></span>  
  
     <span data-ttu-id="337dc-118">Si la **Boîte à outils** n’est pas visible, vous pouvez y accéder en cliquant sur l’élément de menu **Affichage** et en sélectionnant **Boîte à outils**.</span><span class="sxs-lookup"><span data-stu-id="337dc-118">If the **Toolbox** is not visible you can access it by clicking the **View** menu item and selecting **Toolbox**.</span></span>  
  
3.  <span data-ttu-id="337dc-119">Faites glisser le contrôle <xref:System.Windows.Forms.WebBrowser> vers l’aire de conception de votre Windows Form.</span><span class="sxs-lookup"><span data-stu-id="337dc-119">Drag the <xref:System.Windows.Forms.WebBrowser>control onto the design surface of your Windows Form.</span></span>  
  
     <span data-ttu-id="337dc-120">Le contrôle <xref:System.Windows.Forms.WebBrowser> nommé webBrowser1 est ajouté au Formulaire</span><span class="sxs-lookup"><span data-stu-id="337dc-120">The <xref:System.Windows.Forms.WebBrowser>control named webBrowser1 is added to the Form</span></span>  
  
 <span data-ttu-id="337dc-121">Dirigez le contrôle <xref:System.Windows.Forms.WebBrowser> vers une URL en appelant sa méthode **Navigate**.</span><span class="sxs-lookup"><span data-stu-id="337dc-121">You direct the <xref:System.Windows.Forms.WebBrowser> control to a URL by calling its **Navigate** method.</span></span> <span data-ttu-id="337dc-122">Vous pouvez assigner une chaîne d'accès URL spécifique à votre contrôle <xref:System.Windows.Forms.WebBrowser> au moment de l'exécution comme l'illustre l'exemple suivant.</span><span class="sxs-lookup"><span data-stu-id="337dc-122">You can assign a specific URL access string to your <xref:System.Windows.Forms.WebBrowser> control at run time as shown in the following example.</span></span>  
  
```vb  
Dim url As String = "http://localhost/reportserver?/" & _  
                    "AdventureWorks2012 Sample Reports/" & _  
                    "Company Sales&rs:Command=Render"  
WebBrowser1.Navigate(url)  
```  
  
```csharp  
string url = "http://localhost/reportserver?/" +  
             "AdventureWorks2012 Sample Reports/" +  
             "Company Sales&rs:Command=Render";  
webBrowser1.Navigate(url);  
```  
  
## <a name="see-also"></a><span data-ttu-id="337dc-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="337dc-123">See Also</span></span>  
 <span data-ttu-id="337dc-124">[Intégration de Reporting Services dans des applications](../application-integration/integrating-reporting-services-into-applications.md) </span><span class="sxs-lookup"><span data-stu-id="337dc-124">[Integrating Reporting Services into Applications](../application-integration/integrating-reporting-services-into-applications.md) </span></span>  
 <span data-ttu-id="337dc-125">[Intégration d’Reporting Services à l’aide de l’accès URL](integrating-reporting-services-using-url-access.md) </span><span class="sxs-lookup"><span data-stu-id="337dc-125">[Integrating Reporting Services Using URL Access](integrating-reporting-services-using-url-access.md) </span></span>  
 <span data-ttu-id="337dc-126">[Intégration de Reporting Services à l’aide de SOAP](integrating-reporting-services-using-soap.md) </span><span class="sxs-lookup"><span data-stu-id="337dc-126">[Integrating Reporting Services Using SOAP](integrating-reporting-services-using-soap.md) </span></span>  
 <span data-ttu-id="337dc-127">[Intégration de Reporting Services à l’aide des contrôles ReportViewer](integrating-reporting-services-using-reportviewer-controls.md) </span><span class="sxs-lookup"><span data-stu-id="337dc-127">[Integrating Reporting Services Using the ReportViewer Controls](integrating-reporting-services-using-reportviewer-controls.md) </span></span>  
 [<span data-ttu-id="337dc-128">Accès URL &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="337dc-128">URL Access &#40;SSRS&#41;</span></span>](../url-access-ssrs.md)  
  
  
