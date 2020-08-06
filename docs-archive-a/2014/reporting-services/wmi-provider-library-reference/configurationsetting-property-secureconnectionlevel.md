---
title: SecureConnectionLevel, propriété (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SecureConnectionLevel
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SecureConnectionLevel property
ms.assetid: fd5549e7-b874-41e2-866e-2f58caf6f733
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5d1b3bccc8a7fee3899fa21208d83a718a33f5fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705996"
---
# <a name="secureconnectionlevel-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e84ab-102">Propriété SecureConnectionLevel (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="e84ab-102">SecureConnectionLevel Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e84ab-103">Retourne le niveau de connexion sécurisée qui est spécifié dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="e84ab-103">Returns the secure connection level specified in the RSReportServer.config file.</span></span> <span data-ttu-id="e84ab-104">Lecture seule.</span><span class="sxs-lookup"><span data-stu-id="e84ab-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e84ab-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="e84ab-105">Syntax</span></span>  
  
```vb  
Public Dim SecureConnectionLevel As Integer  
```  
  
```csharp  
public Integer SecureConnectionLevel;  
```  
  
## <a name="property-values"></a><span data-ttu-id="e84ab-106">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="e84ab-106">Property Values</span></span>  
 <span data-ttu-id="e84ab-107">Valeur `Integer` qui représente le niveau de connexion sécurisée.</span><span class="sxs-lookup"><span data-stu-id="e84ab-107">An `Integer` value that represents the secure connection level.</span></span> <span data-ttu-id="e84ab-108">Les valeurs de retour indiquent que le protocole SSL est configuré ou non.</span><span class="sxs-lookup"><span data-stu-id="e84ab-108">The return values indicate that the SSL is either configured or not.</span></span> <span data-ttu-id="e84ab-109">Une valeur supérieure ou égale à 1 indique que le protocole SSL est activé.</span><span class="sxs-lookup"><span data-stu-id="e84ab-109">A value of greater than or equal to 1 indicates that SSL is turned on.</span></span> <span data-ttu-id="e84ab-110">La valeur 0 indique que le protocole SSL est désactivé.</span><span class="sxs-lookup"><span data-stu-id="e84ab-110">A value of 0 indicates that SSL is turned off.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="e84ab-111">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="e84ab-111">Example Code</span></span>  
 [<span data-ttu-id="e84ab-112">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e84ab-112">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="e84ab-113">Spécifications</span><span class="sxs-lookup"><span data-stu-id="e84ab-113">Requirements</span></span>  
 <span data-ttu-id="e84ab-114">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e84ab-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e84ab-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e84ab-115">See Also</span></span>  
 [<span data-ttu-id="e84ab-116">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="e84ab-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
