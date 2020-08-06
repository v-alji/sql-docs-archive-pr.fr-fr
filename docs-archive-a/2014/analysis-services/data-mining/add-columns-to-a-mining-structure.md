---
title: Ajouter des colonnes à une structure d’exploration de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], columns
- columns [data mining], mining structure columns
- adding columns
ms.assetid: 3f879344-9f66-4178-851a-e8c5ccccf4cb
author: minewiskan
ms.author: owend
ms.openlocfilehash: 093d78b36ab3aae6600b890a8137025c9dc9134e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612016"
---
# <a name="add-columns-to-a-mining-structure"></a><span data-ttu-id="fe5ca-102">ajouter des colonnes à une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="fe5ca-102">Add Columns to a Mining Structure</span></span>
  <span data-ttu-id="fe5ca-103">Utilisez le Concepteur d'exploration de données dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] pour ajouter des colonnes à une structure d'exploration de données après l'avoir définie dans l'Assistant Exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-103">Use Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] to add columns to a mining structure after you have defined it in the Data Mining Wizard.</span></span> <span data-ttu-id="fe5ca-104">Vous pouvez ajouter n'importe quelle colonne qui existe dans la vue de source de données utilisée pour définir la structure d'exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-104">You can add any column that exists in the data source view that was used to define the mining structure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fe5ca-105">Vous pouvez ajouter plusieurs copies de colonnes à une structure d'exploration de données ; toutefois, vous devez éviter d'utiliser plusieurs instances de la colonne dans le même modèle, afin d'éviter de fausses corrélations entre la source et la colonne dérivée.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-105">You can add multiple copies of columns to a mining structure; however, you should avoid using more than one instance of the column within the same model, to avoid false correlations between the source and the derived column.</span></span>  
  
### <a name="to-add-a-column-to-a-mining-structure"></a><span data-ttu-id="fe5ca-106">Pour ajouter une colonne à une structure d'exploration de données</span><span class="sxs-lookup"><span data-stu-id="fe5ca-106">To add a column to a mining structure</span></span>  
  
1.  <span data-ttu-id="fe5ca-107">Sélectionnez l’onglet **Structure d’exploration de données** dans le Concepteur d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-107">Select the **Mining Structure** tab in Data Mining Designer.</span></span>  
  
2.  <span data-ttu-id="fe5ca-108">Cliquez avec le bouton droit de la souris et sélectionnez **Ajouter une colonne**.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-108">Right-click the mining structure and select **Add a Column**.</span></span>  
  
     <span data-ttu-id="fe5ca-109">La boîte de dialogue **Sélectionner une colonne** s’ouvre.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-109">The **Select a Column** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="fe5ca-110">Sous **Table source**, sélectionnez la table de la vue de source de données qui contient la colonne.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-110">Under **Source table**, select the table in the data source view where the column resides.</span></span>  
  
4.  <span data-ttu-id="fe5ca-111">Sous **Colonne source**, sélectionnez la colonne à ajouter à la structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-111">Under **Source column**, select the column that you want to add to the mining structure.</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
> [!NOTE]  
>  <span data-ttu-id="fe5ca-112">Si vous ajoutez une colonne existante, une copie est incluse dans la structure et « 1 » est ajouté au nom.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-112">If you add a column that already exists, a copy will be included in the structure, and the name appended with a "1".</span></span> <span data-ttu-id="fe5ca-113">Vous pouvez modifier le nom de la colonne copiée pour qu’elle soit plus descriptive en tapant un nouveau nom dans la propriété **Name** de la colonne de structure d’exploration de données.</span><span class="sxs-lookup"><span data-stu-id="fe5ca-113">You can change the name of the copied column to something more descriptive by typing a new name in the **Name** property of the mining structure column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5ca-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fe5ca-114">See Also</span></span>  
 [<span data-ttu-id="fe5ca-115">Tâches de la structure d'exploration de données et procédures</span><span class="sxs-lookup"><span data-stu-id="fe5ca-115">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
