---
title: DatabaseLogonType, propriété (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonType
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonType property
ms.assetid: 6b592582-4c35-4029-ab86-982fff47d8d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bb5a4149c29fb7532b7140a2616dd856e6db2b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706019"
---
# <a name="databaselogontype-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="bbbb1-102">Propriété DatabaseLogonType (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="bbbb1-102">DatabaseLogonType Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="bbbb1-103">Spécifie si le serveur de rapports utilise un compte de service [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, un compte d’utilisateur Windows ou un compte de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour accéder à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-103">Specifies whether the report server uses a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service account, a Windows user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to access the report server database.</span></span> <span data-ttu-id="bbbb1-104">Lecture seule.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbbb1-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bbbb1-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonType As Integer  
```  
  
```csharp  
public int DatabaseLogonType;  
```  
  
## <a name="property-values"></a><span data-ttu-id="bbbb1-106">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="bbbb1-106">Property Values</span></span>  
 <span data-ttu-id="bbbb1-107">Objet `integer` qui représente le type de connexion.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-107">An `integer` object that represents the login type.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="bbbb1-108">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="bbbb1-108">Example Code</span></span>  
 [<span data-ttu-id="bbbb1-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="bbbb1-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="bbbb1-110">Notes</span><span class="sxs-lookup"><span data-stu-id="bbbb1-110">Remarks</span></span>  
 <span data-ttu-id="bbbb1-111">Les valeurs sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="bbbb1-111">Values are:</span></span>  
  
-   <span data-ttu-id="bbbb1-112">0 pour une connexion Windows</span><span class="sxs-lookup"><span data-stu-id="bbbb1-112">0 for Windows login</span></span>  
  
-   <span data-ttu-id="bbbb1-113">1 pour une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbbb1-113">1 for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login</span></span>  
  
-   <span data-ttu-id="bbbb1-114">2 pour une connexion en tant que service.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-114">2 to log in as a service</span></span>  
  
 <span data-ttu-id="bbbb1-115">Si vous spécifiez 0 (Windows), vous devez définir la valeur dans la propriété [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) en fonction d’un compte d’utilisateur Windows valide correspondant.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-115">If you specify 0 (Windows), you must set the value in the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) property to a corresponding a valid Windows user account.</span></span>  
  
 <span data-ttu-id="bbbb1-116">Si vous spécifiez 1 (SQL Server), assurez-vous que la valeur de la propriété [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) correspond à une connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] valide.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-116">If you specify 1 (SQL Server), make sure the value of the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponds to a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="bbbb1-117">Si vous spécifiez 2 (service Windows), le serveur de rapports utilise un compte [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] et le compte de service Windows pour accéder à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-117">If you specify 2 (Windows service), the report server uses an [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account and the Windows service account to access the report server database.</span></span> <span data-ttu-id="bbbb1-118">La propriété DatabaseLogonAccount est ignorée.</span><span class="sxs-lookup"><span data-stu-id="bbbb1-118">The DatabaseLogonAccount property is ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbbb1-119">Spécifications</span><span class="sxs-lookup"><span data-stu-id="bbbb1-119">Requirements</span></span>  
 <span data-ttu-id="bbbb1-120">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbbb1-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbb1-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bbbb1-121">See Also</span></span>  
 [<span data-ttu-id="bbbb1-122">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="bbbb1-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
