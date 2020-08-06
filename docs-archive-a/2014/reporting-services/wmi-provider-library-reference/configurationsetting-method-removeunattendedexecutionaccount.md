---
title: Méthode RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- RemoveUnattendedExecutionAccount method
ms.assetid: 77e371c1-7c26-44f9-9119-7c8dc838db32
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: efe0523c9aa13315399c043367ef05a63da46e91
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703751"
---
# <a name="removeunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="0c496-102">Méthode RemoveUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="0c496-102">RemoveUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="0c496-103">Supprime l'entrée de compte d'exécution sans assistance du fichier de configuration du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0c496-103">Deletes the unattended execution account entry from the report server configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c496-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0c496-104">Syntax</span></span>  
  
```vb  
Public Sub RemoveUnattendedExecutionAccount(ByRef HRESULT as Int32)  
```  
  
```csharp  
public void RemoveUnattendedExecutionAccount (out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c496-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0c496-105">Parameters</span></span>  
 <span data-ttu-id="0c496-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="0c496-106">*HRESULT*</span></span>  
 <span data-ttu-id="0c496-107">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="0c496-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c496-108">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="0c496-108">Return Value</span></span>  
 <span data-ttu-id="0c496-109">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="0c496-109">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="0c496-110">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="0c496-110">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="0c496-111">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="0c496-111">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c496-112">Spécifications</span><span class="sxs-lookup"><span data-stu-id="0c496-112">Requirements</span></span>  
 <span data-ttu-id="0c496-113">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c496-113">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c496-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c496-114">See Also</span></span>  
 [<span data-ttu-id="0c496-115">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="0c496-115">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
