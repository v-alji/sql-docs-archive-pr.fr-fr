---
title: Modifier la requête de source OData au moment de l’exécution | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bcbba7f4-6e5d-46e6-a73a-3f17d3ff376a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b3dbc4d27f2d11537a9d66980ef6ca59b80811b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708504"
---
# <a name="modify-odata-source-query-at-runtime"></a><span data-ttu-id="331c1-102">Modifier la requête de la source OData à l'exécution</span><span class="sxs-lookup"><span data-stu-id="331c1-102">Modify OData Source Query at Runtime</span></span>
  <span data-ttu-id="331c1-103">Vous pouvez modifier la requête de source OData au moment de l’exécution en ajoutant une expression à la propriété **[OData Source].[Query]** de la tâche de flux de données.</span><span class="sxs-lookup"><span data-stu-id="331c1-103">You can modify the OData Source query at runtime by adding an expression to the **[OData Source].[Query]** property of the Data Flow task.</span></span>  
  
 <span data-ttu-id="331c1-104">Notez que les colonnes doivent être identiques à celles utilisées au moment de la conception ; sinon vous obtiendrez une erreur lors de l'exécution du package.</span><span class="sxs-lookup"><span data-stu-id="331c1-104">Note that the columns must remain the same as what was used at design time; otherwise you will get an error when the package is executed.</span></span> <span data-ttu-id="331c1-105">Veillez à spécifier les mêmes colonnes (dans le même ordre) lorsque vous utilisez l'option de requête $select.</span><span class="sxs-lookup"><span data-stu-id="331c1-105">Be sure to specify the same columns (in the same order) when using the $select query option.</span></span> <span data-ttu-id="331c1-106">Une alternative plus sûre à l’utilisation de l’option $select est de désélectionner les colonnes que vous ne souhaitez pas utiliser directement de l’interface utilisateur du composant source.</span><span class="sxs-lookup"><span data-stu-id="331c1-106">A safer alternative to using the $select option is to deselect the columns you don't want directly from the Source Component UI.</span></span>  
  
 <span data-ttu-id="331c1-107">Il existe d'autres méthodes de définition dynamique de la valeur de la requête à l'exécution.</span><span class="sxs-lookup"><span data-stu-id="331c1-107">There are a few different ways of dynamically setting the query value at runtime.</span></span> <span data-ttu-id="331c1-108">Voici quelques-unes des plus courantes.</span><span class="sxs-lookup"><span data-stu-id="331c1-108">Below are some of the more common methods.</span></span>  
  
## <a name="exposing-the-query-as-a-parameter"></a><span data-ttu-id="331c1-109">Exposer une requête en tant que paramètre</span><span class="sxs-lookup"><span data-stu-id="331c1-109">Exposing the Query as a Parameter</span></span>  
 <span data-ttu-id="331c1-110">La procédure suivante comporte des étapes pour exposer une requête utilisée par un composant source OData comme paramètre sur le package.</span><span class="sxs-lookup"><span data-stu-id="331c1-110">The following procedure has steps to expose query used by an OData Source component as a parameter to the package.</span></span>  
  
1.  <span data-ttu-id="331c1-111">Cliquez avec le bouton droit sur **Tâche de flux de données** et sélectionnez l’option **Paramétrer...** .</span><span class="sxs-lookup"><span data-stu-id="331c1-111">Right click on the **Data Flow task** and select the **Parameterize...** option.</span></span>  
  
2.  <span data-ttu-id="331c1-112">Dans la boîte de dialogue **Paramétrer**, sélectionnez **[\<Name of the OData Source Component>].[Query]** pour **Propriété**.</span><span class="sxs-lookup"><span data-stu-id="331c1-112">In the **Parameterize** dialog, select **[\<Name of the OData Source Component>].[Query]** for **Property**.</span></span>  
  
3.  <span data-ttu-id="331c1-113">Vous pouvez soit **créer un paramètre** , soit **utiliser un paramètre existant**.</span><span class="sxs-lookup"><span data-stu-id="331c1-113">Choose whether to **create new parameter** or **use an existing parameter**.</span></span>  
  
4.  <span data-ttu-id="331c1-114">Si vous sélectionnez **Créer un paramètre**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="331c1-114">If you select **Create new parameter**, do the following:</span></span>  
  
    1.  <span data-ttu-id="331c1-115">Entrez un **nom** et une **description** pour le paramètre.</span><span class="sxs-lookup"><span data-stu-id="331c1-115">Enter **name** and **description** for the parameter.</span></span>  
  
    2.  <span data-ttu-id="331c1-116">Spécifiez la **valeur** par défaut du paramètre.</span><span class="sxs-lookup"><span data-stu-id="331c1-116">Specify default **value** for the parameter.</span></span>  
  
    3.  <span data-ttu-id="331c1-117">Spécifiez l’ **étendue** (**package** ou **projet**) du paramètre.</span><span class="sxs-lookup"><span data-stu-id="331c1-117">Specify the **scope** (**package** or **project**) for the parameter.</span></span>  
  
    4.  <span data-ttu-id="331c1-118">Spécifiez si le paramètre est **obligatoire** ou non.</span><span class="sxs-lookup"><span data-stu-id="331c1-118">Specify whether the parameter is **required** or not</span></span>  
  
5.  <span data-ttu-id="331c1-119">Cliquez sur **OK** pour fermer la boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="331c1-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="using-an-expression"></a><span data-ttu-id="331c1-120">Utiliser une expression</span><span class="sxs-lookup"><span data-stu-id="331c1-120">Using an Expression</span></span>  
 <span data-ttu-id="331c1-121">Cette méthode est utile lorsque vous souhaitez construire dynamiquement la chaîne de requête à l'exécution.</span><span class="sxs-lookup"><span data-stu-id="331c1-121">This method is useful when you want to dynamically construct query string at runtime.</span></span> <span data-ttu-id="331c1-122">Dans cet exemple, la variable MaxRows sera définie par d'autres moyens (script, paramètre, etc.).</span><span class="sxs-lookup"><span data-stu-id="331c1-122">In this example, MaxRows variable will be set through other means (script, parameter, etc).</span></span>  
  
1.  <span data-ttu-id="331c1-123">Sélectionnez la **Tâche de flux de données** qui contient votre **Source OData**.</span><span class="sxs-lookup"><span data-stu-id="331c1-123">Select the **Data Flow Task** which contains your **OData Source**.</span></span>  
  
2.  <span data-ttu-id="331c1-124">La fenêtre **Propriétés** met en surbrillance la propriété **Expressions** .</span><span class="sxs-lookup"><span data-stu-id="331c1-124">In the **Properties** window, highlight the **Expressions** property.</span></span>  
  
3.  <span data-ttu-id="331c1-125">Cliquez sur... (points de suspension) pour afficher l' **éditeur d’expressions**de la propriété.</span><span class="sxs-lookup"><span data-stu-id="331c1-125">Click the ... (ellipses) button to bring up the **Property Expressions Editor**.</span></span>  
  
4.  <span data-ttu-id="331c1-126">Sélectionnez la propriété **[OData Source].[Query]** .</span><span class="sxs-lookup"><span data-stu-id="331c1-126">Select the **[OData Source].[Query]** property.</span></span>  
  
5.  <span data-ttu-id="331c1-127">Cliquez sur... bouton (points de suspension) pour l' **expression**.</span><span class="sxs-lookup"><span data-stu-id="331c1-127">Click the ... (ellipses) button for **Expression**.</span></span>  
  
6.  <span data-ttu-id="331c1-128">Entrez l’ **expression**.</span><span class="sxs-lookup"><span data-stu-id="331c1-128">Enter the **expression**.</span></span>  
  
7.  <span data-ttu-id="331c1-129">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="331c1-129">Click **OK**.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="331c1-130">Notez qu'en utilisant cette approche, vous devez vous assurer que les valeurs définies sont codées correctement pour l'URL.</span><span class="sxs-lookup"><span data-stu-id="331c1-130">Note that when using this approach you need to ensure that the values set are properly URL encoded.</span></span> <span data-ttu-id="331c1-131">Lorsque vous recevez des valeurs de l'entrée utilisateur (par exemple, lorsque vous définissez des valeurs d'option de requête individuelles), vous devez vous assurer que les valeurs sont validées pour éviter des attaques potentielles par injection SQL.</span><span class="sxs-lookup"><span data-stu-id="331c1-131">When receiving values from user input (for example, setting individual query option values from a parameter), you must ensure that the values are validated to avoid potential SQL injection-type attacks.</span></span>  
  
  
