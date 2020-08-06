---
title: Mettre à niveau le schéma des bases de données DQS après avoir installé la mise à jour SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: c8f3fbae-02c4-464d-a35c-7108f48c58cb
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 80a1714ea250cf7cf5d34bc9d208a42a64284308
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610873"
---
# <a name="upgrade-dqs-databases-schema-after-installing-sql-server-update"></a><span data-ttu-id="9b8db-102">Mettre à niveau le schéma des bases de données DQS après avoir installé la mise à jour SQL Server</span><span class="sxs-lookup"><span data-stu-id="9b8db-102">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>
  <span data-ttu-id="9b8db-103">Après avoir installé une mise à jour SQL Server (correctif, correctif logiciel ou mise à jour cumulative) sur une instance DQS configurée précédemment, vous pouvez être amené à mettre à niveau le schéma des bases de données DQS en exécutant le fichier DQSInstaller.exe avec le paramètre de ligne de commande **upgrade** .</span><span class="sxs-lookup"><span data-stu-id="9b8db-103">After you have installed a SQL Server update (patch, hotfix, or cumulative update) on a previously configured DQS instance, you might have to upgrade the DQS databases schema by running the DQSInstaller.exe file with the **upgrade** command line parameter.</span></span> <span data-ttu-id="9b8db-104">Sinon, l'erreur suivante peut s'afficher lors de la tentative de connexion au serveur de qualité des données à l'aide de votre client de qualité des données :</span><span class="sxs-lookup"><span data-stu-id="9b8db-104">Otherwise, you might receive the following error while trying to connect to Data Quality Server using your Data Quality Client:</span></span>  
  
```  
An error occurred in the Microsoft .NET Framework while trying to load assembly id 65581.  
```  
  
 <span data-ttu-id="9b8db-105">La mise à niveau du schéma des bases de données DQS n'a aucun effet sur les données existantes dans les bases de données DQS (bases de connaissances, projets de qualité des données et résultats exportés dans la base de données DQS_STAGING_DATA).</span><span class="sxs-lookup"><span data-stu-id="9b8db-105">Upgrading DQS databases schema does not impact your existing data in the DQS databases (knowledge bases, data quality projects, and exported results in the DQS_STAGING_DATA database).</span></span> <span data-ttu-id="9b8db-106">Cependant, vous devez sauvegarder vos bases de données DQS avant de mettre à niveau le schéma des bases de données DQS afin d'empêcher toute perte accidentelle de données lors de la mise à niveau du schéma.</span><span class="sxs-lookup"><span data-stu-id="9b8db-106">However, you must back up your DQS databases before upgrading DQS databases schema to prevent any accidental data loss during the schema upgrade.</span></span> <span data-ttu-id="9b8db-107">Pour plus d'informations sur la sauvegarde des bases de données DQS, consultez [Sauvegarde et restauration de bases de données DQS](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9b8db-107">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9b8db-108">La majorité des mises à jour SQL Server nécessite une mise à niveau du schéma des bases de données DQS.</span><span class="sxs-lookup"><span data-stu-id="9b8db-108">Most of the SQL Server updates will require an upgrade to the DQS databases schema.</span></span> <span data-ttu-id="9b8db-109">Pour plus d’informations sur les mises à jour SQL Server qui nécessitent une mise à niveau du schéma des bases de données DQS, consultez le graphique à l’étape 1.A dans [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565)(Mise à niveau de DQS : installation de mises à jour cumulatives ou de correctifs logiciels sur Data Quality Services.</span><span class="sxs-lookup"><span data-stu-id="9b8db-109">For information about the SQL Server updates that will require an upgrade to the DQS databases schema, see the chart in step 1.A in [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9b8db-110">Prérequis</span><span class="sxs-lookup"><span data-stu-id="9b8db-110">Prerequisites</span></span>  
  
-   <span data-ttu-id="9b8db-111">Vous devez être connecté en tant que membre du groupe Administrateurs sur l'ordinateur [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9b8db-111">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="9b8db-112">Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe sysadmin dans l'instance de SQL Server où le [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="9b8db-112">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-dqs-databases-schema"></a><span data-ttu-id="9b8db-113">Pour mettre à niveau le schéma des bases de données DQS</span><span class="sxs-lookup"><span data-stu-id="9b8db-113">To upgrade DQS databases schema</span></span>  
  
1.  <span data-ttu-id="9b8db-114">(Recommandé) Sauvegardez vos bases de données DQS avant de mettre à niveau le schéma.</span><span class="sxs-lookup"><span data-stu-id="9b8db-114">(Recommended) Back up your DQS databases before you proceed with the schema upgrade.</span></span> <span data-ttu-id="9b8db-115">Pour plus d'informations sur la sauvegarde des bases de données DQS, consultez [Sauvegarde et restauration de bases de données DQS](../backing-up-and-restoring-dqs-databases.md).</span><span class="sxs-lookup"><span data-stu-id="9b8db-115">For information about backing up DQS databases, see [Backing Up and Restoring DQS Databases](../backing-up-and-restoring-dqs-databases.md).</span></span>  
  
2.  <span data-ttu-id="9b8db-116">Démarrez l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="9b8db-116">Start Command Prompt.</span></span>  
  
3.  <span data-ttu-id="9b8db-117">À l'invite de commandes, remplacez votre répertoire à l'emplacement où DQSInstaller.exe est disponible.</span><span class="sxs-lookup"><span data-stu-id="9b8db-117">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="9b8db-118">Si vous avez installé l'instance par défaut de SQL Server, le fichier DQSInstaller.exe sera copié sous C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn :</span><span class="sxs-lookup"><span data-stu-id="9b8db-118">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
4.  <span data-ttu-id="9b8db-119">À l'invite de commandes, tapez la commande suivante et appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="9b8db-119">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgrade  
    ```  
  
5.  <span data-ttu-id="9b8db-120">Le programme d'installation vous invite à sauvegarder les bases de données DQS avant de continuer.</span><span class="sxs-lookup"><span data-stu-id="9b8db-120">The installer prompts you for backing up the DQS databases before proceeding.</span></span> <span data-ttu-id="9b8db-121">Si vous avez déjà sauvegardé vos bases de données DQS, tapez `Y` ou `Yes`, puis appuyez sur Entrée pour poursuivre la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="9b8db-121">If you have already backed up your DQS databases, type `Y` or `Yes` and press ENTER to continue with the upgrade.</span></span>  
  
6.  <span data-ttu-id="9b8db-122">Un message d'achèvement s'affiche une fois la mise à niveau du schéma des bases de données DQS terminée.</span><span class="sxs-lookup"><span data-stu-id="9b8db-122">A completion message is displayed after successful upgrade of the DQS databases schema.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9b8db-123">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="9b8db-123">Next Steps</span></span>  
 <span data-ttu-id="9b8db-124">Connectez-vous au serveur de qualité des données à partir d'une application client de qualité des données.</span><span class="sxs-lookup"><span data-stu-id="9b8db-124">Log on to the upgraded Data Quality Server from a Data Quality Client application.</span></span>  
  
 <span data-ttu-id="9b8db-125">Pour plus d’informations sur la mise à niveau du schéma des bases de données DQS après l’installation des mises à jour SQL Server et les procédures de dépannage associées, consultez [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565)(Mise à niveau de DQS : installation de mises à jour cumulatives ou de correctifs logiciels sur Data Quality Services).</span><span class="sxs-lookup"><span data-stu-id="9b8db-125">For more information about upgrading DQS databases schema after installing SQL Server updates and associated troubleshooting steps, see [Upgrade DQS: Installing Cumulative Updates or Hotfix Patches on Data Quality Services](https://go.microsoft.com/fwlink/?LinkID=251565).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b8db-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b8db-126">See Also</span></span>  
 <span data-ttu-id="9b8db-127">[Installer Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="9b8db-127">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="9b8db-128">Mettre à niveau des assemblys SQLCLR après une mise à jour de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9b8db-128">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>](upgrade-sqlclr-assemblies-after-net-framework-update.md)  
  
  
