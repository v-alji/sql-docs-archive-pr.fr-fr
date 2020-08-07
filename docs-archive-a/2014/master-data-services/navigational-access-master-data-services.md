---
title: Accès de navigation (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- navigational access [Master Data Services]
- security [Master Data Services], navigational access
ms.assetid: 3403b7b0-44e2-48c3-a1b7-9c4612b874b8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 7af3c16d98320b6fea3d4611e9e4c6d37c6015bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600107"
---
# <a name="navigational-access-master-data-services"></a><span data-ttu-id="35f9e-102">Accès de navigation (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="35f9e-102">Navigational Access (Master Data Services)</span></span>
  <span data-ttu-id="35f9e-103">L’accès de navigation s’applique à la sécurité de l’objet modèle, affectée sous l’onglet **Modèles** .</span><span class="sxs-lookup"><span data-stu-id="35f9e-103">Navigational access applies to model object security, which is assigned on the **Models** tab.</span></span>  
  
 <span data-ttu-id="35f9e-104">L’accès de navigation désigne l’accès aux niveaux supérieurs par rapport à ceux auxquels vous avez affecté une sécurité.</span><span class="sxs-lookup"><span data-stu-id="35f9e-104">Navigational access is the access you get to levels higher than where you've assigned security.</span></span>  
  
 <span data-ttu-id="35f9e-105">Dans cet exemple, les autorisations sont affectées à une entité, et donc l'accès de navigation est accordé au niveau du modèle.</span><span class="sxs-lookup"><span data-stu-id="35f9e-105">In this example, permissions are assigned to an entity, and so navigational access is granted at the model level.</span></span>  
  
 <span data-ttu-id="35f9e-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span><span class="sxs-lookup"><span data-stu-id="35f9e-106">![mds_conc_inheritance_model](../../2014/master-data-services/media/mds-conc-inheritance-model.gif "mds_conc_inheritance_model")</span></span>  
  
 <span data-ttu-id="35f9e-107">**Entités**</span><span class="sxs-lookup"><span data-stu-id="35f9e-107">**Entities**</span></span>  
  
 <span data-ttu-id="35f9e-108">Lorsque vous affectez une autorisation à une entité, ses membres feuilles ou ses membres consolidés, l'accès de navigation signifie que vous pouvez lire ou mettre à jour le nom et le code de tous les membres.</span><span class="sxs-lookup"><span data-stu-id="35f9e-108">When you assign permission to an entity, its leaf members, or its consolidated members, navigational access means you can read or update the name and code for all members.</span></span> <span data-ttu-id="35f9e-109">Vous pouvez également lire le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="35f9e-109">You can also read the model name.</span></span>  
  
 <span data-ttu-id="35f9e-110">**Attributs**</span><span class="sxs-lookup"><span data-stu-id="35f9e-110">**Attributes**</span></span>  
  
 <span data-ttu-id="35f9e-111">Lorsque vous affectez une autorisation à un attribut, l'accès de navigation signifie que vous pouvez lire ou mettre à jour le nom et le code de tous les membres dans l'entité.</span><span class="sxs-lookup"><span data-stu-id="35f9e-111">When you assign permission to an attribute, navigational access means you can read or update the name and code for all members in the entity.</span></span> <span data-ttu-id="35f9e-112">Vous pouvez également lire le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="35f9e-112">You can also read the model name.</span></span>  
  
 <span data-ttu-id="35f9e-113">**Regroupements**</span><span class="sxs-lookup"><span data-stu-id="35f9e-113">**Collections**</span></span>  
  
 <span data-ttu-id="35f9e-114">Lorsque vous affectez des autorisations aux collections, vous pouvez lire ou mettre à jour le nom, le code, la description et l'ID de propriétaire.</span><span class="sxs-lookup"><span data-stu-id="35f9e-114">When you assign permissions to collections, you can read or update the name, code, description and owner ID.</span></span> <span data-ttu-id="35f9e-115">Vous pouvez également lire le nom du modèle.</span><span class="sxs-lookup"><span data-stu-id="35f9e-115">You can also read the model name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f9e-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="35f9e-116">See Also</span></span>  
 [<span data-ttu-id="35f9e-117">Mode de détermination des autorisations &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="35f9e-117">How Permissions Are Determined &#40;Master Data Services&#41;</span></span>](how-permissions-are-determined-master-data-services.md)  
  
  
