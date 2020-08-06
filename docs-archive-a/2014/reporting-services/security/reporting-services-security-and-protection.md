---
title: Sécurité et protection de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0f8c7a4186c5236260fb27d8de107ce8c97bd363
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613818"
---
# <a name="reporting-services-security-and-protection"></a><span data-ttu-id="27fa5-102">Sécurité et protection de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="27fa5-102">Reporting Services Security and Protection</span></span>
  <span data-ttu-id="27fa5-103">Utilisez les informations de cette section pour en savoir plus sur les fonctionnalités de sécurité de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fa5-103">You can use information in this section to learn about the security features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="27fa5-104">Cette section décrit également les modèles d’autorisation et les fournisseurs d’authentification pris en charge dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27fa5-104">This section also explains the authorization models and authentication providers supported in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>  
  
## <a name="extended-protection-for-authentication"></a><span data-ttu-id="27fa5-105">Protection étendue de l'authentification</span><span class="sxs-lookup"><span data-stu-id="27fa5-105">Extended Protection for Authentication</span></span>  
 <span data-ttu-id="27fa5-106">À compter de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], la prise en charge de la protection étendue de l'authentification est disponible.</span><span class="sxs-lookup"><span data-stu-id="27fa5-106">Beginning with [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], support for Extended Protection for Authentication is available.</span></span> <span data-ttu-id="27fa5-107">La fonctionnalité [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] prend en charge l'utilisation de la liaison de canal et la liaison de service pour améliorer la protection de l'authentification.</span><span class="sxs-lookup"><span data-stu-id="27fa5-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] feature supports the use of channel binding and service binding to enhance protection of authentication.</span></span> <span data-ttu-id="27fa5-108">Les fonctionnalités [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] doivent être utilisées avec un système d'exploitation qui prend en charge la protection étendue.</span><span class="sxs-lookup"><span data-stu-id="27fa5-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] features need to be used with an operating system that supports Extended Protection.</span></span> <span data-ttu-id="27fa5-109">Pour plus d’informations, consultez [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="27fa5-109">For more information, see [Extended Protection for Authentication with Reporting Services](extended-protection-for-authentication-with-reporting-services.md).</span></span>  
  
## <a name="authentication-and-authorization"></a><span data-ttu-id="27fa5-110">Authentification et autorisation</span><span class="sxs-lookup"><span data-stu-id="27fa5-110">Authentication and Authorization</span></span>  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="27fa5-111">fournit différents types d’authentification pour que les utilisateurs et les applications clientes puissent être authentifiés par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="27fa5-111">provides different authentication types for users and client applications to authenticate with the report server.</span></span> <span data-ttu-id="27fa5-112">L'utilisation du bon type d'authentification pour votre serveur de rapports permet à votre organisation d'obtenir le niveau de sécurité approprié requis par votre organisation.</span><span class="sxs-lookup"><span data-stu-id="27fa5-112">Using the right authentication type for your report server enables your organization to achieve the appropriate level of security required by your organization.</span></span> <span data-ttu-id="27fa5-113">Pour plus d’informations, consultez [Authentification avec le serveur de rapports](authentication-with-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="27fa5-113">For more information, see [Authentication with the Report Server](authentication-with-the-report-server.md).</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="27fa5-114">utilise également les rôles et les autorisations pour contrôler l’accès au contenu dans le catalogue du serveur de rapports (en d’autres termes, qui peut accéder à quoi, et comment y accéder).</span><span class="sxs-lookup"><span data-stu-id="27fa5-114">also employs roles and permissions to control user access to content in the report server catalog (in other words, who can access what, and how s/he can access it).</span></span> <span data-ttu-id="27fa5-115">Pour plus d’informations, consultez [Rôles et autorisations &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="27fa5-115">For more information, see [Roles and Permissions &#40;Reporting Services&#41;](roles-and-permissions-reporting-services.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="27fa5-116">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="27fa5-116">Related Tasks</span></span>  
  
|<span data-ttu-id="27fa5-117">Descriptions de tâche</span><span class="sxs-lookup"><span data-stu-id="27fa5-117">Task Descriptions</span></span>|<span data-ttu-id="27fa5-118">Liens</span><span class="sxs-lookup"><span data-stu-id="27fa5-118">Links</span></span>|  
|-----------------------|-----------|  
|<span data-ttu-id="27fa5-119">Configurez le SSL (Secure Socket Layer) pour sécuriser les connexions clientes au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="27fa5-119">Configure the Secure Socket Layer (SSL) to secure client connections to the report server.</span></span>|[<span data-ttu-id="27fa5-120">Configurer des connexions SSL sur un serveur de rapports en mode natif</span><span class="sxs-lookup"><span data-stu-id="27fa5-120">Configure SSL Connections on a Native Mode Report Server</span></span>](configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
