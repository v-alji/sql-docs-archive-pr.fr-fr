---
title: Propriétés du serveur (page Sécurité) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.security.f1
ms.assetid: b8a131c7-e7bd-4203-bf26-234f1ebfe622
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5f45c0a04a0d7cc627901d8de24175f1d63a99fe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614837"
---
# <a name="server-properties-security-page"></a><span data-ttu-id="7f942-102">Propriétés du serveur (page Sécurité)</span><span class="sxs-lookup"><span data-stu-id="7f942-102">Server Properties (Security Page)</span></span>
  <span data-ttu-id="7f942-103">Utilisez cette page pour afficher ou modifier les options de sécurité de votre serveur.</span><span class="sxs-lookup"><span data-stu-id="7f942-103">Use this page to view or modify your server security options.</span></span>  
  
## <a name="server-authentication"></a><span data-ttu-id="7f942-104">Authentification du serveur</span><span class="sxs-lookup"><span data-stu-id="7f942-104">Server Authentication</span></span>  
 <span data-ttu-id="7f942-105">**Mode d'authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="7f942-105">**Windows Authentication mode**</span></span>  
 <span data-ttu-id="7f942-106">Utilisez l'authentification Windows pour valider les tentatives de connexion.</span><span class="sxs-lookup"><span data-stu-id="7f942-106">Uses Windows Authentication to validate attempted connections.</span></span> <span data-ttu-id="7f942-107">Si le mot de passe d’administrateur système **sa** est vide lorsque le mode de sécurité est modifié, le système demande à l’utilisateur d’entrer un mot de passe **sa** .</span><span class="sxs-lookup"><span data-stu-id="7f942-107">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="7f942-108">L'authentification Windows est plus sûre que l'authentification SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f942-108">Windows Authentication is much more secure than SQL Server Authentication.</span></span> <span data-ttu-id="7f942-109">Lorsque c'est possible, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="7f942-109">When possible, you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="7f942-110">**Mode d'authentification SQL Server et Windows**</span><span class="sxs-lookup"><span data-stu-id="7f942-110">**SQL Server and Windows Authentication mode**</span></span>  
 <span data-ttu-id="7f942-111">Utilise le mode d'authentification mixte pour vérifier les tentatives de connexion, pour des raisons de compatibilité descendante avec les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f942-111">Uses mixed mode authentication to verify attempted connections, for backward compatibility with earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f942-112">Si le mot de passe d’administrateur système **sa** est vide lorsque le mode de sécurité est modifié, le système demande à l’utilisateur d’entrer un mot de passe **sa** .</span><span class="sxs-lookup"><span data-stu-id="7f942-112">If the **sa** password is blank when the security mode is being changed, the user is prompted to enter an **sa** password.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f942-113">La modification de la configuration de la sécurité nécessite un redémarrage du service.</span><span class="sxs-lookup"><span data-stu-id="7f942-113">Changing the security configuration requires a restart of the service.</span></span> <span data-ttu-id="7f942-114">Lorsque vous remplacez l'authentification SQL Server par le mode d'authentification SQL Server et Windows, le compte administrateur système n'est pas automatiquement activé.</span><span class="sxs-lookup"><span data-stu-id="7f942-114">When changing the Server Authentication to SQL Server and Windows Authentication mode the SA account is not automatically enabled.</span></span> <span data-ttu-id="7f942-115">Pour utiliser le compte SA, exécutez [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) avec l’option ENABLE.</span><span class="sxs-lookup"><span data-stu-id="7f942-115">To use the SA account, execute [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) with the ENABLE option.</span></span>  
  
## <a name="login-auditing"></a><span data-ttu-id="7f942-116">Audit de connexion en cours</span><span class="sxs-lookup"><span data-stu-id="7f942-116">Login Auditing</span></span>  
 <span data-ttu-id="7f942-117">**Aucun**</span><span class="sxs-lookup"><span data-stu-id="7f942-117">**None**</span></span>  
 <span data-ttu-id="7f942-118">Désactive l'audit de connexion en cours.</span><span class="sxs-lookup"><span data-stu-id="7f942-118">Turns off login auditing.</span></span>  
  
 <span data-ttu-id="7f942-119">**Échecs de connexion uniquement**</span><span class="sxs-lookup"><span data-stu-id="7f942-119">**Failed logins only**</span></span>  
 <span data-ttu-id="7f942-120">Limite l'audit aux connexions qui ont échoué.</span><span class="sxs-lookup"><span data-stu-id="7f942-120">Audits unsuccessful logins only.</span></span>  
  
 <span data-ttu-id="7f942-121">**Réussites de connexion uniquement**</span><span class="sxs-lookup"><span data-stu-id="7f942-121">**Successful logins only**</span></span>  
 <span data-ttu-id="7f942-122">Limite l'audit aux connexions qui ont réussi.</span><span class="sxs-lookup"><span data-stu-id="7f942-122">Audits successful logins only.</span></span>  
  
 <span data-ttu-id="7f942-123">**Échecs et réussites de connexion**</span><span class="sxs-lookup"><span data-stu-id="7f942-123">**Both failed and successful logins**</span></span>  
 <span data-ttu-id="7f942-124">Effectue l'audit de toutes les tentatives de connexion.</span><span class="sxs-lookup"><span data-stu-id="7f942-124">Audits all login attempts.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f942-125">La modification du niveau d'audit nécessite un redémarrage du service.</span><span class="sxs-lookup"><span data-stu-id="7f942-125">Changing the audit level requires restarting the service.</span></span>  
  
## <a name="server-proxy-account"></a><span data-ttu-id="7f942-126">Compte proxy du serveur</span><span class="sxs-lookup"><span data-stu-id="7f942-126">Server Proxy Account</span></span>  
 <span data-ttu-id="7f942-127">**Activer le compte proxy du serveur**</span><span class="sxs-lookup"><span data-stu-id="7f942-127">**Enable server proxy account**</span></span>  
 <span data-ttu-id="7f942-128">Active un compte destiné à être utilisé par **xp_cmdshell**.</span><span class="sxs-lookup"><span data-stu-id="7f942-128">Enables an account for use by **xp_cmdshell**.</span></span> <span data-ttu-id="7f942-129">Les comptes proxy autorisent l'emprunt d'identité des connexions, rôles du serveur et rôles de la base de données lors de l'exécution d'une commande du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="7f942-129">Proxy accounts allow for the impersonation of logins, server roles, and database roles when an operating system command is being executed.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7f942-130">La connexion utilisée par le compte proxy du serveur doit avoir les privilèges minimum requis pour exécuter le travail prévu.</span><span class="sxs-lookup"><span data-stu-id="7f942-130">The login used by the server proxy account should have the least privileges required to perform the intended work.</span></span> <span data-ttu-id="7f942-131">Des privilèges excessifs pour le compte proxy pourraient être employés par un utilisateur malveillant pour compromettre la sécurité de votre système.</span><span class="sxs-lookup"><span data-stu-id="7f942-131">Excessive privileges for the proxy account could be used by a malicious user to compromise your system security.</span></span>  
  
 <span data-ttu-id="7f942-132">**Compte proxy**</span><span class="sxs-lookup"><span data-stu-id="7f942-132">**Proxy account**</span></span>  
 <span data-ttu-id="7f942-133">Spécifiez le compte proxy utilisé.</span><span class="sxs-lookup"><span data-stu-id="7f942-133">Specify the proxy account used.</span></span>  
  
 <span data-ttu-id="7f942-134">**Mot de passe**</span><span class="sxs-lookup"><span data-stu-id="7f942-134">**Password**</span></span>  
 <span data-ttu-id="7f942-135">Spécifiez le mot de passe du compte proxy.</span><span class="sxs-lookup"><span data-stu-id="7f942-135">Specify the password for the proxy account.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f942-136">Options</span><span class="sxs-lookup"><span data-stu-id="7f942-136">Options</span></span>  
 <span data-ttu-id="7f942-137">**Activer le suivi d'audit C2**</span><span class="sxs-lookup"><span data-stu-id="7f942-137">**Enable C2 audit tracing**</span></span>  
 <span data-ttu-id="7f942-138">Les audits tentent tous d’accéder aux instructions et aux objets et de les enregistrer dans un fichier du répertoire \MSSQL\Data pour les instances par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ou dans le répertoire \MSSQL$*nom_instance*\Data pour les instances nommées de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7f942-138">Audits all attempts to access statements and objects and records them to a file in the \MSSQL\Data directory for default instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or the \MSSQL$*instancename*\Data directory for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7f942-139">Pour plus d’informations, consultez [C2 audit mode (option de configuration de serveur)](c2-audit-mode-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="7f942-139">For more information, see [c2 audit mode Server Configuration Option](c2-audit-mode-server-configuration-option.md).</span></span>  
  
 <span data-ttu-id="7f942-140">**Chaînage des propriétés des bases de données croisées**</span><span class="sxs-lookup"><span data-stu-id="7f942-140">**Cross database ownership chaining**</span></span>  
 <span data-ttu-id="7f942-141">Sélectionnez cette option pour autoriser la base de données comme source ou cible d'une chaîne de propriétés de bases de données croisées.</span><span class="sxs-lookup"><span data-stu-id="7f942-141">Select to allow the database to be the source or target of a cross-database ownership chain.</span></span> <span data-ttu-id="7f942-142">Pour plus d’informations, consultez [cross db ownership chaining (option de configuration de serveur)](cross-db-ownership-chaining-server-configuration-option.md).</span><span class="sxs-lookup"><span data-stu-id="7f942-142">For more information, see [cross db ownership chaining Server Configuration Option](cross-db-ownership-chaining-server-configuration-option.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f942-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7f942-143">See Also</span></span>  
 [<span data-ttu-id="7f942-144">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7f942-144">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
