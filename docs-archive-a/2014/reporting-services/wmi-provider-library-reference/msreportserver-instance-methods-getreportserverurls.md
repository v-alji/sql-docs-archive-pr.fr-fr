---
title: GetReportServerUrls, méthode (WMI MSReportServer_Instance) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetReportServerUrls method
ms.assetid: 4865e32c-0114-465a-be8c-be223a7bc09e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f36a5ba10c05276cffabc155e5289d675db8dae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702355"
---
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a><span data-ttu-id="82b42-102">Méthode GetReportServerUrls (WMI MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="82b42-102">GetReportServerUrls Method (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="82b42-103">Retourne la liste des URL que les utilisateurs peuvent employer pour accéder au serveur de rapports et au Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="82b42-103">Returns a list of URLs users can use to access the report server and report manager.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82b42-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="82b42-104">Syntax</span></span>  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82b42-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="82b42-105">Parameters</span></span>  
 <span data-ttu-id="82b42-106">*ApplicationName[]*</span><span class="sxs-lookup"><span data-stu-id="82b42-106">*ApplicationName[]*</span></span>  
 <span data-ttu-id="82b42-107">Tableau qui contient les applications installées.</span><span class="sxs-lookup"><span data-stu-id="82b42-107">An array that contains the applications that are installed.</span></span> <span data-ttu-id="82b42-108">Les valeurs possibles sont `ReportServerWebService` et `ReportManager`.</span><span class="sxs-lookup"><span data-stu-id="82b42-108">Values are either `ReportServerWebService` or `ReportManager`.</span></span>  
  
 <span data-ttu-id="82b42-109">*URLs[]*</span><span class="sxs-lookup"><span data-stu-id="82b42-109">*URLs[]*</span></span>  
 <span data-ttu-id="82b42-110">Tableau qui contient les URL inscrites avec succès.</span><span class="sxs-lookup"><span data-stu-id="82b42-110">An array that contains the successfully registered Urls.</span></span>  
  
 <span data-ttu-id="82b42-111">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="82b42-111">*Length*</span></span>  
 <span data-ttu-id="82b42-112">Valeur entière qui contient la longueur des tableaux retournés.</span><span class="sxs-lookup"><span data-stu-id="82b42-112">An integer value that contains the length of the arrays returned.</span></span>  
  
 <span data-ttu-id="82b42-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="82b42-113">*HRESULT*</span></span>  
 <span data-ttu-id="82b42-114">Valeur qui indique le succès ou un code d'erreur.</span><span class="sxs-lookup"><span data-stu-id="82b42-114">A value that indicates success or an error code.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="82b42-115">Valeurs de retour</span><span class="sxs-lookup"><span data-stu-id="82b42-115">Return Values</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82b42-116">Notes</span><span class="sxs-lookup"><span data-stu-id="82b42-116">Remarks</span></span>  
 <span data-ttu-id="82b42-117">Les méthodes exposées par les objets de gestion WMI sont appelées par le biais de la fonction InvokeMethod.</span><span class="sxs-lookup"><span data-stu-id="82b42-117">Methods exposed by WMI management objects are called through the InvokeMethod function.</span></span> <span data-ttu-id="82b42-118">Pour plus d’informations, consultez la section relative à l’exécution des méthodes sur des objets de gestion dans la documentation WMI du [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="82b42-118">For more information, please see "Executing Methods on Management Objects" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82b42-119">Spécifications</span><span class="sxs-lookup"><span data-stu-id="82b42-119">Requirements</span></span>  
 <span data-ttu-id="82b42-120">**Espace de noms :** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82b42-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b42-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="82b42-121">See Also</span></span>  
 [<span data-ttu-id="82b42-122">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="82b42-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
