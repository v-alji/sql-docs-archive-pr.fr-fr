---
title: '&#39;nouveautés de Générateur de rapports pour SQL Server 2014 | Microsoft Docs'
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 8223c19b-4b0d-4b1d-a042-9a726c18e708
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 0ce72af225130bc3f081a53008a303c5213db636
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610963"
---
# <a name="what39s-new-in-report-builder-for-sql-server-2014"></a><span data-ttu-id="57638-102">&#39;nouveautés de Générateur de rapports pour SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="57638-102">What&#39;s New in Report Builder for SQL Server 2014</span></span>
  <span data-ttu-id="57638-103">[!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] inclut plusieurs fonctionnalités [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="57638-103">The [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] introduces a number of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] features.</span></span>  
  
 <span data-ttu-id="57638-104">Pour plus d’informations sur les fonctionnalités de cette version pour d’autres [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] produits et technologies, consultez [nouveautés de SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span><span class="sxs-lookup"><span data-stu-id="57638-104">For information about features in this release for other [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] products and technologies, see [What's New in SQL Server 2014](../sql-server/what-s-new-in-sql-server-2016.md).</span></span>  
  
> [!TIP]  
>  <span data-ttu-id="57638-105">Pour obtenir les dernières informations et ressources sur les nouvelles fonctionnalités de cette version, consultez [Informations supplémentaires sur les nouveautés de SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span><span class="sxs-lookup"><span data-stu-id="57638-105">For the most recent information and resources regarding new features in this release, see [Additional information on what is new in SQL Server Reporting Services (SSRS)](https://go.microsoft.com/fwlink/?LinkId=207147).</span></span>  
  
##  <a name="excel-renderer-for-microsoft-excel-2007-2010-and-microsoft-excel-2003"></a><a name="ExcelRenderer"></a><span data-ttu-id="57638-106">Convertisseur Excel pour Microsoft Excel 2007-2010 et Microsoft Excel 2003</span><span class="sxs-lookup"><span data-stu-id="57638-106">Excel Renderer for Microsoft Excel 2007-2010 and Microsoft Excel 2003</span></span>  
 <span data-ttu-id="57638-107">L'extension de rendu Excel [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , nouvelle dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], restitue un rapport sous la forme d'un document Excel compatible avec [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010, ainsi qu'avec [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 moyennant l'installation préalable du Module de compatibilité pour formats de fichiers Microsoft Office Word, Excel et PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="57638-107">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Excel rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as an Excel document that is compatible with [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2007-2010 as well as [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="57638-108">Le format est Office Open XML et l'extension de fichier est .xlsx.</span><span class="sxs-lookup"><span data-stu-id="57638-108">The format is Office Open XML and the file extension of files is .xlsx.</span></span>  
  
 <span data-ttu-id="57638-109">Cette extension de rendu Excel supprime les limitations de la version antérieure, compatible avec Excel 2003.</span><span class="sxs-lookup"><span data-stu-id="57638-109">This Excel-rendering extension removes limitations of the earlier version, compatible with Excel 2003.</span></span> <span data-ttu-id="57638-110">Voici les améliorations apportées à l'extension de rendu :</span><span class="sxs-lookup"><span data-stu-id="57638-110">The following lists the improvement in the rendering extension:</span></span>  
  
-   <span data-ttu-id="57638-111">Le nombre maximal de lignes par feuille de travail est de 1 048 576.</span><span class="sxs-lookup"><span data-stu-id="57638-111">Maximum rows per worksheet is 1,048,576.</span></span>  
  
-   <span data-ttu-id="57638-112">Le nombre maximal de colonnes par feuille de travail est de 16 384.</span><span class="sxs-lookup"><span data-stu-id="57638-112">Maximum columns per worksheet is 16,384.</span></span>  
  
-   <span data-ttu-id="57638-113">Le nombre de couleurs autorisé dans une feuille de travail est approximativement de 16 millions (couleurs 24 bits).</span><span class="sxs-lookup"><span data-stu-id="57638-113">Number of colors allowed in a worksheet is approximately 16 million (24-bit color).</span></span>  
  
-   <span data-ttu-id="57638-114">La compression ZIP réduit la taille des fichiers.</span><span class="sxs-lookup"><span data-stu-id="57638-114">ZIP compression provides smaller files sizes.</span></span>  
  
 <span data-ttu-id="57638-115">Pour plus d’informations, consultez [Exportation vers Microsoft Excel &#40;Générateur de rapports et SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="57638-115">For more information, see [Exporting to Microsoft Excel &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-excel-report-builder-and-ssrs.md).</span></span>  
  
##  <a name="word-renderer-for-microsoft-word-2007-2010-and-microsoft-word-2003"></a><a name="WordRenderer"></a><span data-ttu-id="57638-116">Convertisseur Word pour Microsoft Word 2007-2010 et Microsoft Word 2003</span><span class="sxs-lookup"><span data-stu-id="57638-116">Word Renderer for Microsoft Word 2007-2010 and Microsoft Word 2003</span></span>  
 <span data-ttu-id="57638-117">L'extension de rendu Word [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , nouvelle dans [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], restitue un rapport sous la forme d'un document Word compatible avec [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010, ainsi qu'avec [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 moyennant l'installation préalable du Module de compatibilité pour formats de fichiers [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Word, Excel et PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="57638-117">The [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] Word rendering extension, new in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], renders a report as a Word document that is compatible with [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2007-2010 as well as [!INCLUDE[ofprword](../includes/ofprword-md.md)] 2003 with the [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Compatibility Pack for Word, Excel, and PowerPoint installed.</span></span> <span data-ttu-id="57638-118">Le format est Office Open XML et l'extension de fichier est .docx.</span><span class="sxs-lookup"><span data-stu-id="57638-118">The format is Office Open XML and the file extension of files is docx.</span></span>  
  
 <span data-ttu-id="57638-119">En plus de rendre les nouvelles fonctions de Word 2007-2010 disponibles dans les rapports exportés, les fichiers \*.docx des rapports exportés paraissent plus petits.</span><span class="sxs-lookup"><span data-stu-id="57638-119">In addition to making the features that are new in Word 2007-2010 available to exported reports, \*.docx files of exported reports tend to be smaller.</span></span> <span data-ttu-id="57638-120">Les rapports exportés à l'aide du convertisseur Word sont généralement beaucoup plus petits que les mêmes rapports exportés à l'aide du convertisseur Word 2003.</span><span class="sxs-lookup"><span data-stu-id="57638-120">Reports exported by using the Word renderer are typically significantly smaller than the same reports exported by using the Word 2003 renderer.</span></span>  
  
 <span data-ttu-id="57638-121">Pour plus d’informations, consultez [Exportation vers Microsoft Word &#40;Générateur de rapports et SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="57638-121">For more information, see [Exporting to Microsoft Word &#40;Report Builder and SSRS&#41;](report-builder/exporting-to-microsoft-word-report-builder-and-ssrs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57638-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="57638-122">See Also</span></span>  
 [<span data-ttu-id="57638-123">Générateur de rapports dans SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="57638-123">Report Builder in SQL Server 2014</span></span>](report-builder/report-builder-in-sql-server-2016.md)  
  
  
