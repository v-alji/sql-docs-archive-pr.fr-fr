---
title: Initialisation d’objets dans un assembly personnalisé | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- initializing custom assemblies [Reporting Services]
- custom assemblies [Reporting Services], initializing
- OnInit method
ms.assetid: 26fd74dc-d02f-40f7-aeb3-50ce05e9e6b9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2aba0bd8b71b26651067a2370728dcdff521ceaa
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87605243"
---
# <a name="initializing-custom-assembly-objects"></a><span data-ttu-id="af84b-102">Initialisation d'objets Assembly personnalisés</span><span class="sxs-lookup"><span data-stu-id="af84b-102">Initializing Custom Assembly Objects</span></span>
  <span data-ttu-id="af84b-103">Dans certains cas, vous pouvez être amené à initialiser des valeurs de propriété et de champ dans vos classes d'assembly personnalisées lorsque vous les instanciez.</span><span class="sxs-lookup"><span data-stu-id="af84b-103">In some cases, you may need to initialize property and field values in your custom assembly classes when you instantiate them.</span></span> <span data-ttu-id="af84b-104">Vous aurez vraisemblablement besoin d'initialiser vos classes personnalisées avec des valeurs disponibles à partir des collections d'objets globales du rapport.</span><span class="sxs-lookup"><span data-stu-id="af84b-104">You will most likely need to initialize your custom classes with values available to you from the report's global object collections.</span></span> <span data-ttu-id="af84b-105">Pour cela, substituez la méthode **OnInit** de l’objet **Code** d’un rapport.</span><span class="sxs-lookup"><span data-stu-id="af84b-105">You do this by overriding the **OnInit** method of the **Code** object of a report.</span></span> <span data-ttu-id="af84b-106">Pour accéder à **OnInit**, utilisez l’élément **Code** de la définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="af84b-106">To access **OnInit**, use the **Code** element of the report definition.</span></span> <span data-ttu-id="af84b-107">Deux techniques vous permettent d’initialiser les valeurs de propriété ou de champ des classes dans un assembly personnalisé que vous projetez d’utiliser dans votre rapport : vous pouvez soit déclarer et créer une instance de votre classe à l’aide **d’OnInit**, soit appeler une méthode publiquement disponible à l’aide **d’OnInit**.</span><span class="sxs-lookup"><span data-stu-id="af84b-107">There are two techniques for initializing property or field values of the classes in a custom assembly that you plan to use in your report: You can either declare and create a new instance of your class using **OnInit**, or you can call a publicly available method using **OnInit**.</span></span>  
  
## <a name="global-object-collections-and-initialization"></a><span data-ttu-id="af84b-108">Collections d'objets globales et initialisation</span><span class="sxs-lookup"><span data-stu-id="af84b-108">Global Object Collections and Initialization</span></span>  
 <span data-ttu-id="af84b-109">Plusieurs collections sont disponibles pour initialiser vos variables de classe personnalisées.</span><span class="sxs-lookup"><span data-stu-id="af84b-109">Several collections are available to you for initializing your custom class variables.</span></span> <span data-ttu-id="af84b-110">Vous pouvez utiliser les collections **Globals** et **User**.</span><span class="sxs-lookup"><span data-stu-id="af84b-110">You can use the **Globals** and **User** collections.</span></span> <span data-ttu-id="af84b-111">Les collections **Parameters**, **Fields** et **ReportItems** ne sont pas disponibles au moment où, dans le cycle de vie du rapport, la méthode **OnInit** est appelée.</span><span class="sxs-lookup"><span data-stu-id="af84b-111">The **Parameters**, **Fields** and **ReportItems** collections are not available to you at the point in the report lifecycle when the **OnInit** method is invoked.</span></span> <span data-ttu-id="af84b-112">Pour utiliser les collections partagées, **Globals** ou **User**, vous devez inclure la référence d’objet **Report**.</span><span class="sxs-lookup"><span data-stu-id="af84b-112">To use the shared collections, **Globals** or **User**, you need to include the **Report** object reference.</span></span> <span data-ttu-id="af84b-113">Par exemple, pour initialiser votre classe personnalisée selon la langue actuelle de l’utilisateur qui accède au rapport, votre élément **Code** peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="af84b-113">For example, to initialize your custom class based on the current language of the user accessing the report, your **Code** element might look like the following:</span></span>  
  
```  
<Code>  
   Dim m_myClass As MyClass  
  
   Protected Overrides Sub OnInit()  
      m_myClass = new MyClass(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="af84b-114">L'une des méthodes permettant d'initialiser les valeurs de propriété et de champ d'une classe comme montré précédemment consiste à déclarer votre classe et à créer une nouvelle instance de celle-ci en appelant un constructeur substitué.</span><span class="sxs-lookup"><span data-stu-id="af84b-114">One way to initialize the property and field values of a class as shown previously is to declare your class and create a new instance of it by calling an overridden constructor.</span></span>  
  
 <span data-ttu-id="af84b-115">Une autre méthode permettant d’initialiser les valeurs de propriété et de champ des classes dans vos assemblys personnalisés consiste à appeler une méthode publiquement disponible que vous définissez à partir de la méthode **OnInit**.</span><span class="sxs-lookup"><span data-stu-id="af84b-115">Another way to initialize the property and field values of the classes in your custom assemblies is to call a publicly available method that you define from the **OnInit** method.</span></span> <span data-ttu-id="af84b-116">Vous devez d'abord ajouter un nom d'instance pour votre classe dans le fichier de définition de rapport.</span><span class="sxs-lookup"><span data-stu-id="af84b-116">You first need to add an instance name for your class in the report definition file.</span></span> <span data-ttu-id="af84b-117">Une fois que vous avez ajouté la référence d'assembly et le nom d'instance appropriés, vous pouvez appeler votre méthode d'initialisation pour initialiser les valeurs de propriété et de champ pour votre classe.</span><span class="sxs-lookup"><span data-stu-id="af84b-117">Once you have added the appropriate assembly reference and instance name, you can call your initialization method to initialize property and field values for your class.</span></span> <span data-ttu-id="af84b-118">Votre méthode **OnInit** peut se présenter comme suit :</span><span class="sxs-lookup"><span data-stu-id="af84b-118">Your **OnInit** method might look like the following:</span></span>  
  
```  
<Code>  
   Protected Overrides Sub OnInit()  
      m_myClass.MyInitializationMethod(Report.User!Language, _  
         Report.Globals!ExecutionTime)  
   End Sub  
</Code>  
```  
  
 <span data-ttu-id="af84b-119">Pour plus d’informations sur l’ajout d’une référence d’assembly et d’un nom de l’instance pour votre classe personnalisée, consultez [Ajouter une référence d’assembly à un rapport &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="af84b-119">For more information about adding an assembly reference and instance name for your custom class, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](../report-design/add-an-assembly-reference-to-a-report-ssrs.md).</span></span>  
  
 <span data-ttu-id="af84b-120">Pour plus d’informations sur les collections d’objets globales, consultez [Collections intégrées dans les expressions &#40;Générateur de rapports et SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span><span class="sxs-lookup"><span data-stu-id="af84b-120">For more information about the global object collections, see [Built-in Collections in Expressions &#40;Report Builder and SSRS&#41;](../report-design/built-in-collections-in-expressions-report-builder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af84b-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="af84b-121">See Also</span></span>  
 [<span data-ttu-id="af84b-122">Utilisation d'assemblys personnalisés avec des rapports</span><span class="sxs-lookup"><span data-stu-id="af84b-122">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
