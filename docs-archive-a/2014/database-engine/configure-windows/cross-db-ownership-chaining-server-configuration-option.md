---
title: cross db ownership chaining (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- cross-database ownership chaining
- cross db ownership chaining option
- chaining ownership
ms.assetid: 7b2d49f2-b91c-4aee-a52b-6cc49bed03af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cfb768065cc0aa2aaa7aed0f996b18e46f1da7ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610857"
---
# <a name="cross-db-ownership-chaining-server-configuration-option"></a><span data-ttu-id="874bf-102">cross db ownership chaining (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="874bf-102">cross db ownership chaining Server Configuration Option</span></span>
  <span data-ttu-id="874bf-103">Utilisez l’option **cross db ownership chaining** pour configurer le chaînage des propriétés des bases de données croisées pour une instance de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="874bf-103">Use the **cross db ownership chaining** option to configure cross-database ownership chaining for an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="874bf-104">Cette option de serveur vous permet de contrôler le chaînage des propriétés des bases de données croisées au niveau de la base de données ou d'autoriser le chaînage des propriétés des bases de données croisées pour toutes les bases de données :</span><span class="sxs-lookup"><span data-stu-id="874bf-104">This server option allows you to control cross-database ownership chaining at the database level or to allow cross-database ownership chaining for all databases:</span></span>  
  
-   <span data-ttu-id="874bf-105">Lorsque l’option **cross db ownership chaining** est désactivée (0) pour l’instance, le chaînage des propriétés des bases de données croisées est désactivé pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="874bf-105">When **cross db ownership chaining** is off (0) for the instance, cross-database ownership chaining is disabled for all databases.</span></span>  
  
-   <span data-ttu-id="874bf-106">Lorsque l’option **cross db ownership chaining** est activée (1) pour l’instance, le chaînage des propriétés des bases de données croisées est activé pour toutes les bases de données.</span><span class="sxs-lookup"><span data-stu-id="874bf-106">When **cross db ownership chaining** is on (1) for the instance, cross-database ownership chaining is on for all databases.</span></span>  
  
-   <span data-ttu-id="874bf-107">Vous pouvez définir le chaînage des propriétés des bases de données croisées pour des bases de données spécifiques à l'aide de la clause SET de l'instruction ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="874bf-107">You can set cross-database ownership chaining for individual databases using the SET clause of the ALTER DATABASE statement.</span></span> <span data-ttu-id="874bf-108">Si vous créez une nouvelle base de données, vous pouvez définir l'option de chaînage des propriétés des bases de données croisées pour la nouvelle base de données à l'aide de l'instruction CREATE DATABASE.</span><span class="sxs-lookup"><span data-stu-id="874bf-108">If you are creating a new database, you can set the cross-database ownership chaining option for the new database using the CREATE DATABASE statement.</span></span>  
  
     <span data-ttu-id="874bf-109">Il n’est pas recommandé d’attribuer la valeur 1 à l’option **cross db ownership chaining** , sauf si toutes les bases de données hébergées par l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent participer au chaînage des propriétés des bases de données croisées et que vous êtes conscient de l’impact de ce paramétrage sur la sécurité.</span><span class="sxs-lookup"><span data-stu-id="874bf-109">Setting **cross db ownership chaining** to 1 is not recommended unless all of the databases hosted by the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must participate in cross-database ownership chaining and you are aware of the security implications of this setting.</span></span>  
  
## <a name="controlling-cross-database-ownership-chaining"></a><span data-ttu-id="874bf-110">Contrôle du chaînage des propriétés des bases de données croisées</span><span class="sxs-lookup"><span data-stu-id="874bf-110">Controlling Cross-Database Ownership Chaining</span></span>  
 <span data-ttu-id="874bf-111">Avant d'activer ou de désactiver le chaînage des propriétés des bases de données croisées, prenez en considération les points suivants :</span><span class="sxs-lookup"><span data-stu-id="874bf-111">Before turning cross-database ownership chaining on or off, consider the following:</span></span>  
  
-   <span data-ttu-id="874bf-112">Vous devez être membre du rôle serveur fixe **sysadmin** pour activer ou désactiver le chaînage des propriétés des bases de données croisées.</span><span class="sxs-lookup"><span data-stu-id="874bf-112">You must be a member of the **sysadmin** fixed server role to turn cross-database ownership chaining on or off.</span></span>  
  
-   <span data-ttu-id="874bf-113">Avant de désactiver le chaînage des propriétés des bases de données croisées sur un serveur de production, testez entièrement toutes les applications, y compris les applications de tierces parties, pour vérifier que les modifications n'affectent pas leurs fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="874bf-113">Before turning off cross-database ownership chaining on a production server, fully test all applications, including third-party applications, to ensure that the changes do not affect application functionality.</span></span>  
  
-   <span data-ttu-id="874bf-114">Vous pouvez modifier l’option **cross db ownership chaining** pendant que le serveur est en cours d’exécution si vous spécifiez RECONFIGURE avec **sp_configure**.</span><span class="sxs-lookup"><span data-stu-id="874bf-114">You can change the **cross db ownership chaining** option while the server is running if you specify RECONFIGURE with **sp_configure**.</span></span>  
  
-   <span data-ttu-id="874bf-115">Si des bases de données spécifiques requièrent le chaînage des propriétés des bases de données croisées, il est conseillé de désactiver l’option **cross db ownership chaining** pour l’instance à l’aide de **sp_configure**; ensuite, activez le chaînage des propriétés des bases de données croisées pour les bases de données qui le requièrent à l’aide de l’instruction ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="874bf-115">If you have databases that require cross-database ownership chaining, the recommended practice is to turn off the **cross db ownership chaining** option for the instance using **sp_configure**; then turn on cross-database ownership chaining for individual databases that require it using the ALTER DATABASE statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874bf-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="874bf-116">See Also</span></span>  
 <span data-ttu-id="874bf-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="874bf-117">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="874bf-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="874bf-118">[CREATE DATABASE &#40;SQL Server Transact-SQL&#41;](/sql/t-sql/statements/create-database-sql-server-transact-sql) </span></span>  
 <span data-ttu-id="874bf-119">[Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="874bf-119">[Server Configuration Options &#40;SQL Server&#41;](server-configuration-options-sql-server.md) </span></span>  
 <span data-ttu-id="874bf-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="874bf-120">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 [<span data-ttu-id="874bf-121">RECONFIGURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="874bf-121">RECONFIGURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/reconfigure-transact-sql)  
  
  
