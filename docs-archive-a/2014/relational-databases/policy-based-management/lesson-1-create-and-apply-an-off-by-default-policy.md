---
title: 'Leçon 1 : Créer et appliquer une stratégie Désactivé par défaut | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: d31367db-b7db-44c4-8df2-f1240474cf78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a76df1a72b93d09c5c1c199cb0246dbb51c9cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601416"
---
# <a name="lesson-1-create-and-apply-an-off-by-default-policy"></a><span data-ttu-id="9c5d6-102">Leçon 1 : Créer et appliquer une stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="9c5d6-102">Lesson 1: Create and Apply an Off By Default Policy</span></span>
  <span data-ttu-id="9c5d6-103">À l'aide des stratégies de la Gestion basée sur des stratégies, vous pouvez administrer une ou plusieurs instances de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], un ou plusieurs objets d'instance, une ou plusieurs instances de serveur, une ou plusieurs bases de données, de même qu'un ou plusieurs objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="9c5d6-103">Using Policy-Based Management policies, you can administer one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], one or more instance objects, server instances, one or more databases, or one or more database objects.</span></span> <span data-ttu-id="9c5d6-104">En tant qu'administrateur de base de données, vous souhaitez vous assurer que la Messagerie de base de données n'est pas activée sur certains serveurs.</span><span class="sxs-lookup"><span data-stu-id="9c5d6-104">As the database administrator, you want to ensure that certain servers do not have Database Mail enabled.</span></span> <span data-ttu-id="9c5d6-105">Dans cette leçon, vous allez créer une condition et une stratégie qui définissent cette option de serveur.</span><span class="sxs-lookup"><span data-stu-id="9c5d6-105">In this lesson, you will create a condition and a policy that sets that server option.</span></span> <span data-ttu-id="9c5d6-106">Vous allez tester le serveur pour vérifier s'il est conforme à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="9c5d6-106">You will test the server to see whether it complies with the policy.</span></span> <span data-ttu-id="9c5d6-107">Ensuite, vous utiliserez la stratégie pour reconfigurer le serveur afin de le rendre conforme.</span><span class="sxs-lookup"><span data-stu-id="9c5d6-107">Then, you will use the policy to reconfigure the server to bring the server into compliance.</span></span>  
  
 <span data-ttu-id="9c5d6-108">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c5d6-108">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="9c5d6-109">Créer la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="9c5d6-109">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
-   [<span data-ttu-id="9c5d6-110">Configurer un serveur pour exécuter la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="9c5d6-110">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="9c5d6-111">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="9c5d6-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="9c5d6-112">Créer la stratégie Désactivé par défaut</span><span class="sxs-lookup"><span data-stu-id="9c5d6-112">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="9c5d6-113">Leçon suivante</span><span class="sxs-lookup"><span data-stu-id="9c5d6-113">Next Lesson</span></span>  
 [<span data-ttu-id="9c5d6-114">Leçon 2 : Créer et appliquer une stratégie de normes d’affectation de noms</span><span class="sxs-lookup"><span data-stu-id="9c5d6-114">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
