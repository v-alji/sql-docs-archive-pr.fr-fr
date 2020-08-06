---
title: GenerateDatabaseRightsScript, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseRightsScript method
ms.assetid: f2e6dcc9-978f-4c2c-bafe-36c330247fd0
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 768e73d13d3b06f7913c3c816fded1b28c56199f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706087"
---
# <a name="generatedatabaserightsscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="da80f-102">Méthode GenerateDatabaseRightsScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="da80f-102">GenerateDatabaseRightsScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="da80f-103">Génère un script SQL pouvant être utilisé pour accorder des droits d'utilisateur à la base de données du serveur de rapports et à d'autres bases de données requises pour l'exécution d'un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="da80f-103">Generates a SQL Script that can be used to grant a user rights to the report server database and other databases required for a report server to run.</span></span> <span data-ttu-id="da80f-104">Il est prévu que l'appelant se connecte au serveur de base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et exécute le script.</span><span class="sxs-lookup"><span data-stu-id="da80f-104">The caller is expected to connect to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database server and execute the script.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da80f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="da80f-105">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseRightsScript(ByVal UserName As String, _  
    ByVal DatabaseName As String, ByVal IsRemote As Boolean, _  
    ByVal IsWindowsUser As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseRightsScript(string UserName, string DatabaseName, bool IsRemote, bool IsWindowsUser, out string Script,   
out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da80f-106">Paramètres</span><span class="sxs-lookup"><span data-stu-id="da80f-106">Parameters</span></span>  
 <span data-ttu-id="da80f-107">*UserName*</span><span class="sxs-lookup"><span data-stu-id="da80f-107">*UserName*</span></span>  
 <span data-ttu-id="da80f-108">Nom d'utilisateur ou identificateur de sécurité Windows (SID) de l'utilisateur auquel le script accorde des droits.</span><span class="sxs-lookup"><span data-stu-id="da80f-108">The user name or Windows security identifier (SID) of the user to which the script will grant rights.</span></span>  
  
 <span data-ttu-id="da80f-109">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="da80f-109">*DatabaseName*</span></span>  
 <span data-ttu-id="da80f-110">Nom de la base de données à laquelle le script accordera l'accès à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da80f-110">The database name to which the script will grant access to the user.</span></span>  
  
 <span data-ttu-id="da80f-111">*IsRemote*</span><span class="sxs-lookup"><span data-stu-id="da80f-111">*IsRemote*</span></span>  
 <span data-ttu-id="da80f-112">Valeur booléenne indiquant si la base de données est distante du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="da80f-112">A Boolean value to indicating whether the database is remote from the report server.</span></span>  
  
 <span data-ttu-id="da80f-113">*IsWindowsUser*</span><span class="sxs-lookup"><span data-stu-id="da80f-113">*IsWindowsUser*</span></span>  
 <span data-ttu-id="da80f-114">Valeur booléenne qui indique si le nom d'utilisateur spécifié est un utilisateur Windows ou un utilisateur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da80f-114">A Boolean value indicating whether the specified user name is a Windows user or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] user.</span></span>  
  
 <span data-ttu-id="da80f-115">*Script*</span><span class="sxs-lookup"><span data-stu-id="da80f-115">*Script*</span></span>  
 <span data-ttu-id="da80f-116">[out] Chaîne contenant le script [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] généré.</span><span class="sxs-lookup"><span data-stu-id="da80f-116">[out] A string containing the generated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span>  
  
 <span data-ttu-id="da80f-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="da80f-117">*HRESULT*</span></span>  
 <span data-ttu-id="da80f-118">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="da80f-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da80f-119">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="da80f-119">Return Value</span></span>  
 <span data-ttu-id="da80f-120">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="da80f-120">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="da80f-121">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="da80f-121">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="da80f-122">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="da80f-122">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da80f-123">Notes</span><span class="sxs-lookup"><span data-stu-id="da80f-123">Remarks</span></span>  
 <span data-ttu-id="da80f-124">Si *DatabaseName* est vide, *IsRemote* est ignoré et la valeur du fichier de configuration du serveur de rapports est utilisée comme nom de base de données.</span><span class="sxs-lookup"><span data-stu-id="da80f-124">If *DatabaseName* is empty then *IsRemote* is ignored and the report server configuration file value is used for the database name.</span></span>  
  
 <span data-ttu-id="da80f-125">Si *IsWindowsUser* a la valeur `true` , le *nom d’utilisateur* doit être au format \<domain> \\<nom d’utilisateur \> .</span><span class="sxs-lookup"><span data-stu-id="da80f-125">If *IsWindowsUser* is set to `true`, *UserName* should be in the format \<domain>\\<username\>.</span></span>  
  
 <span data-ttu-id="da80f-126">Lorsque *IsWindowsUser* a la valeur `true` , le script généré accorde des droits de connexion à l’utilisateur pour le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , en définissant la base de données du serveur de rapports comme base de données par défaut et accorde le rôle **RSExec** sur la base de données du serveur de rapports, la base de données temporaire du serveur de rapports, la base de données master et la base de données système msdb.</span><span class="sxs-lookup"><span data-stu-id="da80f-126">When *IsWindowsUser* is set to `true`, the generated script grants login rights to the user for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], setting the report server database as the default database, and grants the **RSExec** role on the report server database, the report server temporary database, the master database and the MSDB system database.</span></span>  
  
 <span data-ttu-id="da80f-127">Quand *IsWindowsUser* a la valeur `true` , la méthode accepte les SID Windows standard comme entrée.</span><span class="sxs-lookup"><span data-stu-id="da80f-127">When *IsWindowsUser* is set to `true`, the method accepts standard Windows SIDs as input.</span></span> <span data-ttu-id="da80f-128">Lorsqu'un nom de compte de service ou un SID Windows standard est fourni, il est converti en une chaîne de nom d'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="da80f-128">When a standard Windows SID or service account name is supplied, it is translated to a user name string.</span></span> <span data-ttu-id="da80f-129">Si la base de données est locale, le compte est converti en la représentation localisée correcte du compte.</span><span class="sxs-lookup"><span data-stu-id="da80f-129">If the database is local, the account is translated to the correct localized representation of the account.</span></span> <span data-ttu-id="da80f-130">Si la base de données est distante, le compte est représenté en tant que compte de l’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="da80f-130">If the database is remote, the account is represented as the computer's account.</span></span>  
  
 <span data-ttu-id="da80f-131">Le tableau suivant répertorie les comptes qui sont convertis et indique leur représentation distante.</span><span class="sxs-lookup"><span data-stu-id="da80f-131">The following table shows accounts that are translated and their remote representation.</span></span>  
  
|<span data-ttu-id="da80f-132">Compte/SID converti</span><span class="sxs-lookup"><span data-stu-id="da80f-132">Account / SID that is translated</span></span>|<span data-ttu-id="da80f-133">Nom commun</span><span class="sxs-lookup"><span data-stu-id="da80f-133">Common Name</span></span>|<span data-ttu-id="da80f-134">Nom distant</span><span class="sxs-lookup"><span data-stu-id="da80f-134">Remote Name</span></span>|  
|---------------------------------------|-----------------|-----------------|  
|<span data-ttu-id="da80f-135">(S-1-5-18)</span><span class="sxs-lookup"><span data-stu-id="da80f-135">(S-1-5-18)</span></span>|<span data-ttu-id="da80f-136">Système Local</span><span class="sxs-lookup"><span data-stu-id="da80f-136">Local System</span></span>|<span data-ttu-id="da80f-137">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="da80f-137">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="da80f-138">.\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="da80f-138">.\LocalSystem</span></span>|<span data-ttu-id="da80f-139">Système Local</span><span class="sxs-lookup"><span data-stu-id="da80f-139">Local System</span></span>|<span data-ttu-id="da80f-140">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="da80f-140">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="da80f-141">ComputerName\LocalSystem</span><span class="sxs-lookup"><span data-stu-id="da80f-141">ComputerName\LocalSystem</span></span>|<span data-ttu-id="da80f-142">Système Local</span><span class="sxs-lookup"><span data-stu-id="da80f-142">Local System</span></span>|<span data-ttu-id="da80f-143">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="da80f-143">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="da80f-144">LocalSystem</span><span class="sxs-lookup"><span data-stu-id="da80f-144">LocalSystem</span></span>|<span data-ttu-id="da80f-145">Système Local</span><span class="sxs-lookup"><span data-stu-id="da80f-145">Local System</span></span>|<span data-ttu-id="da80f-146">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="da80f-146">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="da80f-147">(S-1-5-20)</span><span class="sxs-lookup"><span data-stu-id="da80f-147">(S-1-5-20)</span></span>|<span data-ttu-id="da80f-148">Service réseau</span><span class="sxs-lookup"><span data-stu-id="da80f-148">Network Service</span></span>|<span data-ttu-id="da80f-149">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="da80f-149">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="da80f-150">NT AUTHORITY\NetworkService</span><span class="sxs-lookup"><span data-stu-id="da80f-150">NT AUTHORITY\NetworkService</span></span>|<span data-ttu-id="da80f-151">Service réseau</span><span class="sxs-lookup"><span data-stu-id="da80f-151">Network Service</span></span>|<span data-ttu-id="da80f-152">\<Domain>\\<ComputerName\>$</span><span class="sxs-lookup"><span data-stu-id="da80f-152">\<Domain>\\<ComputerName\>$</span></span>|  
|<span data-ttu-id="da80f-153">(S-1-5-19)</span><span class="sxs-lookup"><span data-stu-id="da80f-153">(S-1-5-19)</span></span>|<span data-ttu-id="da80f-154">Service local</span><span class="sxs-lookup"><span data-stu-id="da80f-154">Local Service</span></span>|<span data-ttu-id="da80f-155">Erreur (voir ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="da80f-155">Error - see below.</span></span>|  
|<span data-ttu-id="da80f-156">NT AUTHORITY\LocalService</span><span class="sxs-lookup"><span data-stu-id="da80f-156">NT AUTHORITY\LocalService</span></span>|<span data-ttu-id="da80f-157">Service local</span><span class="sxs-lookup"><span data-stu-id="da80f-157">Local Service</span></span>|<span data-ttu-id="da80f-158">Erreur (voir ci-dessous)</span><span class="sxs-lookup"><span data-stu-id="da80f-158">Error - see below.</span></span>|  
  
 <span data-ttu-id="da80f-159">Dans [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], si vous utilisez un compte intégré et que la base de données du serveur de rapports est distante, une erreur est retournée.</span><span class="sxs-lookup"><span data-stu-id="da80f-159">On [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)], if you are using a built-in account and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="da80f-160">Si le compte intégré `LocalService` est spécifié et que la base de données du serveur de rapports est distante, une erreur est retournée.</span><span class="sxs-lookup"><span data-stu-id="da80f-160">If the `LocalService` built-in account is specified and the report server database is remote, an error is returned.</span></span>  
  
 <span data-ttu-id="da80f-161">Quand *IsWindowsUser* a la valeur true et qu’il est nécessaire de convertir la valeur indiquée dans *UserName* , le fournisseur WMI détermine si la base de données du serveur de rapports réside sur le même ordinateur ou sur un ordinateur distant.</span><span class="sxs-lookup"><span data-stu-id="da80f-161">When *IsWindowsUser* is true and the value supplied in *UserName* needs to be translated, the WMI provider determines whether the report server database is located on the same computer or on a remote computer.</span></span> <span data-ttu-id="da80f-162">Pour déterminer si l’installation est locale, le fournisseur WMI évalue la propriété DatabaseServerName par rapport à la liste de valeurs suivante.</span><span class="sxs-lookup"><span data-stu-id="da80f-162">To determine if the installation is local, the WMI provider evaluates the DatabaseServerName property against the following list of values.</span></span> <span data-ttu-id="da80f-163">Si une correspondance est trouvée, la base de données est locale.</span><span class="sxs-lookup"><span data-stu-id="da80f-163">If a match is found, the database is local.</span></span> <span data-ttu-id="da80f-164">Dans le cas contraire, elle est distante.</span><span class="sxs-lookup"><span data-stu-id="da80f-164">Otherwise, it is remote.</span></span> <span data-ttu-id="da80f-165">La comparaison respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="da80f-165">The comparison is case-insensitive.</span></span>  
  
|<span data-ttu-id="da80f-166">Valeur de DatabaseServerName</span><span class="sxs-lookup"><span data-stu-id="da80f-166">Value of DatabaseServerName</span></span>|<span data-ttu-id="da80f-167">Exemple</span><span class="sxs-lookup"><span data-stu-id="da80f-167">Example</span></span>|  
|---------------------------------|-------------|  
|<span data-ttu-id="da80f-168">"."</span><span class="sxs-lookup"><span data-stu-id="da80f-168">"."</span></span>||  
|<span data-ttu-id="da80f-169">"(local)"</span><span class="sxs-lookup"><span data-stu-id="da80f-169">"(local)"</span></span>||  
|<span data-ttu-id="da80f-170">"LOCAL"</span><span class="sxs-lookup"><span data-stu-id="da80f-170">"LOCAL"</span></span>||  
|<span data-ttu-id="da80f-171">localhost</span><span class="sxs-lookup"><span data-stu-id="da80f-171">localhost</span></span>||  
|\<Machinename>|<span data-ttu-id="da80f-172">labtest14</span><span class="sxs-lookup"><span data-stu-id="da80f-172">testlab14</span></span>|  
|\<MachineFQDN>|<span data-ttu-id="da80f-173">example.redmond.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="da80f-173">example.redmond.microsoft.com</span></span>|  
|\<IPAddress>|<span data-ttu-id="da80f-174">180.012.345,678</span><span class="sxs-lookup"><span data-stu-id="da80f-174">180.012.345,678</span></span>|  
  
 <span data-ttu-id="da80f-175">Lorsque *IsWindowsUser* a la valeur `true` , le fournisseur WMI appelle LookupAccountName pour obtenir le SID du compte, puis il appelle LookupAccountSid pour obtenir le nom à placer dans le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span><span class="sxs-lookup"><span data-stu-id="da80f-175">When *IsWindowsUser* is set to `true`, the WMI provider calls LookupAccountName to get the SID for the account and then calls LookupAccountSID to get the name to put in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] script.</span></span> <span data-ttu-id="da80f-176">De cette manière, le nom du compte utilisé réussit systématiquement la validation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="da80f-176">This ensures that the account name used will pass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] validation.</span></span>  
  
 <span data-ttu-id="da80f-177">Quand *IsWindowsUser* a la valeur `false` , le script généré accorde le rôle **RSExec** sur la base de données du serveur de rapports, la base de données temporaire du serveur de rapports et la base de données msdb.</span><span class="sxs-lookup"><span data-stu-id="da80f-177">When *IsWindowsUser* is set to `false`, the generated script grants the **RSExec** role on the report server database, the report server temporary database, and the MSDB database.</span></span>  
  
 <span data-ttu-id="da80f-178">Quand *IsWindowsUser* a la valeur `false` , l’utilisateur SQL Server doit déjà exister sur le [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour que le script s’exécute correctement.</span><span class="sxs-lookup"><span data-stu-id="da80f-178">When *IsWindowsUser* is set to `false`, the SQL Server user must already exist on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the script to run successfully.</span></span>  
  
 <span data-ttu-id="da80f-179">Si aucune base de données de serveur de rapports n’est spécifiée pour le serveur de rapports, l’appel de GrantRightsToDatabaseUser retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="da80f-179">If the report server does not have a report server database specified, calling GrantRightsToDatabaseUser returns an error.</span></span>  
  
 <span data-ttu-id="da80f-180">Le script généré prend en charge [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 et [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da80f-180">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da80f-181">Spécifications</span><span class="sxs-lookup"><span data-stu-id="da80f-181">Requirements</span></span>  
 <span data-ttu-id="da80f-182">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da80f-182">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da80f-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da80f-183">See Also</span></span>  
 [<span data-ttu-id="da80f-184">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="da80f-184">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
