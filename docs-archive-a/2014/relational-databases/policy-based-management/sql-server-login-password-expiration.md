---
title: Expiration du mot de passe de connexion SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 7e3bf9da-a436-433d-847a-47c30428cad3
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 678e8e9c6b567014bdd49e89d043165bc48d168a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600838"
---
# <a name="sql-server-login-password-expiration"></a><span data-ttu-id="988bb-102">Expiration du mot de passe de connexion SQL Server</span><span class="sxs-lookup"><span data-stu-id="988bb-102">SQL Server Login Password Expiration</span></span>
  <span data-ttu-id="988bb-103">Cette règle vérifie si l'option Expiration du mot de passe est activée pour chaque connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="988bb-103">This rule checks whether "Password expiration" of each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login is enabled.</span></span> <span data-ttu-id="988bb-104">Si l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] est activée et si la version du système d'exploitation est antérieure à [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], un pirate peut régulièrement exploiter un mot de passe de connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connu.</span><span class="sxs-lookup"><span data-stu-id="988bb-104">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is enabled and if the operating system version is earlier than [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)], an attacker could repeatedly exploit a known [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login password.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="988bb-105">Meilleures pratiques recommandées</span><span class="sxs-lookup"><span data-stu-id="988bb-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="988bb-106">Nous vous recommandons de mettre à niveau le système d'exploitation vers [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="988bb-106">We recommend that you upgrade the operating system to [!INCLUDE[winxpsvr](../../includes/winxpsvr-md.md)].</span></span>  
  
 <span data-ttu-id="988bb-107">Si l'authentification [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est pas requise dans votre environnement, utilisez l'authentification Windows.</span><span class="sxs-lookup"><span data-stu-id="988bb-107">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication is not required in your environment, use Windows Authentication.</span></span> <span data-ttu-id="988bb-108">Pour plus d’informations, consultez [Choisir un mode d’authentification](../security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="988bb-108">For more information, see [Choose an Authentication Mode](../security/choose-an-authentication-mode.md).</span></span>  
  
 <span data-ttu-id="988bb-109">Activez l'option Expiration du mot de passe pour toutes les connexions [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="988bb-109">Enable "Password expiration" for all the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] logins.</span></span> <span data-ttu-id="988bb-110">Utilisez [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) pour configurer la stratégie de mot de passe pour la connexion [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="988bb-110">Use [ALTER LOGIN](/sql/t-sql/statements/alter-login-transact-sql) to configure the password policy for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="988bb-111">Pour plus d'informations</span><span class="sxs-lookup"><span data-stu-id="988bb-111">For More Information</span></span>  
 [<span data-ttu-id="988bb-112">Stratégie de mot de passe</span><span class="sxs-lookup"><span data-stu-id="988bb-112">Password Policy</span></span>](../security/password-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="988bb-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="988bb-113">See Also</span></span>  
 [<span data-ttu-id="988bb-114">Contrôler et appliquer les bonnes pratiques à l’aide de la gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="988bb-114">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
