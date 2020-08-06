---
title: Domaines d’application et sécurité de l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- application domains [CLR integration]
ms.assetid: 54ee904e-e21a-4ee7-b4ad-a6f6f71bd473
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 85d6e66b1d51cc9d7c5829b8e83c510bea750e2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602998"
---
# <a name="application-domains-and-clr-integration-security"></a><span data-ttu-id="386f9-102">Domaines d'application et sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="386f9-102">Application Domains and CLR Integration Security</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="386f9-103">charge des assemblys qui appartiennent au même propriétaire dans le même domaine d'application.</span><span class="sxs-lookup"><span data-stu-id="386f9-103">loads assemblies belonging to the same owner in the same application domain.</span></span> <span data-ttu-id="386f9-104">En raison d'un jeu d'assemblys s'exécutant dans le même domaine d'application, les assemblys sont capables de se découvrir les uns les autres au moment de l'exécution à l'aide d'interfaces de programmation d'applications de réflexion du .NET Framework ou par d'autres moyens, et ils sont capables d'y faire des appels en mode de liaison tardive.</span><span class="sxs-lookup"><span data-stu-id="386f9-104">By virtue of a set of assemblies running in the same application domain, assemblies are able to discover each other at execution time using the.NET Framework reflection application programming interfaces or other means, and can call into them in late-bound fashion.</span></span> <span data-ttu-id="386f9-105">De tels appels se produisant sur des assemblys qui appartiennent au même propriétaire, aucune autorisation [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] n'est vérifiée pour ces appels.</span><span class="sxs-lookup"><span data-stu-id="386f9-105">Because such calls are occurring against assemblies belonging to the same owner, there are no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permissions checked for these calls.</span></span> <span data-ttu-id="386f9-106">Le schéma de positionnement des assemblys dans les domaines d'application est principalement conçu pour répondre à des objectifs en matière d'évolutivité, de sécurité et d'isolation. Il est susceptible d'être modifié dans des versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="386f9-106">The placement scheme of assemblies in application domains is designed primarily to achieve scalability, security, and isolation goals, and can potentially change in future releases.</span></span> <span data-ttu-id="386f9-107">Pour cette raison, il est possible que la recherche d'assemblys dans le même domaine d'application par le biais de mécanismes à liaison tardive s'avère infructueuse.</span><span class="sxs-lookup"><span data-stu-id="386f9-107">Hence, you should not rely on finding assemblies in the same application domain through late-bound mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="386f9-108">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="386f9-108">See Also</span></span>  
 [<span data-ttu-id="386f9-109">Sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="386f9-109">CLR Integration Security</span></span>](../../relational-databases/clr-integration/security/clr-integration-security.md)  
  
  
