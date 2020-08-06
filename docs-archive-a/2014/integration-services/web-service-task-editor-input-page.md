---
title: Éditeur de tâche de service Web (page entrée) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.webservicestask.input.f1
helpviewer_keywords:
- Web Service Task Editor
ms.assetid: 93529c88-f540-47f2-a10a-12c87318ed6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0ae876572747b9bb1088fe8b0a1c2c2fdde9f4f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613521"
---
# <a name="web-service-task-editor-input-page"></a><span data-ttu-id="39d60-102">Éditeur de tâche de service Web (page Entrée)</span><span class="sxs-lookup"><span data-stu-id="39d60-102">Web Service Task Editor (Input Page)</span></span>
  <span data-ttu-id="39d60-103">Utilisez la page **Entrée** de l' **Éditeur de tâche de service Web** pour définir le service Web, la méthode Web et les valeurs à fournir à la méthode Web comme entrée.</span><span class="sxs-lookup"><span data-stu-id="39d60-103">Use the **Input** page of the **Web Service Task Editor** dialog box to specify the Web Service, the Web method, and the values to provide to the Web method as input.</span></span> <span data-ttu-id="39d60-104">Vous pouvez fournir les valeurs en tapant des chaînes directement dans la colonne Valeur ou en y sélectionnant des variables.</span><span class="sxs-lookup"><span data-stu-id="39d60-104">The values can be provided either by typing strings directly in the Value column, or by selecting variables in the Value column.</span></span>  
  
 <span data-ttu-id="39d60-105">Pour en savoir plus sur cette tâche, consultez [Tâche de service web](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="39d60-105">To learn about this task, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="39d60-106">Options</span><span class="sxs-lookup"><span data-stu-id="39d60-106">Options</span></span>  
 <span data-ttu-id="39d60-107">**Service**</span><span class="sxs-lookup"><span data-stu-id="39d60-107">**Service**</span></span>  
 <span data-ttu-id="39d60-108">Sélectionnez un service Web dans la liste pour l'utiliser afin d'exécuter la méthode Web.</span><span class="sxs-lookup"><span data-stu-id="39d60-108">Select a Web service from the list to use to execute the Web method.</span></span>  
  
 <span data-ttu-id="39d60-109">**Méthode**</span><span class="sxs-lookup"><span data-stu-id="39d60-109">**Method**</span></span>  
 <span data-ttu-id="39d60-110">Dans la liste, sélectionnez la méthode Web que doit exécuter la tâche.</span><span class="sxs-lookup"><span data-stu-id="39d60-110">Select a Web method from the list for the task to execute.</span></span>  
  
 <span data-ttu-id="39d60-111">**WebMethodDocumentation**</span><span class="sxs-lookup"><span data-stu-id="39d60-111">**WebMethodDocumentation**</span></span>  
 <span data-ttu-id="39d60-112">Entrez la description de la méthode web ou cliquez sur le bouton Parcourir **(...)** et entrez la description dans la boîte de dialogue **Documentation de la méthode Web**.</span><span class="sxs-lookup"><span data-stu-id="39d60-112">Type a description of Web method, or the click the browse button **(...)** and then type the description in the **Web Method Documentation** dialog box.</span></span>  
  
 <span data-ttu-id="39d60-113">**Nom**</span><span class="sxs-lookup"><span data-stu-id="39d60-113">**Name**</span></span>  
 <span data-ttu-id="39d60-114">Contient la liste des noms des entrées dans la méthode Web.</span><span class="sxs-lookup"><span data-stu-id="39d60-114">Lists the names of the inputs to the Web method.</span></span>  
  
 <span data-ttu-id="39d60-115">**Type**</span><span class="sxs-lookup"><span data-stu-id="39d60-115">**Type**</span></span>  
 <span data-ttu-id="39d60-116">Indique le type des données des entrées.</span><span class="sxs-lookup"><span data-stu-id="39d60-116">Lists the data type of the inputs.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="39d60-117">La tâche de service Web prend uniquement en charge les paramètres des types de données suivants : les types de primitives tels que les entiers et les chaînes ; les tableaux et séquences de types de primitives, ainsi que les énumérations.</span><span class="sxs-lookup"><span data-stu-id="39d60-117">The Web Service task supports parameters of the following data types only: primitive types such as integers and strings; arrays and sequences of primitive types; and enumerations.</span></span>  
  
 <span data-ttu-id="39d60-118">**Variable**</span><span class="sxs-lookup"><span data-stu-id="39d60-118">**Variable**</span></span>  
 <span data-ttu-id="39d60-119">Activez les cases à cocher afin d'utiliser des variables pour fournir les entrées.</span><span class="sxs-lookup"><span data-stu-id="39d60-119">Select the check boxes to use variables to provide inputs.</span></span>  
  
 <span data-ttu-id="39d60-120">**Valeur**</span><span class="sxs-lookup"><span data-stu-id="39d60-120">**Value**</span></span>  
 <span data-ttu-id="39d60-121">Si les cases Variable sont cochées, sélectionnez les variables dans la liste pour fournir les entrées ; sinon, tapez les valeurs à utiliser en guise d’entrées.</span><span class="sxs-lookup"><span data-stu-id="39d60-121">If the Variable check-boxes are selected, select the variables in the list to provide the inputs; otherwise, type the values to use in the inputs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39d60-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="39d60-122">See Also</span></span>  
 <span data-ttu-id="39d60-123">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="39d60-123">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="39d60-124">[Éditeur de tâche de service Web &#40;page général&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="39d60-124">[Web Service Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="39d60-125">[Éditeur de tâche de service Web &#40;page sortie&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="39d60-125">[Web Service Task Editor &#40;Output Page&#41;](../../2014/integration-services/web-service-task-editor-output-page.md) </span></span>  
 [<span data-ttu-id="39d60-126">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="39d60-126">Expressions Page</span></span>](expressions/expressions-page.md)  
  
  
