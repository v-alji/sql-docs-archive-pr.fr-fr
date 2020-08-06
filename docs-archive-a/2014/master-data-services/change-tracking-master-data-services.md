---
title: Suivi des modifications (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server]
ms.assetid: 5e879c65-0d38-454f-9a20-62a6e72c89f7
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2d3b69057b02884f41a43aa9a009ab3db937ed25
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701280"
---
# <a name="change-tracking-master-data-services"></a><span data-ttu-id="b434c-102">Suivi des modifications (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="b434c-102">Change Tracking (Master Data Services)</span></span>
  <span data-ttu-id="b434c-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez utiliser des groupes de suivi des modifications pour agir lorsqu'une valeur d'attribut change.</span><span class="sxs-lookup"><span data-stu-id="b434c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can use change tracking groups to take action when an attribute value changes.</span></span> <span data-ttu-id="b434c-104">Utilisez le suivi des modifications quand vous ne savez pas ce que sera la nouvelle valeur, mais souhaitez à la place savoir si une modification est intervenue.</span><span class="sxs-lookup"><span data-stu-id="b434c-104">Use change tracking when you don't know what the new value will be, but instead want to know if any change occurred.</span></span>  
  
## <a name="configuring-change-tracking"></a><span data-ttu-id="b434c-105">Configuration du suivi des modifications</span><span class="sxs-lookup"><span data-stu-id="b434c-105">Configuring Change Tracking</span></span>  
 <span data-ttu-id="b434c-106">Pour configurer le suivi des modifications, vous ajoutez un attribut à un groupe de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="b434c-106">To configure change tracking, you add an attribute to a change tracking group.</span></span> <span data-ttu-id="b434c-107">Le groupe peut contenir un ou plusieurs attributs.</span><span class="sxs-lookup"><span data-stu-id="b434c-107">The group can contain one or many attributes.</span></span> <span data-ttu-id="b434c-108">Ensuite, vous créez une règle d'entreprise pour définir l'action effectuée lorsque l'un des attributs du groupe change.</span><span class="sxs-lookup"><span data-stu-id="b434c-108">Then, you create a business rule to define the action that is taken when any of the attributes in the group change.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b434c-109">Les règles d'entreprise de suivi des modifications considèrent les données (importées) mises en lots à modifier.</span><span class="sxs-lookup"><span data-stu-id="b434c-109">Change tracking business rules consider staged (imported) data to be changed.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="b434c-110">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="b434c-110">Related Tasks</span></span>  
  
|<span data-ttu-id="b434c-111">Description de la tâche</span><span class="sxs-lookup"><span data-stu-id="b434c-111">Task Description</span></span>|<span data-ttu-id="b434c-112">Rubrique</span><span class="sxs-lookup"><span data-stu-id="b434c-112">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="b434c-113">Ajoutez des attributs à un groupe de suivi des modifications.</span><span class="sxs-lookup"><span data-stu-id="b434c-113">Add attributes to a change tracking group.</span></span>|[<span data-ttu-id="b434c-114">Ajouter des attributs à un groupe de suivi des modifications &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b434c-114">Add Attributes to a Change Tracking Group &#40;Master Data Services&#41;</span></span>](add-attributes-to-a-change-tracking-group-master-data-services.md)|  
|<span data-ttu-id="b434c-115">Créez une règle d'entreprise qui initie les actions en fonction des modifications apportées aux attributs.</span><span class="sxs-lookup"><span data-stu-id="b434c-115">Create a business rule that initiates actions based on attribute changes.</span></span>|[<span data-ttu-id="b434c-116">Initier des actions en fonction de modifications de valeurs d’attribut &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b434c-116">Initiate Actions Based on Attribute Value Changes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/initiate-actions-based-on-attribute-value-changes-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="b434c-117">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="b434c-117">Related Content</span></span>  
  
-   [<span data-ttu-id="b434c-118">Validation &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b434c-118">Validation &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validation-master-data-services.md)  
  
-   [<span data-ttu-id="b434c-119">Règles d’entreprise &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b434c-119">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="b434c-120">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="b434c-120">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
  
