---
title: Destination du recordset | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.recordsetdest.f1
helpviewer_keywords:
- Recordset destination
- ADO recordsets [Integration Services]
- destinations [Integration Services], Recordset
- in-memory ADO recordsets [Integration Services]
ms.assetid: be973cf1-c4ff-49f8-987e-314c08ef98e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c1acc29c904e9020721e8ac62dff09a8ec29a392
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602906"
---
# <a name="recordset-destination"></a><span data-ttu-id="a9086-102">Destination de l'ensemble d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="a9086-102">Recordset Destination</span></span>
  <span data-ttu-id="a9086-103">La destination de l'ensemble d'enregistrements crée et remplit un ensemble d'enregistrements ADO en mémoire.</span><span class="sxs-lookup"><span data-stu-id="a9086-103">The Recordset destination creates and populates an in-memory ADO recordset.</span></span> <span data-ttu-id="a9086-104">La forme de l'ensemble d'enregistrements est définie par l'entrée de la destination d'ensemble d'enregistrements au moment de la conception.</span><span class="sxs-lookup"><span data-stu-id="a9086-104">The shape of the recordset is defined by the input to the Recordset destination at design time.</span></span>  
  
## <a name="configuration-of-the-recordset-destination"></a><span data-ttu-id="a9086-105">Configuration de la destination de l'ensemble d'enregistrements</span><span class="sxs-lookup"><span data-stu-id="a9086-105">Configuration of the Recordset Destination</span></span>  
 <span data-ttu-id="a9086-106">Pour configurer la destination de l'ensemble d'enregistrements,vous devez spécifier la variable qui contient l'ensemble d'enregistrements ADO.</span><span class="sxs-lookup"><span data-stu-id="a9086-106">You configure the Recordset destination by specifying the variable that stores the ADO recordset.</span></span>  
  
 <span data-ttu-id="a9086-107">Au moment de l’exécution, un ensemble d’enregistrements ADO est écrit dans la variable du type, Object, qui est spécifié dans la propriété VariableName de la destination de l’ensemble d’enregistrements.</span><span class="sxs-lookup"><span data-stu-id="a9086-107">At run time, an ADO recordset is written to the variable of type, Object, that is specified in the VariableName property of the Recordset destination.</span></span> <span data-ttu-id="a9086-108">La variable rend ensuite l'ensemble d'enregistrements disponible en dehors du flux de données, où il peut être utilisé par des scripts et d'autres éléments de package.</span><span class="sxs-lookup"><span data-stu-id="a9086-108">The variable then makes the Recordset available outside the data flow, where it can be used by scripts and other package elements.</span></span>  
  
 <span data-ttu-id="a9086-109">Cette source possède une entrée.</span><span class="sxs-lookup"><span data-stu-id="a9086-109">This source has one input.</span></span> <span data-ttu-id="a9086-110">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="a9086-110">It does not support an error output.</span></span>  
  
 <span data-ttu-id="a9086-111">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="a9086-111">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="a9086-112">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="a9086-112">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="a9086-113">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="a9086-113">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="a9086-114">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="a9086-114">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="a9086-115">Propriétés personnalisées de la destination du jeu d’enregistrements</span><span class="sxs-lookup"><span data-stu-id="a9086-115">Recordset Destination Custom Properties</span></span>](recordset-destination-custom-properties.md)  
  
 <span data-ttu-id="a9086-116">Pour plus d’informations sur la façon de définir des propriétés, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a9086-116">For more information about how to set the properties, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="a9086-117">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="a9086-117">Related Tasks</span></span>  
 [<span data-ttu-id="a9086-118">Utiliser une destination de jeu d’enregistrements</span><span class="sxs-lookup"><span data-stu-id="a9086-118">Use a Recordset Destination</span></span>](recordset-destination.md)  
  
  
