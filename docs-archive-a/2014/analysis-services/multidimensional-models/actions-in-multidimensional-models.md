---
title: Actions dans les modèles multidimensionnels | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- actions [Analysis Services], creating
- report actions [Analysis Services]
- drillthrough actions [Analysis Services]
- cubes [Analysis Services], actions
ms.assetid: b9fee2b9-05a5-4077-848d-d8457326dc27
author: minewiskan
ms.author: owend
ms.openlocfilehash: ce42907190363be085e8f4d8e9adfbab52a70590
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604209"
---
# <a name="actions-in-multidimensional-models"></a><span data-ttu-id="da4d2-102">Actions dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="da4d2-102">Actions in Multidimensional Models</span></span>
  <span data-ttu-id="da4d2-103">Une action est une opération réalisée par un utilisateur final sur un cube (ou portion de cube) sélectionné.</span><span class="sxs-lookup"><span data-stu-id="da4d2-103">An action is an end user-initiated operation upon a selected cube or portion of a cube.</span></span> <span data-ttu-id="da4d2-104">Cette opération peut soit démarrer une application en prenant comme paramètre l'élément sélectionné, soit extraire des informations relatives à l'élément sélectionné.</span><span class="sxs-lookup"><span data-stu-id="da4d2-104">The operation can start an application with the selected item as a parameter, or it can retrieve information about the selected item.</span></span> <span data-ttu-id="da4d2-105">Pour plus d’informations sur les d’actions, consultez [Actions &#40;Analysis Services - Données multidimensionnelles&#41;](actions-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="da4d2-105">For more information about actions, see [Actions &#40;Analysis Services - Multidimensional Data&#41;](actions-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="da4d2-106">Pour construire des actions pour un cube, utilisez l’onglet **Actions** du Concepteur de cube.</span><span class="sxs-lookup"><span data-stu-id="da4d2-106">Use the **Actions** tab of Cube Designer to build actions for a cube.</span></span> <span data-ttu-id="da4d2-107">Spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="da4d2-107">Specify the following:</span></span>  
  
 <span data-ttu-id="da4d2-108">**Nom**</span><span class="sxs-lookup"><span data-stu-id="da4d2-108">**Name**</span></span>  
 <span data-ttu-id="da4d2-109">Sélectionnez un nom identifiant l'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-109">Select a name that identifies the action.</span></span>  
  
 <span data-ttu-id="da4d2-110">**Cible d'action**</span><span class="sxs-lookup"><span data-stu-id="da4d2-110">**Action Target**</span></span>  
 <span data-ttu-id="da4d2-111">Sélectionnez l'objet auquel l'action est attachée.</span><span class="sxs-lookup"><span data-stu-id="da4d2-111">Select the object to which the action is attached.</span></span> <span data-ttu-id="da4d2-112">Généralement, dans les applications clientes, l'action s'affiche lorsque les utilisateurs finaux sélectionnent l'objet cible ; toutefois, l'application cliente détermine quelle opération de l'utilisateur final affiche les actions.</span><span class="sxs-lookup"><span data-stu-id="da4d2-112">Generally, in client applications, the action is displayed when end users select the target object; however, the client application determines which end-user operation displays actions.</span></span> <span data-ttu-id="da4d2-113">Pour **Type de cible**, sélectionnez l’un des objets suivants :</span><span class="sxs-lookup"><span data-stu-id="da4d2-113">For **Target type**, select from the following objects:</span></span>  
  
-   <span data-ttu-id="da4d2-114">Membres d'attribut</span><span class="sxs-lookup"><span data-stu-id="da4d2-114">Attribute members</span></span>  
  
-   <span data-ttu-id="da4d2-115">Cellules</span><span class="sxs-lookup"><span data-stu-id="da4d2-115">Cells</span></span>  
  
-   <span data-ttu-id="da4d2-116">Cube</span><span class="sxs-lookup"><span data-stu-id="da4d2-116">Cube</span></span>  
  
-   <span data-ttu-id="da4d2-117">Membres de dimension</span><span class="sxs-lookup"><span data-stu-id="da4d2-117">Dimension members</span></span>  
  
-   <span data-ttu-id="da4d2-118">Hierarchy</span><span class="sxs-lookup"><span data-stu-id="da4d2-118">Hierarchy</span></span>  
  
-   <span data-ttu-id="da4d2-119">Membres de hiérarchie</span><span class="sxs-lookup"><span data-stu-id="da4d2-119">Hierarchy members</span></span>  
  
-   <span data-ttu-id="da4d2-120">Level</span><span class="sxs-lookup"><span data-stu-id="da4d2-120">Level</span></span>  
  
-   <span data-ttu-id="da4d2-121">Membres de niveau</span><span class="sxs-lookup"><span data-stu-id="da4d2-121">Level members</span></span>  
  
 <span data-ttu-id="da4d2-122">Après avoir sélectionné le type de l’objet cible, sous **Objet cible**, sélectionnez l’objet de cube du type désigné.</span><span class="sxs-lookup"><span data-stu-id="da4d2-122">After you select the target object type, under **Target object**, select the cube object of the designated type.</span></span>  
  
 <span data-ttu-id="da4d2-123">**Condition (facultatif)**</span><span class="sxs-lookup"><span data-stu-id="da4d2-123">**Condition (Optional)**</span></span>  
 <span data-ttu-id="da4d2-124">Spécifiez une expression MDX (Multidimensional Expressions) facultative qui est résolue en valeur booléenne.</span><span class="sxs-lookup"><span data-stu-id="da4d2-124">Specify an optional Multidimensional Expressions (MDX) expression that resolves to a Boolean value.</span></span> <span data-ttu-id="da4d2-125">Si la valeur est `True`, l'action est effectuée sur la cible spécifiée.</span><span class="sxs-lookup"><span data-stu-id="da4d2-125">If the value is `True`, the action is performed on the specified target.</span></span> <span data-ttu-id="da4d2-126">Si la valeur est `False`, l'action n'est pas effectuée.</span><span class="sxs-lookup"><span data-stu-id="da4d2-126">If the value is `False`, the action is not performed.</span></span>  
  
 <span data-ttu-id="da4d2-127">**Contenu d'action**</span><span class="sxs-lookup"><span data-stu-id="da4d2-127">**Action Content**</span></span>  
 <span data-ttu-id="da4d2-128">Sélectionnez le type d'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-128">Select the type of action.</span></span> <span data-ttu-id="da4d2-129">Le tableau suivant récapitule les types disponibles.</span><span class="sxs-lookup"><span data-stu-id="da4d2-129">The following table summarizes the available types.</span></span>  
  
|<span data-ttu-id="da4d2-130">Type</span><span class="sxs-lookup"><span data-stu-id="da4d2-130">Type</span></span>|<span data-ttu-id="da4d2-131">Description</span><span class="sxs-lookup"><span data-stu-id="da4d2-131">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="da4d2-132">Jeu de données</span><span class="sxs-lookup"><span data-stu-id="da4d2-132">Data Set</span></span>|<span data-ttu-id="da4d2-133">Récupère un dataset.</span><span class="sxs-lookup"><span data-stu-id="da4d2-133">Retrieves a dataset.</span></span>|  
|<span data-ttu-id="da4d2-134">Propriétaire</span><span class="sxs-lookup"><span data-stu-id="da4d2-134">Proprietary</span></span>|<span data-ttu-id="da4d2-135">Effectue une opération en utilisant une interface différente de celles répertoriées dans ce tableau.</span><span class="sxs-lookup"><span data-stu-id="da4d2-135">Performs an operation by using an interface other than those listed in this table.</span></span>|  
|<span data-ttu-id="da4d2-136">Ensemble de lignes</span><span class="sxs-lookup"><span data-stu-id="da4d2-136">Row Set</span></span>|<span data-ttu-id="da4d2-137">Récupère un ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="da4d2-137">Retrieves a rowset.</span></span>|  
|<span data-ttu-id="da4d2-138">Instruction</span><span class="sxs-lookup"><span data-stu-id="da4d2-138">Statement</span></span>|<span data-ttu-id="da4d2-139">Exécute une commande OLE DB.</span><span class="sxs-lookup"><span data-stu-id="da4d2-139">Runs an OLE DB command.</span></span>|  
|<span data-ttu-id="da4d2-140">URL</span><span class="sxs-lookup"><span data-stu-id="da4d2-140">URL</span></span>|<span data-ttu-id="da4d2-141">Affiche une page qui varie selon le cas dans un navigateur Internet.</span><span class="sxs-lookup"><span data-stu-id="da4d2-141">Displays a variable page in an Internet browser.</span></span>|  
  
 <span data-ttu-id="da4d2-142">Pour **Expression d’action**, spécifiez les paramètres qui sont transmis quand l’action est exécutée.</span><span class="sxs-lookup"><span data-stu-id="da4d2-142">For **Action Expression**, specify the parameters that are passed when the action is run.</span></span> <span data-ttu-id="da4d2-143">La syntaxe doit correspondre à une chaîne et vous devez inclure une expression écrite en MDX.</span><span class="sxs-lookup"><span data-stu-id="da4d2-143">The syntax must evaluate to a string, and you must include an expression written in MDX.</span></span> <span data-ttu-id="da4d2-144">Par exemple, votre expression MDX peut indiquer une partie du cube inclus dans la syntaxe.</span><span class="sxs-lookup"><span data-stu-id="da4d2-144">For example, your MDX expression can indicate a part of the cube that is included in the syntax.</span></span> <span data-ttu-id="da4d2-145">Les expressions MDX sont évaluées avant la transmission des paramètres.</span><span class="sxs-lookup"><span data-stu-id="da4d2-145">MDX expressions are evaluated before the parameters are passed.</span></span> <span data-ttu-id="da4d2-146">Par ailleurs, vous pouvez utiliser le générateur MDX pour élaborer vos expressions MDX.</span><span class="sxs-lookup"><span data-stu-id="da4d2-146">Also, MDX Builder is available to help you build MDX expressions.</span></span>  
  
 <span data-ttu-id="da4d2-147">**Propriétés supplémentaires**</span><span class="sxs-lookup"><span data-stu-id="da4d2-147">**Additional Properties**</span></span>  
 <span data-ttu-id="da4d2-148">Sélectionnez la propriété.</span><span class="sxs-lookup"><span data-stu-id="da4d2-148">Select the property.</span></span> <span data-ttu-id="da4d2-149">Le tableau suivant répertorie les propriétés disponibles.</span><span class="sxs-lookup"><span data-stu-id="da4d2-149">The following table summarizes the available properties.</span></span>  
  
|<span data-ttu-id="da4d2-150">Propriété</span><span class="sxs-lookup"><span data-stu-id="da4d2-150">Property</span></span>|<span data-ttu-id="da4d2-151">Description</span><span class="sxs-lookup"><span data-stu-id="da4d2-151">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="da4d2-152">**Invocation**</span><span class="sxs-lookup"><span data-stu-id="da4d2-152">**Invocation**</span></span>|<span data-ttu-id="da4d2-153">Détermine le mode d'exécution de l'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-153">Specifies how the action is run.</span></span> <span data-ttu-id="da4d2-154">Le mode interactif, qui est celui par défaut, spécifie que l'action est exécutée lorsqu'un utilisateur accède à un objet.</span><span class="sxs-lookup"><span data-stu-id="da4d2-154">Interactive, the default, specifies that the action is run when a user accesses an object.</span></span> <span data-ttu-id="da4d2-155">Les paramètres possibles sont :</span><span class="sxs-lookup"><span data-stu-id="da4d2-155">The possible settings are:</span></span><br /><br /> <span data-ttu-id="da4d2-156">Batch</span><span class="sxs-lookup"><span data-stu-id="da4d2-156">Batch</span></span><br /><br /> <span data-ttu-id="da4d2-157">Interactive</span><span class="sxs-lookup"><span data-stu-id="da4d2-157">Interactive</span></span><br /><br /> <span data-ttu-id="da4d2-158">À l’ouverture</span><span class="sxs-lookup"><span data-stu-id="da4d2-158">On Open</span></span>|  
|<span data-ttu-id="da4d2-159">**Application**</span><span class="sxs-lookup"><span data-stu-id="da4d2-159">**Application**</span></span>|<span data-ttu-id="da4d2-160">Décrit l'application de l'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-160">Describes the application of the action.</span></span>|  
|<span data-ttu-id="da4d2-161">**Description**</span><span class="sxs-lookup"><span data-stu-id="da4d2-161">**Description**</span></span>|<span data-ttu-id="da4d2-162">Décrit l'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-162">Describes the action.</span></span>|  
|<span data-ttu-id="da4d2-163">**Caption**</span><span class="sxs-lookup"><span data-stu-id="da4d2-163">**Caption**</span></span>|<span data-ttu-id="da4d2-164">Fournit une légende qui s'affiche pour l'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-164">Provides a caption that is displayed for the action.</span></span> <span data-ttu-id="da4d2-165">Si la légende est MDX, spécifiez `True` pour **Caption est MDX**.</span><span class="sxs-lookup"><span data-stu-id="da4d2-165">If the caption is MDX, specify `True` for **Caption is MDX**.</span></span>|  
|<span data-ttu-id="da4d2-166">**La légende est MDX**</span><span class="sxs-lookup"><span data-stu-id="da4d2-166">**Caption is MDX**</span></span>|<span data-ttu-id="da4d2-167">Spécifiez `True` si la légende est au format MDX ou `False` si ce n'est pas le cas.</span><span class="sxs-lookup"><span data-stu-id="da4d2-167">Specify `True` if the caption is MDX or `False` if it is not.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="da4d2-168">Vous devez utiliser le langage de script Analysis Services (ASSL) ou les objets AMO (Analysis Management Objects) pour définir les types d'action de ligne de commande et HTML.</span><span class="sxs-lookup"><span data-stu-id="da4d2-168">You must use Analysis Services Scripting Language (ASSL) or Analysis Management Objects (AMO) to define HTML and Command Line action types.</span></span> <span data-ttu-id="da4d2-169">Pour plus d’informations, consultez [Élément Action &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Élément Type &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl) et [Programmation d’objets OLAP AMO avancés](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span><span class="sxs-lookup"><span data-stu-id="da4d2-169">For more information, see [Action Element &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/objects/action-element-assl), [Type Element &#40;Action&#41; &#40;ASSL&#41;](https://docs.microsoft.com/bi-reference/assl/properties/type-element-action-assl), and [Programming AMO OLAP Advanced Objects](https://docs.microsoft.com/bi-reference/amo/programming-amo-olap-advanced-objects).</span></span>  
  
## <a name="creating-a-reporting-action"></a><span data-ttu-id="da4d2-170">Création d'une action de rapport</span><span class="sxs-lookup"><span data-stu-id="da4d2-170">Creating a Reporting Action</span></span>  
 <span data-ttu-id="da4d2-171">Le serveur de rapports répond aux demandes de rapports basées sur une URL.</span><span class="sxs-lookup"><span data-stu-id="da4d2-171">The report server responds to URL-based requests for reports.</span></span> <span data-ttu-id="da4d2-172">Pour créer une action de rapport, dans le menu **Cube** , cliquez sur **Nouvelle action de rapport**.</span><span class="sxs-lookup"><span data-stu-id="da4d2-172">To create a reporting action, on the **Cube** menu, click **New Reporting Action**.</span></span> <span data-ttu-id="da4d2-173">Les options suivantes sont propres à une action de rapport.</span><span class="sxs-lookup"><span data-stu-id="da4d2-173">The following options are specific to a reporting action.</span></span>  
  
 <span data-ttu-id="da4d2-174">**Serveur de rapports**</span><span class="sxs-lookup"><span data-stu-id="da4d2-174">**Report Server**</span></span>  
 <span data-ttu-id="da4d2-175">Les propriétés décrites dans le tableau suivant sont spécifiées pour le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="da4d2-175">The properties described in the following table are specified for the report server.</span></span>  
  
|<span data-ttu-id="da4d2-176">Propriété</span><span class="sxs-lookup"><span data-stu-id="da4d2-176">Property</span></span>|<span data-ttu-id="da4d2-177">Description</span><span class="sxs-lookup"><span data-stu-id="da4d2-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="da4d2-178">**Nom du serveur**</span><span class="sxs-lookup"><span data-stu-id="da4d2-178">**Server name**</span></span>|<span data-ttu-id="da4d2-179">Nom de l'ordinateur exécutant le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="da4d2-179">The name of the computer running report server.</span></span>|  
|<span data-ttu-id="da4d2-180">**Chemin d'accès au serveur**</span><span class="sxs-lookup"><span data-stu-id="da4d2-180">**Server path**</span></span>|<span data-ttu-id="da4d2-181">Chemin exposé par le serveur de rapports.</span><span class="sxs-lookup"><span data-stu-id="da4d2-181">The path exposed by report server.</span></span>|  
|<span data-ttu-id="da4d2-182">**Format de rapport**</span><span class="sxs-lookup"><span data-stu-id="da4d2-182">**Report format**</span></span>|<span data-ttu-id="da4d2-183">HTML5, HTML3, Excel ou PDF.</span><span class="sxs-lookup"><span data-stu-id="da4d2-183">HTML5, HTML3, Excel, or PDF.</span></span>|  
  
 <span data-ttu-id="da4d2-184">**Paramètres (facultatif)**</span><span class="sxs-lookup"><span data-stu-id="da4d2-184">**Parameters (Optional)**</span></span>  
 <span data-ttu-id="da4d2-185">Les paramètres sont envoyés au serveur comme une partie de la chaîne de l'URL lorsque l'action est créée.</span><span class="sxs-lookup"><span data-stu-id="da4d2-185">The parameters are sent to the server as part of the URL string when the action is created.</span></span> <span data-ttu-id="da4d2-186">Ceux-ci comptent notamment **Nom du paramètre** et **Valeur du paramètre**, c’est-à-dire une expression MDX.</span><span class="sxs-lookup"><span data-stu-id="da4d2-186">They include **Parameter Name** and **Parameter Value**, which is an MDX expression.</span></span>  
  
 <span data-ttu-id="da4d2-187">L'URL du serveur de rapports est construite comme suit :</span><span class="sxs-lookup"><span data-stu-id="da4d2-187">The report server URL is constructed as follows:</span></span>  
  
```  
  
http://  
host  
/  
virtualdirectory  
/Path&  
parametername1  
=  
parametervalue1  
& ...  
```  
  
 <span data-ttu-id="da4d2-188">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="da4d2-188">For example:</span></span>  
  
```  
http://localhost/ReportServer/Sales/YearlySalesByCategory?rs:Command=Render&Region=West  
```  
  
## <a name="creating-a-drillthrough-action"></a><span data-ttu-id="da4d2-189">Création d'une action d'extraction</span><span class="sxs-lookup"><span data-stu-id="da4d2-189">Creating a Drillthrough Action</span></span>  
 <span data-ttu-id="da4d2-190">Une action d'extraction est définie par une action de type ensemble de lignes, qui est retournée à l'application cliente comme une instruction d'extraction.</span><span class="sxs-lookup"><span data-stu-id="da4d2-190">A drillthrough action is defined by a rowset action, which is returned to the client application as a drillthrough statement.</span></span> <span data-ttu-id="da4d2-191">La cible d'action est le membre d'un groupe de mesures.</span><span class="sxs-lookup"><span data-stu-id="da4d2-191">The action target is a member of a measure group.</span></span> <span data-ttu-id="da4d2-192">Pour créer une action d’extraction, dans le menu **Cube** , cliquez sur **Nouvelle action d’extraction**.</span><span class="sxs-lookup"><span data-stu-id="da4d2-192">To create a new drillthrough action, on the **Cube** menu, click **New Drillthrough Action**.</span></span> <span data-ttu-id="da4d2-193">Les options suivantes sont propres à une action d'extraction.</span><span class="sxs-lookup"><span data-stu-id="da4d2-193">The following options are specific to a drillthrough action:</span></span>  
  
 <span data-ttu-id="da4d2-194">**Colonnes d'extraction**</span><span class="sxs-lookup"><span data-stu-id="da4d2-194">**Drillthrough Columns**</span></span>  
 <span data-ttu-id="da4d2-195">Sélectionnez une ou plusieurs dimensions et, pour chacune d'entre elles, les colonnes d'extraction retournées à l'application cliente par l'action.</span><span class="sxs-lookup"><span data-stu-id="da4d2-195">Select one or more dimensions and, for each dimension, the drillthrough columns returned to the client application by the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da4d2-196">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da4d2-196">See Also</span></span>  
 [<span data-ttu-id="da4d2-197">Cubes dans les modèles multidimensionnels</span><span class="sxs-lookup"><span data-stu-id="da4d2-197">Cubes in Multidimensional Models</span></span>](cubes-in-multidimensional-models.md)  
  
  
