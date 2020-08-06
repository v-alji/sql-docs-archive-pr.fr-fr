---
title: ReencryptSecureInformation, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ReencryptSecureInformation method
ms.assetid: 8a487497-c207-45b2-8c92-87c58cc68716
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 1a0c657b69d624df8895ae4d5a6d12277b011b24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612155"
---
# <a name="reencryptsecureinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="699c2-102">Méthode ReencryptSecureInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="699c2-102">ReencryptSecureInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="699c2-103">Génère une nouvelle clé de chiffrement et rechiffre toutes les informations sécurisées dans le catalogue à l'aide de cette nouvelle clé.</span><span class="sxs-lookup"><span data-stu-id="699c2-103">Generates a new encryption key and re-encrypts all secure information in the catalog using this new key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="699c2-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="699c2-104">Syntax</span></span>  
  
```vb  
Public Sub ReencryptSecureInformation(ByRef HRESULT as Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ReencryptSecureInformation (out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="699c2-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="699c2-105">Parameters</span></span>  
 <span data-ttu-id="699c2-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="699c2-106">*HRESULT*</span></span>  
 <span data-ttu-id="699c2-107">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="699c2-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="699c2-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="699c2-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="699c2-109">[out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.</span><span class="sxs-lookup"><span data-stu-id="699c2-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="699c2-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="699c2-110">Return Value</span></span>  
 <span data-ttu-id="699c2-111">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="699c2-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="699c2-112">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="699c2-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="699c2-113">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="699c2-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="699c2-114">Notes</span><span class="sxs-lookup"><span data-stu-id="699c2-114">Remarks</span></span>  
 <span data-ttu-id="699c2-115">La méthode ReencryptSecureInformation permet à l’administrateur de remplacer la clé de chiffrement existante par une nouvelle clé.</span><span class="sxs-lookup"><span data-stu-id="699c2-115">The ReencryptSecureInformation method allows the administrator to replace the existing encryption key with a new key.</span></span>  
  
 <span data-ttu-id="699c2-116">Lorsque cette méthode est appelée, le serveur de rapports génère une nouvelle clé de chiffrement et parcourt tout le contenu chiffré afin de le rechiffrer avec la nouvelle clé de chiffrement.</span><span class="sxs-lookup"><span data-stu-id="699c2-116">When this method is invoked, the report server generates a new encryption key and iterates through all encrypted content to re-encrypt it with the new encryption key.</span></span>  
  
 <span data-ttu-id="699c2-117">Les extensions de remise peuvent stocker des informations sécurisées dans leurs structures de paramètres de remise.</span><span class="sxs-lookup"><span data-stu-id="699c2-117">Delivery extensions can store secured information in their delivery settings structures.</span></span> <span data-ttu-id="699c2-118">Quand ReencryptSecureInformation est appelée, le serveur de rapports charge chaque abonnement et l’extension de remise correspondante pour rechiffrer les informations stockées dans les paramètres associés.</span><span class="sxs-lookup"><span data-stu-id="699c2-118">When ReencryptSecureInformation is called, the report server loads each subscription and the corresponding delivery extension to re-encrypt information stored in the associated settings.</span></span>  
  
 <span data-ttu-id="699c2-119">Si cette méthode est exécutée sur un ordinateur dans un déploiement avec montée en puissance parallèle, chaque ordinateur dans le déploiement avec montée en puissance parallèle doit être réinitialisé.</span><span class="sxs-lookup"><span data-stu-id="699c2-119">If this method is run on a computer in a scale-out deployment, each computer in the scale-out deployment will need to be initialized again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="699c2-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="699c2-120">Requirements</span></span>  
 <span data-ttu-id="699c2-121">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="699c2-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="699c2-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="699c2-122">See Also</span></span>  
 [<span data-ttu-id="699c2-123">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="699c2-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
