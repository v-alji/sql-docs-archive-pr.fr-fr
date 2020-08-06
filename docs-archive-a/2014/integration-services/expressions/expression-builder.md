---
title: Générateur d’expressions | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.expressionbuilder.f1
helpviewer_keywords:
- Expression Builder dialog box
ms.assetid: 4717ce33-bd4e-44bc-81e0-002de075b4d1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 812b0d744d415d5419d54176359ddcd5837dd206
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604664"
---
# <a name="expression-builder"></a><span data-ttu-id="e54e8-102">Générateur d’expressions</span><span class="sxs-lookup"><span data-stu-id="e54e8-102">Expression Builder</span></span>
  <span data-ttu-id="e54e8-103">Utilisez la boîte de dialogue **Générateur d’expressions** pour créer et modifier l’expression d’une propriété ou écrire l’expression qui définit la valeur d’une variable à l’aide d’une interface graphique utilisateur qui affiche la liste des variables et fournit une référence intégrée aux fonctions, aux conversions de type et aux opérateurs que contient le langage d’expression [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e54e8-103">Use the **Expression Builder** dialog box to create and edit a property expression or write the expression that sets the value of a variable using a graphical user interface that lists variables and provides a built-in reference to the functions, type casts, and operators that the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] expression language includes.</span></span>  
  
 <span data-ttu-id="e54e8-104">Une expression de propriété est une expression qui est affectée à une propriété.</span><span class="sxs-lookup"><span data-stu-id="e54e8-104">A property expression is an expression that is assigned to a property.</span></span> <span data-ttu-id="e54e8-105">Lorsque l'expression est évaluée, la propriété est mise à jour de manière dynamique pour utiliser le résultat d'évaluation de l'expression.</span><span class="sxs-lookup"><span data-stu-id="e54e8-105">When the expression is evaluated, the property is dynamically updated to use the evaluation result of the expression.</span></span> <span data-ttu-id="e54e8-106">De la même manière, une expression utilisée dans une variable permet à la valeur de la variable d'être mise à jour avec le résultat de l'évaluation de l'expression.</span><span class="sxs-lookup"><span data-stu-id="e54e8-106">Likewise, an expression that is used in a variable enables the variable value to be updated with the evaluation result of the expression.</span></span>  
  
 <span data-ttu-id="e54e8-107">Il existe deux manières d'utiliser les expressions :</span><span class="sxs-lookup"><span data-stu-id="e54e8-107">There are many ways to use expressions:</span></span>  
  
-   <span data-ttu-id="e54e8-108">**Tâches** Mettez à jour la ligne À utilisée par une tâche Envoyer un message en insérant une adresse e-mail qui est stockée dans une variable ou mettez à jour la ligne Objet en concaténant une chaîne comme « Ventes pour : » et la date du jour retournée par la fonction GETDATE.</span><span class="sxs-lookup"><span data-stu-id="e54e8-108">**Tasks** Update the To line that a Send Mail task uses by inserting an e-mail address that is stored in a variable; or update the Subject line by concatenating a string such as "Sales for: " and the current date returned by the GETDATE function.</span></span>  
  
-   <span data-ttu-id="e54e8-109">**Variables** Affectez à la valeur d'une variable le mois en cours à l'aide d'une expression telle que `DATEPART("mm",GETDATE())`; ou définissez la valeur d'une chaîne en concaténant le littéral de chaîne à l'aide de l'expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span><span class="sxs-lookup"><span data-stu-id="e54e8-109">**Variables** Set the value of a variable to the current month by using an expression like `DATEPART("mm",GETDATE())`; or set the value of a string by concatenating the string literal and the current date by using the expression `"Today's date is " + (DT_WSTR,30)(GETDATE())`.</span></span>  
  
-   <span data-ttu-id="e54e8-110">**Gestionnaire de connexions** Définissez la page de codes d'un gestionnaire de connexions de fichiers plats à l'aide d'une variable qui contient un identificateur de page de codes différent ; ou spécifiez le nombre de lignes dans le fichier de données à ignorer en entrant un entier positif (par exemple, 3) dans l'expression.</span><span class="sxs-lookup"><span data-stu-id="e54e8-110">**Connection Managers** Set the code page of a Flat File connection manager by using a variable that contains a different code page identifier; or specify the number of rows in the data file to skip by entering a positive integer like 3 in the expression.</span></span>  
  
 <span data-ttu-id="e54e8-111">Pour en savoir plus sur les expressions de propriétés et l’écriture d’expressions, consultez [Expressions de propriété dans des packages](use-property-expressions-in-packages.md) et [Expressions Integration Services &#40;SSIS&#41;](integration-services-ssis-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="e54e8-111">To learn more about property expressions and writing expressions, see [Use Property Expressions in Packages](use-property-expressions-in-packages.md) and [Integration Services &#40;SSIS&#41; Expressions](integration-services-ssis-expressions.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e54e8-112">Options</span><span class="sxs-lookup"><span data-stu-id="e54e8-112">Options</span></span>  
  
|<span data-ttu-id="e54e8-113">Terme</span><span class="sxs-lookup"><span data-stu-id="e54e8-113">Term</span></span>|<span data-ttu-id="e54e8-114">Définition</span><span class="sxs-lookup"><span data-stu-id="e54e8-114">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="e54e8-115">**Variables**</span><span class="sxs-lookup"><span data-stu-id="e54e8-115">**Variables**</span></span>|<span data-ttu-id="e54e8-116">Développez le dossier **Variables** et faites glisser les variables dans la zone **Expression** .</span><span class="sxs-lookup"><span data-stu-id="e54e8-116">Expand the **Variables** folder and drag variables to the **Expression** box.</span></span>|  
|<span data-ttu-id="e54e8-117">**Fonctions mathématiques**</span><span class="sxs-lookup"><span data-stu-id="e54e8-117">**Mathematical Functions**</span></span><br /><br /> <span data-ttu-id="e54e8-118">**Fonctions de chaîne**</span><span class="sxs-lookup"><span data-stu-id="e54e8-118">**String Functions**</span></span><br /><br /> <span data-ttu-id="e54e8-119">**Fonctions de date et d'heure**</span><span class="sxs-lookup"><span data-stu-id="e54e8-119">**Date/Time Functions**</span></span><br /><br /> <span data-ttu-id="e54e8-120">**Fonctions NULL**</span><span class="sxs-lookup"><span data-stu-id="e54e8-120">**NULL Functions**</span></span><br /><br /> <span data-ttu-id="e54e8-121">**Casts de type**</span><span class="sxs-lookup"><span data-stu-id="e54e8-121">**Type Casts**</span></span><br /><br /> <span data-ttu-id="e54e8-122">**Opérateurs**</span><span class="sxs-lookup"><span data-stu-id="e54e8-122">**Operators**</span></span>|<span data-ttu-id="e54e8-123">Développez les dossiers et faites glisser les fonctions, les conversions de type et les opérateurs dans la zone **Expression** .</span><span class="sxs-lookup"><span data-stu-id="e54e8-123">Expand the folders and drag functions, type casts, and operators to the **Expression** box.</span></span>|  
|<span data-ttu-id="e54e8-124">**Expression**</span><span class="sxs-lookup"><span data-stu-id="e54e8-124">**Expression**</span></span>|<span data-ttu-id="e54e8-125">Modifiez ou tapez une expression.\`</span><span class="sxs-lookup"><span data-stu-id="e54e8-125">Edit or type an expression.\`</span></span>|  
|<span data-ttu-id="e54e8-126">**Valeur évaluée**</span><span class="sxs-lookup"><span data-stu-id="e54e8-126">**Evaluated value**</span></span>|<span data-ttu-id="e54e8-127">Donne le résultat de l'évaluation de l'expression.</span><span class="sxs-lookup"><span data-stu-id="e54e8-127">Lists the evaluation result of the expression.</span></span>|  
|<span data-ttu-id="e54e8-128">**Évaluer l'expression**</span><span class="sxs-lookup"><span data-stu-id="e54e8-128">**Evaluate Expression**</span></span>|<span data-ttu-id="e54e8-129">Cliquez sur **Évaluer l'expression** pour afficher le résultat de l'évaluation de l'expression</span><span class="sxs-lookup"><span data-stu-id="e54e8-129">Click **Evaluate Expression** to view the evaluation result of the expression.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e54e8-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e54e8-130">See Also</span></span>  
 <span data-ttu-id="e54e8-131">[Page Expressions](expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="e54e8-131">[Expressions Page](expressions-page.md) </span></span>  
 <span data-ttu-id="e54e8-132">[Éditeur d’expressions de la propriété](property-expressions-editor.md) </span><span class="sxs-lookup"><span data-stu-id="e54e8-132">[Property Expressions Editor](property-expressions-editor.md) </span></span>  
 <span data-ttu-id="e54e8-133">[Variables Integration Services &#40;SSIS&#41;](../integration-services-ssis-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e54e8-133">[Integration Services &#40;SSIS&#41; Variables](../integration-services-ssis-variables.md) </span></span>  
 [<span data-ttu-id="e54e8-134">Variables système</span><span class="sxs-lookup"><span data-stu-id="e54e8-134">System Variables</span></span>](../system-variables.md)  
  
  
