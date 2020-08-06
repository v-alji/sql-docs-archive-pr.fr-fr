---
title: SetDatabaseLogonTimeout, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseLogonTimeout method
ms.assetid: b8773596-5b98-4355-a4ab-4412e1317c67
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bf93cd9158c3489db611446ac8523701f52831f4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706067"
---
# <a name="setdatabaselogontimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="76a52-102">Méthode SetDatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="76a52-102">SetDatabaseLogonTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="76a52-103">Spécifie la valeur de délai par défaut pour l'établissement d'une connexion à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="76a52-103">Specifies the default timeout value for report server database connections.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a52-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="76a52-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseLogonTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseLogonTimeout(Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76a52-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="76a52-105">Parameters</span></span>  
 <span data-ttu-id="76a52-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="76a52-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="76a52-107">Valeur de délai par défaut, en secondes, pour l'établissement d'une connexion à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="76a52-107">The default time-out value, in seconds, for report server database connections.</span></span>  
  
 <span data-ttu-id="76a52-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="76a52-108">*HRESULT*</span></span>  
 <span data-ttu-id="76a52-109">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="76a52-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76a52-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="76a52-110">Return Value</span></span>  
 <span data-ttu-id="76a52-111">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="76a52-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="76a52-112">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="76a52-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="76a52-113">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="76a52-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76a52-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="76a52-114">Requirements</span></span>  
 <span data-ttu-id="76a52-115">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a52-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a52-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76a52-116">See Also</span></span>  
 [<span data-ttu-id="76a52-117">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="76a52-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
