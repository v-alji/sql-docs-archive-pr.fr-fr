---
title: Démarrer l'utilitaire sqlcmd
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 00d57437-7a29-4da1-b639-ee990db055fb
author: rothja
ms.author: jroth
ms.openlocfilehash: d71e6f140238599b3f22850ee9b63a0ee25d900b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602027"
---
# <a name="start-the-sqlcmd-utility"></a><span data-ttu-id="49a7a-102">Démarrer l'utilitaire sqlcmd</span><span class="sxs-lookup"><span data-stu-id="49a7a-102">Start the sqlcmd Utility</span></span>
  <span data-ttu-id="49a7a-103">Pour vous servir de l'utilitaire `sqlcmd`, vous devez le lancer, puis vous connecter à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="49a7a-103">To begin using `sqlcmd`, you must first launch the utility and connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="49a7a-104">Vous pouvez vous connecter à une instance par défaut ou nommée.</span><span class="sxs-lookup"><span data-stu-id="49a7a-104">You can connect to either a default or named instance.</span></span> <span data-ttu-id="49a7a-105">La première étape consiste à démarrer l'utilitaire `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="49a7a-105">The first step is to start the `sqlcmd` utility.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49a7a-106">L'authentification Windows est le mode d'authentification par défaut pour `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="49a7a-106">Windows Authentication is the default authentication mode for `sqlcmd`.</span></span> <span data-ttu-id="49a7a-107">Pour utiliser l’authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , vous devez spécifier un nom d’utilisateur et un mot de passe en utilisant les options **-U** et **-P** .</span><span class="sxs-lookup"><span data-stu-id="49a7a-107">To use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication, you must specify a user name and password by using the **-U** and **-P** options.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="49a7a-108"> Par défaut, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] s'installe en tant qu'instance nommée **sqlexpress**.</span><span class="sxs-lookup"><span data-stu-id="49a7a-108">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs as the named instance **sqlexpress**.</span></span>  
  
 <span data-ttu-id="49a7a-109">Si vous ne vous êtes pas connecté préalablement à cette instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], vous devez configurer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour accepter les connexions.</span><span class="sxs-lookup"><span data-stu-id="49a7a-109">If you have not connected to this instance of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] before, you may have to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to accept connections.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-default-instance-of-sql-server"></a><span data-ttu-id="49a7a-110">Pour démarrer l'utilitaire sqlcmd et établir une connexion à une instance par défaut de SQL Server</span><span class="sxs-lookup"><span data-stu-id="49a7a-110">To start the sqlcmd utility and connect to a default instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="49a7a-111">Dans le menu **Démarrer** , cliquez sur **exécuter**.</span><span class="sxs-lookup"><span data-stu-id="49a7a-111">On the **Start** menu click **Run**.</span></span> <span data-ttu-id="49a7a-112">Dans la zone **Ouvrir** , tapez **cmd**, puis cliquez sur **OK** pour ouvrir une fenêtre d'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="49a7a-112">In the **Open** box type **cmd**, and then click **OK** to open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="49a7a-113">À l’invite de commandes, tapez `sqlcmd`.</span><span class="sxs-lookup"><span data-stu-id="49a7a-113">At the command prompt, type `sqlcmd`.</span></span>  
  
3.  <span data-ttu-id="49a7a-114">Appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="49a7a-114">Press ENTER.</span></span>  
  
     <span data-ttu-id="49a7a-115">Vous bénéficiez maintenant d'une connexion approuvée à l'instance par défaut de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] qui est exécutée sur votre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="49a7a-115">You now have a trusted connection to the default instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on your computer.</span></span>  
  
     <span data-ttu-id="49a7a-116">**1>** est l' `sqlcmd` invite qui spécifie le numéro de ligne.</span><span class="sxs-lookup"><span data-stu-id="49a7a-116">**1>** is the `sqlcmd` prompt that specifies the line number.</span></span> <span data-ttu-id="49a7a-117">Chaque fois que vous appuyez sur ENTRÉE, le numéro augmente de un.</span><span class="sxs-lookup"><span data-stu-id="49a7a-117">Each time you press ENTER, the number increases by one.</span></span>  
  
4.  <span data-ttu-id="49a7a-118">Pour mettre fin à la `sqlcmd` session, tapez `EXIT` à l' `sqlcmd` invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="49a7a-118">To end the `sqlcmd` session, type `EXIT` at the `sqlcmd` prompt.</span></span>  
  
### <a name="to-start-the-sqlcmd-utility-and-connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="49a7a-119">Pour démarrer l'utilitaire sqlcmd et établir une connexion à une instance nommée de SQL Server</span><span class="sxs-lookup"><span data-stu-id="49a7a-119">To start the sqlcmd utility and connect to a named instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="49a7a-120">Ouvrez une fenêtre d’invite de commandes, puis tapez `sqlcmd -S` *myServer\instanceName*.</span><span class="sxs-lookup"><span data-stu-id="49a7a-120">Open a Command Prompt window, and type `sqlcmd -S`*myServer\instanceName*.</span></span> <span data-ttu-id="49a7a-121">Remplacez *mon_serveur\nom_instance[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] par le nom de l’ordinateur et de l’instance de* à laquelle vous souhaitez vous connecter.</span><span class="sxs-lookup"><span data-stu-id="49a7a-121">Replace *myServer\instanceName* with the name of the computer and the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that you want to connect to.</span></span>  
  
2.  <span data-ttu-id="49a7a-122">Appuyez sur Entrée.</span><span class="sxs-lookup"><span data-stu-id="49a7a-122">Press ENTER.</span></span>  
  
     <span data-ttu-id="49a7a-123">L' `sqlcmd` invite (1>) indique que vous êtes connecté à l’instance spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="49a7a-123">The `sqlcmd` prompt (1>) indicates that you are connected to the specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="49a7a-124">Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] entrées sont stockées dans une mémoire tampon.</span><span class="sxs-lookup"><span data-stu-id="49a7a-124">Entered [!INCLUDE[tsql](../../includes/tsql-md.md)] statements are stored in a buffer.</span></span> <span data-ttu-id="49a7a-125">Elles sont exécutées en tant que lot lorsque la commande GO est rencontrée.</span><span class="sxs-lookup"><span data-stu-id="49a7a-125">They are executed as a batch when the GO command is encountered.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a7a-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49a7a-126">See Also</span></span>  
 [<span data-ttu-id="49a7a-127">Exécuter des fichiers de script Transact-SQL à l’aide de sqlcmd</span><span class="sxs-lookup"><span data-stu-id="49a7a-127">Run Transact-SQL Script Files Using sqlcmd</span></span>](sqlcmd-run-transact-sql-script-files.md)  
  
  
