---
title: Bonnes pratiques pour la gestion des exceptions dans Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e0561c19fbd3e709a0440a55f023f938eabf692
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604385"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a><span data-ttu-id="df880-102">Meilleures pratiques pour la gestion des exceptions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="df880-102">Best Practices for Reporting Services Exception Handling</span></span>
  <span data-ttu-id="df880-103">Lors du développement d'applications [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vous disposez de plusieurs méthodologies pour supprimer ou réduire les exceptions.</span><span class="sxs-lookup"><span data-stu-id="df880-103">When developing [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] applications, there are several methodologies you can use to eliminate or reduce the occurrence of exceptions.</span></span> <span data-ttu-id="df880-104">En cas d'exceptions, fournissez des informations claires et concises à l'utilisateur sous la forme de messages d'erreur, et prévoyez une gestion adéquate des exceptions pour empêcher vos applications de se terminer de façon inattendue.</span><span class="sxs-lookup"><span data-stu-id="df880-104">When exceptions do occur, provide clear and concise error messages to the user, and add adequate exception handling to prevent your applications from ending unexpectedly.</span></span>  
  
 <span data-ttu-id="df880-105">Une application qui envoie des demandes au service Web Report Server doit effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="df880-105">An application that sends requests to the Report Server Web service should do the following:</span></span>  
  
-   <span data-ttu-id="df880-106">Éviter de provoquer des exceptions en empêchant le plus grand nombre possible de demandes non valides.</span><span class="sxs-lookup"><span data-stu-id="df880-106">Avoid causing exceptions by preventing as many invalid requests as possible.</span></span>  
  
-   <span data-ttu-id="df880-107">Intercepter des exceptions et fournir le code spécifique de gestion des erreurs autant que possible.</span><span class="sxs-lookup"><span data-stu-id="df880-107">Catch exceptions and provide specific error-handling code whenever possible.</span></span>  
  
-   <span data-ttu-id="df880-108">Traiter les cas d'erreur qui ne lèvent pas d'exceptions.</span><span class="sxs-lookup"><span data-stu-id="df880-108">Deal with error cases that do not throw exceptions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="df880-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="df880-109">In This Section</span></span>  
  
|<span data-ttu-id="df880-110">Rubrique</span><span class="sxs-lookup"><span data-stu-id="df880-110">Topic</span></span>|<span data-ttu-id="df880-111">Description</span><span class="sxs-lookup"><span data-stu-id="df880-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="df880-112">Éviter les demandes non valides</span><span class="sxs-lookup"><span data-stu-id="df880-112">Preventing Invalid Requests</span></span>](preventing-invalid-requests.md)|<span data-ttu-id="df880-113">Décrit des techniques pour empêcher l'envoi au serveur de rapports de demandes qui ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="df880-113">Describes techniques for preventing requests that are not valid from being sent to the report server.</span></span>|  
|[<span data-ttu-id="df880-114">Utilisation des blocs Try et Catch</span><span class="sxs-lookup"><span data-stu-id="df880-114">Using Try and Catch Blocks</span></span>](using-try-and-catch-blocks.md)|<span data-ttu-id="df880-115">Décrit comment améliorer la fiabilité de votre application à l'aide des blocs try et catch.</span><span class="sxs-lookup"><span data-stu-id="df880-115">Describes how to further enhance the reliability of your application with try/catch blocks.</span></span>|  
|[<span data-ttu-id="df880-116">Gestion des avertissements et des erreurs qui ne lèvent pas d'exceptions</span><span class="sxs-lookup"><span data-stu-id="df880-116">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|<span data-ttu-id="df880-117">Explique comment gérer des erreurs qui ne provoquent pas la levée d'une exception par [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df880-117">Explains how to handle errors that do not result in an exception being thrown by [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="df880-118">Utilisation de la propriété Detail pour gérer des erreurs spécifiques</span><span class="sxs-lookup"><span data-stu-id="df880-118">Using the Detail Property to Handle Specific Errors</span></span>](using-the-detail-property-to-handle-specific-errors.md)|<span data-ttu-id="df880-119">Explique comment gérer par programmation des erreurs spécifiques en utilisant la propriété **Detail** de l’objet **SoapException**.</span><span class="sxs-lookup"><span data-stu-id="df880-119">Explains how to programmatically handle specific errors by using the **Detail** property of the **SoapException** object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df880-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="df880-120">See Also</span></span>  
 <span data-ttu-id="df880-121">[Detail, propriété](../soapexception-class/detail-property.md) </span><span class="sxs-lookup"><span data-stu-id="df880-121">[Detail Property](../soapexception-class/detail-property.md) </span></span>  
 <span data-ttu-id="df880-122">[Présentation de la gestion des exceptions dans Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="df880-122">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="df880-123">Classe SoapException Reporting Services</span><span class="sxs-lookup"><span data-stu-id="df880-123">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
