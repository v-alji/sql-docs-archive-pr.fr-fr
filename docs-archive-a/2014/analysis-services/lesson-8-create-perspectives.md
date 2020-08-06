---
title: 'Leçon 9 : créer des perspectives | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 55b0f0d0-1cdf-4876-9c3d-d0c848be3f5d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 417b6a4d3b16857f48bcc2f39dc8ec4c010a2b10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706915"
---
# <a name="lesson-9-create-perspectives"></a><span data-ttu-id="33976-102">Leçon 9 : Créer des perspectives</span><span class="sxs-lookup"><span data-stu-id="33976-102">Lesson 9: Create Perspectives</span></span>
  <span data-ttu-id="33976-103">Dans cette leçon, vous allez créer une perspective Internet Sales.</span><span class="sxs-lookup"><span data-stu-id="33976-103">In this lesson, you will create an Internet Sales perspective.</span></span> <span data-ttu-id="33976-104">Une perspective correspond à un sous-ensemble visualisable d’un modèle qui fournit des points de vue précis, spécifiques à l’entreprise ou à l’application.</span><span class="sxs-lookup"><span data-stu-id="33976-104">A perspective defines a viewable subset of a model that provides focused, business-specific, or application-specific viewpoints.</span></span> <span data-ttu-id="33976-105">Lorsqu'un utilisateur se connecte à un modèle à l'aide d'une perspective, il voit uniquement les objets de modèle (tables, colonnes, mesures, hiérarchies et KPI) en tant que champs définis dans cette perspective.</span><span class="sxs-lookup"><span data-stu-id="33976-105">When a user connects to a model using a perspective, they see only those model objects (tables, columns, measures, hierarchies, and KPIs) as fields defined in that perspective.</span></span>  
  
 <span data-ttu-id="33976-106">La perspective Internet Sales que vous créez dans cette leçon exclura l'objet table Customer.</span><span class="sxs-lookup"><span data-stu-id="33976-106">The Internet Sales perspective you create in this lesson will exclude the Customer table object.</span></span> <span data-ttu-id="33976-107">Lorsque vous créez une perspective qui exclut certains objets de la vue, cet objet existe toujours dans le modèle ; toutefois, il n'est pas visible dans une liste de champs de client de création de rapports.</span><span class="sxs-lookup"><span data-stu-id="33976-107">When you create a perspective that excludes certain objects from view, that object still exists in the model; however, it is not visible in a reporting client field list.</span></span> <span data-ttu-id="33976-108">Les colonnes calculées et les mesures incluses ou non dans une perspective peuvent toujours être calculées à partir de données d'objet exclues.</span><span class="sxs-lookup"><span data-stu-id="33976-108">Calculated columns and measures either included in a perspective or not can still calculate from object data that is excluded.</span></span>  
  
 <span data-ttu-id="33976-109">L'objectif de cette leçon est plutôt de décrire comment créer des points de vue et de vous familiariser avec les outils de création de modèles tabulaires.</span><span class="sxs-lookup"><span data-stu-id="33976-109">The purpose of this lesson is to describe how to create perspectives and become familiar with the tabular model authoring tools.</span></span> <span data-ttu-id="33976-110">Si vous développez par la suite ce modèle pour inclure des tables supplémentaires, vous pourrez créer des perspectives supplémentaires pour définir des points de vue différents, concernant, par exemple, les stocks et la forces de vente.</span><span class="sxs-lookup"><span data-stu-id="33976-110">If you later expand this model to include additional tables, you can create additional perspectives to define different viewpoints of the model, for example, Inventory and Sales Force.</span></span>  
  
 <span data-ttu-id="33976-111">Pour plus d’informations, consultez [Perspectives &#40;SSSAS Tabulaire&#41;](tabular-models/perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="33976-111">To learn more, see [Perspectives &#40;SSAS Tabular&#41;](tabular-models/perspectives-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="33976-112">Durée estimée pour effectuer cette leçon : **5 minutes**</span><span class="sxs-lookup"><span data-stu-id="33976-112">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33976-113">Prérequis</span><span class="sxs-lookup"><span data-stu-id="33976-113">Prerequisites</span></span>  
 <span data-ttu-id="33976-114">Cette rubrique fait partie d’un didacticiel de modélisation tabulaire, qui doit être suivi dans l’ordre prévu.</span><span class="sxs-lookup"><span data-stu-id="33976-114">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="33976-115">Avant d’effectuer les tâches de cette leçon, vous devez avoir terminé la leçon précédente : [Leçon 8 : Créer les indicateurs de performance clés](lesson-7-create-key-performance-indicators.md).</span><span class="sxs-lookup"><span data-stu-id="33976-115">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 8: Create Key Performance Indicators](lesson-7-create-key-performance-indicators.md).</span></span>  
  
## <a name="create-perspectives"></a><span data-ttu-id="33976-116">Créer des perspectives</span><span class="sxs-lookup"><span data-stu-id="33976-116">Create Perspectives</span></span>  
  
#### <a name="to-create-an-internet-sales-perspective"></a><span data-ttu-id="33976-117">Pour créer une perspective Internet Sales</span><span class="sxs-lookup"><span data-stu-id="33976-117">To create an Internet Sales perspective</span></span>  
  
1.  <span data-ttu-id="33976-118">Dans le générateur de modèles, cliquez sur le menu **modèle** , puis sur **perspectives**.</span><span class="sxs-lookup"><span data-stu-id="33976-118">In the model designer, click the **Model** menu, and then click **Perspectives**.</span></span>  
  
2.  <span data-ttu-id="33976-119">Dans la boîte de dialogue **Perspectives** , cliquez sur **Nouvelle perspective**.</span><span class="sxs-lookup"><span data-stu-id="33976-119">In the **Perspectives** dialog box, click **New Perspective**.</span></span>  
  
3.  <span data-ttu-id="33976-120">Pour renommer la perspective, double-cliquez sur l’en-tête **de colonne nouvelle perspective 1** , puis tapez `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="33976-120">To rename the perspective, double-click the **New Perspective 1** column heading, and then type `Internet Sales`.</span></span>  
  
4.  <span data-ttu-id="33976-121">Dans **champs**, sélectionnez les tables suivantes : **Date**, **géographie**, **produit**, **catégorie de produit**, sous-catégorie de **produit**et `Internet Sales` .</span><span class="sxs-lookup"><span data-stu-id="33976-121">In **Fields**, select the following tables **Date**, **Geography**, **Product**, **Product Category**, **Product Subcategory**, and `Internet Sales`.</span></span>  
  
     <span data-ttu-id="33976-122">Notez que vous avez exclu la table Customer et toutes ses colonnes de cette perspective.</span><span class="sxs-lookup"><span data-stu-id="33976-122">Notice you excluded the Customer table and all of its columns from this perspective.</span></span> <span data-ttu-id="33976-123">Ultérieurement, au cours de la leçon 12, vous utiliserez la fonctionnalité Analyser dans Excel pour tester cette perspective.</span><span class="sxs-lookup"><span data-stu-id="33976-123">Later, in Lesson 12, you will use the Analyze in Excel feature to test this perspective.</span></span> <span data-ttu-id="33976-124">La liste de champs de tableau croisé dynamique Excel inclut chaque table sauf la table Customer.</span><span class="sxs-lookup"><span data-stu-id="33976-124">The Excel PivotTable Field List will include each table except the Customer table.</span></span>  
  
5.  <span data-ttu-id="33976-125">Vérifiez vos sélections, vérifiez que la table **Customer** n’est pas sélectionnée, puis cliquez sur **OK**</span><span class="sxs-lookup"><span data-stu-id="33976-125">Verify your selections, making sure the **Customer** table is not checked, and then click **OK**</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="33976-126">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="33976-126">Next Steps</span></span>  
 <span data-ttu-id="33976-127">Pour poursuivre l’étude de ce didacticiel, passez à la [Leçon 10 : Créer des hiérarchies](lesson-9-create-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="33976-127">To continue this tutorial, go to the next lesson: [Lesson 10: Create Hierarchies](lesson-9-create-hierarchies.md).</span></span>  
  
  
