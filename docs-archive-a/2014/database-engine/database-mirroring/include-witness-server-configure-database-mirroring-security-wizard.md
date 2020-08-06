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
# <a name="include-witness-server-configure-database-mirroring-security-wizard"></a>Inclure un serveur témoin (Configurer l'Assistant Sécurité de mise en miroir de bases de données)
  Utilisez cette page pour indiquer si vous voulez inclure un serveur témoin dans cette configuration de sécurité pour la mise en miroir de bases de données.  
  
 **Pour configurer la mise en miroir de bases de données à l'aide de SQL Server Management Studio**  
  
-   [Établir une session de mise en miroir de bases de données au moyen de l’authentification Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md)  
  
-   [Démarrer l’Assistant Configuration de la sécurité de mise en miroir de bases de données &#40;SQL Server Management Studio&#41;](start-the-configuring-database-mirroring-security-wizard.md)  
  
## <a name="options"></a>Options  
 **Oui**  
 Cliquez sur Oui pour inclure une instance de serveur témoin dans la configuration de sécurité. Ce serveur témoin est nécessaire en mode haute sécurité avec basculement automatique, ce qui permet la prise en charge du basculement automatique vers l'instance de serveur miroir en cas de défaillance de l'instance de serveur principal.  
  
 **Non**  
 Cliquez sur Non pour ne pas inclure de serveur témoin dans la configuration de sécurité.  
  
## <a name="see-also"></a>Voir aussi  
 [Propriétés de la base de données &#40;page Mise en miroir&#41;](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Mise en miroir de bases de données &#40;SQL Server&#41;](database-mirroring-sql-server.md)   
 [Témoin de mise en miroir de base de données](database-mirroring-witness.md)  
  
  
