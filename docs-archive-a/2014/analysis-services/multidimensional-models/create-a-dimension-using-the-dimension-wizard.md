---
title: Créer une dimension à l’aide de l’Assistant Dimension | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], creating
ms.assetid: d84f66ae-7551-49bf-99d0-88368ca2dd0e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9ec38dc7170b915dce0cedea60c93385560e11f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87705612"
---
# <a name="create-a-dimension-using-the-dimension-wizard"></a><span data-ttu-id="73dc1-102">Créer une dimension à l'aide de l'Assistant Dimension</span><span class="sxs-lookup"><span data-stu-id="73dc1-102">Create a Dimension Using the Dimension Wizard</span></span>
  <span data-ttu-id="73dc1-103">Vous pouvez créer une dimension en utilisant l'Assistant Dimension dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73dc1-103">You can create a new dimension by using the Dimension Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-dimension"></a><span data-ttu-id="73dc1-104">Pour créer une dimension</span><span class="sxs-lookup"><span data-stu-id="73dc1-104">To create a new dimension</span></span>  
  
1.  <span data-ttu-id="73dc1-105">Dans **Explorateur de solutions**, cliquez avec le bouton droit sur **dimensions**, puis cliquez sur **nouvelle dimension**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-105">In **Solution Explorer**, right-click **Dimensions**, and then click **New Dimension**.</span></span>  
  
2.  <span data-ttu-id="73dc1-106">Dans la page **Sélectionner la méthode de création** de l’Assistant Dimension, sélectionnez **Utiliser une table existante**, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-106">On the **Select Creation Method** page of the Dimension Wizard, select **Use an existing table**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73dc1-107">Parfois, vous devrez peut-être créer une dimension sans utiliser de table existante.</span><span class="sxs-lookup"><span data-stu-id="73dc1-107">You might occasionally have to create a dimension without using an existing table.</span></span> <span data-ttu-id="73dc1-108">Pour plus d’informations, consultez [Créer une dimension en générant une table non temporelle dans la source de données](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) et [Créer une dimension de temps en générant une table de temps](create-a-time-dimension-by-generating-a-time-table.md).</span><span class="sxs-lookup"><span data-stu-id="73dc1-108">For more information, see [Create a Dimension by Generating a Non-Time Table in the Data Source](create-a-dimension-by-generating-a-non-time-table-in-the-data-source.md) and [Create a Time Dimension by Generating a Time Table](create-a-time-dimension-by-generating-a-time-table.md).</span></span>  
  
3.  <span data-ttu-id="73dc1-109">Dans la page **Spécifier des informations sur la source** , exécutez les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="73dc1-109">On the **Specify Source Information** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="73dc1-110">Dans la liste **Vue de source de données** , sélectionnez une vue de source de données.</span><span class="sxs-lookup"><span data-stu-id="73dc1-110">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="73dc1-111">Dans la liste **Table principale** , sélectionnez la table de dimension principale.</span><span class="sxs-lookup"><span data-stu-id="73dc1-111">In the **Main table** list, select the main dimension table.</span></span>  
  
    3.  <span data-ttu-id="73dc1-112">Dans la liste **Colonnes clés** , examinez les colonnes clés que l’Assistant a sélectionnées automatiquement selon la clé primaire qui est définie dans la table de dimension principale.</span><span class="sxs-lookup"><span data-stu-id="73dc1-112">In the **Key columns** list, review the key columns that the wizard has automatically selected based on the primary key that is defined in the main dimension table.</span></span> <span data-ttu-id="73dc1-113">Pour modifier ce paramètre par défaut, spécifiez les colonnes clés qui lient la table de dimension à la table de faits.</span><span class="sxs-lookup"><span data-stu-id="73dc1-113">To change this default setting, specify the key columns that link the dimension table to the fact table.</span></span>  
  
    4.  <span data-ttu-id="73dc1-114">Dans la liste déroulante **Colonne de nom** , examinez la colonne de nom que l’Assistant a sélectionnée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="73dc1-114">In the **Name column** drop-down list, review the name column that the wizard has automatically selected.</span></span>  
  
         <span data-ttu-id="73dc1-115">Ce nom par défaut est approprié lorsque la colonne contient des informations descriptives.</span><span class="sxs-lookup"><span data-stu-id="73dc1-115">This default name is appropriate when the column contains descriptive information.</span></span> <span data-ttu-id="73dc1-116">Toutefois, vous pouvez souhaiter spécifier un nom qui contient des valeurs qui sont plus explicites pour l'utilisateur final.</span><span class="sxs-lookup"><span data-stu-id="73dc1-116">However, you might want to specify a name that contains values that are more meaningful for the end user.</span></span> <span data-ttu-id="73dc1-117">Par exemple, si un attribut de catégorie de produit d’une dimension Products utilise la colonne **ProductCategoryKey** en tant que colonne clé, vous pouvez spécifier la colonne **ProductCategoryName** en tant que colonne de nom.</span><span class="sxs-lookup"><span data-stu-id="73dc1-117">For example, if a product category attribute in a Products dimension uses the **ProductCategoryKey** column as its key column, you can specify the **ProductCategoryName** column as its name column.</span></span>  
  
         <span data-ttu-id="73dc1-118">Si la liste **Colonnes clés** contient plusieurs colonnes clés, vous devez spécifier une colonne de nom qui fournit les valeurs d’un membre pour l’attribut de clé.</span><span class="sxs-lookup"><span data-stu-id="73dc1-118">If the **Key columns** list contains multiple key columns, you must specify a name column that provides the member values for the key attribute.</span></span> <span data-ttu-id="73dc1-119">Pour cela, vous pouvez créer un calcul nommé dans la vue de source de données et l'utiliser comme colonne de nom.</span><span class="sxs-lookup"><span data-stu-id="73dc1-119">To do this, you can create a named calculation in the data source view and use that as the name column.</span></span>  
  
    5.  <span data-ttu-id="73dc1-120">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-120">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="73dc1-121">Dans la page **Sélectionner les tables associées** , sélectionnez les tables associées à inclure dans votre dimension, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-121">On the **Select Related Tables** page, select the related tables that you want to include in your dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73dc1-122">La page **Sélectionner les tables associées** apparaît si la table de dimension principale que vous avez spécifiée a des relations avec d’autres tables de dimension.</span><span class="sxs-lookup"><span data-stu-id="73dc1-122">The **Select Related Tables** page appears if the main dimension table that you specified has relationships to other dimension tables.</span></span>  
  
5.  <span data-ttu-id="73dc1-123">Dans la page **Sélectionner les attributs de la dimension** , sélectionnez les attributs associés à inclure dans la dimension, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-123">On the **Select Dimension Attributes** page, select the attributes that you want to include in the dimension, and then click **Next**.</span></span>  
  
     <span data-ttu-id="73dc1-124">Vous pouvez éventuellement modifier les noms d'attribut, activer ou désactiver l'exploration et spécifier le type d'attribut.</span><span class="sxs-lookup"><span data-stu-id="73dc1-124">Optionally, you can change the attribute names, enable or disable browsing, and specify the attribute type.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73dc1-125">Pour activer les champs **Permettre la navigation** et **Type d’attribut** d’un attribut, l’attribut doit être sélectionné pour être inclus dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="73dc1-125">To make the **Enable Browsing** and **Attribute Type** fields of an attribute active, the attribute must be selected for inclusion in the dimension.</span></span>  
  
6.  <span data-ttu-id="73dc1-126">Dans la page **Définir l’intelligence comptable** , dans la colonne **Types de comptes intégrés** , sélectionnez le type de compte, puis cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-126">On the **Define Account Intelligence** page, in the **Built-In Account Types** column, select the account type, and then click **Next**.</span></span>  
  
     <span data-ttu-id="73dc1-127">Le type de compte doit correspondre au type de compte de la table source qui est répertorié dans la colonne **Types de comptes de la table source** .</span><span class="sxs-lookup"><span data-stu-id="73dc1-127">The account type must correspond to the account type of the source table that is listed in the **Source Table Account Types** column.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73dc1-128">La page **Définir l’intelligence comptable** apparaît si vous avez défini un attribut de dimension **Type de compte** dans la page **Sélectionner les attributs de la dimension** de l’Assistant.</span><span class="sxs-lookup"><span data-stu-id="73dc1-128">The **Define Account Intelligence** page appears if you defined an **Account Type** dimension attribute on the **Select Dimension Attributes** page of the wizard.</span></span>  
  
7.  <span data-ttu-id="73dc1-129">Dans la page **Fin de l’Assistant** , entrez le nom de la nouvelle dimension et examinez sa structure.</span><span class="sxs-lookup"><span data-stu-id="73dc1-129">On the **Completing the Wizard** page, enter a name for the new dimension and review the dimension structure.</span></span> <span data-ttu-id="73dc1-130">Si vous souhaitez apporter des modifications, cliquez sur **Précédent**; sinon, cliquez sur **Terminer**.</span><span class="sxs-lookup"><span data-stu-id="73dc1-130">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="73dc1-131">Vous pouvez utiliser le Concepteur de dimensions après avoir terminé l'Assistant Dimension pour ajouter, supprimer et configurer des attributs et des hiérarchies dans la dimension.</span><span class="sxs-lookup"><span data-stu-id="73dc1-131">You can use Dimension Designer after you complete the Dimension Wizard to add, remove, and configure attributes and hierarchies in the dimension.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73dc1-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="73dc1-132">See Also</span></span>  
 [<span data-ttu-id="73dc1-133">Créer une dimension à l'aide d'une table existante</span><span class="sxs-lookup"><span data-stu-id="73dc1-133">Create a Dimension by Using an Existing Table</span></span>](create-a-dimension-by-using-an-existing-table.md)  
  
  
