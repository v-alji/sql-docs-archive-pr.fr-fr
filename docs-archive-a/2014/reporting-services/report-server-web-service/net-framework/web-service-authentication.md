---
title: Authentification du service web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], authentication
- XML Web service [Reporting Services], authentication
- Report Server Web service, authentication
ms.assetid: 852b4947-a090-4e54-8555-5a503945ceab
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0c7836d6eba8c6ab3f0a8e705ebb79c7ed73eb17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707044"
---
# <a name="web-service-authentication"></a><span data-ttu-id="f4106-102">Authentification du service web</span><span class="sxs-lookup"><span data-stu-id="f4106-102">Web Service Authentication</span></span>
  <span data-ttu-id="f4106-103">Vous pouvez utiliser l'authentification Windows ou l'authentification de base pour authentifier les appels effectués auprès du service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="f4106-103">You can use either Windows Authentication or Basic authentication to authenticate the calls made to the Report Server Web service.</span></span> <span data-ttu-id="f4106-104">Tout client qui effectue des demandes SOAP au serveur de rapports doit implémenter la partie cliente de l'un des protocoles d'authentification pris en charge.</span><span class="sxs-lookup"><span data-stu-id="f4106-104">Any client that makes SOAP requests to the report server must implement the client portion of one of the supported authentication protocols.</span></span> <span data-ttu-id="f4106-105">Si vous utilisez [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] , vous pouvez utiliser les classes http du code managé pour implémenter l’authentification.</span><span class="sxs-lookup"><span data-stu-id="f4106-105">If you are using the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], you can use the managed code HTTP classes to implement authentication.</span></span> <span data-ttu-id="f4106-106">L'utilisation de ces API simplifie l'envoi des informations d'authentification et des demandes SOAP.</span><span class="sxs-lookup"><span data-stu-id="f4106-106">Using these APIs makes it easy to send authentication information along with the SOAP requests.</span></span>  
  
 <span data-ttu-id="f4106-107">Si vous n'avez pas les informations d'identification appropriées avant d'effectuer un appel auprès du service Web Report Server, l'appel échoue.</span><span class="sxs-lookup"><span data-stu-id="f4106-107">If you do not have appropriate credentials before you make a call to the Report Server Web service, the call fails.</span></span> <span data-ttu-id="f4106-108">Au moment de l’exécution, vous pouvez passer les informations d’identification au service web en définissant la propriété **Credentials** de l’objet côté client qui représente le service web avant d’appeler ses méthodes.</span><span class="sxs-lookup"><span data-stu-id="f4106-108">At run time, you can pass credentials to the Web service by setting the **Credentials** property of the client-side object that represents the Web service before you call its methods.</span></span>  
  
 <span data-ttu-id="f4106-109">Les sections suivantes contiennent un exemple de code qui envoie des informations d'identification à l'aide de [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4106-109">The following sections contain example code that sends credentials using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="f4106-110">Authentification Windows</span><span class="sxs-lookup"><span data-stu-id="f4106-110">Windows Authentication</span></span>  
 <span data-ttu-id="f4106-111">Le code suivant passe des informations d'identification Windows au service Web.</span><span class="sxs-lookup"><span data-stu-id="f4106-111">The following code passes Windows credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials  
```  
  
```csharp  
ReportingService rs = new ReportingService();  
rs.Credentials = System.Net.CredentialCache.DefaultCredentials;  
```  
  
## <a name="basic-authentication"></a><span data-ttu-id="f4106-112">Authentification de base</span><span class="sxs-lookup"><span data-stu-id="f4106-112">Basic Authentication</span></span>  
 <span data-ttu-id="f4106-113">Le code suivant passe des informations d'identification de base au service Web.</span><span class="sxs-lookup"><span data-stu-id="f4106-113">The following code passes Basic credentials to the Web service.</span></span>  
  
```vb  
Dim rs As New ReportingService()  
rs.Credentials = New System.Net.NetworkCredential("username", "password", "domain")  
```  
  
```csharp  
ReportingService service = new ReportingService();  
service.Credentials = new System.Net.NetworkCredential("username", "password", "domain");  
```  
  
 <span data-ttu-id="f4106-114">Les informations d'identification doivent être définies avant d'appeler chacune des méthodes du service Web Report Server.</span><span class="sxs-lookup"><span data-stu-id="f4106-114">The credentials must be set before you call any of the methods of the Report Server Web service.</span></span> <span data-ttu-id="f4106-115">Si vous ne définissez pas ces informations, vous recevez le code d'erreur HTTP 401 : Accès refusé.</span><span class="sxs-lookup"><span data-stu-id="f4106-115">If you do not set the credentials, you receive the error code an HTTP 401 Error: Access Denied.</span></span> <span data-ttu-id="f4106-116">Vous devez authentifier le service avant de l’utiliser, mais après avoir défini les informations d’identification, il n’est pas nécessaire de les définir à nouveau si vous continuez à utiliser la même variable de service (telle que *rs*).</span><span class="sxs-lookup"><span data-stu-id="f4106-116">You must authenticate the service before you use it, but after you have set the credentials, you do not need to set them again as long as you continue to use the same service variable (such as *rs*).</span></span>  
  
## <a name="custom-authentication"></a><span data-ttu-id="f4106-117">Authentification personnalisée</span><span class="sxs-lookup"><span data-stu-id="f4106-117">Custom Authentication</span></span>  
 [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="f4106-118">inclut une API de programmation qui permet aux développeurs de concevoir et de développer des extensions d'authentification personnalisées appelées extensions de sécurité.</span><span class="sxs-lookup"><span data-stu-id="f4106-118">includes a programming API that provides developers with the opportunity to design and develop custom authentication extensions, known as security extensions.</span></span> <span data-ttu-id="f4106-119">Pour plus d’informations, consultez [Implémentation d’une extension de sécurité](../../extensions/security-extension/implementing-a-security-extension.md).</span><span class="sxs-lookup"><span data-stu-id="f4106-119">For more information, see [Implementing a Security Extension](../../extensions/security-extension/implementing-a-security-extension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4106-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4106-120">See Also</span></span>  
 <span data-ttu-id="f4106-121">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="f4106-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="f4106-122">Service Web des serveurs de rapports</span><span class="sxs-lookup"><span data-stu-id="f4106-122">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
