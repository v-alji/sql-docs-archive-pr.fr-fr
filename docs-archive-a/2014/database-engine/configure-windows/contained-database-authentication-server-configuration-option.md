---
title: Authentification de la base de données autonome (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- contained_database_authentication_TSQL
- contained database authentication
helpviewer_keywords:
- contained database, enabling
- contained database authentication option
ms.assetid: b80768d2-ac20-4035-a335-d9adb74b3f6e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: cf5bf07c8b0913ff81f31ff0ca64a18eee0f2ac2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611277"
---
# <a name="contained-database-authentication-server-configuration-option"></a><span data-ttu-id="92f46-102">Authentification de la base de données autonome (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="92f46-102">contained database authentication Server Configuration Option</span></span>
  <span data-ttu-id="92f46-103">Utilisez l'option **authentification de la base de données autonome** pour activer des bases de données autonomes sur l'instance du [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f46-103">Use the **contained database authentication** option to enable contained databases on the instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="92f46-104">Cette option de serveur vous permet de contrôler **l’authentification de la base de données autonome**.</span><span class="sxs-lookup"><span data-stu-id="92f46-104">This server option allows you to control **contained database authentication**.</span></span>  
  
-   <span data-ttu-id="92f46-105">Lorsque l'option **authentification de la base de données autonome** est désactivée (0) pour l'instance, les bases de données autonomes ne peuvent pas être créées ou attachées au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f46-105">When **contained database authentication** is off (0) for the instance, contained databases cannot be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="92f46-106">Lorsque l'option **authentification de la base de données autonome** est activée (1) pour l'instance, les bases de données autonomes peuvent être créées ou attachées au [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f46-106">When **contained database authentication** is on (1) for the instance, contained databases can be created, or attached to the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="92f46-107">Une base de données autonome inclut tous les paramètres et métadonnées de la base de données requis pour définir la base de données ; sa configuration ne dépend pas de l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)] où la base de données est installée.</span><span class="sxs-lookup"><span data-stu-id="92f46-107">A contained database includes all database settings and metadata required to define the database and has no configuration dependencies on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] where the database is installed.</span></span> <span data-ttu-id="92f46-108">Les utilisateurs peuvent se connecter à la base de données sans authentifier de connexion au niveau du [!INCLUDE[ssDE](../../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="92f46-108">Users can connect to the database without authenticating a login at the [!INCLUDE[ssDE](../../includes/ssde-md.md)] level.</span></span> <span data-ttu-id="92f46-109">Isoler la base de données du moteur de base de données permet de la déplacer facilement vers une autre instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f46-109">Isolating the database from the Database Engine makes it possible to easily move the database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="92f46-110">Inclure tous les paramètres de base de données dans la base de données permet aux propriétaires de base de données de gérer tous les paramètres de configuration pour la base de données.</span><span class="sxs-lookup"><span data-stu-id="92f46-110">Including all the database settings in the database enables database owners to manage all the configuration settings for the database.</span></span> <span data-ttu-id="92f46-111">Pour plus d'informations sur les bases de données autonomes, consultez [Bases de données autonomes](../../relational-databases/databases/contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="92f46-111">For more information about contained databases, see [Contained Databases](../../relational-databases/databases/contained-databases.md).</span></span>  
  
 <span data-ttu-id="92f46-112">Si une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] comporte des bases de données autonomes, le paramètre **contained database authentication** peut avoir la valeur 0 grâce à l'instruction **RECONFIGURE WITH OVERRIDE** .</span><span class="sxs-lookup"><span data-stu-id="92f46-112">If an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has any contained databases the **contained database authentication** setting can be set to 0 by using the **RECONFIGURE WITH OVERRIDE** statement.</span></span> <span data-ttu-id="92f46-113">Lorsque le paramètre **contained database authentication** a la valeur 0, l'authentification des bases de données autonomes est désactivée.</span><span class="sxs-lookup"><span data-stu-id="92f46-113">Setting **contained database authentication** to 0 will disable contained database authentication for the contained databases.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="92f46-114">Quand des bases de données autonomes sont activées, les utilisateurs de base de données dotés de l'autorisation ALTER ANY USER, comme les membres des rôles de base de données db_owner et db_accessadmin, peuvent accorder l'accès aux bases de données et ce faisant, accorder l'accès à l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f46-114">When contained databases are enabled, database users with the ALTER ANY USER permission, such as members of the db_owner and db_accessadmin database roles, can grant access to databases and by doing so, grant access to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="92f46-115">Cela signifie que le contrôle de l'accès au serveur n'est plus limité aux membres du rôle serveur fixe sysadmin et securityadmin et aux connexions avec le niveau de serveur CONTROL SERVER et l'autorisation ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="92f46-115">This means that control over access to the server is no longer limited to members of the sysadmin and securityadmin fixed server role, and logins with the server level CONTROL SERVER and ALTER ANY LOGIN permission.</span></span> <span data-ttu-id="92f46-116">Avant d'autoriser des bases de données autonomes, vous devez comprendre les risques qui leur sont associés.</span><span class="sxs-lookup"><span data-stu-id="92f46-116">Before allowing contained databases, you should understand the risks associated with contained databases.</span></span> <span data-ttu-id="92f46-117">Pour plus d'informations, consultez [Meilleures pratiques de sécurité recommandées avec les bases de données autonomes](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span><span class="sxs-lookup"><span data-stu-id="92f46-117">For more information, see [Security Best Practices with Contained Databases](../../relational-databases/databases/security-best-practices-with-contained-databases.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="92f46-118">Exemples</span><span class="sxs-lookup"><span data-stu-id="92f46-118">Examples</span></span>  
 <span data-ttu-id="92f46-119">L'exemple suivant active des bases de données autonomes sur l'instance du [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92f46-119">The following example enables contained databases on the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```sql  
sp_configure 'contained database authentication', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="92f46-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="92f46-120">See Also</span></span>  
 <span data-ttu-id="92f46-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="92f46-121">[sp_configure &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql) </span></span>  
 <span data-ttu-id="92f46-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="92f46-122">[RECONFIGURE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/reconfigure-transact-sql) </span></span>  
 [<span data-ttu-id="92f46-123">Options de configuration de serveur &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="92f46-123">Server Configuration Options &#40;SQL Server&#41;</span></span>](server-configuration-options-sql-server.md)  
  
  
