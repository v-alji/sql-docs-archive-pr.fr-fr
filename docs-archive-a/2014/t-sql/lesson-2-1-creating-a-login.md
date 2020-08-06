---
title: Création d’une connexion | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating a login
ms.assetid: a2512310-bdb6-41dc-858a-e866b2b58afc
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 400a57693fbea10270a51f5735a19b9639112ce9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705812"
---
# <a name="creating-a-login"></a><span data-ttu-id="1ebf5-102">Création d'une connexion</span><span class="sxs-lookup"><span data-stu-id="1ebf5-102">Creating a Login</span></span>
  <span data-ttu-id="1ebf5-103">Pour accéder au [!INCLUDE[ssDE](../includes/ssde-md.md)], les utilisateurs ont besoin d’une connexion.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-103">To access the [!INCLUDE[ssDE](../includes/ssde-md.md)], users require a login.</span></span> <span data-ttu-id="1ebf5-104">Cette connexion peut représenter l’identité de l’utilisateur sous forme d’un compte Windows ou d’un membre d’un groupe Windows, ou la connexion peut être une connexion [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] qui existe uniquement dans [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ebf5-104">The login can represent the user's identity as a Windows account or as a member of a Windows group, or the login can be a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login that exists only in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ebf5-105">Chaque fois que vous en avez la possibilité, utilisez l’authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-105">Whenever possible you should use Windows Authentication.</span></span>  
  
 <span data-ttu-id="1ebf5-106">Par défaut, les administrateurs de votre ordinateur ont un accès complet à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ebf5-106">By default, administrators on your computer have full access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ebf5-107">Dans le cadre de cette leçon, l'utilisateur a moins de privilèges ; par conséquent, vous allez créer un nouveau compte d'authentification Windows local sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-107">For this lesson, we want to have a less privileged user; therefore, you will create a new local Windows Authentication account on your computer.</span></span> <span data-ttu-id="1ebf5-108">Pour ce faire, vous devez être administrateur de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-108">To do this, you must be an administrator on your computer.</span></span> <span data-ttu-id="1ebf5-109">Puis vous allez octroyer à ce nouvel utilisateur l'accès à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ebf5-109">Then you will grant that new user access to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-create-a-new-windows-account"></a><span data-ttu-id="1ebf5-110">Pour créer un nouveau compte Windows</span><span class="sxs-lookup"><span data-stu-id="1ebf5-110">To create a new Windows account</span></span>  
  
1.  <span data-ttu-id="1ebf5-111">Cliquez sur **Démarrer**, sur **exécuter**, dans la zone **ouvrir** , tapez `%SystemRoot%\system32\compmgmt.msc /s` , puis cliquez sur **OK** pour ouvrir le programme gestion de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-111">Click **Start**, click **Run**, in the **Open** box, type `%SystemRoot%\system32\compmgmt.msc /s`, and then click **OK** to open the Computer Management program.</span></span>  
  
2.  <span data-ttu-id="1ebf5-112">Sous **Outils système**, développez **Utilisateurs et groupes locaux**, cliquez avec le bouton droit sur **Utilisateurs**, puis cliquez sur **Nouvel utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-112">Under **System Tools**, expand **Local Users and Groups**, right-click **Users**, and then click **New User**.</span></span>  
  
3.  <span data-ttu-id="1ebf5-113">Dans la zone **Nom d’utilisateur** , tapez **Mary**.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-113">In the **User name** box type **Mary**.</span></span>  
  
4.  <span data-ttu-id="1ebf5-114">Dans les zones **Mot de passe** et **Confirmer le mot de passe** , tapez un mot de passe fort, puis cliquez sur **Créer** pour créer un utilisateur Windows local.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-114">In the **Password** and **Confirm password** box, type a strong password, and then click **Create** to create a new local Windows user.</span></span>  
  
### <a name="to-create-a-login"></a><span data-ttu-id="1ebf5-115">Pour créer une connexion</span><span class="sxs-lookup"><span data-stu-id="1ebf5-115">To create a login</span></span>  
  
1.  <span data-ttu-id="1ebf5-116">Dans une fenêtre de l'Éditeur de requête [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], tapez et exécutez le code suivant en remplaçant `computer_name` par le nom de votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-116">In a Query Editor window of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], type and execute the following code replacing `computer_name` with the name of your computer.</span></span> <span data-ttu-id="1ebf5-117">`FROM WINDOWS` indique que Windows va authentifier l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-117">`FROM WINDOWS` indicates that Windows will authenticate the user.</span></span> <span data-ttu-id="1ebf5-118">L'argument `DEFAULT_DATABASE` facultatif connecte `Mary` à la base de données `TestData` , sauf si sa chaîne de connexion indique une autre base de données.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-118">The optional `DEFAULT_DATABASE` argument connects `Mary` to the `TestData` database, unless her connection string indicates another database.</span></span> <span data-ttu-id="1ebf5-119">Cette instruction introduit le point-virgule comme arrêt facultatif pour une instruction [!INCLUDE[tsql](../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1ebf5-119">This statement introduces the semicolon as an optional termination for a [!INCLUDE[tsql](../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    CREATE LOGIN [computer_name\Mary]  
        FROM WINDOWS  
        WITH DEFAULT_DATABASE = [TestData];  
    GO  
    ```  
  
     <span data-ttu-id="1ebf5-120">Cela autorise un nom d'utilisateur, `Mary`, authentifié par votre ordinateur, d'accéder à cette instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1ebf5-120">This authorizes a user name `Mary`, authenticated by your computer, to access this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1ebf5-121">Si votre ordinateur a plus d’une instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , vous devez créer la connexion sur chaque instance à laquelle `Mary` doit accéder.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-121">If there is more than one instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] on the computer, you must create the login on each instance that `Mary` must access.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1ebf5-122">Étant donné que `Mary` n'est pas un compte de domaine, ce nom d'utilisateur ne peut être authentifié que sur cet ordinateur.</span><span class="sxs-lookup"><span data-stu-id="1ebf5-122">Because `Mary` is not a domain account, this user name can only be authenticated on this computer.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="1ebf5-123">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="1ebf5-123">Next Task in Lesson</span></span>  
 [<span data-ttu-id="1ebf5-124">Octroi de l'accès à une base de données</span><span class="sxs-lookup"><span data-stu-id="1ebf5-124">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ebf5-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ebf5-125">See Also</span></span>  
 <span data-ttu-id="1ebf5-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1ebf5-126">[CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql) </span></span>  
 [<span data-ttu-id="1ebf5-127">Choisir un mode d’authentification</span><span class="sxs-lookup"><span data-stu-id="1ebf5-127">Choose an Authentication Mode</span></span>](../relational-databases/security/choose-an-authentication-mode.md)  
  
  
