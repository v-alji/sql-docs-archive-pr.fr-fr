---
title: Force du mot de passe de connexion SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: b0862c3a-926b-490c-a37f-382e50146a3e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5534748fbbf810539f2dcfc22239e4b987cf0f77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696716"
---
# <a name="sql-server-login-password-strength"></a><span data-ttu-id="ddece-102">Force du mot de passe de connexion SQL Server</span><span class="sxs-lookup"><span data-stu-id="ddece-102">SQL Server Login Password Strength</span></span>
  <span data-ttu-id="ddece-103">Cette règle vérifie si l'option Conserver la stratégie de mot de passe est activée pour chaque connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddece-103">This rule checks whether "Enforce password policy" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="ddece-104">Si l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est activée et si la version du système d'exploitation est antérieure à [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], un pirate peut régulièrement exploiter un mot de passe de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connu.</span><span class="sxs-lookup"><span data-stu-id="ddece-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ddece-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="ddece-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ddece-106">Nous vous recommandons de mettre à niveau le système d'exploitation vers [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ddece-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="ddece-107">Si l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas requise dans votre environnement, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="ddece-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="ddece-108">Activez l'option Conserver la stratégie de mot de passe pour toutes les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddece-108">Enable "Enforce password policy" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="ddece-109">Utilisez [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) pour configurer la stratégie de mot de passe pour la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ddece-109">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ddece-110">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="ddece-110">For More Information</span></span>  
 [<span data-ttu-id="ddece-111">Stratégie de mot de passe</span><span class="sxs-lookup"><span data-stu-id="ddece-111">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="ddece-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ddece-112">See Also</span></span>  
 [<span data-ttu-id="ddece-113">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="ddece-113">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
