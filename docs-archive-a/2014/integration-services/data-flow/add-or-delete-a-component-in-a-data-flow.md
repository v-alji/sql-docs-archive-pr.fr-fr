---
title: Ajouter ou supprimer un composant dans un flux de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- adding components
- components [Integration Services], data flow
ms.assetid: d99124f9-0994-4f40-a48e-fdca6a4383e7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2f041258d2b66e7b8da540a842848ebf70f4ed5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697035"
---
# <a name="add-or-delete-a-component-in-a-data-flow"></a><span data-ttu-id="5a2ad-102">Ajouter ou supprimer un composant dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="5a2ad-102">Add or Delete a Component in a Data Flow</span></span>
  <span data-ttu-id="5a2ad-103">Les composants de flux de données sont des sources, des destinations et des transformations dans un flux de données.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-103">Data flow components are sources, destinations, and transformations in a data flow.</span></span> <span data-ttu-id="5a2ad-104">Pour que vous puissiez ajouter des composants à un flux de données, le flux de contrôle du package doit inclure une tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-104">Before you can add components to a data flow, the control flow in the package must include a Data Flow task.</span></span>  
  
 <span data-ttu-id="5a2ad-105">Les procédures ci-dessous montrent comment ajouter ou supprimer un composant dans le flux de données d'un package.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-105">The following procedures describe how to add or delete a component in the data flow of a package.</span></span>  
  
### <a name="to-add-a-component-to-a-data-flow"></a><span data-ttu-id="5a2ad-106">Pour ajouter un composant à un flux de données</span><span class="sxs-lookup"><span data-stu-id="5a2ad-106">To add a component to a data flow</span></span>  
  
1.  <span data-ttu-id="5a2ad-107">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-107">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5a2ad-108">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-108">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="5a2ad-109">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la tâche de flux de données qui contient le flux de données auquel vous voulez ajouter un composant.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-109">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow to which you want to add a component.</span></span>  
  
4.  <span data-ttu-id="5a2ad-110">Dans la boîte à outils, développez **Sources de flux de données**, **Transformations du flux de données**ou **Destinations du flux de données**, puis faites glisser un élément de flux de données sur l’aire de conception de l’onglet **Flux de données** .</span><span class="sxs-lookup"><span data-stu-id="5a2ad-110">In the Toolbox, expand **Data Flow Sources**, **Data Flow Transformations**, or **Data Flow Destinations**, and then drag a data flow item to the design surface of the **Data Flow** tab.</span></span>  
  
5.  <span data-ttu-id="5a2ad-111">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="5a2ad-111">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
### <a name="to-delete-a-component-from-a-data-flow"></a><span data-ttu-id="5a2ad-112">Pour supprimer un composant d'un flux de données</span><span class="sxs-lookup"><span data-stu-id="5a2ad-112">To delete a component from a data flow</span></span>  
  
1.  <span data-ttu-id="5a2ad-113">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-113">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5a2ad-114">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-114">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="5a2ad-115">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la tâche de flux de données contenant le flux de données duquel vous voulez supprimer un composant.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-115">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow from which you want to delete a component.</span></span>  
  
4.  <span data-ttu-id="5a2ad-116">Cliquez avec le bouton droit sur le composant du flux de données, puis cliquez sur **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-116">Right-click the data flow component, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="5a2ad-117">Confirmez la suppression.</span><span class="sxs-lookup"><span data-stu-id="5a2ad-117">Confirm the delete operation.</span></span>  
  
6.  <span data-ttu-id="5a2ad-118">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="5a2ad-118">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a2ad-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5a2ad-119">See Also</span></span>  
 <span data-ttu-id="5a2ad-120">[Connecter des composants dans un flux de données](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="5a2ad-120">[Connect Components in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="5a2ad-121">[Configurer une sortie d’erreur dans un composant de transmission de données](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="5a2ad-121">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="5a2ad-122">Flux de données</span><span class="sxs-lookup"><span data-stu-id="5a2ad-122">Data Flow</span></span>](data-flow.md)  
  
  
