---
title: open objects (option de configuration de serveur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- open objects option
ms.assetid: c8424d3c-86ba-4cc5-bf0c-be4ce44bdd04
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6d22a3d6dd358afe9cf921376664c2d25705a6a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696035"
---
# <a name="open-objects-server-configuration-option"></a>open objects (option de configuration de serveur)
  Cette option est toujours présente dans **sp_configure**, même si ses fonctionnalités ont été désactivées dans [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. (La valeur n'a pas d'effet.) Dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], le nombre d'objets de base de données ouverts est géré dynamiquement et n'est limité que par la mémoire disponible. L’option **open objects** est disponible dans **sp_configure** pour assurer une compatibilité descendante avec les scripts existants.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)]  
  
## <a name="see-also"></a>Voir aussi  
 [Options de configuration de serveur &#40;SQL Server&#41;](server-configuration-options-sql-server.md)  
  
  
