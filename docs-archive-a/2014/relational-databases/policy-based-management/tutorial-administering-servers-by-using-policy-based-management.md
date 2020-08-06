---
title: 'Didacticiel : Administration de serveurs à l’aide de la gestion basée sur des stratégies | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: 7de96e7b-9fb8-4cc8-8d85-61345d68a1e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b707a5ecd362c6b3b54e853f89d79e25a9e1428
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603444"
---
# <a name="tutorial-administering-servers-by-using-policy-based-management"></a><span data-ttu-id="c1a8c-102">Tutoriel : Administration de serveurs à l’aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="c1a8c-102">Tutorial: Administering Servers by Using Policy-Based Management</span></span>
  <span data-ttu-id="c1a8c-103">Bienvenue au didacticiel Administration de serveurs à l'aide de stratégies de la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-103">Welcome to the Administering Servers by Using Policy-Based Management Policies tutorial.</span></span> <span data-ttu-id="c1a8c-104">Ce didacticiel est destiné aux utilisateurs familiarisés avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mais ne connaissant pas la Gestion basée sur des stratégies.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but new to the Policy-Based Management.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="c1a8c-105">Contenu du didacticiel</span><span class="sxs-lookup"><span data-stu-id="c1a8c-105">What You Will Learn</span></span>  
 <span data-ttu-id="c1a8c-106">Ce didacticiel crée une stratégie permettant d'administrer votre serveur et une stratégie qui s'appliquent à une base de données unique.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-106">This tutorial creates a policy to administer your server and a policy that applies to a single database.</span></span> <span data-ttu-id="c1a8c-107">Une stratégie est exécutée sur demande pour tester la conformité.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-107">One policy is run on demand to test for compliance.</span></span> <span data-ttu-id="c1a8c-108">L'autre stratégie applique la conformité future.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-108">The other policy enforces future compliance.</span></span>  
  
 <span data-ttu-id="c1a8c-109">Ce didacticiel est divisé en deux leçons :</span><span class="sxs-lookup"><span data-stu-id="c1a8c-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="c1a8c-110">Leçon 1 : Créer et appliquer une stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="c1a8c-110">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
 <span data-ttu-id="c1a8c-111">Cette leçon crée une stratégie qui spécifie que la Messagerie de base de données n'est pas activée sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-111">This lesson creates a policy that specifies that Database Mail is not enabled on the server.</span></span> <span data-ttu-id="c1a8c-112">Ensuite, il vérifie si votre serveur est conforme à la stratégie et configure le serveur en désactivant la Messagerie de base de données.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-112">Then, it checks to see whether your server complies with the policy, and configures the server by disabling Database Mail.</span></span>  
  
 [<span data-ttu-id="c1a8c-113">Leçon 2 : Créer et appliquer une stratégie de normes d’affectation de noms</span><span class="sxs-lookup"><span data-stu-id="c1a8c-113">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
 <span data-ttu-id="c1a8c-114">Cette leçon crée une stratégie qui définit et applique une norme d'affectation de noms pour les tables.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-114">This lesson creates a policy that defines and enforces a naming standard for tables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1a8c-115">Spécifications</span><span class="sxs-lookup"><span data-stu-id="c1a8c-115">Requirements</span></span>  
 <span data-ttu-id="c1a8c-116">Cette leçon requiert une connaissance élémentaire des bases de données et une compréhension des notions fondamentales de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1a8c-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="c1a8c-117">L'utilisation de ce didacticiel nécessite l'installation de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] sur votre système.</span><span class="sxs-lookup"><span data-stu-id="c1a8c-117">To use this tutorial, your system must have [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="c1a8c-118">Démarrer le didacticiel</span><span class="sxs-lookup"><span data-stu-id="c1a8c-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="c1a8c-119">Leçon 1 : Créer et appliquer une stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="c1a8c-119">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="c1a8c-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c1a8c-120">See Also</span></span>  
 [<span data-ttu-id="c1a8c-121">Administrer des serveurs à l'aide de la Gestion basée sur des stratégies</span><span class="sxs-lookup"><span data-stu-id="c1a8c-121">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
