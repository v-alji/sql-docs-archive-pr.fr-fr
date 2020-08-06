---
title: Méthode GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604368"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="26eda-102">Méthode GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="26eda-102">GenerateDatabaseCreationScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="26eda-103">Génère un script SQL qui peut être utilisé pour créer une base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="26eda-103">Generates a SQL Script that can be used to create a report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26eda-104">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="26eda-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="26eda-105">Paramètres</span><span class="sxs-lookup"><span data-stu-id="26eda-105">Parameters</span></span>  
 <span data-ttu-id="26eda-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="26eda-106">*Databasename*</span></span>  
 <span data-ttu-id="26eda-107">Chaîne contenant le nom de la base de données du serveur de rapports à créer.</span><span class="sxs-lookup"><span data-stu-id="26eda-107">A string containing the name of the report server database to create.</span></span>  
  
 <span data-ttu-id="26eda-108">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="26eda-108">*Lcid*</span></span>  
 <span data-ttu-id="26eda-109">Valeur utilisée pour la localisation des noms de rôles.</span><span class="sxs-lookup"><span data-stu-id="26eda-109">Value used for localization of role names.</span></span>  
  
 <span data-ttu-id="26eda-110">*IsSharePointMode*</span><span class="sxs-lookup"><span data-stu-id="26eda-110">*IsSharePointMode*</span></span>  
 <span data-ttu-id="26eda-111">Indique s'il convient de créer la base de données en mode natif ou mode SharePoint.</span><span class="sxs-lookup"><span data-stu-id="26eda-111">Indicates whether to create database in native mode or SharePoint mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="26eda-112">À compter de [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , *IsSharePointMode* = `True` n’est pas pris en charge, car en mode SharePoint, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] est un service partagé SharePoint et n’est pas contrôlé par le fournisseur WMI.</span><span class="sxs-lookup"><span data-stu-id="26eda-112">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *IsSharePointMode*=`True` is not supported because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is a SharePoint shared service and is not controlled by the WMI provider.</span></span> <span data-ttu-id="26eda-113">Ce paramètre doit toujours avoir la valeur `False`.</span><span class="sxs-lookup"><span data-stu-id="26eda-113">You should always set this parameter to `False`.</span></span>  
  
 <span data-ttu-id="26eda-114">*Script*</span><span class="sxs-lookup"><span data-stu-id="26eda-114">*Script*</span></span>  
 <span data-ttu-id="26eda-115">[out] Chaîne contenant le script SQL généré.</span><span class="sxs-lookup"><span data-stu-id="26eda-115">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="26eda-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="26eda-116">*HRESULT*</span></span>  
 <span data-ttu-id="26eda-117">[out] Valeur indiquant si l'appel a réussi ou échoué.</span><span class="sxs-lookup"><span data-stu-id="26eda-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="26eda-118">Valeur de retour</span><span class="sxs-lookup"><span data-stu-id="26eda-118">Return Value</span></span>  
 <span data-ttu-id="26eda-119">Retourne un paramètre *HRESULT* qui indique si l'appel de la méthode a réussi ou a échoué.</span><span class="sxs-lookup"><span data-stu-id="26eda-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="26eda-120">Une valeur 0 indique que l'appel de méthode a réussi.</span><span class="sxs-lookup"><span data-stu-id="26eda-120">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="26eda-121">Une valeur différente de zéro indique qu'une erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="26eda-121">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26eda-122">Notes</span><span class="sxs-lookup"><span data-stu-id="26eda-122">Remarks</span></span>  
 <span data-ttu-id="26eda-123">Cette méthode génère un script SQL qui crée des bases de données du serveur de rapports pour la version du serveur de rapports actuellement connecté.</span><span class="sxs-lookup"><span data-stu-id="26eda-123">This method generates an SQL script that creates report server databases for the version of the report server currently connected to.</span></span>  
  
 <span data-ttu-id="26eda-124">La valeur fournie dans le paramètre *DatabaseName* doit être conforme aux conventions d’affectation des noms de la base de données [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="26eda-124">The value supplied in the *DatabaseName* parameter must conform to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database naming conventions.</span></span>  
  
 <span data-ttu-id="26eda-125">La méthode ne vérifie pas l'existence de la base de données lors de la génération du script.</span><span class="sxs-lookup"><span data-stu-id="26eda-125">The method does not check the existence of the database when generating the script.</span></span>  
  
 <span data-ttu-id="26eda-126">Cette méthode ne vérifie pas l'existence de la base de données du serveur de rapports lors de la génération du script.</span><span class="sxs-lookup"><span data-stu-id="26eda-126">This method does not check for the existence of the report server database when generating the script.</span></span>  
  
 <span data-ttu-id="26eda-127">Le script généré prend en charge [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 et [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="26eda-127">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26eda-128">Spécifications</span><span class="sxs-lookup"><span data-stu-id="26eda-128">Requirements</span></span>  
 <span data-ttu-id="26eda-129">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26eda-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26eda-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26eda-130">See Also</span></span>  
 [<span data-ttu-id="26eda-131">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="26eda-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
