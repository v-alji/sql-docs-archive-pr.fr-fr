---
title: Authentification dans Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- security [Reporting Services], authentication
- forms-based authentication [Reporting Services]
- authentication [Reporting Services]
- custom authentication [Reporting Services]
ms.assetid: 103ce1f9-31d8-44bb-b540-2752e4dcf60b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59e97ba6ef849d8b4bfddfd6953c85826e351d6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610480"
---
# <a name="authentication-in-reporting-services"></a><span data-ttu-id="ca43d-102">Authentification dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ca43d-102">Authentication in Reporting Services</span></span>
  <span data-ttu-id="ca43d-103">L'authentification est le processus d'établissement du droit d'un utilisateur à une identité.</span><span class="sxs-lookup"><span data-stu-id="ca43d-103">Authentication is the process of establishing a user's right to an identity.</span></span> <span data-ttu-id="ca43d-104">De nombreuses techniques vous permettent d'authentifier un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ca43d-104">There are many techniques that you can use to authenticate a user.</span></span> <span data-ttu-id="ca43d-105">La façon la plus courante consiste à utiliser des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="ca43d-105">The most common way is to use passwords.</span></span> <span data-ttu-id="ca43d-106">Par exemple, lorsque vous implémentez l'authentification par formulaire, vous voulez une implémentation qui interroge les utilisateurs au sujet de leurs informations d'identification (généralement par le biais d'une interface qui demande un nom de connexion et un mot de passe), puis valide les utilisateurs par rapport à une banque de données, telle qu'une table de base de données ou un fichier de configuration.</span><span class="sxs-lookup"><span data-stu-id="ca43d-106">When you implement Forms Authentication, for example, you want an implementation that queries users for credentials (usually by some interface that requests a login name and password) and then validates users against a data store, such as a database table or configuration file.</span></span> <span data-ttu-id="ca43d-107">Si les informations d'identification ne peuvent pas être validées, le processus d'authentification échoue et l'utilisateur assume une identité anonyme.</span><span class="sxs-lookup"><span data-stu-id="ca43d-107">If the credentials can't be validated, the authentication process fails and the user will assume an anonymous identity.</span></span>  
  
## <a name="custom-authentication-in-reporting-services"></a><span data-ttu-id="ca43d-108">Authentification personnalisée dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="ca43d-108">Custom Authentication in Reporting Services</span></span>  
 <span data-ttu-id="ca43d-109">Dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], le système d'exploitation Windows traite l'authentification des utilisateurs par le biais de la sécurité intégrée ou de la réception explicite et de la validation des informations d'identification des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ca43d-109">In [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], the Windows operating system handles the authentication of users either through integrated security or through the explicit reception and validation of user credentials.</span></span> <span data-ttu-id="ca43d-110">L'authentification personnalisée peut être développée dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pour prendre en charge des schémas d'authentification supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="ca43d-110">Custom authentication can be developed in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to support additional authentication schemes.</span></span> <span data-ttu-id="ca43d-111">Cela est possible grâce à l'interface d'extension de sécurité <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span><span class="sxs-lookup"><span data-stu-id="ca43d-111">This is made possible through the security extension interface <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>.</span></span> <span data-ttu-id="ca43d-112">Toutes les extensions héritent de l'interface de base <xref:Microsoft.ReportingServices.Interfaces.IExtension> pour toute extension déployée et utilisée par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ca43d-112">All extensions inherit from the <xref:Microsoft.ReportingServices.Interfaces.IExtension> base interface for any extension deployed and used by the report server.</span></span> <span data-ttu-id="ca43d-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, ainsi que <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, sont membres de l'espace de noms <xref:Microsoft.ReportingServices.Interfaces>.</span><span class="sxs-lookup"><span data-stu-id="ca43d-113"><xref:Microsoft.ReportingServices.Interfaces.IExtension>, as well as <xref:Microsoft.ReportingServices.Interfaces.IAuthenticationExtension>, are members of the <xref:Microsoft.ReportingServices.Interfaces> namespace.</span></span>  
  
 <span data-ttu-id="ca43d-114">Le principal moyen d'authentification auprès d'un serveur de rapports dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] est la méthode <xref:ReportService2010.ReportingService2010.LogonUser%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca43d-114">The primary way to authenticate against a report server in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] is the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method.</span></span> <span data-ttu-id="ca43d-115">Ce membre du service Web Reporting Services peut être utilisé pour passer les informations d'identification de l'utilisateur à un serveur de rapports pour validation.</span><span class="sxs-lookup"><span data-stu-id="ca43d-115">This member of the Reporting Services Web service can be used to pass user credentials to a report server for validation.</span></span> <span data-ttu-id="ca43d-116">Votre extension de sécurité sous-jacente implémente **IAuthenticationExtension. LogonUser** qui contient votre code d’authentification personnalisé.</span><span class="sxs-lookup"><span data-stu-id="ca43d-116">Your underlying security extension implements **IAuthenticationExtension.LogonUser** which contains your custom authentication code.</span></span> <span data-ttu-id="ca43d-117">Dans l’exemple d’authentification par formulaire, **LogonUser** effectue un contrôle d’authentification par rapport aux informations d’identification fournies et un magasin d’utilisateurs personnalisé dans une base de données.</span><span class="sxs-lookup"><span data-stu-id="ca43d-117">In the Forms Authentication sample, **LogonUser**, which performs an authentication check against the supplied credentials and a custom user store in a database.</span></span> <span data-ttu-id="ca43d-118">L’exemple suivant illustre une implémentation de **LogonUser** :</span><span class="sxs-lookup"><span data-stu-id="ca43d-118">An example of an implementation of **LogonUser** looks like this:</span></span>  
  
```  
public bool LogonUser(string userName, string password, string authority)  
{  
   return AuthenticationUtilities.VerifyPassword(userName, password);  
}  
  
```  
  
 <span data-ttu-id="ca43d-119">L'exemple de fonction suivant est utilisé pour vérifier les informations d'identification fournies :</span><span class="sxs-lookup"><span data-stu-id="ca43d-119">The following sample function is used to verify the supplied credentials:</span></span>  
  
```  
  
internal static bool VerifyPassword(string suppliedUserName,  
   string suppliedPassword)  
{   
   bool passwordMatch = false;  
   // Get the salt and pwd from the database based on the user name.  
   // See "How To: Use DPAPI (Machine Store) from ASP.NET," "How To:  
   // Use DPAPI (User Store) from Enterprise Services," and "How To:  
   // Create a DPAPI Library" for more information about how to use  
   // DPAPI to securely store connection strings.  
   SqlConnection conn = new SqlConnection(  
      "Server=localhost;" +   
      "Integrated Security=SSPI;" +  
      "database=UserAccounts");  
   SqlCommand cmd = new SqlCommand("LookupUser", conn);  
   cmd.CommandType = CommandType.StoredProcedure;  
  
   SqlParameter sqlParam = cmd.Parameters.Add("@userName",  
       SqlDbType.VarChar,  
       255);  
   sqlParam.Value = suppliedUserName;  
   try  
   {  
      conn.Open();  
      SqlDataReader reader = cmd.ExecuteReader();  
      reader.Read(); // Advance to the one and only row  
      // Return output parameters from returned data stream  
      string dbPasswordHash = reader.GetString(0);  
      string salt = reader.GetString(1);  
      reader.Close();  
      // Now take the salt and the password entered by the user  
      // and concatenate them together.  
      string passwordAndSalt = String.Concat(suppliedPassword, salt);  
      // Now hash them  
      string hashedPasswordAndSalt =  
         FormsAuthentication.HashPasswordForStoringInConfigFile(  
         passwordAndSalt,  
         "SHA1");  
      // Now verify them. Returns true if they are equal.  
      passwordMatch = hashedPasswordAndSalt.Equals(dbPasswordHash);  
   }  
   catch (Exception ex)  
   {  
       throw new Exception("Exception verifying password. " +  
          ex.Message);  
   }  
   finally  
   {  
       conn.Close();  
   }  
   return passwordMatch;  
}  
```  
  
## <a name="authentication-flow"></a><span data-ttu-id="ca43d-120">Flux d'authentification</span><span class="sxs-lookup"><span data-stu-id="ca43d-120">Authentication Flow</span></span>  
 <span data-ttu-id="ca43d-121">Le service Web Reporting Services fournit des extensions d'authentification personnalisées pour permettre au Gestionnaire de rapports et au serveur de rapports d'effectuer l'authentification par formulaire.</span><span class="sxs-lookup"><span data-stu-id="ca43d-121">The Reporting Services Web service provides custom authentication extensions to enable Forms Authentication by Report Manager and the report server.</span></span>  
  
 <span data-ttu-id="ca43d-122">La méthode <xref:ReportService2010.ReportingService2010.LogonUser%2A> du service Web Reporting Services est utilisée pour envoyer des informations d'identification au serveur de rapports pour authentification.</span><span class="sxs-lookup"><span data-stu-id="ca43d-122">The <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of the Reporting Services Web service is used to submit credentials to the report server for authentication.</span></span> <span data-ttu-id="ca43d-123">Le service Web utilise des en-têtes HTTP pour passer un ticket d'authentification (appelé « cookie ») du serveur au client pour les demandes d'ouverture de session validées.</span><span class="sxs-lookup"><span data-stu-id="ca43d-123">The Web service uses HTTP headers to pass an authentication ticket (known as a "cookie") from the server to the client for validated logon requests.</span></span>  
  
 <span data-ttu-id="ca43d-124">L'illustration suivante représente la méthode d'authentification d'utilisateurs auprès du service Web lorsque votre application est déployée avec un serveur de rapports configuré pour utiliser une extension d'authentification personnalisée.</span><span class="sxs-lookup"><span data-stu-id="ca43d-124">The following illustration depicts the method of authenticating users to the Web service when your application is deployed with a report server configured to use a custom authentication extension.</span></span>  
  
 <span data-ttu-id="ca43d-125">![Flux d'authentification de sécurité de Reporting Services](../../media/rosettasecurityextensionauthenticationflow.gif "Flux d'authentification de sécurité de Reporting Services")</span><span class="sxs-lookup"><span data-stu-id="ca43d-125">![Reporting Services security authentication flow](../../media/rosettasecurityextensionauthenticationflow.gif "Reporting Services security authentication flow")</span></span>  
  
 <span data-ttu-id="ca43d-126">Comme indiqué dans la figure 2, le processus d'authentification est le suivant :</span><span class="sxs-lookup"><span data-stu-id="ca43d-126">As shown in Figure 2, the authentication process is as follows:</span></span>  
  
1.  <span data-ttu-id="ca43d-127">Une application cliente appelle la méthode <xref:ReportService2010.ReportingService2010.LogonUser%2A> du service Web pour authentifier un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ca43d-127">A client application calls the Web service <xref:ReportService2010.ReportingService2010.LogonUser%2A> method to authenticate a user.</span></span>  
  
2.  <span data-ttu-id="ca43d-128">Le service Web appelle la <xref:ReportService2010.ReportingService2010.LogonUser%2A> méthode de votre extension de sécurité, plus précisément la classe qui implémente **IAuthenticationExtension**.</span><span class="sxs-lookup"><span data-stu-id="ca43d-128">The Web service makes a call to the <xref:ReportService2010.ReportingService2010.LogonUser%2A> method of your security extension, specifically, the class that implements **IAuthenticationExtension**.</span></span>  
  
3.  <span data-ttu-id="ca43d-129">Votre implémentation de <xref:ReportService2010.ReportingService2010.LogonUser%2A> valide le nom d'utilisateur et le mot de passe dans le magasin d'utilisateurs ou l'autorité de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ca43d-129">Your implementation of <xref:ReportService2010.ReportingService2010.LogonUser%2A> validates the user name and password in the user store or security authority.</span></span>  
  
4.  <span data-ttu-id="ca43d-130">En cas d'authentification réussie, le service Web crée un cookie et le gère pour la session.</span><span class="sxs-lookup"><span data-stu-id="ca43d-130">Upon successful authentication, the Web service creates a cookie and manages it for the session.</span></span>  
  
5.  <span data-ttu-id="ca43d-131">Le service Web retourne le ticket d'authentification à l'application appelante sur l'en-tête HTTP.</span><span class="sxs-lookup"><span data-stu-id="ca43d-131">The Web service returns the authentication ticket to the calling application on the HTTP header.</span></span>  
  
 <span data-ttu-id="ca43d-132">Lorsque le service Web authentifie avec succès un utilisateur par le biais de l'extension de sécurité, il génère un cookie qui est utilisé pour les demandes suivantes.</span><span class="sxs-lookup"><span data-stu-id="ca43d-132">When the Web service successfully authenticates a user through the security extension, it generates a cookie that is used for subsequent requests.</span></span> <span data-ttu-id="ca43d-133">Le cookie n'est pas persistant dans l'autorité de sécurité personnalisée puisque celle-ci n'appartient pas au serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ca43d-133">The cookie may not persist within the custom security authority because the report server does not own the security authority.</span></span> <span data-ttu-id="ca43d-134">Le cookie est retourné par la méthode <xref:ReportService2010.ReportingService2010.LogonUser%2A> du service Web et est utilisé dans les appels de méthode du service Web suivants et dans l'accès URL.</span><span class="sxs-lookup"><span data-stu-id="ca43d-134">The cookie is returned from the <xref:ReportService2010.ReportingService2010.LogonUser%2A> Web service method and is used in subsequent Web service method calls and in URL access.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ca43d-135">Pour éviter de compromettre le cookie pendant la transmission, les cookies d'authentification retournés par <xref:ReportService2010.ReportingService2010.LogonUser%2A> doivent être transmis de manière sécurisée à l'aide du chiffrement SSL (Secure Sockets Layer).</span><span class="sxs-lookup"><span data-stu-id="ca43d-135">In order to avoid compromising the cookie during transmission, authentication cookies returned from <xref:ReportService2010.ReportingService2010.LogonUser%2A> should be transmitted securely using Secure Sockets Layer (SSL) encryption.</span></span>  
  
 <span data-ttu-id="ca43d-136">Si vous accédez au serveur de rapports par l'accès URL lorsqu'une extension de sécurité personnalisée est installée, les services Internet (IIS) et [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] gèrent automatiquement la transmission du ticket d'authentification.</span><span class="sxs-lookup"><span data-stu-id="ca43d-136">If you access the report server through URL access when a custom security extension is installed, Internet Information Services (IIS) and [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] automatically manage the transmission of the authentication ticket.</span></span> <span data-ttu-id="ca43d-137">Si vous accédez au serveur de rapports par le biais de l'API SOAP, votre implémentation de la classe proxy doit inclure la prise en charge supplémentaire pour gérer le ticket d'authentification.</span><span class="sxs-lookup"><span data-stu-id="ca43d-137">If you are accessing the report server through the SOAP API, your implementation of the proxy class must include additional support for managing the authentication ticket.</span></span> <span data-ttu-id="ca43d-138">Pour plus d'informations sur l'utilisation de l'API SOAP et la gestion du ticket d'authentification, consultez « Utilisation du service Web avec la sécurité personnalisée ».</span><span class="sxs-lookup"><span data-stu-id="ca43d-138">For more information about using the SOAP API and managing the authentication ticket, see "Using the Web Service with Custom Security."</span></span>  
  
## <a name="forms-authentication"></a><span data-ttu-id="ca43d-139">Authentification par formulaire</span><span class="sxs-lookup"><span data-stu-id="ca43d-139">Forms Authentication</span></span>  
 <span data-ttu-id="ca43d-140">L'authentification par formulaire est un type d'authentification [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] dans laquelle un utilisateur non authentifié est dirigé vers un formulaire HTML.</span><span class="sxs-lookup"><span data-stu-id="ca43d-140">Forms Authentication is a type of [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in which an unauthenticated user is directed to an HTML form.</span></span> <span data-ttu-id="ca43d-141">Lorsque l'utilisateur fournit des informations d'identification, le système émet un cookie qui contient un ticket d'authentification.</span><span class="sxs-lookup"><span data-stu-id="ca43d-141">Once the user provides credentials, the system issues a cookie containing an authentication ticket.</span></span> <span data-ttu-id="ca43d-142">Lors des demandes ultérieures, le système examine d'abord le cookie pour déterminer si l'utilisateur a déjà été authentifié par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ca43d-142">On later requests, the system first checks the cookie to see if the user was already authenticated by the report server.</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ca43d-143">peut être étendu pour prendre en charge l'authentification par formulaire à l'aide des interfaces d'extensibilité de la sécurité disponibles par le biais de l'API Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ca43d-143">can be extended to support Forms Authentication using the security extensibility interfaces available through the Reporting Services API.</span></span> <span data-ttu-id="ca43d-144">Si vous étendez [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] pour utiliser l'authentification par formulaire, utilisez le chiffrement SSL pour toutes les communications avec le serveur de rapports pour empêcher des utilisateurs malveillants d'accéder au cookie d'un autre utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ca43d-144">If you extend [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] to use Forms Authentication, use Secure Sockets Layer (SSL) for all communications with the report server to prevent malicious users from gaining access to another user's cookie.</span></span> <span data-ttu-id="ca43d-145">Le chiffrement SSL permet aux clients et au serveur de rapports de s'authentifier mutuellement et garantit qu'aucun autre ordinateur ne peut lire le contenu des communications entre les deux ordinateurs.</span><span class="sxs-lookup"><span data-stu-id="ca43d-145">SSL enables clients and a report server to authenticate each other and to ensure that no other computers can read the contents of communications between the two computers.</span></span> <span data-ttu-id="ca43d-146">Toutes les données envoyées par un client par un client une connexion SSL sont chiffrées pour empêcher des utilisateurs malveillants d'intercepter des mots de passe ou des données envoyés à un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ca43d-146">All data sent from a client through an SSL connection is encrypted so that malicious users cannot intercept passwords or data sent to a report server.</span></span>  
  
 <span data-ttu-id="ca43d-147">L'authentification par formulaire est généralement implémentée pour prendre en charge des comptes et l'authentification pour des plateformes autres que Windows.</span><span class="sxs-lookup"><span data-stu-id="ca43d-147">Forms Authentication is generally implemented to support accounts and authentication for platforms other than Windows.</span></span> <span data-ttu-id="ca43d-148">Une interface graphique est présentée à un utilisateur qui demande l'accès à un serveur de rapports, et les informations d'identification fournies sont envoyées à une autorité de sécurité pour authentification.</span><span class="sxs-lookup"><span data-stu-id="ca43d-148">A graphical interface is presented to a user who requests access to a report server, and the supplied credentials are submitted to a security authority for authentication.</span></span>  
  
 <span data-ttu-id="ca43d-149">L'authentification par formulaire nécessite qu'une personne soit présente pour entrer des informations d'identification.</span><span class="sxs-lookup"><span data-stu-id="ca43d-149">Forms Authentication requires that a person is present to enter credentials.</span></span> <span data-ttu-id="ca43d-150">Pour les applications sans assistance qui communiquent directement avec le service Web Reporting Services, l'authentification par formulaire doit être associée à un schéma d'authentification personnalisé.</span><span class="sxs-lookup"><span data-stu-id="ca43d-150">For unattended applications that communicate directly with the Reporting Services Web service, Forms Authentication must be combined with a custom authentication scheme.</span></span>  
  
 <span data-ttu-id="ca43d-151">L'authentification par formulaire est adaptée à [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] lorsque vous devez répondre aux deux exigences suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca43d-151">Forms Authentication is appropriate for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] when:</span></span>  
  
-   <span data-ttu-id="ca43d-152">Vous devez stocker et authentifier des utilisateurs qui ne possèdent pas de comptes [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="ca43d-152">You need to store and authenticate users that do not have [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows accounts, and</span></span>  
  
-   <span data-ttu-id="ca43d-153">Vous devez fournir votre propre formulaire d'interface utilisateur en tant que page d'ouverture de session entre différentes pages sur un site Web.</span><span class="sxs-lookup"><span data-stu-id="ca43d-153">You need to provide your own user interface form as a logon page between different pages on a Web site.</span></span>  
  
 <span data-ttu-id="ca43d-154">Tenez compte des points suivants lors de l'écriture d'une extension de sécurité personnalisée qui prend en charge l'authentification par formulaire :</span><span class="sxs-lookup"><span data-stu-id="ca43d-154">Consider the following when writing a custom security extension that supports Forms Authentication:</span></span>  
  
-   <span data-ttu-id="ca43d-155">Si vous utilisez l'authentification par formulaire, l'accès anonyme doit être activé sur le répertoire virtuel du serveur de rapports dans les services Internet (IIS).</span><span class="sxs-lookup"><span data-stu-id="ca43d-155">If you use Forms Authentication, anonymous access must be enabled on the report server virtual directory in Internet Information Services (IIS).</span></span>  
  
-   <span data-ttu-id="ca43d-156">L'authentification [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] doit avoir la valeur « Forms ».</span><span class="sxs-lookup"><span data-stu-id="ca43d-156">[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication must be set to Forms.</span></span> <span data-ttu-id="ca43d-157">Vous configurez l'authentification [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] dans le fichier Web.config pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="ca43d-157">You configure [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] authentication in the Web.config file for the report server.</span></span>  
  
-   [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ca43d-158">peut authentifier et autoriser des utilisateurs avec l'authentification Windows ou l'authentification personnalisée, mais pas les deux à la fois.</span><span class="sxs-lookup"><span data-stu-id="ca43d-158">can authenticate and authorize users with either Windows Authentication or custom authentication, but not both.</span></span> [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="ca43d-159">ne prend pas en charge l'utilisation simultanée de plusieurs extensions de sécurité.</span><span class="sxs-lookup"><span data-stu-id="ca43d-159">does not support simultaneous use of multiple security extensions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca43d-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca43d-160">See Also</span></span>  
 [<span data-ttu-id="ca43d-161">Implémentation d'une extension de sécurité</span><span class="sxs-lookup"><span data-stu-id="ca43d-161">Implementing a Security Extension</span></span>](../security-extension/implementing-a-security-extension.md)  
  
  
