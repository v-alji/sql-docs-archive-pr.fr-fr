---
title: Utilisation des méthodes de service web sécurisées | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- SOAP [Reporting Services], secure connections
- Web service [Reporting Services], SOAP
- Report Server Web service, SOAP
- XML Web service [Reporting Services], SOAP
ms.assetid: 87329299-c2ea-4517-9148-d855726768a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: e88a164602f9bbe6ad42c3897285a484cac94466
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707055"
---
# <a name="using-secure-web-service-methods"></a><span data-ttu-id="3045d-102">Utilisation des méthodes de service Web sécurisées</span><span class="sxs-lookup"><span data-stu-id="3045d-102">Using Secure Web Service Methods</span></span>
  <span data-ttu-id="3045d-103">Certaines méthodes de service Web Report Server peuvent requérir une connexion sécurisée lorsque vous les appelez.</span><span class="sxs-lookup"><span data-stu-id="3045d-103">Certain Report Server Web service methods may require a secure connection when you invoke them.</span></span> <span data-ttu-id="3045d-104">Ces méthodes sont déterminées par le paramètre `SecureConnectionLevel` dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="3045d-104">The methods that require a secure connection are determined by the `SecureConnectionLevel` setting in the RSReportServer.config file.</span></span> <span data-ttu-id="3045d-105">La valeur du paramètre est une valeur entière avec une plage valide supérieure ou égale à 0.</span><span class="sxs-lookup"><span data-stu-id="3045d-105">The value of the setting is an integer value with a valid range of 0 and higher.</span></span> <span data-ttu-id="3045d-106">Le tableau suivant décrit ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="3045d-106">The following table describes these values.</span></span>  
  
|<span data-ttu-id="3045d-107">Level</span><span class="sxs-lookup"><span data-stu-id="3045d-107">Level</span></span>|<span data-ttu-id="3045d-108">Description</span><span class="sxs-lookup"><span data-stu-id="3045d-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3045d-109">**0**</span><span class="sxs-lookup"><span data-stu-id="3045d-109">**0**</span></span>|<span data-ttu-id="3045d-110">Non sécurisé.</span><span class="sxs-lookup"><span data-stu-id="3045d-110">Not secure.</span></span> <span data-ttu-id="3045d-111">Les appels effectués auprès de l'API SOAP de Reporting Services ne requièrent pas de connexion sécurisée.</span><span class="sxs-lookup"><span data-stu-id="3045d-111">Calls made to the Reporting Services SOAP API do not require a secure connection.</span></span>|  
|<span data-ttu-id="3045d-112">Supérieur à **0**</span><span class="sxs-lookup"><span data-stu-id="3045d-112">Greater than **0**</span></span>|<span data-ttu-id="3045d-113">Sécurisé.</span><span class="sxs-lookup"><span data-stu-id="3045d-113">Secure.</span></span> <span data-ttu-id="3045d-114">Les appels effectués auprès de l'API SOAP de Reporting Services requièrent une connexion sécurisée.</span><span class="sxs-lookup"><span data-stu-id="3045d-114">All calls made to the Reporting Services SOAP API require a secure connection.</span></span>|  
  
 <span data-ttu-id="3045d-115">Vous pouvez utiliser la méthode <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> du service Web pour renvoyer une liste des méthodes de service Web qui requièrent une connexion sécurisée d'après la configuration actuelle du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="3045d-115">You can use the <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> method of the Web service to return a list of Web service methods that require a secure connection according to the current configuration of the report server.</span></span> <span data-ttu-id="3045d-116">Dans un scénario SSL, vous devez évaluer la liste des méthodes qui sont renvoyées par <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> et remplacer le nom de méthode de l'URI de service Web par "https" ou "http" selon la méthode appelée.</span><span class="sxs-lookup"><span data-stu-id="3045d-116">In an SSL scenario, you should evaluate the list of methods that are returned by <xref:ReportExecution2005.ReportExecutionService.ListSecureMethods%2A> and change the scheme name of the Web service URI to "https" or "http" depending on the method being called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3045d-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3045d-117">See Also</span></span>  
 <span data-ttu-id="3045d-118">[Création d’applications à l’aide du service web et du .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="3045d-118">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="3045d-119">Service Web des serveurs de rapports</span><span class="sxs-lookup"><span data-stu-id="3045d-119">Report Server Web Service</span></span>](../report-server-web-service.md)  
  
  
