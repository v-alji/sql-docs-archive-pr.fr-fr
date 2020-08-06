---
title: Modifier une connexion à une source de données existante (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.selexistconn.f1
ms.assetid: 97e63f18-a01d-4c91-a411-e7e6d40a0647
author: minewiskan
ms.author: owend
ms.openlocfilehash: 675a0d1119e25a92231d3e74a79739cb2e96b6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613197"
---
# <a name="edit-an-existing-data-source-connection-ssas-tabular"></a><span data-ttu-id="9bb04-102">Modifier une connexion à une source de données existante (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="9bb04-102">Edit an Existing Data Source Connection (SSAS Tabular)</span></span>
  <span data-ttu-id="9bb04-103">Cette rubrique décrit la procédure de modification des propriétés d'une connexion de source de données existante dans un modèle tabulaire.</span><span class="sxs-lookup"><span data-stu-id="9bb04-103">This topic describes how to edit the properties of an existing data source connection in a tabular model.</span></span>  
  
 <span data-ttu-id="9bb04-104">Après avoir créé une connexion à une source de données externe, vous pouvez modifier cette connexion des différentes façons suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bb04-104">After you have created a connection to an external data source, you can later modify that connection in these ways:</span></span>  
  
-   <span data-ttu-id="9bb04-105">Vous pouvez modifier les informations de la connexion, notamment le fichier, le flux ou la base de données utilisés comme source, ses propriétés ou d'autres options de connexion spécifiques du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9bb04-105">You can change the connection information, including the file, feed, or database used as a source, its properties, or other provider-specific connection options.</span></span>  
  
-   <span data-ttu-id="9bb04-106">Vous pouvez modifier les mappages de tables et de colonnes et supprimer des références aux colonnes qui ne sont plus utilisées.</span><span class="sxs-lookup"><span data-stu-id="9bb04-106">You can change table and column mappings, and remove references to columns that are no longer used.</span></span>  
  
-   <span data-ttu-id="9bb04-107">Vous pouvez modifier les tables, les vues et les colonnes que vous obtenez à partir de la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="9bb04-107">You can change the tables, views, or columns that you get from the external data source.</span></span>  
  
## <a name="modify-a-connection"></a><span data-ttu-id="9bb04-108">Modifier une connexion</span><span class="sxs-lookup"><span data-stu-id="9bb04-108">Modify a Connection</span></span>  
 <span data-ttu-id="9bb04-109">Cette procédure décrit comment modifier une connexion de source de données de base de données.</span><span class="sxs-lookup"><span data-stu-id="9bb04-109">This procedure describes how to modify a database data source connection.</span></span> <span data-ttu-id="9bb04-110">Certaines options relatives à l'utilisation des sources de données diffèrent selon le type de source de données ; toutefois, vous devez pouvoir identifier facilement ces différences.</span><span class="sxs-lookup"><span data-stu-id="9bb04-110">Some options for working with data sources differ depending on the data source type; however, you should be able to easily identify those differences.</span></span>  
  
#### <a name="to-change-the-external-data-source-used-by-a-current-connection"></a><span data-ttu-id="9bb04-111">Pour modifier la source de données externe utilisée par une connexion actuelle</span><span class="sxs-lookup"><span data-stu-id="9bb04-111">To change the external data source used by a current connection</span></span>  
  
1.  <span data-ttu-id="9bb04-112">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Modèle** , puis sur **Connexions existantes**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="9bb04-113">Sélectionnez la connexion à la source de données que vous souhaitez modifier, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-113">Select the data source connection you want to modify, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="9bb04-114">Dans la boîte de dialogue **Modifier la connexion** , cliquez sur **Parcourir** pour localiser une autre base de données du même type avec un nom ou un emplacement différent.</span><span class="sxs-lookup"><span data-stu-id="9bb04-114">In the **Edit Connection** dialog box, click **Browse** to locate another database of the same type but with a different name or location.</span></span>  
  
     <span data-ttu-id="9bb04-115">Dès que vous modifiez le fichier de base de données, un message apparaît pour indiquer que vous devez enregistrer et actualiser les tables pour afficher les nouvelles données.</span><span class="sxs-lookup"><span data-stu-id="9bb04-115">As soon as you change the database file, a message appears indicating that you need to save and refresh the tables in order to see the new data.</span></span>  
  
4.  <span data-ttu-id="9bb04-116">Cliquez sur **Enregistrer**, puis sur **Fermer**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-116">Click **Save**, and then click **Close**.</span></span>  
  
5.  <span data-ttu-id="9bb04-117">Dans [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], cliquez sur **Modèle**, sur **Traiter**, puis sur **Traiter tout**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model**, click **Process**, and then click **Process All**.</span></span>  
  
     <span data-ttu-id="9bb04-118">Les tables sont retraitées à l'aide de la nouvelle source de données, mais avec les sélections de données d'origine.</span><span class="sxs-lookup"><span data-stu-id="9bb04-118">The tables are re-processed using the new data source, but with the original data selections.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9bb04-119">Si la nouvelle source de données contient des tables supplémentaires qui n'étaient pas présentes dans la source de données d'origine, vous devez rouvrir la connexion modifiée et ajouter les tables.</span><span class="sxs-lookup"><span data-stu-id="9bb04-119">If the new data source contains any additional tables that were not present in the original data source, you must re-open the changed connection and add the tables.</span></span>  
  
## <a name="edit-table-and-column-mappings-bindings"></a><span data-ttu-id="9bb04-120">Modifier les mappages de tables et de colonnes (liaisons)</span><span class="sxs-lookup"><span data-stu-id="9bb04-120">Edit Table and Column Mappings (Bindings)</span></span>  
 <span data-ttu-id="9bb04-121">Cette procédure décrit comment modifier les mappages après avoir modifié une source de données.</span><span class="sxs-lookup"><span data-stu-id="9bb04-121">This procedure describes how to edit the mappings after you change a data source.</span></span>  
  
#### <a name="to-edit-column-mappings-when-a-data-source-changes"></a><span data-ttu-id="9bb04-122">Pour modifier des mappages de colonnes lorsqu'une source de données change</span><span class="sxs-lookup"><span data-stu-id="9bb04-122">To edit column mappings when a data source changes</span></span>  
  
1.  <span data-ttu-id="9bb04-123">Dans le générateur de modèles, sélectionnez une table.</span><span class="sxs-lookup"><span data-stu-id="9bb04-123">In the model designer, select a table.</span></span>  
  
2.  <span data-ttu-id="9bb04-124">Cliquez sur le menu **Table** , puis sur **Propriétés de la table**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-124">Click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
     <span data-ttu-id="9bb04-125">Le nom de la table sélectionnée est affiché dans la zone **Nom de la table** .</span><span class="sxs-lookup"><span data-stu-id="9bb04-125">The name of the selected table is displayed in the **Table Name** box.</span></span> <span data-ttu-id="9bb04-126">La zone **Nom de la source** contient le nom de la table dans la source de données externe.</span><span class="sxs-lookup"><span data-stu-id="9bb04-126">The **Source Name** box contains the name of the table in the external data source.</span></span> <span data-ttu-id="9bb04-127">Si des colonnes sont nommées différemment dans la source et dans le modèle, vous pouvez basculer entre les deux ensembles de noms de colonnes en sélectionnant les options **Source** ou **Modèle**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-127">If columns are named differently in the source and in the model, you can toggle between the two sets of column names by selecting the options **Source** or **Model**.</span></span>  
  
3.  <span data-ttu-id="9bb04-128">Pour changer la table utilisée comme source de données, sélectionnez une autre table dans la zone **Nom de la source**.</span><span class="sxs-lookup"><span data-stu-id="9bb04-128">To change the table that is used as a data source, for **Source Name**, select a different table than the current one.</span></span>  
  
4.  <span data-ttu-id="9bb04-129">Modifiez les mappages de colonnes si nécessaire :</span><span class="sxs-lookup"><span data-stu-id="9bb04-129">Change column mappings if needed:</span></span>  
  
    1.  <span data-ttu-id="9bb04-130">Pour ajouter des colonnes qui sont présentes dans la source mais pas dans le modèle, activez la case à cocher en regard du nom des colonnes.</span><span class="sxs-lookup"><span data-stu-id="9bb04-130">To add columns that are present in the source but not in the model, select the checkbox beside the column name.</span></span>  
  
         <span data-ttu-id="9bb04-131">Les données effectives seront chargées dans le modèle lors de la prochaine actualisation des données.</span><span class="sxs-lookup"><span data-stu-id="9bb04-131">The actual data will be loaded into the model the next time you refresh.</span></span>  
  
    2.  <span data-ttu-id="9bb04-132">Si certaines colonnes du modèle ne sont plus disponibles dans la source de données actuelle, un message s'affiche dans la zone de notification, répertoriant les colonnes non valides.</span><span class="sxs-lookup"><span data-stu-id="9bb04-132">If some columns in the model are no longer available in the current data source, a message appears in the notification area that lists the invalid columns.</span></span> <span data-ttu-id="9bb04-133">Vous n'avez pas besoin de faire autre chose.</span><span class="sxs-lookup"><span data-stu-id="9bb04-133">You do not need to do anything else.</span></span>  
  
5.  <span data-ttu-id="9bb04-134">Cliquez sur **Enregistrer** pour appliquer les modifications à votre modèle.</span><span class="sxs-lookup"><span data-stu-id="9bb04-134">Click **Save** to apply the changes to your model.</span></span>  
  
     <span data-ttu-id="9bb04-135">Lorsque vous enregistrez l'ensemble actuel de propriétés de table, un message peut apparaître pour vous prévenir que vous devez traiter les tables.</span><span class="sxs-lookup"><span data-stu-id="9bb04-135">When you save the current set of table properties, a message may appear indicating that you need to process the tables.</span></span> <span data-ttu-id="9bb04-136">Cliquez sur **Traiter** pour charger les données mises à jour dans votre modèle.</span><span class="sxs-lookup"><span data-stu-id="9bb04-136">Click **Process** to load updated data into your model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bb04-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9bb04-137">See Also</span></span>  
 <span data-ttu-id="9bb04-138">[Traiter des données &#40;tabulaires SSAS&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="9bb04-138">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="9bb04-139">Sources de données prises en charge &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="9bb04-139">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
