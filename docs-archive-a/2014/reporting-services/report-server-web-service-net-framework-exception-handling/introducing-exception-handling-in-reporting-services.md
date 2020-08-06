---
title: Présentation de la gestion des exceptions dans Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], exception handling
- errors [Reporting Services]
- exceptions [Reporting Services]
- Report Server Web service, exception handling
- XML Web service [Reporting Services], exception handling
ms.assetid: 54381870-ce67-482b-aa83-6a838cdbf9b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 091b1f40d293515617e369b750a5f18dfe12951b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699318"
---
# <a name="introducing-exception-handling-in-reporting-services"></a><span data-ttu-id="5dbfd-102">Présentation de la gestion des exceptions dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5dbfd-102">Introducing Exception Handling in Reporting Services</span></span>
  <span data-ttu-id="5dbfd-103">Si votre application [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] envoie un demande au service Web Report Server, mais que ce dernier ne parvient pas à la traiter, le service retourne une exception SOAP au client.</span><span class="sxs-lookup"><span data-stu-id="5dbfd-103">If your [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] application sends a request to the Report Server Web service that the service is unable to process, the service returns a SOAP exception to the client.</span></span> <span data-ttu-id="5dbfd-104">La gestion des exceptions levées par le service Web Report Server est une composante importante des applications que vous développez car vous avez la possibilité de retourner des informations utiles aux utilisateurs lorsque des erreurs se produisent.</span><span class="sxs-lookup"><span data-stu-id="5dbfd-104">Handling exceptions thrown by the Report Server Web service is an important part of the applications that you develop because you can return useful information to users when errors occur.</span></span>  
  
 <span data-ttu-id="5dbfd-105">Cette section contient des informations sur la gestion des exceptions, la manière d'éviter les entrées utilisateur non valides et l'envoi d'informations pertinentes sur les erreurs aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5dbfd-105">This section contains specific information about handling exceptions, preventing user input that is not valid, and returning meaningful error information to users.</span></span> <span data-ttu-id="5dbfd-106">Pour obtenir des informations générales sur la gestion des exceptions, consultez « Gestion et levée des exceptions » dans la [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] documentation du kit de développement logiciel (SDK).</span><span class="sxs-lookup"><span data-stu-id="5dbfd-106">For general information about exception handling, see "Handling and Throwing Exceptions" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5dbfd-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="5dbfd-107">In This Section</span></span>  
  
|<span data-ttu-id="5dbfd-108">Rubrique</span><span class="sxs-lookup"><span data-stu-id="5dbfd-108">Topic</span></span>|<span data-ttu-id="5dbfd-109">Description</span><span class="sxs-lookup"><span data-stu-id="5dbfd-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5dbfd-110">Gestion des exceptions dans Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5dbfd-110">Handling Exceptions in Reporting Services</span></span>](handling-exceptions-in-reporting-services.md)|<span data-ttu-id="5dbfd-111">Fournit une vue d'ensemble des exceptions dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] et le rôle de SOAP dans le renvoi d'erreurs depuis un service Web.</span><span class="sxs-lookup"><span data-stu-id="5dbfd-111">Provides an overview of exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] and the role of SOAP in returning errors from a Web service.</span></span>|  
|[<span data-ttu-id="5dbfd-112">Meilleures pratiques pour la gestion des exceptions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5dbfd-112">Best Practices for Reporting Services Exception Handling</span></span>](best-practices/best-practices-for-reporting-services-exception-handling.md)|<span data-ttu-id="5dbfd-113">Fournit des recommandations sur la manière de gérer les exceptions dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbfd-113">Provides recommendations on how to handle exceptions in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="5dbfd-114">Classe SoapException Reporting Services</span><span class="sxs-lookup"><span data-stu-id="5dbfd-114">Reporting Services SoapException Class</span></span>](soapexception-class/reporting-services-soapexception-class.md)|<span data-ttu-id="5dbfd-115">Décrit la classe **SoapException** dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dbfd-115">Describes the **SoapException** class in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5dbfd-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5dbfd-116">See Also</span></span>  
 [<span data-ttu-id="5dbfd-117">Création d’applications à l’aide du service web et du .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5dbfd-117">Building Applications Using the Web Service and the .NET Framework</span></span>](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md)  
  
  
