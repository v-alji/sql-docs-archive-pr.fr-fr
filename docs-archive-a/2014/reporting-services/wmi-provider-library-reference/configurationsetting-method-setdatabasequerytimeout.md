---
title: SetDatabaseQueryTimeout, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDatabaseQueryTimeout method
ms.assetid: bd2809e5-7848-45b3-a502-b04fc698b646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ab6b5bf27eca5e9d6d083d03af48c0ab71b4dd2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706059"
---
# <a name="setdatabasequerytimeout-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="ef4e1-102">Méthode SetDatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="ef4e1-102">SetDatabaseQueryTimeout Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="ef4e1-103">Spécifie la valeur de délai par défaut pour les requêtes sur la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ef4e1-103">Specifies the default time-out value for report server database queries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef4e1-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ef4e1-104">Syntax</span></span>  
  
```vb  
Public Sub SetDatabaseQueryTimeout(LogonTimeout as Int32, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetDatabaseQueryTimeout (Int32 LogonTimeout,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef4e1-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="ef4e1-105">Parameters</span></span>  
 <span data-ttu-id="ef4e1-106">*LogonTimeout*</span><span class="sxs-lookup"><span data-stu-id="ef4e1-106">*LogonTimeout*</span></span>  
 <span data-ttu-id="ef4e1-107">Valeur de délai par défaut, en secondes, pour les requêtes sur la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ef4e1-107">The default timeout value, in seconds, for report server database queries.</span></span>  
  
 <span data-ttu-id="ef4e1-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="ef4e1-108">*HRESULT*</span></span>  
 <span data-ttu-id="ef4e1-109">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="ef4e1-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef4e1-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="ef4e1-110">Return Value</span></span>  
 <span data-ttu-id="ef4e1-111">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="ef4e1-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="ef4e1-112">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="ef4e1-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="ef4e1-113">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="ef4e1-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef4e1-114">Spécifications</span><span class="sxs-lookup"><span data-stu-id="ef4e1-114">Requirements</span></span>  
 <span data-ttu-id="ef4e1-115">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef4e1-115">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef4e1-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ef4e1-116">See Also</span></span>  
 [<span data-ttu-id="ef4e1-117">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="ef4e1-117">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
