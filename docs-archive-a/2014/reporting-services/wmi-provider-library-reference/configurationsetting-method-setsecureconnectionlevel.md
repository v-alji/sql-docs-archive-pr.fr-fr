---
title: SetSecureConnectionLevel, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetSecureConnectionLevel method
ms.assetid: 0fac7d5e-2670-4657-9439-331e7d93babb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4361f09eb38b3e5650b68ae6f86b7f2266bbf1a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706055"
---
# <a name="setsecureconnectionlevel-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f6666-102">Méthode SetSecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="f6666-102">SetSecureConnectionLevel Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f6666-103">Définit le niveau de connexion sécurisée du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="f6666-103">Sets the secure connection level of the report server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6666-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="f6666-104">Syntax</span></span>  
  
```vb  
Public Sub SetSecureConnectionLevel(Level as Integer, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetSecureConnectionLevel(Int32 Level,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6666-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="f6666-105">Parameters</span></span>  
 <span data-ttu-id="f6666-106">*Niveau*</span><span class="sxs-lookup"><span data-stu-id="f6666-106">*Level*</span></span>  
 <span data-ttu-id="f6666-107">Valeur entière représentant un niveau de connexion sécurisée.</span><span class="sxs-lookup"><span data-stu-id="f6666-107">An integer value representing a secure connection level.</span></span>  
  
 <span data-ttu-id="f6666-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="f6666-108">*HRESULT*</span></span>  
 <span data-ttu-id="f6666-109">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="f6666-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6666-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="f6666-110">Return Value</span></span>  
 <span data-ttu-id="f6666-111">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="f6666-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="f6666-112">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="f6666-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="f6666-113">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="f6666-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6666-114">Notes</span><span class="sxs-lookup"><span data-stu-id="f6666-114">Remarks</span></span>  
 <span data-ttu-id="f6666-115">Quand cette méthode est appelée, la propriété de serveur de rapports SecureConnectionLevel prend la valeur spécifiée.</span><span class="sxs-lookup"><span data-stu-id="f6666-115">When called, the report server SecureConnectionLevel property is set to the value specified.</span></span> <span data-ttu-id="f6666-116">La valeur 0 indique que le protocole SSL est désactivé.</span><span class="sxs-lookup"><span data-stu-id="f6666-116">A value of 0 indicates that SSL is turned off.</span></span> <span data-ttu-id="f6666-117">Une valeur supérieure ou égale à 1 indique que le protocole SSL est activé.</span><span class="sxs-lookup"><span data-stu-id="f6666-117">A value greater than or equal to 1 indicates that SSL is turned on.</span></span>  
  
-   <span data-ttu-id="f6666-118">Lorsque la valeur est définie, l’élément SecureConnectionLevel dans le fichier de configuration du serveur de rapports est modifié et l' `URLRoot` élément dans le fichier de configuration est défini de façon à utiliser « https:// » si le *niveau* spécifié est supérieur ou égal à 1, ou « http:// » si le *niveau* spécifié est 0.</span><span class="sxs-lookup"><span data-stu-id="f6666-118">When the value is set, the SecureConnectionLevel element in the report server configuration file is changed, and the `URLRoot` element in the configuration file is set to use "https://" if the specified *Level* is greater than or equal to 1, or "http://" if the specified *Level* is 0.</span></span>  
  
 <span data-ttu-id="f6666-119">Dans [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel est un commutateur d’activation ou de désactivation. La valeur par défaut est 0.</span><span class="sxs-lookup"><span data-stu-id="f6666-119">In [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], SecureConnectionLevel is made an on/off switch, default value is 0.</span></span> <span data-ttu-id="f6666-120">Pour toute valeur supérieure ou égale à 1 passée par le biais de l’API de la méthode SetSecureConnectionLevel, le protocole SSL est considéré comme activé et la propriété de configuration SecureConnectionLevel est définie en conséquence dans le fichier rsreportserver.config.</span><span class="sxs-lookup"><span data-stu-id="f6666-120">For any value greater than or equal to 1 passed through SetSecureConnectionLevel method API, SSL is considered on and the configuration property SecureConnectionLevel is set accordingly in the rsreportserver.config file.</span></span> <span data-ttu-id="f6666-121">Les valeurs 2 et 3 sont toujours autorisées pour des raisons de compatibilité descendante.</span><span class="sxs-lookup"><span data-stu-id="f6666-121">Values of 2 and 3 are still allowed for backward compatibility.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6666-122">Spécifications</span><span class="sxs-lookup"><span data-stu-id="f6666-122">Requirements</span></span>  
 <span data-ttu-id="f6666-123">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6666-123">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6666-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f6666-124">See Also</span></span>  
 [<span data-ttu-id="f6666-125">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="f6666-125">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
