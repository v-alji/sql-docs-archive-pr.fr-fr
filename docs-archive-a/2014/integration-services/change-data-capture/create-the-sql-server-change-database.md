---
title: Créer la base de données de modifications SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- oraIns
ms.assetid: 4f79c24a-e99a-4a06-8637-51eeec406259
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0eaeb26d5bea4c9e50db29aaa45297ba763dbbfa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707720"
---
# <a name="create-the-sql-server-change-database"></a><span data-ttu-id="47363-102">Créer la base de données de modification SQL Server</span><span class="sxs-lookup"><span data-stu-id="47363-102">Create the SQL Server Change Database</span></span>
  <span data-ttu-id="47363-103">Lorsque vous démarrez l'Assistant Nouvelle instance, la page Créer une base de données CDC s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="47363-103">When you start the New Instance wizard, the Create CDC Database page opens.</span></span> <span data-ttu-id="47363-104">Cette page permet de fournir des informations sur la nouvelle instance de capture de données modifiées et de créer une nouvelle base de données de modification.</span><span class="sxs-lookup"><span data-stu-id="47363-104">Use the Create CDC Database page to provide information about the new CDC instance and create a new Change database.</span></span>  
  
 <span data-ttu-id="47363-105">Lorsque vous créez une base de données CDC, elle est activée pour SQL Server CDC et cette activation requiert une connexion membre du rôle serveur fixe `sysadmin` .</span><span class="sxs-lookup"><span data-stu-id="47363-105">When you create a new CDC database it is enabled for SQL Server CDC and this enablement requires a login that is a member of the `sysadmin` fixed-server role.</span></span>  
  
 <span data-ttu-id="47363-106">Lorsqu'un utilisateur qui démarre l'Assistant Création d'une instance Oracle CDC n'est pas membre du rôle serveur fixe `sysadmin` , la boîte de dialogue Connexion à SQL Server s'ouvre et vous invite à entrer les informations d'identification pour un membre du rôle sysadmin de façon à effectuer la tâche Activer la base de données pour SQL Server CDC.</span><span class="sxs-lookup"><span data-stu-id="47363-106">When a user that starts the Create an Oracle CDC Instance wizard is not a member of the `sysadmin` fixed-server role, the Connect to SQL Server dialog box opens and requests the credentials for a member of the sysadmin role to carry out the Enable the database for SQL Server CDC task.</span></span> <span data-ttu-id="47363-107">Lorsque la base de données CDC est créée, la connexion `sysadmin` est ignorée et la tâche reprend avec la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] d'origine utilisée lorsque la console du concepteur Oracle a été ouverte.</span><span class="sxs-lookup"><span data-stu-id="47363-107">When the CDC database is created, the `sysadmin` login is discarded and work resumes with the original [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used when the Oracle Designer Console was entered.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="47363-108">Pour les tâches autres que l’activation de la base de données pour SQL Server CDC, la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisée pour exécuter l’Assistant Nouvelle instance doit disposer du rôle serveur fixe `dbcreator` et des autorisations UPDATE sur la base de données MSXDBCDC.</span><span class="sxs-lookup"><span data-stu-id="47363-108">For tasks other than Enable the database for SQL Server CDC of, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login used for running the New Instance Wizard must have the `dbcreator` fixed-server role and UPDATE permissions on the MSXDBCDC database.</span></span>  
  
 <span data-ttu-id="47363-109">Pour plus d'informations sur la saisie de données dans la boîte de dialogue Connexion à SQL Server, consultez [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span><span class="sxs-lookup"><span data-stu-id="47363-109">For information on entering the data in the Connect to SQL Server dialog box, see [SQL Server Connection for Instance Creation](sql-server-connection-for-instance-creation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="47363-110">Options</span><span class="sxs-lookup"><span data-stu-id="47363-110">Options</span></span>  
 <span data-ttu-id="47363-111">**Instance Oracle CDC**</span><span class="sxs-lookup"><span data-stu-id="47363-111">**Oracle CDC Instance**</span></span>  
 <span data-ttu-id="47363-112">Entrez les informations suivantes sur l'instance CDC que vous créez.</span><span class="sxs-lookup"><span data-stu-id="47363-112">Type the following information about the CDC instance you are creating.</span></span>  
  
-   <span data-ttu-id="47363-113">**Nom**: tapez le nom du nouveau service.</span><span class="sxs-lookup"><span data-stu-id="47363-113">**Name**: Type a name for the new service.</span></span> <span data-ttu-id="47363-114">Ce sera également le nom de la nouvelle base de données modifiée.</span><span class="sxs-lookup"><span data-stu-id="47363-114">This will also be the name of the new Change database.</span></span>  
  
-   <span data-ttu-id="47363-115">**Description**: tapez une description de la nouvelle instance pour vous aider à l'identifier.</span><span class="sxs-lookup"><span data-stu-id="47363-115">**Description**: Type a description for the new instance to help you identify it.</span></span> <span data-ttu-id="47363-116">Ce paramètre est facultatif.</span><span class="sxs-lookup"><span data-stu-id="47363-116">This is optional.</span></span>  
  
 <span data-ttu-id="47363-117">**Base de données modifiée SQL Server**</span><span class="sxs-lookup"><span data-stu-id="47363-117">**SQL Server Change Database**</span></span>  
 <span data-ttu-id="47363-118">Cette section est utilisée pour créer la base de données.</span><span class="sxs-lookup"><span data-stu-id="47363-118">This section is used to create the database.</span></span>  
  
1.  <span data-ttu-id="47363-119">**Modifier la base de données**: nom de la nouvelle base de données modifiée.</span><span class="sxs-lookup"><span data-stu-id="47363-119">**Change Database**: The name of the new Change database.</span></span> <span data-ttu-id="47363-120">Le nom de la base de données est identique au nom donné à l'instance.</span><span class="sxs-lookup"><span data-stu-id="47363-120">The name of the database is the same as the name that you gave to the instance.</span></span> <span data-ttu-id="47363-121">Ce champ en lecture seule affiche le chemin d'accès complet à la base de données.</span><span class="sxs-lookup"><span data-stu-id="47363-121">This read-only field displays the full path to the database.</span></span>  
  
2.  <span data-ttu-id="47363-122">**Créer une base de données**: cliquez sur **Créer une base de données** pour créer la base de données.</span><span class="sxs-lookup"><span data-stu-id="47363-122">**Create Database**: Click **Create Database** to create the database.</span></span>  
  
     <span data-ttu-id="47363-123">Pour créer la base de données, la connexion doit posséder le rôle serveur `sysasmin` .</span><span class="sxs-lookup"><span data-stu-id="47363-123">To create the database, the login must have the `sysasmin` server role.</span></span> <span data-ttu-id="47363-124">Pour plus d'informations, consultez la remarque sur la sécurité ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="47363-124">See the security note above for more information.</span></span>  
  
     <span data-ttu-id="47363-125">Après avoir créé la base de données, vous pouvez cliquer sur **Suivant** pour [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span><span class="sxs-lookup"><span data-stu-id="47363-125">After you create the database, you can click **Next** to [Connect to an Oracle Source Database](connect-to-an-oracle-source-database.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47363-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="47363-126">See Also</span></span>  
 <span data-ttu-id="47363-127">[Procédure : créer l'instance SQL Server de base de données de modifications](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="47363-127">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="47363-128">Service de capture de données modifiées Oracle</span><span class="sxs-lookup"><span data-stu-id="47363-128">The Oracle CDC Service</span></span>](the-oracle-cdc-service.md)  
  
  
