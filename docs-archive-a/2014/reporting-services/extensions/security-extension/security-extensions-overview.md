---
title: Présentation des extensions de sécurité | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], extensions
ms.assetid: 24ccd795-6506-457c-93ac-6a9dd6bb9a46
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9cd6c2a1518b724a7faafecdb2926505694e9707
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610464"
---
# <a name="security-extensions-overview"></a><span data-ttu-id="2ddf2-102">Présentation des extensions de sécurité</span><span class="sxs-lookup"><span data-stu-id="2ddf2-102">Security Extensions Overview</span></span>
  <span data-ttu-id="2ddf2-103">Une extension de sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] permet l'authentification d'utilisateurs ou de groupes ainsi que l'attribution d'autorisations à ces derniers, en permettant à différents utilisateurs de se connecter à un serveur de rapports et d'effectuer différentes tâches ou opérations selon leur identité.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-103">A [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security extension enables the authentication and authorization of users or groups; that is, it enables different users to log on to a report server and, based on their identities, perform different tasks or operations.</span></span> <span data-ttu-id="2ddf2-104">Par défaut, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] utilise une extension d'authentification Windows, qui utilise des protocoles de compte Windows pour vérifier l'identité des utilisateurs qui prétendent avoir des comptes sur le système.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-104">By default, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] uses a Windows-based authentication extension, which uses Windows account protocols to verify the identities of users who claim to have accounts on the system.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="2ddf2-105">utilise un système de sécurité basé sur les rôles pour l'autorisation des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-105">uses a role-based security system to authorize users.</span></span> <span data-ttu-id="2ddf2-106">Le modèle de sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] basé sur les rôles est identiques aux modèles de sécurité basé sur les rôles d'autres technologies.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-106">The [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] role-based security model is similar to the role-based security models of other technologies.</span></span>

 <span data-ttu-id="2ddf2-107">Les extensions de sécurité étant basées sur une API ouverte et extensible, vous pouvez créer des extensions d'authentification et d'autorisation dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddf2-107">Because security extensions are based on an open and extensible API, you can create new authentication and authorization extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="2ddf2-108">L'exemple suivant illustre une implémentation d'extension de sécurité type qui utilise une authentification et une autorisation à base de formulaires :</span><span class="sxs-lookup"><span data-stu-id="2ddf2-108">The following is an example of a typical security extension implementation that uses Forms-based authentication and authorization:</span></span>

 <span data-ttu-id="2ddf2-109">![Processus d'extension de sécurité de Reporting Services](../../media/rosettasecurityextensionflow.gif "Processus d'extension de sécurité de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="2ddf2-109">![Reporting Services security extension process](../../media/rosettasecurityextensionflow.gif "Reporting Services security extension process")</span></span>

 <span data-ttu-id="2ddf2-110">Comme indiqué dans l'illustration, l'authentification et l'autorisation se déroulent comme suit :</span><span class="sxs-lookup"><span data-stu-id="2ddf2-110">As shown in the illustration, authentication and authorization occur as follows:</span></span>

1.  <span data-ttu-id="2ddf2-111">Un utilisateur tente d'accéder au Gestionnaire de rapports à l'aide d'une URL et est redirigé vers un formulaire qui collecte ses informations d'identification pour l'application cliente.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-111">A user tries to access Report Manager by using a URL and is redirected to a form that collects user credentials for the client application.</span></span>

2.  <span data-ttu-id="2ddf2-112">L'utilisateur indique ses informations d'identification sur le formulaire.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-112">The user submits credentials to the form.</span></span>

3.  <span data-ttu-id="2ddf2-113">Les informations d'identification de l'utilisateur sont transmises au service Web Reporting Services via la méthode <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-113">The user credentials are submitted to the Reporting Services Web service through the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span>

4.  <span data-ttu-id="2ddf2-114">Le service Web appelle l'extension de sécurité fournie par le client et vérifie que le nom et le mot de passe de l'utilisateur existent dans l'autorité de sécurité personnalisée.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-114">The Web service calls the customer-supplied security extension and verifies that the user name and password exist in the custom security authority.</span></span>

5.  <span data-ttu-id="2ddf2-115">Après l'authentification, le service Web crée un ticket d'authentification (appelé « cookie »), gère ce dernier et vérifie le rôle de l'utilisateur pour la page d'accueil du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-115">After authentication, the Web service creates an authentication ticket (known as a "cookie"), manages the ticket, and verifies the user's role for the Home page of Report Manager.</span></span>

6.  <span data-ttu-id="2ddf2-116">Le service Web retourne le cookie au navigateur et affiche l'interface utilisateur appropriée dans le Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-116">The Web service returns the cookie to the browser and displays the appropriate user interface in Report Manager.</span></span>

7.  <span data-ttu-id="2ddf2-117">Une fois l'utilisateur authentifié, le navigateur envoie des demandes au Gestionnaire de rapports lors de la transmission du cookie dans l'en-tête HTTP.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-117">After the user is authenticated, the browser makes requests to Report Manager while transmitting the cookie in the HTTP header.</span></span> <span data-ttu-id="2ddf2-118">Ces demandes font suite aux actions de l'utilisateur dans l'application du Gestionnaire de rapports.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-118">These requests are in response to user actions within the Report Manager application.</span></span>

8.  <span data-ttu-id="2ddf2-119">Le cookie est transmis dans l'en-tête HTTP au service Web avec l'opération d'utilisateur demandée.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-119">The cookie is transmitted in the HTTP header to the Web service along with the requested user operation.</span></span>

9. <span data-ttu-id="2ddf2-120">Le cookie est validé et, s'il est valide, le serveur de rapports retourne le descripteur de sécurité ainsi que d'autres informations sur l'opération demandée, à partir de la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-120">The cookie is validated, and if it is valid, the report server returns the security descriptor and other information relating to the requested operation from the report server database.</span></span>

10. <span data-ttu-id="2ddf2-121">Si le cookie est valide, le serveur de rapports effectue un appel vers l'extension de sécurité afin de vérifier si l'utilisateur dispose des autorisations nécessaires pour effectuer l'opération demandée.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-121">If the cookie is valid, the report server makes a call to the security extension to check if the user is authorized to perform the specific operation.</span></span>

11. <span data-ttu-id="2ddf2-122">Si tel est le cas, le serveur de rapports effectue l'opération demandée et retourne le contrôle à l'appelant.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-122">If the user is authorized, the report server performs the requested operation and returns control to the caller.</span></span>

12. <span data-ttu-id="2ddf2-123">Une fois l'utilisateur authentifié, l'accès URL au serveur de rapports utilise le même cookie.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-123">After the user is authenticated, URL access to the report server uses the same cookie.</span></span> <span data-ttu-id="2ddf2-124">Le cookie est transmis dans l'en-tête HTTP.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-124">The cookie is transmitted in the HTTP header.</span></span>

13. <span data-ttu-id="2ddf2-125">L'utilisateur continue à demander des opérations sur le serveur de rapports jusqu'à la fin de la session.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-125">The user continues to request operations on the report server until the session has ended.</span></span>

## <a name="when-to-implement-a-security-extension"></a><span data-ttu-id="2ddf2-126">Quand implémenter une extension de sécurité</span><span class="sxs-lookup"><span data-stu-id="2ddf2-126">When to Implement a Security Extension</span></span>
 <span data-ttu-id="2ddf2-127">Nous vous recommandons d'utiliser l'authentification Windows dans la mesure du possible.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-127">We recommend that you use Windows Authentication if at all possible.</span></span> <span data-ttu-id="2ddf2-128">Toutefois, une authentification et une autorisation personnalisées pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] peuvent être appropriées dans les deux cas suivants :</span><span class="sxs-lookup"><span data-stu-id="2ddf2-128">However, custom authentication and authorization for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] may be appropriate in the following two cases:</span></span>

-   <span data-ttu-id="2ddf2-129">Vous disposez d'une application Internet ou extranet qui ne peut pas utiliser de comptes Windows.</span><span class="sxs-lookup"><span data-stu-id="2ddf2-129">You have an Internet or extranet application that cannot use Windows accounts.</span></span>

-   <span data-ttu-id="2ddf2-130">Vous avez des utilisateurs et des rôles personnalisés et devez fournir un schéma d'autorisation correspondant dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ddf2-130">You have custom-defined users and roles and need to provide a matching authorization scheme in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="2ddf2-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ddf2-131">See Also</span></span>
 <span data-ttu-id="2ddf2-132">[Implémentation d’une extension de sécurité](../security-extension/implementing-a-security-extension.md) [configurer gestionnaire de rapports pour passer des cookies d’authentification personnalisée](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span><span class="sxs-lookup"><span data-stu-id="2ddf2-132">[Implementing a Security Extension](../security-extension/implementing-a-security-extension.md) [Configure Report Manager to Pass Custom Authentication Cookies](../../security/configure-the-web-portal-to-pass-custom-authentication-cookies.md)</span></span>


