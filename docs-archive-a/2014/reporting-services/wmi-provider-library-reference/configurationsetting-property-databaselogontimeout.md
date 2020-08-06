---
title: DatabaseLogonTimeout, propriété (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonTimeout property
ms.assetid: 4a65162c-33de-485e-8fd3-2bd6bff8bf8d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4920f5ef2282478f4d12a19b0806cf6ff9632cac
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706020"
---
# <a name="databaselogontimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="c4102-102">Propriété DatabaseLogonTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="c4102-102">DatabaseLogonTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="c4102-103">Spécifie le délai d'attente, en secondes, avant l'échec d'une tentative de connexion à la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="c4102-103">Specifies the number of seconds to wait before an attempt to log on to the report server database fails.</span></span> <span data-ttu-id="c4102-104">La valeur **0** indique une durée d’attente illimitée.</span><span class="sxs-lookup"><span data-stu-id="c4102-104">A value of **0** indicates an infinite wait time.</span></span> <span data-ttu-id="c4102-105">Lecture seule.</span><span class="sxs-lookup"><span data-stu-id="c4102-105">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4102-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="c4102-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonTimeout As Int32  
```  
  
```csharp  
public Int32 DatabaseLogonTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="c4102-107">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="c4102-107">Property Values</span></span>  
 <span data-ttu-id="c4102-108">Objet entier signé 32 bits qui représente le nombre de secondes.</span><span class="sxs-lookup"><span data-stu-id="c4102-108">A 32-bit signed integer object that represents the number of seconds.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="c4102-109">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="c4102-109">Example Code</span></span>  
 [<span data-ttu-id="c4102-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c4102-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="c4102-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c4102-111">Requirements</span></span>  
 <span data-ttu-id="c4102-112">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4102-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4102-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c4102-113">See Also</span></span>  
 [<span data-ttu-id="c4102-114">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="c4102-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
