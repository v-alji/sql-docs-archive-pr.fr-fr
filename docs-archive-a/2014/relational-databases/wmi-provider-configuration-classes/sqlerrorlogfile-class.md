---
title: SqlErrorLogFile, classe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
ms.assetid: 2b83ae4a-c0d4-414c-b6e5-a41ec7c13159
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d73f97ebddd7a1d18c73a2cbce7fe79dafc17a77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696579"
---
# <a name="sqlerrorlogfile-class"></a><span data-ttu-id="58098-102">Classe SqlErrorLogFile</span><span class="sxs-lookup"><span data-stu-id="58098-102">SqlErrorLogFile Class</span></span>
  <span data-ttu-id="58098-103">Fournit des propriétés pour l'affichage des informations relatives à un fichier journal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58098-103">Provides properties for viewing information about a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58098-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="58098-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogFile  
{  
   uint32ArchiveNumber;  
   stringInstanceName;  
   datetimeLastModified;  
   uint32LogFileSize;  
   stringName;  
  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="58098-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="58098-105">Properties</span></span>  
 <span data-ttu-id="58098-106">La classe SQLErrorLogFile définit les propriétés suivantes.</span><span class="sxs-lookup"><span data-stu-id="58098-106">The SQLErrorLogFile class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58098-107">ArchiveNumber</span><span class="sxs-lookup"><span data-stu-id="58098-107">ArchiveNumber</span></span>|<span data-ttu-id="58098-108">Type de données : `uint32`</span><span class="sxs-lookup"><span data-stu-id="58098-108">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="58098-109">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="58098-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="58098-110">Numéro d'archive pour le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="58098-110">The archive number for the log file.</span></span>|  
|<span data-ttu-id="58098-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="58098-111">InstanceName</span></span>|<span data-ttu-id="58098-112">Type de données : `string`</span><span class="sxs-lookup"><span data-stu-id="58098-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="58098-113">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="58098-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="58098-114">Qualificateurs : Clé</span><span class="sxs-lookup"><span data-stu-id="58098-114">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="58098-115">Nom de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] où le fichier journal réside.</span><span class="sxs-lookup"><span data-stu-id="58098-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="58098-116">LastModified</span><span class="sxs-lookup"><span data-stu-id="58098-116">LastModified</span></span>|<span data-ttu-id="58098-117">Type de données : `datetime`</span><span class="sxs-lookup"><span data-stu-id="58098-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="58098-118">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="58098-118">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="58098-119">Date de la dernière modification du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="58098-119">The date that the log file was last modified.</span></span>|  
|<span data-ttu-id="58098-120">LogFileSize</span><span class="sxs-lookup"><span data-stu-id="58098-120">LogFileSize</span></span>|<span data-ttu-id="58098-121">Type de données : `uint32`</span><span class="sxs-lookup"><span data-stu-id="58098-121">Data type: `uint32`</span></span><br /><br /> <span data-ttu-id="58098-122">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="58098-122">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="58098-123">Taille du fichier journal, en octets.</span><span class="sxs-lookup"><span data-stu-id="58098-123">The log file size, in bytes.</span></span>|  
|<span data-ttu-id="58098-124">Nom</span><span class="sxs-lookup"><span data-stu-id="58098-124">Name</span></span>|<span data-ttu-id="58098-125">Type de données : `string`</span><span class="sxs-lookup"><span data-stu-id="58098-125">Data type: `string`</span></span><br /><br /> <span data-ttu-id="58098-126">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="58098-126">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="58098-127">Qualificateurs : Clé</span><span class="sxs-lookup"><span data-stu-id="58098-127">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="58098-128">Nom du fichier journal.</span><span class="sxs-lookup"><span data-stu-id="58098-128">The name of the log file.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58098-129">Notes</span><span class="sxs-lookup"><span data-stu-id="58098-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58098-130">MOF</span><span class="sxs-lookup"><span data-stu-id="58098-130">MOF</span></span>|<span data-ttu-id="58098-131">Sqlmgmprovider xpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="58098-131">Sqlmgmprovider xpsp2up.mof</span></span>|  
|<span data-ttu-id="58098-132">DLL</span><span class="sxs-lookup"><span data-stu-id="58098-132">DLL</span></span>|<span data-ttu-id="58098-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="58098-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="58098-134">Espace de noms</span><span class="sxs-lookup"><span data-stu-id="58098-134">Namespace</span></span>|<span data-ttu-id="58098-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="58098-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="58098-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="58098-136">Example</span></span>  
 <span data-ttu-id="58098-137">L'exemple suivant extrait les informations relatives à tous les fichiers journaux [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sur une instance spécifiée de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58098-137">The following example retrieves information about all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log files on a specified instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="58098-138">Pour exécuter l’exemple, remplacez \<*Instance_Name*> par le nom de l’instance, par exemple « Instance1 ».</span><span class="sxs-lookup"><span data-stu-id="58098-138">To run the example, replace \<*Instance_Name*> with the name of the instance, for example, 'Instance1'.</span></span>  
  
```  
on error resume next  
set strComputer = "."  
set objWMIService = GetObject("winmgmts:\\.\root\Microsoft\SqlServer\ComputerManagement10")  
set LogFiles = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogFile WHERE InstanceName = '<Instance_Name>'")  
  
For Each logFile in LogFiles  
  
WScript.Echo "Instance Name:  " & logFile.InstanceName & vbNewLine _  
    & "Log File Name:  " & logFile.Name & vbNewLine _  
    & "Archive Number: " & logFile.ArchiveNumber & vbNewLine _  
    & "Log File Size:  " & logFile.LogFileSize & " bytes" & vbNewLine _  
    & "Last Modified:  " & logFile.LastModified & vbNewLine _  
  
Next   
```  
  
## <a name="comments"></a><span data-ttu-id="58098-139">Commentaires</span><span class="sxs-lookup"><span data-stu-id="58098-139">Comments</span></span>  
 <span data-ttu-id="58098-140">Lorsque *InstanceName* n’est pas fourni dans l’instruction WQL, la requête retourne des informations pour l’instance par défaut.</span><span class="sxs-lookup"><span data-stu-id="58098-140">When *InstanceName* is not provided in the WQL statement, the query will return information for the default instance.</span></span> <span data-ttu-id="58098-141">Par exemple, l'instruction WQL suivante retournera les informations relatives à tous les fichiers journaux de l'instance par défaut (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="58098-141">For example, the following WQL statement will return information about all log files from the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogFile"  
```  
  
## <a name="security"></a><span data-ttu-id="58098-142">Sécurité</span><span class="sxs-lookup"><span data-stu-id="58098-142">Security</span></span>  
 <span data-ttu-id="58098-143">Pour vous connecter à un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fichier journal via WMI, vous devez disposer des autorisations suivantes sur les ordinateurs locaux et distants :</span><span class="sxs-lookup"><span data-stu-id="58098-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="58098-144">Accès en lecture à l’espace de noms WMI **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="58098-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="58098-145">Par défaut, tout le monde dispose de l'accès en lecture via l'autorisation Activer le compte.</span><span class="sxs-lookup"><span data-stu-id="58098-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="58098-146">Pour plus d’informations sur la vérification des autorisations WMI, consultez la section sécurité de la rubrique [afficher les fichiers journaux hors connexion](../logs/view-offline-log-files.md).</span><span class="sxs-lookup"><span data-stu-id="58098-146">For information about how to verify WMI permissions, see the Security section of the topic [View Offline Log Files](../logs/view-offline-log-files.md).</span></span>  
  
-   <span data-ttu-id="58098-147">Autorisation en lecture sur le dossier qui contient les journaux des erreurs.</span><span class="sxs-lookup"><span data-stu-id="58098-147">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="58098-148">Par défaut, les journaux des erreurs se trouvent dans le chemin d’accès suivant (où \<*Drive> \* représente le lecteur sur lequel vous avez installé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le \<*InstanceName*> nom de l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) :</span><span class="sxs-lookup"><span data-stu-id="58098-148">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="58098-149">\*\* \<Drive> : \Program Files\Microsoft SQL Server\MSSQL11\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="58098-149">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL11** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="58098-150">Si vous vous connectez via un pare-feu, vérifiez qu'une exception est définie dans le pare-feu pour WMI sur les ordinateurs cibles distants.</span><span class="sxs-lookup"><span data-stu-id="58098-150">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="58098-151">Pour plus d’informations, consultez [connexion à WMI à distance à partir de Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="58098-151">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58098-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="58098-152">See Also</span></span>  
 <span data-ttu-id="58098-153">[SqlErrorLogEvent, classe](sqlerrorlogevent-class.md) </span><span class="sxs-lookup"><span data-stu-id="58098-153">[SqlErrorLogEvent Class](sqlerrorlogevent-class.md) </span></span>  
 [<span data-ttu-id="58098-154">Afficher les fichiers journaux hors connexion</span><span class="sxs-lookup"><span data-stu-id="58098-154">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
