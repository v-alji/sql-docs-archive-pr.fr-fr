---
title: Configuration du service Integration Services (service SSIS) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services service, configuring
- configuration files [Integration Services]
- service [Integration Services], configuring
- default configuration files
ms.assetid: 36d78393-a54c-44b0-8709-7f003f44c27f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c70c41377a2c302e1a021c6ade2a9d487579fa64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706663"
---
# <a name="configuring-the-integration-services-service-ssis-service"></a><span data-ttu-id="f1e1f-102">Configuration du service Integration Services (Service SSIS)</span><span class="sxs-lookup"><span data-stu-id="f1e1f-102">Configuring the Integration Services Service (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="f1e1f-103">Cette rubrique présente le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , un service Windows qui permet de gérer les packages [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1e1f-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] <span data-ttu-id="f1e1f-104">prend en charge le service pour la compatibilité avec les versions antérieures de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e1f-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f1e1f-105">À compter de [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], vous pouvez gérer des objets tels que des packages sur le serveur Integration Services.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="f1e1f-106">Le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dépend d'un fichier de configuration pour ses paramètres.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-106">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service relies on a configuration file for its settings.</span></span> <span data-ttu-id="f1e1f-107">Par défaut, le nom de ce fichier de configuration est MsDtsSrvr.ini.xml, et le fichier se trouve dans le dossier%ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-107">By default, the name for this configuration file is MsDtsSrvr.ini.xml, and the file is located in the folder, %ProgramFiles%\Microsoft SQL Server\120\DTS\Binn.</span></span>  
  
 <span data-ttu-id="f1e1f-108">Généralement, il n'est pas nécessaire d'apporter des modifications à ce fichier de configuration, ni de modifier l'emplacement par défaut du fichier.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-108">Typically, you do not have to make any changes to this configuration file, nor do you have to change the file's default location.</span></span> <span data-ttu-id="f1e1f-109">Cependant, si vos packages sont stockés dans une instance nommée ou une instance distante du [!INCLUDE[ssDE](../includes/ssde-md.md)]ou dans plusieurs instances du [!INCLUDE[ssDE](../includes/ssde-md.md)], vous devez modifier le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-109">However, you will have to modify the configuration file if your packages are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)], or in multiple instances of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="f1e1f-110">De plus, si vous déplacez le fichier de configuration vers un emplacement autre que l'emplacement par défaut, vous devez modifier la clé de Registre qui spécifie l'emplacement de fichier.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-110">Also, if you move the configuration file to a location other than the default location, you will have to modify the Registry key that specifies the file location.</span></span>  
  
## <a name="configuration-file-contents"></a><span data-ttu-id="f1e1f-111">Contenu du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="f1e1f-111">Configuration File Contents</span></span>  
 <span data-ttu-id="f1e1f-112">Lorsque vous installez [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], le processus d'installation crée et installe le fichier de configuration pour le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1e1f-112">When you install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], the setup process creates and installs the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="f1e1f-113">Ce fichier de configuration par défaut contient les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f1e1f-113">This configuration file contains the following settings:</span></span>  
  
-   <span data-ttu-id="f1e1f-114">Les packages reçoivent une commande d'arrêt lorsque le service s'arrête.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-114">Packages are sent a stop command when the service stops.</span></span>  
  
-   <span data-ttu-id="f1e1f-115">Les dossiers racine à afficher pour [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dans l'Explorateur d'objets de [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] sont les dossiers MSDB et File System.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-115">The root folders to display for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] in Object Explorer of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] are the MSDB and File System folders.</span></span>  
  
-   <span data-ttu-id="f1e1f-116">Les packages du système de fichiers gérés par le [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service se trouvent dans%ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-116">The packages in the file system that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service manages are located in %ProgramFiles%\Microsoft SQL Server\120\DTS\Packages.</span></span>  
  
 <span data-ttu-id="f1e1f-117">Ce fichier de configuration spécifie également quelle base de données msdb contient les packages que le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] gère.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-117">This configuration file also specifies which msdb database contains the packages that the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service will manage.</span></span> <span data-ttu-id="f1e1f-118">Par défaut, le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] est configuré pour gérer les packages dans la base de données msdb de l’instance du [!INCLUDE[ssDE](../includes/ssde-md.md)] qui est installée au même moment que [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e1f-118">By default, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] that is installed at the same time as [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f1e1f-119">Si une instance du [!INCLUDE[ssDE](../includes/ssde-md.md)] n’est pas installée au même moment, le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] est configuré pour gérer les packages dans la base de données msdb de l’instance locale par défaut du [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e1f-119">If an instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)] is not installed at the same time, the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service is configured to manage packages in the msdb database of the local, default instance of the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
### <a name="default-configuration-file-example"></a><span data-ttu-id="f1e1f-120">Exemple de fichier de configuration par défaut</span><span class="sxs-lookup"><span data-stu-id="f1e1f-120">Default Configuration File Example</span></span>  
 <span data-ttu-id="f1e1f-121">L'exemple suivant présente un fichier de configuration par défaut qui spécifie les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="f1e1f-121">The following example shows a default configuration file that specifies the following settings:</span></span>  
  
-   <span data-ttu-id="f1e1f-122">Arrêt des packages exécutés si le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] est arrêté.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-122">Packages stop running when the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service stops.</span></span>  
  
-   <span data-ttu-id="f1e1f-123">Les dossiers racine pour le stockage de package dans [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sont les dossiers MSDB et File System.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-123">The root folders for package storage in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] are MSDB and File System.</span></span>  
  
-   <span data-ttu-id="f1e1f-124">Le service gère les packages qui sont stockés dans la base de données msdb de l'instance locale par défaut de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e1f-124">The service manages packages that are stored in the msdb database of the local, default instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f1e1f-125">Le service gère des packages qui sont stockés dans le système de fichiers du dossier Packages.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-125">The service manages packages that are stored in the file system in the Packages folder.</span></span>  
  
 <span data-ttu-id="f1e1f-126">**Exemple de fichier de configuration par défaut**</span><span class="sxs-lookup"><span data-stu-id="f1e1f-126">**Example of a Default Configuration File**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>.</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file"></a><span data-ttu-id="f1e1f-127">Modification du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="f1e1f-127">Modification of the Configuration File</span></span>  
 <span data-ttu-id="f1e1f-128">Vous pouvez modifier le fichier de configuration de manière à permettre aux packages de poursuivre leur exécution en cas d'arrêt du service, à afficher des dossiers racine supplémentaires dans l'Explorateur d'objets ou à spécifier un dossier différent ou des dossiers supplémentaires dans le système de fichiers que doit gérer le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1e1f-128">You can modify the configuration file to allow packages to continue running if the service stops, to display additional root folders in Object Explorer, or to specify a different folder or additional folders in the file system to be managed by [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span> <span data-ttu-id="f1e1f-129">Par exemple, vous pouvez créer des dossiers racine supplémentaires de type, `SqlServerFolder` , pour gérer les packages dans les bases de données msdb d’instances supplémentaires de [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f1e1f-129">For example, you can create additional root folders of type, `SqlServerFolder`, to manage packages in the msdb databases of additional instances of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1e1f-130">Certains caractères ne sont pas valides dans les noms de dossiers.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-130">Some characters are not valid in folder names.</span></span> <span data-ttu-id="f1e1f-131">Les caractères valides des noms de dossiers sont déterminés par la classe [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]**System.IO.Path** et le champ **GetInvalidFilenameChars** .</span><span class="sxs-lookup"><span data-stu-id="f1e1f-131">Valid characters for folder names are determined by the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] class **System.IO.Path** and the **GetInvalidFilenameChars** field.</span></span> <span data-ttu-id="f1e1f-132">Le champ **GetInvalidFilenameChars** fournit un tableau de caractères propre à la plateforme, qui ne peuvent pas être spécifiés dans des arguments de chaîne de chemin transmis aux membres de la classe **Path** .</span><span class="sxs-lookup"><span data-stu-id="f1e1f-132">The **GetInvalidFilenameChars** field provides a platform-specific array of characters that cannot be specified in path string arguments passed to members of the **Path** class.</span></span> <span data-ttu-id="f1e1f-133">Le jeu des caractères non valides peut varier selon le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-133">The set of invalid characters can vary by file system.</span></span> <span data-ttu-id="f1e1f-134">En général, les caractères non valides sont le guillemet ("), le caractère « inférieur à » (<) et la barre verticale (|).</span><span class="sxs-lookup"><span data-stu-id="f1e1f-134">Typically, invalid characters are the quotation mark ("), less than (<) character, and pipe (|) character.</span></span>  
  
 <span data-ttu-id="f1e1f-135">Cependant, pour gérer des packages stockés dans une instance nommée ou une instance distante du [!INCLUDE[ssDE](../includes/ssde-md.md)], vous devez modifier le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-135">However, you will have to modify the configuration file to manage packages that are stored in a named instance or a remote instance of [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span> <span data-ttu-id="f1e1f-136">Si vous ne mettez pas à jour le fichier de configuration, vous ne pouvez pas utiliser **l’Explorateur d’objets** dans [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] pour consulter des packages stockés dans la base de données msdb sur l’instance nommée ou l’instance distante.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-136">If you do not update the configuration file, you cannot use **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to view packages that are stored in the msdb database on the named instance or the remote instance.</span></span> <span data-ttu-id="f1e1f-137">Si vous essayez d'utiliser l' **Explorateur d'objets** pour consulter ces packages, le message d'erreur suivant apparaît :</span><span class="sxs-lookup"><span data-stu-id="f1e1f-137">If you try to use **Object Explorer** to view these packages, you receive the following error message:</span></span>  
  
 `Failed to retrieve data for this request. (Microsoft.SqlServer.SmoEnum)`  
  
 `The SQL Server specified in Integration Services service configuration is not present or is not available. This might occur when there is no default instance of SQL Server on the computer. For more information, see the topic "Configuring the Integration Services Service" in SQL Server 2008 Books Online.`  
  
 `Login Timeout Expired`  
  
 `An error has occurred while establishing a connection to the server. When connecting to SQL Server 2008, this failure may be caused by the fact that under the default settings SQL Server does not allow remote connections.`  
  
 `Named Pipes Provider: Could not open a connection to SQL Server [2]. (MsDtsSvr).`  
  
 <span data-ttu-id="f1e1f-138">Pour modifier le fichier de configuration pour le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , utilisez un éditeur de texte.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-138">To modify the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, you use a text editor.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f1e1f-139">Après avoir modifié le fichier de configuration de service, vous devez redémarrer le service afin d'utiliser la configuration de service mise à jour.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-139">After you modify the service configuration file, you must restart the service to use the updated service configuration.</span></span>  
  
### <a name="modified-configuration-file-example"></a><span data-ttu-id="f1e1f-140">Exemple de fichier de configuration modifié</span><span class="sxs-lookup"><span data-stu-id="f1e1f-140">Modified Configuration File Example</span></span>  
 <span data-ttu-id="f1e1f-141">L'exemple suivant illustre un fichier de configuration modifié pour [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f1e1f-141">The following example shows a modified configuration file for [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="f1e1f-142">Ce fichier concerne une instance nommée de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] appelée `InstanceName` , située sur un serveur nommé `ServerName`.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-142">This file is for a named instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] called `InstanceName` on a server named `ServerName`.</span></span>  
  
 <span data-ttu-id="f1e1f-143">**Exemple de fichier de configuration modifié pour une instance nommée de SQL Server**</span><span class="sxs-lookup"><span data-stu-id="f1e1f-143">**Example of a Modified Configuration File for a Named Instance of SQL Server**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<DtsServiceConfiguration xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <StopExecutingPackagesOnShutdown>true</StopExecutingPackagesOnShutdown>  
  <TopLevelFolders>  
    <Folder xsi:type="SqlServerFolder">  
      <Name>MSDB</Name>  
      <ServerName>ServerName\InstanceName</ServerName>  
    </Folder>  
    <Folder xsi:type="FileSystemFolder">  
      <Name>File System</Name>  
      <StorePath>..\Packages</StorePath>  
    </Folder>  
  </TopLevelFolders>    
</DtsServiceConfiguration>  
```  
  
## <a name="modification-of-the-configuration-file-location"></a><span data-ttu-id="f1e1f-144">Modification de l'emplacement du fichier de configuration</span><span class="sxs-lookup"><span data-stu-id="f1e1f-144">Modification of the Configuration File Location</span></span>  
<span data-ttu-id="f1e1f-145">La clé de Registre **HKEY_LOCAL_MACHINE \SOFTWARE\MICROSOFT\MICROSOFT SQL Server\120\SSIS\ServiceConfigFile** spécifie l’emplacement et le nom du fichier de configuration utilisé par le [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-145">The Registry key **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\120\SSIS\ServiceConfigFile** specifies the location and name for the configuration file that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service uses.</span></span> <span data-ttu-id="f1e1f-146">La valeur par défaut de la clé de Registre est **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-146">The default value of the Registry key is **C:\Program Files\Microsoft SQL Server\120\DTS\Binn\MsDtsSrvr.ini.xml**.</span></span> <span data-ttu-id="f1e1f-147">Vous pouvez mettre à jour la valeur de la clé de Registre pour utiliser un nom et un emplacement différents pour le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-147">You can update the value of the Registry key to use a different name and location for the configuration file.</span></span> <span data-ttu-id="f1e1f-148">Notez que le numéro de version dans le chemin d’accès (120 pour SQL Server [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)] ) varie en fonction de la version de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-148">Note that the version number in the path (120 for SQL Server  [!INCLUDE[ssSQL14_md](../includes/sssql14-md.md)]) will vary depending on the SQL Server version.</span></span> 
  
  
> [!CAUTION]  
>  <span data-ttu-id="f1e1f-149">La modification incorrecte du Registre peut entraîner de graves problèmes et nécessiter la réinstallation du système d'exploitation.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-149">Incorrectly editing the Registry can cause serious problems that may require you to reinstall your operating system.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="f1e1f-150">ne garantit pas que les problèmes résultant d'une modification incorrecte du Registre peuvent être résolus.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-150">cannot guarantee that problems resulting from editing the Registry incorrectly can be resolved.</span></span> <span data-ttu-id="f1e1f-151">Avant de modifier le Registre, sauvegardez toutes vos données importantes.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-151">Before editing the Registry, back up any valuable data.</span></span> <span data-ttu-id="f1e1f-152">Pour plus d'informations sur la méthode de sauvegarde, de restauration et de modification du Registre, consultez l'article [!INCLUDE[msCoName](../includes/msconame-md.md)] Description du Registre de Microsoft Windows [de la Base de connaissances](https://support.microsoft.com/kb/256986).</span><span class="sxs-lookup"><span data-stu-id="f1e1f-152">For information about how to back up, restore, and edit the Registry, see the [!INCLUDE[msCoName](../includes/msconame-md.md)] Knowledge Base article, [Description of the Microsoft Windows registry](https://support.microsoft.com/kb/256986).</span></span>  
  
 <span data-ttu-id="f1e1f-153">Lorsqu'il démarre, le service [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] charge le fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-153">The [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service loads the configuration file when the service is started.</span></span> <span data-ttu-id="f1e1f-154">Toute modification de l'entrée de Registre nécessite le redémarrage du service.</span><span class="sxs-lookup"><span data-stu-id="f1e1f-154">Any changes to the Registry entry require that the service be restarted.</span></span>  
  
  
