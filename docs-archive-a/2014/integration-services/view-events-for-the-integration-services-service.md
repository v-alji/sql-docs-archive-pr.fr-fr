---
title: Afficher les événements du service Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- events [Integration Services]
- service [Integration Services], events
- Integration Services service, events
ms.assetid: 37e23946-10d1-4116-8568-8fd24067102e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a513c8fc917da2987f3619c8eb9011e1170f7dcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613009"
---
# <a name="view-events-for-the-integration-services-service"></a><span data-ttu-id="0b4b0-102">afficher les événements du service Integration Services</span><span class="sxs-lookup"><span data-stu-id="0b4b0-102">View Events for the Integration Services Service</span></span>
  <span data-ttu-id="0b4b0-103">Il existe deux outils dans lesquels vous pouvez afficher les événements du service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="0b4b0-103">There are two tools in which you can view events for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service:</span></span>  
  
-   <span data-ttu-id="0b4b0-104">La boîte de dialogue **Visionneuse du fichier journal** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b4b0-104">The **Log File Viewer** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="0b4b0-105">La boîte de dialogue **Visionneuse du fichier Journal** comprend des options permettant d’exporter et de filtrer le journal et d’effectuer des recherches.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-105">The **Log File Viewer** dialog box includes options to export, filter, and search the log.</span></span> <span data-ttu-id="0b4b0-106">Pour plus d’informations sur les options de la **Visionneuse du fichier Journal**, consultez [Visionneuse du fichier journal - Aide (F1)](../relational-databases/logs/log-file-viewer-f1-help.md).</span><span class="sxs-lookup"><span data-stu-id="0b4b0-106">For more information about the options in the **Log File Viewer**, see [Log File Viewer F1 Help](../relational-databases/logs/log-file-viewer-f1-help.md).</span></span>  
  
-   <span data-ttu-id="0b4b0-107">L'Observateur d'événements Windows.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-107">The Windows Event Viewer.</span></span>  
  
 <span data-ttu-id="0b4b0-108">Pour obtenir une description des événements consignés par le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , consultez [Événements consignés par le service Integration Services](service/events-logged-by-the-integration-services-service.md).</span><span class="sxs-lookup"><span data-stu-id="0b4b0-108">For descriptions of the events logged by the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, see [Events Logged by the Integration Services Service](service/events-logged-by-the-integration-services-service.md).</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-sql-server-management-studio"></a><span data-ttu-id="0b4b0-109">Pour afficher les événements du service Integration Services dans SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0b4b0-109">To view service events for Integration Services in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="0b4b0-110">Ouvrez [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b4b0-110">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="0b4b0-111">Dans le menu **Fichier** , cliquez sur **Connecter l’Explorateur d’objets**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-111">On the **File** menu, click **Connect Object Explorer**.</span></span>  
  
3.  <span data-ttu-id="0b4b0-112">Dans la boîte de dialogue **Se connecter au serveur** , sélectionnez le type de serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , sélectionnez ou recherchez le serveur auquel la connexion doit être établie, puis cliquez sur **Se connecter**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-112">In the **Connect to Server** dialog box, select the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server type, select or locate the server to connect to, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="0b4b0-113">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , puis sélectionnez **Afficher les journaux**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-113">In Object Explorer, right-click [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] and click **View Logs**.</span></span>  
  
5.  <span data-ttu-id="0b4b0-114">Pour afficher les événements [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , sélectionnez **SQL Server Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-114">To view [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] events, select **SQL Server Integration Services**.</span></span> <span data-ttu-id="0b4b0-115">L’option **Événements NT** est automatiquement sélectionnée et effacée avec l’option **SQL Server Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="0b4b0-115">The **NT Events** option is automatically selected and cleared with the **SQL Server Integration Services** option.</span></span>  
  
### <a name="to-view-service-events-for-integration-services-in-windows-event-viewer"></a><span data-ttu-id="0b4b0-116">Pour afficher les événements du service Integration Services dans l'Observateur d'événements Windows</span><span class="sxs-lookup"><span data-stu-id="0b4b0-116">To view service events for Integration Services in Windows Event Viewer</span></span>  
  
1.  <span data-ttu-id="0b4b0-117">Dans le **Panneau de configuration**, si vous utilisez l’affichage classique, cliquez sur **Outils d’administration**. Si vous utilisez l’affichage des catégories, cliquez sur **Performance et maintenance** puis sur **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-117">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="0b4b0-118">Cliquez sur **Observateur d’événements**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-118">Click **Event Viewer**.</span></span>  
  
3.  <span data-ttu-id="0b4b0-119">Dans la boîte de dialogue **Observateur d’événements** , cliquez sur **Application**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-119">In the **Event Viewer** dialog box, click **Application**.</span></span>  
  
4.  <span data-ttu-id="0b4b0-120">Dans le composant logiciel enfichable **Application** , recherchez dans la colonne **Source** l’entrée dont la valeur est **SQLISService**, cliquez sur cette entrée avec le bouton droit, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-120">In the **Application** snap-in, locate an entry in the **Source** column that has the value **SQLISService**, right-click the entry, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="0b4b0-121">Si vous le souhaitez, cliquez sur la flèche vers le haut ou le bas pour afficher l'événement précédent ou suivant.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-121">Optionally, click the up or down arrow to show the previous or next event.</span></span>  
  
6.  <span data-ttu-id="0b4b0-122">Vous pouvez également cliquez sur l'icône Copier dans le Presse-papiers pour copier les informations sur l'événement.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-122">Optionally, click the Copy to Clipboard icon to copy the event information.</span></span>  
  
7.  <span data-ttu-id="0b4b0-123">Choisissez d'afficher les données d'événements sous forme d'octets ou de mots.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-123">Choose to display event data using bytes or words.</span></span>  
  
8.  <span data-ttu-id="0b4b0-124">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b4b0-124">Click **OK**.</span></span>  
  
9. <span data-ttu-id="0b4b0-125">Dans le menu **Fichier** , cliquez sur **Quitter** pour fermer la boîte de dialogue **Observateur d’événements** .</span><span class="sxs-lookup"><span data-stu-id="0b4b0-125">On the **File** menu, click **Exit** to close the **Event Viewer** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b4b0-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b4b0-126">See Also</span></span>  
 <span data-ttu-id="0b4b0-127">[Gérer le service de Integration Services](../../2014/integration-services/manage-the-integration-services-service.md) </span><span class="sxs-lookup"><span data-stu-id="0b4b0-127">[Manage the Integration Services Service](../../2014/integration-services/manage-the-integration-services-service.md) </span></span>  
 [<span data-ttu-id="0b4b0-128">Ajouter un journal pour les compteurs de performances de flux de données</span><span class="sxs-lookup"><span data-stu-id="0b4b0-128">Add a Log for Data Flow Performance Counters</span></span>](performance/performance-counters.md)  
  
  
