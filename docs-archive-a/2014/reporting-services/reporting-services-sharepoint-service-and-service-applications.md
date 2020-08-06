---
title: Reporting Services les services SharePoint et les applications de service | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 501aa9ee-8c13-458c-bf6f-24e00c82681b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5654764f7913002cdae58d3264848250a292c585
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615014"
---
# <a name="reporting-services-sharepoint-service-and-service-applications"></a><span data-ttu-id="881e1-102">Services Reporting Services SharePoint et applications de service</span><span class="sxs-lookup"><span data-stu-id="881e1-102">Reporting Services SharePoint Service and Service Applications</span></span>
  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="881e1-103">SharePoint repose sur l'architecture de service SharePoint et utilise un service SharePoint et l'une des nombreuses applications de service disponibles.</span><span class="sxs-lookup"><span data-stu-id="881e1-103">SharePoint mode is architected on the SharePoint service architecture and utilizes a SharePoint service and one to many service applications.</span></span> <span data-ttu-id="881e1-104">Lorsque vous créez une application de service, le service devient disponible et la base de données d'application de service est générée.</span><span class="sxs-lookup"><span data-stu-id="881e1-104">Creating a service application makes the service available and generates the service application database.</span></span> <span data-ttu-id="881e1-105">Vous pouvez créer plusieurs applications de service Reporting Services mais une application de service est suffisante pour la plupart des scénarios de déploiement.</span><span class="sxs-lookup"><span data-stu-id="881e1-105">You can create multiple Reporting Services service applications but one service application is sufficient for most deployment scenarios.</span></span>  
  
 <span data-ttu-id="881e1-106">Cette rubrique fournit les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="881e1-106">This topic covers the following information:</span></span>  
  
-   [<span data-ttu-id="881e1-107">Création d'une application de service Reporting Services</span><span class="sxs-lookup"><span data-stu-id="881e1-107">Creating a Reporting Services Service Application</span></span>](#bkmk_createapp)  
  
-   [<span data-ttu-id="881e1-108">Modifier les associations de l’application de service avec un groupe de proxy</span><span class="sxs-lookup"><span data-stu-id="881e1-108">Modify the Associations of the Service Application with a proxy group</span></span>](#bkmk_associations)  
  
-   [<span data-ttu-id="881e1-109">Modifier les propriétés d'une application de service</span><span class="sxs-lookup"><span data-stu-id="881e1-109">Edit Service Application Properties</span></span>](#bkmk_editserviceapplication)  
  
-   [<span data-ttu-id="881e1-110">Pour créer une application de service Reporting Services à l'aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="881e1-110">To create a Reporting Services Service Application using PowerShell</span></span>](#bkmk_powershell_create_ssrs_serviceapp)  
  
-   [<span data-ttu-id="881e1-111">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="881e1-111">Related Tasks</span></span>](#bkmk_related)  
  
##  <a name="creating-a-reporting-services-service-application"></a><a name="bkmk_createapp"></a><span data-ttu-id="881e1-112">Création d’une application de service Reporting Services</span><span class="sxs-lookup"><span data-stu-id="881e1-112">Creating a Reporting Services Service Application</span></span>  
 <span data-ttu-id="881e1-113">Vous pouvez utiliser l'Administration centrale de SharePoint ou les scripts PowerShell pour créer des applications de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="881e1-113">You can use SharePoint Central Administration or PowerShell scripts to create the [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] services applications.</span></span> <span data-ttu-id="881e1-114">Pour plus d’informations sur l’utilisation de l’Administration centrale de SharePoint, consultez la section « Créer une application de service Reporting Services » dans [Installer le mode SharePoint de Reporting Services pour SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span><span class="sxs-lookup"><span data-stu-id="881e1-114">For more information on using SharePoint Central Administration, see the "Create a Reporting Services Service Application" section in [Install Reporting Services SharePoint Mode for SharePoint 2010](../../2014/sql-server/install/install-reporting-services-sharepoint-mode-for-sharepoint-2010.md).</span></span> <span data-ttu-id="881e1-115">Consultez la section PowerShell plus loin dans cette rubrique pour obtenir un exemple de script PowerShell permettant de créer des applications de service.</span><span class="sxs-lookup"><span data-stu-id="881e1-115">See the PowerShell section later in this topic for a sample PowerShell script for creating service applications.</span></span>  
  
##  <a name="modify-the-associations-of-the-service-application-with-a-proxy-group"></a><a name="bkmk_associations"></a> <span data-ttu-id="881e1-116">Modifier les associations de l'application de service avec un groupe de proxy</span><span class="sxs-lookup"><span data-stu-id="881e1-116">Modify the Associations of the Service Application with a proxy group</span></span>  
 <span data-ttu-id="881e1-117">La nouvelle page de création d'une application de service contient la section **Association d'application Web**.</span><span class="sxs-lookup"><span data-stu-id="881e1-117">The New page for creating a services application contains the section **Web Application Association**.</span></span> <span data-ttu-id="881e1-118">Cette section vous permet d'associer l'application de service que vous créez.</span><span class="sxs-lookup"><span data-stu-id="881e1-118">The section allows you to associate your service application as you create it.</span></span> <span data-ttu-id="881e1-119">Utilisez la procédure suivante pour modifier l'association et assigner une configuration personnalisée à l'application de service.</span><span class="sxs-lookup"><span data-stu-id="881e1-119">Use the following steps to change the association and assign a customer configuration to the service application.</span></span> <span data-ttu-id="881e1-120">Le même processus général peut également être utilisé pour ajouter le proxy au groupe par défaut plutôt que modifier l'association à un groupe personnalisé de l'application de service.</span><span class="sxs-lookup"><span data-stu-id="881e1-120">The same general process can also be used to add the proxy to the default group rather than changing the association of the service application to a custom group.</span></span>  
  
1.  <span data-ttu-id="881e1-121">Dans l'Administration Centrale de SharePoint, sous Gestion des applications, cliquez sur **Configurer les associations des applications de service**.</span><span class="sxs-lookup"><span data-stu-id="881e1-121">In SharePoint Central Administration, in the Application Management, click **Configure Service Application Associations**.</span></span>  
  
2.  <span data-ttu-id="881e1-122">Dans la page des Associations de l'application de service, modifiez la vue en **Applications de service**.</span><span class="sxs-lookup"><span data-stu-id="881e1-122">On the Service application Associations page, change the view to **Service Applications**.</span></span>  
  
3.  <span data-ttu-id="881e1-123">Recherchez et cliquez sur le nom de votre nouvelle application de service [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="881e1-123">Find and click the name of your new [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Service application.</span></span> <span data-ttu-id="881e1-124">Vous pourriez cliquer également sur la **valeur par défaut** du nom de groupe du proxy de l'application pour ajouter le proxy au groupe par défaut plutôt que compléter les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="881e1-124">You could also click the application proxy group name **default** to add the proxy to default group rather than completing the following steps.</span></span>  
  
4.  <span data-ttu-id="881e1-125">Sélectionnez **Personnalisé** dans la zone de sélection **Modifier le groupe de connexions suivant :**.</span><span class="sxs-lookup"><span data-stu-id="881e1-125">Select **Custom** in the selection box **Edit the following group of connections**.</span></span>  
  
5.  <span data-ttu-id="881e1-126">Activez la zone pour votre proxy et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="881e1-126">Check the box for your proxy and click **Ok**.</span></span>  
  
##  <a name="edit-service-application-properties"></a><a name="bkmk_editserviceapplication"></a><span data-ttu-id="881e1-127">Modifier les propriétés d’une application de service</span><span class="sxs-lookup"><span data-stu-id="881e1-127">Edit Service Application Properties</span></span>  
 <span data-ttu-id="881e1-128">Vous pouvez rouvrir la page de propriétés de l'application de service pour modifier les propriétés.</span><span class="sxs-lookup"><span data-stu-id="881e1-128">You can reopen the property page of the service application to modify the properties.</span></span>  
  
1.  <span data-ttu-id="881e1-129">Dans l’administration centrale de SharePoint, dans le groupe gestion des applications, cliquez sur **gérer les applications de service**.</span><span class="sxs-lookup"><span data-stu-id="881e1-129">In SharePoint Central Administration, in the Application Management group, click **Manage service applications**.</span></span>  
  
2.  <span data-ttu-id="881e1-130">Sélectionnez l'application de service en cliquant sur la colonne de type pour sélectionner la ligne entière.</span><span class="sxs-lookup"><span data-stu-id="881e1-130">Select the service application by clicking the type column to select the entire row.</span></span> <span data-ttu-id="881e1-131">Si vous cliquez sur le nom de l'application, la page des options de gestion du service s'affiche au lieu des propriétés de l'application de service.</span><span class="sxs-lookup"><span data-stu-id="881e1-131">If you click the name of the application it, the Management options page for the service opens instead of opening the properties of the service application.</span></span>  
  
3.  <span data-ttu-id="881e1-132">Dans le ruban Applications de service, cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="881e1-132">In the Service Applications ribbon, click **Properties**.</span></span>  
  
##  <a name="to-create-a-reporting-services-service-application-using-powershell"></a><a name="bkmk_powershell_create_ssrs_serviceapp"></a><span data-ttu-id="881e1-133">Pour créer une application de service Reporting Services à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="881e1-133">To create a Reporting Services Service Application using PowerShell</span></span>  
 <span data-ttu-id="881e1-134">Vous pouvez utiliser PowerShell pour créer l'application de service et le proxy.</span><span class="sxs-lookup"><span data-stu-id="881e1-134">You can use PowerShell to create the Service application and proxy.</span></span> <span data-ttu-id="881e1-135">L'exemple suivant suppose que vous connaissez le pool d'applications qui sera utilisé par l'application de service.</span><span class="sxs-lookup"><span data-stu-id="881e1-135">The sample below assumes that you know what application pool you want to configure the service application to use.</span></span>  
  
1.  <span data-ttu-id="881e1-136">Ajoutez l'objet de pool d'applications de votre nom de pool d'applications à une variable qui est passée dans l'action New.</span><span class="sxs-lookup"><span data-stu-id="881e1-136">Add the application pool object of your application pool name to a variable that is passed into the New action.</span></span>  
  
    ```powershell
    $appPoolName = Get-SPServiceApplicationPool "<application pool name>"  
    ```  
  
2.  <span data-ttu-id="881e1-137">Créez l'application de service en lui attribuant le nom et le nom de pool d'applications que vous fournissez.</span><span class="sxs-lookup"><span data-stu-id="881e1-137">Create the service application with a name and application pool name you provide.</span></span>  
  
    ```powershell
    New-SPRSServiceApplication -Name 'MyServiceApplication' -ApplicationPool $appPoolName -DatabaseName 'MyServiceApplicationDatabase' -DatabaseServer '<Server Name>'  
    ```  
  
3.  <span data-ttu-id="881e1-138">Obtenez le nouvel objet d'application de service et dirigez l'objet dans le canal du nouvel applet de commande de proxy.</span><span class="sxs-lookup"><span data-stu-id="881e1-138">Get the new service application object, and pipe the object into the Pipe the new proxy cmdlet.</span></span>  
  
    ```powershell
    Get-SPRSServiceApplication -name MyServiceApplication | New-SPRSServiceApplicationProxy "MyServiceApplicationProxy"  
    ```  
  
##  <a name="related-tasks"></a><a name="bkmk_related"></a> <span data-ttu-id="881e1-139">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="881e1-139">Related Tasks</span></span>  
  
|<span data-ttu-id="881e1-140">Tâche</span><span class="sxs-lookup"><span data-stu-id="881e1-140">Task</span></span>|<span data-ttu-id="881e1-141">Lien</span><span class="sxs-lookup"><span data-stu-id="881e1-141">Link</span></span>|  
|----------|----------|  
|<span data-ttu-id="881e1-142">Gérez les paramètres de votre application de service.</span><span class="sxs-lookup"><span data-stu-id="881e1-142">Manage the settings of your Service Application.</span></span>|[<span data-ttu-id="881e1-143">Gérer une application de service SharePoint Reporting Services</span><span class="sxs-lookup"><span data-stu-id="881e1-143">Manage a Reporting Services SharePoint Service Application</span></span>](../../2014/reporting-services/manage-a-reporting-services-sharepoint-service-application.md)|  
|<span data-ttu-id="881e1-144">Sauvegardez et restaurez l'application de service et ses composants connexes tels que les clés de chiffrement et le proxy.</span><span class="sxs-lookup"><span data-stu-id="881e1-144">Backup and restore the service application and related components such as encryption keys and proxy.</span></span>|[<span data-ttu-id="881e1-145">Applications de service SharePoint de sauvegarde et de restauration Reporting Services</span><span class="sxs-lookup"><span data-stu-id="881e1-145">Backup and Restore Reporting Services SharePoint Service Applications</span></span>](../../2014/reporting-services/backup-and-restore-reporting-services-sharepoint-service-applications.md)|  
