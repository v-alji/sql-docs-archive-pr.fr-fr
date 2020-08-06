---
title: Création des informations d’identification | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- credentials [SQL Server], creating
- authentication [SQL Server], credentials
- logins [SQL Server], credentials
ms.assetid: c1e77e91-2a69-40d9-b8b3-97cffc710586
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23221424699449ac3775b0e805bb02ae0ad233f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697776"
---
# <a name="create-a-credential"></a><span data-ttu-id="9924d-102">Create a Credential</span><span class="sxs-lookup"><span data-stu-id="9924d-102">Create a Credential</span></span>
  <span data-ttu-id="9924d-103">Cette rubrique explique comment créer des informations d'identification dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9924d-103">This topic describes how to create a credential in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9924d-104">Les informations d'identification fournissent un moyen d'autoriser les utilisateurs de l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à avoir une identité en dehors de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9924d-104">Credentials provide a way to allow [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication users to have an identity outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9924d-105">Ceci sert principalement à exécuter du code dans des assemblys avec le jeu d'autorisations EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="9924d-105">This is primarily used to execute code in Assemblies with EXTERNAL_ACCESS permission set.</span></span> <span data-ttu-id="9924d-106">Les informations d'identification peuvent également être utilisées lorsqu'un utilisateur de l'authentification [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a besoin d'accéder à une ressource du domaine, par exemple à un emplacement de fichier pour y stocker une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="9924d-106">Credentials can also be used when a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Authentication user needs access to a domain resource, such as a file location to store a backup.</span></span>  
  
 <span data-ttu-id="9924d-107">Un jeu d'informations d'identification peut être mappé sur plusieurs connexions [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à la fois.</span><span class="sxs-lookup"><span data-stu-id="9924d-107">A credential can be mapped to several [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] logins at the same time.</span></span> <span data-ttu-id="9924d-108">Une connexion [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] ne peut être mappée que sur un seul jeu d'informations d'identification à la fois.</span><span class="sxs-lookup"><span data-stu-id="9924d-108">A [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login can only be mapped to one credential at a time.</span></span> <span data-ttu-id="9924d-109">Après avoir créé des informations d’identification, utilisez **Propriétés de la connexion (page Général)** pour mapper une connexion à un jeu d’informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="9924d-109">After a credential is created, use the **Login Properties (General Page)** to map a login to a credential.</span></span>  
  
 <span data-ttu-id="9924d-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="9924d-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9924d-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="9924d-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9924d-112">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="9924d-112">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9924d-113">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9924d-113">Security</span></span>](#Security)  
  
-   <span data-ttu-id="9924d-114">**Pour créer des informations d'identification, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="9924d-114">**To create a credential, using:**</span></span>  
  
     [<span data-ttu-id="9924d-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9924d-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="9924d-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9924d-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9924d-117">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="9924d-117">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9924d-118">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="9924d-118">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9924d-119">En l'absence d'une information d'identification mappée à une connexion pour le fournisseur, l'information d'identification mappée au compte de service [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] est utilisée.</span><span class="sxs-lookup"><span data-stu-id="9924d-119">If there is no login mapped credential for the provider, the credential mapped to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] service account is used.</span></span>  
  
-   <span data-ttu-id="9924d-120">Une connexion peut avoir plusieurs informations d'identification mappées à elle, à condition qu'elles soient utilisées avec des fournisseurs distinctifs.</span><span class="sxs-lookup"><span data-stu-id="9924d-120">A login can have multiple credentials mapped to it as long as they are used with distinctive providers.</span></span> <span data-ttu-id="9924d-121">Il ne doit y avoir qu'une seule information d'identification mappée par fournisseur par connexion.</span><span class="sxs-lookup"><span data-stu-id="9924d-121">There must be only one mapped credential per provider per login.</span></span> <span data-ttu-id="9924d-122">La même information d'identification peut être mappée à d'autres connexions.</span><span class="sxs-lookup"><span data-stu-id="9924d-122">The same credential can be mapped to other logins.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9924d-123">Sécurité</span><span class="sxs-lookup"><span data-stu-id="9924d-123">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9924d-124">Autorisations</span><span class="sxs-lookup"><span data-stu-id="9924d-124">Permissions</span></span>  
 <span data-ttu-id="9924d-125">Requiert l'autorisation ALTER ANY CREDENTIAL pour créer ou modifier des informations d'identification et une autorisation ALTER ANY LOGIN pour mapper une connexion à des informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="9924d-125">Requires ALTER ANY CREDENTIAL permission to create or modify a credential and ALTER ANY LOGIN permission to map a login to a credential.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="9924d-126">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="9924d-126">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-create-a-credential"></a><span data-ttu-id="9924d-127">Pour créer les informations d'identification</span><span class="sxs-lookup"><span data-stu-id="9924d-127">To create a credential</span></span>  
  
1.  <span data-ttu-id="9924d-128">Dans l’Explorateur d’objets, développez le dossier **Sécurité** .</span><span class="sxs-lookup"><span data-stu-id="9924d-128">In Object Explorer, expand  the **Security** folder.</span></span>  
  
2.  <span data-ttu-id="9924d-129">Cliquez avec le bouton droit sur le dossier **Informations d’identification** et sélectionnez **Nouvelles informations d’identification...** .</span><span class="sxs-lookup"><span data-stu-id="9924d-129">Right-click the **Credentials** folder and select **New Credential...**.</span></span>  
  
3.  <span data-ttu-id="9924d-130">Dans la boîte de dialogue **Nouvelles informations d'identification** , saisissez le nom des information d'identification dans la zone **Nom d'identification** .</span><span class="sxs-lookup"><span data-stu-id="9924d-130">In the **New Credential** dialog box, in the **Credential Name** box, type a name for the credential.</span></span>  
  
4.  <span data-ttu-id="9924d-131">Dans la zone **Identité** , tapez le nom du compte utilisé pour les connexions sortantes (en quittant le contexte de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="9924d-131">In the **Identity** box, type the name of the account used for outgoing connections (when leaving the context of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="9924d-132">En général, il s'agit d'un compte d'utilisateur Windows, mais l'identité peut être un autre type de compte.</span><span class="sxs-lookup"><span data-stu-id="9924d-132">Typically, this will be a Windows user account, but the identity can be an account of another type.</span></span>  
  
     <span data-ttu-id="9924d-133">Vous pouvez également cliquer sur les points de suspension **(...)** pour ouvrir la boîte de dialogue **Sélectionner un utilisateur ou un groupe**.</span><span class="sxs-lookup"><span data-stu-id="9924d-133">Alternately, click the ellipsis **(...)** to open the **Select User or Group** dialog box.</span></span>  
  
5.  <span data-ttu-id="9924d-134">Dans les zones **Mot de passe** et **Confirmer le mot de passe** , tapez le mot de passe du compte indiqué dans la zone **Identité** .</span><span class="sxs-lookup"><span data-stu-id="9924d-134">In the **Password** and **Confirm password** boxes, type the password of the account specified in the **Identity** box.</span></span> <span data-ttu-id="9924d-135">Si **Identité** correspond à un compte d'utilisateur Windows, il s'agit du mot de passe Windows.</span><span class="sxs-lookup"><span data-stu-id="9924d-135">If **Identity** is a Windows user account, this is the Windows password.</span></span> <span data-ttu-id="9924d-136">Si le mot de passe n'est pas requis, la zone **Mot de passe** peut être vide.</span><span class="sxs-lookup"><span data-stu-id="9924d-136">The **Password** can be blank, if no password is required.</span></span>  
  
6.  <span data-ttu-id="9924d-137">Sélectionnez **Utiliser le fournisseur de chiffrement** pour définir les informations d’identification devant être vérifiées par un fournisseur de gestion de clés extensible (EKM).</span><span class="sxs-lookup"><span data-stu-id="9924d-137">Select **Use Encryption Provider** to set the credential to be verified by an Extensible Key Management (EKM) Provider.</span></span> <span data-ttu-id="9924d-138">Pour plus d’informations, consultez [Gestion de clés extensible &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md).</span><span class="sxs-lookup"><span data-stu-id="9924d-138">For more information, see [Extensible Key Management &#40;EKM&#41;](../encryption/extensible-key-management-ekm.md)</span></span>  
  
7.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9924d-139">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9924d-139">Using Transact-SQL</span></span>  
  
###  <a name="to-create-a-credential"></a><a name="Credential"></a><span data-ttu-id="9924d-140">Pour créer des informations d’identification</span><span class="sxs-lookup"><span data-stu-id="9924d-140">To create a credential</span></span>  
  
1.  <span data-ttu-id="9924d-141">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9924d-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="9924d-142">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="9924d-142">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="9924d-143">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="9924d-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Creates the credential called "AlterEgo.".   
    -- The credential contains the Windows user "Mary5" and a password.  
    CREATE CREDENTIAL AlterEgo WITH IDENTITY = 'Mary5',   
        SECRET = '<EnterStrongPasswordHere>';  
    GO  
    ```  
  
 <span data-ttu-id="9924d-144">Pour plus d’informations, consultez [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="9924d-144">For more information, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>  
  
  
