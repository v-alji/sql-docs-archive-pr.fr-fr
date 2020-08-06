---
title: Autorisations du serveur public | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 9a276caa-ea38-473d-92bc-26302bfcf660
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7913c4715f47b8105b72b1c817dbe77e52d40539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708216"
---
# <a name="server-public-permissions"></a><span data-ttu-id="1b67b-102">Autorisations du serveur public</span><span class="sxs-lookup"><span data-stu-id="1b67b-102">Server public Permissions</span></span>
  <span data-ttu-id="1b67b-103">Cette règle détermine si le rôle serveur public possède des autorisations de serveur.</span><span class="sxs-lookup"><span data-stu-id="1b67b-103">This rule determines whether the public server role has server permissions.</span></span> <span data-ttu-id="1b67b-104">Chaque nom de connexion créé sur le serveur est un membre du rôle serveur public.</span><span class="sxs-lookup"><span data-stu-id="1b67b-104">Every login that is created on the server is a member of the public server role.</span></span> <span data-ttu-id="1b67b-105">Si cette condition est remplie, chaque nom de connexion sur le serveur disposera d'autorisations de serveur.</span><span class="sxs-lookup"><span data-stu-id="1b67b-105">If this condition is met, every login on the server will have server permissions.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="1b67b-106">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="1b67b-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="1b67b-107">N'octroyez pas d'autorisations de serveur au rôle public du serveur.</span><span class="sxs-lookup"><span data-stu-id="1b67b-107">Do not grant server permissions to the server public role.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b67b-108">Une fois l’installation terminée, le rôle **public** dispose `CONNECT` de l’autorisation sur tous les points de terminaison, à l’exception de la **connexion administrateur dédiée**.</span><span class="sxs-lookup"><span data-stu-id="1b67b-108">After setup completes the **PUBLIC** role has `CONNECT` permission on all the endpoints except the **Dedicated Admin Connection**.</span></span> <span data-ttu-id="1b67b-109">Ce comportement est normal et ne doit normalement pas être modifié.</span><span class="sxs-lookup"><span data-stu-id="1b67b-109">This is normal and should not be normally changed.</span></span> <span data-ttu-id="1b67b-110">(L'accès est contrôlé par l'autorisation `CONNECT SQL` qui est automatiquement accordée lorsque de nouvelles connexions sont créées.)</span><span class="sxs-lookup"><span data-stu-id="1b67b-110">(Access is controlled by using the `CONNECT SQL` permission which is automatically granted when new logins are created.)</span></span>  
  
### <a name="for-more-information"></a><span data-ttu-id="1b67b-111">Informations supplémentaires</span><span class="sxs-lookup"><span data-stu-id="1b67b-111">For more information</span></span>  
 [<span data-ttu-id="1b67b-112">Sécurisation de SQL Server</span><span class="sxs-lookup"><span data-stu-id="1b67b-112">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
  
