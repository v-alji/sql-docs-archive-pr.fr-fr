---
title: 'Leçon 1 : créer le projet Visual Studio du schéma RDL | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f420509c-51aa-4170-8c25-64c2954f4bb9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: a8411e3f0458ccda8c291d5c86a4467bb051a263
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694887"
---
# <a name="lesson-1-create-the-rdl-schema-visual-studio-project"></a><span data-ttu-id="5ac37-102">Leçon 1 : Créer le projet Visual Studio du schéma RDL</span><span class="sxs-lookup"><span data-stu-id="5ac37-102">Lesson 1: Create the RDL Schema Visual Studio Project</span></span>
  <span data-ttu-id="5ac37-103">Dans ce didacticiel, vous allez créer une application console simple.</span><span class="sxs-lookup"><span data-stu-id="5ac37-103">For this tutorial, you will create a simple console application.</span></span> <span data-ttu-id="5ac37-104">Ce didacticiel part du principe que vous développez dans [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5ac37-104">This tutorial assumes you are developing in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5ac37-105">Lorsque vous accédez au service Web Report Server qui s'exécute sur [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, vous devez ajouter "_SQLExpress" au chemin d'accès "ReportServer".</span><span class="sxs-lookup"><span data-stu-id="5ac37-105">When accessing the Report Server Web service running on [!INCLUDE[ssExpress](../includes/ssexpress-md.md)] with Advanced Services, you must append "_SQLExpress" to the "ReportServer" path.</span></span> <span data-ttu-id="5ac37-106">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="5ac37-106">For example:</span></span>  
>   
>  `http://myserver/reportserver_sqlexpress/reportservice2010.asmx"`  
  
### <a name="to-create-the-web-service-proxy"></a><span data-ttu-id="5ac37-107">Pour créer le proxy de service Web</span><span class="sxs-lookup"><span data-stu-id="5ac37-107">To create the web service proxy</span></span>  
  
1.  <span data-ttu-id="5ac37-108">Dans le menu **Démarrer** , sélectionnez **Tous les programmes**, Microsoft Visual Studio, **Visual Studio Tools**, puis **Invite de commandes de Visual Studio 2010**.</span><span class="sxs-lookup"><span data-stu-id="5ac37-108">From the **Start** menu, select **All Programs**, then Microsoft Visual Studio, then **Visual Studio Tools**, and then **Visual Studio 2010 Command Prompt**.</span></span>  
  
2.  <span data-ttu-id="5ac37-109">Dans la fenêtre d'invite de commandes, exécutez la commande suivante si vous utilisez C# :</span><span class="sxs-lookup"><span data-stu-id="5ac37-109">In the command prompt window, run the following command if you are using C#:</span></span>  
  
    ```  
    wsdl /language:CS /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="5ac37-110">Si vous utilisez Visual Basic, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="5ac37-110">If you are using Visual Basic, then run the following command:</span></span>  
  
    ```  
    wsdl /language:VB /n:"ReportService2010" http://<Server Name>/reportserver/reportservice2010.asmx?wsdl  
    ```  
  
     <span data-ttu-id="5ac37-111">Cette commande génère un fichier .cs ou .vb.</span><span class="sxs-lookup"><span data-stu-id="5ac37-111">This command generates a .cs or .vb file.</span></span> <span data-ttu-id="5ac37-112">Vous ajouterez ce fichier à votre application.</span><span class="sxs-lookup"><span data-stu-id="5ac37-112">You will add this file to your application.</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="5ac37-113">Pour créer une application console</span><span class="sxs-lookup"><span data-stu-id="5ac37-113">To create a console application</span></span>  
  
1.  <span data-ttu-id="5ac37-114">Dans le menu **Fichier** , pointez sur **Nouveau**, puis cliquez sur **Projet** pour ouvrir la boîte de dialogue **Nouveau projet** .</span><span class="sxs-lookup"><span data-stu-id="5ac37-114">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="5ac37-115">Dans le volet gauche, sous **Modèles installés**, cliquez sur le nœud **Visual Basic** ou **Visual C#** , puis sélectionnez une catégorie de types de projets dans la liste développée.</span><span class="sxs-lookup"><span data-stu-id="5ac37-115">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="5ac37-116">Choisissez le type de projet **Application console** .</span><span class="sxs-lookup"><span data-stu-id="5ac37-116">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="5ac37-117">Dans la zone **Nom** , tapez le nom de votre projet.</span><span class="sxs-lookup"><span data-stu-id="5ac37-117">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="5ac37-118">Tapez le nom `SampleRDLSchema` .</span><span class="sxs-lookup"><span data-stu-id="5ac37-118">Type the name `SampleRDLSchema`.</span></span>  
  
5.  <span data-ttu-id="5ac37-119">Dans la zone **Emplacement** , entrez le chemin d'accès de l'emplacement où vous voulez enregistrer le projet, ou cliquez sur **Parcourir** pour rechercher le dossier.</span><span class="sxs-lookup"><span data-stu-id="5ac37-119">In the **Location** box, type the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="5ac37-120">Une vue réduite de votre projet s’affiche dans Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="5ac37-120">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
7.  <span data-ttu-id="5ac37-121">Dans le menu **Projet** , cliquez sur **Ajouter un élément existant**.</span><span class="sxs-lookup"><span data-stu-id="5ac37-121">On the **Project** menu, click **Add Existing Item**.</span></span>  
  
8.  <span data-ttu-id="5ac37-122">Naviguez jusqu'à l'emplacement où vous avez généré le fichier .cs ou .vb, sélectionnez le fichier, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="5ac37-122">Navigate to the location for the .cs or .vb file you generated, then select the file, and then click **Add**.</span></span>  
  
     <span data-ttu-id="5ac37-123">Vous devrez également ajouter une référence à l'espace de noms <xref:System.Web.Services> pour que votre référence Web fonctionne.</span><span class="sxs-lookup"><span data-stu-id="5ac37-123">You will also need to add a reference to the <xref:System.Web.Services> namespace for your Web reference to work.</span></span>  
  
9. <span data-ttu-id="5ac37-124">Dans le menu Projet, cliquez sur **Ajouter une référence**.</span><span class="sxs-lookup"><span data-stu-id="5ac37-124">On the Project menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="5ac37-125">Dans la boîte de dialogue **Ajouter une référence** , dans l'onglet **.NET** , sélectionnez **System.Web.Services**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ac37-125">In the **Add Reference** dialog box, in the **.NET** tab, select **System.Web.Services**, then click **OK**.</span></span>  
  
     <span data-ttu-id="5ac37-126">Pour plus d’informations sur la façon de se connecter au service Web Report Server, consultez [génération d’applications à l’aide du service Web et du .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span><span class="sxs-lookup"><span data-stu-id="5ac37-126">For more information about how to connect to the Report Server Web service, see [Building Applications Using the Web Service and the .NET Framework](../reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md).</span></span>  
  
10. <span data-ttu-id="5ac37-127">Dans l'Explorateur de solutions, développez le nœud du projet.</span><span class="sxs-lookup"><span data-stu-id="5ac37-127">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="5ac37-128">Un fichier de code portant le nom par défaut Program.cs (Module1.vb pour [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) a été ajouté à votre projet.</span><span class="sxs-lookup"><span data-stu-id="5ac37-128">You will see a code file with the default name of Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
11. <span data-ttu-id="5ac37-129">Ouvrez le fichier Program.cs (Module1.vb pour [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) et remplacez le code par le suivant :</span><span class="sxs-lookup"><span data-stu-id="5ac37-129">Open the Program.cs (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) file and replace the code with the following:</span></span>  
  
     <span data-ttu-id="5ac37-130">Le code suivant fournit les stubs de méthode que nous utiliserons pour implémenter les fonctionnalités de chargement, de mise à jour et d'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="5ac37-130">The following code provides the method stubs we will use to implement the Load, Update and Save functionality.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using ReportService2010;  
  
    namespace SampleRDLSchema  
    {  
        class ReportUpdater  
        {  
            ReportingService2010 _reportService;  
  
            static void Main(string[] args)  
            {  
                ReportUpdater reportUpdater = new ReportUpdater();  
                reportUpdater.UpdateReport();  
            }  
  
            private void UpdateReport()  
            {  
                try  
                {  
                    // Set up the Report Service connection  
                    _reportService = new ReportingService2010();  
                    _reportService.Credentials =  
                        System.Net.CredentialCache.DefaultCredentials;  
                    _reportService.Url =  
                       "http://<Server Name>/reportserver/" +  
                                       "reportservice2010.asmx";  
  
                    // Call the methods to update a report definition  
                    LoadReportDefinition();  
                    UpdateReportDefinition();  
                    PublishReportDefinition();  
                }  
                catch (Exception ex)  
                {  
                    System.Console.WriteLine(ex.Message);  
                }  
            }  
  
            private void LoadReportDefinition()  
            {  
                //Lesson 3: Load a report definition from the report   
                //          catalog  
            }  
  
            private void UpdateReportDefinition()  
            {  
                //Lesson 4: Update the report definition using the    
                //          classes generated from the RDL Schema  
            }  
  
            private void PublishReportDefinition()  
            {  
                //Lesson 5: Publish the updated report definition back   
                //          to the report catalog  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Imports System  
    Imports System.Collections.Generic  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports ReportService2010  
  
    Namespace SampleRDLSchema  
  
        Module ReportUpdater  
  
            Private m_reportService As ReportingService2010  
  
            Public Sub Main(ByVal args As String())  
  
                Try  
                    'Set up the Report Service connection  
                    m_reportService = New ReportingService2010  
                    m_reportService.Credentials = _  
                        System.Net.CredentialCache.DefaultCredentials  
                    m_reportService.Url = _  
                        "http:// <Server Name>/reportserver/" & _  
                               "reportservice2010.asmx"  
  
                    'Call the methods to update a report definition  
                    LoadReportDefinition()  
                    UpdateReportDefinition()  
                    PublishReportDefinition()  
                Catch ex As Exception  
                    System.Console.WriteLine(ex.Message)  
                End Try  
  
            End Sub  
  
            Private Sub LoadReportDefinition()  
                'Lesson 3: Load a report definition from the report   
                '          catalog  
            End Sub  
  
            Private Sub UpdateReportDefinition()  
                'Lesson 4: Update the report definition using the   
                '          classes generated from the RDL Schema  
            End Sub  
  
            Private Sub PublishReportDefinition()  
                'Lesson 5: Publish the updated report definition back   
                '          to the report catalog  
            End Sub  
  
        End Module  
  
    End Namespace   
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="5ac37-131">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="5ac37-131">Next Lesson</span></span>  
 <span data-ttu-id="5ac37-132">Dans la prochaine leçon, vous allez utiliser l'outil de définition de schéma XML (Xsd.exe) pour générer des classes à partir du schéma RDL et les inclure dans votre projet.</span><span class="sxs-lookup"><span data-stu-id="5ac37-132">In the next lesson, you will use the XML Schema Definition Tool (Xsd.exe) to generate classes from the RDL schema and include them in your project.</span></span> <span data-ttu-id="5ac37-133">Consultez [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span><span class="sxs-lookup"><span data-stu-id="5ac37-133">See [Lesson 2: Generate Classes from the RDL Schema using the xsd Tool](../../2014/tutorials/lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ac37-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5ac37-134">See Also</span></span>  
 <span data-ttu-id="5ac37-135">[Mise à jour des rapports à l’aide de classes générées à partir du schéma RDL &#40;didacticiel SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="5ac37-135">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="5ac37-136">RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ac37-136">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
