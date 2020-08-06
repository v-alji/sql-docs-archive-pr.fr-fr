---
title: Mettre à niveau des assemblys SQLCLR après une mise à jour de .NET Framework | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: b1a008cc-7e6b-4655-a869-bd429f986400
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 45d60db413e11828f26bd03e1c8f350645838d12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610871"
---
# <a name="upgrade-sqlclr-assemblies-after-net-framework-update"></a><span data-ttu-id="8bd5a-102">Mettre à niveau des assemblys SQLCLR après une mise à jour de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8bd5a-102">Upgrade SQLCLR Assemblies After .NET Framework Update</span></span>
  [!INCLUDE[ssDQSnoversion](../../includes/ssdqsnoversion-md.md)] <span data-ttu-id="8bd5a-103">(DQS) est un ensemble de routines Common Language Runtime SQL (SQLCR) qui font référence à des assemblys Microsoft .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-103">(DQS) is a collection of SQL Common Language Runtime (SQLCR) routines that reference Microsoft .NET Framework 4 assemblies.</span></span> <span data-ttu-id="8bd5a-104">Lorsque vous installez sur votre ordinateur toutes les mises à jour.NET framework qui affectent un tel assembly. NET Framework référencé, cela entraîne une modification dans l'ID de version du module (MVID) de l'assembly dans Global Assembly Cache (GAC).</span><span class="sxs-lookup"><span data-stu-id="8bd5a-104">When you install any .NET Framework updates on your computer that affect any such referenced .NET Framework assembly, it leads to a change in the Module Version ID (MVID) of the assembly in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="8bd5a-105">Cela provoque une discordance entre les MVID de l'assembly référencé dans le GAC et de l'assembly dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bd5a-105">This causes a mismatch between the MVIDs of the referenced assembly in GAC and the assembly in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="8bd5a-106">Si la mise à jour .NET Framework nécessite de redémarrer le [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , les assemblys SQLCLR affectés sont mis à niveau automatiquement pour résoudre le problème d'incompatibilité de MVID au redémarrage du [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bd5a-106">If the .NET Framework update requires you to restart the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, the affected SQLCLR assemblies are upgraded automatically to fix the MVID mismatch issue on restarting the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span> <span data-ttu-id="8bd5a-107">Toutefois, pour les mises à jour .NET Framework qui ne nécessitent pas de redémarrage de votre [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] , une erreur se produit en raison d'une incohérence dans les MVID des assemblys lorsque vous essayez de vous connecter à un [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] à l'aide d'un [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="8bd5a-107">However, for .NET Framework updates that do not require you to restart your [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer, an error occurs due to the mismatch in the MVIDs of the assemblies when you try to connect to a [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] using a [!INCLUDE[ssDQSClient](../../includes/ssdqsclient-md.md)]:</span></span>  
  
```  
A new version of .NET was installed on this machine. In order to continue to work with DQS please run dqsinstaller.exe -upgradedlls.  
```  
  
 <span data-ttu-id="8bd5a-108">Pour résoudre ce problème, les assemblys SQLCLR affectés dans [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] doivent être mis à niveau.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-108">To fix this issue, the affected SQLCLR assemblies in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] must be upgraded.</span></span> <span data-ttu-id="8bd5a-109">Pour ce faire, vous pouvez exécuter le fichier DQSInstaller.exe avec le paramètre de ligne de commande **upgradedlls** pour ignorer la recréation des bases de données DQS et mettre à niveau uniquement les assemblys concernés.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-109">You can do so by running the DQSInstaller.exe file with the **upgradedlls** command line parameter to skip recreating the DQS databases, and just upgrade the affected assemblies.</span></span> <span data-ttu-id="8bd5a-110">Cela garantit que vos bases de connaissances, projets de qualité des données et toutes autres données dans DQS sont conservés.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-110">This ensures that your knowledge bases, data quality projects, and any other data in DQS are preserved.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8bd5a-111">Prérequis</span><span class="sxs-lookup"><span data-stu-id="8bd5a-111">Prerequisites</span></span>  
  
-   <span data-ttu-id="8bd5a-112">Vous devez être connecté en tant que membre du groupe Administrateurs sur l'ordinateur [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8bd5a-112">You must be logged on as a member of the Administrators group on the [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] computer.</span></span>  
  
-   <span data-ttu-id="8bd5a-113">Votre compte d'utilisateur Windows doit être membre du rôle serveur fixe sysadmin dans l'instance de SQL Server où le [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] est installé.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-113">Your Windows user account must be a member of the sysadmin fixed server role in the SQL Server instance where [!INCLUDE[ssDQSServer](../../includes/ssdqsserver-md.md)] is installed.</span></span>  
  
### <a name="to-upgrade-sqlclr-assemblies"></a><span data-ttu-id="8bd5a-114">Pour mettre à niveau des assemblys SQLCLR</span><span class="sxs-lookup"><span data-stu-id="8bd5a-114">To upgrade SQLCLR Assemblies</span></span>  
  
1.  <span data-ttu-id="8bd5a-115">Démarrez l'invite de commandes.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-115">Start Command Prompt.</span></span>  
  
2.  <span data-ttu-id="8bd5a-116">À l'invite de commandes, remplacez votre répertoire à l'emplacement où DQSInstaller.exe est disponible.</span><span class="sxs-lookup"><span data-stu-id="8bd5a-116">At the command prompt, change your directory to the location where DQSInstaller.exe is available.</span></span> <span data-ttu-id="8bd5a-117">Si vous avez installé l'instance par défaut de SQL Server, le fichier DQSInstaller.exe sera copié sous C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn :</span><span class="sxs-lookup"><span data-stu-id="8bd5a-117">If you installed the default instance of SQL Server, the DQSInstaller.exe file will be available at C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn:</span></span>  
  
    ```  
    cd C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn  
    ```  
  
3.  <span data-ttu-id="8bd5a-118">À l'invite de commandes, tapez la commande suivante et appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="8bd5a-118">At the command prompt, type the following command, and press ENTER:</span></span>  
  
    ```  
    dqsinstaller.exe -upgradedlls  
    ```  
  
4.  <span data-ttu-id="8bd5a-119">Les étapes restantes sont les mêmes que les étapes 2 à 6 de la section [Exécuter DQSInstaller.exe à partir du menu Démarrer ou de l’Explorateur Windows](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) de l’article [Exécuter DQSInstaller.exe pour terminer l’installation du serveur DQS](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span><span class="sxs-lookup"><span data-stu-id="8bd5a-119">Rest of the steps are same as steps 2-6 in the [Run DQSInstaller.exe from Start Screen, Start Menu or Windows Explorer](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md#WindowsExplorer) section in [Run DQSInstaller.exe to Complete Data Quality Server Installation](run-dqsinstaller-exe-to-complete-data-quality-server-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd5a-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8bd5a-120">See Also</span></span>  
 <span data-ttu-id="8bd5a-121">[Installer Data Quality Services](install-data-quality-services.md) </span><span class="sxs-lookup"><span data-stu-id="8bd5a-121">[Install Data Quality Services](install-data-quality-services.md) </span></span>  
 [<span data-ttu-id="8bd5a-122">Mettre à niveau le schéma des bases de données DQS après avoir installé la mise à jour SQL Server</span><span class="sxs-lookup"><span data-stu-id="8bd5a-122">Upgrade DQS Databases Schema After Installing SQL Server Update</span></span>](upgrade-dqs-databases-schema-after-installing-sql-server-update.md)  
  
  
