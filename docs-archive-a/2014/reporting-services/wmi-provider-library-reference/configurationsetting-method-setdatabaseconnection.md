---
title: SetDatabaseConnection, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseConnection method
ms.assetid: c040aa78-92b8-41e4-9ae2-eff9fcdddc5b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b5c62777edd1fab2b0cb3babc13ab09f7bcf32a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706068"
---
# <a name="setdatabaseconnection-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="81c51-102">Méthode SetDatabaseConnection (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="81c51-102">SetDatabaseConnection Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="81c51-103">Définit la connexion à une base de données de serveur de rapports spécifique.</span><span class="sxs-lookup"><span data-stu-id="81c51-103">Sets the report server database connection to a particular report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c51-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="81c51-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseConnection(Server as String, _  
    DatabaseName as string, CredentialsType as Integer, _  
    Username as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void BackupEncryptionKey(string Server,   
    string DatabaseName, Int32 CredentialsType,   
    string UserName, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81c51-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="81c51-105">Parameters</span></span>  
 <span data-ttu-id="81c51-106">*Serveur*</span><span class="sxs-lookup"><span data-stu-id="81c51-106">*Server*</span></span>  
 <span data-ttu-id="81c51-107">Nom de l’instance [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utilisée pour héberger la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="81c51-107">The name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is used to host the report server database.</span></span>  
  
 <span data-ttu-id="81c51-108">*DatabaseName*</span><span class="sxs-lookup"><span data-stu-id="81c51-108">*DatabaseName*</span></span>  
 <span data-ttu-id="81c51-109">Nom de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="81c51-109">The name of the report server database.</span></span>  
  
 <span data-ttu-id="81c51-110">*CredentialsType*</span><span class="sxs-lookup"><span data-stu-id="81c51-110">*CredentialsType*</span></span>  
 <span data-ttu-id="81c51-111">Type d'informations d'identification à utiliser pour la connexion.</span><span class="sxs-lookup"><span data-stu-id="81c51-111">The type of credentials to use for the connection.</span></span> <span data-ttu-id="81c51-112">Les valeurs peuvent être les suivantes :</span><span class="sxs-lookup"><span data-stu-id="81c51-112">Values can be:</span></span>  
  
-   <span data-ttu-id="81c51-113">0 - Windows</span><span class="sxs-lookup"><span data-stu-id="81c51-113">0 - Windows</span></span>  
  
-   <span data-ttu-id="81c51-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c51-114">1 - [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
  
-   <span data-ttu-id="81c51-115">2 - Service Windows</span><span class="sxs-lookup"><span data-stu-id="81c51-115">2 - Windows Service</span></span>  
  
 <span data-ttu-id="81c51-116">*UserName*</span><span class="sxs-lookup"><span data-stu-id="81c51-116">*UserName*</span></span>  
 <span data-ttu-id="81c51-117">Nom du compte utilisé pour établir la connexion à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="81c51-117">The account name used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="81c51-118">*Mot de passe*</span><span class="sxs-lookup"><span data-stu-id="81c51-118">*Password*</span></span>  
 <span data-ttu-id="81c51-119">Mot de passe utilisé pour établir la connexion à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="81c51-119">The password used to connect to the report server database.</span></span>  
  
 <span data-ttu-id="81c51-120">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="81c51-120">*HRESULT*</span></span>  
 <span data-ttu-id="81c51-121">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="81c51-121">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81c51-122">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="81c51-122">Return Value</span></span>  
 <span data-ttu-id="81c51-123">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="81c51-123">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="81c51-124">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="81c51-124">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="81c51-125">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="81c51-125">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81c51-126">Notes</span><span class="sxs-lookup"><span data-stu-id="81c51-126">Remarks</span></span>  
 <span data-ttu-id="81c51-127">Quand le paramètre *CredentialsType* a la valeur 0 (Windows), les paramètres *UserName* et *Password* doivent être définis.</span><span class="sxs-lookup"><span data-stu-id="81c51-127">When the *CredentialsType* parameter is set to 0 (Windows), the *UserName* and *Password* parameters must be set.</span></span> <span data-ttu-id="81c51-128">Le paramètre *UserName* doit être au format « domaine\nom utilisateur », et la valeur doit représenter une ouverture de session Windows valide.</span><span class="sxs-lookup"><span data-stu-id="81c51-128">The *UserName* parameter must be in the form "domain\username", and the value must represent a valid Windows logon.</span></span>  
  
 <span data-ttu-id="81c51-129">Quand le paramètre *CredentialsType* a la valeur 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), la valeur transmise dans le paramètre *UserName* doit être conforme aux spécifications d’un nom de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="81c51-129">When the *CredentialsType* parameter is set to 1 ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]), the value passed in the *UserName* parameter must conform to the requirements of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login name.</span></span>  
  
 <span data-ttu-id="81c51-130">Quand le paramètre *CredentialsType* a la valeur 2 (Service Windows), le serveur de rapports utilise la sécurité intégrée pour se connecter à la base de données du serveur de rapports, et les paramètres *UserName* et *Password* sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="81c51-130">When the *CredentialsType* parameter is set to 2 (Windows Service), the report server uses integrated security to connect to the report server database and the *UserName* and *Password* parameters are ignored.</span></span> <span data-ttu-id="81c51-131">Le service web Report Server utilise soit le compte [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)], soit le compte d’un pool d’applications et le compte de service Windows pour accéder à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="81c51-131">The Reporting Server Web service will use either the [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account or an application pool's account and the Windows service account to access the report server database.</span></span>  
  
 <span data-ttu-id="81c51-132">Quand la méthode SetDatabaseConnection est appelée, elle chiffre et stocke les informations d’identification et les informations sur la base de données dans le fichier de configuration du serveur de rapports spécifié.</span><span class="sxs-lookup"><span data-stu-id="81c51-132">When called, the SetDatabaseConnection method encrypts and stores the credentials and database information in the configuration file for the specified report server.</span></span>  
  
 <span data-ttu-id="81c51-133">La méthode SetDatabaseConnection ne vérifie pas si le serveur de rapports peut se connecter à la base de données à l’aide des données spécifiées.</span><span class="sxs-lookup"><span data-stu-id="81c51-133">The SetDatabaseConnection method does not check that the report server can connect to the report server database using the data specified.</span></span>  
  
 <span data-ttu-id="81c51-134">Quand elle est configurée pour la première fois, la propriété ConnectionPoolSize est définie selon les processeurs suivants : ConnectionPoolSize = #Processors \* 75.</span><span class="sxs-lookup"><span data-stu-id="81c51-134">When set for the first time, the ConnectionPoolSize property is set based on the following processors: ConnectionPoolSize = #Processors \* 75.</span></span>  
  
 <span data-ttu-id="81c51-135">La méthode SetDatabaseConnection n’accorde pas d’autorisations aux comptes spécifiés.</span><span class="sxs-lookup"><span data-stu-id="81c51-135">The SetDatabaseConnection method does not grant permissions to the specified account(s).</span></span> <span data-ttu-id="81c51-136">Vous devez appeler la méthode [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) pour chaque compte qui doit accéder à la base de données du serveur de rapports et exécuter le script obtenu.</span><span class="sxs-lookup"><span data-stu-id="81c51-136">You must call the [GenerateDatabaseRightsScript](configurationsetting-method-generatedatabaserightsscript.md) method for each account that requires access to the report server database and run the resulting script.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81c51-137">Spécifications</span><span class="sxs-lookup"><span data-stu-id="81c51-137">Requirements</span></span>  
 <span data-ttu-id="81c51-138">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c51-138">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c51-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="81c51-139">See Also</span></span>  
 [<span data-ttu-id="81c51-140">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="81c51-140">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
