---
title: Éditeur de transformation de copie de colonne | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copymaptransformation.f1
helpviewer_keywords:
- Copy Column Transformation Editor
ms.assetid: d8e70541-d563-4ce4-bf66-bc888a0d3026
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7647d25891b37e5f09356d427072e84b45882e4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610791"
---
# <a name="copy-column-transformation-editor"></a><span data-ttu-id="ab422-102">Éditeur de transformation de copie de colonne</span><span class="sxs-lookup"><span data-stu-id="ab422-102">Copy Column Transformation Editor</span></span>
  <span data-ttu-id="ab422-103">Utilisez la boîte de dialogue **Éditeur de transformation de copie de colonne** pour sélectionner des colonnes à copier et attribuer des noms aux nouvelles colonnes de sortie.</span><span class="sxs-lookup"><span data-stu-id="ab422-103">Use the **Copy Column Transformation Editor** dialog box to select columns to copy and to assign names for the new output columns.</span></span>  
  
 <span data-ttu-id="ab422-104">Pour en savoir plus sur la transformation de copie de colonne, consultez [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ab422-104">To learn more about the Copy Column transformation, see [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ab422-105">Si vous copiez simplement toutes vos données sources vers une destination, l'utilisation de la transformation de copie de colonne peut ne pas être obligatoire.</span><span class="sxs-lookup"><span data-stu-id="ab422-105">When you are simply copying all of your source data to a destination, it may not be necessary to use the Copy Column transformation.</span></span> <span data-ttu-id="ab422-106">Dans certains scénarios, vous pouvez connecter une source directement à une destination, lorsque aucune transformation de données n'est requise.</span><span class="sxs-lookup"><span data-stu-id="ab422-106">In some scenarios, you can connect a source directly to a destination, when no data transformation is required.</span></span> <span data-ttu-id="ab422-107">Dans ces circonstances, il est souvent préférable d'utiliser l'Assistant Importation et Exportation SQL Server pour créer votre package.</span><span class="sxs-lookup"><span data-stu-id="ab422-107">In these circumstances it is often preferable to use the SQL Server Import and Export Wizard to create your package for you.</span></span> <span data-ttu-id="ab422-108">Ultérieurement, vous pouvez améliorer et reconfigurer le package selon les besoins.</span><span class="sxs-lookup"><span data-stu-id="ab422-108">Later you can enhance and reconfigure the package as needed.</span></span> <span data-ttu-id="ab422-109">Pour plus d'informations, consultez [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="ab422-109">For more information, see [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ab422-110">Options</span><span class="sxs-lookup"><span data-stu-id="ab422-110">Options</span></span>  
 <span data-ttu-id="ab422-111">**Colonnes d'entrée disponibles**</span><span class="sxs-lookup"><span data-stu-id="ab422-111">**Available Input Columns**</span></span>  
 <span data-ttu-id="ab422-112">Utilisez les cases à cocher pour sélectionner les colonnes à copier.</span><span class="sxs-lookup"><span data-stu-id="ab422-112">Select columns to copy by using the check boxes.</span></span> <span data-ttu-id="ab422-113">Les sélections ajoutent des colonnes d'entrée à la table ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ab422-113">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="ab422-114">**Colonne d'entrée**</span><span class="sxs-lookup"><span data-stu-id="ab422-114">**Input Column**</span></span>  
 <span data-ttu-id="ab422-115">Sélectionnez dans la liste les colonnes d'entrée à copier.</span><span class="sxs-lookup"><span data-stu-id="ab422-115">Select columns to copy from the list of available input columns.</span></span> <span data-ttu-id="ab422-116">Vos sélections se reflètent dans les sélections des cases à cocher de la table **Colonnes d'entrée disponibles** .</span><span class="sxs-lookup"><span data-stu-id="ab422-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="ab422-117">**Alias de sortie**</span><span class="sxs-lookup"><span data-stu-id="ab422-117">**Output Alias**</span></span>  
 <span data-ttu-id="ab422-118">Tapez un alias pour chaque nouvelle colonne de sortie.</span><span class="sxs-lookup"><span data-stu-id="ab422-118">Type an alias for each new output column.</span></span> <span data-ttu-id="ab422-119">Le nom par défaut est **Copie de**suivi du nom de la colonne d'entrée ; vous pouvez néanmoins choisir un nom unique et descriptif.</span><span class="sxs-lookup"><span data-stu-id="ab422-119">The default is **Copy of**, followed by the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab422-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab422-120">See Also</span></span>  
 [<span data-ttu-id="ab422-121">Guide de référence des erreurs et des messages propres à Integration Services</span><span class="sxs-lookup"><span data-stu-id="ab422-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
