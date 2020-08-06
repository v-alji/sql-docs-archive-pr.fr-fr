---
title: Modifier le nom d’un attribut (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], changing name
ms.assetid: d348f238-f59d-41c7-ad20-3ccd55bfd9e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: abbe5f666daed42b25b46f02e954343b57446145
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703059"
---
# <a name="change-an-attribute-name-master-data-services"></a><span data-ttu-id="1541e-102">Modifier le nom d'un attribut (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1541e-102">Change an Attribute Name (Master Data Services)</span></span>
  <span data-ttu-id="1541e-103">Dans [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], vous pouvez modifier le nom d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="1541e-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], you can change the name of an attribute.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1541e-104">Prérequis</span><span class="sxs-lookup"><span data-stu-id="1541e-104">Prerequisites</span></span>  
 <span data-ttu-id="1541e-105">Pour effectuer cette procédure :</span><span class="sxs-lookup"><span data-stu-id="1541e-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="1541e-106">Vous devez avoir l'autorisation d'accéder à la zone fonctionnelle **Administration de système** .</span><span class="sxs-lookup"><span data-stu-id="1541e-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="1541e-107">Vous devez être administrateur de modèle.</span><span class="sxs-lookup"><span data-stu-id="1541e-107">You must be a model administrator.</span></span> <span data-ttu-id="1541e-108">Pour plus d’informations, consultez [administrateurs &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1541e-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-change-an-attribute-name"></a><span data-ttu-id="1541e-109">Pour modifier le nom d'un attribut</span><span class="sxs-lookup"><span data-stu-id="1541e-109">To change an attribute name</span></span>  
  
1.  <span data-ttu-id="1541e-110">Dans [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], cliquez sur **Administration de système**.</span><span class="sxs-lookup"><span data-stu-id="1541e-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="1541e-111">Dans la page **Vue du modèle** , dans la barre de menus, pointez sur **Gérer** , puis cliquez sur **Entités**.</span><span class="sxs-lookup"><span data-stu-id="1541e-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="1541e-112">Dans la page **Maintenance de l'entité** , dans la liste **Modèle** , sélectionnez un modèle.</span><span class="sxs-lookup"><span data-stu-id="1541e-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="1541e-113">Cliquez sur la ligne de l'entité qui contient l'attribut dont vous souhaitez modifier le nom.</span><span class="sxs-lookup"><span data-stu-id="1541e-113">Click the row for the entity that contains the attribute with the name you want to change.</span></span>  
  
5.  <span data-ttu-id="1541e-114">Cliquez sur **Modifier l'entité sélectionnée**.</span><span class="sxs-lookup"><span data-stu-id="1541e-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="1541e-115">Dans la page **modifier l’entité** , cliquez sur l’attribut dont vous souhaitez modifier le nom.</span><span class="sxs-lookup"><span data-stu-id="1541e-115">On the **Edit Entity** page, click the attribute with the name you want to change.</span></span>  
  
7.  <span data-ttu-id="1541e-116">Cliquez sur **modifier l’attribut sélectionné**.</span><span class="sxs-lookup"><span data-stu-id="1541e-116">Click **Edit selected attribute**.</span></span>  
  
8.  <span data-ttu-id="1541e-117">Dans la zone **Nom** , entrez le nom mis à jour de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="1541e-117">In the **Name** box, type the updated name of the attribute.</span></span> <span data-ttu-id="1541e-118">Pour obtenir la liste des mots qui ne doivent pas être utilisés comme noms d’attribut, consultez la section [Mots réservés &#40;Master Data Services&#41;](reserved-words-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1541e-118">For a list of words that should not be used as attribute names, see [Reserved Words &#40;Master Data Services&#41;](reserved-words-master-data-services.md).</span></span>  
  
9. <span data-ttu-id="1541e-119">Cliquez sur **Enregistrer l'attribut**.</span><span class="sxs-lookup"><span data-stu-id="1541e-119">Click **Save attribute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1541e-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1541e-120">See Also</span></span>  
 <span data-ttu-id="1541e-121">[Créez un attribut de texte &#40;Master Data Services&#41;](create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1541e-121">[Create a Text Attribute &#40;Master Data Services&#41;](create-a-text-attribute-master-data-services.md) </span></span>  
 <span data-ttu-id="1541e-122">[Supprimer un attribut &#40;Master Data Services&#41;](delete-an-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="1541e-122">[Delete an Attribute &#40;Master Data Services&#41;](delete-an-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="1541e-123">Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1541e-123">Attributes &#40;Master Data Services&#41;</span></span>](attributes-master-data-services.md)  
  
  
