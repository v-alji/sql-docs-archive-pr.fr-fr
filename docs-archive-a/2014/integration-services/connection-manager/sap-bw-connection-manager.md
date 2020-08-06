---
title: Gestionnaire de connexions SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 06b166a1-a9df-48ea-a0e8-9b8d6979c0a1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bc3bb32c4895c6ec8fbcf31d57e8685c74de32dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602261"
---
# <a name="sap-bw-connection-manager"></a><span data-ttu-id="e5b49-102">Gestionnaire de connexions SAP BW</span><span class="sxs-lookup"><span data-stu-id="e5b49-102">SAP BW Connection Manager</span></span>
  <span data-ttu-id="e5b49-103">Le gestionnaire de connexions SAP BW est le composant de gestionnaire de connexions de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e5b49-103">The SAP BW connection manager is the connection manager component of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="e5b49-104">Ainsi, le gestionnaire de connexions SAP BW fournit la connectivité à un système SAP Netweaver BW version 7 dont ont besoin les composants source et de destination de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e5b49-104">Thus, the SAP BW connection manager provides the connectivity to an SAP Netweaver BW version 7 system that the source and destination components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW need.</span></span> <span data-ttu-id="e5b49-105">(La source et la destination SAP BW qui font partie du package [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW sont les seuls composants [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] qui utilisent le gestionnaire de connexions SAP BW.)</span><span class="sxs-lookup"><span data-stu-id="e5b49-105">(The SAP BW source and destination that are part of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW package are the only [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components that use the SAP BW connection manager.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e5b49-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="e5b49-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="e5b49-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="e5b49-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="e5b49-108">Lorsque vous ajoutez un gestionnaire de connexions SAP BW à un package, la propriété `ConnectionManagerType` du gestionnaire de connexions est définie sur `SAPBI`.</span><span class="sxs-lookup"><span data-stu-id="e5b49-108">When you add an SAP BW connection manager to a package, the `ConnectionManagerType` property of the connection manager is set to `SAPBI`.</span></span>  
  
## <a name="configuring-the-sap-bw-connection-manager"></a><span data-ttu-id="e5b49-109">Configuration du gestionnaire de connexions SAP BW</span><span class="sxs-lookup"><span data-stu-id="e5b49-109">Configuring the SAP BW Connection Manager</span></span>  
 <span data-ttu-id="e5b49-110">Vous pouvez configurer le gestionnaire de connexions SAP BW de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="e5b49-110">You can configure the SAP BW connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="e5b49-111">Fournissez le client, le nom d'utilisateur, le mot de passe et la langue pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="e5b49-111">Provide the client, user name, password, and language for the connection.</span></span>  
  
-   <span data-ttu-id="e5b49-112">Déterminez si la connexion doit être établie à un serveur d'applications unique ou à un groupe de serveurs à charge équilibrée.</span><span class="sxs-lookup"><span data-stu-id="e5b49-112">Choose whether to connect to a single application server or to a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="e5b49-113">Fournissez le numéro d'hôte et du système pour un serveur d'applications unique, ou fournissez le serveur de messages, le groupe et le SID pour un groupe de serveurs à charge équilibrée.</span><span class="sxs-lookup"><span data-stu-id="e5b49-113">Provide the host and system number for a single application server, or provide the message server, group, and SID for a group of load-balanced servers.</span></span>  
  
-   <span data-ttu-id="e5b49-114">Activez la journalisation personnalisée des appels de fonction RFC pour les composants de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e5b49-114">Enable custom logging of RFC function calls for the components of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span> <span data-ttu-id="e5b49-115">(Cette journalisation diffère de la journalisation facultative que vous pouvez activer sur les packages [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .) Pour activer la journalisation des appels de fonction RFC, spécifiez un répertoire dans lequel stocker les fichiers journaux qui sont créés avant et après chaque appel de fonction RFC.</span><span class="sxs-lookup"><span data-stu-id="e5b49-115">(This logging is separate from the optional logging that you can enable on [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.) To enable logging of RFC function calls, you specify a directory in which to store the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="e5b49-116">(Cette fonctionnalité de journalisation crée un grand nombre de fichiers journaux au format XML.</span><span class="sxs-lookup"><span data-stu-id="e5b49-116">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="e5b49-117">Comme ces fichiers journaux contiennent également toutes les lignes de données qui sont transférées, ils peuvent occuper beaucoup d'espace sur le disque.) Si vous ne sélectionnez pas de répertoire de journal, la journalisation n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="e5b49-117">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.) If you do not select a log directory, logging is not enabled.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="e5b49-118">Si les données qui sont transférées contiennent des informations sensibles, les fichiers journaux contiendront également ces informations sensibles.</span><span class="sxs-lookup"><span data-stu-id="e5b49-118">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
-   <span data-ttu-id="e5b49-119">Utilisez les valeurs que vous avez entrées pour tester la connexion.</span><span class="sxs-lookup"><span data-stu-id="e5b49-119">Use the values that you have entered to test the connection.</span></span>  
  
 <span data-ttu-id="e5b49-120">Si vous ne connaissez pas toutes les valeurs requises pour configurer le gestionnaire de connexions, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="e5b49-120">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="e5b49-121">Pour obtenir la procédure pas à pas qui montre comment configurer et utiliser le gestionnaire de connexions, la source et la destination SAP BW, consultez le livre blanc [Utilisation de SQL Server 2008 Integration Services avec SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span><span class="sxs-lookup"><span data-stu-id="e5b49-121">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server 2008 Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkID=137090).</span></span> <span data-ttu-id="e5b49-122">Ce livre blanc explique également comment configurer les objets nécessaires dans SAP BW.</span><span class="sxs-lookup"><span data-stu-id="e5b49-122">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
### <a name="using-the-ssis-designer-to-configure-the-source"></a><span data-ttu-id="e5b49-123">Utilisation du concepteur SSIS pour configurer la source</span><span class="sxs-lookup"><span data-stu-id="e5b49-123">Using the SSIS Designer to Configure the Source</span></span>  
 <span data-ttu-id="e5b49-124">Pour plus d'informations sur les propriétés du gestionnaire de connexions SAP BW que vous pouvez définir dans le concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] , cliquez sur la rubrique suivante :</span><span class="sxs-lookup"><span data-stu-id="e5b49-124">For more information about the properties of the SAP BW connection manager that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click the following topic:</span></span>  
  
-   [<span data-ttu-id="e5b49-125">Éditeur du gestionnaire de connexions SAP BW</span><span class="sxs-lookup"><span data-stu-id="e5b49-125">SAP BW Connection Manager Editor</span></span>](../sap-bw-connection-manager-editor.md)  
  
## <a name="see-also"></a><span data-ttu-id="e5b49-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e5b49-126">See Also</span></span>  
 [<span data-ttu-id="e5b49-127">Composants Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="e5b49-127">Microsoft Connector 1.1 for SAP BW Components</span></span>](../microsoft-connector-for-sap-bw-components.md)  
  
  
