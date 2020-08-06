---
title: Écrire des scripts avec l’utilitaire rs.exe et le service web | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Web service [Reporting Services], scripts
- rs utility
- XML Web service [Reporting Services], scripts
- Report Server Web service, scripts
- scripts [Reporting Services], Web service
ms.assetid: 0ec5ac6e-b3cf-49cd-96f6-6b4b7dc29982
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 9d84bb8722fd31a08ff7788ad31c601b377c23d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610972"
---
# <a name="script-with-the-rsexe-utility-and-the-web-service"></a><span data-ttu-id="1153c-102">Écrire des scripts avec l'utilitaire rs.exe et le service Web</span><span class="sxs-lookup"><span data-stu-id="1153c-102">Script with the rs.exe Utility and the Web Service</span></span>
  <span data-ttu-id="1153c-103">Les développeurs et les administrateurs du serveur de rapports peuvent effectuer des opérations sur un serveur de rapports grâce à l’utilitaire **rs** (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="1153c-103">Developers and report server administrators can perform operations on a report server through the use of the **rs** utility (RS.exe).</span></span> <span data-ttu-id="1153c-104">Ils peuvent ainsi administrer par programmation un serveur de rapports à l’aide de scripts écrits avec [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1153c-104">Using this utility, you can programmatically administer a report server using scripts written with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)].</span></span>  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="1153c-105">Les scripts peuvent être utilisés pour exécuter n’importe laquelle des opérations de service web Report Server.</span><span class="sxs-lookup"><span data-stu-id="1153c-105">scripts can be used to run any of the Report Server Web service operations.</span></span> <span data-ttu-id="1153c-106">Les scripts peuvent être utilisés, entre autres, pour copier la sécurité sur plusieurs rapports d'un serveur, ajouter et supprimer des éléments et copier des éléments de serveur de rapports d'un serveur vers un autre.</span><span class="sxs-lookup"><span data-stu-id="1153c-106">Scripting can be used to copy security to multiple reports on a server, to add and delete items, to copy report server items from one server to another and more.</span></span> <span data-ttu-id="1153c-107">Pour plus d’informations sur l’environnement de script, consultez [Exécuter un fichier de script Reporting Services](run-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="1153c-107">For more information about the scripting environment, see [Run a Reporting Services Script File](run-a-reporting-services-script-file.md).</span></span> <span data-ttu-id="1153c-108">Les fichiers de script obéissent à un certain format et sont écrits en [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span><span class="sxs-lookup"><span data-stu-id="1153c-108">Script files take a certain format and are written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET.</span></span> <span data-ttu-id="1153c-109">Pour plus d’informations, consultez [Vérifier une installation de Reporting Services](format-a-reporting-services-script-file.md).</span><span class="sxs-lookup"><span data-stu-id="1153c-109">For more information, see [Format a Reporting Services Script File](format-a-reporting-services-script-file.md).</span></span>  
  
 <span data-ttu-id="1153c-110">Pour obtenir des exemples de script, consultez :</span><span class="sxs-lookup"><span data-stu-id="1153c-110">For script samples, see the following:</span></span>  
  
 <span data-ttu-id="1153c-111">[Exemple Reporting Services rs.exe script pour migrer le contenu entre les serveurs de rapports](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span><span class="sxs-lookup"><span data-stu-id="1153c-111">[Sample Reporting Services rs.exe Script to Migrate Content between Report Servers](sample-reporting-services-rs-exe-script-to-copy-content-between-report-servers.md).</span></span>  
  
 <span data-ttu-id="1153c-112">[Exemples de produit SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="1153c-112">[SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1153c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1153c-113">See Also</span></span>  
 <span data-ttu-id="1153c-114">[Écrire des scripts pour les tâches d'administration et de déploiement](script-deployment-and-administrative-tasks.md) </span><span class="sxs-lookup"><span data-stu-id="1153c-114">[Script Deployment and Administrative Tasks](script-deployment-and-administrative-tasks.md) </span></span>  
 <span data-ttu-id="1153c-115">[Service web Report Server](../report-server-web-service/report-server-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="1153c-115">[Report Server Web Service](../report-server-web-service/report-server-web-service.md) </span></span>  
 <span data-ttu-id="1153c-116">[Informations techniques de référence &#40;SSRS&#41;](../technical-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="1153c-116">[Technical Reference &#40;SSRS&#41;](../technical-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="1153c-117">Utilitaire RS.exe &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="1153c-117">RS.exe Utility &#40;SSRS&#41;</span></span>](rs-exe-utility-ssrs.md)  
  
  
