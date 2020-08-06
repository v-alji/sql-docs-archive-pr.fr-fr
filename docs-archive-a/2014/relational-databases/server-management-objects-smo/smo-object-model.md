---
title: Modèle objet SMO | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- object models [SMO]
- SMO [SQL Server], object model
- SQL Server Management Objects, object model
ms.assetid: bd6e59b6-ca46-42c0-adb2-c9d64cf6e00b
author: stevestein
ms.author: sstein
ms.openlocfilehash: c973e381a6cc7de44a0072d012147271eaa609ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695540"
---
# <a name="smo-object-model"></a><span data-ttu-id="b9116-102">Modèle objet SMO</span><span class="sxs-lookup"><span data-stu-id="b9116-102">SMO Object Model</span></span>
  <span data-ttu-id="b9116-103">Le modèle objet SMO est composé d'une hiérarchie d'objets.</span><span class="sxs-lookup"><span data-stu-id="b9116-103">The SMO object model is made up of a hierarchy of objects.</span></span> <span data-ttu-id="b9116-104">L'objet <xref:Microsoft.SqlServer.Management.Smo.Server> est l'objet de niveau supérieur et tous les objets de classe d'instance résident sous l'objet <xref:Microsoft.SqlServer.Management.Smo.Server>.</span><span class="sxs-lookup"><span data-stu-id="b9116-104">The <xref:Microsoft.SqlServer.Management.Smo.Server> object is the top level object and all instance class objects reside under the <xref:Microsoft.SqlServer.Management.Smo.Server> object.</span></span>  
  
 <span data-ttu-id="b9116-105">La classe <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> est une classe de niveau supérieur avec une hiérarchie d'objets distincte.</span><span class="sxs-lookup"><span data-stu-id="b9116-105">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> class is a top level class with a separate object hierarchy.</span></span> <span data-ttu-id="b9116-106">L' <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objet représente les [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services et les paramètres réseau disponibles via le fournisseur WMI.</span><span class="sxs-lookup"><span data-stu-id="b9116-106">The <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> object represents [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and network settings available through the WMI Provider.</span></span>  
  
 <span data-ttu-id="b9116-107">Outre les objets <xref:Microsoft.SqlServer.Management.Smo.Server> et <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer>, il existe plusieurs classes utilitaires qui représentent des tâches ou des opérations, telles que <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup> ou <xref:Microsoft.SqlServer.Management.Smo.Restore></span><span class="sxs-lookup"><span data-stu-id="b9116-107">Besides the <xref:Microsoft.SqlServer.Management.Smo.Server> and <xref:Microsoft.SqlServer.Management.Smo.Wmi.ManagedComputer> objects, there are several utility classes that represent tasks or operations, such as <xref:Microsoft.SqlServer.Management.Smo.Transfer>, <xref:Microsoft.SqlServer.Management.Smo.Backup>, or <xref:Microsoft.SqlServer.Management.Smo.Restore></span></span>  
  
 <span data-ttu-id="b9116-108">Le modèle objet SMO est composé de plusieurs espaces de noms.</span><span class="sxs-lookup"><span data-stu-id="b9116-108">The SMO object model is made up of several namespaces.</span></span> <span data-ttu-id="b9116-109">Pour plus d’informations, consultez [Espaces de noms SMO](smo-object-model-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="b9116-109">For more information, see [SMO Namespaces](smo-object-model-namespaces.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9116-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b9116-110">See Also</span></span>  
 <span data-ttu-id="b9116-111">[Diagramme du modèle objet SMO](smo-object-model-diagram.md) </span><span class="sxs-lookup"><span data-stu-id="b9116-111">[SMO Object Model Diagram](smo-object-model-diagram.md) </span></span>  
 <span data-ttu-id="b9116-112">[Espaces de noms SMO](smo-object-model-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="b9116-112">[SMO Namespaces](smo-object-model-namespaces.md) </span></span>  
 [<span data-ttu-id="b9116-113">Fournisseur WMI pour les concepts de gestion de configuration</span><span class="sxs-lookup"><span data-stu-id="b9116-113">WMI Provider for Configuration Management Concepts</span></span>](../wmi-provider-configuration/wmi-provider-for-configuration-management.md)  
  
  
