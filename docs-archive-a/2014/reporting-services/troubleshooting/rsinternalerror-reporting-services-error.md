---
title: rsInternalError - Erreur Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsInternalError
ms.assetid: 52613d52-fc78-4870-93f0-7d393ab9c335
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 85b88519df810f60c580ad2d6eb355dde236d081
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605909"
---
# <a name="rsinternalerror---reporting-services-error"></a><span data-ttu-id="8d35e-102">rsInternalError - Erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="8d35e-102">rsInternalError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="8d35e-103">Détails</span><span class="sxs-lookup"><span data-stu-id="8d35e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d35e-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="8d35e-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="8d35e-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="8d35e-105">Event ID</span></span>|<span data-ttu-id="8d35e-106">rsInternalError</span><span class="sxs-lookup"><span data-stu-id="8d35e-106">rsInternalError</span></span>|  
|<span data-ttu-id="8d35e-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="8d35e-107">Event Source</span></span>|<span data-ttu-id="8d35e-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="8d35e-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="8d35e-109">Composant</span><span class="sxs-lookup"><span data-stu-id="8d35e-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="8d35e-110">Texte du message</span><span class="sxs-lookup"><span data-stu-id="8d35e-110">Message Text</span></span>|<span data-ttu-id="8d35e-111">Une erreur interne s'est produite sur le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8d35e-111">An internal error occurred on the report server.</span></span> <span data-ttu-id="8d35e-112">Consultez le journal des erreurs pour plus d'informations.</span><span class="sxs-lookup"><span data-stu-id="8d35e-112">See the error log for more details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="8d35e-113">Explication</span><span class="sxs-lookup"><span data-stu-id="8d35e-113">Explanation</span></span>  
 <span data-ttu-id="8d35e-114">Il s'agit d'un message d'erreur générique qui est souvent suivi par un autre message plus descriptif fournissant des informations détaillées.</span><span class="sxs-lookup"><span data-stu-id="8d35e-114">This is a generic error message that is often followed by a more descriptive error that provides more detail.</span></span>  
  
 <span data-ttu-id="8d35e-115">Les erreurs internes sont rares.</span><span class="sxs-lookup"><span data-stu-id="8d35e-115">Internal errors are uncommon.</span></span> <span data-ttu-id="8d35e-116">Si vous recevez ce message, des informations supplémentaires sont disponibles dans les journaux des traces du serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="8d35e-116">If you get this error, more information is available in report server trace logs.</span></span> <span data-ttu-id="8d35e-117">En outre, si vous êtes connecté en tant qu'administrateur local sur l'ordinateur sur lequel l'erreur s'est produite, vous pouvez afficher la pile des appels pour avoir accès à des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="8d35e-117">In addition, if you are running as local administrator on the same computer on which the error occurs, you can view the call stack for more information.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d35e-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="8d35e-118">User Action</span></span>  
 <span data-ttu-id="8d35e-119">Pour déterminer la cause spécifique de ce message, passez en revue les fichiers journaux du serveur de rapports, qui se trouvent dans \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="8d35e-119">To determine the specific cause for this message, review the report server log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="8d35e-120">Pour plus d’informations, consultez [Fichiers journaux et sources de Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="8d35e-120">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
 <span data-ttu-id="8d35e-121">Pour afficher la pile des appels, cliquez avec le bouton droit sur la page sur laquelle l’erreur s’est produite et pointez sur **Afficher la source**.</span><span class="sxs-lookup"><span data-stu-id="8d35e-121">To view the call stack, right-click the page on which the error occurs and point to **View Source**.</span></span> <span data-ttu-id="8d35e-122">La consultation de la pile des appels requiert des autorisations d'administrateur sur l'ordinateur où l'erreur s'est produite.</span><span class="sxs-lookup"><span data-stu-id="8d35e-122">Viewing the call stack requires administrator permissions on the same computer on which the error occurs.</span></span>  
  
 <span data-ttu-id="8d35e-123">Si aucune information supplémentaire n'est disponible, vous pouvez réessayer votre demande.</span><span class="sxs-lookup"><span data-stu-id="8d35e-123">If there is no additional information available, you can try your request again.</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="8d35e-124">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="8d35e-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d35e-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d35e-125">See Also</span></span>  
 [<span data-ttu-id="8d35e-126">Démarrer et arrêter le service du serveur de rapports</span><span class="sxs-lookup"><span data-stu-id="8d35e-126">Start and Stop the Report Server Service</span></span>](../report-server/start-and-stop-the-report-server-service.md)  
  
  
