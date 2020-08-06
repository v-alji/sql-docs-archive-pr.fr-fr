---
title: Changer le mode d’authentification du serveur | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- sa account
- authentication [SQL Server], changing modes
- server authentication mode [SQL Server]
- modifying server authentication mode
ms.assetid: 79babcf8-19fd-4495-b8eb-453dc575cac0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8bda31ca7d0c5949173a9a3e5ea656c1757c04f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707879"
---
# <a name="change-server-authentication-mode"></a><span data-ttu-id="0c5f9-102">Changer le mode d'authentification du serveur</span><span class="sxs-lookup"><span data-stu-id="0c5f9-102">Change Server Authentication Mode</span></span>
  <span data-ttu-id="0c5f9-103">Cette rubrique explique comment modifier le mode d'authentification du serveur dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou de [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c5f9-103">This topic describes how to change the server authentication mode in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="0c5f9-104">Au cours de l’installation, le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] est paramétré sur **Mode d’authentification Windows** ou sur **Mode d’authentification SQL Server et Windows**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-104">During installation, [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] is set to either **Windows Authentication mode** or **SQL Server and Windows Authentication mode**.</span></span> <span data-ttu-id="0c5f9-105">Après l'installation, vous pouvez modifier le mode d'authentification à tout moment.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-105">After installation, you can change the authentication mode at any time.</span></span>  
  
 <span data-ttu-id="0c5f9-106">Si vous sélectionnez le **Mode d’authentification Windows** au cours de l’installation, la connexion sa est désactivée et un mot de passe est attribué par le programme d’installation.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-106">If **Windows Authentication mode** is selected during installation, the sa login is disabled and a password is assigned by setup.</span></span> <span data-ttu-id="0c5f9-107">Si vous remplacez ensuite le mode d’authentification par **Mode d’authentification SQL Server et Windows**, la connexion sa reste désactivée.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-107">If you later change authentication mode to **SQL Server and Windows Authentication mode**, the sa login remains disabled.</span></span> <span data-ttu-id="0c5f9-108">Pour utiliser la connexion sa, utilisez l’instruction ALTER LOGIN de façon à activer la connexion et attribuer un nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-108">To use the sa login, use the ALTER LOGIN statement to enable the sa login and assign a new password.</span></span> <span data-ttu-id="0c5f9-109">La connexion sa au serveur est possible uniquement via l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c5f9-109">The sa login can only connect to the server by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span>  
  
 <span data-ttu-id="0c5f9-110">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="0c5f9-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="0c5f9-111">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="0c5f9-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="0c5f9-112">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0c5f9-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="0c5f9-113">**Pour modifier le mode d'authentification du serveur, utilisez :**</span><span class="sxs-lookup"><span data-stu-id="0c5f9-113">**To change server authentication mode, using:**</span></span>  
  
     [<span data-ttu-id="0c5f9-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c5f9-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="0c5f9-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c5f9-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c5f9-116">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="0c5f9-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="0c5f9-117">Sécurité</span><span class="sxs-lookup"><span data-stu-id="0c5f9-117">Security</span></span>  
 <span data-ttu-id="0c5f9-118">Le compte sa est un compte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bien connu qui est souvent la cible d'utilisateurs malveillants.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-118">The sa account is a well-known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] account and it is often targeted by malicious users.</span></span> <span data-ttu-id="0c5f9-119">N'activez pas le compte sa à moins que votre application l'exige.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-119">Do not enable the sa account unless your application requires it.</span></span> <span data-ttu-id="0c5f9-120">Il est très important que vous utilisiez un mot de passe fort pour la connexion sa.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-120">It is very important that you use a strong password for the sa login.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="0c5f9-121">Utilisation de SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0c5f9-121">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-change-security-authentication-mode"></a><span data-ttu-id="0c5f9-122">Pour modifier le mode d'authentification de sécurité</span><span class="sxs-lookup"><span data-stu-id="0c5f9-122">To change security authentication mode</span></span>  
  
1.  <span data-ttu-id="0c5f9-123">Dans l’Explorateur d’objets de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez avec le bouton droit sur le serveur, puis sélectionnez **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-123">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] Object Explorer, right-click the server, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0c5f9-124">Dans la page **Sécurité** , sous **Authentification du serveur**, sélectionnez le nouveau mode d'authentification du serveur, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-124">On the **Security** page, under **Server authentication**, select the new server authentication mode, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="0c5f9-125">Dans la boîte de dialogue [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] , cliquez sur **OK** pour accepter le message indiquant la nécessité de redémarrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c5f9-125">In the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] dialog box, click **OK** to acknowledge the requirement to restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="0c5f9-126">Dans l’Explorateur d’objets, cliquez avec le bouton droit sur votre serveur, puis cliquez sur **Redémarrer**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-126">In Object Explorer, right-click your server, and then click **Restart**.</span></span> <span data-ttu-id="0c5f9-127">S'il est en cours d'exécution, l'Agent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doit également être redémarré.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-127">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent is running, it must also be restarted.</span></span>  
  
#### <a name="to-enable-the-sa-login"></a><span data-ttu-id="0c5f9-128">Pour activer la connexion sa</span><span class="sxs-lookup"><span data-stu-id="0c5f9-128">To enable the sa login</span></span>  
  
1.  <span data-ttu-id="0c5f9-129">Dans l’Explorateur d’objets, développez **sécurité**, puis connexions, cliquez avec le bouton droit sur `sa` , puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-129">In Object Explorer, expand **Security**, expand Logins, right-click `sa`, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0c5f9-130">Sur la page **Général** , vous devrez peut-être créer et confirmer un mot de passe pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-130">On the **General** page, you might have to create and confirm a password for the  login.</span></span>  
  
3.  <span data-ttu-id="0c5f9-131">Sur la page **État** , dans la section **Connexion** , cliquez sur **Activée**, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-131">On the **Status** page, in the **Login** section, click **Enabled**, and then click **OK**.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="0c5f9-132">Utilisation de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="0c5f9-132">Using Transact-SQL</span></span>  
 <span data-ttu-id="0c5f9-133">**Pour activer la connexion sa**</span><span class="sxs-lookup"><span data-stu-id="0c5f9-133">**To enable the sa login**</span></span>  
  
1.  <span data-ttu-id="0c5f9-134">Dans l'Explorateur d'objets, connectez-vous à une instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c5f9-134">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="0c5f9-135">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-135">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="0c5f9-136">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-136">Copy and paste the following example into the query window and click **Execute**.</span></span> <span data-ttu-id="0c5f9-137">L’exemple suivant active la connexion sa et définit un nouveau mot de passe.</span><span class="sxs-lookup"><span data-stu-id="0c5f9-137">The following example enables the sa login and sets a new password.</span></span>  
  
    ```  
    ALTER LOGIN sa ENABLE ;  
    GO  
    ALTER LOGIN sa WITH PASSWORD = '<enterStrongPasswordHere>' ;  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0c5f9-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c5f9-138">See Also</span></span>  
 <span data-ttu-id="0c5f9-139">[Mots de passe forts](../../relational-databases/security/strong-passwords.md) </span><span class="sxs-lookup"><span data-stu-id="0c5f9-139">[Strong Passwords](../../relational-databases/security/strong-passwords.md) </span></span>  
 <span data-ttu-id="0c5f9-140">[Considérations sur la sécurité pour une installation SQL Server](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span><span class="sxs-lookup"><span data-stu-id="0c5f9-140">[Security Considerations for a SQL Server Installation](../../sql-server/install/security-considerations-for-a-sql-server-installation.md) </span></span>  
 <span data-ttu-id="0c5f9-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="0c5f9-141">[ALTER LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-login-transact-sql) </span></span>  
 [<span data-ttu-id="0c5f9-142">Se connecter à SQL Server lorsque les administrateurs système n'y ont plus accès</span><span class="sxs-lookup"><span data-stu-id="0c5f9-142">Connect to SQL Server When System Administrators Are Locked Out</span></span>](connect-to-sql-server-when-system-administrators-are-locked-out.md)  
  
  
