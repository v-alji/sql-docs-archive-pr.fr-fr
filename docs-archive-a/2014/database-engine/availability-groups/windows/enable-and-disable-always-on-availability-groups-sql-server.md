---
title: Activer et désactiver les groupes de disponibilité AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], server instance
- Availability Groups [SQL Server], deploying
- Availability Groups [SQL Server], disabling
- Availability Groups [SQL Server], enabling
ms.assetid: 7c326958-5ae9-4761-9c57-905972276a8f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 585f1d86d328b7c5027241310108d102b56ca327
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601702"
---
# <a name="enable-and-disable-alwayson-availability-groups-sql-server"></a><span data-ttu-id="c6b6f-102">Activer et désactiver les groupes de disponibilité AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="c6b6f-102">Enable and Disable AlwaysOn Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="c6b6f-103">L'activation de [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] est indispensable pour qu'une instance de serveur utilise des groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-103">Enabling [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is a prerequisite for a server instance to use availability groups.</span></span> <span data-ttu-id="c6b6f-104">Avant de pouvoir créer et configurer un groupe de disponibilité, la fonctionnalité [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] doit avoir été activée sur chaque instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui hébergera un réplica de disponibilité pour un ou plusieurs groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-104">Before you can create and configure any availability group, the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature must have been enabled on the each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that will host an availability replica for one or more availability groups.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6b6f-105">Si vous supprimez et recréez un cluster WSFC, vous devez désactiver puis réactiver la fonctionnalité [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] sur chaque instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] qui hébergeait un réplica de disponibilité sur le cluster WSFC d'origine.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-105">If you delete and re-create a WSFC cluster, you must disable and re-enable the [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] feature on each instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that hosted an availability replica on the original WSFC cluster.</span></span>  
  
-   <span data-ttu-id="c6b6f-106">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-106">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="c6b6f-107">Composants requis</span><span class="sxs-lookup"><span data-stu-id="c6b6f-107">Prerequisites</span></span>](#Prerequisites)  
  
     [<span data-ttu-id="c6b6f-108">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c6b6f-108">Security</span></span>](#Security)  
  
-   <span data-ttu-id="c6b6f-109">**Comment:**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-109">**How To:**</span></span>  
  
    -   [<span data-ttu-id="c6b6f-110">Déterminer si l'option Groupes de disponibilité AlwaysOn est activée</span><span class="sxs-lookup"><span data-stu-id="c6b6f-110">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>](#IsEnabled)  
  
    -   [<span data-ttu-id="c6b6f-111">Activer groupes de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-111">Enable AlwaysOn Availability Groups</span></span>](#EnableAOAG)  
  
    -   [<span data-ttu-id="c6b6f-112">Désactiver les groupes de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-112">Disable AlwaysOn Availability Groups</span></span>](#DisableAOAG)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="c6b6f-113">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="c6b6f-113">Before You Begin</span></span>  
  
###  <a name="prerequisites-for-enabling-alwayson-availability-groups"></a><a name="Prerequisites"></a><span data-ttu-id="c6b6f-114">Conditions préalables à l’activation de groupes de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-114">Prerequisites for Enabling AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="c6b6f-115">L'instance de serveur doit résider sur un nœud de Clustering de basculement Windows Server (WSFC).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-115">The server instance must reside on a Windows Server Failover Clustering (WSFC) node.</span></span>  
  
-   <span data-ttu-id="c6b6f-116">L'instance du serveur doit exécuter une édition de SQL Server qui prend en charge [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b6f-116">The server instance must be running an edition of SQL Server that supports [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="c6b6f-117">Pour plus d’informations, consultez [fonctionnalités prises en charge par les éditions de SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-117">For more information, see [Features Supported by the Editions of SQL Server 2014](../../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span>  
  
-   <span data-ttu-id="c6b6f-118">Activez les groupes de disponibilité AlwaysOn sur une seule instance de serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-118">Enable AlwaysOn Availability Groups on only one server instance at a time.</span></span> <span data-ttu-id="c6b6f-119">Après avoir activé les groupes de disponibilité AlwaysOn, attendez le redémarrage du service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avant de passer à une autre instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-119">After enabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
 <span data-ttu-id="c6b6f-120">Pour plus d’informations sur les conditions préalables supplémentaires pour la création et la configuration des groupes de disponibilité, consultez [conditions préalables requises, restrictions et recommandations pour groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-120">For information about additional prerequisites for creating and configuring availability groups, see [Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md).</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="c6b6f-121">Sécurité</span><span class="sxs-lookup"><span data-stu-id="c6b6f-121">Security</span></span>  
 <span data-ttu-id="c6b6f-122">Lorsque les groupes de disponibilité AlwaysOn sont activés sur une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], l'instance de serveur a le contrôle total sur le cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-122">While AlwaysOn Availability Groups is enabled on an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server instance has full control on the WSFC cluster.</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6b6f-123">Autorisations</span><span class="sxs-lookup"><span data-stu-id="c6b6f-123">Permissions</span></span>  
 <span data-ttu-id="c6b6f-124">Nécessite l'appartenance au groupe **Administrateur** sur l'ordinateur local et le contrôle total sur le cluster WSFC.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-124">Requires membership in the **Administrator** group on the local computer and full control on the WSFC cluster.</span></span> <span data-ttu-id="c6b6f-125">Pour activer AlwaysOn à l'aide de PowerShell, ouvrez la fenêtre d'invite de commandes en utilisant l'option **Exécuter en tant qu'administrateur** .</span><span class="sxs-lookup"><span data-stu-id="c6b6f-125">When enabling AlwaysOn by using PowerShell, open the Command Prompt window using the **Run as administrator** option.</span></span>  
  
 <span data-ttu-id="c6b6f-126">Requiert des autorisations de création et de gestion d'objets Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-126">Requires Active Directory Create Objects and Manage Objects permissions.</span></span>  
  
##  <a name="determine-whether-alwayson-availability-groups-is-enabled"></a><a name="IsEnabled"></a><span data-ttu-id="c6b6f-127">Déterminer si groupes de disponibilité AlwaysOn est activé</span><span class="sxs-lookup"><span data-stu-id="c6b6f-127">Determine Whether AlwaysOn Availability Groups is Enabled</span></span>  
  
-   [<span data-ttu-id="c6b6f-128">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6b6f-128">SQL Server Management Studio</span></span>](#SSMS1Procedure)  
  
-   [<span data-ttu-id="c6b6f-129">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6b6f-129">Transact-SQL</span></span>](#Tsql1Procedure)  
  
-   [<span data-ttu-id="c6b6f-130">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-130">PowerShell</span></span>](#PowerShell1Procedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMS1Procedure"></a> <span data-ttu-id="c6b6f-131">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="c6b6f-131">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="c6b6f-132">**Pour déterminer si l'option Groupes de disponibilité AlwaysOn est activée**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-132">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="c6b6f-133">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur l’instance de serveur, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-133">In Object Explorer, right-click the server instance, and  click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c6b6f-134">Dans la boîte de dialogue **Propriétés du serveur** , cliquez sur la page **Général** .</span><span class="sxs-lookup"><span data-stu-id="c6b6f-134">In the **Server Properties** dialog box, click the **General** page.</span></span> <span data-ttu-id="c6b6f-135">La propriété **Is HADR Enabled** affiche une des valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-135">The **Is HADR Enabled** property displays one of the following values:</span></span>  
  
    -   <span data-ttu-id="c6b6f-136">**True**, si l'option Groupes de disponibilité AlwaysOn est activée</span><span class="sxs-lookup"><span data-stu-id="c6b6f-136">**True**, if AlwaysOn Availability Groups is enabled</span></span>  
  
    -   <span data-ttu-id="c6b6f-137">**False**, si l'option Groupes de disponibilité AlwaysOn est désactivée.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-137">**False**, if AlwaysOn Availability Groups is disabled.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="Tsql1Procedure"></a> <span data-ttu-id="c6b6f-138">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6b6f-138">Using Transact-SQL</span></span>  
 <span data-ttu-id="c6b6f-139">**Pour déterminer si l'option Groupes de disponibilité AlwaysOn est activée**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-139">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="c6b6f-140">Utilisez l'instruction [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) suivante :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-140">Use the following [SERVERPROPERTY](/sql/t-sql/functions/serverproperty-transact-sql) statement:</span></span>  
  
    ```sql
    SELECT SERVERPROPERTY ('IsHadrEnabled');  
    ```  
  
     <span data-ttu-id="c6b6f-141">Le paramètre de la propriété de serveur `IsHadrEnabled` indique si une instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est activée pour les groupes de disponibilité AlwaysOn, comme suit :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-141">The setting of the `IsHadrEnabled` server property indicates whether an instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is enabled for AlwaysOn Availability Groups, as follows:</span></span>  
  
    -   <span data-ttu-id="c6b6f-142">Si `IsHadrEnabled` = 1, l'option Groupes de disponibilité AlwaysOn est activée.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-142">If `IsHadrEnabled` = 1, AlwaysOn Availability Groups is enabled.</span></span>  
  
    -   <span data-ttu-id="c6b6f-143">Si `IsHadrEnabled` = 0, l'option Groupes de disponibilité AlwaysOn est désactivée.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-143">If `IsHadrEnabled` = 0, AlwaysOn Availability Groups is disabled.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6b6f-144">Pour plus d’informations sur la `IsHadrEnabled` propriété de serveur, consultez [ServerProperty &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-144">For more information about the `IsHadrEnabled` server property, see [SERVERPROPERTY &#40;Transact-SQL&#41;](/sql/t-sql/functions/serverproperty-transact-sql).</span></span>  
  
###  <a name="using-powershell"></a><a name="PowerShell1Procedure"></a> <span data-ttu-id="c6b6f-145">Utilisation de PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-145">Using PowerShell</span></span>  
 <span data-ttu-id="c6b6f-146">**Pour déterminer si l'option Groupes de disponibilité AlwaysOn est activée**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-146">**To determine whether AlwaysOn Availability Groups is enabled**</span></span>  
  
1.  <span data-ttu-id="c6b6f-147">Définissez la valeur par défaut ( `cd` ) sur l’instance de serveur (par exemple `\SQL\NODE1\DEFAULT` ,) sur laquelle vous souhaitez déterminer si [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] est activé.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-147">Set default (`cd`) to the server instance (e.g. `\SQL\NODE1\DEFAULT`) on which you want to determine whether [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] is enabled.</span></span>  
  
2.  <span data-ttu-id="c6b6f-148">Entrez la commande PowerShell `Get-Item` suivante :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-148">Enter the following PowerShell `Get-Item` command:</span></span>  
  
    ```powershell
    Get-Item . | Select IsHadrEnabled  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6b6f-149">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-149">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="c6b6f-150">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-150">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="c6b6f-151">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-151">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="c6b6f-152">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-152">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
##  <a name="enable-alwayson-availability-groups"></a><a name="EnableAOAG"></a> <span data-ttu-id="c6b6f-153">Activer les groupes de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-153">Enable AlwaysOn Availability Groups</span></span>  
 <span data-ttu-id="c6b6f-154">**Pour activer AlwaysOn, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-154">**To enable AlwaysOn, using:**</span></span>  
  
-   [<span data-ttu-id="c6b6f-155">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b6f-155">SQL Server Configuration Manager</span></span>](#SQLCM2Procedure)  
  
-   [<span data-ttu-id="c6b6f-156">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-156">PowerShell</span></span>](#PScmd2Procedure)  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM2Procedure"></a> <span data-ttu-id="c6b6f-157">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b6f-157">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="c6b6f-158">**Pour activer les groupes de disponibilité AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-158">**To enable AlwaysOn Availability Groups**</span></span>  
  
1.  <span data-ttu-id="c6b6f-159">Connectez-vous au nœud de clustering de basculement Windows Server (WSFC) qui héberge l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur laquelle vous souhaitez activer les groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-159">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to enable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="c6b6f-160">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and  click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="c6b6f-161">Dans **Gestionnaire de configuration SQL Server**, cliquez sur **services SQL Server**, cliquez avec le bouton droit sur SQL Server (\*\* < *`instance name`*>)\*\*, où **<*`instance name`*>** est le nom d’une instance de serveur local pour laquelle vous souhaitez activer groupes de disponibilité AlwaysOn, puis cliquez sur **Propriétés.**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-161">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to enable AlwaysOn Availability Groups, and click **Properties.**</span></span>  
  
4.  <span data-ttu-id="c6b6f-162">Sélectionnez l'onglet **Haute disponibilité AlwaysOn** .</span><span class="sxs-lookup"><span data-stu-id="c6b6f-162">Select the **AlwaysOn High Availability** tab.</span></span>  
  
5.  <span data-ttu-id="c6b6f-163">Vérifiez que le champ **Nom du cluster de basculement Windows** contient le nom du cluster de basculement local.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-163">Verify that **Windows failover cluster name** field contains the name of the local failover cluster.</span></span> <span data-ttu-id="c6b6f-164">Si ce champ est vide, cette instance de serveur ne prend pas en charge [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)]pour le moment.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-164">If this field is blank, this server instance currently does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span> <span data-ttu-id="c6b6f-165">L'ordinateur local n'est pas un nœud de cluster, le cluster WSFC a été arrêté, ou cette édition de [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] ne prend pas en charge [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6b6f-165">Either the local computer is not a cluster node, the WSFC cluster has been shut down, or this edition of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] that does not support [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span></span>  
  
6.  <span data-ttu-id="c6b6f-166">Activez la case à cocher **activer la groupes de disponibilité AlwaysOn** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-166">Select the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="c6b6f-167">enregistre votre modification.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-167">Configuration Manager saves your change.</span></span> <span data-ttu-id="c6b6f-168">Ensuite, vous devez redémarrer manuellement le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6b6f-168">Then, you must manually restart the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="c6b6f-169">Cela vous permet de choisir l'heure de redémarrage la plus adaptée aux besoins de l'entreprise.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-169">This enables you to choose a restart time that is best for your business requirements.</span></span> <span data-ttu-id="c6b6f-170">Lorsque le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] redémarre, AlwaysOn est activé, et la propriété de serveur `IsHadrEnabled` a la valeur 1.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-170">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be enabled, and the `IsHadrEnabled` server property will be set to 1.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd2Procedure"></a> <span data-ttu-id="c6b6f-171">Utilisation de PowerShell SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b6f-171">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="c6b6f-172">**Pour activer AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-172">**To enable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="c6b6f-173">Changez de répertoire (`cd`) pour accéder à une instance de serveur pour laquelle vous voulez activer les groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-173">Change directory (`cd`) to a server instance that you want to enable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="c6b6f-174">Utilisez l'applet de commande `Enable-SqlAlwaysOn` pour activer les groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-174">Use the `Enable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="c6b6f-175">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-175">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="c6b6f-176">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-176">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c6b6f-177">Pour plus d’informations sur la façon de contrôler si l’applet de commande redémarre le `Enable-SqlAlwaysOn` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, consultez à [quel moment une applet de commande redémarre-t-elle le service SQL Server ?](#WhenCmdletRestartsSQL), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-177">For information about how to control whether the `Enable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
 <span data-ttu-id="c6b6f-178">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-178">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="c6b6f-179">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-179">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
####  <a name="example-enable-sqlalwayson"></a><a name="ExmplEnable-SqlHadrServic"></a> <span data-ttu-id="c6b6f-180">Exemple : Enable-SqlAlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-180">Example: Enable-SqlAlwaysOn</span></span>  
 <span data-ttu-id="c6b6f-181">La commande PowerShell suivante active les [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] sur une instance de SQL Server (*Ordinateur*\\*Instance*).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-181">The following PowerShell command enables [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  
  
```powershell
Enable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
```  
  
##  <a name="disable-alwayson-availability-groups"></a><a name="DisableAOAG"></a><span data-ttu-id="c6b6f-182">Désactiver les groupes de disponibilité AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-182">Disable AlwaysOn Availability Groups</span></span>  
  
-   <span data-ttu-id="c6b6f-183">**Avant de désactiver AlwaysOn :**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-183">**Before you disable AlwaysOn:**</span></span>  
  
     [<span data-ttu-id="c6b6f-184">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c6b6f-184">Recommendations</span></span>](#Recommendations)  
  
-   <span data-ttu-id="c6b6f-185">**Pour désactiver AlwaysOn, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-185">**To disable AlwaysOn, using:**</span></span>  
  
    -   [<span data-ttu-id="c6b6f-186">Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b6f-186">SQL Server Configuration Manager</span></span>](#SQLCM3Procedure)  
  
    -   [<span data-ttu-id="c6b6f-187">PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-187">PowerShell</span></span>](#PScmd3Procedure)  
  
-   <span data-ttu-id="c6b6f-188">**Suivi :**  [Après la désactivation d'AlwaysOn](#FollowUp)</span><span class="sxs-lookup"><span data-stu-id="c6b6f-188">**Follow Up:**  [After Disabling AlwaysOn](#FollowUp)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c6b6f-189">Désactivez AlwaysOn sur une seule instance de serveur à la fois.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-189">Disable AlwaysOn on only one server instance at a time.</span></span> <span data-ttu-id="c6b6f-190">Après avoir désactivé les groupes de disponibilité AlwaysOn, attendez le redémarrage du service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] avant de passer à une autre instance de serveur.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-190">After disabling AlwaysOn Availability Groups, wait until the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service has restarted before you proceed to another server instance.</span></span>  
  
###  <a name="recommendations"></a><a name="Recommendations"></a> <span data-ttu-id="c6b6f-191">Recommandations</span><span class="sxs-lookup"><span data-stu-id="c6b6f-191">Recommendations</span></span>  
 <span data-ttu-id="c6b6f-192">Avant de désactiver AlwaysOn sur une instance de serveur, nous vous recommandons d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-192">Before you disable AlwaysOn on a server instance, we recommend that you do the following:</span></span>  
  
1.  <span data-ttu-id="c6b6f-193">Si l'instance de serveur héberge actuellement le réplica principal d'un groupe de disponibilité que vous souhaitez conserver, nous recommandons de basculer manuellement le groupe de disponibilité vers un réplica secondaire synchronisé, si possible.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-193">If the server instance is currently hosting the primary replica of an availability group that you want to keep, we recommend that you manually fail over the availability group to a synchronized secondary replica, if possible.</span></span> <span data-ttu-id="c6b6f-194">Pour plus d’informations, consultez [Effectuer un basculement manuel planifié d’un groupe de disponibilité &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-194">For more information, see [Perform a Planned Manual Failover of an Availability Group &#40;SQL Server&#41;](perform-a-planned-manual-failover-of-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="c6b6f-195">Supprimez tous les réplicas secondaires locaux.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-195">Remove all local secondary replicas.</span></span> <span data-ttu-id="c6b6f-196">Pour plus d’informations, consultez [Supprimer un réplica secondaire d’un groupe de disponibilité &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-196">For more information, see [Remove a Secondary Replica from an Availability Group &#40;SQL Server&#41;](remove-a-secondary-replica-from-an-availability-group-sql-server.md).</span></span>  
  
###  <a name="using-sql-server-configuration-manager"></a><a name="SQLCM3Procedure"></a> <span data-ttu-id="c6b6f-197">Utilisation du Gestionnaire de configuration SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b6f-197">Using SQL Server Configuration Manager</span></span>  
 <span data-ttu-id="c6b6f-198">**Pour désactiver AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-198">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="c6b6f-199">Connectez-vous au nœud de clustering de basculement Windows Server (WSFC) qui héberge l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sur laquelle vous souhaitez désactiver les groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-199">Connect to the Windows Server Failover Clustering (WSFC) node that hosts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance where you want to disable AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="c6b6f-200">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)]et sur **Outils de configuration**, puis cliquez sur **Gestionnaire de configuration SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-200">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../../includes/sscurrentui-md.md)], point to **Configuration Tools**, and click **SQL Server Configuration Manager**.</span></span>  
  
3.  <span data-ttu-id="c6b6f-201">Dans **Gestionnaire de configuration SQL Server**, cliquez sur **services SQL Server**, cliquez avec le bouton droit sur SQL Server (\*\* < *`instance name`*>)\*\*, où **<*`instance name`*>** est le nom d’une instance de serveur local pour laquelle vous souhaitez désactiver groupes de disponibilité AlwaysOn, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-201">In **SQL Server Configuration Manager**, click **SQL Server Services**, right-click SQL Server (**<*`instance name`*>)**, where **<*`instance name`*>** is the name of a local server instance for which you want to disable AlwaysOn Availability Groups, and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="c6b6f-202">Sur l’onglet**Haute disponibilité AlwaysOn**, décochez la case **Activer les groupes de disponibilité AlwaysOn** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-202">On the**AlwaysOn High Availability**tab, deselect the **Enable AlwaysOn Availability Groups** check box, and click **OK**.</span></span>  
  
     [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="c6b6f-203">enregistre votre modification et redémarre le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6b6f-203">Configuration Manager saves your change and restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service.</span></span> <span data-ttu-id="c6b6f-204">Lorsque le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] redémarre, AlwaysOn est désactivé, et la propriété de serveur `IsHadrEnabled` a la valeur 0, pour indiquer que l'option Groupes de disponibilité AlwaysOn est désactivée.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-204">When the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarts, AlwaysOn will be disabled, and the `IsHadrEnabled` server property will be set to 0, to indicate that AlwaysOn Availability Groups is disabled.</span></span>  
  
5.  <span data-ttu-id="c6b6f-205">Nous vous recommandons de lire les informations de la section [Suivi : Après la désactivation d'AlwaysOn](#FollowUp), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-205">We recommend that you read the information in [Follow Up: After Disabling AlwaysOn](#FollowUp), later in this topic.</span></span>  
  
###  <a name="using-sql-server-powershell"></a><a name="PScmd3Procedure"></a> <span data-ttu-id="c6b6f-206">Utilisation de PowerShell SQL Server</span><span class="sxs-lookup"><span data-stu-id="c6b6f-206">Using SQL Server PowerShell</span></span>  
 <span data-ttu-id="c6b6f-207">**Pour désactiver AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-207">**To disable AlwaysOn**</span></span>  
  
1.  <span data-ttu-id="c6b6f-208">Remplacez le répertoire ( `cd` ) par une instance de serveur actuellement activée que vous souhaitez désactiver pour groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-208">Change directory (`cd`) to a currently-enabled server instance that you want to disenable for AlwaysOn Availability Groups.</span></span>  
  
2.  <span data-ttu-id="c6b6f-209">Utilisez l'applet de commande `Disable-SqlAlwaysOn` pour activer les groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-209">Use the `Disable-SqlAlwaysOn` cmdlet to enable AlwaysOn Availability Groups.</span></span>  
  
     <span data-ttu-id="c6b6f-210">Par exemple, la commande suivante désactive groupes de disponibilité AlwaysOn sur une instance de SQL Server (instance de l'*ordinateur* \\ *Instance*).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-210">For example, the following command disables AlwaysOn Availability Groups on an instance of SQL Server (*Computer*\\*Instance*).</span></span>  <span data-ttu-id="c6b6f-211">Cette commande nécessite le redémarrage de l'instance et vous serez invité à confirmer ce redémarrage.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-211">This command requires restarting the instance, and you will be prompted to confirm this restart.</span></span>  
  
    ```powershell
    Disable-SqlAlwaysOn -Path SQLSERVER:\SQL\Computer\Instance  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c6b6f-212">Pour plus d’informations sur la façon de contrôler si l’applet de commande redémarre le `Disable-SqlAlwaysOn` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, consultez à [quel moment une applet de commande redémarre-t-elle le service SQL Server ?](#WhenCmdletRestartsSQL), plus loin dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-212">For information about how to control whether the `Disable-SqlAlwaysOn` cmdlet restarts the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service, see [When Does a Cmdlet Restart the SQL Server Service?](#WhenCmdletRestartsSQL), later in this topic.</span></span>  
  
     <span data-ttu-id="c6b6f-213">Pour afficher la syntaxe d'une applet de commande, utilisez l'applet de commande `Get-Help` dans l'environnement [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-213">To view the syntax of a cmdlet, use the `Get-Help` cmdlet in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] PowerShell environment.</span></span> <span data-ttu-id="c6b6f-214">Pour en savoir plus, voir [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-214">For more information, see [Get Help SQL Server PowerShell](../../../powershell/sql-server-powershell.md).</span></span>  
  
 <span data-ttu-id="c6b6f-215">**Pour configurer et utiliser le fournisseur SQL Server PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-215">**To set up and use the SQL Server PowerShell provider**</span></span>  
  
-   [<span data-ttu-id="c6b6f-216">Fournisseur SQL Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6b6f-216">SQL Server PowerShell Provider</span></span>](../../../powershell/sql-server-powershell-provider.md)  
  
###  <a name="follow-up-after-disabling-alwayson"></a><a name="FollowUp"></a><span data-ttu-id="c6b6f-217">Suivi : après la désactivation d’AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="c6b6f-217">Follow Up: After Disabling AlwaysOn</span></span>  
 <span data-ttu-id="c6b6f-218">Après avoir désactivé des groupes de disponibilité AlwaysOn, l'instance de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] doit être redémarrée.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-218">After you disable AlwaysOn Availability Groups, the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] must be restarted.</span></span> <span data-ttu-id="c6b6f-219">Le Gestionnaire de configuration SQL redémarre l'instance de serveur automatiquement.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-219">SQL Configuration Manager restarts the server instance automatically.</span></span> <span data-ttu-id="c6b6f-220">Toutefois, si vous avez utilisé l'applet de commande `Disable-SqlAlwaysOn`, vous devez redémarrer l'instance de serveur manuellement.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-220">However, if you used the `Disable-SqlAlwaysOn` cmdlet, you will need to restart the server instance manually.</span></span> <span data-ttu-id="c6b6f-221">Pour plus d’informations, consultez [sqlservr Application](../../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-221">For more information, see [sqlservr Application](../../../tools/sqlservr-application.md).</span></span>  
  
 <span data-ttu-id="c6b6f-222">Sur l'instance de serveur redémarrée :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-222">On the restarted server instance:</span></span>  
  
-   <span data-ttu-id="c6b6f-223">Les bases de données de disponibilité ne démarrent pas au démarrage de SQL Server, ce qui les rend inaccessibles.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-223">Availability databases do not start up at SQL Server startup, making them inaccessible.</span></span>  
  
-   <span data-ttu-id="c6b6f-224">La seule instruction [!INCLUDE[tsql](../../../includes/tsql-md.md)] AlwaysOn prise en charge est [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-224">The only supported AlwaysOn [!INCLUDE[tsql](../../../includes/tsql-md.md)] statement is [DROP AVAILABILITY GROUP](/sql/t-sql/statements/drop-availability-group-transact-sql).</span></span> <span data-ttu-id="c6b6f-225">Les options CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP et SET HADR de ALTER DATABASE ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-225">CREATE AVAILABILITY GROUP, ALTER AVAILABILITY GROUP, and the SET HADR options of ALTER DATABASE are not supported.</span></span>  
  
-   <span data-ttu-id="c6b6f-226">Les métadonnées [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] et les données de configuration [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] dans WSFC ne sont pas affectées par la désactivation des groupes de disponibilité AlwaysOn.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-226">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] metadata and [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] configuration data in WSFC are unaffected by disabling AlwaysOn Availability Groups.</span></span>  
  
 <span data-ttu-id="c6b6f-227">Si vous désactivez définitivement des groupes de disponibilité AlwaysOn sur chaque instance de serveur qui héberge un réplica de disponibilité pour un ou plusieurs groupes de disponibilité, nous recommandons de procéder comme suit :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-227">If you permanently disable AlwaysOn Availability Groups on every server instance that hosts an availability replica for one or more availability groups, we recommend that you complete the following steps:</span></span>  
  
1.  <span data-ttu-id="c6b6f-228">Si vous ne supprimez pas les réplicas de disponibilité locaux avant de désactiver AlwaysOn, supprimez (avec l'instruction Drop) chaque groupe de disponibilité pour lequel l'instance de serveur héberge un réplica de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-228">If you did not remove the local availability replicas before disabling AlwaysOn, delete (drop) each availability group for which the server instance is hosting an availability replica.</span></span> <span data-ttu-id="c6b6f-229">Pour plus d’informations sur la suppression d’un groupe de disponibilité, consultez [Supprimer un groupe de disponibilité &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c6b6f-229">For information about deleting an availability group, see [Remove an Availability Group &#40;SQL Server&#41;](remove-an-availability-group-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="c6b6f-230">Pour supprimer les métadonnées restantes, supprimez (avec l'instruction Drop) chaque groupe de disponibilité affecté sur une instance de serveur qui fait partie du cluster WSFC d'origine.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-230">To remove the metadata left behind, delete (drop) each affected availability group on a server instance that is part of the original WSFC cluster.</span></span>  
  
3.  <span data-ttu-id="c6b6f-231">Toutes les bases de données primaires restent accessibles à toutes les connexions, mais la synchronisation des données entre les bases de données primaires et secondaires est arrêtée.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-231">Any primary databases continue to be accessible to all connections but the data synchronization between the primary and secondary databases stops.</span></span>  
  
4.  <span data-ttu-id="c6b6f-232">Les bases de données secondaires passent à l'état RESTORING.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-232">The secondary databases enter the RESTORING state.</span></span> <span data-ttu-id="c6b6f-233">Vous pouvez les supprimer ou les restaurer à l'aide de RESTORE WITH RECOVERY.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-233">You can delete them, or you can restore them by using RESTORE WITH RECOVERY.</span></span> <span data-ttu-id="c6b6f-234">Toutefois, les bases de données restaurées ne participent plus à la synchronisation des données des groupes de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-234">However, restored databases are no longer participating in availability-group data synchronization.</span></span>  
  
##  <a name="when-does-a-cmdlet-restart-the-sql-server-service"></a><a name="WhenCmdletRestartsSQL"></a> <span data-ttu-id="c6b6f-235">À quel moment une applet de commande redémarre-t-elle le service SQL Server ?</span><span class="sxs-lookup"><span data-stu-id="c6b6f-235">When Does a Cmdlet Restart the SQL Server Service?</span></span>  
 <span data-ttu-id="c6b6f-236">Sur une instance de serveur en cours d'exécution, l'utilisation de `Enable-SqlAlwaysOn` ou de `Disable-SqlAlwaysOn` pour modifier le paramètre actuel d'AlwaysOn peut entraîner le redémarrage du service SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-236">On a server instance that is currently running, using `Enable-SqlAlwaysOn` or `Disable-SqlAlwaysOn` to change the current AlwaysOn setting could cause the SQL Server service to restart.</span></span> <span data-ttu-id="c6b6f-237">Le comportement de redémarrage dépend des conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-237">The restart behavior on depends on the following conditions:</span></span>  
  
|<span data-ttu-id="c6b6f-238">Paramètre -NoServiceRestart spécifié</span><span class="sxs-lookup"><span data-stu-id="c6b6f-238">-NoServiceRestart parameter specified</span></span>|<span data-ttu-id="c6b6f-239">Paramètre -Force spécifié</span><span class="sxs-lookup"><span data-stu-id="c6b6f-239">-Force parameter specified</span></span>|<span data-ttu-id="c6b6f-240">Le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a-t-il été redémarré ?</span><span class="sxs-lookup"><span data-stu-id="c6b6f-240">Is the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service restarted?</span></span>|  
|--------------------------------------------|---------------------------------|---------------------------------------------------------|  
|<span data-ttu-id="c6b6f-241">Non</span><span class="sxs-lookup"><span data-stu-id="c6b6f-241">No</span></span>|<span data-ttu-id="c6b6f-242">Non</span><span class="sxs-lookup"><span data-stu-id="c6b6f-242">No</span></span>|<span data-ttu-id="c6b6f-243">Par défaut.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-243">By default.</span></span> <span data-ttu-id="c6b6f-244">Mais l'applet de commande vous invite à agir comme suit :</span><span class="sxs-lookup"><span data-stu-id="c6b6f-244">But the cmdlet prompts you as follows:</span></span><br /><br /> <span data-ttu-id="c6b6f-245">**Pour permettre l’achèvement de cette action, le service SQL Server de l’instance de serveur <nom_instance> doit redémarrer. Voulez-vous continuer ? »**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-245">**To complete this action, we must restart the SQL Server service for server instance '<instance_name>'. Do you want to continue?**</span></span><br /><br /> <span data-ttu-id="c6b6f-246">**[Y] Oui [N] Non [S] Suspendre [?] Aide (la valeur par défaut est « Y ») :**</span><span class="sxs-lookup"><span data-stu-id="c6b6f-246">**[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):**</span></span><br /><br /> <span data-ttu-id="c6b6f-247">Si vous spécifiez **N** ou **S**, le service n'est pas redémarré.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-247">If you specify **N** or **S**, the service is not restarted.</span></span>|  
|<span data-ttu-id="c6b6f-248">Non</span><span class="sxs-lookup"><span data-stu-id="c6b6f-248">No</span></span>|<span data-ttu-id="c6b6f-249">Oui</span><span class="sxs-lookup"><span data-stu-id="c6b6f-249">Yes</span></span>|<span data-ttu-id="c6b6f-250">Le service est redémarré.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-250">Service is restarted.</span></span>|  
|<span data-ttu-id="c6b6f-251">Oui</span><span class="sxs-lookup"><span data-stu-id="c6b6f-251">Yes</span></span>|<span data-ttu-id="c6b6f-252">Non</span><span class="sxs-lookup"><span data-stu-id="c6b6f-252">No</span></span>|<span data-ttu-id="c6b6f-253">Le service n'est pas redémarré.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-253">Service is not restarted.</span></span>|  
|<span data-ttu-id="c6b6f-254">Oui</span><span class="sxs-lookup"><span data-stu-id="c6b6f-254">Yes</span></span>|<span data-ttu-id="c6b6f-255">Oui</span><span class="sxs-lookup"><span data-stu-id="c6b6f-255">Yes</span></span>|<span data-ttu-id="c6b6f-256">Le service n'est pas redémarré.</span><span class="sxs-lookup"><span data-stu-id="c6b6f-256">Service is not restarted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c6b6f-257">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c6b6f-257">See Also</span></span>  
 <span data-ttu-id="c6b6f-258">[Vue d’ensemble de groupes de disponibilité AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c6b6f-258">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="c6b6f-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c6b6f-259">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
