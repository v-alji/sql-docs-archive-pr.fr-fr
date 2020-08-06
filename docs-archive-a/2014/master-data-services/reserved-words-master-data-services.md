---
title: Mots réservés (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c54bb371cd8f797cfb36f015387e0e21339c0426
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610707"
---
# <a name="reserved-words-master-data-services"></a><span data-ttu-id="94355-102">Mots réservés (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="94355-102">Reserved Words (Master Data Services)</span></span>
  <span data-ttu-id="94355-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lorsque vous créez des objets de modèle ou des membres, certains mots ne peuvent pas être utilisés.</span><span class="sxs-lookup"><span data-stu-id="94355-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], when you create model objects or members, some words cannot be used.</span></span> <span data-ttu-id="94355-104">Ces mots peuvent provoquer des erreurs.</span><span class="sxs-lookup"><span data-stu-id="94355-104">Using these words may cause errors.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="94355-105">Vous devez également limiter votre utilisation des caractères spéciaux (symboles, césure, etc.).</span><span class="sxs-lookup"><span data-stu-id="94355-105">You should also limit your use of special characters (symbols, hyphenation, etc.).</span></span>  
  
-   [<span data-ttu-id="94355-106">Modèles</span><span class="sxs-lookup"><span data-stu-id="94355-106">Models</span></span>](#models)  
  
-   [<span data-ttu-id="94355-107">Entités</span><span class="sxs-lookup"><span data-stu-id="94355-107">Entities</span></span>](#entities)  
  
-   [<span data-ttu-id="94355-108">Hiérarchies explicites</span><span class="sxs-lookup"><span data-stu-id="94355-108">Explicit Hierarchies</span></span>](#exhierarchies)  
  
-   [<span data-ttu-id="94355-109">Attributs</span><span class="sxs-lookup"><span data-stu-id="94355-109">Attributes</span></span>](#attributes)  
  
-   [<span data-ttu-id="94355-110">Membres</span><span class="sxs-lookup"><span data-stu-id="94355-110">Members</span></span>](#members)  
  
##  <a name="models"></a><a name="models"></a><span data-ttu-id="94355-111">Axisymétriques</span><span class="sxs-lookup"><span data-stu-id="94355-111">Models</span></span>  
 <span data-ttu-id="94355-112">Si vous créez un modèle dont le nom est défini sur **nom**, ne sélectionnez pas **créer une entité portant le même nom que le modèle** , car le nom ne peut pas être utilisé pour le nom d’une entité. **Name**</span><span class="sxs-lookup"><span data-stu-id="94355-112">If you create a model with the name set to **Name**, do not select **Create entity with same name as model** because **Name** cannot be used for the name of an entity.</span></span>  
  
##  <a name="entities"></a><a name="entities"></a><span data-ttu-id="94355-113">Lesquelles</span><span class="sxs-lookup"><span data-stu-id="94355-113">Entities</span></span>  
 <span data-ttu-id="94355-114">Pour les noms d'entité, vous ne pouvez pas utiliser **Name** ou **Code**.</span><span class="sxs-lookup"><span data-stu-id="94355-114">For entity names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a><span data-ttu-id="94355-115">Hiérarchies explicites</span><span class="sxs-lookup"><span data-stu-id="94355-115">Explicit Hierarchies</span></span>  
 <span data-ttu-id="94355-116">Pour les noms de hiérarchies explicites, vous ne pouvez pas utiliser **Name** ou **Code**.</span><span class="sxs-lookup"><span data-stu-id="94355-116">For explicit hierarchy names, you cannot use **Name** or **Code**.</span></span>  
  
##  <a name="attributes"></a><a name="attributes"></a><span data-ttu-id="94355-117">Attributs</span><span class="sxs-lookup"><span data-stu-id="94355-117">Attributes</span></span>  
  
-   <span data-ttu-id="94355-118">**Identifiant**</span><span class="sxs-lookup"><span data-stu-id="94355-118">**ID**</span></span>  
  
-   <span data-ttu-id="94355-119">**Code**</span><span class="sxs-lookup"><span data-stu-id="94355-119">**Code**</span></span>  
  
-   <span data-ttu-id="94355-120">**Nom**</span><span class="sxs-lookup"><span data-stu-id="94355-120">**Name**</span></span>  
  
-   <span data-ttu-id="94355-121">**EnterDTM**</span><span class="sxs-lookup"><span data-stu-id="94355-121">**EnterDTM**</span></span>  
  
-   <span data-ttu-id="94355-122">**EnterUserID**</span><span class="sxs-lookup"><span data-stu-id="94355-122">**EnterUserID**</span></span>  
  
-   <span data-ttu-id="94355-123">**EnterUserName**</span><span class="sxs-lookup"><span data-stu-id="94355-123">**EnterUserName**</span></span>  
  
-   <span data-ttu-id="94355-124">**LastChgDTM**</span><span class="sxs-lookup"><span data-stu-id="94355-124">**LastChgDTM**</span></span>  
  
-   <span data-ttu-id="94355-125">**LastChgUserID**</span><span class="sxs-lookup"><span data-stu-id="94355-125">**LastChgUserID**</span></span>  
  
-   <span data-ttu-id="94355-126">**Status_ID**</span><span class="sxs-lookup"><span data-stu-id="94355-126">**Status_ID**</span></span>  
  
-   <span data-ttu-id="94355-127">**ValidationStatus_ID**</span><span class="sxs-lookup"><span data-stu-id="94355-127">**ValidationStatus_ID**</span></span>  
  
-   <span data-ttu-id="94355-128">**Version_ID**</span><span class="sxs-lookup"><span data-stu-id="94355-128">**Version_ID**</span></span>  
  
##  <a name="members"></a><a name="members"></a><span data-ttu-id="94355-129">Membres</span><span class="sxs-lookup"><span data-stu-id="94355-129">Members</span></span>  
 <span data-ttu-id="94355-130">Pour les membres, vous ne pouvez pas utiliser **MDMMemberStatus** ou **root** pour la valeur de l’attribut **code** .</span><span class="sxs-lookup"><span data-stu-id="94355-130">For members, you cannot use **MDMMemberStatus** or **ROOT** for the **Code** attribute value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94355-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="94355-131">See Also</span></span>  
 [<span data-ttu-id="94355-132">Vue d'ensemble de Master Data Services</span><span class="sxs-lookup"><span data-stu-id="94355-132">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
  
