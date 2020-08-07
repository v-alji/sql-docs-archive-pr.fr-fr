---
title: 'Leçon 2 : générer des classes à partir du schéma RDL à l’aide de l’outil XSD | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a81c87f1-7977-4b30-b6ac-b38b3e2b6398
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 2c5db118ad8f94afc72cea44b9a2489f2b4fd7f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703535"
---
# <a name="lesson-2-generate-classes-from-the-rdl-schema-using-the-xsd-tool"></a><span data-ttu-id="b312d-102">Leçon 2 : Générer des classes à partir du schéma RDL à l’aide de l’outil xsd</span><span class="sxs-lookup"><span data-stu-id="b312d-102">Lesson 2: Generate Classes from the RDL Schema using the xsd Tool</span></span>
  <span data-ttu-id="b312d-103">Une fois que vous avez créé votre projet [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], l'étape suivante consiste à extraire une copie locale du schéma de la définition du rapport et à exécuter l'outil de définition du schéma XML (Xsd.exe).</span><span class="sxs-lookup"><span data-stu-id="b312d-103">After you have created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project, the next step is to retrieve a local copy of the report definition schema and run the XML Schema Definition Tool (Xsd.exe).</span></span>  
  
### <a name="to-generate-the-rdl-classes"></a><span data-ttu-id="b312d-104">Pour générer les classes RDL</span><span class="sxs-lookup"><span data-stu-id="b312d-104">To generate the RDL classes</span></span>  
  
1.  <span data-ttu-id="b312d-105">Ouvrez une instance d' [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (ou un navigateur Web équivalent) et accédez à l’URL suivante :</span><span class="sxs-lookup"><span data-stu-id="b312d-105">Open an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] Internet Explorer (or equivalent Web browser) and navigate to the following URL:</span></span>  
  
    ```  
    https://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition/ReportDefinition.xsd  
    ```  
  
2.  <span data-ttu-id="b312d-106">Une fois le schéma RDL ouvert dans le navigateur, accédez au menu **fichier** , puis sélectionnez **Enregistrer sous**.</span><span class="sxs-lookup"><span data-stu-id="b312d-106">Once the RDL schema has been opened in the browser, browse to the **File** menu, and select **Save As**.</span></span>  
  
3.  <span data-ttu-id="b312d-107">Accédez à l'emplacement où vous avez créé votre projet [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] et enregistrez le schéma avec le nom de fichier ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="b312d-107">Browse to the location where you created your [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] project and save the schema with the file name ReportDefinition.xsd.</span></span>  
  
4.  <span data-ttu-id="b312d-108">Une fois le fichier enregistré, ouvrez une instance de l' [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="b312d-108">After the file has been saved, open an instance of the [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] command prompt.</span></span> <span data-ttu-id="b312d-109">Pour ouvrir une instance de l’invite de commandes, cliquez sur le menu Démarrer, pointez sur **tous les programmes**, pointez sur **Microsoft Visual Studio 2010**, sur **Visual Studio Tools** , puis cliquez sur **invite de commandes de Visual Studio (2010)**.</span><span class="sxs-lookup"><span data-stu-id="b312d-109">To open an instance of the command prompt, click the Start menu, point to **All Programs**, point to **Microsoft Visual Studio 2010**, point to **Visual Studio Tools** and click **Visual Studio Command Prompt (2010)**.</span></span>  
  
5.  <span data-ttu-id="b312d-110">Remplacez le chemin d'accès en cours par l'emplacement où vous avez enregistré le fichier ReportDefinition.xsd :</span><span class="sxs-lookup"><span data-stu-id="b312d-110">Change the current path to the location where you saved the ReportDefinition.xsd file:</span></span>  
  
     `CD\<ReportDefinition.xsd Path>`  
  
6.  <span data-ttu-id="b312d-111">Générez le fichier ReportDefinition.cs qui contient les classes du schéma RDL à l'aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b312d-111">Generate the ReportDefinition.cs file that contains the classes for the RDL schema with the following command:</span></span>  
  
     `xsd /c /n:SampleRDLSchema ReportDefinition.xsd`  
  
     <span data-ttu-id="b312d-112">Pour générer un fichier ReportDefinition.vb, utilisez la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="b312d-112">To generate a ReportDefinition.vb file use this command:</span></span>  
  
     `xsd /c /l:VB /n:SampleRDLSchema ReportDefinition.xsd`  
  
7.  <span data-ttu-id="b312d-113">Ajoutez ReportDefinition.xsd à votre projet.</span><span class="sxs-lookup"><span data-stu-id="b312d-113">Add ReportDefinition.xsd your project.</span></span> <span data-ttu-id="b312d-114">Dans le menu **projet** , cliquez sur **Ajouter un élément existant**.</span><span class="sxs-lookup"><span data-stu-id="b312d-114">From the **Project** menu, click **Add Existing Item**.</span></span> <span data-ttu-id="b312d-115">Accédez à l’emplacement du fichier fichier ReportDefinition. xsd, sélectionnez fichier ReportDefinition. xsd, puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="b312d-115">Browse to the location of the ReportDefinition.xsd file, select ReportDefinition.xsd, and click **Add**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b312d-116">Une fois que vous avez ajouté le fichier fichier ReportDefinition. xsd au projet, vous remarquerez dans **Explorateur de solutions** que le fichier ReportDefinition.cs (. vb) n’y figure pas.</span><span class="sxs-lookup"><span data-stu-id="b312d-116">After you have added the ReportDefinition.xsd file to the project you will notice in **Solution Explorer** that the ReportDefinition.cs (.vb) file is not there.</span></span> <span data-ttu-id="b312d-117">Pour afficher le fichier, cliquez sur le bouton Développer/Réduire en regard du fichier ReportDefinition.xsd.</span><span class="sxs-lookup"><span data-stu-id="b312d-117">To display the file, click the expand/collapse button next to the ReportDefinition.xsd file.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="b312d-118">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="b312d-118">Next Lesson</span></span>  
 <span data-ttu-id="b312d-119">Dans la prochaine leçon, vous allez écrire du code pour charger une définition de rapport à partir d'un serveur de rapports à l'aide des classes que vous avez générées depuis le schéma RDL.</span><span class="sxs-lookup"><span data-stu-id="b312d-119">In the next lesson, you will write code to load a report definition from a report server using the classes you generated from the RDL schema.</span></span> <span data-ttu-id="b312d-120">Consultez [la leçon 3 : charger une définition de rapport à partir du serveur de rapports](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="b312d-120">See [Lesson 3: Load a Report Definition from the Report Server](../../2014/tutorials/lesson-3-load-a-report-definition-from-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b312d-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b312d-121">See Also</span></span>  
 <span data-ttu-id="b312d-122">[Mise à jour des rapports à l’aide de classes générées à partir du schéma RDL &#40;didacticiel SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="b312d-122">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="b312d-123">RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b312d-123">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
