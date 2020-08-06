---
title: 'Procédure : exécuter l’Assistant analyse du conseiller de mise à niveau | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Analysis Wizard
ms.assetid: d7d2a1e2-1179-4c05-9b0f-555b04dd1199
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7c3e5e8a52c3b166b076aedb122e68f860037edf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613797"
---
# <a name="how-to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="fede8-102">Procédure : exécuter l’Assistant Analyse du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fede8-102">How to: Run the Upgrade Advisor Analysis Wizard</span></span>
  <span data-ttu-id="fede8-103">Vous démarrez l'Assistant Analyse du Conseiller de mise à niveau à partir de la page de démarrage du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fede8-103">You start the Upgrade Advisor Analysis Wizard from the Upgrade Advisor start page.</span></span> <span data-ttu-id="fede8-104">Cette rubrique décrit comment exécuter l'Assistant Analyse du Conseiller de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fede8-104">This topic describes how to run the Upgrade Advisor Analysis Wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fede8-105">Lorsque vous exécutez l'Assistant Analyse du Conseiller de mise à niveau, le Conseiller de mise à niveau enregistre les rapports dans le dossier des rapports par défaut.</span><span class="sxs-lookup"><span data-stu-id="fede8-105">When you run the Upgrade Advisor Analysis Wizard, Upgrade Advisor saves the reports in the default report folder.</span></span> <span data-ttu-id="fede8-106">Toutefois, la visionneuse de rapports affiche uniquement les cinq derniers rapports enregistrés.</span><span class="sxs-lookup"><span data-stu-id="fede8-106">However, the report viewer displays only the five latest saved reports.</span></span> <span data-ttu-id="fede8-107">L’emplacement par défaut des rapports est My documents \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span><span class="sxs-lookup"><span data-stu-id="fede8-107">The default location for the reports is My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span></span>  
  
### <a name="to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="fede8-108">Pour exécuter l’Assistant analyse du conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fede8-108">To run the Upgrade Advisor Analysis Wizard</span></span>  
  
1.  <span data-ttu-id="fede8-109">Sur la page de démarrage du conseiller de mise à niveau, cliquez sur **lancer l’Assistant analyse du conseiller de mise à niveau**.</span><span class="sxs-lookup"><span data-stu-id="fede8-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Analysis Wizard**.</span></span>  
  
2.  <span data-ttu-id="fede8-110">Dans la page \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] composants\*\* , entrez le nom du serveur à analyser dans la zone **nom du serveur** , puis cliquez sur **détecter**.</span><span class="sxs-lookup"><span data-stu-id="fede8-110">On the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components** page, enter the name of the server to scan in the **Server name** box, and then click **Detect**.</span></span> <span data-ttu-id="fede8-111">Utilisez les indications suivantes pour le nom du serveur :</span><span class="sxs-lookup"><span data-stu-id="fede8-111">Use the following guidelines for the server name:</span></span>  
  
    -   <span data-ttu-id="fede8-112">Pour analyser les instances non cluster, entrez le nom de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="fede8-112">To scan nonclustered instances, enter the computer name.</span></span>  
  
    -   <span data-ttu-id="fede8-113">Pour analyser les instances cluster, entrez le nom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] virtuel.</span><span class="sxs-lookup"><span data-stu-id="fede8-113">To scan clustered instances, enter the virtual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name.</span></span>  
  
    -   <span data-ttu-id="fede8-114">Pour analyser les composants non-cluster installés sur un nœud d’un cluster, entrez le nom du nœud.</span><span class="sxs-lookup"><span data-stu-id="fede8-114">To scan nonclustered components that are installed on a node of a cluster, enter the node name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="fede8-115">Le Conseiller de mise à niveau ne prend pas en charge la connexion à une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui n'est pas définie pour utiliser le port standard (1433) pour les connexions clientes.</span><span class="sxs-lookup"><span data-stu-id="fede8-115">Upgrade Advisor does not support connecting to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is not set to use the standard port (1433) for client connections.</span></span> <span data-ttu-id="fede8-116">Si vous voulez vous connecter à une instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui n'utilise pas le port standard (1433), créez un alias à l'aide de l'adresse IP et du port.</span><span class="sxs-lookup"><span data-stu-id="fede8-116">If you want to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that does not use the standard port (1433), create an alias using the IP address and the port.</span></span> <span data-ttu-id="fede8-117">Pour plus d’informations sur la configuration des protocoles clients et la création d’un alias pour les [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, consultez [configurer des protocoles clients](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="fede8-117">For more information about configuring client protocols and creating an alias for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
    >   
    >  <span data-ttu-id="fede8-118">Si vous n’avez pas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installé sur l’ordinateur sur lequel vous exécutez le conseiller de mise à niveau, cliquez sur **Démarrer**, puis sur exécuter `cliconfg` .</span><span class="sxs-lookup"><span data-stu-id="fede8-118">If you do not have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer on which you are running Upgrade Advisor, click **Start**, and then run  `cliconfg`.</span></span> <span data-ttu-id="fede8-119">La boîte de dialogue \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilitaire réseau client\*\* s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="fede8-119">This opens the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility** dialog box.</span></span> <span data-ttu-id="fede8-120">Utilisez l’onglet **alias** pour créer l’alias.</span><span class="sxs-lookup"><span data-stu-id="fede8-120">Use the **Alias** tab to create the alias.</span></span>  
  
3.  <span data-ttu-id="fede8-121">Passez en revue la liste des composants détectés, modifiez les sélections si nécessaire, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fede8-121">Review the list of components detected, modify the selections as necessary, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="fede8-122">Sur la page **paramètres de connexion** , sélectionnez l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que vous souhaitez analyser, sélectionnez la méthode d’authentification et, si nécessaire, entrez les informations de nom d’utilisateur et de mot de passe, puis cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="fede8-122">On the **Connection Parameters** page, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you want to scan, select the authentication method and, if necessary, enter user name and password information, and then click **Next**.</span></span>  
  
     <span data-ttu-id="fede8-123">MSSQLSERVER est le nom de l'instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="fede8-123">The default instance name is MSSQLSERVER.</span></span>  
  
5.  <span data-ttu-id="fede8-124">Pour les composants sélectionnés, entrez les informations demandées.</span><span class="sxs-lookup"><span data-stu-id="fede8-124">For selected components, enter the requested information.</span></span> <span data-ttu-id="fede8-125">Pour plus d’informations sur les boîtes de dialogue individuelles, consultez Référence de l' [interface utilisateur du conseiller de mise à niveau](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="fede8-125">For more information about individual dialog boxes, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
6.  <span data-ttu-id="fede8-126">Sur la page **confirmer le paramètre du conseiller de mise à niveau** , passez en revue les informations que vous avez entrées.</span><span class="sxs-lookup"><span data-stu-id="fede8-126">On the **Confirm Upgrade Advisor Setting** page, review the information that you entered.</span></span> <span data-ttu-id="fede8-127">Vous pouvez sélectionner **Envoyer des rapports [!INCLUDE[msCoName](../../includes/msconame-md.md)] à** si vous souhaitez envoyer votre rapport de mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="fede8-127">You can select **Send reports to [!INCLUDE[msCoName](../../includes/msconame-md.md)]** if you want to submit your upgrade report.</span></span> <span data-ttu-id="fede8-128">Vous pouvez également examiner la politique de confidentialité.</span><span class="sxs-lookup"><span data-stu-id="fede8-128">You can also review the privacy policy.</span></span>  
  
7.  <span data-ttu-id="fede8-129">Cliquez sur **exécuter** pour analyser l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="fede8-129">Click **Run** to analyze the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
8.  <span data-ttu-id="fede8-130">Une fois l’analyse terminée, cliquez sur **lancer le rapport** pour afficher les problèmes de mise à niveau détectés.</span><span class="sxs-lookup"><span data-stu-id="fede8-130">When the analysis is finished, click **Launch Report** to view the detected upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fede8-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fede8-131">See Also</span></span>  
 <span data-ttu-id="fede8-132">[Procédure : lancer le conseiller de mise à niveau](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="fede8-132">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="fede8-133">[Exécution du conseiller de mise à niveau &#40;de l’interface utilisateur&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="fede8-133">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 [<span data-ttu-id="fede8-134">Utilisation du Conseiller de mise à niveau</span><span class="sxs-lookup"><span data-stu-id="fede8-134">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
