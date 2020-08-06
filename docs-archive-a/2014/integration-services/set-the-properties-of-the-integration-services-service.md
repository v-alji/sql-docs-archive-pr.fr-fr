---
title: Définir les propriétés du service Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- Integration Services service, properties
ms.assetid: 3a8ad546-0f58-4b31-ab56-58d6313b1098
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 055eadd9a1d59c59dd40675b142eae480763f6f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709724"
---
# <a name="set-the-properties-of-the-integration-services-service"></a><span data-ttu-id="bd542-102">définir les propriétés du service Integration Services</span><span class="sxs-lookup"><span data-stu-id="bd542-102">Set the Properties of the Integration Services Service</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="bd542-103">Cette rubrique présente le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un service Windows qui permet de gérer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd542-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="bd542-104">prend en charge le service pour la compatibilité avec les versions antérieures de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd542-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="bd542-105">À compter de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vous pouvez gérer des objets tels que des packages sur le serveur Integration Services.</span><span class="sxs-lookup"><span data-stu-id="bd542-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="bd542-106">Le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gère et surveille les packages dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bd542-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages and monitors packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="bd542-107">Lorsque vous installez pour la première fois [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , le [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service est démarré et le type de démarrage du service est défini sur automatique.</span><span class="sxs-lookup"><span data-stu-id="bd542-107">When you first install [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is started and the startup type of the service is set to automatic.</span></span>  
  
 <span data-ttu-id="bd542-108">Après avoir installé le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , vous pouvez définir les propriétés du service en utilisant le composant logiciel enfichable Gestionnaire de configuration SQL Server ou Services MMC.</span><span class="sxs-lookup"><span data-stu-id="bd542-108">After the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has been installed, you can set the properties of the service by using either SQL Server Configuration Manager or the Services MMC snap-in.</span></span>  
  
 <span data-ttu-id="bd542-109">Pour configurer d'autres fonctionnalités importantes du service, y compris les emplacements auxquels il stocke et gère les packages, vous devez modifier le fichier de configuration du service.</span><span class="sxs-lookup"><span data-stu-id="bd542-109">To configure other important features of the service, including the locations where it stores and manages packages, you must modify the configuration file of the service.</span></span> <span data-ttu-id="bd542-110">Pour plus d’informations, consultez [Configuration du service Integration Services &#40;Service SSIS&#41;](service/integration-services-service-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="bd542-110">For more information, see [Configuring the Integration Services Service &#40;SSIS Service&#41;](service/integration-services-service-ssis-service.md).</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-sql-server-configuration-manager"></a><span data-ttu-id="bd542-111">Pour définir les propriétés du service Integration Services à l'aide du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="bd542-111">To set properties of the Integration Services service by using SQL Server Configuration Manager</span></span>  
  
1.  <span data-ttu-id="bd542-112">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur **Microsoft SQL Server**, sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="bd542-112">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server**, point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="bd542-113">Dans le composant logiciel enfichable **Gestionnaire de configuration SQL Server** , recherchez **SQL Server Integration Services** dans la liste des services, cliquez avec le bouton droit sur **SQL Server Integration Services**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd542-113">In the **SQL Server Configuration Manager** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="bd542-114">Dans la boîte de dialogue **Propriétés du SQL Server Integration Services** , vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd542-114">In the **SQL Server Integration Services Properties** dialog box you can do the following:</span></span>  
  
    -   <span data-ttu-id="bd542-115">Cliquez sur l’onglet **Ouvrir une session** pour afficher les informations d’ouverture de session, comme le nom du compte.</span><span class="sxs-lookup"><span data-stu-id="bd542-115">Click the **Log On** tab to view the logon information such as the account name.</span></span>  
  
    -   <span data-ttu-id="bd542-116">Cliquez sur l’onglet **Service** pour afficher les informations relatives au service, comme le nom de l’ordinateur hôte, puis spécifiez le mode de démarrage du service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd542-116">Click the **Service** tab to view information about the service such as the name of the host computer and to specify the start mode of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="bd542-117">L’onglet **Avancé** ne contient aucune information sur le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bd542-117">The **Advanced** tab contains no information for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
4.  <span data-ttu-id="bd542-118">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd542-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="bd542-119">Dans le menu **Fichier** , cliquez sur **Quitter** pour fermer le composant logiciel enfichable **Gestionnaire de configuration SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="bd542-119">On the **File** menu, click **Exit** to close the **SQL Server Configuration Manager** snap-in.</span></span>  
  
### <a name="to-set-properties-of-the-integration-services-service-by-using-services"></a><span data-ttu-id="bd542-120">Pour définir les propriétés du service Integration Services à l’aide de Services</span><span class="sxs-lookup"><span data-stu-id="bd542-120">To set properties of the Integration Services service by using Services</span></span>  
  
1.  <span data-ttu-id="bd542-121">Dans le **Panneau de configuration**, si vous utilisez l’affichage classique, cliquez sur **Outils d’administration**. Si vous utilisez l’affichage des catégories, cliquez sur **Performance et maintenance** puis sur **Outils d’administration**.</span><span class="sxs-lookup"><span data-stu-id="bd542-121">In **Control Panel**, if you are using Classic View, click **Administrative Tools**, or, if you are using Category View, click **Performance and Maintenance** and then click **Administrative Tools**.</span></span>  
  
2.  <span data-ttu-id="bd542-122">Cliquez sur **Services**.</span><span class="sxs-lookup"><span data-stu-id="bd542-122">Click **Services**.</span></span>  
  
3.  <span data-ttu-id="bd542-123">Dans le composant logiciel enfichable **Services** , recherchez **SQL Server Integration Services** dans la liste des services, cliquez avec le bouton droit sur **SQL Server Integration Services**, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="bd542-123">In the **Services** snap-in, locate **SQL Server Integration Services** in the list of services, right-click **SQL Server Integration Services**, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="bd542-124">Dans la boîte de dialogue **Propriétés de SQL Server Integration Services** , vous pouvez effectuer les actions suivantes :</span><span class="sxs-lookup"><span data-stu-id="bd542-124">In the **SQL Server Integration Services Properties** dialog box, you can do the following:</span></span>  
  
    -   <span data-ttu-id="bd542-125">Cliquez sur l’onglet **général** . Pour activer le service, sélectionnez le type de démarrage manuel ou automatique.</span><span class="sxs-lookup"><span data-stu-id="bd542-125">Click the **General** tab. To enable the service, select either the manual or automatic startup type.</span></span> <span data-ttu-id="bd542-126">Pour désactiver le service, sélectionnez Désactiver dans la zone **Type de démarrage** .</span><span class="sxs-lookup"><span data-stu-id="bd542-126">To disable the service, select Disable in the **Startup type** box.</span></span> <span data-ttu-id="bd542-127">Le fait de sélectionner Désactiver n'arrête pas le service s'il est en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="bd542-127">Selecting Disable does not stop the service if it is currently running.</span></span>  
  
         <span data-ttu-id="bd542-128">Si le service est déjà activé, vous pouvez cliquer sur **Arrêter** pour arrêter le service ou sur **Démarrer** pour le démarrer.</span><span class="sxs-lookup"><span data-stu-id="bd542-128">If the service is already enabled, you can click **Stop** to stop the service, or click **Start** to start the service.</span></span>  
  
    -   <span data-ttu-id="bd542-129">Cliquez sur l’onglet **Ouvrir une session** pour afficher ou modifier les informations d’ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="bd542-129">Click the **Log On** tab to view or edit the logon information.</span></span>  
  
    -   <span data-ttu-id="bd542-130">Cliquez sur l’onglet **Récupération** pour afficher les réponses par défaut de l’ordinateur à l’échec du service.</span><span class="sxs-lookup"><span data-stu-id="bd542-130">Click the **Recovery** tab to view the default computer responses to service failure.</span></span> <span data-ttu-id="bd542-131">Vous pouvez modifier ces options pour les adapter à votre environnement.</span><span class="sxs-lookup"><span data-stu-id="bd542-131">You can modify these options to suit your environment.</span></span>  
  
    -   <span data-ttu-id="bd542-132">Cliquez sur l’onglet **Dépendances** pour afficher la liste des services dépendants.</span><span class="sxs-lookup"><span data-stu-id="bd542-132">Click the **Dependencies** tab to view a list of dependent services.</span></span> <span data-ttu-id="bd542-133">Le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] n’a pas de dépendances.</span><span class="sxs-lookup"><span data-stu-id="bd542-133">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service has no dependencies.</span></span>  
  
5.  <span data-ttu-id="bd542-134">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd542-134">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="bd542-135">Si le type de démarrage est manuel ou automatique, vous pouvez si vous le souhaitez cliquer avec le bouton droit sur **SQL Server Integration Services** , puis cliquer sur **Démarrer, Arrêter ou Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="bd542-135">Optionally, if the startup type is Manual or Automatic, you can right-click **SQL Server Integration Services** and click **Start, Stop, or Restart**.</span></span>  
  
7.  <span data-ttu-id="bd542-136">Dans le menu **Fichier** , cliquez sur **Quitter** pour fermer le composant logiciel enfichable **Services** .</span><span class="sxs-lookup"><span data-stu-id="bd542-136">On the **File** menu, click **Exit** to close the **Services** snap-in.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd542-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bd542-137">See Also</span></span>  
 [<span data-ttu-id="bd542-138">Gérer le service Integration Services</span><span class="sxs-lookup"><span data-stu-id="bd542-138">Manage the Integration Services Service</span></span>](../../2014/integration-services/manage-the-integration-services-service.md)  
  
  
