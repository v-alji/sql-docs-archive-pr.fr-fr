---
title: Éditeur du gestionnaire de connexions SAP BW | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ec970319-e749-4753-8675-9cf76ed99669
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 527af979fc9c92062f24e1fe161b93e88ed4ab4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698435"
---
# <a name="sap-bw-connection-manager-editor"></a><span data-ttu-id="558da-102">Éditeur du gestionnaire de connexions SAP BW</span><span class="sxs-lookup"><span data-stu-id="558da-102">SAP BW Connection Manager Editor</span></span>
  <span data-ttu-id="558da-103">Utilisez l' **Éditeur du gestionnaire de connexions SAP BW** pour spécifier les propriétés à utiliser pour se connecter à un système SAP Netweaver BW version 7.</span><span class="sxs-lookup"><span data-stu-id="558da-103">Use the **SAP BW Connection Manager Editor** to specify the properties to use to connect to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="558da-104">Le gestionnaire de connexions SAP BW fournit la connectivité à un système SAP Netweaver BW version 7 en vue d'une utilisation par la source ou la destination SAP BW.</span><span class="sxs-lookup"><span data-stu-id="558da-104">The SAP BW connection manager provides connectivity to an SAP Netweaver BW 7 system for use by the SAP BW source or destination.</span></span> <span data-ttu-id="558da-105">Pour en savoir plus sur le gestionnaire de connexions SAP BW de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW, consultez [Gestionnaire de connexions SAP BW](connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="558da-105">To learn more about the SAP BW connection manager of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Connection Manager](connection-manager/sap-bw-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="558da-106">La documentation de Microsoft Connector 1.1 pour SAP BW suppose que vous êtes familiarisé avec l'environnement SAP Netweaver BW.</span><span class="sxs-lookup"><span data-stu-id="558da-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="558da-107">Pour plus d'informations sur SAP Netweaver BW, ou sur la configuration des objets et des processus SAP Netweaver BW objets, consultez la documentation SAP.</span><span class="sxs-lookup"><span data-stu-id="558da-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="558da-108">**Pour ouvrir l'Éditeur du gestionnaire de connexions SAP BW**</span><span class="sxs-lookup"><span data-stu-id="558da-108">**To open the SAP BW Connection Manager Editor**</span></span>  
  
1.  <span data-ttu-id="558da-109">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], ouvrez le package [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] qui contient le gestionnaire de connexions SAP BW.</span><span class="sxs-lookup"><span data-stu-id="558da-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that contains the SAP BW connection manager.</span></span>  
  
2.  <span data-ttu-id="558da-110">Dans la zone Gestionnaires de connexions de l'onglet **Flux de contrôle** , procédez de l'une des façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="558da-110">In the Connection Managers area on the **Control Flow** tab, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="558da-111">Double-cliquez sur le gestionnaire de connexions SAP BW.</span><span class="sxs-lookup"><span data-stu-id="558da-111">Double-click the SAP BW connection manager.</span></span>  
  
         <span data-ttu-id="558da-112">-ou-</span><span class="sxs-lookup"><span data-stu-id="558da-112">-or-</span></span>  
  
    -   <span data-ttu-id="558da-113">Cliquez avec le bouton droit sur le gestionnaire de connexions SAP BW, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="558da-113">Right-click the SAP BW connection manager, and then select **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="558da-114">Options</span><span class="sxs-lookup"><span data-stu-id="558da-114">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="558da-115">Si vous ne connaissez pas toutes les valeurs requises pour configurer le gestionnaire de connexions, adressez-vous à votre administrateur SAP.</span><span class="sxs-lookup"><span data-stu-id="558da-115">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="558da-116">**Client**</span><span class="sxs-lookup"><span data-stu-id="558da-116">**Client**</span></span>  
 <span data-ttu-id="558da-117">Spécifiez le numéro de client du système.</span><span class="sxs-lookup"><span data-stu-id="558da-117">Specify the client number of the system.</span></span>  
  
 <span data-ttu-id="558da-118">**Langage**</span><span class="sxs-lookup"><span data-stu-id="558da-118">**Language**</span></span>  
 <span data-ttu-id="558da-119">Spécifiez la langue utilisée par le système.</span><span class="sxs-lookup"><span data-stu-id="558da-119">Specify the language that the system uses.</span></span> <span data-ttu-id="558da-120">Par exemple, spécifiez **FR** pour le français.</span><span class="sxs-lookup"><span data-stu-id="558da-120">For example, specify **EN** for English.</span></span>  
  
 <span data-ttu-id="558da-121">**Nom d'utilisateur**</span><span class="sxs-lookup"><span data-stu-id="558da-121">**User name**</span></span>  
 <span data-ttu-id="558da-122">Spécifiez le nom d'utilisateur qui sera utilisé pour se connecter au système.</span><span class="sxs-lookup"><span data-stu-id="558da-122">Specify the user name that will be used to connect to the system.</span></span>  
  
 <span data-ttu-id="558da-123">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="558da-123">**Password**</span></span>  
 <span data-ttu-id="558da-124">Spécifiez le mot de passe qui sera utilisé avec le nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="558da-124">Specify the password that will be used with the user name.</span></span>  
  
 <span data-ttu-id="558da-125">**Utiliser le serveur d'applications unique**</span><span class="sxs-lookup"><span data-stu-id="558da-125">**Use single application server**</span></span>  
 <span data-ttu-id="558da-126">Connectez-vous à un serveur d'applications unique.</span><span class="sxs-lookup"><span data-stu-id="558da-126">Connect to a single application server.</span></span>  
  
 <span data-ttu-id="558da-127">Pour vous connecter à un groupe de serveurs à charge équilibrée, utilisez plutôt l’option **Utiliser l’équilibrage de charge** .</span><span class="sxs-lookup"><span data-stu-id="558da-127">To connect to a group of load-balanced servers, use the **Use load balancing** option instead.</span></span>  
  
 <span data-ttu-id="558da-128">**Hôte**</span><span class="sxs-lookup"><span data-stu-id="558da-128">**Host**</span></span>  
 <span data-ttu-id="558da-129">Si vous vous connectez à un serveur d'applications unique, spécifiez le nom d'hôte.</span><span class="sxs-lookup"><span data-stu-id="558da-129">If connecting to a single application server, specify the host name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="558da-130"> Cette option est disponible uniquement si vous avez sélectionné l'option **Utiliser le serveur d'applications unique** .</span><span class="sxs-lookup"><span data-stu-id="558da-130">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="558da-131">**Numéro système**</span><span class="sxs-lookup"><span data-stu-id="558da-131">**System number**</span></span>  
 <span data-ttu-id="558da-132">Si vous vous connectez à un serveur d'applications unique, spécifiez le numéro du système.</span><span class="sxs-lookup"><span data-stu-id="558da-132">If connecting to a single application server, specify the system number.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="558da-133"> Cette option est disponible uniquement si vous avez sélectionné l'option **Utiliser le serveur d'applications unique** .</span><span class="sxs-lookup"><span data-stu-id="558da-133">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="558da-134">**Utiliser l’équilibrage de charge**</span><span class="sxs-lookup"><span data-stu-id="558da-134">**Use load balancing**</span></span>  
 <span data-ttu-id="558da-135">Connectez-vous à un groupe de serveurs à charge équilibrée.</span><span class="sxs-lookup"><span data-stu-id="558da-135">Connect to a group of load-balanced servers.</span></span>  
  
 <span data-ttu-id="558da-136">Pour vous connecter à un serveur d'applications unique, utilisez plutôt l'option **Utiliser le serveur d'applications unique** .</span><span class="sxs-lookup"><span data-stu-id="558da-136">To connect to a single application server, use the **Use single application server** option instead.</span></span>  
  
 <span data-ttu-id="558da-137">**Serveur de messagerie**</span><span class="sxs-lookup"><span data-stu-id="558da-137">**Message server**</span></span>  
 <span data-ttu-id="558da-138">Si vous vous connectez à un groupe de serveurs à charge équilibrée, spécifiez le nom du serveur de messages.</span><span class="sxs-lookup"><span data-stu-id="558da-138">If connecting to a group of load-balanced servers, specify the name of the message server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="558da-139"> Cette option est disponible uniquement si vous avez sélectionné l'option **Utiliser l'équilibrage de charge** .</span><span class="sxs-lookup"><span data-stu-id="558da-139">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="558da-140">**Groupe**</span><span class="sxs-lookup"><span data-stu-id="558da-140">**Group**</span></span>  
 <span data-ttu-id="558da-141">Si vous vous connectez à un groupe de serveurs à charge équilibrée, spécifiez le nom du groupe de serveurs.</span><span class="sxs-lookup"><span data-stu-id="558da-141">If connecting to a group of load-balanced servers, specify the name of the server group name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="558da-142"> Cette option est disponible uniquement si vous avez sélectionné l'option **Utiliser l'équilibrage de charge** .</span><span class="sxs-lookup"><span data-stu-id="558da-142">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="558da-143">**SID**</span><span class="sxs-lookup"><span data-stu-id="558da-143">**SID**</span></span>  
 <span data-ttu-id="558da-144">Si vous vous connectez à un groupe de serveurs à charge équilibrée, spécifiez l'ID système pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="558da-144">If connecting to a group of load-balanced servers, specify the System ID for the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="558da-145"> Cette option est disponible uniquement si vous avez sélectionné l'option **Utiliser l'équilibrage de charge** .</span><span class="sxs-lookup"><span data-stu-id="558da-145">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="558da-146">**Répertoire du journal**</span><span class="sxs-lookup"><span data-stu-id="558da-146">**Log directory**</span></span>  
 <span data-ttu-id="558da-147">Activez la journalisation des composants de [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 pour SAP BW.</span><span class="sxs-lookup"><span data-stu-id="558da-147">Enable logging for the components of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 <span data-ttu-id="558da-148">Pour activer la journalisation, spécifiez un répertoire pour les fichiers journaux qui sont créés avant et après chaque appel de fonction RFC.</span><span class="sxs-lookup"><span data-stu-id="558da-148">To enable logging, specify a directory for the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="558da-149">(Cette fonctionnalité de journalisation crée un grand nombre de fichiers journaux au format XML.</span><span class="sxs-lookup"><span data-stu-id="558da-149">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="558da-150">Comme ces fichiers journaux contiennent également toutes les lignes de données qui sont transférées, ils peuvent occuper beaucoup d'espace sur le disque.)</span><span class="sxs-lookup"><span data-stu-id="558da-150">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="558da-151">Si les données qui sont transférées contiennent des informations sensibles, les fichiers journaux contiendront également ces informations sensibles.</span><span class="sxs-lookup"><span data-stu-id="558da-151">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
 <span data-ttu-id="558da-152">Pour spécifier le répertoire du journal, vous pouvez entrer le chemin d'accès au répertoire manuellement, ou cliquer sur **Parcourir** et accéder au répertoire du journal.</span><span class="sxs-lookup"><span data-stu-id="558da-152">To specify the log directory, you can either enter the directory path manually, or click **Browse** and browse to the log directory.</span></span>  
  
 <span data-ttu-id="558da-153">Si vous ne sélectionnez pas de répertoire de journal, la journalisation n'est pas activée.</span><span class="sxs-lookup"><span data-stu-id="558da-153">If you do not select a log directory, logging is not enabled.</span></span>  
  
 <span data-ttu-id="558da-154">**Parcourir**</span><span class="sxs-lookup"><span data-stu-id="558da-154">**Browse**</span></span>  
 <span data-ttu-id="558da-155">Parcourez l'arborescence pour sélectionner un dossier pour le répertoire du journal.</span><span class="sxs-lookup"><span data-stu-id="558da-155">Browse to select a folder for the log directory.</span></span>  
  
 <span data-ttu-id="558da-156">**Tester la connexion**</span><span class="sxs-lookup"><span data-stu-id="558da-156">**Test Connection**</span></span>  
 <span data-ttu-id="558da-157">Testez la connexion à l'aide des valeurs que vous avez fournies.</span><span class="sxs-lookup"><span data-stu-id="558da-157">Test the connection using the values that you have provided.</span></span> <span data-ttu-id="558da-158">Après avoir cliqué sur **Tester la connexion**, un message apparaît et indique si la connexion a été établie ou si elle a échoué.</span><span class="sxs-lookup"><span data-stu-id="558da-158">After clicking **Test Connection**, a message box appears and indicates whether the connection succeeded or failed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558da-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="558da-159">See Also</span></span>  
 [<span data-ttu-id="558da-160">Aide (F1) sur Microsoft Connector 1.1 pour SAP BW</span><span class="sxs-lookup"><span data-stu-id="558da-160">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
  
  
