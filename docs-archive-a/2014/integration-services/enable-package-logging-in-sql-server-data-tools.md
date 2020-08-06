---
title: Activer la journalisation des packages dans SQL Server Data Tools | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], enabling
ms.assetid: b69a8593-5bb0-4f04-87d2-f8e7bd7eb4fc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d73dbca034047e853669dd503a62e105d1dd7b45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610768"
---
# <a name="enable-package-logging-in-sql-server-data-tools"></a><span data-ttu-id="eb2ab-102">Activer la journalisation des packages dans les outils de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb2ab-102">Enable Package Logging in SQL Server Data Tools</span></span>
  <span data-ttu-id="eb2ab-103">Cette procédure décrit comment ajouter des journaux à un package, configurer la journalisation au niveau du package et enregistrer la configuration dans un fichier XML.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-103">This procedure describes how to add logs to a package, configure package-level logging, and save the logging configuration to an XML file.</span></span> <span data-ttu-id="eb2ab-104">Vous ne pouvez ajouter des journaux qu'au niveau du package, mais le package n'a pas besoin d'effectuer une journalisation pour activer la journalisation dans les conteneurs inclus dans ce package.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-104">You can add logs only at the package level, but the package does not have to perform logging to enable logging in the containers that the package includes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eb2ab-105">Si vous déployez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sur le serveur [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , le niveau de journalisation que vous définissez pour l'exécution du package remplace l'enregistrement du package que vous configurez dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb2ab-105">If you deploy the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server, the logging level that you set for the package execution overrides the package logging that you configure using [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="eb2ab-106">Par défaut, les conteneurs du package utilisent la même configuration de journalisation que leur conteneur parent.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-106">By default, the containers in the package use the same logging configuration as their parent container.</span></span> <span data-ttu-id="eb2ab-107">Pour plus d’informations sur la définition des options de journalisation pour les conteneurs individuels, consultez [Configurer la journalisation à l’aide d’un fichier de configuration enregistré](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="eb2ab-107">For information about setting logging options for individual containers, see [Configure Logging by Using a Saved Configuration File](../../2014/integration-services/configure-logging-by-using-a-saved-configuration-file.md).</span></span>  
  
### <a name="to-enable-logging-in-a-package"></a><span data-ttu-id="eb2ab-108">Pour activer la journalisation dans un package</span><span class="sxs-lookup"><span data-stu-id="eb2ab-108">To enable logging in a package</span></span>  
  
1.  <span data-ttu-id="eb2ab-109">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-109">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="eb2ab-110">Dans le menu **SSIS** , cliquez sur **Enregistrement**.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-110">On the **SSIS** menu, click **Logging**.</span></span>  
  
3.  <span data-ttu-id="eb2ab-111">Sélectionnez un module fournisseur d'informations dans la liste **Type de fournisseur** , puis cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-111">Select a log provider in the **Provider type** list, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="eb2ab-112">Dans la colonne **Configuration**, sélectionnez un gestionnaire de connexions ou cliquez sur **\<New connection>** afin de créer un gestionnaire de connexions du type approprié pour le module fournisseur d’informations.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-112">In the **Configuration** column, select a connection manager or click **\<New connection>** to create a new connection manager of the appropriate type for the log provider.</span></span> <span data-ttu-id="eb2ab-113">En fonction du module fournisseur sélectionné, utilisez l'un des gestionnaires de connexions suivants :</span><span class="sxs-lookup"><span data-stu-id="eb2ab-113">Depending on the selected provider, use one of the following connection managers:</span></span>  
  
    -   <span data-ttu-id="eb2ab-114">Pour les fichiers texte, utilisez un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-114">For Text files, use a File connection manager.</span></span> <span data-ttu-id="eb2ab-115">Pour plus d’informations, consultez [File Connection Manager](connection-manager/file-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="eb2ab-115">For more information, see [File Connection Manager](connection-manager/file-connection-manager.md)</span></span>  
  
    -   <span data-ttu-id="eb2ab-116">Pour [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], utilisez un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-116">For [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use a File connection manager.</span></span>  
  
    -   <span data-ttu-id="eb2ab-117">Pour [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], utilisez un gestionnaire de connexions OLE DB.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-117">For [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], use an OLE DB connection manager.</span></span> <span data-ttu-id="eb2ab-118">Pour plus d’informations, consultez [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="eb2ab-118">For more information, see [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md).</span></span>  
  
    -   <span data-ttu-id="eb2ab-119">Pour le journal des événements Windows, ne faites rien :</span><span class="sxs-lookup"><span data-stu-id="eb2ab-119">For Windows Event Log, do nothing.</span></span> [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="eb2ab-120">crée automatiquement le journal.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-120">automatically creates the log.</span></span>  
  
    -   <span data-ttu-id="eb2ab-121">Pour les fichiers XML, utilisez un gestionnaire de connexions de fichiers.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-121">For XML files, use a File connection manager.</span></span>  
  
5.  <span data-ttu-id="eb2ab-122">Répétez les étapes 3 et 4 pour chaque journal à utiliser dans le package.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-122">Repeat steps 3 and 4 for each log to use in the package.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb2ab-123">Un package peut utiliser plusieurs journaux du même type.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-123">A package can use more than one log of each type.</span></span>  
  
6.  <span data-ttu-id="eb2ab-124">Vous pouvez également cocher la case du niveau du package, sélectionner les journaux à utiliser pour la journalisation au niveau du package, puis cliquer sur l’onglet **Détails** .</span><span class="sxs-lookup"><span data-stu-id="eb2ab-124">Optionally, select the package-level check box, select the logs to use for package-level logging, and then click the **Details** tab.</span></span>  
  
7.  <span data-ttu-id="eb2ab-125">Sur l'onglet **Détails** , activez **Événements** pour enregistrer toutes les entrées de journal ou désactivez **Événements** pour sélectionner des événements individuels.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-125">On the **Details** tab, select **Events** to log all log entries, or clear **Events** to select individual events.</span></span>  
  
8.  <span data-ttu-id="eb2ab-126">Éventuellement, cliquez sur **Avancé** pour spécifier les informations à journaliser.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-126">Optionally, click **Advanced** to specify which information to log.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="eb2ab-127">Par défaut, toutes les informations sont journalisées.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-127">By default, all information is logged.</span></span>  
  
9. <span data-ttu-id="eb2ab-128">Sous l’onglet **Détails** , cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-128">On the **Details** tab, click **Save.**</span></span> <span data-ttu-id="eb2ab-129">La boîte de dialogue **Enregistrer sous** s’affiche.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-129">The **Save As** dialog box appears.</span></span> <span data-ttu-id="eb2ab-130">Recherchez l'emplacement où enregistrer la configuration de journalisation, tapez un nom de fichier pour la nouvelle configuration de journal, puis cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-130">Locate the folder in which to save the logging configuration, type a file name for the new log configuration, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="eb2ab-131">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb2ab-131">Click **OK**.</span></span>  
  
11. <span data-ttu-id="eb2ab-132">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="eb2ab-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb2ab-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb2ab-133">See Also</span></span>  
 <span data-ttu-id="eb2ab-134">[Integration Services &#40;la journalisation SSIS&#41;](performance/integration-services-ssis-logging.md) </span><span class="sxs-lookup"><span data-stu-id="eb2ab-134">[Integration Services &#40;SSIS&#41; Logging](performance/integration-services-ssis-logging.md) </span></span>  
 [<span data-ttu-id="eb2ab-135">Journalisation Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="eb2ab-135">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
