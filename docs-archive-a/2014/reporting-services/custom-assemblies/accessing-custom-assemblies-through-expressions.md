---
title: Accès aux assemblages personnalisés par le biais d’expressions | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- expressions [Reporting Services], custom assemblies
- static member calls
- instance member calls [Reporting Services]
- calling class members
- custom assemblies [Reporting Services], expressions
ms.assetid: 917c4d47-1a95-4f54-98b1-e8cb2165d90f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 99497de0456d90fd522ce27c62fd5aa1b812059f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87599791"
---
# <a name="accessing-custom-assemblies-through-expressions"></a><span data-ttu-id="1a1f0-102">Accès aux assemblys personnalisés par le biais d'expressions</span><span class="sxs-lookup"><span data-stu-id="1a1f0-102">Accessing Custom Assemblies Through Expressions</span></span>
  <span data-ttu-id="1a1f0-103">Une fois que vous avez créé un assembly personnalisé, qu'il est disponible auprès du Concepteur de rapports ou du serveur de rapports, que vous avez ajouté la stratégie de sécurité appropriée et une référence à votre assembly personnalisé dans votre définition de rapport, vous pouvez accéder aux membres des classes dans votre assembly à l'aide d'expressions de rapport.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-103">Once you have created a custom assembly, made it available to Report Designer or the report server, added the appropriate security policy, and added a reference to your custom assembly in your report definition, you can access the members of the classes in your assembly using report expressions.</span></span> <span data-ttu-id="1a1f0-104">Pour faire référence à du code personnalisé dans une expression, vous devez appeler le membre d'une classe au sein de l'assembly.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-104">To refer to custom code in an expression, you must call the member of a class within the assembly.</span></span> <span data-ttu-id="1a1f0-105">La procédure pour ce faire dépend du type de méthode, à savoir statique ou basée sur une instance.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-105">How you do this depends on whether the method is static or instance-based.</span></span>  
  
## <a name="calling-static-members-from-a-report-definition-file"></a><span data-ttu-id="1a1f0-106">Appel de membres statiques d'un fichier de définition de rapport</span><span class="sxs-lookup"><span data-stu-id="1a1f0-106">Calling Static Members from a Report Definition File</span></span>  
 <span data-ttu-id="1a1f0-107">Les membres statiques appartiennent à la classe ou au type, pas à un objet instancié.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-107">Static members belong to the class or type itself and not to an instantiated object.</span></span> <span data-ttu-id="1a1f0-108">Ces membres sont accessibles en les appelant directement depuis la classe.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-108">These members can be accessed by directly calling them from the class.</span></span> <span data-ttu-id="1a1f0-109">Vous devez utiliser des membres statiques pour appeler des fonctions personnalisées dans un rapport chaque fois que possible, parce que les membres statiques offrent de meilleures performances.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-109">You should use static members to call custom functions in a report whenever possible, because static members perform best.</span></span> <span data-ttu-id="1a1f0-110">Pour appeler un membre statique, vous devez le référencer comme une expression qui prend la forme =*Namespace.Class.Method*.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-110">To call a static member, you need to reference it as an expression that takes the form =*Namespace.Class.Method*.</span></span>  
  
#### <a name="to-call-static-members"></a><span data-ttu-id="1a1f0-111">Pour appeler des membres statiques</span><span class="sxs-lookup"><span data-stu-id="1a1f0-111">To call static members</span></span>  
  
-   <span data-ttu-id="1a1f0-112">Pour appeler un membre statique, définissez votre expression pour qu'elle soit égale au nom complet du membre, à savoir l'espace de noms, le nom de classe et le nom de membre.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-112">To call a static member, set your expression equal to the fully qualified name of the member, which includes the namespace, class name, and member name.</span></span> <span data-ttu-id="1a1f0-113">L’exemple suivant appelle la méthode **ToGBP** qui convertit la valeur de champ **StandardCost** de dollars en livres sterling et l’affiche dans un rapport :</span><span class="sxs-lookup"><span data-stu-id="1a1f0-113">The following example calls the **ToGBP** method, which converts the **StandardCost** field value from dollars to pounds sterling and displays it in a report:</span></span>  
  
    ```  
    =CurrencyConversion.DollarCurrencyConversion.ToGBP(Fields!StandardCost.Value)  
    ```  
  
### <a name="important-information-regarding-static-fields-and-properties"></a><span data-ttu-id="1a1f0-114">Informations importantes concernant les champs et les propriétés statiques</span><span class="sxs-lookup"><span data-stu-id="1a1f0-114">Important Information Regarding Static Fields and Properties</span></span>  
 <span data-ttu-id="1a1f0-115">Actuellement, tous les rapports sont exécutés dans le même domaine d'application.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-115">Currently, all reports are executed in the same application domain.</span></span> <span data-ttu-id="1a1f0-116">Cela signifie que les rapports contenant des données statiques spécifiques à l'utilisateur exposent ces données à d'autres instances du même rapport.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-116">This means that reports with user-specific, static data expose this data to other instances of the same report.</span></span> <span data-ttu-id="1a1f0-117">Cette condition peut permettre aux données statiques d'un utilisateur d'être disponibles pour tous les utilisateurs qui exécutent actuellement un rapport particulier.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-117">This condition might make it possible for the static data of one user to be available to all users currently running a particular report.</span></span> <span data-ttu-id="1a1f0-118">Pour cette raison, il est fortement recommandé de ne pas faire appel aux champs ou propriétés statiques dans les assemblys personnalisés ou dans l’élément **Code** ; à la place, utilisez des champs ou des propriétés d’instance dans vos rapports.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-118">For this reason, it is highly recommended that you not use static fields or properties in custom assemblies or in the **Code** element; instead, use instance fields or properties in your reports.</span></span> <span data-ttu-id="1a1f0-119">Les méthodes statiques peuvent encore être utilisées car elles ne stockent pas d'état ou de données.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-119">Static methods can still be used, because they do not store state or data.</span></span>  
  
## <a name="calling-instance-members-from-a-report-definition-file"></a><span data-ttu-id="1a1f0-120">Appel de membres d'instance à partir d'un fichier de définition de rapport</span><span class="sxs-lookup"><span data-stu-id="1a1f0-120">Calling Instance Members from a Report Definition File</span></span>  
 <span data-ttu-id="1a1f0-121">Si votre assembly personnalisé contient des membres d'instance auxquels vous devez accéder dans une définition de rapport, vous devez ajouter un nom d'instance pour votre classe au rapport.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-121">If your custom assembly contains instance members that you need to access in a report definition, you must add an instance name for your class to the report.</span></span> <span data-ttu-id="1a1f0-122">Vous pouvez ajouter un nom d’instance pour une classe à l’aide de l’onglet **Code** de la boîte de dialogue **Propriétés de rapport**.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-122">You can add an instance name for a class using the **Code** tab of the **Report Properties** dialog.</span></span> <span data-ttu-id="1a1f0-123">Pour plus d’informations sur l’ajout d’instances de classes à un rapport, consultez [Code personnalisé et références d’assembly dans les expressions du Concepteur de rapports &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="1a1f0-123">For more information about adding instances of classes to a report, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](../report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
 <span data-ttu-id="1a1f0-124">Pour appeler un membre statique, vous devez le référencer en tant qu’expression qui prend la forme = code *. InstanceName. Method*.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-124">To call a static member, you need to reference it as an expression that takes the form = Code *.InstanceName.Method*.</span></span>  
  
#### <a name="to-call-instance-members"></a><span data-ttu-id="1a1f0-125">Pour appeler des membres d'instance</span><span class="sxs-lookup"><span data-stu-id="1a1f0-125">To call instance members</span></span>  
  
-   <span data-ttu-id="1a1f0-126">Pour appeler un membre d’instance d’un assembly personnalisé, vous devez référencer le mot clé **Code** suivi par le nom de l’instance et la méthode.</span><span class="sxs-lookup"><span data-stu-id="1a1f0-126">To call an instance member of a custom assembly, you must reference the **Code** keyword followed by the instance name and the method.</span></span> <span data-ttu-id="1a1f0-127">L’exemple suivant appelle une méthode d’instance **ToEUR** qui convertit la valeur de champ **StandardCost** de dollars en euros et l’affiche dans un rapport :</span><span class="sxs-lookup"><span data-stu-id="1a1f0-127">The following example calls an instance method **ToEUR** which converts the **StandardCost** field value from dollars to euros and displays it in a report:</span></span>  
  
    ```  
    =Code.m_myDollarCoversion.ToEUR(Fields!StandardCost.Value)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a1f0-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a1f0-128">See Also</span></span>  
 [<span data-ttu-id="1a1f0-129">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="1a1f0-129">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
