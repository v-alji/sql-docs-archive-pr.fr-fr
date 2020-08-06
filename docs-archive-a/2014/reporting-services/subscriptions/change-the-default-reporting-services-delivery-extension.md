---
title: Modifier l’extension de remise par défaut de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Report Manager [Reporting Services], default delivery extension
ms.assetid: 5f6fee72-01bf-4f6c-85d2-7863c46c136b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cc1b3af2a4fe3038b761d0b48030062da06d354e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703752"
---
# <a name="change-the-default-reporting-services-delivery-extension"></a><span data-ttu-id="2c43f-102">Modification de l’extension de remise par défaut de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2c43f-102">Change the Default Reporting Services Delivery Extension</span></span>
  <span data-ttu-id="2c43f-103">Vous pouvez modifier les paramètres de configuration [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pour modifier l’extension de remise par défaut qui s’affiche dans la liste **Remis par** d’une page de définition d’abonnement.</span><span class="sxs-lookup"><span data-stu-id="2c43f-103">You can modify [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] configuration settings to change the default delivery extension that appears in the **Delivered by** list of a subscription definition page.</span></span> <span data-ttu-id="2c43f-104">Par exemple, vous pouvez modifier la configuration afin que, lorsque les utilisateurs créent un nouvel abonnement, la remise par partage de fichiers soit activée par défaut, plutôt que la remise par messagerie électronique.</span><span class="sxs-lookup"><span data-stu-id="2c43f-104">For example you can modify the configuration so that when users create a new subscription, file share delivery is selected by default instead of e-mail delivery.</span></span> <span data-ttu-id="2c43f-105">Vous pouvez également modifier l'ordre selon lequel les extensions de remise sont répertoriées dans l'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="2c43f-105">You can also change the order the delivery extensions are listed in the user interface.</span></span>

 <span data-ttu-id="2c43f-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en mode natif | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c43f-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode | [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>

 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2c43f-107">comprend les extensions de remise par messagerie électronique et de remise par partage de fichiers Windows.</span><span class="sxs-lookup"><span data-stu-id="2c43f-107">includes E-mail and Windows File Share delivery are extensions.</span></span> <span data-ttu-id="2c43f-108">Il se peut que votre serveur de rapports possède des extensions de remise supplémentaires si vous avez déployé des extensions personnalisées ou tierces pour la prise en charge d'une remise personnalisée.</span><span class="sxs-lookup"><span data-stu-id="2c43f-108">Your report server might have additional delivery extensions if you have deployed custom or third-party extensions to support custom delivery.</span></span> <span data-ttu-id="2c43f-109">La disponibilité d'une extension de remise varie selon qu'elle est déployée sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2c43f-109">The availability of a delivery extension depends on whether it is deployed on a report server.</span></span>

## <a name="default-native-mode-report-server-configuration"></a><span data-ttu-id="2c43f-110">Configuration de serveur de rapports en mode natif par défaut</span><span class="sxs-lookup"><span data-stu-id="2c43f-110">Default Native mode report server configuration</span></span>
 <span data-ttu-id="2c43f-111">L’ordre d’une extension de remise dans la liste **Remis par** du Gestionnaire de rapports dépend de l’ordre des entrées d’extension de remise dans le fichier **RSReportServer.config** .</span><span class="sxs-lookup"><span data-stu-id="2c43f-111">The order of a delivery extension appears in Report Manager in the **Delivered by** list is based on the order of the delivery extension entries in the **RSReportServer.config** file.</span></span> <span data-ttu-id="2c43f-112">Par exemple, l'image suivante présente la messagerie au début de la liste et elle est sélectionnée par défaut.</span><span class="sxs-lookup"><span data-stu-id="2c43f-112">For example the following image shows e-mail first in the list and it is selected by default.</span></span>

 <span data-ttu-id="2c43f-113">![liste par défaut des extensions de remise](../media/ssrs-default-delivery.png "liste par défaut des extensions de remise")</span><span class="sxs-lookup"><span data-stu-id="2c43f-113">![default list of delivery extensions](../media/ssrs-default-delivery.png "default list of delivery extensions")</span></span>

 <span data-ttu-id="2c43f-114">Voici la section par défaut de **RSReportServer.config** qui contrôle l’extension de remise par défaut et l’ordre d’apparition dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2c43f-114">The following is the default section of **RSReportServer.config** that controls the default delivery extension and the order they are displayed in Report Manager.</span></span> <span data-ttu-id="2c43f-115">Notez que la messagerie électronique apparaît en premier dans le fichier, elle est définie comme valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="2c43f-115">Note that email appears first in the file and it is set as the default.</span></span>

```xml
<DeliveryUI>
     <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
          <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
               <Configuration>
               <RSEmailDPConfiguration>
                    <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
               </RSEmailDPConfiguration>
               </Configuration>
     </Extension>
     <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider"/>
</DeliveryUI>
```

#### <a name="configure-file-share-delivery-as-the-default-delivery-extension-in-report-manager"></a><span data-ttu-id="2c43f-116">Configuration de la remise par partage de fichiers comme extension de remise par défaut dans le Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="2c43f-116">Configure File Share Delivery as the default delivery extension in Report Manager</span></span>

1.  <span data-ttu-id="2c43f-117">Les étapes de cette procédure modifient la configuration afin que la remise par partage de fichiers soit répertoriée comme la première option dans l'interface utilisateur et soit la sélection par défaut.</span><span class="sxs-lookup"><span data-stu-id="2c43f-117">The steps in this procedure modify the configuration so that file share delivery is listed as the first option in the UI and it is the default selection.</span></span>

     <span data-ttu-id="2c43f-118">Ouvrez le fichier RSReportServer.config dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="2c43f-118">Open the RSReportServer.config file in a text editor.</span></span> <span data-ttu-id="2c43f-119">Pour plus d'informations sur le fichier de configuration, consultez [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="2c43f-119">For more information on the configuration file, see [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md).</span></span> <span data-ttu-id="2c43f-120">Une fois la configuration modifiée, l'interface utilisateur doit ressembler à l'image suivante :</span><span class="sxs-lookup"><span data-stu-id="2c43f-120">After the configuration changes, the UI will look like the following image:</span></span>

     <span data-ttu-id="2c43f-121">![liste modifiée des extensions de remise](../media/ssrs-modified-delivery.png "liste modifiée des extensions de remise")</span><span class="sxs-lookup"><span data-stu-id="2c43f-121">![modified list of delivery extensions](../media/ssrs-modified-delivery.png "modified list of delivery extensions")</span></span>

2.  <span data-ttu-id="2c43f-122">Modifiez la section DeliveryUI pour qu’elle ressemble à l'exemple suivant et notez les changements principaux :</span><span class="sxs-lookup"><span data-stu-id="2c43f-122">Modify the DeliveryUI section to look like the following sample and note the key changes of:</span></span>

    1.  <span data-ttu-id="2c43f-123">L'extension de partage de fichiers se trouve avant l'extension de messagerie.</span><span class="sxs-lookup"><span data-stu-id="2c43f-123">The FileShare extension is before the email extension.</span></span> <span data-ttu-id="2c43f-124">Cela modifie l'ordre selon lequel les extensions sont répertoriées dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2c43f-124">This will change the order the extensions are listed in Report Manager.</span></span>

    2.  <span data-ttu-id="2c43f-125">L’extension de partage de fichiers contient la balise DefaultExtension `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` et `</Extension>`a été ajouté à la balise de fin d’extension.</span><span class="sxs-lookup"><span data-stu-id="2c43f-125">The File share extension contains DefaultExtension tag `<DefaultDeliveryExtension>True</DefaultDeliveryExtension>` and the extension end tag was added `</Extension>`.</span></span>

    3.  <span data-ttu-id="2c43f-126">L'extension de messagerie n'est plus configurée comme celle par défaut.</span><span class="sxs-lookup"><span data-stu-id="2c43f-126">The email extension is no longer configured as the default.</span></span> `<DefaultDeliveryExtension>False</DefaultDeliveryExtension>`

    ```
    <DeliveryUI>
         <Extension Name="Report Server FileShare" Type="Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl,ReportingServicesFileShareDeliveryProvider">
              <DefaultDeliveryExtension>True</DefaultDeliveryExtension>
         </Extension>
         <Extension Name="Report Server Email" Type="Microsoft.ReportingServices.EmailDeliveryProvider.EmailDeliveryProviderControl,ReportingServicesEmailDeliveryProvider">
         <DefaultDeliveryExtension>False</DefaultDeliveryExtension>
         <Configuration>
              <RSEmailDPConfiguration>
                   <DefaultRenderingExtension>MHTML</DefaultRenderingExtension>
              </RSEmailDPConfiguration>
         </Configuration>
         </Extension>
    </DeliveryUI>
    ```

3.  <span data-ttu-id="2c43f-127">Enregistrez le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="2c43f-127">Save the configuration file.</span></span>

4.  <span data-ttu-id="2c43f-128">En quelques minutes, le serveur de rapports recharge le fichier de configuration et les nouveaux paramètres prennent effet.</span><span class="sxs-lookup"><span data-stu-id="2c43f-128">Within a few minutes the report server will reload the configuration file and the new settings will take effect.</span></span> <span data-ttu-id="2c43f-129">Vous pouvez redémarrer le service de serveur de rapports pour forcer le chargement du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="2c43f-129">You can restart the report server service to force the loading of the configuration file.</span></span>

     <span data-ttu-id="2c43f-130">Lors de la lecture de la configuration, l'événement suivant est écrit dans le journal des événements Windows.</span><span class="sxs-lookup"><span data-stu-id="2c43f-130">The following event is written to the windows event log when the configuration is read.</span></span>

     <span data-ttu-id="2c43f-131">**ID d’événement :** 109</span><span class="sxs-lookup"><span data-stu-id="2c43f-131">**Event ID:** 109</span></span>

     <span data-ttu-id="2c43f-132">**Source :** Service Windows Serveur de rapports (nom de l'instance)</span><span class="sxs-lookup"><span data-stu-id="2c43f-132">**Source:** Report Server Windows Service (instance name)</span></span>

     <span data-ttu-id="2c43f-133">Le fichier RSReportServer.config a été modifié.</span><span class="sxs-lookup"><span data-stu-id="2c43f-133">The RSReportServer.config file has been modified</span></span>

## <a name="sharepoint-mode-report-servers"></a><span data-ttu-id="2c43f-134">Serveurs de rapports en mode SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c43f-134">SharePoint mode report servers</span></span>
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2c43f-135">Le mode SharePoint stocke les informations d’extensions dans les bases de données d’application de service SharePoint et non dans le fichier RsrReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="2c43f-135">SharePoint mode stores extensions information in the SharePoint service application databases and not in the RsrReportServer.config file.</span></span> <span data-ttu-id="2c43f-136">En mode SharePoint, la configuration d'extension de remise est modifiée à l'aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2c43f-136">In SharePoint mode, delivery extension configuration is modified using PowerShell.</span></span>

#### <a name="configure-the-default-delivery-extension"></a><span data-ttu-id="2c43f-137">Configuration de l'extension de remise par défaut</span><span class="sxs-lookup"><span data-stu-id="2c43f-137">Configure the default delivery extension</span></span>

1.  <span data-ttu-id="2c43f-138">Ouvrez **SharePoint Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2c43f-138">Open the **SharePoint Management Shell**.</span></span>

2.  <span data-ttu-id="2c43f-139">Vous pouvez ignorer cette étape si vous connaissez déjà le nom de votre application de service [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2c43f-139">You can skip this step if you already know the name of your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application.</span></span> <span data-ttu-id="2c43f-140">Utilisez la commande PowerShell suivante pour dresser la liste des applications de service [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] présentes dans votre batterie de serveurs SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2c43f-140">Use the following PowerShell to list the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service applications in your SharePoint farm.</span></span>

    ```powershell
    Get-SPRSServiceApplication | Format-List *
    ```

3.  <span data-ttu-id="2c43f-141">Exécutez la commande PowerShell suivante pour vérifier l’extension de remise par défaut actuelle de l’application de service [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] « ssrsapp ».</span><span class="sxs-lookup"><span data-stu-id="2c43f-141">Run the following PowerShell to verify the current default delivery extension for the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] service application "ssrsapp".</span></span>

    ```powershell
    $app = Get-SPRSServiceApplication | Where {$_.name -Like "ssrsapp*"};
    Get-SPRSExtension -Identity $app | Where {$_.ServerDirectivesXML -Like "<DefaultDelivery*"} | Format-List *
    ```

## <a name="see-also"></a><span data-ttu-id="2c43f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c43f-142">See Also</span></span>
 <span data-ttu-id="2c43f-143">[Fichier de configuration RSReportServer](../report-server/rsreportserver-config-configuration-file.md) fichier de [configuration RSReportServer](../report-server/rsreportserver-config-configuration-file.md) [remise par partage de fichiers dans Reporting Services](file-share-delivery-in-reporting-services.md) [remise par courrier électronique dans Reporting Services](e-mail-delivery-in-reporting-services.md) [configurer un serveur de rapports pour la remise par messagerie &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span><span class="sxs-lookup"><span data-stu-id="2c43f-143">[RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [RSReportServer Configuration File](../report-server/rsreportserver-config-configuration-file.md) [File Share Delivery in Reporting Services](file-share-delivery-in-reporting-services.md) [E-Mail Delivery in Reporting Services](e-mail-delivery-in-reporting-services.md) [Configure a Report Server for E-Mail Delivery &#40;SSRS Configuration Manager&#41;](../../sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)</span></span>
