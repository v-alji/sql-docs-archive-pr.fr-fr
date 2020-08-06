---
title: Préparation pour la mise en œuvre d’une extension de remise | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- interfaces [Reporting Services]
- delivery extensions [Reporting Services], implementing
ms.assetid: aee1608d-374f-4ad3-bc23-fe07fdaa52b7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bbf98286e6ed35542d8117b4b87b5ff3425def69
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615038"
---
# <a name="preparing-to-implement-a-delivery-extension"></a><span data-ttu-id="e9434-102">Préparation à l'implémentation d'une extension de remise</span><span class="sxs-lookup"><span data-stu-id="e9434-102">Preparing to Implement a Delivery Extension</span></span>
  <span data-ttu-id="e9434-103">Avant d'implémenter votre extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)], vous devez définir les interfaces à implémenter.</span><span class="sxs-lookup"><span data-stu-id="e9434-103">Before you implement your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you should define the interfaces to implement.</span></span> <span data-ttu-id="e9434-104">Vous devez en premier décider de la manière dont votre extension de remise sera utilisée, quels paramètres votre extension de remise nécessite, et les fonctionnalités spécifiques à implémenter pour la remise des notifications de rapport.</span><span class="sxs-lookup"><span data-stu-id="e9434-104">You first need to decide how your delivery extension will be used, what settings your delivery extension will require, and the specific functionality you will need to implement in order to deliver report notifications.</span></span>  
  
 <span data-ttu-id="e9434-105">Chaque extension de remise [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] doit fournir les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="e9434-105">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension must provide the following functionality:</span></span>  
  
-   <span data-ttu-id="e9434-106">Une implémentation d'interface <xref:Microsoft.ReportingServices.Interfaces.IExtension> qui représente l'extension et un nom d'extension localisé.</span><span class="sxs-lookup"><span data-stu-id="e9434-106">An <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface implementation that represents the extension and a localized extension name.</span></span>  
  
-   <span data-ttu-id="e9434-107">Une implémentation <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> qui crée une extension de remise qui peut être utilisée pour remettre des notifications de rapport aux utilisateurs finaux.</span><span class="sxs-lookup"><span data-stu-id="e9434-107">An <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> implementation that creates a delivery extension that can be used to deliver report notifications to end users.</span></span>  
  
-   <span data-ttu-id="e9434-108">La capacité à traiter des données utilisateur spécifiques pour un abonnement.</span><span class="sxs-lookup"><span data-stu-id="e9434-108">The ability to process specific user data for a subscription.</span></span>  
  
 <span data-ttu-id="e9434-109">Chaque extension de remise peut être améliorée pour inclure les fonctionnalités suivantes :</span><span class="sxs-lookup"><span data-stu-id="e9434-109">Each delivery extension can be enhanced to include the following functionality:</span></span>  
  
-   <span data-ttu-id="e9434-110">Une implémentation du contrôle utilisateur [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] qui permet aux utilisateurs finaux d'utiliser le Gestionnaire de rapports pour créer des abonnements de rapport qui utilisent l'extension de remise.</span><span class="sxs-lookup"><span data-stu-id="e9434-110">An [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] user control implementation that enables end users to use Report Manager to create report subscriptions that use the delivery extension.</span></span>  
  
 <span data-ttu-id="e9434-111">Le tableau suivant décrit les interfaces et les classes disponibles pour les extensions de remise.</span><span class="sxs-lookup"><span data-stu-id="e9434-111">The following table describes the available interfaces and classes for delivery extensions.</span></span>  
  
|<span data-ttu-id="e9434-112">Interface ou classe</span><span class="sxs-lookup"><span data-stu-id="e9434-112">Interface or class</span></span>|<span data-ttu-id="e9434-113">Description</span><span class="sxs-lookup"><span data-stu-id="e9434-113">Description</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="e9434-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> .</span><span class="sxs-lookup"><span data-stu-id="e9434-114"><xref:Microsoft.ReportingServices.Interfaces.IExtension> Interface</span></span>|<span data-ttu-id="e9434-115">Représente une extension dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9434-115">Represents an extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="e9434-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> .</span><span class="sxs-lookup"><span data-stu-id="e9434-116"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> Interface</span></span>|<span data-ttu-id="e9434-117">Représente une extension de remise dans [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9434-117">Represents a delivery extension in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|<span data-ttu-id="e9434-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> .</span><span class="sxs-lookup"><span data-stu-id="e9434-118"><xref:Microsoft.ReportingServices.Interfaces.IDeliveryReportServerInformation> Interface</span></span>|<span data-ttu-id="e9434-119">Contient des informations relatives au serveur de rapports requises par les extensions de remise (par exemple, une liste des extensions de rendu disponibles).</span><span class="sxs-lookup"><span data-stu-id="e9434-119">Contains information about the report server that is required by delivery extensions (for example, a list of the available rendering extensions).</span></span>|  
|<span data-ttu-id="e9434-120">La classe <xref:Microsoft.ReportingServices.Interfaces.Setting></span><span class="sxs-lookup"><span data-stu-id="e9434-120"><xref:Microsoft.ReportingServices.Interfaces.Setting> Class</span></span>|<span data-ttu-id="e9434-121">Représente un paramètre pour une extension.</span><span class="sxs-lookup"><span data-stu-id="e9434-121">Represents a setting for an extension.</span></span>|  
|<span data-ttu-id="e9434-122">La classe <xref:Microsoft.ReportingServices.Interfaces.Notification></span><span class="sxs-lookup"><span data-stu-id="e9434-122"><xref:Microsoft.ReportingServices.Interfaces.Notification> Class</span></span>|<span data-ttu-id="e9434-123">Contient des informations d'abonnement que les extensions de remise utilisent pour remettre des rapports.</span><span class="sxs-lookup"><span data-stu-id="e9434-123">Contains subscription information that delivery extensions use to deliver reports.</span></span>|  
|<span data-ttu-id="e9434-124">La classe <xref:Microsoft.ReportingServices.Interfaces.Report></span><span class="sxs-lookup"><span data-stu-id="e9434-124"><xref:Microsoft.ReportingServices.Interfaces.Report> Class</span></span>|<span data-ttu-id="e9434-125">Représente des informations spécifiques aux rapports et méthodes qui permettent aux extensions de remise de remettre des rapports aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="e9434-125">Represents report-specific information and methods that enable delivery extensions to deliver reports to users.</span></span>|  
|<span data-ttu-id="e9434-126">La classe <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile></span><span class="sxs-lookup"><span data-stu-id="e9434-126"><xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> Class</span></span>|<span data-ttu-id="e9434-127">Représente la sortie d'une extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="e9434-127">Represents the output from a rendering extension.</span></span> <span data-ttu-id="e9434-128">Un objet <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> contient le nom de fichier associé et les informations de type requises par l'extension de remise afin de traiter le flux de données retourné par l'extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="e9434-128">A <xref:Microsoft.ReportingServices.Interfaces.RenderedOutputFile> object contains the associated file name and type information that is required by the delivery extension in order to process the stream returned by the rendering extension.</span></span>|  
|<span data-ttu-id="e9434-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> .</span><span class="sxs-lookup"><span data-stu-id="e9434-129"><xref:Microsoft.ReportingServices.Interfaces.ISubscriptionBaseUIUserControl> Interface</span></span>|<span data-ttu-id="e9434-130">Contrôle utilisateur qui représente les moyens d'extraire les informations d'abonnement spécifiques à l'extension de remise auprès de l'utilisateur dans le Gestionnaire de rapports (par exemple, une adresse de messagerie ou le chemin d'accès à un partage de fichiers).</span><span class="sxs-lookup"><span data-stu-id="e9434-130">A user control that represents the means to retrieve delivery extension-specific subscription information from the user in Report Manager (for example, an e-mail address or the path to a file share).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9434-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9434-131">See Also</span></span>  
 <span data-ttu-id="e9434-132">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="e9434-132">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="e9434-133">[Implémentation d’une extension de remise](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="e9434-133">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="e9434-134">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e9434-134">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
