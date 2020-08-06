---
title: Créer des classes proxy de service web Master Data Manager | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
ms.assetid: 8bdab026-a0c0-41f3-9d36-f3919c23247f
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c4f25d749f829357f6541f14073e654bade27215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615178"
---
# <a name="create-master-data-manager-web-service-proxy-classes"></a><span data-ttu-id="3c262-102">Créer des classes proxy de service Web Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="3c262-102">Create Master Data Manager Web Service Proxy Classes</span></span>
  <span data-ttu-id="3c262-103">Le service Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] vous permet de programmer les fonctionnalités de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] à partir de n'importe quel ordinateur pouvant accéder à votre site Web [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3c262-103">The [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web service lets you make programmatic use of the features of [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] from any computer that can access your [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web site.</span></span> <span data-ttu-id="3c262-104">Avant de commencer à écrire du code pour accéder au service Web, vous devez générer des classes proxy.</span><span class="sxs-lookup"><span data-stu-id="3c262-104">Before you can start writing code to access the web service, you must generate proxy classes.</span></span> <span data-ttu-id="3c262-105">La classe proxy principale que vous utilisez pour effectuer des opérations de service Web est la classe <xref:Microsoft.MasterDataServices.ServiceClient>, qui implémente l'interface <xref:Microsoft.MasterDataServices.IService>.</span><span class="sxs-lookup"><span data-stu-id="3c262-105">The main proxy class you use to perform web service operations is the <xref:Microsoft.MasterDataServices.ServiceClient> class, which implements the <xref:Microsoft.MasterDataServices.IService> interface.</span></span>  
  
## <a name="enable-web-service-metadata-publishing"></a><span data-ttu-id="3c262-106">Activer la publication de métadonnées de service Web</span><span class="sxs-lookup"><span data-stu-id="3c262-106">Enable Web Service Metadata Publishing</span></span>  
 <span data-ttu-id="3c262-107">Avant de pouvoir générer des classes proxy, vous devez activer la publication de métadonnées de service Web.</span><span class="sxs-lookup"><span data-stu-id="3c262-107">Before you can generate proxy classes, you must enable web service metadata publishing.</span></span> <span data-ttu-id="3c262-108">Pour cela, effectuez les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="3c262-108">Follow these steps to do this:</span></span>  
  
1.  <span data-ttu-id="3c262-109">Ouvrez le fichier Web.config [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="3c262-109">Open the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] Web.config file in a text editor.</span></span> <span data-ttu-id="3c262-110">Ce fichier se trouve dans le dossier WebApplication du chemin d'installation de [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c262-110">This file is in the WebApplication folder of the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)] installation path.</span></span>  
  
2.  <span data-ttu-id="3c262-111">Recherchez la `mdsWsHttpBehavior` section sous **\<serviceBehaviors>** .</span><span class="sxs-lookup"><span data-stu-id="3c262-111">Find the `mdsWsHttpBehavior` section under **\<serviceBehaviors>**.</span></span> <span data-ttu-id="3c262-112">Pour l' **\<serviceMetadata>** élément, affectez à la valeur `httpGetEnabled` `true` .</span><span class="sxs-lookup"><span data-stu-id="3c262-112">For the **\<serviceMetadata>** element, set `httpGetEnabled` to `true`.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="3c262-113">Si vous souhaitez activer des services Web via SSL (Secure Sockets Layer), définissez `httpsGetEnabled` sur `true` dans la section `mdsWsHttpBehavior` du fichier web.config.</span><span class="sxs-lookup"><span data-stu-id="3c262-113">If you want to enable Web services over Secure Sockets Layer (SSL), set `httpsGetEnabled` to `true` in the `mdsWsHttpBehavior` section of the web.config file.</span></span> <span data-ttu-id="3c262-114">Vous devez également modifier `mdsWsHTTPBinding` afin qu'il soit configuré pour SSL et mettre en commentaire la section non-SSL.</span><span class="sxs-lookup"><span data-stu-id="3c262-114">You also need to change `mdsWsHTTPBinding` so that it is configured for SSL, as well, and comment out the non-SSL section.</span></span>  
  
3.  <span data-ttu-id="3c262-115">Enregistrez les modifications apportées au fichier.</span><span class="sxs-lookup"><span data-stu-id="3c262-115">Save changes to the file.</span></span>  
  
4.  <span data-ttu-id="3c262-116">Testez les métadonnées de la publication en naviguant jusqu’à l’URL du service, par exemple : http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="3c262-116">Test metadata publishing by browsing to the service URL, for example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="3c262-117">Si la publication de métadonnées est activée, une page s'affiche, commençant par :</span><span class="sxs-lookup"><span data-stu-id="3c262-117">If metadata publishing is enabled, a page is displayed that begins with</span></span>   
    <span data-ttu-id="3c262-118">« Vous avez créé un service. »</span><span class="sxs-lookup"><span data-stu-id="3c262-118">"You have created a service."</span></span>  
  
## <a name="creating-proxy-classes-by-using-visual-studio"></a><span data-ttu-id="3c262-119">Création de classes proxy à l'aide de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3c262-119">Creating Proxy Classes by Using Visual Studio</span></span>  
 <span data-ttu-id="3c262-120">Si vous avez installé Visual Studio 2010, la méthode la plus simple de générer des classes proxy est d’ajouter une **Référence de service** à votre projet.</span><span class="sxs-lookup"><span data-stu-id="3c262-120">If you have Visual Studio 2010 installed, the simplest way to generate proxy classes is to add a **Service Reference** to your project.</span></span> <span data-ttu-id="3c262-121">L'adresse de la référence de service est l'URL de l'application Web de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)], suivie de /service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="3c262-121">The address of the service reference is the URL of the [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] web application, appended with /service/service.svc.</span></span> <span data-ttu-id="3c262-122">Par exemple : http://yourserver/MDS/service/service.svc.</span><span class="sxs-lookup"><span data-stu-id="3c262-122">For example: http://yourserver/MDS/service/service.svc.</span></span> <span data-ttu-id="3c262-123">Pour plus d’informations, consultez [Guide pratique pour ajouter, mettre à jour ou supprimer une référence de service](https://go.microsoft.com/fwlink/?LinkId=221167).</span><span class="sxs-lookup"><span data-stu-id="3c262-123">For more information, see [How to: Add, Update, or Remove a Service Reference](https://go.microsoft.com/fwlink/?LinkId=221167).</span></span>  
  
## <a name="creating-proxy-classes-by-using-svcutilexe"></a><span data-ttu-id="3c262-124">Création de classes proxy à l'aide de Svcutil.exe</span><span class="sxs-lookup"><span data-stu-id="3c262-124">Creating Proxy Classes by Using Svcutil.exe</span></span>  
 <span data-ttu-id="3c262-125">Vous devez disposer de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ou de l' [!INCLUDE[msCoName](../../includes/msconame-md.md)] SDK Windows installé pour que Svcutil.exe soit installé sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3c262-125">You must have either [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows SDK installed in order to have Svcutil.exe on your computer.</span></span> <span data-ttu-id="3c262-126">Si vous utilisez [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], vous devez utiliser l'invite de commandes [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] pour exécuter la commande.</span><span class="sxs-lookup"><span data-stu-id="3c262-126">If you use [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], you must use the [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] command prompt to run the command.</span></span> <span data-ttu-id="3c262-127">Pour plus d’informations, consultez [Outil Service Model Metadata Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) et [Génération d’un client WCF à partir de métadonnées de service](https://go.microsoft.com/fwlink/?LinkId=164821).</span><span class="sxs-lookup"><span data-stu-id="3c262-127">For more information, see [ServiceModel Metadata Utility Tool (Svcutil.exe)](https://go.microsoft.com/fwlink/?LinkId=165027) and [Generating a WCF Client from Service Metadata](https://go.microsoft.com/fwlink/?LinkId=164821).</span></span>  
  
 <span data-ttu-id="3c262-128">Pour créer un jeu de classes proxy C# à l'aide de Svcutil.exe, utilisez une commande telle que :</span><span class="sxs-lookup"><span data-stu-id="3c262-128">To create a set of C# proxy classes by using Svcutil.exe, use a command such as the following:</span></span>  
  
```  
svcutil.exe http://<server_name:port>/<virtual_path>/Service/Service.svc   
/out:<proxy_name>.cs /messageContract /tcv:Version35   
/noconfig /ct:System.Collections.ObjectModel.Collection`1   
/namespace:*,Microsoft.MasterDataServices  
```  
  
 <span data-ttu-id="3c262-129">Où :</span><span class="sxs-lookup"><span data-stu-id="3c262-129">Where:</span></span>  
  
-   <span data-ttu-id="3c262-130">*servername*:*port* désignent le nom d’ordinateur et le numéro de port de l’ordinateur qui héberge [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c262-130">*servername*:*port* are the computer name and port number of the computer that hosts [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="3c262-131">*virtual_path* désigne le chemin virtuel de [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] dans IIS (Internet Information Services).</span><span class="sxs-lookup"><span data-stu-id="3c262-131">*virtual_path* is the virtual path of [!INCLUDE[ssMDSmdm](../../includes/ssmdsmdm-md.md)] in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="3c262-132">*proxy_name* désigne le nom du fichier proxy généré.</span><span class="sxs-lookup"><span data-stu-id="3c262-132">*proxy_name* is the name for the generated proxy file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c262-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c262-133">See Also</span></span>  
 [<span data-ttu-id="3c262-134">Opérations de service web par catégorie &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="3c262-134">Categorized Web Service Operations &#40;Master Data Services&#41;</span></span>](categorized-web-service-operations-master-data-services.md)  
  
  
