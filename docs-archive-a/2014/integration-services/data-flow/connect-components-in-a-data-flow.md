---
title: Connecter des composants dans un flux de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 8fc4a2fa81e9b110c27ea63b16d835d069bf12cf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695935"
---
# <a name="connect-components-in-a-data-flow"></a><span data-ttu-id="b09dc-102">Connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="b09dc-102">Connect Components in a Data Flow</span></span>
  <span data-ttu-id="b09dc-103">Cette procédure décrit comment connecter la sortie de composants d'un flux de données à d'autres composants du même flux de données.</span><span class="sxs-lookup"><span data-stu-id="b09dc-103">This procedure describes how to connect the output of components in a data flow to other components within the same data flow.</span></span>  
  
### <a name="to-connect-components-in-a-data-flow"></a><span data-ttu-id="b09dc-104">Pour connecter des composants dans un flux de données</span><span class="sxs-lookup"><span data-stu-id="b09dc-104">To connect components in a data flow</span></span>  
  
1.  <span data-ttu-id="b09dc-105">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] contenant le package souhaité.</span><span class="sxs-lookup"><span data-stu-id="b09dc-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="b09dc-106">Dans l'Explorateur de solutions, double-cliquez sur le package pour l'ouvrir.</span><span class="sxs-lookup"><span data-stu-id="b09dc-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="b09dc-107">Cliquez sur l’onglet **Flux de contrôle** , puis double-cliquez sur la tâche de flux de données qui contient le flux de données dans lequel vous voulez connecter des composants.</span><span class="sxs-lookup"><span data-stu-id="b09dc-107">Click the **Control Flow** tab, and then double-click the Data Flow task that contains the data flow in which you want to connect components.</span></span>  
  
4.  <span data-ttu-id="b09dc-108">Dans l’aire de conception de l’onglet **Flux de données** , sélectionnez la transformation ou la source à connecter.</span><span class="sxs-lookup"><span data-stu-id="b09dc-108">On the design surface of the **Data Flow** tab, select the transformation or source that you want to connect.</span></span>  
  
5.  <span data-ttu-id="b09dc-109">Faites glisser la flèche de sortie verte d'une transformation ou d'une source vers une transformation ou une destination.</span><span class="sxs-lookup"><span data-stu-id="b09dc-109">Drag the green output arrow of a transformation or a source to a transformation or to a destination.</span></span> <span data-ttu-id="b09dc-110">Certains composants de flux de données comportent des sorties d'erreurs, que vous pouvez connecter de la même manière.</span><span class="sxs-lookup"><span data-stu-id="b09dc-110">Some data flow components have error outputs that you can connect in the same way.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b09dc-111">Certains composants de flux de données peuvent avoir plusieurs sorties. Vous pouvez connecter chaque sortie à une transformation ou une destination différente.</span><span class="sxs-lookup"><span data-stu-id="b09dc-111">Some data flow components can have multiple outputs and you can connect each output to a different transformation or destination.</span></span>  
  
6.  <span data-ttu-id="b09dc-112">Pour enregistrer le package mis à jour, cliquez sur **Enregistrer les éléments sélectionnés** dans le menu **Fichier** .</span><span class="sxs-lookup"><span data-stu-id="b09dc-112">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09dc-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b09dc-113">See Also</span></span>  
 <span data-ttu-id="b09dc-114">[Ajouter ou supprimer un composant dans un Workflow](data-flow.md) </span><span class="sxs-lookup"><span data-stu-id="b09dc-114">[Add or Delete a Component in a Data Flow](data-flow.md) </span></span>  
 <span data-ttu-id="b09dc-115">[Configurer une sortie d’erreur dans un composant de transmission de données](../configure-an-error-output-in-a-data-flow-component.md) </span><span class="sxs-lookup"><span data-stu-id="b09dc-115">[Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md) </span></span>  
 [<span data-ttu-id="b09dc-116">Flux de données</span><span class="sxs-lookup"><span data-stu-id="b09dc-116">Data Flow</span></span>](data-flow.md)  
  
  
