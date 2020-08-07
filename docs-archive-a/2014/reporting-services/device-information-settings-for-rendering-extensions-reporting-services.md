---
title: Paramètres d’informations de périphérique pour les extensions de rendu (Reporting Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 947b0ee1-bb35-4b4e-9527-dc501566e7d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f15e27e01cd43bafda3aede3deca7729f2c89756
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703915"
---
# <a name="device-information-settings-for-rendering-extensions-reporting-services"></a><span data-ttu-id="09bd8-102">Paramètres d'informations de périphérique pour les extensions de rendu (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="09bd8-102">Device Information Settings for Rendering Extensions (Reporting Services)</span></span>
  <span data-ttu-id="09bd8-103">Dans [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], les paramètres d'informations de périphérique sont utilisés pour passer les paramètres de rendu à l'extension de rendu définie.</span><span class="sxs-lookup"><span data-stu-id="09bd8-103">In [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], device information settings are used to pass rendering parameters to a rendering extension.</span></span> <span data-ttu-id="09bd8-104">Chaque extension de rendu reçoit un jeu de paramètres spécifique.</span><span class="sxs-lookup"><span data-stu-id="09bd8-104">Each rendering extension accepts a specific set of settings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09bd8-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="09bd8-105">In This Section</span></span>  
  
|<span data-ttu-id="09bd8-106">Rubrique</span><span class="sxs-lookup"><span data-stu-id="09bd8-106">Topic</span></span>|<span data-ttu-id="09bd8-107">Description</span><span class="sxs-lookup"><span data-stu-id="09bd8-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="09bd8-108">Paramètres des informations de périphériques ATOM</span><span class="sxs-lookup"><span data-stu-id="09bd8-108">ATOM Device Information Settings</span></span>](../../2014/reporting-services/atom-device-information-settings.md)|<span data-ttu-id="09bd8-109">Décrit les paramètres d'informations de périphérique associés au format de rendu conforme à Atom.</span><span class="sxs-lookup"><span data-stu-id="09bd8-109">Describes the device information settings that are associated with Atom compliant rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-110">Paramètres des informations de périphériques CSV</span><span class="sxs-lookup"><span data-stu-id="09bd8-110">CSV Device Information Settings</span></span>](csv-device-information-settings.md)|<span data-ttu-id="09bd8-111">Décrit les paramètres d'informations de périphérique associés au format de rendu CSV.</span><span class="sxs-lookup"><span data-stu-id="09bd8-111">Describes the device information settings that are associated with CSV rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-112">Paramètres des informations de périphériques Excel</span><span class="sxs-lookup"><span data-stu-id="09bd8-112">Excel Device Information Settings</span></span>](excel-device-information-settings.md)|<span data-ttu-id="09bd8-113">Décrit les paramètres d'informations de périphérique associés au format de rendu Excel.</span><span class="sxs-lookup"><span data-stu-id="09bd8-113">Describes the device information settings that are associated with Excel rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-114">Paramètres des informations de périphériques Word</span><span class="sxs-lookup"><span data-stu-id="09bd8-114">Word Device Information Settings</span></span>](word-device-information-settings.md)|<span data-ttu-id="09bd8-115">Décrit les paramètres d'informations de périphérique associés au format de rendu Word.</span><span class="sxs-lookup"><span data-stu-id="09bd8-115">Describes the device information settings that are associated with Word rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-116">Paramètres d'informations de périphérique HTML</span><span class="sxs-lookup"><span data-stu-id="09bd8-116">HTML Device Information Settings</span></span>](html-device-information-settings.md)|<span data-ttu-id="09bd8-117">Décrit les paramètres d'informations de périphérique associés au format de rendu HTML.</span><span class="sxs-lookup"><span data-stu-id="09bd8-117">Describes the device information settings that are associated with HTML rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-118">Paramètres d’informations de périphérique pour l’image</span><span class="sxs-lookup"><span data-stu-id="09bd8-118">Image Device Information Settings</span></span>](image-device-information-settings.md)|<span data-ttu-id="09bd8-119">Décrit les paramètres d'informations de périphérique associés au format de rendu IMAGE.</span><span class="sxs-lookup"><span data-stu-id="09bd8-119">Describes the device information settings that are associated with IMAGE rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-120">Paramètres d'informations de périphérique pour le format de rendu MHTML</span><span class="sxs-lookup"><span data-stu-id="09bd8-120">MHTML Device Information Settings</span></span>](mhtml-device-information-settings.md)|<span data-ttu-id="09bd8-121">Décrit les paramètres d'informations de périphérique associés au format de rendu MHTML.</span><span class="sxs-lookup"><span data-stu-id="09bd8-121">Describes the device information settings that are associated with MHTML rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-122">PDF Device Information Settings</span><span class="sxs-lookup"><span data-stu-id="09bd8-122">PDF Device Information Settings</span></span>](pdf-device-information-settings.md)|<span data-ttu-id="09bd8-123">Décrit les paramètres d'informations de périphérique associés au format de rendu PDF.</span><span class="sxs-lookup"><span data-stu-id="09bd8-123">Describes the device information settings that are associated with PDF rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-124">Paramètres des informations de périphériques XML</span><span class="sxs-lookup"><span data-stu-id="09bd8-124">XML Device Information Settings</span></span>](xml-device-information-settings.md)|<span data-ttu-id="09bd8-125">Décrit les paramètres d'informations de périphérique associés au format de rendu XML.</span><span class="sxs-lookup"><span data-stu-id="09bd8-125">Describes the device information settings that are associated with XML rendering output.</span></span>|  
|[<span data-ttu-id="09bd8-126">Paramètres des informations de périphériques RGDI</span><span class="sxs-lookup"><span data-stu-id="09bd8-126">RGDI Device Information Settings</span></span>](rgdi-device-information-settings.md)|<span data-ttu-id="09bd8-127">Décrit les paramètres d'informations de périphérique associés au format de rendu RGDI.</span><span class="sxs-lookup"><span data-stu-id="09bd8-127">Describes the device information settings that are associated with RGDI rendering output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09bd8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="09bd8-128">See Also</span></span>  
 [<span data-ttu-id="09bd8-129">Personnaliser les paramètres d'extension de rendu dans RSReportServer.Config</span><span class="sxs-lookup"><span data-stu-id="09bd8-129">Customize Rendering Extension Parameters in RSReportServer.Config</span></span>](customize-rendering-extension-parameters-in-rsreportserver-config.md)  
  
  
