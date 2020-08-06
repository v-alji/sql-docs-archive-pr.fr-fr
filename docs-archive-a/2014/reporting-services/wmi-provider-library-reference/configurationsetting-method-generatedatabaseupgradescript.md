---
title: GenerateDatabaseUpgradeScript, méthode (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseUpgradeScript method
ms.assetid: 88534e8e-2877-41cd-b5c2-b1d33a0fd203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a619584b9f1cc095f8f624670386d388426e4a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604365"
---
# <a name="generatedatabaseupgradescript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="0ccf6-102">Méthode GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="0ccf6-102">GenerateDatabaseUpgradeScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="0ccf6-103">Génère un script pouvant être utilisé pour mettre à niveau la base de données de serveur de rapports vers le schéma [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0ccf6-103">Generates a script that can be used to upgrade the report server database to the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ccf6-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="0ccf6-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseUpgradeScript(DatabaseName as String, _  
    ServerVersion as String, ByRef Script as String, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GenerateDatabaseUpgradeScript (string DatabaseName,   
    string ServerVersion, out string Script,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ccf6-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="0ccf6-105">Parameters</span></span>  
 <span data-ttu-id="0ccf6-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="0ccf6-106">*Databasename*</span></span>  
 <span data-ttu-id="0ccf6-107">Chaîne contenant le nom de la base de données du serveur de rapports à mettre à niveau.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-107">A string containing the name of the report server database to upgrade.</span></span>  
  
 <span data-ttu-id="0ccf6-108">*ServerVersion*</span><span class="sxs-lookup"><span data-stu-id="0ccf6-108">*ServerVersion*</span></span>  
 <span data-ttu-id="0ccf6-109">Chaîne contenant la version du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-109">A string containing the version of the report server.</span></span>  
  
 <span data-ttu-id="0ccf6-110">*Script*</span><span class="sxs-lookup"><span data-stu-id="0ccf6-110">*Script*</span></span>  
 <span data-ttu-id="0ccf6-111">[out] Chaîne contenant le script SQL généré.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-111">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="0ccf6-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="0ccf6-112">*HRESULT*</span></span>  
 <span data-ttu-id="0ccf6-113">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ccf6-114">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="0ccf6-114">Return Value</span></span>  
 <span data-ttu-id="0ccf6-115">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="0ccf6-116">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="0ccf6-117">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="0ccf6-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ccf6-118">Notes</span><span class="sxs-lookup"><span data-stu-id="0ccf6-118">Remarks</span></span>  
 <span data-ttu-id="0ccf6-119">Le script généré prend en charge [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]et [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ccf6-119">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ccf6-120">Spécifications</span><span class="sxs-lookup"><span data-stu-id="0ccf6-120">Requirements</span></span>  
 <span data-ttu-id="0ccf6-121">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ccf6-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ccf6-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ccf6-122">See Also</span></span>  
 [<span data-ttu-id="0ccf6-123">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="0ccf6-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
