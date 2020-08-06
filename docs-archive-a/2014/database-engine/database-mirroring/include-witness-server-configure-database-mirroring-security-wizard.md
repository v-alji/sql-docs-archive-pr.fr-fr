---
title: Inclure un serveur témoin (Configurer l’Assistant Sécurité de mise en miroir de bases de données) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.configdbmsecurwiz.inclwitness.f1
ms.assetid: f04b38a4-f4e2-4d4c-bdac-7cc70e5a5684
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 314d2205463436e2182b8d1a4cc0cc972213bd5e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601648"
---
# <a name="include-witness-server-configure-database-mirroring-security-wizard"></a><span data-ttu-id="9a4b3-102">Inclure un serveur témoin (Configurer l'Assistant Sécurité de mise en miroir de bases de données)</span><span class="sxs-lookup"><span data-stu-id="9a4b3-102">Include Witness Server (Configure Database Mirroring Security Wizard)</span></span>
  <span data-ttu-id="9a4b3-103">Utilisez cette page pour indiquer si vous voulez inclure un serveur témoin dans cette configuration de sécurité pour la mise en miroir de bases de données.</span><span class="sxs-lookup"><span data-stu-id="9a4b3-103">Use this page to specify whether you want to include a witness server in this security configuration for database mirroring.</span></span>  
  
 <span data-ttu-id="9a4b3-104">**Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**</span><span class="sxs-lookup"><span data-stu-id="9a4b3-104">**To configure database mirroring by using SQL Server Management Studio**</span></span>  
  
-   [<span data-ttu-id="9a4b3-105">Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9a4b3-105">Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;</span></span>](establish-database-mirroring-session-windows-authentication.md)  
  
-   [<span data-ttu-id="9a4b3-106">Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="9a4b3-106">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a><span data-ttu-id="9a4b3-107">Options</span><span class="sxs-lookup"><span data-stu-id="9a4b3-107">Options</span></span>  
 <span data-ttu-id="9a4b3-108">**Oui**</span><span class="sxs-lookup"><span data-stu-id="9a4b3-108">**Yes**</span></span>  
 <span data-ttu-id="9a4b3-109">Cliquez sur Oui pour inclure une instance de serveur témoin dans la configuration de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9a4b3-109">Click to include a witness server instance in the security configuration.</span></span> <span data-ttu-id="9a4b3-110">Ce serveur témoin est nécessaire en mode haute sécurité avec basculement automatique, ce qui permet la prise en charge du basculement automatique vers l'instance de serveur miroir en cas de défaillance de l'instance de serveur principal.</span><span class="sxs-lookup"><span data-stu-id="9a4b3-110">The witness is necessary for high-safety mode with automatic failover, which supports automatic failover to the mirror server instance if the principal server instance fails.</span></span>  
  
 <span data-ttu-id="9a4b3-111">**Non**</span><span class="sxs-lookup"><span data-stu-id="9a4b3-111">**No**</span></span>  
 <span data-ttu-id="9a4b3-112">Cliquez sur Non pour ne pas inclure de serveur témoin dans la configuration de sécurité.</span><span class="sxs-lookup"><span data-stu-id="9a4b3-112">Click to configure security without a witness.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a4b3-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9a4b3-113">See Also</span></span>  
 <span data-ttu-id="9a4b3-114">[Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="9a4b3-114">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="9a4b3-115">[Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9a4b3-115">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="9a4b3-116">Témoin de mise en miroir de base de données</span><span class="sxs-lookup"><span data-stu-id="9a4b3-116">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
