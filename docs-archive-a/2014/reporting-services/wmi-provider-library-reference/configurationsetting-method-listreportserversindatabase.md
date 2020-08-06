---
title: ListReportServersInDatabase, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- ListReportServersInDatabase method
ms.assetid: a4bf5968-c46f-484f-a510-65e2dde65a0d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9eaea72c0737124d89c86b55281326073597fb38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604359"
---
# <a name="listreportserversindatabase-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="11584-102">Méthode ListReportServersInDatabase (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="11584-102">ListReportServersInDatabase Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="11584-103">Retourne la liste des installations du serveur de rapports qui sont présentes dans la base de données du serveur de rapports, même si elles n'ont pas accès aux informations sécurisées.</span><span class="sxs-lookup"><span data-stu-id="11584-103">Returns the list of report server installations that are present in the report server database, regardless of whether they have access to secure information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11584-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="11584-104">Syntax</span></span>  
  
```vb  
Public Sub ListReportServersInDatabase(ByRef MachineNames() As String, _  
    ByRef InstanceNames() As String, ByRef InstallationIDs() As String, _  
    ByRef IsInitialized() As Boolean, ByRef Length As Int32, _  
    ByRef HRESULT As Int32, ByRef ExtendedErrors() As String)  
```  
  
```csharp  
public void ListReportServersInDatabase (out string[] MachineNames,   
    out string[] InstanceNames, out string[] InstallationIDs,   
    out Boolean[] IsInitialized,out Int32 Length, out Int32 HRESULT,    
    out string[] ExtendedErrors);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11584-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="11584-105">Parameters</span></span>  
 <span data-ttu-id="11584-106">*MachineNames[]*</span><span class="sxs-lookup"><span data-stu-id="11584-106">*MachineNames[]*</span></span>  
 <span data-ttu-id="11584-107">[out] Tableau contenant les noms de machines des installations du serveur de rapports dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="11584-107">[out] An array containing the machine names for the report server installations in the database.</span></span>  
  
 <span data-ttu-id="11584-108">*InstanceNames[]*</span><span class="sxs-lookup"><span data-stu-id="11584-108">*InstanceNames[]*</span></span>  
 <span data-ttu-id="11584-109">[out] Tableau contenant les noms d'instances de chacune des installations du serveur de rapports dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="11584-109">[out] An array containing the instance names of each of the report server installations in the database.</span></span>  
  
 <span data-ttu-id="11584-110">*InstallationIDs[]*</span><span class="sxs-lookup"><span data-stu-id="11584-110">*InstallationIDs[]*</span></span>  
 <span data-ttu-id="11584-111">[out] Tableau contenant l'ID d'installation de chaque installation du serveur de rapports dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="11584-111">[out] An array containing the installation IDs of each report server installation in the database.</span></span>  
  
 <span data-ttu-id="11584-112">*IsInitialized[]*</span><span class="sxs-lookup"><span data-stu-id="11584-112">*IsInitialized[]*</span></span>  
 <span data-ttu-id="11584-113">[out] Tableau contenant l'état d'initialisation de chaque installation du serveur de rapports dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="11584-113">[out] An array containing initialization status for each report server installation in the database.</span></span>  
  
 <span data-ttu-id="11584-114">*Longueur*</span><span class="sxs-lookup"><span data-stu-id="11584-114">*Length*</span></span>  
 <span data-ttu-id="11584-115">[out] Longueur des tableaux retournés par la méthode.</span><span class="sxs-lookup"><span data-stu-id="11584-115">[out] The length of the arrays returned by the method.</span></span> <span data-ttu-id="11584-116">Tous les tableaux retournés ont la même longueur.</span><span class="sxs-lookup"><span data-stu-id="11584-116">All returned arrays have the same length.</span></span>  
  
 <span data-ttu-id="11584-117">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="11584-117">*HRESULT*</span></span>  
 <span data-ttu-id="11584-118">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="11584-118">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
 <span data-ttu-id="11584-119">*ExtendedErrors[]*</span><span class="sxs-lookup"><span data-stu-id="11584-119">*ExtendedErrors[]*</span></span>  
 <span data-ttu-id="11584-120">[out] Tableau de chaînes contenant les erreurs supplémentaires retournées par l'appel.</span><span class="sxs-lookup"><span data-stu-id="11584-120">[out] A string array containing additional errors returned by the call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11584-121">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="11584-121">Return Value</span></span>  
 <span data-ttu-id="11584-122">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="11584-122">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="11584-123">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="11584-123">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="11584-124">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="11584-124">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11584-125">Notes</span><span class="sxs-lookup"><span data-stu-id="11584-125">Remarks</span></span>  
 <span data-ttu-id="11584-126">ListReportServersInDatabase répertorie les installations du serveur de rapports qui sont présentes dans la base de données du serveur de rapports, qu’elles aient accès ou non aux informations sécurisées, et retourne un ensemble de tableaux correspondants qui contiennent des informations à propos de chaque installation.</span><span class="sxs-lookup"><span data-stu-id="11584-126">ListReportServersInDatabase lists the report server installations that are present in the report server database, regardless of whether they have access to secure information, and returns a matched set of arrays containing information about each installation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11584-127">Spécifications</span><span class="sxs-lookup"><span data-stu-id="11584-127">Requirements</span></span>  
 <span data-ttu-id="11584-128">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11584-128">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11584-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="11584-129">See Also</span></span>  
 [<span data-ttu-id="11584-130">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="11584-130">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
