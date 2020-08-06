---
title: Ajout ou suppression de tables ou de vues dans une vue de source de données (Analysis Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.dsvdesigner.tablespane.f1
helpviewer_keywords:
- deleting tables
- tables [Analysis Services]
- removing tables
- adding tables
- data source views [Analysis Services], tables
- tables [Analysis Services], data source views
ms.assetid: 98307d04-6548-4d7d-9244-2371dd165249
author: minewiskan
ms.author: owend
ms.openlocfilehash: da1bc2b1ac0af7576cfe3c3593b451f78d6a9fae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614211"
---
# <a name="adding-or-removing-tables-or-views-in-a-data-source-view-analysis-services"></a><span data-ttu-id="da36e-102">Ajout ou suppression de tables ou de vues dans une vue de source de données (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="da36e-102">Adding or Removing Tables or Views in a Data Source View (Analysis Services)</span></span>
  <span data-ttu-id="da36e-103">Après avoir créé une vue de source de données (DSV) dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], vous pouvez la modifier dans le concepteur de vue de source de données en ajoutant ou en supprimant des tables et des colonnes, y compris les tables et les colonnes d'une autre source de données.</span><span class="sxs-lookup"><span data-stu-id="da36e-103">After you have created a data source view (DSV) in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], you can modify it in Data Source View Designer by adding or removing tables and columns, including tables and columns from another data source.</span></span>  
  
 <span data-ttu-id="da36e-104">Pour ouvrir la vue DSV dans le concepteur de vue de source de données, double-cliquez sur la vue DSV dans l'Explorateur de solutions.</span><span class="sxs-lookup"><span data-stu-id="da36e-104">To open the DSV in Data Source View Designer, you double-click the DSV in Solution Explorer.</span></span> <span data-ttu-id="da36e-105">Une fois que vous avez ouvert la vue DSV, vous pouvez utiliser la commande **Ajouter/supprimer des tables** dans la barre de boutons ou le menu pour modifier ou étendre la vue DSV.</span><span class="sxs-lookup"><span data-stu-id="da36e-105">Once you open the DSV, you can use the **Add/Remove Tables** command on the button bar or menu to modify or extend the DSV.</span></span> <span data-ttu-id="da36e-106">Vous pouvez également utiliser les objets du diagramme.</span><span class="sxs-lookup"><span data-stu-id="da36e-106">You can also work with the objects in the diagram.</span></span> <span data-ttu-id="da36e-107">Par exemple, vous pouvez sélectionner un objet puis utiliser la touche Suppr de votre clavier pour supprimer un objet.</span><span class="sxs-lookup"><span data-stu-id="da36e-107">For example, you can select an object and then use the Delete key on your keyboard to remove an object.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="da36e-108">Soyez prudent lors de la suppression d'une table.</span><span class="sxs-lookup"><span data-stu-id="da36e-108">Use caution when removing a table.</span></span> <span data-ttu-id="da36e-109">La suppression d'une table supprime toutes les colonnes et relations associées de la vue DSV et invalide tous les objets liés à cette table.</span><span class="sxs-lookup"><span data-stu-id="da36e-109">Removing a table deletes all the associated columns and relationships from the DSV and invalidates all objects bound to that table.</span></span>  
  
## <a name="selecting-tables-or-views-to-add-or-remove"></a><span data-ttu-id="da36e-110">Sélection des tables ou vues à ajouter ou supprimer</span><span class="sxs-lookup"><span data-stu-id="da36e-110">Selecting Tables or Views to Add or Remove</span></span>  
 <span data-ttu-id="da36e-111">Dans la boîte de dialogue **Ajouter/supprimer des tables** , vous pouvez déplacer des tables ou des vues entre les listes **Objets disponibles** et **Objets inclus** .</span><span class="sxs-lookup"><span data-stu-id="da36e-111">Using the **Add/Remove Tables** dialog box, you can move tables or views between the **Available objects** and **Included objects** lists.</span></span> <span data-ttu-id="da36e-112">La liste **Objets disponibles** inclut à l’origine les tables ou les vues de la source de données principale qui ne se trouvent pas encore dans la vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="da36e-112">The **Available objects** list initially includes any tables or views in the primary data source that are not already in the data source view.</span></span> <span data-ttu-id="da36e-113">Si la source de données principale prend en charge la fonction `OPENROWSET`, vous pouvez également ajouter des tables ou des vues à partir d'autres sources de données dans le projet ou une base de données.</span><span class="sxs-lookup"><span data-stu-id="da36e-113">If the primary data source supports the `OPENROWSET` function, you can also add tables or views from other data sources in the project or database.</span></span>  
  
 <span data-ttu-id="da36e-114">L'ajout ou la suppression d'une table à la vue DSV ajoute ou supprime également la table au diagramme sélectionné dans cette vue DSV.</span><span class="sxs-lookup"><span data-stu-id="da36e-114">Adding or removing a table to the DSV also adds or removes the table to the currently selected diagram in the DSV.</span></span> <span data-ttu-id="da36e-115">Pour plus d’informations sur les diagrammes, consultez [Utiliser des diagrammes dans un concepteur de vues de sources de données &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="da36e-115">For more information on diagrams, see [Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;](work-with-diagrams-in-data-source-view-designer-analysis-services.md).</span></span>  
  
 <span data-ttu-id="da36e-116">Une fois que vous avez placé une table dans la liste **Objets inclus** de la boîte de dialogue **Ajouter/supprimer des tables** , vous pouvez ajouter toutes les tables associées.</span><span class="sxs-lookup"><span data-stu-id="da36e-116">After you move a table to the **Included objects** list in the **Add/Remove Tables** dialog box, you can add all related tables.</span></span> <span data-ttu-id="da36e-117">Cette opération ajoute des tables en fonction des contraintes de clé étrangère dans la source de données, si de telles contraintes existent.</span><span class="sxs-lookup"><span data-stu-id="da36e-117">This operation adds tables according to foreign key constraints in the data source, if such constraints exist.</span></span> <span data-ttu-id="da36e-118">Si aucune contrainte de clé étrangère n'existe, vous pouvez utiliser la propriété `NameMatchingCriteria` de la vue de source de données pour déterminer des relations en spécifiant un critère de correspondance des noms de colonnes dans les tables pour générer des relations possibles.</span><span class="sxs-lookup"><span data-stu-id="da36e-118">If foreign key constraints do not exist, you can use the `NameMatchingCriteria` property of the data source view to determine relationships by specifying a criterion for matching column names in tables to generate likely relationships.</span></span> <span data-ttu-id="da36e-119">Si la `NameMatchingCriteria` propriété est spécifiée pour la vue de source de données, cliquez sur **Ajouter des tables associées** pour ajouter des tables de la source de données qui ont des noms de colonnes correspondants.</span><span class="sxs-lookup"><span data-stu-id="da36e-119">If the `NameMatchingCriteria`property is specified for the data source view, click **Add Related Tables** to add tables from the data source that have matching column names.</span></span> <span data-ttu-id="da36e-120">Pour plus d’informations sur la définition de la `NameMatchingCriteria` propriété, consultez [vues de sources de données dans les modèles multidimensionnels](data-source-views-in-multidimensional-models.md).</span><span class="sxs-lookup"><span data-stu-id="da36e-120">For more information about setting the `NameMatchingCriteria` property, see [Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="da36e-121">L'ajout ou la suppression d'objets dans une vue de source de données n'affecte pas la source de données sous-jacente.</span><span class="sxs-lookup"><span data-stu-id="da36e-121">Adding or removing objects in a data source view does not affect the underlying data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da36e-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="da36e-122">See Also</span></span>  
 <span data-ttu-id="da36e-123">[Vues de sources de données dans les modèles multidimensionnels](data-source-views-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="da36e-123">[Data Source Views in Multidimensional Models](data-source-views-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="da36e-124">Utiliser des diagrammes dans un concepteur de vues de sources de données &#40;Analysis Services&#41;</span><span class="sxs-lookup"><span data-stu-id="da36e-124">Work with Diagrams in Data Source View Designer &#40;Analysis Services&#41;</span></span>](work-with-diagrams-in-data-source-view-designer-analysis-services.md)  
  
  
