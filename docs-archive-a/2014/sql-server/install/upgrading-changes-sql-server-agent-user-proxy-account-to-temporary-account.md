---
title: La mise à niveau va remplacer le SQL Server Agent compte proxy de l’utilisateur par le UpgradedProxyAccount temporaire | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- log shipping [SQL Server Agent]
ms.assetid: cd2d08c3-4e56-4034-8b68-0c78df8b5471
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2bca80580a50f2acebed1b6fbea2dec1f6458dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600474"
---
# <a name="upgrading-will-change-the-sql-server-agent-user-proxy-account-to-the-temporary-upgradedproxyaccount"></a><span data-ttu-id="cdf7f-102">La mise à niveau entraînera la modification du compte proxy utilisateur de l'Agent SQL Server en UpgradedProxyAccount temporaire</span><span class="sxs-lookup"><span data-stu-id="cdf7f-102">Upgrading will change the SQL Server Agent User Proxy Account to the temporary UpgradedProxyAccount</span></span>
  <span data-ttu-id="cdf7f-103">Les plans de maintenance de base de données dans lesquels la copie des journaux de transaction est activée ne seront pas activés après la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="cdf7f-103">Database maintenance plans that have log shipping enabled will not be enabled after upgrade.</span></span>  
  
## <a name="component"></a><span data-ttu-id="cdf7f-104">Composant</span><span class="sxs-lookup"><span data-stu-id="cdf7f-104">Component</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cdf7f-105">Agent</span><span class="sxs-lookup"><span data-stu-id="cdf7f-105">Agent</span></span>  
  
## <a name="description"></a><span data-ttu-id="cdf7f-106">Description</span><span class="sxs-lookup"><span data-stu-id="cdf7f-106">Description</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="cdf7f-107">fournit un nouvel ensemble de fonctions de copie des journaux de transaction qui ne sont pas directement compatibles avec les plans de maintenance de base de données.</span><span class="sxs-lookup"><span data-stu-id="cdf7f-107">provides a new set of log shipping functions that are not directly compatible with database maintenance plans.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="cdf7f-108">Action corrective</span><span class="sxs-lookup"><span data-stu-id="cdf7f-108">Corrective Action</span></span>  
 <span data-ttu-id="cdf7f-109">Les utilisateurs [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] dont les plans de maintenance de base de données contiennent des fonctions de copie des journaux de transaction doivent configurer la copie des journaux de transaction en utilisant les nouvelles fonctions.</span><span class="sxs-lookup"><span data-stu-id="cdf7f-109">[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)] users that have database maintenance plans that contain log shipping functions should configure log shipping by using the new functions.</span></span> <span data-ttu-id="cdf7f-110">Pour plus d'informations, recherchez "copie des journaux de transaction" dans la documentation en ligne de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdf7f-110">For more information, search on "log shipping" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdf7f-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdf7f-111">See Also</span></span>  
 <span data-ttu-id="cdf7f-112">[SQL Server Agent catégorie de travaux d’envoi de journaux provoque l’échec de la mise à niveau](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span><span class="sxs-lookup"><span data-stu-id="cdf7f-112">[SQL Server Agent log shipping job category causes upgrade to fail](../../../2014/sql-server/install/sql-server-agent-log-shipping-job-category-causes-upgrade-to-fail.md) </span></span>  
 [<span data-ttu-id="cdf7f-113">La copie des journaux de transaction ne s'exécutera pas après la mise à niveau</span><span class="sxs-lookup"><span data-stu-id="cdf7f-113">Log shipping will not run after upgrading</span></span>](../../../2014/sql-server/install/log-shipping-will-not-run-after-upgrading.md)  
  
  
