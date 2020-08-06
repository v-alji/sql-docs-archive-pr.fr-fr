---
title: Nouveautés de&#39;(Integration Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, what's new
- what's new [Integration Services]
ms.assetid: da6999c7-e5e3-4a59-a284-1da635995af1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 84f0b668407c89e1d6acc3c8cfbda73f129ca19a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613516"
---
# <a name="what39s-new-integration-services"></a><span data-ttu-id="1219b-102">Nouveautés de&#39;(Integration Services)</span><span class="sxs-lookup"><span data-stu-id="1219b-102">What&#39;s New (Integration Services)</span></span>
  [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]<span data-ttu-id="1219b-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]n’est pas modifié à partir de la version précédente.</span><span class="sxs-lookup"><span data-stu-id="1219b-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] is unchanged from the previous release.</span></span>  
  
 <span data-ttu-id="1219b-104">Pour plus d’informations sur les autres [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] produits et technologies, consultez [nouveautés de SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="1219b-104">For information about other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
 <span data-ttu-id="1219b-105">Pour plus d’informations sur les modifications associées à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, consultez [nouveautés de Analysis Services et Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span><span class="sxs-lookup"><span data-stu-id="1219b-105">For more information about changes related to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Business Intelligence, see [What's New in Analysis Services and Business Intelligence](https://docs.microsoft.com/analysis-services/what-s-new-in-analysis-services).</span></span>  
  
##  <a name="rich-xml-validation-output-in-the-xml-task"></a><a name="ValidateXML"></a> <span data-ttu-id="1219b-106">Sortie de validation XML détaillée dans la tâche XML</span><span class="sxs-lookup"><span data-stu-id="1219b-106">Rich XML validation output in the XML Task</span></span>  
 <span data-ttu-id="1219b-107">Validez des documents XML et obtenez une sortie d’erreur détaillée en activant la propriété `ValidationDetails` de la tâche XML.</span><span class="sxs-lookup"><span data-stu-id="1219b-107">Validate XML documents and get rich error output by enabling the `ValidationDetails` property of the XML Task.</span></span> <span data-ttu-id="1219b-108">Avant que la propriété `ValidationDetails` ne soit disponible, la validation XML par la tâche XML ne renvoyait qu’un résultat true ou false, sans aucune information sur les erreurs ou leur emplacement.</span><span class="sxs-lookup"><span data-stu-id="1219b-108">Before the `ValidationDetails` property was available, XML validation by the XML Task returned only a true or false result, with no information about errors or their locations.</span></span> <span data-ttu-id="1219b-109">À présent, quand vous définissez `ValidationDetails` sur true, le fichier de sortie contient des informations détaillées sur chaque erreur, notamment le numéro de ligne et la position.</span><span class="sxs-lookup"><span data-stu-id="1219b-109">Now, when you set `ValidationDetails` to true, the output file contains detailed information about every error including the line number and the position.</span></span> <span data-ttu-id="1219b-110">Vous pouvez utiliser ces informations pour comprendre, localiser et corriger les erreurs dans les documents XML.</span><span class="sxs-lookup"><span data-stu-id="1219b-110">You can use this information to understand, locate, and fix errors in XML documents.</span></span> <span data-ttu-id="1219b-111">Pour plus d’informations, consultez [Validate XML with the XML Task](control-flow/xml-task.md).</span><span class="sxs-lookup"><span data-stu-id="1219b-111">For more info, see [Validate XML with the XML Task](control-flow/xml-task.md).</span></span>  
  
 [!INCLUDE[ssIS](../includes/ssis-md.md)] <span data-ttu-id="1219b-112">a introduit la propriété `ValidationDetails` dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span><span class="sxs-lookup"><span data-stu-id="1219b-112">introduced the `ValidationDetails` property in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Service Pack 2.</span></span> <span data-ttu-id="1219b-113">Cette nouvelle propriété n’a pas été annoncée ou documentée à ce moment-là.</span><span class="sxs-lookup"><span data-stu-id="1219b-113">This new property was not announced or documented at that time.</span></span> <span data-ttu-id="1219b-114">La propriété `ValidationDetails` est également disponible dans [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] et dans SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="1219b-114">The `ValidationDetails` property is also available in [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] and in SQL Server 2016.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1219b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1219b-115">See Also</span></span>  
 [<span data-ttu-id="1219b-116">Fonctionnalités prises en charge par les éditions de SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="1219b-116">Features Supported by the Editions of SQL Server 2014</span></span>](../getting-started/features-supported-by-the-editions-of-sql-server-2014.md)  
  
  
