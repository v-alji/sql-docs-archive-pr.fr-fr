---
title: rsServerConfigurationError - Erreur Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- rsServerConfigurationError
ms.assetid: 0913afc2-34b4-4713-b570-cfd5718975ac
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 02f8a18c42715d1f118920614eb425820130dacb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706148"
---
# <a name="rsserverconfigurationerror---reporting-services-error"></a><span data-ttu-id="0cc92-102">rsServerConfigurationError - Erreur Reporting Services</span><span class="sxs-lookup"><span data-stu-id="0cc92-102">rsServerConfigurationError - Reporting Services Error</span></span>
    
## <a name="details"></a><span data-ttu-id="0cc92-103">Détails</span><span class="sxs-lookup"><span data-stu-id="0cc92-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0cc92-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="0cc92-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="0cc92-105">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="0cc92-105">Event ID</span></span>|<span data-ttu-id="0cc92-106">rsServerConfiguration</span><span class="sxs-lookup"><span data-stu-id="0cc92-106">rsServerConfiguration</span></span>|  
|<span data-ttu-id="0cc92-107">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="0cc92-107">Event Source</span></span>|<span data-ttu-id="0cc92-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span><span class="sxs-lookup"><span data-stu-id="0cc92-108">Microsoft.ReportingServices.Diagnostics.Utilities.ErrorStrings</span></span>|  
|<span data-ttu-id="0cc92-109">Composant</span><span class="sxs-lookup"><span data-stu-id="0cc92-109">Component</span></span>|[!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]|  
|<span data-ttu-id="0cc92-110">Texte du message</span><span class="sxs-lookup"><span data-stu-id="0cc92-110">Message Text</span></span>|<span data-ttu-id="0cc92-111">Le serveur de rapports a rencontré une erreur de configuration.</span><span class="sxs-lookup"><span data-stu-id="0cc92-111">The report server has encountered a configuration error.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0cc92-112">Explication</span><span class="sxs-lookup"><span data-stu-id="0cc92-112">Explanation</span></span>  
 <span data-ttu-id="0cc92-113">Ceci est une erreur à usage général qui se produit lorsque le serveur de rapports ou un outil de création de rapport a des paramètres de configuration non valides.</span><span class="sxs-lookup"><span data-stu-id="0cc92-113">This is a general purpose error that occurs when either the report server or a report authoring tool has invalid configuration settings.</span></span> <span data-ttu-id="0cc92-114">L'erreur est accompagnée habituellement d'un second message qui indique la cause réelle de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="0cc92-114">The error is usually accompanied by a second message that states the actual cause of the error.</span></span>  
  
 <span data-ttu-id="0cc92-115">La liste suivante résume les causes possibles :</span><span class="sxs-lookup"><span data-stu-id="0cc92-115">The following list summarizes possible causes:</span></span>  
  
-   <span data-ttu-id="0cc92-116">Le fichier RSReportServer.config ou RSReportDesigner.config est introuvable ou illisible.</span><span class="sxs-lookup"><span data-stu-id="0cc92-116">The RSReportServer.config or RSReportDesigner.config file cannot be found or read.</span></span>  
  
-   <span data-ttu-id="0cc92-117">Des éléments XML dans l'un des fichiers de configuration sont manquants ou non valides.</span><span class="sxs-lookup"><span data-stu-id="0cc92-117">XML elements in either configuration file are missing or invalid.</span></span>  
  
-   <span data-ttu-id="0cc92-118">Les valeurs d'un ou de plusieurs éléments XML sont manquantes ou non valides.</span><span class="sxs-lookup"><span data-stu-id="0cc92-118">Values for one or more XML elements are missing or invalid.</span></span>  
  
-   <span data-ttu-id="0cc92-119">Les paramètres du Registre ne sont pas valides.</span><span class="sxs-lookup"><span data-stu-id="0cc92-119">Registry settings are invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0cc92-120">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="0cc92-120">User Action</span></span>  
 <span data-ttu-id="0cc92-121">Si cette erreur a commencé à se produire après que vous avez modifié manuellement un fichier de configuration, supprimez vos modifications et entrez la valeur précédente, ou restaurez une version précédente si vous disposez d'une sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="0cc92-121">If this error began to occur after you manually edited a configuration file, remove your changes and enter the previous value, or restore a previous version if you have a backup.</span></span>  
  
 <span data-ttu-id="0cc92-122">Pour consulter des informations supplémentaires sur les messages d’erreur qui accompagnent l' `rsServerConfiguration` erreur, examinez les fichiers journaux de trace du serveur de rapports, qui se trouvent dans \Microsoft SQL Server\MSRS12. \<instancename > \Reporting Services\LogFiles.</span><span class="sxs-lookup"><span data-stu-id="0cc92-122">To review additional error message information that accompanies the `rsServerConfiguration` error, review the report server trace log files, which are located at \Microsoft SQL Server\MSRS12.\<instancename >\Reporting Services\LogFiles.</span></span> <span data-ttu-id="0cc92-123">Pour plus d’informations, consultez [Fichiers journaux et sources de Reporting Services](../report-server/reporting-services-log-files-and-sources.md).</span><span class="sxs-lookup"><span data-stu-id="0cc92-123">For more information, see [Reporting Services Log Files and Sources](../report-server/reporting-services-log-files-and-sources.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="0cc92-124">Interne uniquement</span><span class="sxs-lookup"><span data-stu-id="0cc92-124">Internal-Only</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc92-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0cc92-125">See Also</span></span>  
 <span data-ttu-id="0cc92-126">[Fichiers de configuration de Reporting Services](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="0cc92-126">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="0cc92-127">Modifier un fichier de configuration Reporting Services &#40;RSreportserver.config&#41;</span><span class="sxs-lookup"><span data-stu-id="0cc92-127">Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;</span></span>](../report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md)  
  
  
