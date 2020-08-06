---
title: DatabaseQueryTimeout, propriété (WMI MSReportServer_ConfigurationSetting) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseQueryTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseQueryTimeout property
ms.assetid: 96faed97-9799-4bbf-a66f-fdd532d3eace
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e92e3e0f6752ea99fe89c962ebe96e343c0195b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706015"
---
# <a name="databasequerytimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="69a26-102">Propriété DatabaseQueryTimeout (WMI MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="69a26-102">DatabaseQueryTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="69a26-103">Spécifie le nombre de secondes qui doivent s'écouler avant que le serveur de rapports suppose que la commande a échoué ou a pris trop de temps pour s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="69a26-103">Specifies the number of seconds that must elapse before the report server assumes the command failed or took too much time to perform.</span></span> <span data-ttu-id="69a26-104">Le serveur de rapports établit la valeur de minutage de la requête par rapport au catalogue SQL Server et non par rapport à une source de données du rapport.</span><span class="sxs-lookup"><span data-stu-id="69a26-104">The report server is timing the querying against the SQL catalog, not a data source for the report.</span></span> <span data-ttu-id="69a26-105">En lecture/écriture.</span><span class="sxs-lookup"><span data-stu-id="69a26-105">Read/write.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a26-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="69a26-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseQueryTimeout As UInt32  
```  
  
```csharp  
public UInt32 DatabaseQueryTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="69a26-107">Valeurs de la propriété</span><span class="sxs-lookup"><span data-stu-id="69a26-107">Property Values</span></span>  
 <span data-ttu-id="69a26-108">Objet `integer` non signé 32 bits qui représente le nombre de secondes pendant lesquelles la requête est autorisée à s'exécuter.</span><span class="sxs-lookup"><span data-stu-id="69a26-108">A 32-bit unsigned `integer` object that represents the number of seconds that the query is allowed to run.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="69a26-109">Exemple de code</span><span class="sxs-lookup"><span data-stu-id="69a26-109">Example Code</span></span>  
 [<span data-ttu-id="69a26-110">Classe MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="69a26-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="69a26-111">Spécifications</span><span class="sxs-lookup"><span data-stu-id="69a26-111">Requirements</span></span>  
 <span data-ttu-id="69a26-112">**Espace de noms :** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69a26-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a26-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69a26-113">See Also</span></span>  
 [<span data-ttu-id="69a26-114">Membres MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="69a26-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
