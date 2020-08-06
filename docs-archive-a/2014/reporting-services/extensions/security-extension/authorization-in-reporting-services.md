---
title: Autorisation dans Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- authorization [Reporting Services]
ms.assetid: 15fc1c7b-560c-4737-b126-e0d428a1b530
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7420b45175ca0b0a5fc66da4a7939b07b79c75b7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610471"
---
# <a name="authorization-in-reporting-services"></a><span data-ttu-id="ce0b6-102">Autorisation dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ce0b6-102">Authorization in Reporting Services</span></span>
  <span data-ttu-id="ce0b6-103">L'autorisation est le processus permettant de déterminer si une identité peut se voir accorder le type d'accès demandé à une ressource donnée dans la base de données du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-103">Authorization is the process of determining whether an identity should be granted the requested type of access to a given resource in the report server database.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ce0b6-104">utilise une architecture d'autorisation basée sur les rôles qui permet à un utilisateur d'accéder à une ressource donnée en fonction de l'attribution de rôle de l'utilisateur pour l'application.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-104">uses a role-based authorization architecture that grants a user access to a given resource based on the user's role assignment for the application.</span></span> <span data-ttu-id="ce0b6-105">Les extensions de sécurité pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contiennent une implémentation d'un composant d'autorisation servant à accorder l'accès aux utilisateurs une fois ceux-ci authentifiés sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-105">Security extensions for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] contain an implementation of an authorization component that is used to grant access to users once they are authenticated on the report server.</span></span> <span data-ttu-id="ce0b6-106">L'autorisation est appelée lorsqu'un utilisateur tente d'effectuer une opération sur le système ou sur un élément du serveur de rapports par le biais de l'API SOAP et via l'accès URL.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-106">Authorization is invoked when a user attempts to perform an operation on the system or a report server item through the SOAP API and via URL access.</span></span> <span data-ttu-id="ce0b6-107">Cela est possible grâce à l'interface d'extension de sécurité **IAuthorizationExtension**.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-107">This is made possible through the security extension interface **IAuthorizationExtension**.</span></span> <span data-ttu-id="ce0b6-108">Comme indiqué précédemment, toutes les extensions héritent d' **IExtension** , l'interface de base pour n'importe quelle extension que vous déployez.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-108">As stated previously, all extensions inherit from **IExtension** the base interface for any extension that you deploy.</span></span> <span data-ttu-id="ce0b6-109">**IExtension** et **IAuthorizationExtension** sont membres de l'espace de noms **Microsoft.ReportingServices.Interfaces** .</span><span class="sxs-lookup"><span data-stu-id="ce0b6-109">**IExtension** and **IAuthorizationExtension** are members of the **Microsoft.ReportingServices.Interfaces** namespace.</span></span>

## <a name="checking-access"></a><span data-ttu-id="ce0b6-110">Vérification de l'accès</span><span class="sxs-lookup"><span data-stu-id="ce0b6-110">Checking Access</span></span>
 <span data-ttu-id="ce0b6-111">En matière d'autorisation, l'élément fondamental de toute implémentation de sécurité personnalisée est la vérification de l'accès, qui est implémentée dans la méthode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-111">In authorization, the key to any custom security implementation is the access check, which is implemented in the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span> <span data-ttu-id="ce0b6-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> est appelé chaque fois qu'un utilisateur tente une opération sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-112"><xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> is called each time a user attempts an operation on the report server.</span></span> <span data-ttu-id="ce0b6-113">La méthode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> est surchargée pour chaque type d'opération.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-113">The <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method is overloaded for each operation type.</span></span> <span data-ttu-id="ce0b6-114">Voici un exemple de vérification d'accès pour les opérations de dossier :</span><span class="sxs-lookup"><span data-stu-id="ce0b6-114">For folder operations, an example of an access check might look like the following:</span></span>

```
// Overload for Folder operations
public bool CheckAccess(
   string userName, 
   IntPtr userToken, 
   byte[] secDesc, 
   FolderOperation requiredOperation)
{
   // If the user is the administrator, allow unrestricted access.
   if (userName == m_adminUserName) 
      return true;

   AceCollection acl = DeserializeAcl(secDesc);
   foreach(AceStruct ace in acl)
   {
         if (userName == ace.PrincipalName)
         {
            foreach(FolderOperation aclOperation in 
               ace.FolderOperations)
            {
               if (aclOperation == requiredOperation)
                     return true;
            }
         }
   }
   return false;
}
```

 <span data-ttu-id="ce0b6-115">Le serveur de rapports appelle la méthode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> en passant le nom de l'utilisateur connecté, un jeton utilisateur, le descripteur de sécurité de l'élément et l'opération demandée dans le nom de l'utilisateur connecté.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-115">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method by passing in the name of the logged-on user, a user token, the security descriptor for the item, and the requested operation.</span></span> <span data-ttu-id="ce0b6-116">Ici, vous devez vérifier le descripteur de sécurité pour le nom d'utilisateur et l'autorisation appropriée pour effectuer la demande, puis retourner `true` pour indiquer que l'accès est accordé ou `false` pour indiquer que l'accès est refusé.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-116">Here you would check the security descriptor for the user name and the appropriate permission to complete the request, then return `true` to signify that access is granted or `false` to signify access is denied.</span></span>

## <a name="security-descriptors"></a><span data-ttu-id="ce0b6-117">Descripteurs de sécurité</span><span class="sxs-lookup"><span data-stu-id="ce0b6-117">Security Descriptors</span></span>
 <span data-ttu-id="ce0b6-118">Lors de la définition de stratégies d'autorisation sur des éléments dans la base de données du serveur de rapports, une application cliente (telle que le Gestionnaire de rapports) envoie les informations utilisateur ainsi qu'une stratégie de sécurité pour l'élément à l'extension de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-118">When setting authorization policies on items in the report server database, a client application (such as Report Manager) submits the user information to the security extension along with a security policy for the item.</span></span> <span data-ttu-id="ce0b6-119">La stratégie de sécurité et les informations utilisateur sont désignées collectivement sous le nom de « descripteur de sécurité ».</span><span class="sxs-lookup"><span data-stu-id="ce0b6-119">This security policy and user information are known collectively as a security descriptor.</span></span> <span data-ttu-id="ce0b6-120">Un descripteur de sécurité contient les informations suivantes pour un élément dans la base de données du serveur de rapports :</span><span class="sxs-lookup"><span data-stu-id="ce0b6-120">A security descriptor contains the following information for an item in the report server database:</span></span>

-   <span data-ttu-id="ce0b6-121">le groupe ou l'utilisateur étant autorisé d'une certaine manière à effectuer des opérations sur l'élément ;</span><span class="sxs-lookup"><span data-stu-id="ce0b6-121">The group or user that has some type of permission to perform operations on the item.</span></span>

-   <span data-ttu-id="ce0b6-122">le type de l'élément ;</span><span class="sxs-lookup"><span data-stu-id="ce0b6-122">The item's type.</span></span>

-   <span data-ttu-id="ce0b6-123">une liste de contrôle d'accès discrétionnaire qui contrôle l'accès à l'élément.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-123">A discretionary access control list controlling access to the item.</span></span>

 <span data-ttu-id="ce0b6-124">Les descripteurs de sécurité sont créés à l'aide des méthodes <xref:ReportService2010.ReportingService2010.SetPolicies%2A> et <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> du service Web.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-124">Security descriptors are created using the Web service <xref:ReportService2010.ReportingService2010.SetPolicies%2A> and <xref:ReportService2010.ReportingService2010.SetSystemPolicies%2A> methods.</span></span>

### <a name="authorization-flow"></a><span data-ttu-id="ce0b6-125">Flux d'autorisation</span><span class="sxs-lookup"><span data-stu-id="ce0b6-125">Authorization Flow</span></span>
 <span data-ttu-id="ce0b6-126">L'autorisation [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] est contrôlée par l'extension de sécurité actuellement configurée pour s'exécuter sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-126">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] authorization is controlled by the security extension currently configured to run on the server.</span></span> <span data-ttu-id="ce0b6-127">L'autorisation, basée sur les rôles, est limitée aux autorisations et aux opérations fournies par l'architecture de la sécurité [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ce0b6-127">Authorization is role-based and limited to the permissions and operations supplied by the [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] security architecture.</span></span> <span data-ttu-id="ce0b6-128">Le diagramme suivant représente le processus permettant d'autoriser des utilisateurs à manipuler des éléments dans la base de données du serveur de rapports :</span><span class="sxs-lookup"><span data-stu-id="ce0b6-128">The following diagram depicts the process of authorizing users to operate on items in the report server database:</span></span>

 <span data-ttu-id="ce0b6-129">![Flux d'autorisation de sécurité de Reporting Services](../../media/rosettasecurityextensionauthorizationflow.gif "Flux d'autorisation de sécurité de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="ce0b6-129">![Reporting Services security authorization flow](../../media/rosettasecurityextensionauthorizationflow.gif "Reporting Services security authorization flow")</span></span>

 <span data-ttu-id="ce0b6-130">Comme représenté dans ce diagramme, l'autorisation suit la séquence suivante :</span><span class="sxs-lookup"><span data-stu-id="ce0b6-130">As shown in this diagram, authorization follows this sequence:</span></span>

1.  <span data-ttu-id="ce0b6-131">Une fois authentifié, les applications clientes font des demandes au serveur de rapports par le biais des méthodes du service Web Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-131">Once authenticated, client applications make requests to the report server through the Reporting Services Web service methods.</span></span> <span data-ttu-id="ce0b6-132">Un ticket d'authentification est passé au serveur de rapports sous forme d'un cookie dans l'en-tête HTTP de chaque demande Web.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-132">An authentication ticket is passed to the report server in the form of a cookie in the HTTP header of each Web request.</span></span>

2.  <span data-ttu-id="ce0b6-133">Le cookie est validé avant toute vérification d'accès.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-133">The cookie is validated prior to any access check.</span></span>

3.  <span data-ttu-id="ce0b6-134">Une fois le cookie validé, le serveur de rapports appelle <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> et une identité est attribuée à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-134">Once the cookie is validated, the report server calls <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension.GetUserInfo%2A> and the user is given an identity.</span></span>

4.  <span data-ttu-id="ce0b6-135">L'utilisateur tente une opération par le biais du service Web Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-135">The user attempts an operation through the Reporting Services Web service.</span></span>

5.  <span data-ttu-id="ce0b6-136">Le serveur de rapports appelle la méthode <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-136">The report server calls the <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A> method.</span></span>

6.  <span data-ttu-id="ce0b6-137">Le descripteur de sécurité est récupéré et passé à une implémentation d'extension de sécurité personnalisée de <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-137">The security descriptor is retrieved and passed to a custom security extension implementation of <xref:Microsoft.ReportingServices.Interfaces.IAuthorizationExtension.CheckAccess%2A>.</span></span> <span data-ttu-id="ce0b6-138">À ce stade, l'utilisateur, le groupe ou l'ordinateur est comparé au descripteur de sécurité de l'élément en cours d'accès et est autorisé à effectuer l'opération demandée.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-138">At this point, the user, group, or computer is compared to the security descriptor of the item being accessed and is authorized to perform the requested operation.</span></span>

7.  <span data-ttu-id="ce0b6-139">Si l'utilisateur est autorisé, le service Web effectue l'opération et retourne une réponse à l'application appelante.</span><span class="sxs-lookup"><span data-stu-id="ce0b6-139">If the user is authorized, the Web service performs the operation and returns a response to the calling application.</span></span>


