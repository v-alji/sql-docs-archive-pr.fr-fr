---
title: TRUSTWORTHY, propriété de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TRUSTWORTHY database property
ms.assetid: 64b2a53d-4416-4a19-acc0-664a61b45348
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 23391fe48037d4cd7f69aef7df6649949301a0f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697656"
---
# <a name="trustworthy-database-property"></a><span data-ttu-id="1788e-102">TRUSTWORTHY, propriété de base de données</span><span class="sxs-lookup"><span data-stu-id="1788e-102">TRUSTWORTHY Database Property</span></span>
  <span data-ttu-id="1788e-103">La propriété de base de données TRUSTWORTHY permet d'indiquer si l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] approuve la base de données et son contenu.</span><span class="sxs-lookup"><span data-stu-id="1788e-103">The TRUSTWORTHY database property is used to indicate whether the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] trusts the database and the contents within it.</span></span> <span data-ttu-id="1788e-104">Par défaut, cette propriété a la valeur OFF, mais peut être définie sur ON à l'aide de l'instruction ALTER DATABASE.</span><span class="sxs-lookup"><span data-stu-id="1788e-104">By default, this setting is OFF, but can be set to ON by using the ALTER DATABASE statement.</span></span> <span data-ttu-id="1788e-105">Par exemple : `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span><span class="sxs-lookup"><span data-stu-id="1788e-105">For example, `ALTER DATABASE AdventureWorks2012 SET TRUSTWORTHY ON;`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1788e-106">Pour définir cette option, vous devez être membre du rôle serveur fixe **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="1788e-106">To set this option, you must be a member of the **sysadmin** fixed server role.</span></span>  
  
 <span data-ttu-id="1788e-107">Cette propriété permet de minimiser certaines menaces résultant de l'attachement d'une base de données contenant l'un des objets suivants :</span><span class="sxs-lookup"><span data-stu-id="1788e-107">This property can be used to reduce certain threats that can exist as a result of attaching a database that contains one of the following objects:</span></span>  
  
-   <span data-ttu-id="1788e-108">Assemblys malveillants dotés d'une autorisation EXTERNAL_ACCESS ou UNSAFE.</span><span class="sxs-lookup"><span data-stu-id="1788e-108">Malicious assemblies with an EXTERNAL_ACCESS or UNSAFE permission setting.</span></span> <span data-ttu-id="1788e-109">Pour plus d’informations, consultez [Sécurité de l’intégration du CLR](../clr-integration/security/clr-integration-security.md).</span><span class="sxs-lookup"><span data-stu-id="1788e-109">For more information, see [CLR Integration Security](../clr-integration/security/clr-integration-security.md).</span></span>  
  
-   <span data-ttu-id="1788e-110">Modules malveillants définis dans le but de s'exécuter en tant qu'utilisateurs à privilèges élevés.</span><span class="sxs-lookup"><span data-stu-id="1788e-110">Malicious modules that are defined to execute as high privileged users.</span></span> <span data-ttu-id="1788e-111">Pour plus d’informations, consultez [Clause EXECUTE AS &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="1788e-111">For more information, see [EXECUTE AS Clause &#40;Transact-SQL&#41;](/sql/t-sql/statements/execute-as-clause-transact-sql).</span></span>  
  
 <span data-ttu-id="1788e-112">Ces deux situations exigent un niveau spécifique de privilèges et sont mises en défaut par des mécanismes appropriés dès lors qu'elles sont utilisées dans le cadre d'une base de données déjà attachée à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1788e-112">Both of these situations require a specific degree of privileges and are protected against by appropriate mechanisms when they are used in the context of a database that is already attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="1788e-113">Toutefois, si la base de données est mise hors ligne, un utilisateur qui a accès au fichier de la base de données peut éventuellement l'attacher à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de son choix et ajouter un contenu malveillant à la base de données.</span><span class="sxs-lookup"><span data-stu-id="1788e-113">However, if the database is taken offline, a user that has access to the database file can potentially attach it to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] of his or her choice and add malicious content to the database.</span></span> <span data-ttu-id="1788e-114">En cas de détachement et d'attachement de bases de données dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], certaines autorisations sont définies dans des fichiers de données et des fichiers journaux pour restreindre l'accès aux fichiers de la base de données.</span><span class="sxs-lookup"><span data-stu-id="1788e-114">When databases are detached and attached in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], certain permissions are set on the data and log files that restrict access to the database files.</span></span>  
  
 <span data-ttu-id="1788e-115">Dans la mesure où il est impossible de faire immédiatement confiance à une base de données qui est attachée à une instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , la base de données n'a pas le droit d'accéder aux ressources au-delà de son étendue tant qu'elle n'a pas été explicitement déclarée fiable.</span><span class="sxs-lookup"><span data-stu-id="1788e-115">Because a database that is attached to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot be immediately trusted, the database is not allowed to access resources beyond the scope of the database until the database is explicitly marked trustworthy.</span></span> <span data-ttu-id="1788e-116">De plus, les modules conçus pour accéder aux ressources extérieures à la base de données et les assemblys dotés des autorisations EXTERNAL_ACCESS ou UNSAFE ont des impératifs supplémentaires à respecter pour pouvoir s'exécuter correctement.</span><span class="sxs-lookup"><span data-stu-id="1788e-116">Also, modules that are designed to access resources outside the database, and assemblies with either the EXTERNAL_ACCESS and UNSAFE permission setting, have additional requirements in order to run successfully.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="1788e-117">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="1788e-117">Related Content</span></span>  
 [<span data-ttu-id="1788e-118">Centre de sécurité pour le moteur de base de données SQL Server et Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="1788e-118">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
 [<span data-ttu-id="1788e-119">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="1788e-119">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
  
