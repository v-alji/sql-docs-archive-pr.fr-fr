---
title: DatabaseLogonAccount, propriété (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706028"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="09bbb-102">Propriété DatabaseLogonAccount (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="09bbb-102">DatabaseLogonAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="09bbb-103">Spécifie le compte d'ouverture de session utilisé par le serveur de rapports lors de la connexion à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="09bbb-103">Specifies the logon account that the report server uses when connecting to the report server database.</span></span> <span data-ttu-id="09bbb-104">Lecture seule.</span><span class="sxs-lookup"><span data-stu-id="09bbb-104">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09bbb-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="09bbb-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="09bbb-106">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="09bbb-106">Property Values</span></span>  
 <span data-ttu-id="09bbb-107">Objet `String` qui représente le nom du compte d'ouverture de session.</span><span class="sxs-lookup"><span data-stu-id="09bbb-107">A `String` object that represents the logon account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="09bbb-108">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="09bbb-108">Example Code</span></span>  
 [<span data-ttu-id="09bbb-109">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="09bbb-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="09bbb-110">Notes</span><span class="sxs-lookup"><span data-stu-id="09bbb-110">Remarks</span></span>  
 <span data-ttu-id="09bbb-111">Les valeurs valides pour cette propriété varient selon la valeur de la propriété [DatabaseLogonType](configurationsetting-property-databaselogontype.md) .</span><span class="sxs-lookup"><span data-stu-id="09bbb-111">Valid values for this property will vary depending on the value of the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property.</span></span>  
  
 <span data-ttu-id="09bbb-112">Cette propriété est ignorée si la propriété [DatabaseLogonType](configurationsetting-property-databaselogontype.md) a la valeur `2 (Service)` .</span><span class="sxs-lookup"><span data-stu-id="09bbb-112">This property is ignored if the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property is set to `2 (Service)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09bbb-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="09bbb-113">Requirements</span></span>  
 <span data-ttu-id="09bbb-114">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09bbb-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09bbb-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09bbb-115">See Also</span></span>  
 [<span data-ttu-id="09bbb-116">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="09bbb-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
