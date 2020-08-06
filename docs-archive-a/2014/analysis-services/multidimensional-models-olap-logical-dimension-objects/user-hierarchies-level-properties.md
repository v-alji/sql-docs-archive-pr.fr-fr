---
title: Propriétés de niveau | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- user hierarchies [Analysis Services]
- hierarchies [Analysis Services], user
ms.assetid: dabb7335-887b-442a-b67c-4901ba1242b7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 553503b9d35142bcc998b4ec12ad2e29d4c66318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601755"
---
# <a name="level-properties"></a><span data-ttu-id="77228-102">Propriétés de niveau</span><span class="sxs-lookup"><span data-stu-id="77228-102">Level Properties</span></span> 
  <span data-ttu-id="77228-103">Le tableau suivant répertorie et décrit les propriétés d'un niveau dans une hiérarchie définie par l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="77228-103">The following table lists and describes the properties of a level in a user-defined hierarchy.</span></span>  
  
|<span data-ttu-id="77228-104">Propriété</span><span class="sxs-lookup"><span data-stu-id="77228-104">Property</span></span>|<span data-ttu-id="77228-105">Description</span><span class="sxs-lookup"><span data-stu-id="77228-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="77228-106">Description</span><span class="sxs-lookup"><span data-stu-id="77228-106">Description</span></span>|<span data-ttu-id="77228-107">Contient la description du niveau.</span><span class="sxs-lookup"><span data-stu-id="77228-107">Contains the description of the level.</span></span>|  
|<span data-ttu-id="77228-108">HideMemberIf</span><span class="sxs-lookup"><span data-stu-id="77228-108">HideMemberIf</span></span>|<span data-ttu-id="77228-109">Indique si et quand un membre d'un niveau doit être masqué par rapport aux applications clientes.</span><span class="sxs-lookup"><span data-stu-id="77228-109">Indicates whether and when a member in a level should be hidden from client applications.</span></span> <span data-ttu-id="77228-110">Cette propriété peut avoir les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="77228-110">This property can have the following values:</span></span><br /><br /> <span data-ttu-id="77228-111">Jamais</span><span class="sxs-lookup"><span data-stu-id="77228-111">Never</span></span><br /> <span data-ttu-id="77228-112">Les membres ne sont jamais masqués.</span><span class="sxs-lookup"><span data-stu-id="77228-112">Members are never hidden.</span></span> <span data-ttu-id="77228-113">Valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="77228-113">This is the default value.</span></span><br /><br /> <span data-ttu-id="77228-114">OnlyChildWithNoName</span><span class="sxs-lookup"><span data-stu-id="77228-114">OnlyChildWithNoName</span></span><br /> <span data-ttu-id="77228-115">Le membre est masqué s'il est le seul enfant de son parent et que son nom est vide.</span><span class="sxs-lookup"><span data-stu-id="77228-115">A member is hidden when the member is the only child of its parent and the member's name is empty.</span></span><br /><br /> <span data-ttu-id="77228-116">OnlyChildWithParentName</span><span class="sxs-lookup"><span data-stu-id="77228-116">OnlyChildWithParentName</span></span><br /> <span data-ttu-id="77228-117">Le membre est masqué s'il est le seul enfant de son parent et qu'il a le même nom que lui.</span><span class="sxs-lookup"><span data-stu-id="77228-117">A member is hidden when the member is the only child of its parent and the member's name is identical to that of its parent.</span></span><br /><br /> <span data-ttu-id="77228-118">NoName</span><span class="sxs-lookup"><span data-stu-id="77228-118">NoName</span></span><br /> <span data-ttu-id="77228-119">Le membre est masqué si son nom est vide.</span><span class="sxs-lookup"><span data-stu-id="77228-119">A member is hidden when the member's name is empty.</span></span><br /><br /> <span data-ttu-id="77228-120">ParentName</span><span class="sxs-lookup"><span data-stu-id="77228-120">ParentName</span></span><br /> <span data-ttu-id="77228-121">Le membre est masqué s'il a le même nom que son parent.</span><span class="sxs-lookup"><span data-stu-id="77228-121">A member is hidden when the member's name is identical to that of its parent.</span></span>|  
|<span data-ttu-id="77228-122">id</span><span class="sxs-lookup"><span data-stu-id="77228-122">ID</span></span>|<span data-ttu-id="77228-123">Contient l'identificateur (ID) unique du niveau.</span><span class="sxs-lookup"><span data-stu-id="77228-123">Contains the unique identifier (ID) of the level.</span></span>|  
|<span data-ttu-id="77228-124">Nom</span><span class="sxs-lookup"><span data-stu-id="77228-124">Name</span></span>|<span data-ttu-id="77228-125">Contient le nom convivial du niveau.</span><span class="sxs-lookup"><span data-stu-id="77228-125">Contains the friendly name of the level.</span></span> <span data-ttu-id="77228-126">Par défaut, le niveau a le même nom que l'attribut source.</span><span class="sxs-lookup"><span data-stu-id="77228-126">By default, the name of a level is the same as the name of the source attribute.</span></span>|  
|<span data-ttu-id="77228-127">SourceAttribute</span><span class="sxs-lookup"><span data-stu-id="77228-127">SourceAttribute</span></span>|<span data-ttu-id="77228-128">Contient le nom de l'attribut source sur lequel est basé le niveau.</span><span class="sxs-lookup"><span data-stu-id="77228-128">Contains the name of the source attribute on which the level is based.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77228-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="77228-129">See Also</span></span>  
 [<span data-ttu-id="77228-130">Propriétés de la hiérarchie définie par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="77228-130">User Hierarchy Properties</span></span>](user-hierarchies-properties.md)  
  
  
