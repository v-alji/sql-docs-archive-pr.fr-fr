---
title: 'Procédure : déployer une extension pour le traitement des données sur le Concepteur de rapports | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], deploying
- assemblies [Reporting Services], data processing extension deployments
ms.assetid: 3614e601-004e-4a16-8388-836ffd67e9dd
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 56bd56e9d8eeeeff1781f22b42cf0eb1ce706fa4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708959"
---
# <a name="how-to-deploy-a-data-processing-extension-to-report-designer"></a><span data-ttu-id="110a8-102">Procédure : déployer une extension pour le traitement des données sur le Concepteur de rapports</span><span class="sxs-lookup"><span data-stu-id="110a8-102">How to: Deploy a Data Processing Extension to Report Designer</span></span>
  <span data-ttu-id="110a8-103">Le Concepteur de rapports utilise des extensions pour le traitement des données afin de récupérer et traiter des données pendant que vous concevez des rapports.</span><span class="sxs-lookup"><span data-stu-id="110a8-103">Report Designer uses data processing extensions for retrieving and processing data while you are designing reports.</span></span> <span data-ttu-id="110a8-104">Vous devez déployer votre assembly d'extension pour le traitement des données sur le Concepteur de rapports en tant qu'assembly privé.</span><span class="sxs-lookup"><span data-stu-id="110a8-104">You should deploy your data processing extension assembly to Report Designer as a private assembly.</span></span> <span data-ttu-id="110a8-105">Vous devez également créer une entrée dans le fichier de configuration du Concepteur de rapports (RSReportDesigner.config.)</span><span class="sxs-lookup"><span data-stu-id="110a8-105">You also need to make an entry in the Report Designer configuration file, RSReportDesigner.config.</span></span>  
  
#### <a name="to-deploy-a-data-processing-extension-assembly"></a><span data-ttu-id="110a8-106">Pour déployer un assembly d'extension pour le traitement des données</span><span class="sxs-lookup"><span data-stu-id="110a8-106">To deploy a data processing extension assembly</span></span>  
  
1.  <span data-ttu-id="110a8-107">Copiez votre assembly depuis son emplacement intermédiaire vers le répertoire du Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="110a8-107">Copy your assembly from your staging location to the Report Designer directory.</span></span> <span data-ttu-id="110a8-108">L'emplacement par défaut du répertoire du Concepteur de rapports est le suivant : C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="110a8-108">The default location of the Report Designer directory is C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span>  
  
2.  <span data-ttu-id="110a8-109">Une fois le fichier d'assembly copié, ouvrez le fichier RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="110a8-109">After the assembly file is copied, open the RSReportDesigner.config file.</span></span> <span data-ttu-id="110a8-110">Le fichier RSReportDesigner.config se trouve également dans le répertoire du Concepteur de rapports.</span><span class="sxs-lookup"><span data-stu-id="110a8-110">The RSReportDesigner.config file is also located in the Report Designer directory.</span></span> <span data-ttu-id="110a8-111">Dans le fichier de configuration, créez une entrée correspondant au fichier d'assembly copié.</span><span class="sxs-lookup"><span data-stu-id="110a8-111">You need to make an entry in the configuration file for your data processing extension assembly file.</span></span> <span data-ttu-id="110a8-112">Vous pouvez ouvrir le fichier de configuration à l’aide de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] ou d’un simple éditeur de texte, tel que le Bloc-notes.</span><span class="sxs-lookup"><span data-stu-id="110a8-112">You can open the configuration file with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or with a simple text editor, such as Notepad.</span></span>  
  
3.  <span data-ttu-id="110a8-113">Localisez l’élément **Data** dans le fichier RSReportDesigner.config.</span><span class="sxs-lookup"><span data-stu-id="110a8-113">Locate the **Data** element in the RSReportDesigner.config file.</span></span> <span data-ttu-id="110a8-114">L'entrée correspondant à votre nouvelle extension pour le traitement des données doit être créée à l'emplacement suivant :</span><span class="sxs-lookup"><span data-stu-id="110a8-114">An entry for your newly created data processing extension should be made in the following location:</span></span>  
  
    ```  
    <Extensions>  
       <Data>  
          <Your extension configuration information goes here>  
       </Data>  
    </Extensions>  
    ```  
  
4.  <span data-ttu-id="110a8-115">Ajoutez une entrée pour votre extension pour le traitement des données qui comprend un élément **extension** avec des valeurs pour les `Name` `Type` attributs, et `Visible` .</span><span class="sxs-lookup"><span data-stu-id="110a8-115">Add an entry for your data processing extension which includes an **Extension** element with values for the `Name`, `Type`, and `Visible` attributes.</span></span> <span data-ttu-id="110a8-116">Votre entrée peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="110a8-116">Your entry might look like the following:</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="CompanyName.ExtensionName.MyConnectionClass, AssemblyName" />  
    ```  
  
     <span data-ttu-id="110a8-117">La valeur `Name` doit correspondre au nom unique de l'extension utilisée pour le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="110a8-117">The value for `Name` is the unique name of the data processing extension.</span></span> <span data-ttu-id="110a8-118">La valeur `Type` est une liste séparée par des virgules comportant une entrée dans laquelle doit figurer l'espace de noms complet de la classe qui implémente les interfaces <xref:Microsoft.ReportingServices.Interfaces.IExtension> et <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection>, suivi du nom de votre assembly (l'extension de fichier .dll ne doit pas figurer dans cette entrée).</span><span class="sxs-lookup"><span data-stu-id="110a8-118">The value for `Type` is a comma-separated list that includes an entry for the fully qualified namespace of your class that implements the <xref:Microsoft.ReportingServices.Interfaces.IExtension> and <xref:Microsoft.ReportingServices.DataProcessing.IDbConnection> interfaces, followed by the name of your assembly (not including the .dll file extension).</span></span> <span data-ttu-id="110a8-119">Par défaut, les extensions utilisées pour le traitement des données sont visibles par les utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="110a8-119">By default, data processing extensions are visible.</span></span> <span data-ttu-id="110a8-120">Pour masquer une extension à partir des interfaces utilisateur, telles que Concepteur de rapports, ajoutez un `Visible` attribut à l’élément d' **extension** et affectez-lui la valeur `false` .</span><span class="sxs-lookup"><span data-stu-id="110a8-120">To hide an extension from user interfaces, such as Report Designer, add a `Visible` attribute to the **Extension** element, and set it to `false`.</span></span>  
  
5.  <span data-ttu-id="110a8-121">Enfin, vous devez définir un groupe de codes pour votre assembly personnalisé octroyant l’autorisation **FullTrust** à votre extension.</span><span class="sxs-lookup"><span data-stu-id="110a8-121">Finally, add a code group for your custom assembly that grants **FullTrust** permission for your extension.</span></span> <span data-ttu-id="110a8-122">Pour cela, ajoutez le groupe de codes au fichier rspreviewpolicy.config qui se trouve par défaut à l'emplacement C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="110a8-122">You do this by adding the code group to the rspreviewpolicy.config file located by default in C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span></span> <span data-ttu-id="110a8-123">Ce groupe de codes peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="110a8-123">Your code group might look like the following:</span></span>  
  
    ```  
    <CodeGroup class="UnionCodeGroup"  
       version="1"  
       PermissionSetName="FullTrust"  
       Name="MyExtensionCodeGroup"  
       Description="Code group for my data processing extension">  
          <IMembershipCondition class="UrlMembershipCondition"  
             version="1"  
             Url="C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies\MyExtensionAssembly.dll"  
           />  
    </CodeGroup>  
    ```  
  
 <span data-ttu-id="110a8-124">L'appartenance URL n'est qu'une des nombreuses conditions d'appartenance que vous pouvez sélectionner pour l'extension permettant le traitement des données.</span><span class="sxs-lookup"><span data-stu-id="110a8-124">URL membership is only one of many membership conditions you might choose for your data processing extension.</span></span> <span data-ttu-id="110a8-125">Pour plus d’informations sur la sécurité d’accès du code dans [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], consultez [Développement sécurisé &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="110a8-125">For more information about code access security in [!INCLUDE[ssRSversion2005](../../../includes/ssrsversion2005-md.md)], see [Secure Development &#40;Reporting Services&#41;](../secure-development/secure-development-reporting-services.md)</span></span>  
  
## <a name="generic-query-designer"></a><span data-ttu-id="110a8-126">Concepteur de requêtes générique</span><span class="sxs-lookup"><span data-stu-id="110a8-126">Generic Query Designer</span></span>  
 <span data-ttu-id="110a8-127">Le Concepteur de rapports fournit un concepteur de requêtes générique que vous pouvez utiliser avec des extensions pour le traitement des données personnalisées.</span><span class="sxs-lookup"><span data-stu-id="110a8-127">Report Designer provides a generic query designer that you can use with custom data processing extensions.</span></span> <span data-ttu-id="110a8-128">Ce concepteur comprend deux volets : un volet de requête et un volet de résultats.</span><span class="sxs-lookup"><span data-stu-id="110a8-128">This designer consists of two panes: a query pane and a results pane.</span></span> <span data-ttu-id="110a8-129">Vous pouvez utiliser le concepteur générique pour écrire des requêtes qui ne sont pas prises en charge par l'interface graphique.</span><span class="sxs-lookup"><span data-stu-id="110a8-129">You can use the generic designer to write queries that are not supported by the graphical interface.</span></span> <span data-ttu-id="110a8-130">Contrairement au concepteur de requêtes graphique, le concepteur de requêtes générique ne restructure pas les requêtes et n'en vérifie pas la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="110a8-130">Unlike the graphical query designer, the generic query designer does not check query syntax or restructure the query.</span></span>  
  
#### <a name="to-enable-the-generic-query-designer-for-a-custom-extension"></a><span data-ttu-id="110a8-131">Pour activer le concepteur de requêtes générique pour une extension personnalisée</span><span class="sxs-lookup"><span data-stu-id="110a8-131">To enable the generic query designer for a custom extension</span></span>  
  
-   <span data-ttu-id="110a8-132">Ajoutez l’entrée suivante au fichier RSReportDesigner.config sous l’élément **Concepteur** , en remplaçant l' `Name` attribut par le nom que vous avez fourni dans les entrées précédentes.</span><span class="sxs-lookup"><span data-stu-id="110a8-132">Add the following entry to the RSReportDesigner.config file under the **Designer** element, replacing the `Name` attribute with the name that you provided in previous entries.</span></span>  
  
    ```  
    <Extension Name="ExtensionName" Type="Microsoft.ReportingServices.QueryDesigners.GenericQueryDesigner,Microsoft.ReportingServices.QueryDesigners"/>  
    ```  
  
## <a name="verifying-the-deployment"></a><span data-ttu-id="110a8-133">Vérification du déploiement</span><span class="sxs-lookup"><span data-stu-id="110a8-133">Verifying the Deployment</span></span>  
 <span data-ttu-id="110a8-134">Avant de vérifier le déploiement, vous devez fermer toutes les instances de [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] sur votre ordinateur local.</span><span class="sxs-lookup"><span data-stu-id="110a8-134">Before you can verify deployment, you must close all instances of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] on your local computer.</span></span> <span data-ttu-id="110a8-135">Une fois que vous avez clôturé toutes les sessions en cours, vous pouvez vérifier si votre extension pour le traitement des données a été déployée correctement dans le Concepteur de rapports en créant un nouveau projet de rapport dans [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="110a8-135">After you have ended all current sessions, you can verify whether your data processing extension was deployed successfully to Report Designer by creating a new report project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="110a8-136">Votre extension doit être incluse dans la liste des types de source de données disponibles lorsque vous créez un nouveau jeu de données pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="110a8-136">Your extension should be included in the list of available data source types when you create a new data set for your report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="110a8-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="110a8-137">See Also</span></span>  
 <span data-ttu-id="110a8-138">[Déploiement d’une extension pour le traitement des données](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="110a8-138">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="110a8-139">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="110a8-139">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="110a8-140">[Implémentation d’une extension pour le traitement des données](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="110a8-140">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="110a8-141">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="110a8-141">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
