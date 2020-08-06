---
title: Afficher le code XML d’un projet Analysis Services (SSDT) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- projects [Analysis Services], viewing XML
ms.assetid: dd1a4bc6-57b5-47df-8619-09f921aa6351
author: minewiskan
ms.author: owend
ms.openlocfilehash: 1c320145be2073c741498bed0f10732ac8d528e9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87707916"
---
# <a name="view-the-xml-for-an-analysis-services-project-ssdt"></a><span data-ttu-id="36740-102">Afficher le code XML d'un projet Analysis Services (SSDT)</span><span class="sxs-lookup"><span data-stu-id="36740-102">View the XML for an Analysis Services Project (SSDT)</span></span>
  <span data-ttu-id="36740-103">Si vous utilisez une base de données [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] en mode projet, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] crée une définition XML pour chaque objet dans le dossier du projet.</span><span class="sxs-lookup"><span data-stu-id="36740-103">When you are working with an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in project mode, [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] creates an XML definition for each object within the project folder.</span></span> <span data-ttu-id="36740-104">Vous pouvez afficher le contenu du fichier XML pour chaque objet dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36740-104">You can view the contents of the XML file for each object within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="36740-105">Vous pouvez également modifier le fichier XML directement. Toutefois, nous vous déconseillons de procéder ainsi, car certaines modifications peuvent rendre le fichier XML illisible dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36740-105">You can also edit the XML file directly; however, this is not recommended in most circumstances as you may make changes that make the XML unreadable by [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="36740-106">Vous ne pouvez pas afficher le code XML d'un projet complet. Cependant, vous pouvez afficher le code de chaque objet car il existe un fichier distinct pour chaque objet.</span><span class="sxs-lookup"><span data-stu-id="36740-106">You cannot view the xml code for an entire project, but rather you view the code for each object because a separate file exists for each object.</span></span> <span data-ttu-id="36740-107">La seule façon d’afficher le code pour un projet entier est de générer le projet et d’afficher le code ASSL dans le \<project name> fichier. asdatabase.</span><span class="sxs-lookup"><span data-stu-id="36740-107">The only way to view the code for an entire project is to build the project and view the ASSL code in the \<project name>.asdatabase file.</span></span>  
  
### <a name="to-view-the-xml-code-for-an-object"></a><span data-ttu-id="36740-108">Pour afficher le code XML d'un objet</span><span class="sxs-lookup"><span data-stu-id="36740-108">To view the XML code for an object</span></span>  
  
1.  <span data-ttu-id="36740-109">Ouvrez le projet [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36740-109">Open the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="36740-110">Cliquez avec le bouton droit sur l’objet dans l’Explorateur de solutions, puis cliquez sur **Afficher le code**.</span><span class="sxs-lookup"><span data-stu-id="36740-110">Right-click the object in Solution Explorer and then click **View Code**.</span></span>  
  
     <span data-ttu-id="36740-111">Le code XML de l’objet s’affiche dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36740-111">The XML code for the object appears in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36740-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36740-112">See Also</span></span>  
 [<span data-ttu-id="36740-113">Générer des projets Analysis Services &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="36740-113">Build Analysis Services Projects &#40;SSDT&#41;</span></span>](build-analysis-services-projects-ssdt.md)  
  
  
