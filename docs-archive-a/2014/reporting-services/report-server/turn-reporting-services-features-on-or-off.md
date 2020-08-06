---
title: Activer ou désactiver les fonctionnalités Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services, configuration
- security [Reporting Services], strategies
ms.assetid: b69db02a-43a7-4fdc-ad9b-438d817a7f83
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f56f9984b5b02431db23b782652e5575af557bdb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605070"
---
# <a name="turn-reporting-services-features-on-or-off"></a><span data-ttu-id="37f04-102">Activer ou désactiver les fonctionnalités Reporting Services</span><span class="sxs-lookup"><span data-stu-id="37f04-102">Turn Reporting Services Features On or Off</span></span>
  <span data-ttu-id="37f04-103">Vous pouvez désactiver les fonctionnalités de serveur de rapports que vous n'utilisez pas dans le cadre d'une stratégie de verrouillage pour réduire l'exposition aux attaques d'un serveur de rapports de production.</span><span class="sxs-lookup"><span data-stu-id="37f04-103">You can turn off report server features that you do not use as part of a lockdown strategy for reducing the attack surface of a production report server.</span></span> <span data-ttu-id="37f04-104">Dans la plupart des cas, vous préférerez exécuter les fonctionnalités de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] conjointement afin de bénéficier de toutes les fonctionnalités offertes dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f04-104">In most cases, you will want to run [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features concurrently to use all of the functionality provided in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="37f04-105">Toutefois, vous pouvez désactiver les fonctionnalités dont vous n'avez pas besoin, selon votre modèle de déploiement.</span><span class="sxs-lookup"><span data-stu-id="37f04-105">However, depending on your deployment model, you can disable the features that you do not require.</span></span> <span data-ttu-id="37f04-106">Par exemple, vous pouvez activer le traitement en arrière-plan uniquement si le traitement de tous les rapports a été planifié.</span><span class="sxs-lookup"><span data-stu-id="37f04-106">For example, you can enable only the background processing if all report processing is configured as scheduled operations.</span></span> <span data-ttu-id="37f04-107">De même, vous pouvez exécuter simplement le service Web Report Server si vous souhaitez disposer uniquement de rapports interactifs à la demande.</span><span class="sxs-lookup"><span data-stu-id="37f04-107">Similarly, you can run just the Report Server Web service if you only want interactive, on-demand reporting.</span></span>  
  
 <span data-ttu-id="37f04-108">Les procédures passées en revue dans cette rubrique vous indiquent comment désactiver les fonctionnalités [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] en mode natif.</span><span class="sxs-lookup"><span data-stu-id="37f04-108">The procedures in this topic show you how to turn off native mode [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] features.</span></span> <span data-ttu-id="37f04-109">Les fonctionnalités peuvent être configurées de différentes façons, par exemple en modifiant directement le fichier `RsReportServer.config` ou en utilisant la facette **Configuration de la surface d’exposition pour Reporting Services** de la gestion basée sur des stratégies dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f04-109">Features can be configured in different ways, such as by editing the `RsReportServer.config` file directly or by using the **Surface Area Configuration for Reporting Services** facet of Policy-Based Management in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="37f04-110">Utilisez les liens pour localiser les procédures qui expliquent comment activer ou désactiver une fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="37f04-110">Use the links to locate the procedure or procedures that explain how to turn a feature on or off:</span></span>  
  
-   [<span data-ttu-id="37f04-111">Service Web Report Server</span><span class="sxs-lookup"><span data-stu-id="37f04-111">Report Server Web service</span></span>](#RSWebSvc)  
  
-   [<span data-ttu-id="37f04-112">Traitement et événements planifiés</span><span class="sxs-lookup"><span data-stu-id="37f04-112">Scheduled events and processing</span></span>](#Sched)  
  
-   [<span data-ttu-id="37f04-113">Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="37f04-113">Report Manager</span></span>](#ReportManager)  
  
-   [<span data-ttu-id="37f04-114">Générateur de rapports</span><span class="sxs-lookup"><span data-stu-id="37f04-114">Report Builder</span></span>](#ReportBuilder)  
  
-   [<span data-ttu-id="37f04-115">Sécurité intégrée de Windows pour les sources de données de rapport</span><span class="sxs-lookup"><span data-stu-id="37f04-115">Windows Integrated security for report data sources</span></span>](#WinIntSec)  
  
##  <a name="report-server-web-service"></a><a name="RSWebSvc"></a><span data-ttu-id="37f04-116">Service Web Report Server</span><span class="sxs-lookup"><span data-stu-id="37f04-116">Report Server Web Service</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-editing-configuration"></a><span data-ttu-id="37f04-117">Pour activer le service Web Report Server en modifiant la configuration</span><span class="sxs-lookup"><span data-stu-id="37f04-117">To turn on or off the Report Server Web service by editing configuration</span></span>  
  
1.  <span data-ttu-id="37f04-118">Ouvrez le fichier `RsReportServer.config` dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="37f04-118">Open the `RsReportServer.config` file in a text editor.</span></span> <span data-ttu-id="37f04-119">Pour plus d’informations, consultez [Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f04-119">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="37f04-120">Pour activer le service Web Report Server, affectez à `IsWebServiceEnabled` la valeur `true` :</span><span class="sxs-lookup"><span data-stu-id="37f04-120">To turn on the Report Server Web service, set `IsWebServiceEnabled` to `true`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>true</IsWebServiceEnabled>  
    ```  
  
3.  <span data-ttu-id="37f04-121">Pour désactiver le service Web Report Server, affectez à `IsWebServiceEnabled` la valeur `false` :</span><span class="sxs-lookup"><span data-stu-id="37f04-121">To turn off the Report Server Web service, set `IsWebServiceEnabled` to `false`:</span></span>  
  
    ```  
    <IsWebServiceEnabled>false</IsWebServiceEnabled>  
    ```  
  
4.  <span data-ttu-id="37f04-122">Enregistrez vos modifications et fermez le fichier.</span><span class="sxs-lookup"><span data-stu-id="37f04-122">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-the-report-server-web-service-by-using-sql-server-management-studio"></a><span data-ttu-id="37f04-123">Pour activer ou désactiver le service Web Report Server en utilisant SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37f04-123">To turn on or off the Report Server Web service by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="37f04-124">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis connectez-vous à l'instance [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à configurer.</span><span class="sxs-lookup"><span data-stu-id="37f04-124">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="37f04-125">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nœud [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , pointez sur **Stratégies**, puis cliquez sur **Facettes**.</span><span class="sxs-lookup"><span data-stu-id="37f04-125">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="37f04-126">Dans la liste **Facette** , sélectionnez **Configuration de la surface d'exposition pour Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="37f04-126">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="37f04-127">Sous **Propriétés de la facette**:</span><span class="sxs-lookup"><span data-stu-id="37f04-127">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="37f04-128">Pour activer le service Web Report Server, affectez à **WebServiceAndHTTPAccessEnabled** la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="37f04-128">To turn on the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="37f04-129">Pour désactiver le service Web Report Server, affectez à **WebServiceAndHTTPAccessEnabled** la valeur `False` .</span><span class="sxs-lookup"><span data-stu-id="37f04-129">To turn off the Report Server Web service, set **WebServiceAndHTTPAccessEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="scheduled-events-and-delivery"></a><a name="Sched"></a> <span data-ttu-id="37f04-130">Événements planifiés et remise</span><span class="sxs-lookup"><span data-stu-id="37f04-130">Scheduled Events and Delivery</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-editing-configuration"></a><span data-ttu-id="37f04-131">Pour activer ou désactiver les événements planifiés et la remise en modifiant la configuration</span><span class="sxs-lookup"><span data-stu-id="37f04-131">To turn on or off scheduled events and delivery by editing configuration</span></span>  
  
1.  <span data-ttu-id="37f04-132">Ouvrez le fichier RsReportServer.config dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="37f04-132">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="37f04-133">Pour plus d’informations, consultez [Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f04-133">For more information, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="37f04-134">Pour activer le traitement et la remise des rapports planifiés, affectez à `IsSchedulingService`, `IsNotificationService` et `IsEventService` la valeur `true` :</span><span class="sxs-lookup"><span data-stu-id="37f04-134">To turn on scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `true`:</span></span>  
  
    ```  
    <IsSchedulingService>true</IsSchedulingService>  
    <IsNotificationService>true</IsNotificationService>  
    <IsEventService>true</IsEventService>  
    ```  
  
3.  <span data-ttu-id="37f04-135">Pour désactiver le traitement et la remise des rapports planifiés, affectez la à `IsSchedulingService`, `IsNotificationService` et `IsEventService` la valeur `false` :</span><span class="sxs-lookup"><span data-stu-id="37f04-135">To turn off scheduled report processing and delivery, set `IsSchedulingService`, `IsNotificationService`, and `IsEventService` to `false`:</span></span>  
  
    ```  
    <IsSchedulingService>false</IsSchedulingService>  
    <IsNotificationService>false</IsNotificationService>  
    <IsEventService>false</IsEventService>  
    ```  
  
4.  <span data-ttu-id="37f04-136">Enregistrez vos modifications et fermez le fichier.</span><span class="sxs-lookup"><span data-stu-id="37f04-136">Save your changes and then close the file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="37f04-137">Vous ne pouvez pas désactiver complètement le traitement en arrière-plan car il fournit des fonctionnalités de maintenance de base de données requises pour les opérations de serveur.</span><span class="sxs-lookup"><span data-stu-id="37f04-137">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
#### <a name="to-turn-on-or-off-scheduled-events-and-delivery-by-using-sql-server-management-studio"></a><span data-ttu-id="37f04-138">Pour activer ou désactiver les événements planifiés et leur remise en utilisant SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37f04-138">To turn on or off scheduled events and delivery by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="37f04-139">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis connectez-vous à l'instance [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à configurer.</span><span class="sxs-lookup"><span data-stu-id="37f04-139">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="37f04-140">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nœud [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , pointez sur **Stratégies**, puis cliquez sur **Facettes**.</span><span class="sxs-lookup"><span data-stu-id="37f04-140">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="37f04-141">Dans la liste **Facette** , sélectionnez **Configuration de la surface d'exposition pour Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="37f04-141">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="37f04-142">Sous **Propriétés de la facette**:</span><span class="sxs-lookup"><span data-stu-id="37f04-142">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="37f04-143">Pour activer les événements planifiés et la remise, affectez à **ScheduleEventsAndReportDeliveryEnabled** la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="37f04-143">To turn on scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="37f04-144">Pour désactiver les événements planifiés et la remise, affectez à **ScheduleEventsAndReportDeliveryEnabled** la valeur `False` .</span><span class="sxs-lookup"><span data-stu-id="37f04-144">To turn off scheduled events and delivery, set **ScheduleEventsAndReportDeliveryEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="37f04-145">Vous ne pouvez pas désactiver complètement le traitement en arrière-plan car il fournit des fonctionnalités de maintenance de base de données requises pour les opérations de serveur.</span><span class="sxs-lookup"><span data-stu-id="37f04-145">You cannot turn off background processing completely because it provides database maintenance functionality that is required for server operations.</span></span>  
  
##  <a name="report-manager"></a><a name="ReportManager"></a><span data-ttu-id="37f04-146">Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="37f04-146">Report Manager</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-editing-configuration"></a><span data-ttu-id="37f04-147">Pour activer ou désactiver le Gestionnaire de rapports en modifiant la configuration</span><span class="sxs-lookup"><span data-stu-id="37f04-147">To turn on or off Report Manager by editing configuration</span></span>  
  
1.  <span data-ttu-id="37f04-148">Ouvrez le fichier RsReportServer.config dans un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="37f04-148">Open the RsReportServer.config file in a text editor.</span></span> <span data-ttu-id="37f04-149">Pour obtenir des instructions, consultez [Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37f04-149">For instructions, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](modify-a-reporting-services-configuration-file-rsreportserver-config.md) in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
2.  <span data-ttu-id="37f04-150">Pour activer le Gestionnaire de rapports, affectez à `IsReportManagerEnabled` la valeur `true`:</span><span class="sxs-lookup"><span data-stu-id="37f04-150">To turn on Report Manager, set `IsReportManagerEnabled` to `true`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>true</IsReportManagerEnabled>  
    ```  
  
3.  <span data-ttu-id="37f04-151">Pour désactiver le Gestionnaire de rapports, affectez à `IsReportManagerEnabled` la valeur `false`:</span><span class="sxs-lookup"><span data-stu-id="37f04-151">To turn off Report Manager, set `IsReportManagerEnabled` to `false`:</span></span>  
  
    ```  
    <IsReportManagerEnabled>false</IsReportManagerEnabled>  
    ```  
  
4.  <span data-ttu-id="37f04-152">Enregistrez vos modifications et fermez le fichier.</span><span class="sxs-lookup"><span data-stu-id="37f04-152">Save your changes and then close the file.</span></span>  
  
#### <a name="to-turn-on-or-off-report-manager-by-using-sql-server-management-studio"></a><span data-ttu-id="37f04-153">Pour activer ou désactiver le Gestionnaire de rapports en utilisant SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37f04-153">To turn on or off Report Manager by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="37f04-154">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis connectez-vous à l'instance [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à configurer.</span><span class="sxs-lookup"><span data-stu-id="37f04-154">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="37f04-155">Dans l' **Explorateur d’objets**, cliquez avec le bouton droit sur le [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] nœud, pointez sur **stratégies**, puis cliquez sur **facettes**.</span><span class="sxs-lookup"><span data-stu-id="37f04-155">In **Object Explorer**, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, point to **Policies**, and click **Facets**.</span></span>  
  
3.  <span data-ttu-id="37f04-156">Dans la liste **Facette** , sélectionnez **Configuration de la surface d'exposition pour Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="37f04-156">In the **Facet** list, select **Surface Area Configuration for Reporting Services**.</span></span>  
  
4.  <span data-ttu-id="37f04-157">Sous **Propriétés de la facette**:</span><span class="sxs-lookup"><span data-stu-id="37f04-157">Under **Facet Properties**:</span></span>  
  
    -   <span data-ttu-id="37f04-158">Pour activer Gestionnaire de rapports, affectez à **affectez ReportManagerEnabled** la valeur `True` .</span><span class="sxs-lookup"><span data-stu-id="37f04-158">To turn on Report Manager, set **ReportManagerEnabled** to `True`.</span></span>  
  
    -   <span data-ttu-id="37f04-159">Pour désactiver Gestionnaire de rapports, affectez à **affectez ReportManagerEnabled** la valeur `False` .</span><span class="sxs-lookup"><span data-stu-id="37f04-159">To turn off Report Manager, set **ReportManagerEnabled** to `False`.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="report-builder"></a><span data-ttu-id="37f04-160">Générateur de rapports <a name="ReportBuilder"></a></span><span class="sxs-lookup"><span data-stu-id="37f04-160"><a name="ReportBuilder"></a> Report Builder</span></span>  
  
#### <a name="to-turn-on-or-off-report-builder-by-using-sql-server-management-studio"></a><span data-ttu-id="37f04-161">Pour activer ou désactiver le Générateur de rapports en utilisant SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37f04-161">To turn on or off Report Builder by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="37f04-162">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis connectez-vous à l'instance [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à configurer.</span><span class="sxs-lookup"><span data-stu-id="37f04-162">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="37f04-163">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nœud [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="37f04-163">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="37f04-164">Dans la boîte de dialogue **Propriétés du serveur** , sous **Sélectionner une page**, cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="37f04-164">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="37f04-165">Pour activer le Générateur de rapports, sélectionnez l'option **Activer les exécutions de rapports ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="37f04-165">To turn on Report Builder, select the **Enable ad hoc report executions** option.</span></span>  
  
    -   <span data-ttu-id="37f04-166">Pour désactiver le Générateur de rapports, désélectionnez l'option **Activer les exécutions de rapports ad hoc** .</span><span class="sxs-lookup"><span data-stu-id="37f04-166">To turn off Report Builder, unselect the **Enable ad hoc report executions** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
##  <a name="windows-integrated-security"></a><a name="WinIntSec"></a> <span data-ttu-id="37f04-167">Sécurité intégrée de Windows</span><span class="sxs-lookup"><span data-stu-id="37f04-167">Windows Integrated Security</span></span>  
  
#### <a name="to-turn-on-or-off-windows-integrated-security-by-using-sql-server-management-studio"></a><span data-ttu-id="37f04-168">Pour activer ou désactiver la sécurité intégrée de Windows en utilisant SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="37f04-168">To turn on or off Windows Integrated security by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="37f04-169">Ouvrez [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , puis connectez-vous à l'instance [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à configurer.</span><span class="sxs-lookup"><span data-stu-id="37f04-169">Open [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance that you want to configure.</span></span>  
  
2.  <span data-ttu-id="37f04-170">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur le nœud [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="37f04-170">In Object Explorer, right-click the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] node, and click **Properties**.</span></span>  
  
3.  <span data-ttu-id="37f04-171">Dans la boîte de dialogue **Propriétés du serveur** , sous **Sélectionner une page**, cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="37f04-171">In the **Server Properties** dialog box, under **Select a page**, click **Security**.</span></span>  
  
    -   <span data-ttu-id="37f04-172">Pour activer la sécurité intégrée de Windows, sélectionnez l'option **Activer la sécurité intégrée Windows pour les sources de données de rapport** .</span><span class="sxs-lookup"><span data-stu-id="37f04-172">To turn on Windows Integrated security, select the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
    -   <span data-ttu-id="37f04-173">Pour désactiver la sécurité intégrée de Windows, désélectionnez l'option **Activer la sécurité intégrée Windows pour les sources de données de rapport** .</span><span class="sxs-lookup"><span data-stu-id="37f04-173">To turn off Windows integrated security, unselect the **Enable Windows Integrated security for report data sources** option.</span></span>  
  
4.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="37f04-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="37f04-174">See Also</span></span>  
 [<span data-ttu-id="37f04-175">Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="37f04-175">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
