---
title: Mise en œuvre d’une extension de rendu | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- rendering extensions [Reporting Services]
- custom rendering extensions [Reporting Services]
- transformations [Reporting Services]
- extensions [Reporting Services], rendering
- rendering extensions [Reporting Services], implementing
ms.assetid: 4a5c64f5-2391-4597-ba3f-81d265b23703
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 03deb7c818de8d875f69b585ae6015fc178e707d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610486"
---
# <a name="implementing-a-rendering-extension"></a><span data-ttu-id="d639f-102">Implémentation d'une extension de rendu</span><span class="sxs-lookup"><span data-stu-id="d639f-102">Implementing a Rendering Extension</span></span>
  <span data-ttu-id="d639f-103">Une extension de rendu est un composant ou un module d'un serveur de rapports qui transforme les données de rapport et les informations de disposition dans un format spécifique au périphérique.</span><span class="sxs-lookup"><span data-stu-id="d639f-103">A rendering extension is a component or module of a report server that transforms report data and layout information into a device-specific format.</span></span> <span data-ttu-id="d639f-104">SQL Server Reporting Services incluent six extensions de rendu : HTML, Excel, Word, CSV ou Texte, XML, Image et PDF.</span><span class="sxs-lookup"><span data-stu-id="d639f-104">SQL Server Reporting Services includes six rendering extensions: HTML, Excel, Word, CSV or Text, XML, Image, and PDF.</span></span> <span data-ttu-id="d639f-105">Vous pouvez créer des extensions de rendu supplémentaires pour créer des rapports dans d'autres formats.</span><span class="sxs-lookup"><span data-stu-id="d639f-105">You can create additional rendering extensions to generate reports in other formats.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d639f-106">Pour déterminer quelles extensions de rendu sont disponibles, vous pouvez consulter la liste des extensions installées dans le fichier RSReportServer.config.</span><span class="sxs-lookup"><span data-stu-id="d639f-106">To determine which rendering extensions are available, you can view the list of installed extensions in the RSReportServer.config file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d639f-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="d639f-107">In This Section</span></span>  
 [<span data-ttu-id="d639f-108">Vue d'ensemble des extensions de rendu</span><span class="sxs-lookup"><span data-stu-id="d639f-108">Rendering Extensions Overview</span></span>](rendering-extensions-overview.md)  
 <span data-ttu-id="d639f-109">Explique comment écrire une extension de rendu personnalisée pour [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d639f-109">Introduces how to write a custom rendering extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="d639f-110">Mise en œuvre de l'interface IRenderingExtension </span><span class="sxs-lookup"><span data-stu-id="d639f-110">Implementing the IRenderingExtension Interface</span></span>](implementing-the-irenderingextension-interface.md)  
 <span data-ttu-id="d639f-111">Décrit les attributs d'une extension de rendu.</span><span class="sxs-lookup"><span data-stu-id="d639f-111">Describes the attributes of a rendering extension.</span></span>  
  
 [<span data-ttu-id="d639f-112">Déploiement d'une extension de rendu</span><span class="sxs-lookup"><span data-stu-id="d639f-112">Deploying a Rendering Extension</span></span>](deploying-a-rendering-extension.md)  
 <span data-ttu-id="d639f-113">Décrit comment déployer une extension de rendu sur un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d639f-113">Describes how to deploy a rendering extension on a report server.</span></span>  
  
 [<span data-ttu-id="d639f-114">Suppression d'une extension de rendu</span><span class="sxs-lookup"><span data-stu-id="d639f-114">Removing a Rendering Extension</span></span>](removing-a-rendering-extension.md)  
 <span data-ttu-id="d639f-115">Décrit comment supprimer une extension de rendu d'un serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="d639f-115">Describes how to remove a rendering extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d639f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d639f-116">See Also</span></span>  
 <span data-ttu-id="d639f-117">[Extensions Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="d639f-117">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="d639f-118">Bibliothèque d'extensions Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d639f-118">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
