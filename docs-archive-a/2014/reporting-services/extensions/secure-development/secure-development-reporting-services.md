---
title: Développement sécurisé (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- development security [Reporting Services]
- security [Reporting Services], development
- security [Reporting Services], strategies
ms.assetid: 12161a6c-b93b-4312-9d27-0c922561eb9b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7ba284b9013c5da6b03cce06ec72deccb045cfad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615021"
---
# <a name="secure-development-reporting-services"></a><span data-ttu-id="5f919-102">Développement sécurisé (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="5f919-102">Secure Development (Reporting Services)</span></span>
  <span data-ttu-id="5f919-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] constitue un système de sécurité fiable qui peut exécuter du code dans des contextes de sécurité soumis à de fortes contraintes et définis par l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="5f919-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a robust security system that can run code in tightly constrained, administrator-defined security contexts.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="5f919-104">utilise le système de sécurité du [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], appelé sécurité d'accès du code (ou sécurité basée sur les preuves).</span><span class="sxs-lookup"><span data-stu-id="5f919-104">uses the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] security system, known as code access security (or evidence-based security).</span></span> <span data-ttu-id="5f919-105">Sous la sécurité d'accès du code, un utilisateur doit être approuvé pour pouvoir accéder à une ressource, mais si le code qu'il exécute n'est pas approuvé, l'accès à la ressource lui est refusé.</span><span class="sxs-lookup"><span data-stu-id="5f919-105">Under code access security, a user may be trusted to access a resource, but if the code the user executes is not trusted, access to the resource will be denied.</span></span>  
  
 <span data-ttu-id="5f919-106">La sécurité basée sur le code, par opposition à celle basée sur des utilisateurs spécifiques, permet de spécifier la sécurité pour les assemblys personnalisés ou les extensions de données, de remise, de rendu et de sécurité que vous développez pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f919-106">Security based on code, as opposed to specific users, permits security to be expressed for custom assemblies or data, delivery, rendering, and security extensions that you develop for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5f919-107">Votre code d'extension peut être exécuté par un nombre illimité d'utilisateurs de [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], tous inconnus au moment du développement.</span><span class="sxs-lookup"><span data-stu-id="5f919-107">Your extension code may be executed by any number of [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] users, all of whom are unknown at development time.</span></span> <span data-ttu-id="5f919-108">Les assemblys personnalisés ou extensions que vous développez nécessitent des stratégies de sécurité spécifiques dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f919-108">The custom assemblies or extensions that you develop require specific security policies in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="5f919-109">Ces stratégies de sécurité sont représentées en tant que types dans le [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f919-109">These security policies are represented as types in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="5f919-110">Pour plus d'informations sur la sécurité d'accès du code, consultez la rubrique « Sécurité d'accès du code » dans la documentation du [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f919-110">For a more information about code access security, see "Code Access Security" in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f919-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5f919-111">In This Section</span></span>  
 [<span data-ttu-id="5f919-112">Sécurité d'accès du code dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5f919-112">Code Access Security in Reporting Services</span></span>](code-access-security-in-reporting-services.md)  
 <span data-ttu-id="5f919-113">Présente la configuration des stratégies et de la sécurité d'accès du code pour les extensions et assemblys personnalisés dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5f919-113">Introduces code access security and policy configuration for custom assemblies and extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="5f919-114">Présentation des stratégies de sécurité</span><span class="sxs-lookup"><span data-stu-id="5f919-114">Understanding Security Policies</span></span>](understanding-security-policies.md)  
 <span data-ttu-id="5f919-115">Décrit les différents types d'assemblys dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] et explique comment la sécurité d'accès du code affecte les autorisations de code.</span><span class="sxs-lookup"><span data-stu-id="5f919-115">Describes the various assembly types in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] and how code access security affects code permissions.</span></span>  
  
 [<span data-ttu-id="5f919-116">Utilisation des fichiers de stratégie de sécurité Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5f919-116">Using Reporting Services Security Policy Files</span></span>](using-reporting-services-security-policy-files.md)  
 <span data-ttu-id="5f919-117">Décrit les différents composants [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] et les fichiers de configuration de stratégies correspondants.</span><span class="sxs-lookup"><span data-stu-id="5f919-117">Describes the different [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] components and the corresponding policy configuration files.</span></span>  
  
  
