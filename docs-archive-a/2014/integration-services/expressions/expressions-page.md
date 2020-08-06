---
title: Page Expressions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionspage.f1
helpviewer_keywords:
- Expressions Page dialog box
ms.assetid: c9016ec6-11c1-4ebd-b2a7-0fa6631fd9e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ba4e73ea495456e8f9e452108ab09106a65543ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604665"
---
# <a name="expressions-page"></a><span data-ttu-id="78645-102">Page Expressions</span><span class="sxs-lookup"><span data-stu-id="78645-102">Expressions Page</span></span>
  <span data-ttu-id="78645-103">Utilisez la page **Expressions** pour modifier les expressions de propriété et pour accéder aux boîtes de dialogue **Éditeur d’expressions de la propriété** et **Générateur d’expressions** .</span><span class="sxs-lookup"><span data-stu-id="78645-103">Use the **Expressions** page to edit property expressions and to access the **Property Expressions Editor** and **Property Expression Builder** dialog boxes.</span></span>  
  
 <span data-ttu-id="78645-104">Les expressions de propriété mettent à jour les valeurs des propriétés lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="78645-104">Property expressions update the values of properties when the package is run.</span></span> <span data-ttu-id="78645-105">Ces expressions peuvent être utilisées avec les propriétés des packages, des tâches, des conteneurs, des gestionnaires de connexions ainsi que certains composants de flux de données.</span><span class="sxs-lookup"><span data-stu-id="78645-105">Property expressions can be used with the properties of packages, tasks, containers, connection managers, as well as some data flow components.</span></span> <span data-ttu-id="78645-106">Les expressions sont évaluées et leurs résultats sont utilisés à la place des valeurs auxquelles vous appliquez les propriétés lorsque vous avez configuré le package et les objets de package.</span><span class="sxs-lookup"><span data-stu-id="78645-106">The expressions are evaluated and their results are used instead of the values to which you set the properties when you configured the package and package objects.</span></span> <span data-ttu-id="78645-107">Les expressions peuvent inclure des variables et les fonctions et les opérateurs fournis par le langage d'expression.</span><span class="sxs-lookup"><span data-stu-id="78645-107">The expressions can include variables and the functions and operators that the expression language provides.</span></span> <span data-ttu-id="78645-108">Par exemple, vous pouvez générer la ligne Objet pour la tâche d'envoi de courrier en concaténant la valeur d'une variable qui contient la chaîne « prévisions météorologiques pour » et les résultats de retour de la fonction GETDATE() pour obtenir la chaîne « Prévisions météorologiques pour le 5/4/2006 ».</span><span class="sxs-lookup"><span data-stu-id="78645-108">For example, you can generate the subject line for the Send Mail task by concatenating the value of a variable that contains the string "Weather forecast for " and the return results of the GETDATE() function to make the string "Weather forecast for 4/5/2006".</span></span>  
  
 <span data-ttu-id="78645-109">Pour en savoir plus sur l’utilisation des expressions de propriété et l’écriture d’expressions, consultez [Expressions Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md) et [Expressions de propriété dans des packages](use-property-expressions-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="78645-109">To learn more about writing expressions and using property expressions, see [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md) and [Use Property Expressions in Packages](use-property-expressions-in-packages.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="78645-110">Options</span><span class="sxs-lookup"><span data-stu-id="78645-110">Options</span></span>  
 <span data-ttu-id="78645-111">**Expressions (...)**</span><span class="sxs-lookup"><span data-stu-id="78645-111">**Expressions (...)**</span></span>  
 <span data-ttu-id="78645-112">Cliquez sur les points de suspension pour ouvrir la boîte de dialogue **Éditeur d’expressions de la propriété** .</span><span class="sxs-lookup"><span data-stu-id="78645-112">Click the ellipsis to open the **Property Expressions Editor** dialog box.</span></span> <span data-ttu-id="78645-113">Pour plus d’informations, consultez [Éditeur d’expressions de la propriété](property-expressions-editor.md).</span><span class="sxs-lookup"><span data-stu-id="78645-113">For more information, see [Property Expressions Editor](property-expressions-editor.md).</span></span>  
  
 **\<property name>**  
 <span data-ttu-id="78645-114">Cliquez sur les points de suspension pour ouvrir la boîte de dialogue **Générateur d'expression** .</span><span class="sxs-lookup"><span data-stu-id="78645-114">Click the ellipsis to open the **Expression Builder** dialog box.</span></span> <span data-ttu-id="78645-115">Pour plus d'informations, consultez [Expression Builder](expression-builder.md).</span><span class="sxs-lookup"><span data-stu-id="78645-115">For more information, see [Expression Builder](expression-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78645-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="78645-116">See Also</span></span>  
 <span data-ttu-id="78645-117">[Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="78645-117">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 <span data-ttu-id="78645-118">[Variables système](../system-variables.md) </span><span class="sxs-lookup"><span data-stu-id="78645-118">[System Variables](../system-variables.md) </span></span>  
 [<span data-ttu-id="78645-119">Expressions Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="78645-119">Integration Services &#40;SSIS&#41; Expressions</span></span>](integration-services-ssis-expressions.md)  
  
  
