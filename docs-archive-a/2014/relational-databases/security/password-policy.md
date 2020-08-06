---
title: Stratégie de mot de passe | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- ALTER LOGIN statement
- passwords [SQL Server], policy enforcement
- logins [SQL Server], passwords
- CHECK_EXPIRATION option
- complex passwords [SQL Server]
- passwords [SQL Server], expiration
- manual bad password count resets
- MUST_CHANGE option
- expiration [SQL Server]
- expired password [SQL Server]
- symbols [SQL Server]
- NetValidatePasswordPolicy() API
- passwords [SQL Server]
- password policy [SQL Server]
- resetting bad password counts
- security [SQL Server], passwords
- CHECK_POLICY option
- passwords [SQL Server], symbols
- bad password counts
- passwords [SQL Server], complexity
- characters [SQL Server], password policies
ms.assetid: c0040c0a-a18f-45b9-9c40-0625685649b1
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 902c46b4609a32139450843414a3c4d97b52fcf7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602008"
---
# <a name="password-policy"></a><span data-ttu-id="61cc4-102">Stratégie de mot de passe</span><span class="sxs-lookup"><span data-stu-id="61cc4-102">Password Policy</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="61cc4-103">peut exploiter les mécanismes de stratégie de mot de passe Windows.</span><span class="sxs-lookup"><span data-stu-id="61cc4-103">can use Windows password policy mechanisms.</span></span> <span data-ttu-id="61cc4-104">La stratégie de mot de passe s'applique à une connexion qui utilise l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et à un utilisateur de base de données autonome avec un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="61cc4-104">The password policy applies to a login that uses [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] authentication, and to a contained database user with password.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="61cc4-105">peut appliquer aux mots de passe utilisés dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]des stratégies de complexité et d'expiration identiques à celles de Windows.</span><span class="sxs-lookup"><span data-stu-id="61cc4-105">can apply the same complexity and expiration policies used in Windows to passwords used inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="61cc4-106">Cette fonctionnalité dépend de l'API `NetValidatePasswordPolicy` .</span><span class="sxs-lookup"><span data-stu-id="61cc4-106">This functionality depends on the `NetValidatePasswordPolicy` API.</span></span>  
  
## <a name="password-complexity"></a><span data-ttu-id="61cc4-107">Complexité des mots de passe</span><span class="sxs-lookup"><span data-stu-id="61cc4-107">Password Complexity</span></span>  
 <span data-ttu-id="61cc4-108">Les stratégies de mot de passe complexes sont conçues pour décourager les attaques en augmentant le nombre de mots de passe possibles.</span><span class="sxs-lookup"><span data-stu-id="61cc4-108">Password complexity policies are designed to deter brute force attacks by increasing the number of possible passwords.</span></span> <span data-ttu-id="61cc4-109">Lorsque la stratégie de mot de passe complexe est mise en œuvre, les nouveaux mots de passe doivent respecter les critères suivants :</span><span class="sxs-lookup"><span data-stu-id="61cc4-109">When password complexity policy is enforced, new passwords must meet the following guidelines:</span></span>  
  
-   <span data-ttu-id="61cc4-110">Le mot de passe ne doit pas contenir le nom du compte de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="61cc4-110">The password does not contain the account name of the user.</span></span>  
  
-   <span data-ttu-id="61cc4-111">Les mots de passe doivent compter au moins huit caractères.</span><span class="sxs-lookup"><span data-stu-id="61cc4-111">The password is at least eight characters long.</span></span>  
  
-   <span data-ttu-id="61cc4-112">Les mots de passe doivent contenir des caractères appartenant à trois des quatre catégories suivantes :</span><span class="sxs-lookup"><span data-stu-id="61cc4-112">The password contains characters from three of the following four categories:</span></span>  
  
    -   <span data-ttu-id="61cc4-113">Lettres majuscules de l'alphabet latin (A à Z)</span><span class="sxs-lookup"><span data-stu-id="61cc4-113">Latin uppercase letters (A through Z)</span></span>  
  
    -   <span data-ttu-id="61cc4-114">Lettres minuscules de l'alphabet latin (a à z)</span><span class="sxs-lookup"><span data-stu-id="61cc4-114">Latin lowercase letters (a through z)</span></span>  
  
    -   <span data-ttu-id="61cc4-115">Chiffres de la base 10 (0 à 9)</span><span class="sxs-lookup"><span data-stu-id="61cc4-115">Base 10 digits (0 through 9)</span></span>  
  
    -   <span data-ttu-id="61cc4-116">Caractères non alphanumériques tels que : point d'exclamation (!), symbole dollar ($), signe dièse (#) ou pour cent (%).</span><span class="sxs-lookup"><span data-stu-id="61cc4-116">Non-alphanumeric characters such as: exclamation point (!), dollar sign ($), number sign (#), or percent (%).</span></span>  
  
 <span data-ttu-id="61cc4-117">Les mots de passe peuvent comporter jusqu'à 128 caractères.</span><span class="sxs-lookup"><span data-stu-id="61cc4-117">Passwords can be up to 128 characters long.</span></span> <span data-ttu-id="61cc4-118">Vous devez utiliser des mots de passe aussi longs et complexes que possible.</span><span class="sxs-lookup"><span data-stu-id="61cc4-118">You should use passwords that are as long and complex as possible.</span></span>  
  
## <a name="password-expiration"></a><span data-ttu-id="61cc4-119">Expiration des mots de passe</span><span class="sxs-lookup"><span data-stu-id="61cc4-119">Password Expiration</span></span>  
 <span data-ttu-id="61cc4-120">Les stratégies d'expiration des mots de passe servent à gérer la durée de vie d'un mot de passe.</span><span class="sxs-lookup"><span data-stu-id="61cc4-120">Password expiration policies are used to manage the lifespan of a password.</span></span> <span data-ttu-id="61cc4-121">Lorsque [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] applique la stratégie d'expiration des mots de passe, les utilisateurs sont invités à modifier leurs anciens mots de passe, et les comptes associés à des mots de passe arrivés à expiration sont désactivés.</span><span class="sxs-lookup"><span data-stu-id="61cc4-121">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] enforces password expiration policy, users are reminded to change old passwords, and accounts that have expired passwords are disabled.</span></span>  
  
## <a name="policy-enforcement"></a><span data-ttu-id="61cc4-122">Mode d'application d'une stratégie</span><span class="sxs-lookup"><span data-stu-id="61cc4-122">Policy Enforcement</span></span>  
 <span data-ttu-id="61cc4-123">L'application de la stratégie de mot de passe peut être configurée séparément pour chaque connexion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61cc4-123">The enforcement of password policy can be configured separately for each SQL Server login.</span></span> <span data-ttu-id="61cc4-124">Utilisez [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) pour configurer les options de stratégie de mot de passe d’une connexion SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61cc4-124">Use [ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy options of a SQL Server login.</span></span> <span data-ttu-id="61cc4-125">Les règles suivantes régissent la configuration du mode d'application des stratégies de mot de passe :</span><span class="sxs-lookup"><span data-stu-id="61cc4-125">The following rules apply to the configuration of password policy enforcement:</span></span>  
  
-   <span data-ttu-id="61cc4-126">Lorsque CHECK_POLICY prend la valeur ON, les actions suivantes se produisent :</span><span class="sxs-lookup"><span data-stu-id="61cc4-126">When CHECK_POLICY is changed to ON, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="61cc4-127">CHECK_EXPIRATION prend également la valeur ON, sauf si la valeur OFF est définie explicitement.</span><span class="sxs-lookup"><span data-stu-id="61cc4-127">CHECK_EXPIRATION is also set to ON unless it is explicitly set to OFF.</span></span>  
  
    -   <span data-ttu-id="61cc4-128">L'historique du mot de passe est initialisé avec la valeur du hachage de mot de passe actuel.</span><span class="sxs-lookup"><span data-stu-id="61cc4-128">The password history is initialized with the value of the current password hash.</span></span>  
  
    -   <span data-ttu-id="61cc4-129">Les options**Durée de verrouillage de compte**, **Seuil de verrouillage de compte**et **Réinitialiser le compteur de verrouillages du compte après** sont également activées.</span><span class="sxs-lookup"><span data-stu-id="61cc4-129">**Account lockout duration**, **account lockout threshold**, and **reset account lockout counter after** are also enabled.</span></span>  
  
-   <span data-ttu-id="61cc4-130">Lorsque CHECK_POLICY prend la valeur OFF, les actions suivantes se produisent :</span><span class="sxs-lookup"><span data-stu-id="61cc4-130">When CHECK_POLICY is changed to OFF, the following behaviors occur:</span></span>  
  
    -   <span data-ttu-id="61cc4-131">CHECK_EXPIRATION ON prend également la valeur OFF.</span><span class="sxs-lookup"><span data-stu-id="61cc4-131">CHECK_EXPIRATION is also set to OFF.</span></span>  
  
    -   <span data-ttu-id="61cc4-132">L'historique du mot de passe est supprimé.</span><span class="sxs-lookup"><span data-stu-id="61cc4-132">The password history is cleared.</span></span>  
  
    -   <span data-ttu-id="61cc4-133">La valeur de `lockout_time` est réinitialisée.</span><span class="sxs-lookup"><span data-stu-id="61cc4-133">The value of `lockout_time` is reset.</span></span>  
  
 <span data-ttu-id="61cc4-134">Certaines combinaisons d'options de stratégie ne sont pas prises en charge.</span><span class="sxs-lookup"><span data-stu-id="61cc4-134">Some combinations of policy options are not supported.</span></span>  
  
-   <span data-ttu-id="61cc4-135">Si MUST_CHANGE est spécifié, CHECK_EXPIRATION et CHECK_POLICY doivent prendre la valeur ON.</span><span class="sxs-lookup"><span data-stu-id="61cc4-135">If MUST_CHANGE is specified, CHECK_EXPIRATION and CHECK_POLICY must be set to ON.</span></span> <span data-ttu-id="61cc4-136">Sans quoi, l'instruction échoue.</span><span class="sxs-lookup"><span data-stu-id="61cc4-136">Otherwise, the statement will fail.</span></span>  
  
-   <span data-ttu-id="61cc4-137">Si CHECK_POLICY prend la valeur OFF, CHECK_EXPIRATION ne peut pas prendre la valeur ON.</span><span class="sxs-lookup"><span data-stu-id="61cc4-137">If CHECK_POLICY is set to OFF, CHECK_EXPIRATION cannot be set to ON.</span></span> <span data-ttu-id="61cc4-138">Si cette combinaison d'options est utilisée dans une instruction ALTER LOGIN, l'instruction échoue.</span><span class="sxs-lookup"><span data-stu-id="61cc4-138">An ALTER LOGIN statement that has this combination of options will fail.</span></span>  
  
 <span data-ttu-id="61cc4-139">Le paramètre CHECK_POLICY = ON interdit la création des mots de passe qui sont :</span><span class="sxs-lookup"><span data-stu-id="61cc4-139">Setting CHECK_POLICY = ON will prevent the creation of passwords that are:</span></span>  
  
-   <span data-ttu-id="61cc4-140">NULL ou vides</span><span class="sxs-lookup"><span data-stu-id="61cc4-140">Null or empty</span></span>  
  
-   <span data-ttu-id="61cc4-141">Identiques au nom de l'ordinateur ou de la connexion</span><span class="sxs-lookup"><span data-stu-id="61cc4-141">Same as name of computer or login</span></span>  
  
-   <span data-ttu-id="61cc4-142">Égaux à : « password », « admin », « administrator », « sa », « sysadmin »</span><span class="sxs-lookup"><span data-stu-id="61cc4-142">Any of the following: "password", "admin", "administrator", "sa", "sysadmin"</span></span>  
  
 <span data-ttu-id="61cc4-143">La stratégie de sécurité peut être définie dans Windows ou peut être reçue du domaine.</span><span class="sxs-lookup"><span data-stu-id="61cc4-143">The security policy might be set in Windows, or might be received from the domain.</span></span> <span data-ttu-id="61cc4-144">Pour afficher la stratégie de mot de passe sur l’ordinateur, utilisez le composant logiciel enfichable MMC Stratégie de sécurité locale (**secpol.msc**).</span><span class="sxs-lookup"><span data-stu-id="61cc4-144">To view the password policy on the computer, use the Local Security Policy MMC snap-in (**secpol.msc**).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="61cc4-145">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="61cc4-145">Related Tasks</span></span>  
 [<span data-ttu-id="61cc4-146">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61cc4-146">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
 [<span data-ttu-id="61cc4-147">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61cc4-147">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
 [<span data-ttu-id="61cc4-148">CREATE USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61cc4-148">CREATE USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-user-transact-sql)  
  
 [<span data-ttu-id="61cc4-149">ALTER USER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="61cc4-149">ALTER USER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-user-transact-sql)  
  
 [<span data-ttu-id="61cc4-150">Créer un compte de connexion</span><span class="sxs-lookup"><span data-stu-id="61cc4-150">Create a Login</span></span>](authentication-access/create-a-login.md)  
  
 [<span data-ttu-id="61cc4-151">Créer un utilisateur de base de données</span><span class="sxs-lookup"><span data-stu-id="61cc4-151">Create a Database User</span></span>](authentication-access/create-a-database-user.md)  
  
## <a name="related-content"></a><span data-ttu-id="61cc4-152">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="61cc4-152">Related Content</span></span>  
 [<span data-ttu-id="61cc4-153">Mots de passe forts</span><span class="sxs-lookup"><span data-stu-id="61cc4-153">Strong Passwords</span></span>](strong-passwords.md)  
  
  
