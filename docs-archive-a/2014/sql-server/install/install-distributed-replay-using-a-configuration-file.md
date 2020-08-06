---
title: Installer Distributed Replay à l’aide d’un fichier de configuration | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3259232c-6963-4c9c-9d10-ae42aa262eef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7757cce29c2e6b3ce4f1e91fc97cbf8be02ae521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704728"
---
# <a name="install-distributed-replay-using-a-configuration-file"></a><span data-ttu-id="434b5-102">Installer Distributed Replay à l'aide d'un fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="434b5-102">Install Distributed Replay Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="434b5-103">permet de générer un fichier de configuration basé sur les entrées utilisateur et les entrées système par défaut.</span><span class="sxs-lookup"><span data-stu-id="434b5-103">Setup provides the ability to generate a configuration file based on user input and system defaults.</span></span> <span data-ttu-id="434b5-104">Si vous spécifiez que vous souhaitez que les outils d'administration soient installés, vous pouvez utiliser le fichier de configuration pour déployer les trois composants Distributed Replay (outil d'administration, Distributed Replay Controller et Distributed Replay Client).</span><span class="sxs-lookup"><span data-stu-id="434b5-104">If you specify that you want the Management tools installed, you can use the configuration file to deploy the three Distributed Replay components (administration tool, Distributed Replay controller, and the Distributed Replay client).</span></span> <span data-ttu-id="434b5-105">Il prend en charge l'installation, la réparation et la désinstallation des composants Distributed Replay.</span><span class="sxs-lookup"><span data-stu-id="434b5-105">It supports Installing, repairing, and uninstalling of the Distributed Replay components.</span></span>  
  
 <span data-ttu-id="434b5-106">Le programme d'installation ne prend en charge l'utilisation du fichier de configuration qu'à l'aide de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="434b5-106">Setup supports the use of the configuration file only through the command-line.</span></span> <span data-ttu-id="434b5-107">L'ordre de traitement des paramètres lors de l'utilisation du fichier de configuration est décrit ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="434b5-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="434b5-108">Le fichier de configuration remplace les valeurs par défaut d'un package.</span><span class="sxs-lookup"><span data-stu-id="434b5-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="434b5-109">Les valeurs de la ligne de commande remplacent les valeurs du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="434b5-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="434b5-110">Pour plus d’informations sur l’utilisation d’un fichier de configuration, consultez [installer SQL Server 2014 à l’aide d’un fichier de configuration](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="434b5-110">For more information about how to use a configuration file, see [Install SQL Server 2014 Using a Configuration File](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="434b5-111">Une fois que vous avez installé Distributed Replay, vous devez créer des règles de pare-feu sur le contrôleur et les ordinateurs clients, et accorder des autorisations à chaque ordinateur client sur le serveur cible.</span><span class="sxs-lookup"><span data-stu-id="434b5-111">After you install Distributed Replay you must create firewall rules on the controller and client computers, and grant each client computer permissions on the target server.</span></span> <span data-ttu-id="434b5-112">Pour plus d’informations, consultez [Suivre les étapes consécutives à l’installation](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span><span class="sxs-lookup"><span data-stu-id="434b5-112">For more information, see [Complete the Post-Installation Steps](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span></span>  
  
### <a name="to-generate-a-configuration-file"></a><span data-ttu-id="434b5-113">Pour générer un fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="434b5-113">To generate a configuration file</span></span>  
  
1.  <span data-ttu-id="434b5-114">Suivez le déroulement des étapes de l'Assistant Installation jusqu'à la page **Prêt pour l'installation** .</span><span class="sxs-lookup"><span data-stu-id="434b5-114">Follow the Setup wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="434b5-115">Le chemin d'accès au fichier de configuration est spécifié dans la page **Prêt pour l'installation** , dans la section relative au chemin d'accès du fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="434b5-115">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span>  
  
2.  <span data-ttu-id="434b5-116">Annulez l'exécution du programme d'installation sans réellement terminer l'installation afin de générer le fichier INI.</span><span class="sxs-lookup"><span data-stu-id="434b5-116">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
### <a name="to-install-distributed-replay-using-the-configuration-file"></a><span data-ttu-id="434b5-117">Pour installer Distributed Replay à l'aide du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="434b5-117">To Install Distributed Replay Using the Configuration File</span></span>  
  
-   <span data-ttu-id="434b5-118">Exécutez l'installation à partir de l'invite de commandes et spécifiez le fichier ConfigurationFile.ini à l'aide du paramètre ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="434b5-118">Run the installation through the command prompt and supply the ConfigurationFile.ini using the ConfigurationFile parameter.</span></span>  
  
 <span data-ttu-id="434b5-119">**Exemple de syntaxe**</span><span class="sxs-lookup"><span data-stu-id="434b5-119">**Sample Syntax**</span></span>  
  
 <span data-ttu-id="434b5-120">Voici un exemple montrant comment spécifier le fichier de configuration lors de l'invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="434b5-120">Following is an example on how to specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /CTLRSVCPASSWORD="ctlrsvcpswd" /CLTSVCPASSWORD="cltsvcpswd" / ConfigurationFile=ConfigurationFile.INI\  
```  
  
> [!NOTE]  
>  <span data-ttu-id="434b5-121">Vous devez spécifier les deux mots de passe dans la ligne de commande car il n'est pas possible de les configurer dans le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="434b5-121">You must specify both passwords in the command line because you cannot configure them in the configuration file.</span></span>  
  
  
