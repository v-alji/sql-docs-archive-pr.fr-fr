---
title: Éditeur avancé | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.advancededitor.columnmappings.f1
- sql12.dts.designer.advancededitor.inputcolumns.f1
- sql12.dts.designer.advancededitor.columnproperties.f1
- sql12.dts.designer.advancededitor.componentproperties.f1
- sql12.dts.designer.advancededitor.connections.f1
ms.assetid: 5ad0ac71-fa8b-4c26-bd42-e6ef00c87571
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7f4897f2589acdeb93efecbdf9aacde07d21ca42
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602983"
---
# <a name="advanced-editor"></a><span data-ttu-id="34f57-102">Éditeur avancé</span><span class="sxs-lookup"><span data-stu-id="34f57-102">Advanced Editor</span></span>
  <span data-ttu-id="34f57-103">Utilisez la boîte de dialogue **Éditeur avancé** pour configurer les propriétés du composant de l'objet [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] sélectionné.</span><span class="sxs-lookup"><span data-stu-id="34f57-103">Use the **Advanced Editor** dialog box to configure to configure properties for the selected [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="34f57-104">L' **Éditeur avancé** est disponible pour la plupart des objets [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] dont les propriétés sont configurables.</span><span class="sxs-lookup"><span data-stu-id="34f57-104">The **Advanced Editor** is available for most [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] objects that have configurable properties.</span></span> <span data-ttu-id="34f57-105">Il s'agit du seul éditeur disponible pour les objets qui ne comportent pas d'interface utilisateur personnalisée.</span><span class="sxs-lookup"><span data-stu-id="34f57-105">It is the only editor available for those objects that do not expose a custom user interface.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="34f57-106">ont des propriétés qu'il est possible de définir au niveau du composant, de l'entrée et de la sortie et au niveau de la colonne d'entrée et de sortie.</span><span class="sxs-lookup"><span data-stu-id="34f57-106">data flow objects have properties that can be set at the component level, the input and output level, and the input and output column level.</span></span> <span data-ttu-id="34f57-107">L' **Éditeur avancé** énumère toutes les propriétés courantes et personnalisées de l'objet sélectionné. Il les affiche dans au maximum quatre des cinq onglets suivants en fonction des cas :</span><span class="sxs-lookup"><span data-stu-id="34f57-107">The **Advanced Editor** enumerates all the common and custom properties of the selected object and displays them on up to four of the following five tabs as applicable:</span></span>  
  
-   <span data-ttu-id="34f57-108">**Gestionnaires de connexions** : utilisez cet onglet pour définir les propriétés de connexion.</span><span class="sxs-lookup"><span data-stu-id="34f57-108">**Connection Managers** -- use this tab to set connection properties</span></span>  
  
-   <span data-ttu-id="34f57-109">**Propriétés du composant** : utilisez cet onglet pour définir les propriétés au niveau du composant.</span><span class="sxs-lookup"><span data-stu-id="34f57-109">**Component Properties** -- use this tab to set component-level properties</span></span>  
  
-   <span data-ttu-id="34f57-110">**Mappage de colonnes** : utilisez cet onglet pour mapper les colonnes disponibles en tant que colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="34f57-110">**Column Mappings** -- use this tab to map available columns as output columns</span></span>  
  
-   <span data-ttu-id="34f57-111">**Colonnes d’entrée** : utilisez cet onglet pour sélectionner les colonnes d’entrée.</span><span class="sxs-lookup"><span data-stu-id="34f57-111">**Input Columns** -- use this tab to select input columns</span></span>  
  
-   <span data-ttu-id="34f57-112">**Propriétés d’entrée et de sortie** : utilisez cet onglet pour définir les propriétés d’entrée et de sortie, ainsi que pour ajouter et supprimer des sorties, sélectionner ou supprimer les colonnes des entrées et des sorties, et définir les propriétés des entrées et des sorties.</span><span class="sxs-lookup"><span data-stu-id="34f57-112">**Input and Output Properties** -- use this tab to set input and output properties; and to add and remove outputs, select or remove columns for inputs and outputs, and set properties for inputs and outputs</span></span>  
  
 <span data-ttu-id="34f57-113">Les propriétés affichées dépendent des composants.</span><span class="sxs-lookup"><span data-stu-id="34f57-113">The properties displayed vary by component.</span></span> <span data-ttu-id="34f57-114">Pour plus d'informations sur les propriétés qu'il est possible d'afficher dans l' **Éditeur avancé**, consultez les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="34f57-114">For more information on the properties that may be displayed in the **Advanced Editor**, see the following topics:</span></span>  
  
-   [<span data-ttu-id="34f57-115">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="34f57-115">Common Properties</span></span>](../../2014/integration-services/common-properties.md)  
  
-   [<span data-ttu-id="34f57-116">Propriétés personnalisées des transformations</span><span class="sxs-lookup"><span data-stu-id="34f57-116">Transformation Custom Properties</span></span>](data-flow/transformations/transformation-custom-properties.md)  
  
-   [<span data-ttu-id="34f57-117">Propriétés du chemin</span><span class="sxs-lookup"><span data-stu-id="34f57-117">Path Properties</span></span>](../../2014/integration-services/path-properties.md)  
  
 <span data-ttu-id="34f57-118">Pour plus d'informations sur le composant spécifique que vous modifiez, consultez la description du composant dans la section « Composants des flux de données » de la documentation Objets et concepts d' [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="34f57-118">For more information about the specific component that you are editing, see the description of the component in the Data Flow Elements section of the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Objects and Concepts documentation:</span></span>  
  
-   [<span data-ttu-id="34f57-119">Transformations Integration Services</span><span class="sxs-lookup"><span data-stu-id="34f57-119">Integration Services Transformations</span></span>](data-flow/transformations/integration-services-transformations.md)  
  
## <a name="see-also"></a><span data-ttu-id="34f57-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="34f57-120">See Also</span></span>  
 [<span data-ttu-id="34f57-121">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="34f57-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
