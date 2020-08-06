---
title: SetUnattendedExecutionAccount, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetUnattendedExecutionAccount method
ms.assetid: 1ba6be6f-b05c-4ea0-af98-cd0780290b70
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 73cf4c633c51de1e3e6b878c66d73ee710e98df6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706048"
---
# <a name="setunattendedexecutionaccount-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b5807-102">Méthode SetUnattendedExecutionAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b5807-102">SetUnattendedExecutionAccount Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b5807-103">Spécifie le compte utilisé pour exécuter des rapports sans assistance.</span><span class="sxs-lookup"><span data-stu-id="b5807-103">Specifies the account used to execute reports unattended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5807-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b5807-104">Syntax</span></span>  
  
```vb  
Public Sub SetUnattendedExecutionAccount(UserName as String, _  
    Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetUnattendedExecutionAccount (string UserName,   
    string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5807-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b5807-105">Parameters</span></span>  
 <span data-ttu-id="b5807-106">*UserName*</span><span class="sxs-lookup"><span data-stu-id="b5807-106">*UserName*</span></span>  
 <span data-ttu-id="b5807-107">Compte Windows à utiliser pour les exécutions sans assistance.</span><span class="sxs-lookup"><span data-stu-id="b5807-107">A Windows account to be used for unattended executions.</span></span>  
  
 <span data-ttu-id="b5807-108">*Mot de passe*</span><span class="sxs-lookup"><span data-stu-id="b5807-108">*Password*</span></span>  
 <span data-ttu-id="b5807-109">Mot de passe du compte spécifié.</span><span class="sxs-lookup"><span data-stu-id="b5807-109">The password for the specified account.</span></span>  
  
 <span data-ttu-id="b5807-110">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="b5807-110">*HRESULT*</span></span>  
 <span data-ttu-id="b5807-111">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="b5807-111">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5807-112">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b5807-112">Return Value</span></span>  
 <span data-ttu-id="b5807-113">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="b5807-113">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="b5807-114">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="b5807-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="b5807-115">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="b5807-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5807-116">Notes</span><span class="sxs-lookup"><span data-stu-id="b5807-116">Remarks</span></span>  
 <span data-ttu-id="b5807-117">La méthode SetUnattendedExecutionAccount ne vérifie pas si le serveur de rapports peut se connecter en tant que l’utilisateur spécifié.</span><span class="sxs-lookup"><span data-stu-id="b5807-117">The SetUnattendedExecutionAccount method does not verify whether the report server can log in as the specified user.</span></span>  
  
 <span data-ttu-id="b5807-118">Il est impossible d’utiliser la méthode SetUnattendedExecutionAccount pour exécuter des exécutions sans assistance dans le contexte du service Windows de serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b5807-118">It is not possible to use the SetUnattendedExecutionAccount method to run unattended executions in the context of the report server Windows service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5807-119">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b5807-119">Requirements</span></span>  
 <span data-ttu-id="b5807-120">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5807-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5807-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b5807-121">See Also</span></span>  
 [<span data-ttu-id="b5807-122">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b5807-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
