---
title: Modifier les mappages de filtres de lignes, de tables ou de colonnes (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 2124c526-5772-4f84-a019-9dd3e906e8dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: d8a597fb51804ea12caace63f3308b07bffc5899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604155"
---
# <a name="change-table-column-or-row-filter-mappings-ssas-tabular"></a><span data-ttu-id="42108-102">Changer des mappages de filtres de lignes, de tables ou de colonnes (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="42108-102">Change table, column, or row filter mappings (SSAS Tabular)</span></span>
  <span data-ttu-id="42108-103">Cette rubrique explique comment modifier des mappages de filtres de lignes, de tables ou de colonnes à l’aide de la boîte de dialogue **Modifier les propriétés de la table** dans [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42108-103">This topic describes how to change table, column, or row filter mappings by using the **Edit Table Properties** dialog box in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
 <span data-ttu-id="42108-104">Les options proposées dans la boîte de dialogue **Modifier les propriétés de la table** diffèrent selon que vous avez initialement importé les données en sélectionnant des tables dans une liste ou en utilisant une requête SQL.</span><span class="sxs-lookup"><span data-stu-id="42108-104">Options in the **Edit Table Properties** dialog box are different depending on whether you originally imported data by selecting tables from a list or by using a SQL query.</span></span> <span data-ttu-id="42108-105">Si vous avez importé initialement les données par la sélection dans une liste, la boîte de dialogue **Modifier les propriétés de la table** affiche le mode Aperçu de la table.</span><span class="sxs-lookup"><span data-stu-id="42108-105">If you originally imported the data by selecting from a list, the **Edit Table Properties** dialog box displays the Table Preview mode.</span></span> <span data-ttu-id="42108-106">Ce mode affiche uniquement un sous-ensemble limité aux cinquante premières lignes de la table source.</span><span class="sxs-lookup"><span data-stu-id="42108-106">This mode displays only a subset limited to the first fifty rows of the source table.</span></span> <span data-ttu-id="42108-107">Si vous avez importé initialement les données à l’aide d’une instruction SQL, la boîte de dialogue **Modifier les propriétés de la table** affiche uniquement une instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="42108-107">If you originally imported the data by using a SQL statement, the **Edit Table Properties** dialog box only displays a SQL statement.</span></span> <span data-ttu-id="42108-108">Si vous utilisez une instruction de requête SQL, vous pouvez récupérer un sous-ensemble de lignes, soit en concevant un filtre, soit en modifiant manuellement l'instruction SQL.</span><span class="sxs-lookup"><span data-stu-id="42108-108">Using a SQL query statement, you can retrieve a subset of rows, either by designing a filter, or by manually editing the SQL statement.</span></span>  
  
 <span data-ttu-id="42108-109">Si vous modifiez la source en une table qui comporte des colonnes différentes de la table actuelle, un message s'affiche pour vous avertir que les colonnes sont différentes.</span><span class="sxs-lookup"><span data-stu-id="42108-109">If you change the source to a table that has different columns than the current table, a message is displayed warning that the columns are different.</span></span> <span data-ttu-id="42108-110">Vous devez ensuite sélectionner les colonnes que vous souhaitez placer dans la table actuelle et cliquer sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="42108-110">You must then select the columns that you want to put in the current table and click **Save**.</span></span> <span data-ttu-id="42108-111">Vous pouvez remplacer la table entière en activant la case à cocher située à la gauche de la table.</span><span class="sxs-lookup"><span data-stu-id="42108-111">You can replace the entire table by selecting the check box at the left of the table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="42108-112">Si votre table a plusieurs partitions, vous ne pouvez pas utiliser la boîte de dialogue Modifier les propriétés de la table pour modifier les mappages de filtre de lignes.</span><span class="sxs-lookup"><span data-stu-id="42108-112">If your table has more than one partition, you cannot use the Edit Table Properties dialog box to change row filter mappings.</span></span> <span data-ttu-id="42108-113">Pour modifier des mappages de filtre de lignes dans des tables avec plusieurs partitions, utilisez le Gestionnaire de partitions.</span><span class="sxs-lookup"><span data-stu-id="42108-113">To change row filter mappings for tables with multiple partitions, use Partition Manager.</span></span> <span data-ttu-id="42108-114">Pour plus d’informations, consultez [Partitions &#40;SSAS Tabulaire&#41;](partitions-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="42108-114">For more information, see [Partitions &#40;SSAS Tabular&#41;](partitions-ssas-tabular.md).</span></span>  
  
#### <a name="to-change-table-column-or-row-filter-mappings"></a><span data-ttu-id="42108-115">Pour modifier des mappages de filtres de lignes, de tables ou de colonnes</span><span class="sxs-lookup"><span data-stu-id="42108-115">To change table, column, or row filter mappings</span></span>  
  
1.  <span data-ttu-id="42108-116">Dans le générateur de modèles, cliquez sur la table, puis sur le menu **Table** , et enfin sur **Propriétés de la table**.</span><span class="sxs-lookup"><span data-stu-id="42108-116">In the model designer, click the table, then click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
2.  <span data-ttu-id="42108-117">Dans la boîte de dialogue **Modifier les propriétés de la table** , recherchez la colonne qui contient les critères sur lesquels vous souhaitez effectuer le filtrage, puis cliquez sur la flèche Bas à la droite du titre de colonne.</span><span class="sxs-lookup"><span data-stu-id="42108-117">In the **Edit Table Properties** dialog box, locate the column that contains the criteria you want to filter on, and then click the down arrow at the right of the column heading.</span></span>  
  
3.  <span data-ttu-id="42108-118">Dans le menu **filtre automatique** , effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="42108-118">In the **AutoFilter** menu, do one of the following:</span></span>  
  
    -   <span data-ttu-id="42108-119">Dans la liste de valeurs de colonne, sélectionnez ou désélectionnez une ou plusieurs valeurs sur lesquelles filtrer les données, puis cliquez sur OK.</span><span class="sxs-lookup"><span data-stu-id="42108-119">In the list of column values, select or clear one or more values to filter by, and then click OK.</span></span>  
  
         <span data-ttu-id="42108-120">Si le nombre de valeurs est très important, les éléments individuels peuvent ne pas être affichés dans la liste.</span><span class="sxs-lookup"><span data-stu-id="42108-120">If the number of values is extremely large, individual items might not be shown in the list.</span></span> <span data-ttu-id="42108-121">Le message « Trop d'éléments à afficher » sera alors affiché.</span><span class="sxs-lookup"><span data-stu-id="42108-121">Instead, you will see the message, "Too many items to show."</span></span>  
  
    -   <span data-ttu-id="42108-122">Cliquez sur **Filtres de nombres** ou sur **Filtres de texte** (en fonction du type de colonne), puis cliquez sur l’une des commandes de l’opérateur de comparaison (comme Égal à) ou cliquez sur Filtre personnalisé.</span><span class="sxs-lookup"><span data-stu-id="42108-122">Click **Number Filters** or **Text Filters** (depending on the type of column), and then clicke of the comparison operator commands (such as Equals), or click Custom Filter.</span></span> <span data-ttu-id="42108-123">Dans la boîte de dialogue **Filtre personnalisé** , créez le filtre, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="42108-123">In the **Custom Filter** dialog box, create the filter, and then click **OK**.</span></span>  
  
         <span data-ttu-id="42108-124">Si vous faites une erreur et devez recommencer, cliquez sur **Effacer les filtres de lignes**.</span><span class="sxs-lookup"><span data-stu-id="42108-124">If you make a mistake and need to start over, click **Clear Row Filters**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42108-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42108-125">See Also</span></span>  
 [<span data-ttu-id="42108-126">Boîte de dialogue Modifier les propriétés de la table &#40;SSAS&#41;</span><span class="sxs-lookup"><span data-stu-id="42108-126">Edit Table Properties Dialog Box &#40;SSAS&#41;</span></span>](../edit-table-properties-dialog-box-ssas.md)  
  
  
