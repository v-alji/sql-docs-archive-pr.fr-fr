---
title: Sécurité de l’intégration du CLR | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- security [CLR integration]
- authorization [CLR integration]
- common language runtime [SQL Server], security
- database objects [CLR integration], security
ms.assetid: 05d7a471-c5d5-4730-b903-e4edc8157bb4
author: rothja
ms.author: jroth
ms.openlocfilehash: 0d99d32a061d8fe78a8ac3642a503cceb45f3809
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604033"
---
# <a name="clr-integration-security"></a><span data-ttu-id="5dd04-102">Sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-102">CLR Integration Security</span></span>
  <span data-ttu-id="5dd04-103">Le modèle de sécurité du [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] Common Language Runtime (CLR) gère et sécurise l’accès entre les différents types d’objets CLR et non CLR qui s’exécutent dans [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] une instruction ou un autre objet CLR en cours d’exécution sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="5dd04-103">The security model of the [!INCLUDE[ssNoVersion](../../../includes/dnprdnshort-md.md)] common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within [!INCLUDE[ssNoVersion](../../../includes/tsql-md.md)] statement or another CLR object running in the server.</span></span> <span data-ttu-id="5dd04-104">Les appels entre objets portent le nom de liens.</span><span class="sxs-lookup"><span data-stu-id="5dd04-104">The calls between objects are referred to as links.</span></span> <span data-ttu-id="5dd04-105">Les types de vérifications de sécurité effectués sur ces objets dépendent des types de liens impliqués.</span><span class="sxs-lookup"><span data-stu-id="5dd04-105">The types of security checks performed on these objects depend on the types of links involved.</span></span>  
  
 <span data-ttu-id="5dd04-106">Le modèle de sécurité d'intégration du CLR a les objectifs suivants :</span><span class="sxs-lookup"><span data-stu-id="5dd04-106">The CLR integration security model has the following goals:</span></span>  
  
-   <span data-ttu-id="5dd04-107">Par défaut, l’exécution du code utilisateur managé sur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="5dd04-107">By default, running managed user code on [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5dd04-108">L'exécution d'opérations susceptibles de compromettre la robustesse de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] doit être protégée par des autorisations de haut niveau appropriées.</span><span class="sxs-lookup"><span data-stu-id="5dd04-108">Performing operations that potentially compromise the robustness of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] should be protected by appropriate high-level permissions.</span></span>  
  
-   <span data-ttu-id="5dd04-109">Le code utilisateur managé ne doit pas accéder de façon non autorisée aux données utilisateur ou autre code utilisateur dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="5dd04-109">Managed user code should not gain unauthorized access to user data or other user code in the database.</span></span> <span data-ttu-id="5dd04-110">Le code défini par l'utilisateur doit s'exécuter sous le contexte de sécurité de la session utilisateur qui l'a appelé et avec les privilèges corrects pour ce contexte de sécurité.</span><span class="sxs-lookup"><span data-stu-id="5dd04-110">User-defined code should run under the security context of the user-session that invoked it, and with the correct privileges for that security context.</span></span>  
  
-   <span data-ttu-id="5dd04-111">Il doit y avoir des contrôles pour restreindre le code utilisateur à accéder à toute ressource située à l'extérieur du serveur, de sorte qu'il soit utilisé strictement pour l'accès aux données et le calcul locaux.</span><span class="sxs-lookup"><span data-stu-id="5dd04-111">There should be controls for restricting user code from accessing any resources outside the server, using it strictly for local data access and computation.</span></span>  
  
-   <span data-ttu-id="5dd04-112">Le code défini par l'utilisateur ne doit pas être en mesure d'accéder de façon non autorisée aux ressources système du fait de son exécution dans le processus [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dd04-112">User-defined code should not be able to gain unauthorized access to system resources by virtue of running in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="5dd04-113">avec le modèle de sécurité basé sur l’accès du code du CLR.</span><span class="sxs-lookup"><span data-stu-id="5dd04-113">with the code access-based security model of the CLR.</span></span> <span data-ttu-id="5dd04-114">Quelques-uns des avantages offerts par cette approche combinée de la sécurité sont discutés dans cette section.</span><span class="sxs-lookup"><span data-stu-id="5dd04-114">Some of the advantages of this combined approach to security are discussed in this section.</span></span>  
  
 <span data-ttu-id="5dd04-115">Le tableau suivant décrit les rubriques de cette section.</span><span class="sxs-lookup"><span data-stu-id="5dd04-115">The following table lists the topics in this section.</span></span>  
  
 [<span data-ttu-id="5dd04-116">Sécurité d'accès du code de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-116">CLR Integration Code Access Security</span></span>](clr-integration-code-access-security.md)  
 <span data-ttu-id="5dd04-117">Discute du modèle de sécurité d'accès du code pour le code managé.</span><span class="sxs-lookup"><span data-stu-id="5dd04-117">Discusses the code access security (CAS) model for managed code.</span></span>  
  
 [<span data-ttu-id="5dd04-118">Attributs de protection de l'hôte et programmation de l'intégration CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-118">Host Protection Attributes and CLR Integration Programming</span></span>](../../clr-integration-security-host-protection-attributes/host-protection-attributes-and-clr-integration-programming.md)  
 <span data-ttu-id="5dd04-119">Fournit des informations à propos des valeurs d'attributs de protection de l'hôte (HPA) interdites dans les assemblys SAFE et EXTERNAL_ACCESS.</span><span class="sxs-lookup"><span data-stu-id="5dd04-119">Provides information about the host protection attribute (HPA) values that are disallowed in SAFE and EXTERNAL_ACCESS assemblies.</span></span>  
  
 [<span data-ttu-id="5dd04-120">Liens dans la sécurité d'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-120">Links in CLR Integration Security</span></span>](../../../database-engine/dev-guide/links-in-clr-integration-security.md)  
 <span data-ttu-id="5dd04-121">Décrit comment les segments de code utilisateur peuvent s'appeler dans [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dd04-121">Describes how pieces of user-code can call each other in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="5dd04-122">Emprunt d'identité et sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-122">Impersonation and CLR Integration Security</span></span>](../../../database-engine/dev-guide/impersonation-and-clr-integration-security.md)  
 <span data-ttu-id="5dd04-123">Discute la manière dont le code managé accède aux ressources externes à l'aide de l'emprunt d'identité.</span><span class="sxs-lookup"><span data-stu-id="5dd04-123">Discusses how managed code accesses external resources using impersonation.</span></span>  
  
 [<span data-ttu-id="5dd04-124">Autorisation d'appelants partiellement approuvés</span><span class="sxs-lookup"><span data-stu-id="5dd04-124">Allowing Partially Trusted Callers</span></span>](../../../database-engine/dev-guide/allowing-partially-trusted-callers.md)  
 <span data-ttu-id="5dd04-125">Discute des problèmes qui surviennent lorsqu'une méthode managée appelle une méthode dans une classe contenue dans un autre assembly.</span><span class="sxs-lookup"><span data-stu-id="5dd04-125">Discusses issues that arise when a managed method invokes a method in a class contained in another assembly.</span></span>  
  
 [<span data-ttu-id="5dd04-126">Domaines d'application et sécurité de l'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-126">Application Domains and CLR Integration Security</span></span>](../../../database-engine/dev-guide/application-domains-and-clr-integration-security.md)  
 <span data-ttu-id="5dd04-127">Décrit la façon dont les assemblys sont chargés dans les domaines d'application.</span><span class="sxs-lookup"><span data-stu-id="5dd04-127">Describes how assemblies are loaded into application domains.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dd04-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5dd04-128">See Also</span></span>  
 [<span data-ttu-id="5dd04-129">Gestion des assemblys d'intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="5dd04-129">Managing CLR Integration Assemblies</span></span>](../assemblies/managing-clr-integration-assemblies.md)  
  
  
