---
title: Paramètres d’informations de périphérique ATOM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605267"
---
# <a name="atom-device-information-settings"></a><span data-ttu-id="4a949-102">Paramètres d'informations de périphérique ATOM</span><span class="sxs-lookup"><span data-stu-id="4a949-102">ATOM Device Information Settings</span></span>
  <span data-ttu-id="4a949-103">Les paramètres d'informations de périphériques pour l'extension de rendu Atom prennent en charge la soumission du nom d'un flux Atom et de l'encodage de caractères à utiliser.</span><span class="sxs-lookup"><span data-stu-id="4a949-103">The device information settings for the Atom rendering extension support submittal of the name of an Atom feed and character encoding to use.</span></span>  
  
 <span data-ttu-id="4a949-104">Le tableau suivant répertorie les paramètres des informations de périphériques pour le rendu dans un document de service de données.</span><span class="sxs-lookup"><span data-stu-id="4a949-104">The following table lists the device information settings for rendering to a data service document.</span></span>  
  
|<span data-ttu-id="4a949-105">Paramètre</span><span class="sxs-lookup"><span data-stu-id="4a949-105">Setting</span></span>|<span data-ttu-id="4a949-106">Valeur</span><span class="sxs-lookup"><span data-stu-id="4a949-106">Value</span></span>|  
|-------------|-----------|  
|`DataFeed`|<span data-ttu-id="4a949-107">Si spécifié, restitue le flux Atom correspondant au nom de flux fourni dans ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="4a949-107">If specified, renders the Atom feed corresponding to the feed name provided in this setting.</span></span> <span data-ttu-id="4a949-108">Dans le cas contraire, restitue le document de service Atom pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="4a949-108">If not, renders the Atom service document for the report.</span></span> <span data-ttu-id="4a949-109">Identificateur unique de la source de données générée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="4a949-109">The unique auto-generated identifier of the data feed.</span></span> <span data-ttu-id="4a949-110">Cette valeur est utilisée en interne et vous ne devez pas le modifier.</span><span class="sxs-lookup"><span data-stu-id="4a949-110">This  value is used internally and you should not change it.</span></span>|  
|<span data-ttu-id="4a949-111">**Encodage**</span><span class="sxs-lookup"><span data-stu-id="4a949-111">**Encoding**</span></span>|<span data-ttu-id="4a949-112">Nom IANA (Internet Assigned Numbers Authority) d'un encodage de caractères pris en charge par le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a949-112">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="4a949-113">La valeur par défaut est `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="4a949-113">The default value is `UTF-8`.</span></span> <span data-ttu-id="4a949-114">Les exemples d'autres valeurs incluent ASCII, UTF-7 et UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4a949-114">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4a949-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4a949-115">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="4a949-116">[Passage de paramètres d’informations de périphérique aux extensions de rendu](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="4a949-116">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="4a949-117">[Personnaliser les paramètres d’extension de rendu dans RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="4a949-117">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="4a949-118">Informations techniques de référence &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="4a949-118">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
