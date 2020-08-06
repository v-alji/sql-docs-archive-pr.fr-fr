---
title: Configurer un serveur de rapports pour l’administration à distance | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Reporting Services Configuration tool
- WMI provider [Reporting Services], remote configuration
- configuration management [WMI]
- report servers [Reporting Services], configuring
- remote server administration [Reporting Services]
ms.assetid: 8c7f145f-3ac2-4203-8cd6-2a4694395d09
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c34db5299fc1b82a7896a41519e55466c3b3b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611558"
---
# <a name="configure-a-report-server-for-remote-administration"></a><span data-ttu-id="ffdb1-102">Configurer un serveur de rapports pour l'administration à distance</span><span class="sxs-lookup"><span data-stu-id="ffdb1-102">Configure a Report Server for Remote Administration</span></span>
  <span data-ttu-id="ffdb1-103">Dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], vous pouvez configurer des instances de serveur de rapports localement ou à distance.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-103">In [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you can configure report server instances locally or remotely.</span></span> <span data-ttu-id="ffdb1-104">Pour configurer une instance de serveur de rapports à distance, vous pouvez faire appel à l’outil de configuration de Reporting Services ou bien écrire un code personnalisé qui utilise le fournisseur WMI (Windows Management Instrumentation) de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffdb1-104">To configure a remote report server instance, you can use the Reporting Services Configuration tool or write custom code that uses the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] Windows Management Instrumentation (WMI) provider.</span></span> <span data-ttu-id="ffdb1-105">L'outil de configuration de Reporting Services offre une interface graphique avec le fournisseur WMI pour vous permettre de configurer un serveur de rapports sans avoir à écrire du code.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-105">The Reporting Services Configuration tool provides a graphical interface to the WMI provider so that you can configure a report server without having to write code.</span></span> <span data-ttu-id="ffdb1-106">Lorsque vous démarrez l'outil, vous pouvez spécifier un serveur distant auquel vous connecter.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-106">When you start the tool, you can specify a remote server to connect to.</span></span>  
  
 <span data-ttu-id="ffdb1-107">Avant de pouvoir utiliser l'outil pour configurer un serveur de rapports distant, vous devez suivre les instructions de cette rubrique pour activer les ports du Pare-feu Windows, les connexions à distance et les demandes WMI distantes.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-107">Before you can use the tool to configure a remote report server, you must follow the instructions in this topic to enable ports in Windows Firewall, enable remote connections, and enable remote WMI requests.</span></span>  
  
 <span data-ttu-id="ffdb1-108">Une configuration appropriée vous aide à éviter l'erreur suivante :</span><span class="sxs-lookup"><span data-stu-id="ffdb1-108">Proper configuration helps you avoid the following error:</span></span>  
  
 `The machine could not be found.`  
  
 `"The RPC server is unavailable. (Exception from HRESULT: 0x800706BA)".`  
  
## <a name="prerequisites"></a><span data-ttu-id="ffdb1-109">Conditions préalables requises</span><span class="sxs-lookup"><span data-stu-id="ffdb1-109">Prerequisites</span></span>  
 <span data-ttu-id="ffdb1-110">Pour cela, vous devez ouvrir une session localement et être membre du groupe Administrateurs local.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-110">To modify firewall settings, you must be logged on locally and you must be a member of the local Administrators group.</span></span> <span data-ttu-id="ffdb1-111">Vous ne pouvez pas modifier les paramètres du pare-feu Windows d'un ordinateur distant sur une connexion distante.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-111">You cannot modify the Windows firewall settings of a remote computer over a remote connection.</span></span>  
  
 <span data-ttu-id="ffdb1-112">Si vous souhaitez activer l'administration à distance pour un utilisateur non-administrateur, vous devez accorder des autorisations d'activation à distance DCOM (Distributed Component Object Model) au compte.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-112">If you want to enable remote administration for a non-administrator user, you must grant the account Distributed Component Object Model (DCOM) Remote Activation permissions.</span></span> <span data-ttu-id="ffdb1-113">Les instructions de configuration du serveur pour un accès non-administrateur sont fournies dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-113">Instructions for configuring the server for non-administrator access are provided in this topic.</span></span>  
  
 <span data-ttu-id="ffdb1-114">Certaines organisations disposent de stratégies de groupe qui empêchent l'administration serveur à distance pour certains systèmes d'exploitation ou certains utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-114">Some organizations have group policies that prevent remote server administration for certain operating systems or users.</span></span> <span data-ttu-id="ffdb1-115">Avant de commencer à modifier les paramètres du pare-feu, vérifiez auprès de votre administrateur réseau si des restrictions s'appliquent dans le cadre de l'administration à distance.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-115">Before you begin modifying firewall settings, check with your network administrator to verify whether there are restrictions on remote administration.</span></span>  
  
 <span data-ttu-id="ffdb1-116">Pour plus d'informations, consultez [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) dans la documentation du kit de développement Platform SDK sur MSDN.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-116">For more information, see [Connecting Through Windows Firewall](https://go.microsoft.com/fwlink/?LinkId=63615) in the Platform SDK documentation on MSDN.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="ffdb1-117">Tâches</span><span class="sxs-lookup"><span data-stu-id="ffdb1-117">Tasks</span></span>  
 <span data-ttu-id="ffdb1-118">Les tâches qui activent la configuration de serveur de rapports à distance incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="ffdb1-118">Tasks that enable remote report server configuration include the following:</span></span>  
  
-   <span data-ttu-id="ffdb1-119">Activer les ports du Pare-feu Windows afin d'autoriser les demandes sur les ports utilisés par le serveur de rapports et par l'instance du moteur de base de données SQL Server.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-119">Enable ports in Windows Firewall to allow requests on ports used by the report server and by the SQL Server Database Engine instance.</span></span>  
  
-   <span data-ttu-id="ffdb1-120">Autoriser les connexions distantes à l'instance du moteur de base de données qui héberge la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-120">Enable remote connections to the instance of the Database Engine instance that hosts the report server database.</span></span> <span data-ttu-id="ffdb1-121">Une connexion distante est nécessaire pour la configuration de la connexion à la base de données du serveur de rapports et la gestion des clés de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-121">A remote connection is necessary for configuring the report server database connection and managing the encryption keys.</span></span>  
  
-   <span data-ttu-id="ffdb1-122">Activer les demandes WMI distantes pour franchir le Pare-feu [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-122">Enable remote WMI requests to pass through the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows firewall.</span></span>  
  
-   <span data-ttu-id="ffdb1-123">Si vous configurez un serveur de rapports distant pour l'administration par un utilisateur non-administrateur, vous devez définir les autorisations DCOM pour activer l'accès WMI distant à un compte d'utilisateur Windows standard.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-123">If you are configuring a remote report server for administration by a non-administrative user, you must set DCOM permissions to enable remote WMI access to a standard Windows user account.</span></span> <span data-ttu-id="ffdb1-124">Du fait que WMI utilise DCOM en tant que moyen de transport pour les appels distants, vous devez définir les autorisations DCOM afin que les utilisateurs non connectés en tant qu'administrateur local puissent configurer le serveur.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-124">Because WMI uses DCOM as transport for remote calls, you must set the DCOM permissions so that users who are not logged on as the local administrator can configure the server.</span></span>  
  
-   <span data-ttu-id="ffdb1-125">Si vous configurez un serveur de rapports distant pour l'administration par un utilisateur non-administrateur, vous devez également définir les autorisations WMI sur l'espace de noms WMI du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-125">If you are configuring a remote report server for administration by a non-administrative user, you must also set WMI permissions on the report server WMI namespace.</span></span> <span data-ttu-id="ffdb1-126">Par défaut, tous les membres du groupe Administrateurs local ont accès à l'espace de noms WMI du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-126">By default, all members of the local Administrator group have access to the report server WMI namespace.</span></span> <span data-ttu-id="ffdb1-127">Pour accorder un droit d'accès aux personnes qui ne sont pas administrateurs, vous devez définir des autorisations.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-127">If you want to grant access to non-administrators, you must set permissions.</span></span>  
  
 <span data-ttu-id="ffdb1-128">Les instructions relatives à l'exécution de ces tâches sont fournies dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-128">Instructions on how to perform these tasks are provided in this topic.</span></span>  
  
### <a name="to-open-ports-in-windows-firewall"></a><span data-ttu-id="ffdb1-129">Pour ouvrir les ports du Pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="ffdb1-129">To open ports in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="ffdb1-130">[Configurez un pare-feu Windows pour l’accès moteur de base de données](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span><span class="sxs-lookup"><span data-stu-id="ffdb1-130">[Configure a Windows Firewall for Database Engine Access](../../database-engine/configure-windows/configure-a-windows-firewall-for-database-engine-access.md).</span></span>  
  
2.  <span data-ttu-id="ffdb1-131">[Configurer un pare-feu pour l’accès au serveur de rapports](configure-a-firewall-for-report-server-access.md).</span><span class="sxs-lookup"><span data-stu-id="ffdb1-131">[Configure a Firewall for Report Server Access](configure-a-firewall-for-report-server-access.md).</span></span>  
  
### <a name="to-configure-remote-connections-to-the-report-server-database"></a><span data-ttu-id="ffdb1-132">Pour configurer les connexions distantes à la base de données du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="ffdb1-132">To configure remote connections to the report server database</span></span>  
  
1.  <span data-ttu-id="ffdb1-133">Cliquez sur **Démarrer**, pointez sur **Programmes**, sur [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-133">Click **Start**, point to **Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="ffdb1-134">Dans le volet gauche, développez **Configuration du réseau SQL Server**, puis cliquez sur **Protocoles** pour l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ffdb1-134">In the left pane, expand **SQL Server Network Configuration**, and then click **Protocols** for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="ffdb1-135">Dans le volet d’informations, activez les protocoles TCP/IP et Canaux nommés, puis redémarrez le service [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ffdb1-135">In the details pane, enable the TCP/IP and Named Pipes protocols, and then restart the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
### <a name="to-enable-remote-administration-in-windows-firewall"></a><span data-ttu-id="ffdb1-136">Pour activer l'administration à distance dans le pare-feu Windows</span><span class="sxs-lookup"><span data-stu-id="ffdb1-136">To enable remote administration in Windows Firewall</span></span>  
  
1.  <span data-ttu-id="ffdb1-137">Ouvrez une session en tant qu'administrateur local sur l'ordinateur où vous souhaitez activer l'administration à distance.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-137">Log on as a local administrator to the computer for which you want to enable remote administration.</span></span>  
  
2.  <span data-ttu-id="ffdb1-138">Si le serveur de rapports s’exécute sous Windows Vista, cliquez avec le bouton droit sur **invite de commandes** et sélectionnez **exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-138">If the report server is running on Windows Vista, right-click **Command Prompt** and select **Run as administrator**.</span></span> <span data-ttu-id="ffdb1-139">Pour d'autres systèmes d'exploitation, ouvrez une fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-139">For other operating systems, open a command prompt window.</span></span>  
  
3.  <span data-ttu-id="ffdb1-140">Exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="ffdb1-140">Run the following command:</span></span>  
  
    ```  
    netsh.exe firewall set service type=REMOTEADMIN mode=ENABLE scope=ALL  
    ```  
  
     <span data-ttu-id="ffdb1-141">Vous pouvez spécifier différentes options pour l'étendue.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-141">You can specify different options for Scope.</span></span> <span data-ttu-id="ffdb1-142">Pour plus d'informations, consultez la documentation produit du pare-feu Windows.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-142">For more information, see the Windows Firewall product documentation.</span></span>  
  
4.  <span data-ttu-id="ffdb1-143">Vérifiez que l'administration à distance est activée.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-143">Verify that remote administration is enabled.</span></span> <span data-ttu-id="ffdb1-144">Vous pouvez exécuter la commande suivante pour afficher l'état :</span><span class="sxs-lookup"><span data-stu-id="ffdb1-144">You can run the following command to show the status:</span></span>  
  
    ```  
    netsh.exe firewall show state  
    ```  
  
5.  <span data-ttu-id="ffdb1-145">Redémarrez l'ordinateur.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-145">Reboot the computer.</span></span>  
  
### <a name="to-set-dcom-permissions-to-enable-remote-wmi-access-for-non-administrators"></a><span data-ttu-id="ffdb1-146">Pour définir les autorisations DCOM en vue d'activer l'accès WMI à distance pour les non-administrateurs</span><span class="sxs-lookup"><span data-stu-id="ffdb1-146">To set DCOM permissions to enable remote WMI access for non-administrators</span></span>  
  
1.  <span data-ttu-id="ffdb1-147">Dans le menu Démarrer, pointez sur **Outils d'administration**, puis cliquez sur **Services de composants**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-147">On the Start menu, point to **Administrative Tools**, click **Component Services**.</span></span>  
  
     <span data-ttu-id="ffdb1-148">Pour Windows Vista, dans le menu Démarrer, cliquez sur **tous les programmes**, sur **exécuter**, puis sur entrée `mmc comexp.msc` .</span><span class="sxs-lookup"><span data-stu-id="ffdb1-148">For Windows Vista, on the Start menu, click **All Programs**, click **Run**, and then enter `mmc comexp.msc`.</span></span>  
  
2.  <span data-ttu-id="ffdb1-149">Ouvrez le dossier Services de composants.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-149">Open the Component Services folder.</span></span>  
  
3.  <span data-ttu-id="ffdb1-150">Ouvrez le dossier Ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-150">Open the Computers folder.</span></span>  
  
4.  <span data-ttu-id="ffdb1-151">Sélectionnez Poste de travail.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-151">Select My Computer.</span></span>  
  
5.  <span data-ttu-id="ffdb1-152">Dans le menu **Action** , sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-152">On the **Action** menu, and select **Properties**.</span></span>  
  
6.  <span data-ttu-id="ffdb1-153">Cliquez sur **Sécurité COM**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-153">Click **COM Security**.</span></span>  
  
7.  <span data-ttu-id="ffdb1-154">Sous **Autorisations d'exécution et d'activation**, cliquez sur **Modifier les limites**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-154">In **Launch and Activation Permissions**, click **Edit Limits**.</span></span>  
  
8.  <span data-ttu-id="ffdb1-155">Si votre nom n'apparaît pas dans la boîte de dialogue **Autorisation d'exécution**, cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-155">If you do not see your name in **Launch Permission**, click **Add**.</span></span>  
  
9. <span data-ttu-id="ffdb1-156">Tapez le nom de votre compte d'utilisateur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-156">Type the name of your user account, and then click **OK**.</span></span>  
  
10. <span data-ttu-id="ffdb1-157">Dans \*\*autorisations pour \<User or Group> \*\*, dans la colonne **autoriser** , sélectionnez **exécution à distance** et **activation à distance**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-157">In **Permissions for \<User or Group>**, in the **Allow** column, select **Remote Launch** and **Remote Activation**, and then click **OK**.</span></span>  
  
### <a name="to-set-permissions-on-the-report-server-wmi-namespace-for-non-administrators"></a><span data-ttu-id="ffdb1-158">Pour définir les autorisations sur l'espace de noms WMI du rapport de serveurs pour les non-administrateurs</span><span class="sxs-lookup"><span data-stu-id="ffdb1-158">To set permissions on the report server WMI namespace for non-administrators</span></span>  
  
1.  <span data-ttu-id="ffdb1-159">Dans le menu Démarrer, pointez sur **Outils d'administration**, puis cliquez sur **Gestion de l'ordinateur**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-159">On the Start menu, point to **Administrative Tools**, click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="ffdb1-160">Ouvrez le dossier Services et applications.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-160">Open the Services and Applications folder.</span></span>  
  
3.  <span data-ttu-id="ffdb1-161">Cliquez avec le bouton droit sur **Contrôle WMI**, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-161">Right-click **WMI Control**, and select **Properties**.</span></span>  
  
4.  <span data-ttu-id="ffdb1-162">Cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-162">Click **Security**.</span></span>  
  
5.  <span data-ttu-id="ffdb1-163">Ouvrez le dossier Root.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-163">Open the Root folder.</span></span>  
  
6.  <span data-ttu-id="ffdb1-164">Ouvrez le dossier Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-164">Open the Microsoft folder.</span></span>  
  
7.  <span data-ttu-id="ffdb1-165">Ouvrez le dossier SQLServer.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-165">Open the SQLServer folder.</span></span>  
  
8.  <span data-ttu-id="ffdb1-166">Ouvrez le dossier ReportServer.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-166">Open the ReportServer folder.</span></span>  
  
9. <span data-ttu-id="ffdb1-167">Ouvrez le dossier de l'instance.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-167">Open instance folder.</span></span> <span data-ttu-id="ffdb1-168">Si vous avez installé l'instance par défaut, le dossier est MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-168">If you installed the default instance, the folder is MSSQLSERVER.</span></span>  
  
10. <span data-ttu-id="ffdb1-169">Ouvrez le dossier v10.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-169">Open the v10 folder.</span></span>  
  
11. <span data-ttu-id="ffdb1-170">Sélectionnez le dossier Admin, puis cliquez sur **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-170">Select the Admin folder, and then click **Security**.</span></span>  
  
12. <span data-ttu-id="ffdb1-171">Cliquez sur **Ajouter**, puis tapez le compte d'utilisateur que vous utiliserez pour gérer le serveur.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-171">Click **Add**, and then type the user account you will use to manage the server.</span></span>  
  
13. <span data-ttu-id="ffdb1-172">Dans la colonne **Autoriser** , sélectionnez **Activer le compte**, **Appel à distance autorisé**et **Sécurité de lecture**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-172">In the **Allow** column, select **Enable Account**, **Remote Enable**, and **Read Security**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffdb1-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ffdb1-173">See Also</span></span>  
 [<span data-ttu-id="ffdb1-174">Gestionnaire de configuration de Reporting Services &#40;mode natif&#41;</span><span class="sxs-lookup"><span data-stu-id="ffdb1-174">Reporting Services Configuration Manager &#40;Native Mode&#41;</span></span>](../../sql-server/install/reporting-services-configuration-manager-native-mode.md)  
  
  
