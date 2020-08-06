---
title: Membres de la dimension inférés (Assistant Dimension à variation lente) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.inferrdim.f1
ms.assetid: 809e395f-2e10-48ff-8860-56403f130628
author: chugugrace
ms.author: chugu
ms.openlocfilehash: dda4345b91c69b134516baab2e5ba9b9990bd6af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613053"
---
# <a name="inferred-dimension-members-slowly-changing-dimension-wizard"></a><span data-ttu-id="e9247-102">Membres de la dimension inférés (Assistant Dimension à variation lente)</span><span class="sxs-lookup"><span data-stu-id="e9247-102">Inferred Dimension Members (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="e9247-103">La boîte de dialogue **Membres de la dimension inférés** vous permet de spécifier les options d'utilisation des membres inférés.</span><span class="sxs-lookup"><span data-stu-id="e9247-103">Use the **Inferred Dimension Members** dialog box to specify options for using inferred members.</span></span> <span data-ttu-id="e9247-104">Des membres inférés existent lorsqu'une table de faits fait référence à des membres de la dimension qui ne sont pas encore chargés.</span><span class="sxs-lookup"><span data-stu-id="e9247-104">Inferred members exist when a fact table references dimension members that are not yet loaded.</span></span> <span data-ttu-id="e9247-105">Lorsque les données du membre inféré sont chargées, vous pouvez mettre à jour l'enregistrement existant au lieu d'en créer un.</span><span class="sxs-lookup"><span data-stu-id="e9247-105">When data for the inferred member is loaded, you can update the existing record rather than create a new one.</span></span>  
  
 <span data-ttu-id="e9247-106">Pour en savoir plus sur cet Assistant, consultez [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="e9247-106">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e9247-107">Options</span><span class="sxs-lookup"><span data-stu-id="e9247-107">Options</span></span>  
 <span data-ttu-id="e9247-108">**Activer la prise en charge des membres inférés**</span><span class="sxs-lookup"><span data-stu-id="e9247-108">**Enable inferred member support**</span></span>  
 <span data-ttu-id="e9247-109">Si vous décidez d'activer les membres inférés, vous devez sélectionner l'une des deux options ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e9247-109">If you choose to enable inferred members, you must select one of the two options that follow.</span></span>  
  
 <span data-ttu-id="e9247-110">**Toutes les colonnes dont le type est modifié sont NULL**</span><span class="sxs-lookup"><span data-stu-id="e9247-110">**All columns with a change type are null**</span></span>  
 <span data-ttu-id="e9247-111">Indique s'il convient d'entrer des valeurs NULL dans toutes les colonnes avec un type de modification dans le nouvel enregistrement de membre inféré.</span><span class="sxs-lookup"><span data-stu-id="e9247-111">Specify whether to enter null values in all columns with a change type in the new inferred member record.</span></span>  
  
 <span data-ttu-id="e9247-112">**Utiliser une colonne de valeurs booléennes pour indiquer si l'enregistrement actif est un membre inféré**</span><span class="sxs-lookup"><span data-stu-id="e9247-112">**Use a Boolean column to indicate whether the current record is an inferred member**</span></span>  
 <span data-ttu-id="e9247-113">Indique s'il convient d'utiliser une colonne de valeurs booléennes existante pour indiquer si l'enregistrement en cours est un membre inféré.</span><span class="sxs-lookup"><span data-stu-id="e9247-113">Specify whether to use an existing Boolean column to indicate whether the current record is an inferred member.</span></span>  
  
 <span data-ttu-id="e9247-114">**Indicateur de membre inféré**</span><span class="sxs-lookup"><span data-stu-id="e9247-114">**Inferred member indicator**</span></span>  
 <span data-ttu-id="e9247-115">Si vous avez choisi d'utiliser une colonne de valeurs booléennes pour indiquer les membres inférés comme décrit ci-dessus, sélectionnez la colonne dans la liste.</span><span class="sxs-lookup"><span data-stu-id="e9247-115">If you have chosen to use a Boolean column to indicate inferred members as described above, select the column from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9247-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e9247-116">See Also</span></span>  
 [<span data-ttu-id="e9247-117">Configurer les sorties à l'aide de l'Assistant Dimension à variation lente</span><span class="sxs-lookup"><span data-stu-id="e9247-117">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
