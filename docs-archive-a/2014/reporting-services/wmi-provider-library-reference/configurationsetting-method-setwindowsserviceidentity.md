---
title: SetWindowsServiceIdentity, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetWindowsServiceIdentity method
ms.assetid: 9bbc734c-9e69-48c2-8bec-8abe7c6cc987
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15d1b7fa5fc6d69a963785cdaf976c80623c47f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706032"
---
# <a name="setwindowsserviceidentity-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="05163-102">Méthode SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="05163-102">SetWindowsServiceIdentity Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="05163-103">Fait en sorte que le service Windows Report Server s'exécute en tant qu'utilisateur Windows spécifié et accorde des autorisations de système de fichiers suffisantes à ce compte pour permettre au serveur de rapports de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="05163-103">Makes the Report Server Windows service run as a specified Windows user, and grants this account sufficient file system permissions to allow the report server to operate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05163-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="05163-104">Syntax</span></span>  
  
```vb  
Public Sub SetWindowsServiceIdentity(UseBuiltInAccount as Boolean, _  
    Account as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetWindowsServiceIdentity(boolean UseBuiltInAccount,   
    string Account, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05163-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="05163-105">Parameters</span></span>  
 <span data-ttu-id="05163-106">*UseBuiltInAccount*</span><span class="sxs-lookup"><span data-stu-id="05163-106">*UseBuiltInAccount*</span></span>  
 <span data-ttu-id="05163-107">Indique si le compte spécifié est un compte Windows intégré.</span><span class="sxs-lookup"><span data-stu-id="05163-107">Indicates whether the specified account is a built-in Windows account.</span></span>  
  
 <span data-ttu-id="05163-108">*Compte*</span><span class="sxs-lookup"><span data-stu-id="05163-108">*Account*</span></span>  
 <span data-ttu-id="05163-109">Compte Windows à utiliser pour exécuter le service Windows, au format « DOMAINE\alias ».</span><span class="sxs-lookup"><span data-stu-id="05163-109">The Windows account to use to run the Windows service, in the format "DOMAIN\alias".</span></span>  
  
 <span data-ttu-id="05163-110">*Mot de passe*</span><span class="sxs-lookup"><span data-stu-id="05163-110">*Password*</span></span>  
 <span data-ttu-id="05163-111">Mot de passe du compte.</span><span class="sxs-lookup"><span data-stu-id="05163-111">The password for the account.</span></span>  
  
 <span data-ttu-id="05163-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="05163-112">*HRESULT*</span></span>  
 <span data-ttu-id="05163-113">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="05163-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05163-114">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="05163-114">Return Value</span></span>  
 <span data-ttu-id="05163-115">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="05163-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="05163-116">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="05163-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="05163-117">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="05163-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05163-118">Notes</span><span class="sxs-lookup"><span data-stu-id="05163-118">Remarks</span></span>  
 <span data-ttu-id="05163-119">Lorsque le paramètre *UseBuiltInAccount a* a la `true` valeur et que le serveur de rapports s’exécute sur Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] ou Windows XP, la valeur des paramètres *Name*, *Domain*et *Password* est ignorée et le compte système local est utilisé.</span><span class="sxs-lookup"><span data-stu-id="05163-119">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] or Windows XP, the value of the *Name*, *Domain*, and *Password* parameters are ignored and the Local system account is used.</span></span>  
  
 <span data-ttu-id="05163-120">Lorsque le paramètre *UseBuiltInAccount a* a la valeur `true` et que le serveur de rapports s’exécute sur Windows Server 2003, les propriétés *Domain* et *Password* sont ignorées, et le champ Name doit contenir « Builtin\System » ou « , » ou « Builtin\LocalService ».</span><span class="sxs-lookup"><span data-stu-id="05163-120">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Windows Server 2003, the *Domain* and *Password* properties are ignored, and the name field must contain either "Builtin\NetworkService" or "Builtin\System" or "Builtin\LocalService".</span></span>  
  
 <span data-ttu-id="05163-121">La méthode SetWindowsServiceIdentity définit des autorisations d’accès aux fichiers sur les fichiers et les dossiers dans le répertoire d’installation du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="05163-121">The SetWindowsServiceIdentity method sets file permissions on files and folders in the report server installation directory.</span></span>  
  
 <span data-ttu-id="05163-122">Le compte spécifié dans le paramètre de *compte* requiert `LogonAsService` des droits dans Windows.</span><span class="sxs-lookup"><span data-stu-id="05163-122">The account specified in the *Account* parameter requires `LogonAsService` rights in Windows.</span></span> <span data-ttu-id="05163-123">La méthode accorde ce droit au compte spécifié.</span><span class="sxs-lookup"><span data-stu-id="05163-123">The method grants this right to the specified account.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05163-124">Spécifications</span><span class="sxs-lookup"><span data-stu-id="05163-124">Requirements</span></span>  
 <span data-ttu-id="05163-125">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05163-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05163-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="05163-126">See Also</span></span>  
 [<span data-ttu-id="05163-127">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="05163-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
