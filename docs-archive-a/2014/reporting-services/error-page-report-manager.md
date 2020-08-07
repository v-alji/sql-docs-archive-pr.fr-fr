---
title: Page d’erreur (Gestionnaire de rapports) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8311ed32-00f3-451d-8279-946429f5fee1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fc50a5b0516bcbf8221ce3ee130090f66a929c3e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703884"
---
# <a name="error-page-report-manager"></a><span data-ttu-id="41d39-102">Page Erreur (Gestionnaire de rapports)</span><span class="sxs-lookup"><span data-stu-id="41d39-102">Error Page (Report Manager)</span></span>
  <span data-ttu-id="41d39-103">La page Erreur vous permet d'afficher des informations détaillées sur une condition d'erreur.</span><span class="sxs-lookup"><span data-stu-id="41d39-103">Use the Error page to view details about an error condition.</span></span> <span data-ttu-id="41d39-104">Les erreurs basées sur un serveur ou une session s’affichent sur cette page.</span><span class="sxs-lookup"><span data-stu-id="41d39-104">Server-based or session-based errors appear on this page.</span></span> <span data-ttu-id="41d39-105">Les erreurs de validation qui sont liées à des contrôles de page s'affichent en ligne en regard du contrôle.</span><span class="sxs-lookup"><span data-stu-id="41d39-105">Validation errors that relate to specific page controls display inline next to the control.</span></span>  
  
-   <span data-ttu-id="41d39-106">Si vous accédez à un serveur de rapports local et que vous constatez des erreurs similaires à ce qui suit, consultez : [configurer un serveur de rapports en mode natif pour l’administration locale &#40;SSRS&#41;](report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md)</span><span class="sxs-lookup"><span data-stu-id="41d39-106">If you are browsing to a local report server and you see errors similar to the following, see: [Configure a Native Mode Report Server for Local Administration &#40;SSRS&#41;](report-server/configure-a-native-mode-report-server-for-local-administration-ssrs.md)</span></span>  
  
     <span data-ttu-id="41d39-107">L’utilisateur « domaine \\ [nom d’utilisateur] » ne dispose pas des autorisations requises.</span><span class="sxs-lookup"><span data-stu-id="41d39-107">User 'Domain\\[user name]' does not have required permissions.</span></span> <span data-ttu-id="41d39-108">Vérifiez que les autorisations suffisantes ont été accordées et qu'aucune restriction liée au contrôle de compte d'utilisateur (UAC) Windows ne pose problème.</span><span class="sxs-lookup"><span data-stu-id="41d39-108">Verify that sufficient permissions have been granted and Windows User Account Control (UAC) restrictions have been addressed.</span></span>  
  
-   <span data-ttu-id="41d39-109">Si un message d'erreur semblable aux suivants s'affiche, consultez [Configure a Report Server for Remote Administration](report-server/configure-a-report-server-for-remote-administration.md).</span><span class="sxs-lookup"><span data-stu-id="41d39-109">If you see error messages similar to the following, see [Configure a Report Server for Remote Administration](report-server/configure-a-report-server-for-remote-administration.md).</span></span>  
  
     <span data-ttu-id="41d39-110">Ordinateur introuvable.</span><span class="sxs-lookup"><span data-stu-id="41d39-110">The machine could not be found.</span></span> <span data-ttu-id="41d39-111">« Le serveur RPC n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="41d39-111">"The RPC server is unavailable.</span></span> <span data-ttu-id="41d39-112">(Exception de HRESULT : 0x800706BA) ».</span><span class="sxs-lookup"><span data-stu-id="41d39-112">(Exception from HRESULT: 0x800706BA)".</span></span>  
  
-   <span data-ttu-id="41d39-113">Vous pouvez définir des propriétés de serveur sur un serveur de rapports [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] de façon à retourner des informations supplémentaires concernant les conditions d'erreur qui se produisent sur des serveurs distants.</span><span class="sxs-lookup"><span data-stu-id="41d39-113">You can set server properties on a [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] report server to return additional information about error conditions that occur on remote servers.</span></span> <span data-ttu-id="41d39-114">Si un message d’erreur contient le texte « pour plus d’informations sur cette erreur, accédez au serveur de rapports sur le serveur local ou activez les erreurs distantes », consultez [activer les erreurs Distantes &#40;Reporting Services&#41;](report-server/enable-remote-errors-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="41d39-114">If an error message contains the text "For more information about this error, navigate to the report server on the local server machine, or enable remote errors", see [Enable Remote Errors &#40;Reporting Services&#41;](report-server/enable-remote-errors-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d39-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="41d39-115">See Also</span></span>  
 <span data-ttu-id="41d39-116">[Configurer Gestionnaire de rapports mode natif &#40;&#41;](report-server/configure-web-portal.md) </span><span class="sxs-lookup"><span data-stu-id="41d39-116">[Configure Report Manager &#40;Native Mode&#41;](report-server/configure-web-portal.md) </span></span>  
 <span data-ttu-id="41d39-117">[Informations de référence sur les erreurs et les événements &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="41d39-117">[Errors and Events Reference &#40;Reporting Services&#41;](troubleshooting/errors-and-events-reference-reporting-services.md) </span></span>  
 [<span data-ttu-id="41d39-118">Aide F1 du Gestionnaire de rapports</span><span class="sxs-lookup"><span data-stu-id="41d39-118">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
