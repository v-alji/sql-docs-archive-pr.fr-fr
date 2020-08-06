---
title: DeleteEncryptedInformation, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DeleteEncryptedInformation method
ms.assetid: c14ed187-bdd9-4304-88e3-72072f03c21b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: d00dc3e90816cd04c84f124cdc3d25a9ac122bba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604377"
---
# <a name="deleteencryptedinformation-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="1fcb6-102">Méthode DeleteEncryptedInformation (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="1fcb6-102">DeleteEncryptedInformation Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="1fcb6-103">Supprime les informations chiffrées de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-103">Deletes the encrypted information from the report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fcb6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="1fcb6-104">Syntax</span></span>  
  
```vb  
Public Sub DeleteEncryptedInformation(ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void DeleteEncryptedInformation(out Int32 HRESULT, out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fcb6-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="1fcb6-105">Parameters</span></span>  
 <span data-ttu-id="1fcb6-106">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="1fcb6-106">*HRESULT*</span></span>  
 <span data-ttu-id="1fcb6-107">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-107">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="1fcb6-108">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="1fcb6-108">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="1fcb6-109">[out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-109">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1fcb6-110">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="1fcb6-110">Return Value</span></span>  
 <span data-ttu-id="1fcb6-111">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-111">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="1fcb6-112">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-112">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="1fcb6-113">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-113">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fcb6-114">Notes</span><span class="sxs-lookup"><span data-stu-id="1fcb6-114">Remarks</span></span>  
 <span data-ttu-id="1fcb6-115">Lorsque cette méthode est appelée, les données suivantes sont supprimées :</span><span class="sxs-lookup"><span data-stu-id="1fcb6-115">When this method is invoked, the following data is deleted:</span></span>  
  
-   <span data-ttu-id="1fcb6-116">Informations de source de données chiffrées, y compris le nom d'utilisateur et le mot de passe.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-116">Data source information that is encrypted, including user name and password.</span></span>  
  
-   <span data-ttu-id="1fcb6-117">Données d'abonnement chiffrées à l'aide des interfaces d'extension de remise.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-117">Subscription data that is encrypted using the delivery extension interfaces.</span></span>  
  
-   <span data-ttu-id="1fcb6-118">Toutes les informations de la table de clés de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-118">All the information from the keys table in the report server database.</span></span>  
  
 <span data-ttu-id="1fcb6-119">Suite à l'appel de cette méthode, l'utilisateur doit initialiser chaque ordinateur qui utilise la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-119">After this method is invoked, the user must initialize each computer that uses the report server database.</span></span>  
  
 <span data-ttu-id="1fcb6-120">L’appel de la méthode DeleteEncryptedInformation n’affecte pas le fichier de configuration du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="1fcb6-120">Calling the DeleteEncryptedInformation method does not affect the report server configuration file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fcb6-121">Spécifications</span><span class="sxs-lookup"><span data-stu-id="1fcb6-121">Requirements</span></span>  
 <span data-ttu-id="1fcb6-122">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fcb6-122">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcb6-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1fcb6-123">See Also</span></span>  
 [<span data-ttu-id="1fcb6-124">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="1fcb6-124">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
