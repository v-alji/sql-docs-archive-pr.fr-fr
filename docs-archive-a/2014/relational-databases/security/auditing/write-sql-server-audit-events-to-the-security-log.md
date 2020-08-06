---
title: Écrire des événements d’audit SQL Server dans le journal de sécurité | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- logs [SQL Server], Security Log
- server audit [SQL Server]
- audits [SQL Server], writing to Security Log
- security logs [SQL Server]
ms.assetid: 6fabeea3-7a42-4769-a0f3-7e04daada314
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: d59134b278f29c9b604208d8cab7e982144b9c9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602020"
---
# <a name="write-sql-server-audit-events-to-the-security-log"></a><span data-ttu-id="b5bfe-102">Écrire des événements d'audit SQL Server dans le journal de sécurité</span><span class="sxs-lookup"><span data-stu-id="b5bfe-102">Write SQL Server Audit Events to the Security Log</span></span>
  <span data-ttu-id="b5bfe-103">Dans un environnement extrêmement sécurisé, le journal de sécurité Windows est l'emplacement approprié pour consigner des événements d'accès aux objets.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-103">In a high security environment, the Windows Security log is the appropriate location to write events that record object access.</span></span> <span data-ttu-id="b5bfe-104">D'autres emplacements d'audit sont pris en charge mais ils sont plus exposés au risque de falsification.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-104">Other audit locations are supported but are more subject to tampering.</span></span>  
  
 <span data-ttu-id="b5bfe-105">L'écriture des audits du serveur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dans le journal de sécurité Windows est soumise à deux conditions clés :</span><span class="sxs-lookup"><span data-stu-id="b5bfe-105">There are two key requirements for writing [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] server audits to the Windows Security log:</span></span>  
  
-   <span data-ttu-id="b5bfe-106">Le paramètre Auditer l'accès aux objets doit être configuré pour capturer les événements.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-106">The audit object access setting must be configured to capture the events.</span></span> <span data-ttu-id="b5bfe-107">L’outil de stratégie d’audit (`auditpol.exe`) expose différents paramètres de sous-stratégies dans la catégorie **Auditer l’accès aux objets** .</span><span class="sxs-lookup"><span data-stu-id="b5bfe-107">The audit policy tool (`auditpol.exe`) exposes a variety of sub-policies settings in the **audit object access** category.</span></span> <span data-ttu-id="b5bfe-108">Pour permettre à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] d'auditer l'accès aux objets, configurez le paramètre **généré par une application** .</span><span class="sxs-lookup"><span data-stu-id="b5bfe-108">To allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to audit object access, configure the **application generated** setting.</span></span>  
  
-   <span data-ttu-id="b5bfe-109">Le compte sous lequel le service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est exécuté doit posséder l’autorisation **Générer des audits de sécurité** pour écrire dans le journal de sécurité Windows.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-109">The account that the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service is running under must have the **generate security audits** permission to write to the Windows Security log.</span></span> <span data-ttu-id="b5bfe-110">Par défaut, les comptes Service local et Service réseau disposent de cette autorisation.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-110">By default, the LOCAL SERVICE and the NETWORK SERVICE accounts have this permission.</span></span> <span data-ttu-id="b5bfe-111">Cette étape n'est pas requise si [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] s'exécute sous l'un de ces comptes.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-111">This step is not required if [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running under one of those accounts.</span></span>  
  
 <span data-ttu-id="b5bfe-112">La stratégie d'audit Windows peut affecter l'audit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] s'il est configuré pour écrire dans le journal de sécurité Windows, avec la possibilité de perdre des événements si la stratégie d'audit est configurée incorrectement.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-112">The Windows audit policy can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] auditing if it is configured to write to the Windows Security log, with the potential of losing events if the audit policy is incorrectly configured.</span></span> <span data-ttu-id="b5bfe-113">En général, le journal de sécurité Windows est configuré pour remplacer les événements les plus anciens.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-113">Typically, the Windows Security log is set to overwrite the older events.</span></span> <span data-ttu-id="b5bfe-114">Les événements les plus récents sont ainsi préservés.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-114">This preserves the most recent events.</span></span> <span data-ttu-id="b5bfe-115">Toutefois, si le journal de sécurité Windows n'est pas configuré pour remplacer les événements les plus anciens, et si le journal de sécurité est plein, le système publie alors l'événement Windows 1104 (le journal est plein).</span><span class="sxs-lookup"><span data-stu-id="b5bfe-115">However, if the Windows Security log is not set to overwrite older events, then if the Security log is full, the system will issue Windows event 1104 (Log is full).</span></span> <span data-ttu-id="b5bfe-116">À ce stade :</span><span class="sxs-lookup"><span data-stu-id="b5bfe-116">At that point:</span></span>  
  
-   <span data-ttu-id="b5bfe-117">Plus aucun événement de sécurité supplémentaire n'est consigné</span><span class="sxs-lookup"><span data-stu-id="b5bfe-117">No further security events will be recorded</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="b5bfe-118">ne sera pas en mesure de détecter que le système n'est pas capable d'enregistrer les événements dans le journal de sécurité, provoquant ainsi la perte potentielle d'événements d'audit</span><span class="sxs-lookup"><span data-stu-id="b5bfe-118">will not be able to detect that the system is not able to record the events in the Security log, resulting in the potential loss of audit events</span></span>  
  
-   <span data-ttu-id="b5bfe-119">Une fois le journal de sécurité reconfiguré par l'administrateur, le comportement de consignation retourne à la normale.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-119">After the box administrator fixes the Security log, the logging behavior will return to normal.</span></span>  
  
 <span data-ttu-id="b5bfe-120">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="b5bfe-120">**In This Topic**</span></span>  
  
-   <span data-ttu-id="b5bfe-121">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="b5bfe-121">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="b5bfe-122">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b5bfe-122">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="b5bfe-123">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b5bfe-123">Security</span></span>](#Security)  
  
-   <span data-ttu-id="b5bfe-124">**Pour écrire des événements d'audit SQL Server dans le journal de sécurité :**</span><span class="sxs-lookup"><span data-stu-id="b5bfe-124">**To write SQL Server audit events to the Security Log:**</span></span>  
  
     [<span data-ttu-id="b5bfe-125">Configurer le paramètre Auditer l'accès aux objets dans Windows à l'aide de l'outil auditpol</span><span class="sxs-lookup"><span data-stu-id="b5bfe-125">Configure the audit object access setting in Windows using auditpol</span></span>](#auditpolAccess)  
  
     [<span data-ttu-id="b5bfe-126">Configurer le paramètre Auditer l'accès aux objets dans Windows à l'aide de l'outil secpol</span><span class="sxs-lookup"><span data-stu-id="b5bfe-126">Configure the audit object access setting in Windows using secpol</span></span>](#secpolAccess)  
  
     [<span data-ttu-id="b5bfe-127">Octroyer l'autorisation Générer des audits de sécurité à un compte à l'aide de l'outil secpol</span><span class="sxs-lookup"><span data-stu-id="b5bfe-127">Grant the generate security audits permission to an account using secpol</span></span>](#secpolPermission)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="b5bfe-128">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="b5bfe-128">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="b5bfe-129">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="b5bfe-129">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b5bfe-130">Les administrateurs de l'ordinateur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] doivent savoir que les paramètres locaux du journal de sécurité peuvent être remplacés par une stratégie de domaine.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-130">Administrators of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer should understand that local settings for the Security log can be overwritten by a domain policy.</span></span> <span data-ttu-id="b5bfe-131">Dans ce cas, la stratégie de domaine peut remplacer le paramètre de sous-catégorie (**auditpol /get /subcategory:"généré par application"** ).</span><span class="sxs-lookup"><span data-stu-id="b5bfe-131">In this case, the domain policy might overwrite the subcategory setting (**auditpol /get /subcategory:"application generated"**).</span></span> <span data-ttu-id="b5bfe-132">Cela peut affecter la capacité de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à consigner des événements sans avoir aucun moyen de détecter que les événements que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] essaie d'auditer ne vont pas être consignés.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-132">This can affect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ability to log events without having any way to detect that the events that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is trying to audit are not going to be recorded.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="b5bfe-133">Sécurité</span><span class="sxs-lookup"><span data-stu-id="b5bfe-133">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="b5bfe-134">Autorisations</span><span class="sxs-lookup"><span data-stu-id="b5bfe-134">Permissions</span></span>  
 <span data-ttu-id="b5bfe-135">Vous devez être un administrateur Windows pour configurer ces paramètres.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-135">You must be a Windows administrator to configure these settings.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-auditpol"></a><a name="auditpolAccess"></a> <span data-ttu-id="b5bfe-136">Pour configurer le paramètre Auditer l'accès aux objets dans Windows à l'aide de l'outil auditpol</span><span class="sxs-lookup"><span data-stu-id="b5bfe-136">To configure the audit object access setting in Windows using auditpol</span></span>  
  
1.  <span data-ttu-id="b5bfe-137">Ouvrez une invite de commandes avec des autorisations d'administrateur.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-137">Open a command prompt with administrative permissions.</span></span>  
  
    1.  <span data-ttu-id="b5bfe-138">Dans le menu **Démarrer** , pointez sur **Tous les programmes**, sur **Accessoires**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-138">On the **Start** menu, point to **All Programs**, point to **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>  
  
    2.  <span data-ttu-id="b5bfe-139">Si la boîte de dialogue **Contrôle de compte d'utilisateur** s'ouvre, cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-139">If the **User Account Control** dialog box opens, click **Continue**.</span></span>  
  
2.  <span data-ttu-id="b5bfe-140">Exécutez l'instruction suivante pour activer l'audit à partir de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b5bfe-140">Execute the following statement to enable auditing from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
    ```  
    auditpol /set /subcategory:"application generated" /success:enable /failure:enable  
    ```  
  
3.  <span data-ttu-id="b5bfe-141">Fermez la fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-141">Close the command prompt window.</span></span>  
  
##  <a name="to-grant-the-generate-security-audits-permission-to-an-account-using-secpol"></a><a name="secpolAccess"></a> <span data-ttu-id="b5bfe-142">Pour octroyer l'autorisation Générer des audits de sécurité à un compte à l'aide de l'outil secpol</span><span class="sxs-lookup"><span data-stu-id="b5bfe-142">To grant the generate security audits permission to an account using secpol</span></span>  
  
1.  <span data-ttu-id="b5bfe-143">Sur un système d'exploitation Windows, dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-143">For any Windows operating system, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b5bfe-144">Tapez **secpol.msc** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-144">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="b5bfe-145">Si la boîte de dialogue **Contrôle d'accès d'utilisateur** s'affiche, cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-145">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="b5bfe-146">Dans l'outil Stratégie de sécurité locale, développez **Paramètres de sécurité**, **Stratégies locales**, puis cliquez sur **Attribution des droits utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-146">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **User Rights Assignment**.</span></span>  
  
4.  <span data-ttu-id="b5bfe-147">Dans le volet de résultats, double-cliquez sur **Générer des audits de sécurité**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-147">In the results pane, double-click **Generate security audits**.</span></span>  
  
5.  <span data-ttu-id="b5bfe-148">Sous l'onglet **Paramètre de sécurité locale** , cliquez sur **Ajouter un utilisateur ou un groupe**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-148">On the **Local Security Setting** tab, click **Add User or Group**.</span></span>  
  
6.  <span data-ttu-id="b5bfe-149">Dans la boîte de dialogue **Sélectionnez les utilisateurs, les ordinateurs ou les groupes** , tapez le nom du compte d’utilisateur, tel que **domaine1\utilisateur1** , puis cliquez sur **OK**, ou cliquez sur **Avancé** et recherchez le compte.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-149">In the **Select Users, Computers, or Groups** dialog box, either type the name of the user account, such as **domain1\user1** and then click **OK**, or click **Advanced** and search for the account.</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="b5bfe-150">Fermez l'outil Stratégie de sécurité locale.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-150">Close the Security Policy tool.</span></span>  
  
9. <span data-ttu-id="b5bfe-151">Redémarrez [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] pour activer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-151">Restart [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to enable this setting.</span></span>  
  
##  <a name="to-configure-the-audit-object-access-setting-in-windows-using-secpol"></a><a name="secpolPermission"></a> <span data-ttu-id="b5bfe-152">Pour configurer le paramètre Auditer l'accès aux objets dans Windows à l'aide de l'outil secpol</span><span class="sxs-lookup"><span data-stu-id="b5bfe-152">To configure the audit object access setting in Windows using secpol</span></span>  
  
1.  <span data-ttu-id="b5bfe-153">Si la version du système d'exploitation est antérieure à [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] ou Windows Server 2008, dans le menu **Démarrer** , cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-153">If the operating system is earlier than [!INCLUDE[wiprlhext](../../../includes/wiprlhext-md.md)] or Windows Server 2008, on the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="b5bfe-154">Tapez **secpol.msc** , puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-154">Type **secpol.msc** and then click **OK**.</span></span> <span data-ttu-id="b5bfe-155">Si la boîte de dialogue **Contrôle d'accès d'utilisateur** s'affiche, cliquez sur **Continuer**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-155">If the **User Access Control** dialog box appears, click **Continue**.</span></span>  
  
3.  <span data-ttu-id="b5bfe-156">Dans l'outil Stratégie de sécurité locale, développez **Paramètres de sécurité**, **Stratégies locales**, puis cliquez sur **Stratégie d'audit**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-156">In the Local Security Policy tool, expand **Security Settings**, expand **Local Policies**, and then click **Audit Policy**.</span></span>  
  
4.  <span data-ttu-id="b5bfe-157">Dans le volet de résultats, double-cliquez sur **Auditer l’accès aux objets**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-157">In the results pane, double-click **Audit object access**.</span></span>  
  
5.  <span data-ttu-id="b5bfe-158">Sous l'onglet **Paramètre de sécurité locale** , dans la zone **Auditer les tentatives des types suivants** , sélectionnez **Succès** et **Échec**.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-158">On the **Local Security Setting** tab, in the **Audit these attempts** area, select both **Success** and **Failure**.</span></span>  
  
6.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="b5bfe-159">Fermez l'outil Stratégie de sécurité locale.</span><span class="sxs-lookup"><span data-stu-id="b5bfe-159">Close the Security Policy tool.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5bfe-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5bfe-160">See Also</span></span>  
 [<span data-ttu-id="b5bfe-161">SQL Server Audit &#40moteur de base de données&#41;</span><span class="sxs-lookup"><span data-stu-id="b5bfe-161">SQL Server Audit &#40;Database Engine&#41;</span></span>](sql-server-audit-database-engine.md)  
  
  
