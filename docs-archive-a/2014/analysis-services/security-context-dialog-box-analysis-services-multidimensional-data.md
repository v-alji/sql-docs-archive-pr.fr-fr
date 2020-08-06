---
title: Boîte de dialogue contexte de sécurité (Analysis Services-données multidimensionnelles) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.securitycontext.f1
ms.assetid: 238a4a4b-84bd-4b3d-9f02-f3adf57fa3af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58d5f71172ac16087ecc342342e70ade234226a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602355"
---
# <a name="security-context-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="2f64c-102">Boîte de dialogue Contexte de sécurité (Analysis Services - Données multidimensionnelles)</span><span class="sxs-lookup"><span data-stu-id="2f64c-102">Security Context Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="2f64c-103">La boîte de dialogue **Contexte de sécurité** de [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] permet de modifier l'utilisateur et le rôle utilisé pour analyser les données ou métadonnées d'un objet [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f64c-103">Use the **Security Context** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to change the user and role used to examine data or metadata for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="2f64c-104">Pour afficher la boîte de dialogue **Contexte de sécurité** , cliquez sur **Contexte de sécurité** dans le volet **Barre d'outils** soit de l'onglet **Calculs** , soit de l'onglet **Navigateur** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="2f64c-104">You can display the **Security Context** dialog box by clicking **Security Context** in the **Toolbar** pane on either the **Calculations** tab or the **Browser** tab in Cube Designer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2f64c-105">Options</span><span class="sxs-lookup"><span data-stu-id="2f64c-105">Options</span></span>  
 <span data-ttu-id="2f64c-106">**Utilisateur actuel**</span><span class="sxs-lookup"><span data-stu-id="2f64c-106">**Current user**</span></span>  
 <span data-ttu-id="2f64c-107">Permet d'utiliser le domaine et le nom de l'utilisateur actuel, tout en affichant les données et métadonnées de l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f64c-107">Select to use the domain and user name of the current user while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="2f64c-108">**Autre utilisateur**</span><span class="sxs-lookup"><span data-stu-id="2f64c-108">**Other user**</span></span>  
 <span data-ttu-id="2f64c-109">Tapez le domaine et le nom d’un autre utilisateur ou groupe à utiliser tout en affichant les données et métadonnées de l’objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f64c-109">Type the domain and user name of another user or group to use while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="2f64c-110">Le domaine et nom de l'utilisateur ou groupe arborent le format suivant :</span><span class="sxs-lookup"><span data-stu-id="2f64c-110">The domain and name of the user or group uses the following format:</span></span>  
  
 <span data-ttu-id="2f64c-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="2f64c-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="2f64c-112">**Rôles**</span><span class="sxs-lookup"><span data-stu-id="2f64c-112">**Roles**</span></span>  
 <span data-ttu-id="2f64c-113">Permet d'utiliser un ou plusieurs rôles spécifiés lors de l'affichage des données et métadonnées de l'objet [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f64c-113">Select to use one or more specified roles when viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="2f64c-114">Vous pouvez sélectionner les rôles à utiliser si plusieurs rôles sont définis dans la base de données [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2f64c-114">You can select the roles to use if multiple roles are defined in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f64c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2f64c-115">See Also</span></span>  
 <span data-ttu-id="2f64c-116">[Indicateurs de performance clés &#40;&#41; &#40;concepteur de cube Analysis Services-données multidimensionnelles&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2f64c-116">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="2f64c-117">[Navigateur &#40;concepteur de cube&#41; &#40;Analysis Services-données multidimensionnelles&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="2f64c-117">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="2f64c-118">Analysis Services les concepteurs et les boîtes de dialogue &#40;les données multidimensionnelles&#41;</span><span class="sxs-lookup"><span data-stu-id="2f64c-118">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
