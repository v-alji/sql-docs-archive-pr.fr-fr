---
title: Utilisation des en-têtes SOAP Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- SOAP headers [Reporting Services]
- SOAP [Reporting Services], headers
- XML Web service [Reporting Services], SOAP
ms.assetid: 306d2c06-a25a-40f8-8a35-13dd32e8841e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f48be183398d4d441b5781c9f9467178c3011e32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702388"
---
# <a name="using-reporting-services-soap-headers"></a><span data-ttu-id="2ef57-102">Utilisation des en-têtes SOAP de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="2ef57-102">Using Reporting Services SOAP Headers</span></span>
  <span data-ttu-id="2ef57-103">La communication avec une méthode Web Service à l'aide de SOAP suit un format standard.</span><span class="sxs-lookup"><span data-stu-id="2ef57-103">Communication with a Web service method using SOAP follows a standard format.</span></span> <span data-ttu-id="2ef57-104">Ce format est constitué en partie des données encodées dans un document XML.</span><span class="sxs-lookup"><span data-stu-id="2ef57-104">Part of this format is the data that is encoded in an XML document.</span></span> <span data-ttu-id="2ef57-105">Le document XML consiste en un élément **Envelope** racine, composé lui-même d’un élément **Body** obligatoire et d’un élément **Header** facultatif.</span><span class="sxs-lookup"><span data-stu-id="2ef57-105">The XML document consists of a root **Envelope** element, which in turn consists of a required **Body** element and an optional **Header** element.</span></span> <span data-ttu-id="2ef57-106">L’élément **Body** contient les données propres au message.</span><span class="sxs-lookup"><span data-stu-id="2ef57-106">The **Body** element contains the data specific to the message.</span></span> <span data-ttu-id="2ef57-107">L’élément **Header** facultatif peut contenir des informations supplémentaires qui ne sont pas directement liées au message.</span><span class="sxs-lookup"><span data-stu-id="2ef57-107">The optional **Header** element can contain additional information not directly related to the particular message.</span></span> <span data-ttu-id="2ef57-108">Chaque élément enfant de l’élément **Header** est appelé « en-tête SOAP ».</span><span class="sxs-lookup"><span data-stu-id="2ef57-108">Each child element of the **Header** element is called a SOAP header.</span></span>  
  
 <span data-ttu-id="2ef57-109">Bien que les en-têtes SOAP puissent contenir des données en rapport avec le message, ils contiennent en général des informations traitées par l'infrastructure du serveur Web.</span><span class="sxs-lookup"><span data-stu-id="2ef57-109">Although the SOAP headers can contain data related to the message, they typically contain information processed by the Web server infrastructure.</span></span>  
  
 <span data-ttu-id="2ef57-110">Les services Web Report Server définissent plusieurs classes à utiliser dans l'en-tête SOAP : <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader> et <xref:ReportExecution2005.ExecutionHeader>.</span><span class="sxs-lookup"><span data-stu-id="2ef57-110">The Report Server Web services define several classes for use in the SOAP header: <xref:ReportService2005.BatchHeader>, <xref:ReportService2010.ItemNamespaceHeader>, <xref:ReportService2010.ServerInfoHeader>, <xref:ReportService2010.TrustedUserHeader>, and <xref:ReportExecution2005.ExecutionHeader>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ef57-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="2ef57-111">In This Section</span></span>  
  
|<span data-ttu-id="2ef57-112">Rubrique</span><span class="sxs-lookup"><span data-stu-id="2ef57-112">Topic</span></span>|<span data-ttu-id="2ef57-113">Description</span><span class="sxs-lookup"><span data-stu-id="2ef57-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2ef57-114">Méthodes de traitement par lot</span><span class="sxs-lookup"><span data-stu-id="2ef57-114">Batching Methods</span></span>](batching-methods.md)|<span data-ttu-id="2ef57-115">Décrit comment traiter en lot plusieurs opérations dans une transaction unique à l'aide de <xref:ReportService2005.BatchHeader>.</span><span class="sxs-lookup"><span data-stu-id="2ef57-115">Describes how to batch multiple operations into a single transaction using <xref:ReportService2005.BatchHeader>.</span></span>|  
|[<span data-ttu-id="2ef57-116">Identification de l'état d'exécution</span><span class="sxs-lookup"><span data-stu-id="2ef57-116">Identifying Execution State</span></span>](identifying-execution-state.md)|<span data-ttu-id="2ef57-117">Explique comment gérer l’état de session dans [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] à l’aide de **SessionHeader**.</span><span class="sxs-lookup"><span data-stu-id="2ef57-117">Describes how to manage session state in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] using **SessionHeader**.</span></span>|  
|[<span data-ttu-id="2ef57-118">Définition de l'espace de noms d'élément pour la méthode GetProperties</span><span class="sxs-lookup"><span data-stu-id="2ef57-118">Setting the Item Namespace for the GetProperties Method</span></span>](setting-the-item-namespace-for-the-getproperties-method.md)|<span data-ttu-id="2ef57-119">Décrit comment extraire des propriétés selon le chemin d'accès ou l'ID d'un élément, en utilisant la méthode <xref:ReportService2010.ReportingService2010.GetProperties%2A> et l'en-tête SOAP <xref:ReportService2010.ItemNamespaceHeader>.</span><span class="sxs-lookup"><span data-stu-id="2ef57-119">Describes how to retrieve properties based on either the path or the ID of an item by using the <xref:ReportService2010.ReportingService2010.GetProperties%2A> method and the <xref:ReportService2010.ItemNamespaceHeader> SOAP header.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2ef57-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2ef57-120">See Also</span></span>  
 <span data-ttu-id="2ef57-121">[Création d’applications à l’aide du service web et du .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="2ef57-121">[Building Applications Using the Web Service and the .NET Framework](../report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="2ef57-122">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="2ef57-122">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
