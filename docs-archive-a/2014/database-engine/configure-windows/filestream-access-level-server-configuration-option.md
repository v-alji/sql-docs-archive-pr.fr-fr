---
title: filestream access level (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], access level
- filestream access level
ms.assetid: b88f6ff2-795e-4730-bfb8-dbc6a958f2ad
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dfa43b8e6e1762e87dd9c2abbdf7a583963e196e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614201"
---
# <a name="filestream-access-level-server-configuration-option"></a><span data-ttu-id="2e5bf-102">filestream access level (option de configuration de serveur)</span><span class="sxs-lookup"><span data-stu-id="2e5bf-102">filestream access level Server Configuration Option</span></span>
  <span data-ttu-id="2e5bf-103">Utilisez l'option de configuration filestream_access_level pour modifier le niveau d'accès FILESTREAM pour cette instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2e5bf-103">Use the filestream_access_level option to change the FILESTREAM access level for this instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2e5bf-104">Pour que cette option ait un effet, les paramètres d'administration Windows pour FILESTREAM doivent être activés.</span><span class="sxs-lookup"><span data-stu-id="2e5bf-104">Before this option has any effect, the Windows administration settings for FILESTREAM must be enabled.</span></span> <span data-ttu-id="2e5bf-105">Vous pouvez activer ces paramètres lorsque vous installez [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ou à l'aide du Gestionnaire de configuration [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5bf-105">You can enable these settings when you install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or by using [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
|<span data-ttu-id="2e5bf-106">Valeur</span><span class="sxs-lookup"><span data-stu-id="2e5bf-106">Value</span></span>|<span data-ttu-id="2e5bf-107">Définition</span><span class="sxs-lookup"><span data-stu-id="2e5bf-107">Definition</span></span>|  
|-----------|----------------|  
|<span data-ttu-id="2e5bf-108">0</span><span class="sxs-lookup"><span data-stu-id="2e5bf-108">0</span></span>|<span data-ttu-id="2e5bf-109">Désactive la prise en charge FILESTREAM pour cette instance.</span><span class="sxs-lookup"><span data-stu-id="2e5bf-109">Disables FILESTREAM support for this instance.</span></span>|  
|<span data-ttu-id="2e5bf-110">1</span><span class="sxs-lookup"><span data-stu-id="2e5bf-110">1</span></span>|<span data-ttu-id="2e5bf-111">Active FILESTREAM pour l'accès [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e5bf-111">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span>|  
|<span data-ttu-id="2e5bf-112">2</span><span class="sxs-lookup"><span data-stu-id="2e5bf-112">2</span></span>|<span data-ttu-id="2e5bf-113">Active FILESTREAM pour l'accès [!INCLUDE[tsql](../../includes/tsql-md.md)] et l'accès en continu Win32.</span><span class="sxs-lookup"><span data-stu-id="2e5bf-113">Enables FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] and Win32 streaming access.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e5bf-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e5bf-114">See Also</span></span>  
 <span data-ttu-id="2e5bf-115">[Configuration du moteur de base de données - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="2e5bf-115">[Database Engine Configuration - Filestream](../../sql-server/install/database-engine-configuration-filestream.md) </span></span>  
 [<span data-ttu-id="2e5bf-116">Activer et configurer FILESTREAM</span><span class="sxs-lookup"><span data-stu-id="2e5bf-116">Enable and Configure FILESTREAM</span></span>](../../relational-databases/blob/enable-and-configure-filestream.md)  
  
  
