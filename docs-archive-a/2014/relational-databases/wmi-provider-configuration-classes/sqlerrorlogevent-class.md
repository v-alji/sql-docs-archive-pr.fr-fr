---
title: SqlErrorLogEvent, classe | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- SqlErrorLogEvent class
- SqlErrorLogFile class
ms.assetid: bde6c467-38d0-4766-a7af-d6c9d6302b07
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 358b6906e422be2984f2ebdbde636ad0b8376993
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604410"
---
# <a name="sqlerrorlogevent-class"></a><span data-ttu-id="d3821-102">Classe SqlErrorLogEvent</span><span class="sxs-lookup"><span data-stu-id="d3821-102">SqlErrorLogEvent Class</span></span>
  <span data-ttu-id="d3821-103">Fournit des propriétés pour l'affichage d'événements dans un fichier journal [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] spécifié.</span><span class="sxs-lookup"><span data-stu-id="d3821-103">Provides properties for viewing events in a specified [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3821-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="d3821-104">Syntax</span></span>  
  
```  
  
class SQLErrorLogEvent   
{  
   stringFileName;  
   stringInstanceName;  
   datetimeLogDate;  
   stringMessage;  
   stringProcessInfo;  
};  
```  
  
## <a name="properties"></a><span data-ttu-id="d3821-105">Propriétés</span><span class="sxs-lookup"><span data-stu-id="d3821-105">Properties</span></span>  
 <span data-ttu-id="d3821-106">La classe SQLErrorLogEvent définit les propriétés suivantes.</span><span class="sxs-lookup"><span data-stu-id="d3821-106">The SQLErrorLogEvent class defines the following properties.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3821-107">FileName</span><span class="sxs-lookup"><span data-stu-id="d3821-107">FileName</span></span>|<span data-ttu-id="d3821-108">Type de données : `string`</span><span class="sxs-lookup"><span data-stu-id="d3821-108">Data type: `string`</span></span><br /><br /> <span data-ttu-id="d3821-109">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="d3821-109">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="d3821-110">Nom du fichier journal des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d3821-110">The name of the error log file.</span></span>|  
|<span data-ttu-id="d3821-111">InstanceName</span><span class="sxs-lookup"><span data-stu-id="d3821-111">InstanceName</span></span>|<span data-ttu-id="d3821-112">Type de données : `string`</span><span class="sxs-lookup"><span data-stu-id="d3821-112">Data type: `string`</span></span><br /><br /> <span data-ttu-id="d3821-113">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="d3821-113">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="d3821-114">Qualificateurs : Clé</span><span class="sxs-lookup"><span data-stu-id="d3821-114">Qualifiers: Key</span></span><br /><br /> <span data-ttu-id="d3821-115">Nom de l'instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] où le fichier journal réside.</span><span class="sxs-lookup"><span data-stu-id="d3821-115">The name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] where the log file resides.</span></span>|  
|<span data-ttu-id="d3821-116">LogDate</span><span class="sxs-lookup"><span data-stu-id="d3821-116">LogDate</span></span>|<span data-ttu-id="d3821-117">Type de données : `datetime`</span><span class="sxs-lookup"><span data-stu-id="d3821-117">Data type: `datetime`</span></span><br /><br /> <span data-ttu-id="d3821-118">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="d3821-118">Access type: Read-only</span></span><br /><br /> <span data-ttu-id="d3821-119">Qualificateurs : Clé</span><span class="sxs-lookup"><span data-stu-id="d3821-119">Qualifiers: Key</span></span><br /><br /> <br /><br /> <span data-ttu-id="d3821-120">Date et heure auxquelles l'événement a été enregistré dans le fichier journal.</span><span class="sxs-lookup"><span data-stu-id="d3821-120">The date and time that the event was recorded in the log file.</span></span>|  
|<span data-ttu-id="d3821-121">Message</span><span class="sxs-lookup"><span data-stu-id="d3821-121">Message</span></span>|<span data-ttu-id="d3821-122">Type de données : `string`</span><span class="sxs-lookup"><span data-stu-id="d3821-122">Data type: `string`</span></span><br /><br /> <span data-ttu-id="d3821-123">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="d3821-123">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="d3821-124">Message d'événement.</span><span class="sxs-lookup"><span data-stu-id="d3821-124">The event message.</span></span>|  
|<span data-ttu-id="d3821-125">ProcessInfo</span><span class="sxs-lookup"><span data-stu-id="d3821-125">ProcessInfo</span></span>|<span data-ttu-id="d3821-126">Type de données : `string`</span><span class="sxs-lookup"><span data-stu-id="d3821-126">Data type: `string`</span></span><br /><br /> <span data-ttu-id="d3821-127">Type d'accès : Lecture seule</span><span class="sxs-lookup"><span data-stu-id="d3821-127">Access type: Read-only</span></span><br /><br /> <br /><br /> <span data-ttu-id="d3821-128">Informations sur l'ID du processus du serveur source (SPID) pour l'événement.</span><span class="sxs-lookup"><span data-stu-id="d3821-128">Information about the source server process ID (SPID) for the event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3821-129">Notes</span><span class="sxs-lookup"><span data-stu-id="d3821-129">Remarks</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d3821-130">MOF</span><span class="sxs-lookup"><span data-stu-id="d3821-130">MOF</span></span>|<span data-ttu-id="d3821-131">Sqlmgmproviderxpsp2up.mof</span><span class="sxs-lookup"><span data-stu-id="d3821-131">Sqlmgmproviderxpsp2up.mof</span></span>|  
|<span data-ttu-id="d3821-132">DLL</span><span class="sxs-lookup"><span data-stu-id="d3821-132">DLL</span></span>|<span data-ttu-id="d3821-133">Sqlmgmprovider.dll</span><span class="sxs-lookup"><span data-stu-id="d3821-133">Sqlmgmprovider.dll</span></span>|  
|<span data-ttu-id="d3821-134">Espace de noms</span><span class="sxs-lookup"><span data-stu-id="d3821-134">Namespace</span></span>|<span data-ttu-id="d3821-135">\root\Microsoft\SqlServer\ComputerManagement10</span><span class="sxs-lookup"><span data-stu-id="d3821-135">\root\Microsoft\SqlServer\ComputerManagement10</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d3821-136">Exemple</span><span class="sxs-lookup"><span data-stu-id="d3821-136">Example</span></span>  
 <span data-ttu-id="d3821-137">L'exemple suivant indique comment extraire des valeurs pour tous les événements enregistrés dans un fichier journal spécifié.</span><span class="sxs-lookup"><span data-stu-id="d3821-137">The following example shows how to retrieve values for all logged events in a specified log file.</span></span> <span data-ttu-id="d3821-138">Pour exécuter l’exemple, remplacez \<*Instance_Name*> par le nom de l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , par exemple « Instance1 » et remplacez « file_name » par le nom du fichier journal des erreurs, par exemple « ErrorLog. 1 ».</span><span class="sxs-lookup"><span data-stu-id="d3821-138">To run the example, replace \<*Instance_Name*> with the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as 'Instance1', and replace 'File_Name' with the name of the error log file, such as 'ERRORLOG.1'.</span></span>  
  
```  
on error resume next  
strComputer = "."  
Set objWMIService = GetObject("winmgmts:" _  
    & "{impersonationLevel=impersonate}!\\" _  
    & strComputer & "\root\MICROSOFT\SqlServer\ComputerManagement10")  
set logEvents = objWmiService.ExecQuery("SELECT * FROM SqlErrorLogEvent WHERE InstanceName = '<Instance_Name>' AND FileName = 'File_Name'")  
  
For Each logEvent in logEvents  
WScript.Echo "Instance Name: " & logEvent.InstanceName & vbNewLine _  
    & "Log Date: " & logEvent.LogDate & vbNewLine _  
    & "Log File Name: " & logEvent.FileName & vbNewLine _  
    & "Process Info: " & logEvent.ProcessInfo & vbNewLine _  
    & "Message: " & logEvent.Message & vbNewLine _  
  
Next  
```  
  
## <a name="comments"></a><span data-ttu-id="d3821-139">Commentaires</span><span class="sxs-lookup"><span data-stu-id="d3821-139">Comments</span></span>  
 <span data-ttu-id="d3821-140">Lorsque *InstanceName* ou *filename* ne sont pas fournis dans l’instruction WQL, la requête retourne des informations pour l’instance par défaut et le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fichier journal actuel.</span><span class="sxs-lookup"><span data-stu-id="d3821-140">When *InstanceName* or *FileName* are not provided in the WQL statement, the query will return information for the default instance and the current [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file.</span></span> <span data-ttu-id="d3821-141">Par exemple, l'instruction WQL suivante retournera tous les journaux des événements du fichier journal actuel (ERRORLOG) sur l'instance par défaut (MSSQLSERVER).</span><span class="sxs-lookup"><span data-stu-id="d3821-141">For example, the following WQL statement will return all log events from the current log file (ERRORLOG) on the default instance (MSSQLSERVER).</span></span>  
  
```  
"SELECT * FROM SqlErrorLogEvent"  
```  
  
## <a name="security"></a><span data-ttu-id="d3821-142">Sécurité</span><span class="sxs-lookup"><span data-stu-id="d3821-142">Security</span></span>  
 <span data-ttu-id="d3821-143">Pour vous connecter à un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fichier journal via WMI, vous devez disposer des autorisations suivantes sur les ordinateurs locaux et distants :</span><span class="sxs-lookup"><span data-stu-id="d3821-143">To connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] log file through WMI, you must have the following permissions on both the local and remote computers:</span></span>  
  
-   <span data-ttu-id="d3821-144">Accès en lecture à l’espace de noms WMI **Root\Microsoft\SqlServer\ComputerManagement10** .</span><span class="sxs-lookup"><span data-stu-id="d3821-144">Read access to the **Root\Microsoft\SqlServer\ComputerManagement10** WMI namespace.</span></span> <span data-ttu-id="d3821-145">Par défaut, tout le monde dispose de l'accès en lecture via l'autorisation Activer le compte.</span><span class="sxs-lookup"><span data-stu-id="d3821-145">By default, everyone has read access through the Enable Account permission.</span></span>  
  
-   <span data-ttu-id="d3821-146">Autorisation en lecture sur le dossier qui contient les journaux des erreurs.</span><span class="sxs-lookup"><span data-stu-id="d3821-146">Read permission to the folder that contains the error logs.</span></span> <span data-ttu-id="d3821-147">Par défaut, les journaux des erreurs se trouvent dans le chemin d’accès suivant (où \<*Drive> \* représente le lecteur sur lequel vous avez installé [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et le \<*InstanceName*> nom de l’instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) :</span><span class="sxs-lookup"><span data-stu-id="d3821-147">By default the error logs are located in the following path (where \<*Drive>\* represents the drive where you installed [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and \<*InstanceName*> is the name of the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]):</span></span>  
  
     <span data-ttu-id="d3821-148">\*\* \<Drive> : \Program Files\Microsoft SQL Server\MSSQL12\*\* **. \<InstanceName> \MSSQL\Log**</span><span class="sxs-lookup"><span data-stu-id="d3821-148">**\<Drive>:\Program Files\Microsoft SQL Server\MSSQL12** **.\<InstanceName>\MSSQL\Log**</span></span>  
  
 <span data-ttu-id="d3821-149">Si vous vous connectez via un pare-feu, vérifiez qu'une exception est définie dans le pare-feu pour WMI sur les ordinateurs cibles distants.</span><span class="sxs-lookup"><span data-stu-id="d3821-149">If you are connecting through a firewall, ensure that an exception is set in the firewall for WMI on remote target computers.</span></span> <span data-ttu-id="d3821-150">Pour plus d’informations, consultez [connexion à WMI à distance à partir de Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span><span class="sxs-lookup"><span data-stu-id="d3821-150">For more information, see [Connecting to WMI Remotely Starting with Windows Vista](https://go.microsoft.com/fwlink/?LinkId=178848).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3821-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d3821-151">See Also</span></span>  
 <span data-ttu-id="d3821-152">[SqlErrorLogFile, classe](sqlerrorlogfile-class.md) </span><span class="sxs-lookup"><span data-stu-id="d3821-152">[SqlErrorLogFile Class](sqlerrorlogfile-class.md) </span></span>  
 [<span data-ttu-id="d3821-153">Afficher les fichiers journaux hors connexion</span><span class="sxs-lookup"><span data-stu-id="d3821-153">View Offline Log Files</span></span>](../logs/view-offline-log-files.md)  
  
  
