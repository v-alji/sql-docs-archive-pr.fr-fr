---
title: Utilisation des langages WQL et de script avec le fournisseur WMI pour la gestion de la configuration | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- queries [WMI]
- scripts [WMI]
- query language [WMI]
- WMI Query Language [WMI]
- WQL [WMI]
- WMI Provider for Configuration Management, WQL
- WMI Provider for Configuration Management, scripts
ms.assetid: c1e64905-3c2b-4974-88f4-abf17cf7e289
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: d8c903cd0e993728865bce3371c349a2d0ba7485
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605290"
---
# <a name="using-wql-and-scripting-languages-with-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="ce350-102">Utilisation des langages WQL et de script avec le fournisseur WMI pour la gestion de configuration</span><span class="sxs-lookup"><span data-stu-id="ce350-102">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>
  <span data-ttu-id="ce350-103">Les applications de gestion accèdent aux services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et aux paramètres de réseau à l'aide des objets Fournisseur WMI (Windows Management Instrumentation) pour la gestion de configuration de deux manières :</span><span class="sxs-lookup"><span data-stu-id="ce350-103">Management applications access [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings using the Windows Management Instrumentation (WMI) Provider for Configuration Management objects in two ways:</span></span>  
  
-   <span data-ttu-id="ce350-104">à l'aide d'un outil d'édition ou de requête WQL, tel que WBEMTest.exe, pour interroger l'objet défini avec le langage WQL ;</span><span class="sxs-lookup"><span data-stu-id="ce350-104">Using a WQL editor or query tool, such as WBEMTest.exe to query the object set with the Windows Management Instrumentation Language (WQL).</span></span>  
  
-   <span data-ttu-id="ce350-105">à l'aide d'un langage de script, tel que VBScript.</span><span class="sxs-lookup"><span data-stu-id="ce350-105">Using a scripting language, such as VBScript.</span></span>  
  
 <span data-ttu-id="ce350-106">Les services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et les paramètres de réseau peuvent être gérés par programme également à l'aide des objets managés WMI dans SMO.</span><span class="sxs-lookup"><span data-stu-id="ce350-106">Alternatively, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings can be managed programmatically using the WMI managed objects in SMO.</span></span> <span data-ttu-id="ce350-107">Pour plus d’informations sur la programmation des objets gérés par WMI, consultez [gestion des services et des paramètres réseau à l’aide du fournisseur WMI](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="ce350-107">For more information about programming WMI managed objects, see [Managing Services and Network Settings by Using WMI Provider](../server-management-objects-smo/tasks/managing-services-and-network-settings-by-using-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="ce350-108">Le fournisseur WMI pour la gestion de configuration peut être accédé en utilisant le Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] et [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span><span class="sxs-lookup"><span data-stu-id="ce350-108">The WMI provider for Configuration Management can be accessed by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Management Console.</span></span> <span data-ttu-id="ce350-109">Pour plus d’informations sur l’accès au fournisseur WMI à partir d’une interface utilisateur, consultez [rubriques de procédures relatives à la gestion des Services &#40;Gestionnaire de configuration SQL Server&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="ce350-109">For more information about accessing the WMI provider from a user interface, see [Managing Services How-to Topics &#40;SQL Server Configuration Manager&#41;](../../database-engine/managing-services-how-to-topics-sql-server-configuration-manager.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce350-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ce350-110">See Also</span></span>  
 <span data-ttu-id="ce350-111">[Accéder au fournisseur WMI pour la gestion de la configuration à l’aide de WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span><span class="sxs-lookup"><span data-stu-id="ce350-111">[Access WMI Provider for Configuration Management using WQL](access-wmi-provider-for-configuration-management-using-wql.md) </span></span>  
 [<span data-ttu-id="ce350-112">Modifier les propriétés avancées du service SQL Server à l'aide de VBScript</span><span class="sxs-lookup"><span data-stu-id="ce350-112">Modify SQL Server Service Advanced Properties using VBScript</span></span>](access-wmi-provider-for-configuration-management-using-vbscript.md)  
  
  
