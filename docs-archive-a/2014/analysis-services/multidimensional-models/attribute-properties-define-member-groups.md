---
title: Définir des groupes de membres | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- member groups [Analysis Services]
- grouping members
- DiscretizationMethod property
ms.assetid: 006cc915-c499-4781-b9a7-01ad31bebf6a
author: minewiskan
ms.author: owend
ms.openlocfilehash: 95f9516c7a0077e97af348afa863fe15c8d4528b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708796"
---
# <a name="define-member-groups"></a><span data-ttu-id="6c32d-102">Définir des groupes de membres</span><span class="sxs-lookup"><span data-stu-id="6c32d-102">Define Member Groups</span></span>
  <span data-ttu-id="6c32d-103">Si un attribut possède un grand nombre de membres, vous pouvez décider de grouper ces membres dans des compartiments afin de réduire le nombre de membres visibles lorsque les utilisateurs parcourent les données d'une hiérarchie.</span><span class="sxs-lookup"><span data-stu-id="6c32d-103">If an attribute has a large number of members, you can choose to group those members into buckets, reducing the number of members that users see when they browse the data in a hierarchy.</span></span> <span data-ttu-id="6c32d-104">Vous pouvez également déterminer le nombre de compartiments dans lesquels sont groupés les membres et définir un schéma d'attribution de noms pour les compartiments.</span><span class="sxs-lookup"><span data-stu-id="6c32d-104">You can also determine the number of buckets in which the members are groups and set a naming scheme for the buckets.</span></span> <span data-ttu-id="6c32d-105">Pour plus d’informations, consultez [Regrouper des membres d’un attribut &#40;discrétisation&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="6c32d-105">For more information, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
 <span data-ttu-id="6c32d-106">Pour grouper les membres, vous devez configurer la propriété **DiscretizationMethod** à laquelle vous pouvez accéder par le biais de la fenêtre **Propriétés** dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c32d-106">You group members by setting the **DiscretizationMethod** property, which is accessed through the **Properties** window in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="6c32d-107">Lorsque vous créez des groupes de membres, vos modifications ne sont pas mises à la disposition des utilisateurs avant le traitement de la dimension.</span><span class="sxs-lookup"><span data-stu-id="6c32d-107">When you create member groups, your changes are not available to users until you process the dimension.</span></span> <span data-ttu-id="6c32d-108">Pour plus d’informations, consultez traitement de l' [objet de modèle multidimensionnel](processing-a-multidimensional-model-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="6c32d-108">For more information, see [Multidimensional Model Object Processing](processing-a-multidimensional-model-analysis-services.md).</span></span>  
  
### <a name="to-create-member-groups"></a><span data-ttu-id="6c32d-109">Pour créer des groupes de membres</span><span class="sxs-lookup"><span data-stu-id="6c32d-109">To create member groups</span></span>  
  
1.  <span data-ttu-id="6c32d-110">Ouvrez la dimension que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="6c32d-110">Open the dimension that you want to work with.</span></span> <span data-ttu-id="6c32d-111">L’onglet **Structure de dimension** s’ouvre par défaut.</span><span class="sxs-lookup"><span data-stu-id="6c32d-111">The **Dimension Structure** tab opens by default.</span></span>  
  
2.  <span data-ttu-id="6c32d-112">Dans **Attributs**, cliquez avec le bouton droit sur l’attribut dont vous voulez grouper les membres, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="6c32d-112">In **Attributes**, right-click the attribute whose members you want to group, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="6c32d-113">Dans la liste déroulante à côté de **DiscretizationMethod**, sélectionnez la méthode à utiliser pour grouper les membres.</span><span class="sxs-lookup"><span data-stu-id="6c32d-113">From the drop-down list next to **DiscretizationMethod**, select a method by which to group the members.</span></span> <span data-ttu-id="6c32d-114">Pour plus d’informations sur les paramètres de la propriété **DiscretizationMethod**, consultez [Regrouper des membres d’un attribut &#40;discrétisation&#41;](attribute-properties-group-attribute-members.md).</span><span class="sxs-lookup"><span data-stu-id="6c32d-114">For more information about **DiscretizationMethod** settings, see [Group Attribute Members &#40;Discretization&#41;](attribute-properties-group-attribute-members.md).</span></span>  
  
  
