---
title: Apporter des modifications aux tables sélectionnées pour capturer les modifications | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- makChanToTab
ms.assetid: a309f82a-c6ef-464d-a6ef-df555bfb609a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 258eb8e761ac697bebd630cc0e627941b4ffc7d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602963"
---
# <a name="make-changes-to-the-tables-selected-for-capturing-changes"></a><span data-ttu-id="6292f-102">Apporter des modifications aux tables sélectionnées pour capturer les modifications</span><span class="sxs-lookup"><span data-stu-id="6292f-102">Make Changes to the Tables Selected for Capturing Changes</span></span>
  <span data-ttu-id="6292f-103">Cette boîte de dialogue, vous permet de sélectionner des colonnes spécifiques de la table sélectionnée pour la capture des modifications.</span><span class="sxs-lookup"><span data-stu-id="6292f-103">In this dialog box, you can select specific columns from the selected table to capture changes from.</span></span> <span data-ttu-id="6292f-104">Vous pouvez également modifier les informations du **Rôle de sécurité** et de l' **Instance de capture** .</span><span class="sxs-lookup"><span data-stu-id="6292f-104">You can also edit the **Security Role** and **Capture Instance** information.</span></span>  
  
 <span data-ttu-id="6292f-105">Vous pouvez apporter les modifications suivantes aux tables sélectionnées pour capturer les modifications dans cette boîte de dialogue.</span><span class="sxs-lookup"><span data-stu-id="6292f-105">You can make the following changes to the tables you selected for capturing changes in this dialog box.</span></span>  
  
 <span data-ttu-id="6292f-106">**Apporter des modifications aux colonnes incluses dans l'instance de capture de données modifiées :**</span><span class="sxs-lookup"><span data-stu-id="6292f-106">**Make changes to which columns are included in the CDC instance:**</span></span>  
  
 <span data-ttu-id="6292f-107">Effectuez une des actions suivantes ou les deux :</span><span class="sxs-lookup"><span data-stu-id="6292f-107">Do one or both of the following:</span></span>  
  
-   <span data-ttu-id="6292f-108">Activez la case à cocher en regard des colonnes supplémentaires à inclure.</span><span class="sxs-lookup"><span data-stu-id="6292f-108">Select the check box next to any additional column you want to include.</span></span>  
  
-   <span data-ttu-id="6292f-109">Désactivez la case à cocher en regard des colonnes que vous ne souhaitez plus inclure.</span><span class="sxs-lookup"><span data-stu-id="6292f-109">Clear the check box next to any column that you no longer want to include.</span></span>  
  
 <span data-ttu-id="6292f-110">**Modifier le type de données d'une colonne spécifique**:</span><span class="sxs-lookup"><span data-stu-id="6292f-110">**Change the data type for a specific column**:</span></span>  
  
 <span data-ttu-id="6292f-111">Vous pouvez sélectionner un type de données différent pour une colonne spécifique.</span><span class="sxs-lookup"><span data-stu-id="6292f-111">You can select a different data type for a specific column.</span></span> <span data-ttu-id="6292f-112">Vous ne pouvez remplacer le type de données que par un type de données compatible avec le type de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="6292f-112">You can only change the data type to a data type that is compatible with the original data type.</span></span>  
  
 <span data-ttu-id="6292f-113">Pour changer de type de données, cliquez dans la colonne **Type de données** , puis sélectionnez un autre type de données.</span><span class="sxs-lookup"><span data-stu-id="6292f-113">To change the data type, click in the **Data Type** column and select a different data type.</span></span> <span data-ttu-id="6292f-114">Seuls les types de données compatibles avec le type de données d'origine sont disponibles.</span><span class="sxs-lookup"><span data-stu-id="6292f-114">Only data types that are compatible with the original data type are available.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6292f-115">Si aucun type de données supplémentaire ne peut être sélectionné, la liste déroulante n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="6292f-115">If no additional data types can be selected, the drop-down list is not available.</span></span>  
  
 <span data-ttu-id="6292f-116">**Modifier le rôle de sécurité**</span><span class="sxs-lookup"><span data-stu-id="6292f-116">**Change the Security Role**</span></span>  
  
 <span data-ttu-id="6292f-117">Tapez un nouveau nom ou modifiez le rôle de régulation de la sécurité dans le champ **Rôle de sécurité** .</span><span class="sxs-lookup"><span data-stu-id="6292f-117">Type a new name or edit the name of the security gating role in the **Security Role** field.</span></span>  
  
 <span data-ttu-id="6292f-118">**Modifier ou ajouter une instance de capture**</span><span class="sxs-lookup"><span data-stu-id="6292f-118">**Change or add a capture instance**</span></span>  
  
 <span data-ttu-id="6292f-119">Dans le champ **Instance de capture** , entrez un nom pour l'instance de capture.</span><span class="sxs-lookup"><span data-stu-id="6292f-119">In the **Capture Instance** field enter a name for the capture instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6292f-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6292f-120">See Also</span></span>  
 <span data-ttu-id="6292f-121">[Procédure : créer l'instance SQL Server de base de données de modifications](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="6292f-121">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="6292f-122">Sélectionner des tables et des colonnes Oracle</span><span class="sxs-lookup"><span data-stu-id="6292f-122">Select Oracle Tables and Columns</span></span>](select-oracle-tables-and-columns.md)  
  
  
