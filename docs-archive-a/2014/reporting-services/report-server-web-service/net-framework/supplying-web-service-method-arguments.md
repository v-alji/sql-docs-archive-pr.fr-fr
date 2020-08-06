---
title: Spécification d’arguments de méthode de service web | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Report Server Web service, methods
- Web service [Reporting Services], methods
- methods [Reporting Services], arguments
- XML Web service [Reporting Services], methods
ms.assetid: f7b9ca05-fc4c-4b30-8e5d-172dd0f4a832
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3ef5188934628589751fe92d1839da0efb265766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707051"
---
# <a name="supplying-web-service-method-arguments"></a><span data-ttu-id="2e102-102">Spécification d'arguments de méthode de service Web</span><span class="sxs-lookup"><span data-stu-id="2e102-102">Supplying Web Service Method Arguments</span></span>
  <span data-ttu-id="2e102-103">Une méthode de service Web Report Server envoie une demande au service à une URL donnée à l'aide de SOAP sur HTTP.</span><span class="sxs-lookup"><span data-stu-id="2e102-103">A Report Server Web service method sends a request to the service at a given URL using SOAP over HTTP.</span></span> <span data-ttu-id="2e102-104">Le service reçoit la demande, la traite, puis renvoie une réponse.</span><span class="sxs-lookup"><span data-stu-id="2e102-104">The service receives the request, processes it, and then returns a response.</span></span> <span data-ttu-id="2e102-105">Ces demandes et réponses prennent la forme de documents XML.</span><span class="sxs-lookup"><span data-stu-id="2e102-105">These requests and responses are in the form of XML documents.</span></span>  
  
## <a name="optional-parameters"></a><span data-ttu-id="2e102-106">Paramètres facultatifs</span><span class="sxs-lookup"><span data-stu-id="2e102-106">Optional Parameters</span></span>  
 <span data-ttu-id="2e102-107">Dans certains cas, une méthode de service Web peut comporter des paramètres d'entrée facultatifs.</span><span class="sxs-lookup"><span data-stu-id="2e102-107">In some cases, a Web service method can have optional input parameters.</span></span> <span data-ttu-id="2e102-108">Quand bien même un paramètre d'entrée d'une méthode de service Web est facultatif, vous devez quand même l'inclure et lui affecter la valeur `null` (`Nothing` dans [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="2e102-108">Even if an input parameter for a Web service method is optional, you must still include it and set the parameter value to `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span> <span data-ttu-id="2e102-109">L'affectation de la valeur `null` à un paramètre permet d'affecter la valeur `null` à l'élément de ce paramètre dans la demande SOAP.</span><span class="sxs-lookup"><span data-stu-id="2e102-109">Setting a parameter value to `null` sets the element value for that parameter in the SOAP request to `null`.</span></span>  
  
 <span data-ttu-id="2e102-110">L'exemple suivant utilise la méthode <xref:ReportService2010.ReportingService2010.CreateFolder%2A> pour créer un dossier nommé Product Sales dans le dossier Sales.</span><span class="sxs-lookup"><span data-stu-id="2e102-110">The following example uses the <xref:ReportService2010.ReportingService2010.CreateFolder%2A> method to create a new folder named Product Sales in the Sales folder.</span></span> <span data-ttu-id="2e102-111">En spécifiant la valeur `null` pour les propriétés du dossier, aucune propriété propre à l'utilisateur n'est fournie pour le dossier :</span><span class="sxs-lookup"><span data-stu-id="2e102-111">By supplying a `null` value for the folder properties, no user-specific properties are supplied for the folder:</span></span>  
  
```  
// C#  
rs.CreateFolder("Product Sales", "/Sales", null);  
```  
  
## <a name="complex-data-types"></a><span data-ttu-id="2e102-112">Types de données complexes</span><span class="sxs-lookup"><span data-stu-id="2e102-112">Complex Data Types</span></span>  
 <span data-ttu-id="2e102-113">La classe principale du service Web Report Server est l'objet <xref:ReportService2010.ReportingService2010>, que vous utilisez pour appeler les opérations SOAP ou les méthodes Web de la classe proxy.</span><span class="sxs-lookup"><span data-stu-id="2e102-113">The core class of the Report Server Web service is <xref:ReportService2010.ReportingService2010>, which you use to invoke the SOAP operations or Web methods of the proxy class.</span></span> <span data-ttu-id="2e102-114">Pour prendre en charge cette classe et ses méthodes, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] inclut des types de données complexes et définis par l'utilisateur qui sont propres aux paramètres d'entrée et de sortie des méthodes de service Web.</span><span class="sxs-lookup"><span data-stu-id="2e102-114">To support this class and its methods, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes user-defined, complex data types that are specific to the input and output parameters of the Web service methods.</span></span> <span data-ttu-id="2e102-115">Ces types de données complexes font partie de la classe proxy générée, que vous pouvez utiliser lors du développement dans l' [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environnement.</span><span class="sxs-lookup"><span data-stu-id="2e102-115">These complex data types are part of the generated proxy class, which you can use when developing in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] environment.</span></span>  
  
 <span data-ttu-id="2e102-116">Lorsque vous générez une classe proxy, les types de données complexes définis dans le fichier WSDL sont représentés par les classes du proxy, qui incluent des propriétés qui correspondent aux divers éléments SOAP des types de données complexes.</span><span class="sxs-lookup"><span data-stu-id="2e102-116">When you generate a proxy class, the complex data types that are defined in the WSDL file are represented by the classes of the proxy, which include properties that correspond to the various SOAP elements of the complex data types.</span></span> <span data-ttu-id="2e102-117">Les séquences de ces types de données deviennent des tableaux d'objets que vous pouvez énumérer dans votre code.</span><span class="sxs-lookup"><span data-stu-id="2e102-117">Sequences of these data types become arrays of objects that you can enumerate through in your code.</span></span> <span data-ttu-id="2e102-118">Cela élimine le besoin d'utiliser directement les structures XML envoyées dans les messages SOAP.</span><span class="sxs-lookup"><span data-stu-id="2e102-118">This eliminates the need to work directly with the XML structures sent in SOAP messages.</span></span> <span data-ttu-id="2e102-119">Le [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] gère cette traduction à votre place.</span><span class="sxs-lookup"><span data-stu-id="2e102-119">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] handles that translation for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e102-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e102-120">See Also</span></span>  
 <span data-ttu-id="2e102-121">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="2e102-121">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 <span data-ttu-id="2e102-122">[Service web Report Server](../report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="2e102-122">[Report Server Web Service](../report-server-web-service.md) </span></span>  
 [<span data-ttu-id="2e102-123">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2e102-123">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
