---
title: DeleteEncryptionKey, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptionKey method
ms.assetid: ed2f25b6-6a63-468d-9279-a577ca01b096
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0e302659615bd620b3b0ed802b83aafc4e9506d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604370"
---
# <a name="deleteencryptionkey-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="b2b2e-102">Méthode DeleteEncryptionKey (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="b2b2e-102">DeleteEncryptionKey Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="b2b2e-103">Supprime les clés de chiffrement de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-103">Deletes the encryption keys from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2b2e-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="b2b2e-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptionKeys(ByVal InstallationID As String, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptionKeys(string InstallationID, out Int32 HRESULT,   
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2b2e-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="b2b2e-105">Parameters</span></span>  
 <span data-ttu-id="b2b2e-106">*InstallationID*</span><span class="sxs-lookup"><span data-stu-id="b2b2e-106">*InstallationID*</span></span>  
 <span data-ttu-id="b2b2e-107">ID d'installation d'un serveur de rapports figurant dans la table de clés de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-107">The installation ID of a report server that is in the keys table of the report server database.</span></span>  
  
 <span data-ttu-id="b2b2e-108">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="b2b2e-108">*HRESULT*</span></span>  
 <span data-ttu-id="b2b2e-109">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-109">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="b2b2e-110">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="b2b2e-110">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="b2b2e-111">[out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-111">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2b2e-112">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="b2b2e-112">Return Value</span></span>  
 <span data-ttu-id="b2b2e-113">Retourne un paramètre HRESULT indiquant si l'appel de la méthode a abouti ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-113">Returns an HRESULT indicating success or failure of the method call.</span></span> <span data-ttu-id="b2b2e-114">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-114">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="b2b2e-115">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-115">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2b2e-116">Notes</span><span class="sxs-lookup"><span data-stu-id="b2b2e-116">Remarks</span></span>  
 <span data-ttu-id="b2b2e-117">La méthode *DeleteEncryptionKey* supprime les entrées de la table de clés pour les serveurs de rapports qui ont accès aux informations sécurisées dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-117">The *DeleteEncryptionKey* method deletes entries from the keys table for any report servers that have access to the secure information in the report server database.</span></span> <span data-ttu-id="b2b2e-118">Si le paramètre *InstallationID* spécifié ne correspond pas à un ID d'installation figurant dans la base de données, la méthode retourne une erreur.</span><span class="sxs-lookup"><span data-stu-id="b2b2e-118">If the *InstallationID* parameter specified does not correspond to an installation ID in the database, the method returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2b2e-119">Spécifications</span><span class="sxs-lookup"><span data-stu-id="b2b2e-119">Requirements</span></span>  
 <span data-ttu-id="b2b2e-120">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2b2e-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b2e-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2b2e-121">See Also</span></span>  
 [<span data-ttu-id="b2b2e-122">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b2b2e-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
