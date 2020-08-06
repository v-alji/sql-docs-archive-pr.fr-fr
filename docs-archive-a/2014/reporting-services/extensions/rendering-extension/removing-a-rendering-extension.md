---
title: Suppression d’une extension de rendu | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- deleting rendering extensions
- removing rendering extensions
- rendering extensions [Reporting Services], removing
ms.assetid: 2abfebfb-065f-45cc-a904-c914394cf900
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 77a8a9ac44b35f338f978913985617e4f264ddb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610484"
---
# <a name="removing-a-rendering-extension"></a><span data-ttu-id="cdd29-102">Suppression d'une extension de rendu</span><span class="sxs-lookup"><span data-stu-id="cdd29-102">Removing a Rendering Extension</span></span>
  <span data-ttu-id="cdd29-103">Pour supprimer une [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] extension de rendu, supprimez simplement l' `Extension` élément pour votre extension de rendu du fichier rsreportserver.config, situé dans **%programfiles%\microsoft SQL Server \ MSRS10_50. \<Instance Name> Dossier \Reporting Services\ReportServer** .</span><span class="sxs-lookup"><span data-stu-id="cdd29-103">To remove a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] rendering extension, simply remove the `Extension` element for your rendering extension from the rsreportserver.config file, located in **%ProgramFiles%\Microsoft SQL Server\MSRS10_50.\<Instance Name>\Reporting Services\ReportServer** folder.</span></span> <span data-ttu-id="cdd29-104">Si vous avez créé des entrées pour un Concepteur de rapports, ainsi qu’un serveur de rapports, supprimez `Extension` également l’élément du [fichier de configuration RSReportDesigner](../../report-server/rsreportdesigner-configuration-file.md) .</span><span class="sxs-lookup"><span data-stu-id="cdd29-104">If you made entries for a Report Designer as well as a report server, remove the `Extension` element from the [RSReportDesigner Configuration File](../../report-server/rsreportdesigner-configuration-file.md) as well.</span></span> <span data-ttu-id="cdd29-105">Une fois les informations de configuration supprimées, l'extension de rendu n'est plus accessible au composant.</span><span class="sxs-lookup"><span data-stu-id="cdd29-105">After the configuration information is removed, the rendering extension is no longer available to the component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd29-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cdd29-106">See Also</span></span>  
 <span data-ttu-id="cdd29-107">[Fichiers de configuration de Reporting Services](../../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="cdd29-107">[Reporting Services Configuration Files](../../report-server/reporting-services-configuration-files.md) </span></span>  
 <span data-ttu-id="cdd29-108">[Implémentation d’une extension de rendu](implementing-a-rendering-extension.md) </span><span class="sxs-lookup"><span data-stu-id="cdd29-108">[Implementing a Rendering Extension](implementing-a-rendering-extension.md) </span></span>  
 <span data-ttu-id="cdd29-109">[Vue d’ensemble des extensions de rendu](rendering-extensions-overview.md) </span><span class="sxs-lookup"><span data-stu-id="cdd29-109">[Rendering Extensions Overview](rendering-extensions-overview.md) </span></span>  
 <span data-ttu-id="cdd29-110">[Mise en œuvre de l’interface IRenderingExtension](implementing-the-irenderingextension-interface.md) </span><span class="sxs-lookup"><span data-stu-id="cdd29-110">[Implementing the IRenderingExtension Interface](implementing-the-irenderingextension-interface.md) </span></span>  
 <span data-ttu-id="cdd29-111">[Considérations sur la sécurité pour les extensions](../security-considerations-for-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="cdd29-111">[Security Considerations for Extensions](../security-considerations-for-extensions.md) </span></span>  
 [<span data-ttu-id="cdd29-112">Déploiement d'une extension de rendu</span><span class="sxs-lookup"><span data-stu-id="cdd29-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
  
  
