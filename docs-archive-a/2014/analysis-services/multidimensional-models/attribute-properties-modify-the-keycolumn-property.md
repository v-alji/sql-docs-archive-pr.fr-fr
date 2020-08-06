---
title: Modifier la propriété KeyColumn d’un attribut | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- binding attributes [Analysis Services]
- attributes [Analysis Services], binding
- key columns [Analysis Services]
ms.assetid: a2643be4-8123-4cc3-baf9-e5ec54a1669d
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3367a7aec84ba59efd118a56745bb76fc5266061
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708792"
---
# <a name="modify-the-keycolumn-property-of-an-attribute"></a><span data-ttu-id="d4a1a-102">Modifier la propriété KeyColumn d'un attribut</span><span class="sxs-lookup"><span data-stu-id="d4a1a-102">Modify the KeyColumn Property of an Attribute</span></span>
  <span data-ttu-id="d4a1a-103">Vous pouvez modifier la propriété **KeyColumns** d'un attribut.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-103">You can modify the **KeyColumns** property of an attribute.</span></span> <span data-ttu-id="d4a1a-104">Par exemple, vous souhaiterez peut-être spécifier une clé composite plutôt qu'une clé unique comme clé de l'attribut.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-104">For example, you might want to specify a composite key instead of a single key as the key for the attribute.</span></span>  
  
### <a name="to-modify-the-keycolumns-property-of-an-attribute"></a><span data-ttu-id="d4a1a-105">Pour modifier la propriété KeyColumns d'un attribut</span><span class="sxs-lookup"><span data-stu-id="d4a1a-105">To modify the KeyColumns property of an attribute</span></span>  
  
1.  <span data-ttu-id="d4a1a-106">Dans [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], ouvrez le projet dont vous souhaitez modifier la propriété **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="d4a1a-106">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the project in which you want to modify the **KeyColumns** property.</span></span>  
  
2.  <span data-ttu-id="d4a1a-107">Ouvrez le Concepteur de dimensions en suivant l'une des procédures ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="d4a1a-107">Open Dimension Designer by doing one of the following procedures:</span></span>  
  
    -   <span data-ttu-id="d4a1a-108">Dans **l’Explorateur de solutions**, cliquez avec le bouton droit sur la dimension dans le dossier **Dimensions** , puis cliquez sur **Ouvrir** ou **Concepteur de vues**.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-108">In **Solution Explorer**, right-click the dimension in the **Dimensions** folder, and then either click **Open** or **View Designer**.</span></span>  
  
         <span data-ttu-id="d4a1a-109">-ou-</span><span class="sxs-lookup"><span data-stu-id="d4a1a-109">-or-</span></span>  
  
    -   <span data-ttu-id="d4a1a-110">Dans le concepteur de cube, sous l’onglet **structure de cube** , développez la dimension de cube dans le volet **dimensions** , puis cliquez sur \*\*modifier \<dimension> \*\*.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-110">In Cube Designer, on the **Cube Structure** tab, expand the cube dimension in the **Dimensions** pane and click **Edit \<dimension>**.</span></span>  
  
3.  <span data-ttu-id="d4a1a-111">Sous l'onglet **Structure de dimension** , dans le volet **Attributs** , cliquez sur l'attribut dont vous souhaitez modifier la propriété **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="d4a1a-111">On the **Dimension Structure** tab, in the **Attributes** pane, click the attribute whose **KeyColumns** property you want to modify.</span></span>  
  
4.  <span data-ttu-id="d4a1a-112">Dans la fenêtre **Propriétés** , cliquez sur la valeur de la propriété **KeyColumns** .</span><span class="sxs-lookup"><span data-stu-id="d4a1a-112">In the **Properties** window, click the value for the **KeyColumns** property.</span></span>  
  
5.  <span data-ttu-id="d4a1a-113">Cliquez sur le bouton Parcourir **(...)** qui apparaît dans la cellule de la valeur de la zone de propriété.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-113">Click the browse **(...)** button that appears in the value cell of the property box.</span></span>  
  
     <span data-ttu-id="d4a1a-114">La boîte de dialogue de **Colonnes clés** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-114">The **Key Columns** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="d4a1a-115">Pour supprimer une colonne clé existante, sélectionnez la colonne dans la liste **Colonnes clés** , puis cliquez sur le bouton **\<** .</span><span class="sxs-lookup"><span data-stu-id="d4a1a-115">To remove an existing key column, in the **Key Columns** list, select the column, and then click the **\<** button.</span></span>  
  
7.  <span data-ttu-id="d4a1a-116">Pour ajouter une colonne clé, sélectionnez la colonne dans la liste **Colonnes disponibles** , puis cliquez sur le bouton **>** .</span><span class="sxs-lookup"><span data-stu-id="d4a1a-116">To add a key column, in the **Available Columns** list, select the column, and then click the **>** button.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d4a1a-117">Si vous définissez plusieurs colonnes clés, l'ordre dans lequel ces colonnes apparaissent dans la liste **Colonnes clés** affecte l'ordre d'affichage.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-117">If you define multiple key columns, the order in which those columns appear in the **Key Columns** list affects the display order.</span></span> <span data-ttu-id="d4a1a-118">Par exemple, un attribut de mois a deux colonnes clés : mois et année.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-118">For example, a month attribute has two key columns: month and year.</span></span> <span data-ttu-id="d4a1a-119">Si la colonne d'année apparaît dans la liste avant la colonne de mois, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] triera par année, puis par mois.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-119">If the year column appears in the list before the month column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by year and then by month.</span></span> <span data-ttu-id="d4a1a-120">Si la colonne de mois apparaît avant la colonne d'année, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] triera par mois, puis par année.</span><span class="sxs-lookup"><span data-stu-id="d4a1a-120">If the month column appears before the year column, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] will sort by month and then by year.</span></span>  
  
8.  <span data-ttu-id="d4a1a-121">Pour modifier l'ordre des colonnes clés, sélectionnez une colonne, puis cliquez le bouton **Haut** ou **Bas** .</span><span class="sxs-lookup"><span data-stu-id="d4a1a-121">To change the order of key columns, select a column, and then click the **Up** or **Down** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a1a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4a1a-122">See Also</span></span>  
 [<span data-ttu-id="d4a1a-123">Référence des propriétés d’attribut de dimension</span><span class="sxs-lookup"><span data-stu-id="d4a1a-123">Dimension Attribute Properties Reference</span></span>](dimension-attribute-properties-reference.md)  
  
  
