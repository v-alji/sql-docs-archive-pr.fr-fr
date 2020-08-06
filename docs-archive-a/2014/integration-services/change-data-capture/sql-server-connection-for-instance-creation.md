---
title: Connexion SQL Server pour la création d’une instance | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 81d0e7e2-d8f0-4bd9-9565-218ce996f28e
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cdff17b763257c2a3280981c1f5c16040cc61413
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602262"
---
# <a name="sql-server-connection-for-instance-creation"></a><span data-ttu-id="2936c-102">Connexion SQL Server pour la création d'une instance</span><span class="sxs-lookup"><span data-stu-id="2936c-102">SQL Server Connection for Instance Creation</span></span>
  <span data-ttu-id="2936c-103">Une des premières étapes de la création d'une instance Oracle CDC est la création d'une base de données CDC sur l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible.</span><span class="sxs-lookup"><span data-stu-id="2936c-103">One of the first steps when creating an Oracle CDC Instance is the creation of a CDC database on the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="2936c-104">Cette base de données CDC est activée pour SQL Server CDC et cette activation requiert une connexion membre du rôle serveur fixe `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="2936c-104">This CDC database is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="2936c-105">Quand un utilisateur qui démarre l’Assistant **Création d’une instance Oracle CDC** n’est pas membre du rôle serveur fixe `sysadmin` , la boîte de dialogue **Connexion à SQL Server** s’ouvre et vous invite à entrer les informations d’identification pour un membre du rôle `sysadmin` de façon à effectuer la tâche Activer la base de données pour SQL Server CDC.</span><span class="sxs-lookup"><span data-stu-id="2936c-105">When a user that starts the **Create an Oracle CDC Instance** wizard is not a member of the `sysadmin` fixed-server role, the **Connect to SQL Server** dialog box opens and requests the credentials for a member of the `sysadmin` role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="2936c-106">Lorsque la base de données CDC est créée, la connexion `sysadmin` est ignorée et la tâche reprend avec la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'origine utilisée lorsque la console du concepteur Oracle a été ouverte.</span><span class="sxs-lookup"><span data-stu-id="2936c-106">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="2936c-107">Liste des tâches</span><span class="sxs-lookup"><span data-stu-id="2936c-107">Task List</span></span>  
 <span data-ttu-id="2936c-108">Dans la boîte de dialogue **Connexion à SQL Server** , entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2936c-108">Enter the following information in the **Connect to SQL Server** dialog box.</span></span>  
  
 <span data-ttu-id="2936c-109">**Nom de serveur**</span><span class="sxs-lookup"><span data-stu-id="2936c-109">**Server Name**</span></span>  
 <span data-ttu-id="2936c-110">Tapez le nom du serveur où se trouve [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2936c-110">Type the name of the server where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is located.</span></span>  
  
 <span data-ttu-id="2936c-111">**Authentification**</span><span class="sxs-lookup"><span data-stu-id="2936c-111">**Authentication**</span></span>  
 <span data-ttu-id="2936c-112">Sélectionnez l’un des suivants :</span><span class="sxs-lookup"><span data-stu-id="2936c-112">Select one of the following:</span></span>  
  
-   <span data-ttu-id="2936c-113">**Authentification Windows**</span><span class="sxs-lookup"><span data-stu-id="2936c-113">**Windows Authentication**</span></span>  
  
-   <span data-ttu-id="2936c-114">**Authentification SQL Server** : si vous sélectionnez cette option, vous devez taper **l’Identifiant** et le **Mot de passe** de l’utilisateur dans l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] à laquelle vous vous connectez.</span><span class="sxs-lookup"><span data-stu-id="2936c-114">**SQL Server Authentication**: If you select this option, you must type the **Login** and **Password** for the user in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you are connecting to.</span></span>  
  
 <span data-ttu-id="2936c-115">La connexion doit avoir un rôle de base de données qui permet l'accès à la base de données MSXCDCDB.</span><span class="sxs-lookup"><span data-stu-id="2936c-115">The login must have a database role that allows access to the MSXCDCDB database.</span></span> <span data-ttu-id="2936c-116">Il est recommandé que la connexion ait également accès à toutes les bases de données supplémentaires qui sont utilisées, sinon l'utilisateur ne pourra pas afficher les données de ces bases de données.</span><span class="sxs-lookup"><span data-stu-id="2936c-116">It is recommended that the login also have access to any additional databases being used or the user will not be able to view the data in those databases.</span></span>  
  
 <span data-ttu-id="2936c-117">**Options**</span><span class="sxs-lookup"><span data-stu-id="2936c-117">**Options**</span></span>  
 <span data-ttu-id="2936c-118">Cliquez sur la flèche pour afficher les options disponibles à configurer.</span><span class="sxs-lookup"><span data-stu-id="2936c-118">Click the arrow to view available options to be configured.</span></span> <span data-ttu-id="2936c-119">Vous pouvez choisir de conserver ces options avec leur valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="2936c-119">You can choose to leave these options with their default value.</span></span> <span data-ttu-id="2936c-120">Options disponibles :</span><span class="sxs-lookup"><span data-stu-id="2936c-120">The available options are:</span></span>  
  
-   <span data-ttu-id="2936c-121">**Délai de connexion** : Tapez le délai (en secondes) pendant lequel le service de capture de données modifiées pour Oracle attend une connexion à [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] avant expiration. La valeur par défaut est **15**.</span><span class="sxs-lookup"><span data-stu-id="2936c-121">**Connection Timeout**: Type the time (in seconds) that the CDC Service for Oracle waits for a connection to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before timing out. The default value is **15**.</span></span>  
  
-   <span data-ttu-id="2936c-122">**Délai d’exécution** : Tapez le délai (en secondes) pendant lequel le service Windows de capture de données modifiées Oracle attend l'exécution d'une commande avant expiration. La valeur par défaut est **30**.</span><span class="sxs-lookup"><span data-stu-id="2936c-122">**Execution Timeout**: Type the time (in seconds) that the Oracle CDC Windows Service waits for a command to execute before timing out. The default value is **30**.</span></span>  
  
-   <span data-ttu-id="2936c-123">**Chiffrer la connexion** : Sélectionnez **Chiffrer la connexion** pour la communication entre le service de capture de données modifiées Oracle et l'instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cible à l'aide d'une connexion chiffrée.</span><span class="sxs-lookup"><span data-stu-id="2936c-123">**Encrypt Connection**: Select **Encrypt Connection** for communication between the Oracle CDC Service and the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance using an encrypted connection.</span></span>  
  
-   <span data-ttu-id="2936c-124">**Avancé** : Cliquez sur **Avancé** et tapez toutes les propriétés de connexion supplémentaires dans la boîte de dialogue Propriétés avancées de connexion, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="2936c-124">**Advanced**: Click **Advanced** and type any additional connection properties into the Advanced Connection Properties dialog box, if necessary.</span></span>  
  
     <span data-ttu-id="2936c-125">Pour plus d’informations sur la boîte de dialogue Propriétés avancées de connexion, consultez [Propriétés avancées de connexion](advanced-connection-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2936c-125">For information about the Advanced Connection Properties dialog box, see [Advanced Connection Properties](advanced-connection-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2936c-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2936c-126">See Also</span></span>  
 <span data-ttu-id="2936c-127">[Créer la base de données de modification SQL Server](create-the-sql-server-change-database.md) </span><span class="sxs-lookup"><span data-stu-id="2936c-127">[Create the SQL Server Change Database](create-the-sql-server-change-database.md) </span></span>  
 [<span data-ttu-id="2936c-128">Autorisations de connexion SQL Server nécessaires pour le concepteur CDC</span><span class="sxs-lookup"><span data-stu-id="2936c-128">SQL Server Connection Required Permissions for the CDC Designer</span></span>](sql-server-connection-required-permissions-for-the-cdc-designer.md)  
  
  
