---
title: 'Procédure : déployer une extension pour le traitement des données sur un serveur de rapports | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: e00dface-70f8-434b-9763-8ebee18737d2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d606096b9f2060d3cf5b9cea1f95a5345e592383
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708975"
---
# <a name="how-to-deploy-a-data-processing-extension-to-a-report-server"></a><span data-ttu-id="d70d7-102">Procédure : déployer une extension pour le traitement des données sur un serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="d70d7-102">How to: Deploy a Data Processing Extension to a Report Server</span></span>
  <span data-ttu-id="d70d7-103">Les serveurs de rapports utilisent les extensions de traitement des données pour extraire, puis traiter les données qui figurent dans les rapports rendus.</span><span class="sxs-lookup"><span data-stu-id="d70d7-103">Report servers use data processing extensions for retrieving and processing data in rendered reports.</span></span> <span data-ttu-id="d70d7-104">Vous devez déployer l'assembly d'extension utilisé pour le traitement des données sur un serveur de rapports, et ce sous la forme d'un assembly privé.</span><span class="sxs-lookup"><span data-stu-id="d70d7-104">You should deploy your data processing extension assembly to a report server as a private assembly.</span></span> <span data-ttu-id="d70d7-105">Vous devez également créer une entrée dans le fichier de configuration du serveur de rapports, à savoir dans le fichier dénommé RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="d70d7-105">You also need to make an entry in the report server configuration file, RSReportServer.config.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d70d7-106">Procédures</span><span class="sxs-lookup"><span data-stu-id="d70d7-106">Procedures</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="d70d7-107">Pour déployer un assembly d'extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="d70d7-107">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="d70d7-108">Copiez l'assembly en question depuis son emplacement vers le répertoire bin du serveur de rapports sur lequel l'extension pour le traitement des données doit être utilisée.</span><span class="sxs-lookup"><span data-stu-id="d70d7-108">Copy your assembly from your staging location to the bin directory of the report server on which you want to use the data processing extension.</span></span> <span data-ttu-id="d70d7-109">L’emplacement par défaut du répertoire bin du serveur de rapports est%ProgramFiles%\Microsoft SQL Server \ MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="d70d7-109">The default location of the report server bin directory is %ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer\bin.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d70d7-110">Cette étape permet d'éviter la mise à niveau vers une instance de SQL Server plus récente.</span><span class="sxs-lookup"><span data-stu-id="d70d7-110">This step will prevent an upgrade to a newer instance of SQL Server.</span></span> <span data-ttu-id="d70d7-111">Pour plus d'informations, consultez [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d70d7-111">For more information, see [Upgrade and Migrate Reporting Services](../../install-windows/upgrade-and-migrate-reporting-services.md).</span></span>  
  
2.  <span data-ttu-id="d70d7-112">Une fois le fichier correspondant à l'assembly copié, ouvrez le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="d70d7-112">After the assembly file is copied, open the RSReportServer.config file.</span></span> <span data-ttu-id="d70d7-113">Ce fichier se trouve dans le répertoire ReportServer.</span><span class="sxs-lookup"><span data-stu-id="d70d7-113">The RSReportServer.config file is located in the ReportServer directory.</span></span> <span data-ttu-id="d70d7-114">Dans le fichier de configuration, créez une entrée correspondant au fichier d'assembly copié.</span><span class="sxs-lookup"><span data-stu-id="d70d7-114">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="d70d7-115">Vous pouvez ouvrir le fichier de configuration dans Visual Studio ou simplement à l’aide d’un éditeur de texte, tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="d70d7-115">You can open the configuration file with Visual Studio or a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="d70d7-116">Localisez l'élément `Data` dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="d70d7-116">Locate the `Data` element in the RSReportServer.config file.</span></span> <span data-ttu-id="d70d7-117">L'entrée correspondant à votre nouvelle extension pour le traitement des données doit être créée à l'emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="d70d7-117">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="d70d7-118">Ajoutez une entrée correspondant à votre nouvelle extension pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="d70d7-118">Add an entry for your data processing extension.</span></span> <span data-ttu-id="d70d7-119">Cette entrée doit comporter un élément `Extension` dont les valeurs `Name` et `Type` doivent être définies. Cette entrée peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="d70d7-119">Your entry should include an `Extension` element with values for `Name` and `Type` and might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, MyExtensionAssembly" />  
    ```  
  
     <span data-ttu-id="d70d7-120">La valeur `Name` doit correspondre au nom unique de l'extension utilisée pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="d70d7-120">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="d70d7-121">La valeur `Type` est une liste séparée par des virgules comportant une entrée dans laquelle doit figurer l'espace de noms complet de la classe qui implémente les interfaces <xref:Microsoft.ReportingServices.Interfaces.IExtension> et <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, suivi du nom de votre assembly (l'extension de fichier .dll ne doit pas figurer dans cette entrée).</span><span class="sxs-lookup"><span data-stu-id="d70d7-121">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="d70d7-122">Par défaut, les extensions utilisées pour le traitement des données sont visibles par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="d70d7-122">By default, data processing extensions are visible.</span></span> <span data-ttu-id="d70d7-123">Pour masquer ces extensions des interfaces utilisateur, telles que le Gestionnaires de rapports, et ne plus les afficher, ajoutez un attribut `Visible` à l'élément `Extension`, puis attribuez à cet élément la valeur `false`.</span><span class="sxs-lookup"><span data-stu-id="d70d7-123">To hide an extension from user interfaces, such as Report Manager, add a `Visible` attribute to the `Extension` element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="d70d7-124">Ajoutez un groupe de codes pour votre assembly personnalisé octroyant l'autorisation `FullTrust` à votre extension.</span><span class="sxs-lookup"><span data-stu-id="d70d7-124">Add a code group for your custom assembly that grants `FullTrust` permission for your extension.</span></span> <span data-ttu-id="d70d7-125">Pour ce faire, ajoutez le groupe de codes au fichier rssrvpolicy.config situé par défaut dans%ProgramFiles%\Microsoft SQL Server \\<MSRS10_50. \<*Instance Name*> \Reporting Services\ReportServer.</span><span class="sxs-lookup"><span data-stu-id="d70d7-125">You do this by adding the code group to the rssrvpolicy.config file located by default in %ProgramFiles%\Microsoft SQL Server\\<MSRS10_50.\<*Instance Name*>\Reporting Services\ReportServer.</span></span> <span data-ttu-id="d70d7-126">Ce groupe de codes peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="d70d7-126">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.<Instance Name>\Reporting Services\ReportServer\bin\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="d70d7-127">L'appartenance URL n'est qu'une des nombreuses conditions d'appartenance que vous pouvez sélectionner pour l'extension permettant le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="d70d7-127">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="d70d7-128">Pour plus d’informations sur la sécurité d’accès du code dans [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], consultez [Développement sécurisé &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="d70d7-128">For more information about code access security in [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span></span>  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="d70d7-129">Vérification du déploiement</span><span class="sxs-lookup"><span data-stu-id="d70d7-129">Verifying the Deployment</span></span>  
 <span data-ttu-id="d70d7-130">Si vous le souhaitez, vous pouvez vous assurer que votre extension pour le traitement des données a été correctement déployée sur le serveur de rapports sélectionné en utilisant la méthode de service Web <xref:ReportService2010.ReportingService2010.ListExtensions%2A>.</span><span class="sxs-lookup"><span data-stu-id="d70d7-130">You can verify whether your data processing extension was deployed successfully to the report server by using the Web service <xref:ReportService2010.ReportingService2010.ListExtensions%2A> method.</span></span> <span data-ttu-id="d70d7-131">À cette même fin, vous pouvez également ouvrir le Gestionnaire de rapports, puis vérifier que votre extension est effectivement répertoriée dans la liste de sources de données qu'il contient.</span><span class="sxs-lookup"><span data-stu-id="d70d7-131">You can also open Report Manager and verify that your extension is included in the list of available data sources.</span></span> <span data-ttu-id="d70d7-132">Pour plus d’informations sur le Gestionnaire de rapports et les sources de données, consultez [Créer, modifier, puis supprimer des sources de données partagées &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d70d7-132">For more information about Report Manager and data sources, see [Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](../../report-data/create-modify-and-delete-shared-data-sources-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70d7-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d70d7-133">See Also</span></span>  
 <span data-ttu-id="d70d7-134">[Déploiement d’une extension pour le traitement des données](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="d70d7-134">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="d70d7-135">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d70d7-135">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="d70d7-136">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="d70d7-136">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="d70d7-137">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d70d7-137">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
