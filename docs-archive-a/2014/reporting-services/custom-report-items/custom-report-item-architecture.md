---
title: Architecture des éléments de rapports personnalisés| Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, architecture
ms.assetid: 2a88ea46-c9f8-4dd7-aad1-16de11da4f06
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a053eb55547da9030eebe9036667cca2e14606f1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600655"
---
# <a name="custom-report-item-architecture"></a><span data-ttu-id="544d9-102">Architecture des éléments de rapports personnalisés</span><span class="sxs-lookup"><span data-stu-id="544d9-102">Custom Report Item Architecture</span></span>
  <span data-ttu-id="544d9-103">Un élément de rapport personnalisé est une extension du langage RDL (Report Definition Language) qui permet aux développeurs d’ajouter des fonctionnalités qui ne sont pas prises en charge en mode natif dans le langage RDL ou d’étendre les fonctionnalités de contrôles existants.</span><span class="sxs-lookup"><span data-stu-id="544d9-103">A custom report item is an extension to the Report Definition Language (RDL) that allows developers to add functionality that's not natively supported in RDL or extend the functionality of existing controls.</span></span> <span data-ttu-id="544d9-104">Un élément de rapport personnalisé comprend deux composants principaux : le composant d'exécution et le composant de conception.</span><span class="sxs-lookup"><span data-stu-id="544d9-104">There are two main components to a custom report item: the run-time component and the design-time component.</span></span> <span data-ttu-id="544d9-105">Ces composants sont implémentés en tant qu'assemblys [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] et peuvent être écrits dans n'importe quel langage conforme CLS.</span><span class="sxs-lookup"><span data-stu-id="544d9-105">These components are implemented as [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] assemblies, and can be written in any CLS-compliant language.</span></span>  
  
## <a name="the-run-time-component"></a><span data-ttu-id="544d9-106">Composant d’exécution</span><span class="sxs-lookup"><span data-stu-id="544d9-106">The Run-Time Component</span></span>  
 <span data-ttu-id="544d9-107">Le composant d'exécution pour un élément de rapport personnalisé est appelé par le processeur de rapports au moment de l'exécution.</span><span class="sxs-lookup"><span data-stu-id="544d9-107">The run-time component for a custom report item is called by the report processor at run time.</span></span> <span data-ttu-id="544d9-108">Le composant d'exécution accepte les données passées par le processeur de rapports au moment de l'exécution, traite ces données, puis retourne une image contenant l'élément de rapport personnalisé rendu.</span><span class="sxs-lookup"><span data-stu-id="544d9-108">The run-time component accepts data passed by the report processor at run time, processes this data, and returns an image containing the rendered custom report item.</span></span>  
  
 <span data-ttu-id="544d9-109">![Composant au moment de l'exécution des éléments de rapports personnalisés](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Composant au moment de l'exécution des éléments de rapports personnalisés")</span><span class="sxs-lookup"><span data-stu-id="544d9-109">![Custom report item run-time component](../../../2014/reporting-services/media/customreportitemrun-timecomponentarchitecture.gif "Custom report item run-time component")</span></span>  
  
## <a name="the-design-time-component"></a><span data-ttu-id="544d9-110">Composant de conception</span><span class="sxs-lookup"><span data-stu-id="544d9-110">The Design-Time Component</span></span>  
 <span data-ttu-id="544d9-111">Le composant de conception autorise la définition et la manipulation de l'élément de rapport personnalisé dans l'interface du Concepteur de rapports dans [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="544d9-111">The design-time component allows the custom report item to be defined and manipulated in the Report Designer interface in [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="544d9-112">Le composant de conception comprend plusieurs sous-contrôles qui contrôlent l'apparence et les propriétés de l'élément de rapport personnalisé dans l'environnement de conception.</span><span class="sxs-lookup"><span data-stu-id="544d9-112">The design-time component consists of several sub-controls that control the appearance and properties of the custom report item in the design environment.</span></span>  
  
 <span data-ttu-id="544d9-113">![Composant au moment de la conception des éléments de rapports personnalisés](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Composant au moment de la conception des éléments de rapports personnalisés")</span><span class="sxs-lookup"><span data-stu-id="544d9-113">![Custom report item design-time component](../../../2014/reporting-services/media/customreportitemdesign-timecomponentarchitecture.gif "Custom report item design-time component")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="544d9-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="544d9-114">See Also</span></span>  
 <span data-ttu-id="544d9-115">[Création d’un composant d’exécution d’élément de rapport personnalisé](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="544d9-115">[Creating a Custom Report Item Run-Time Component](../custom-report-items/creating-a-custom-report-item-run-time-component.md) </span></span>  
 <span data-ttu-id="544d9-116">[Création d’un composant au moment de la conception d’éléments de rapport personnalisés](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="544d9-116">[Creating a Custom Report Item Design-Time Component](../custom-report-items/creating-a-custom-report-item-design-time-component.md) </span></span>  
 [<span data-ttu-id="544d9-117">Procédure : déployer un élément de rapport personnalisé</span><span class="sxs-lookup"><span data-stu-id="544d9-117">How to: Deploy a Custom Report Item</span></span>](../custom-report-items/how-to-deploy-a-custom-report-item.md)  
  
  
