---
title: Préparer SQL Server pour CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- prepSqlSrv
ms.assetid: 20b51dbf-a545-4234-87ae-4228268a0fb2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dafa29d9bdb0c27decb605398a6d1cfe383427e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602264"
---
# <a name="prepare-sql-server-for-cdc"></a><span data-ttu-id="ea5bf-102">Préparer SQL Server pour la capture de données modifiées</span><span class="sxs-lookup"><span data-stu-id="ea5bf-102">Prepare SQL Server for CDC</span></span>
  <span data-ttu-id="ea5bf-103">Le service de capture de données modifiées Oracle requiert que toutes les instances [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cibles contiennent la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-103">The Oracle CDC service requires all target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances to contain the MSXDBCDC database.</span></span> <span data-ttu-id="ea5bf-104">Vous créez cette base de données à l'aide de l'action Préparer SQL Server dans la console de configuration du service de capture de données modifiées.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-104">You create this database using the Prepare SQL Server action in the CDC Service Configuration Console.</span></span> <span data-ttu-id="ea5bf-105">Cela crée un script spécial qui est exécuté pour créer les tables requises, les procédures stockées et autres artefacts nécessaires pour cette base de données.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-105">This creates a special script that is run to create the required tables, stored procedures, and other required artifacts for this database.</span></span> <span data-ttu-id="ea5bf-106">Cette tâche est effectuée une seule fois pour chaque instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-106">This task is done one time only for each target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="ea5bf-107">Pour plus d'informations sur la base de données MSXDBCDC, consultez Base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-107">For more information about the MSXDBCDC database, see The MSXDBCDC Database.</span></span>  
  
 <span data-ttu-id="ea5bf-108">Dans la console de configuration du service de capture de données modifiées, cliquez sur **Préparer SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-108">In the CDC Service Configuration Console, click **Prepare SQL Server**.</span></span> <span data-ttu-id="ea5bf-109">Si cette option n’est pas disponible, vérifiez que **Services de capture de données modifiées locaux** est sélectionné dans le volet gauche de la console.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-109">If this option is not available, make sure that **Local CDC Services** is selected in the left pane of the console.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ea5bf-110">Options</span><span class="sxs-lookup"><span data-stu-id="ea5bf-110">Options</span></span>  
  
### <a name="server-name"></a><span data-ttu-id="ea5bf-111">Nom du serveur</span><span class="sxs-lookup"><span data-stu-id="ea5bf-111">Server Name</span></span>  
 <span data-ttu-id="ea5bf-112">Tapez le nom du serveur où se trouve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea5bf-112">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
### <a name="authentication"></a><span data-ttu-id="ea5bf-113">Authentification</span><span class="sxs-lookup"><span data-stu-id="ea5bf-113">Authentication</span></span>  
 <span data-ttu-id="ea5bf-114">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="ea5bf-114">Select one of the following:</span></span>  
  
-   <span data-ttu-id="ea5bf-115">**Authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="ea5bf-115">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="ea5bf-116">**Authentification SQL Server** : Si vous sélectionnez cette option, vous devez taper le **nom d’utilisateur** et le **mot de passe** de l’utilisateur dans l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-116">**SQL Server Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="ea5bf-117">Pour préparer l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour la capture de données modifiées Oracle, la connexion doit avoir l'autorisation d'écriture dans la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-117">To prepare the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance for Oracle CDC, the login must have write permission to the MSXDBCDC database.</span></span> <span data-ttu-id="ea5bf-118">Entrez les informations d'identification pour une connexion qui a l'autorisation d'écriture dans la base de données MSXDBCDC, telle qu'un membre du rôle `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="ea5bf-118">Enter the credentials for a login that has write permission to the MSXDBCDC database, such as a member of the `sysasmin` role.</span></span>  
  
### <a name="options"></a><span data-ttu-id="ea5bf-119">Options</span><span class="sxs-lookup"><span data-stu-id="ea5bf-119">Options</span></span>  
 <span data-ttu-id="ea5bf-120">Cliquez sur la flèche pour afficher les options disponibles à configurer.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-120">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="ea5bf-121">Vous pouvez choisir de conserver ces options avec leur valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-121">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="ea5bf-122">Options disponibles :</span><span class="sxs-lookup"><span data-stu-id="ea5bf-122">The available options are:</span></span>  
  
-   <span data-ttu-id="ea5bf-123">**Délai de connexion** : Tapez le délai (en secondes) pendant lequel le service de capture de données modifiées pour Oracle attend une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant expiration. La valeur par défaut est **15**.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-123">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="ea5bf-124">**Délai d’exécution** : Tapez le délai (en secondes) pendant lequel le service Windows de capture de données modifiées Oracle attend l'exécution d'une commande avant expiration. La valeur par défaut est **30**.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-124">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="ea5bf-125">**Chiffrer la connexion** : Sélectionnez **Chiffrer la connexion** pour la communication entre le service de capture de données modifiées Oracle et l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible à l'aide d'une connexion chiffrée.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-125">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="ea5bf-126">**Avancé** : Tapez des propriétés de connexion supplémentaires, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-126">**Advanced**: Type any additional connection properties, if necessary.</span></span>  
  
### <a name="view-script"></a><span data-ttu-id="ea5bf-127">Afficher le script</span><span class="sxs-lookup"><span data-stu-id="ea5bf-127">View Script</span></span>  
 <span data-ttu-id="ea5bf-128">Cliquez sur **Afficher le script** pour afficher une version en lecture seule du script d’installation.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-128">Click **View Script** to view a read-only version of the setup script.</span></span> <span data-ttu-id="ea5bf-129">Un administrateur système [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] peut copier ce script dans la console de gestion SQL Server en vue de le modifier et de l'exécuter, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="ea5bf-129">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator can copy this script into the SQL Server Management Console to edit it, if necessary.</span></span> <span data-ttu-id="ea5bf-130">Pour plus d’informations sur le script Préparer SQL Server, consultez [Préparer SQL Server pour Oracle CDC : afficher le script](prepare-sql-server-for-oracle-cdc-view-script.md).</span><span class="sxs-lookup"><span data-stu-id="ea5bf-130">For more information about the Prepare SQL Server Script, see [Prepare SQL Server for Oracle CDC-View Script](prepare-sql-server-for-oracle-cdc-view-script.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5bf-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ea5bf-131">See Also</span></span>  
 <span data-ttu-id="ea5bf-132">[Procédure : utiliser des services de capture de données modifiées](work-with-cdc-services.md) </span><span class="sxs-lookup"><span data-stu-id="ea5bf-132">[How to Work with CDC Services](work-with-cdc-services.md) </span></span>  
 [<span data-ttu-id="ea5bf-133">Guide pratique pour préparer SQL Server pour CDC</span><span class="sxs-lookup"><span data-stu-id="ea5bf-133">How to Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
