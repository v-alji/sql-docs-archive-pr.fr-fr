---
title: 'Étape 2 : Vérification du bundle de déploiement | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f452a87154175ac05a050761d8f12b6bfe61cd8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601565"
---
# <a name="step-2-verifying-the-deployment-bundle"></a><span data-ttu-id="ff1fd-102">Étape 2 : Vérification de l’application de déploiement</span><span class="sxs-lookup"><span data-stu-id="ff1fd-102">Step 2: Verifying the Deployment Bundle</span></span>
  <span data-ttu-id="ff1fd-103">Dans la leçon 1, vous avez créé le projet Didacticiel de déploiement et ajouté au projet les packages et les fichiers annexes ; dans la tâche précédente, vous avez créé un utilitaire de déploiement pour le projet.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-103">In lesson 1, you created the Deployment Tutorial project and added packages and ancillary files to the project; in the previous task you built a deployment utility for the project.</span></span>  
  
 <span data-ttu-id="ff1fd-104">Dans cette tâche, vous allez vérifier le contenu de l'application de déploiement.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-104">In this task, you will verify the contents of the deployment bundle.</span></span> <span data-ttu-id="ff1fd-105">Elle correspond au dossier que vous allez copier sur l'ordinateur de destination et qui servira à installer des packages.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-105">The deployment bundle is the folder that you will copy to the destination computer and use to install packages.</span></span> <span data-ttu-id="ff1fd-106">Si vous avez utilisé la valeur par défaut, bin\Deployment, comme emplacement de l’utilitaire de déploiement, l’application de déploiement correspond au dossier Bin\Deployment dans le dossier du tutoriel de déploiement du projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff1fd-106">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a><span data-ttu-id="ff1fd-107">Pour vérifier le contenu de l'application de déploiement</span><span class="sxs-lookup"><span data-stu-id="ff1fd-107">To verify the content of deployment bundle</span></span>  
  
1.  <span data-ttu-id="ff1fd-108">Localisez le dossier bin\Deployment sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-108">Locate the bin\Deployment folder on your computer.</span></span>  
  
2.  <span data-ttu-id="ff1fd-109">Vérifiez que les fichiers suivants sont présents :</span><span class="sxs-lookup"><span data-stu-id="ff1fd-109">Verify that the following files are present:</span></span>  
  
    -   <span data-ttu-id="ff1fd-110">DataTransfer.dtsx</span><span class="sxs-lookup"><span data-stu-id="ff1fd-110">DataTransfer.dtsx</span></span>  
  
    -   <span data-ttu-id="ff1fd-111">datatransferconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="ff1fd-111">datatransferconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="ff1fd-112">Deployment Tutorial.SSISDeploymentManifest</span><span class="sxs-lookup"><span data-stu-id="ff1fd-112">Deployment Tutorial.SSISDeploymentManifest</span></span>  
  
    -   <span data-ttu-id="ff1fd-113">LoadXMLData.dtsx</span><span class="sxs-lookup"><span data-stu-id="ff1fd-113">LoadXMLData.dtsx</span></span>  
  
    -   <span data-ttu-id="ff1fd-114">loadxmldataconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="ff1fd-114">loadxmldataconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="ff1fd-115">NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="ff1fd-115">NewCustomers.txt</span></span>  
  
    -   <span data-ttu-id="ff1fd-116">orders.xml</span><span class="sxs-lookup"><span data-stu-id="ff1fd-116">orders.xml</span></span>  
  
    -   <span data-ttu-id="ff1fd-117">orders.xsd</span><span class="sxs-lookup"><span data-stu-id="ff1fd-117">orders.xsd</span></span>  
  
    -   <span data-ttu-id="ff1fd-118">Lisezmoi.txt</span><span class="sxs-lookup"><span data-stu-id="ff1fd-118">Readme.txt</span></span>  
  
3.  <span data-ttu-id="ff1fd-119">Cliquez avec le bouton droit sur Deployment Tutorial.SSISDeploymentManifest, pointez sur **Ouvrir avec**, puis cliquez sur **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-119">Right-click Deployment Tutorial.SSISDeploymentManifest, point **to Open With**, and then click **Internet Explorer**.</span></span> <span data-ttu-id="ff1fd-120">Vous pouvez aussi faire appel à un éditeur de texte tel que le Bloc-notes pour ouvrir le fichier.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-120">You can also open the file in a text editor such as Notepad.</span></span> <span data-ttu-id="ff1fd-121">Le code XML du fichier doit être le suivant :</span><span class="sxs-lookup"><span data-stu-id="ff1fd-121">The XML code of the file should be the following:</span></span>  
  
     `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  <span data-ttu-id="ff1fd-122">Vérifiez que la valeur de l' `AllowConfigurationChanges` attribut est **true** et que le code XML comprend un `Package` élément pour chacun des deux packages, un `MiscellaneousFile` élément pour chacun des quatre fichiers non-package et un `ConfigurationFile` élément pour chacun des deux fichiers de configuration XML.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-122">Verify that the value of the `AllowConfigurationChanges` attribute is **true** and the XML includes a `Package` element for each of the two packages, a `MiscellaneousFile` element for each of the four non-package files, and a `ConfigurationFile` element for each of the two XML configuration files.</span></span>  
  
5.  <span data-ttu-id="ff1fd-123">Quittez Internet Explorer ou l'éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-123">Exit Internet Explorer or the text editor.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="ff1fd-124">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="ff1fd-124">Next Lesson</span></span>  
 [<span data-ttu-id="ff1fd-125">Leçon 3 : Installation des packages</span><span class="sxs-lookup"><span data-stu-id="ff1fd-125">Lesson 3: Installing Packages</span></span>](../integration-services/lesson-3-install-ssis-package.md)  
  
<span data-ttu-id="ff1fd-126">![Icône de Integration Services (petite)](media/dts-16.gif "Icône Integration Services (petite)")  **restez à jour avec Integration Services**</span><span class="sxs-lookup"><span data-stu-id="ff1fd-126">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="ff1fd-127">Pour obtenir les derniers téléchargements, articles, exemples et vidéos de Microsoft, ainsi que des solutions sélectionnées par la communauté, visitez la page [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur MSDN :</span><span class="sxs-lookup"><span data-stu-id="ff1fd-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="ff1fd-128">Visiter la page Integration Services sur MSDN</span><span class="sxs-lookup"><span data-stu-id="ff1fd-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="ff1fd-129">Pour recevoir une notification automatique de ces mises à jour, abonnez-vous aux flux RSS disponibles sur la page.</span><span class="sxs-lookup"><span data-stu-id="ff1fd-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
