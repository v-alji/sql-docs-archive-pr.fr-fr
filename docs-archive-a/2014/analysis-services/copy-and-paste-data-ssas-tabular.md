---
title: Copier et coller des données (SSAS tabulaire) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.pastepreviewdb.f1
ms.assetid: 2f8d8b3d-810b-4c31-98f2-341015e13da8
author: minewiskan
ms.author: owend
ms.openlocfilehash: 30df733377f3cb6f7583d380fbb8e92a0ea69e88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602445"
---
# <a name="copy-and-paste-data-ssas-tabular"></a><span data-ttu-id="bc407-102">Copier et coller des données (SSAS Tabulaire)</span><span class="sxs-lookup"><span data-stu-id="bc407-102">Copy and Paste Data (SSAS Tabular)</span></span>
  <span data-ttu-id="bc407-103">Vous pouvez copier des données de table depuis des applications externes et les coller dans une table nouvelle ou existante du générateur de modèles.</span><span class="sxs-lookup"><span data-stu-id="bc407-103">You can copy table data from external applications and paste it into a new or existing table in the model designer.</span></span> <span data-ttu-id="bc407-104">Les données que vous collez à partir du Presse-papiers doivent être au format HTML, notamment les données copiées à partir d’Excel ou de Word.</span><span class="sxs-lookup"><span data-stu-id="bc407-104">The data that you paste from the Clipboard must be in HTML format, for example, data that is copied from Excel or Word.</span></span> <span data-ttu-id="bc407-105">Le générateur de modèles détecte et applique automatiquement les types de données aux données collées.</span><span class="sxs-lookup"><span data-stu-id="bc407-105">The model designer will automatically detect and apply data types to the pasted data.</span></span> <span data-ttu-id="bc407-106">Vous pouvez également modifier manuellement le type de données ou la mise en forme d'affichage d'une colonne.</span><span class="sxs-lookup"><span data-stu-id="bc407-106">You can also manually modify the data type or display formatting of a column.</span></span>  
  
 <span data-ttu-id="bc407-107">Contrairement aux tables avec une connexion de source de données, les tables collées n'ont pas de propriété Nom de la connexion ou Données source.</span><span class="sxs-lookup"><span data-stu-id="bc407-107">Unlike tables with a data source connection, pasted tables do not have a Connection Name or Source Data property.</span></span> <span data-ttu-id="bc407-108">Les données collées sont persistantes dans le fichier model.bim.</span><span class="sxs-lookup"><span data-stu-id="bc407-108">Pasted data is persisted in the Model.bim file.</span></span> <span data-ttu-id="bc407-109">Lorsque le projet ou le fichier model.bim est enregistré, les données collées le sont également.</span><span class="sxs-lookup"><span data-stu-id="bc407-109">When the project or Model.bim file is saved, the pasted data is also saved.</span></span>  
  
 <span data-ttu-id="bc407-110">Lorsqu'un modèle est déployé, les données collées sont également déployées avec lui, que le modèle soit traité ou non avec le déploiement.</span><span class="sxs-lookup"><span data-stu-id="bc407-110">When a model is deployed, pasted data will also be deployed with it regardless if the model is processed with the deployment.</span></span>  
  
 <span data-ttu-id="bc407-111">Sections de cette rubrique :</span><span class="sxs-lookup"><span data-stu-id="bc407-111">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="bc407-112">Composants requis</span><span class="sxs-lookup"><span data-stu-id="bc407-112">Prerequisites</span></span>](#bkmk_prerequisites)  
  
-   [<span data-ttu-id="bc407-113">Coller des données</span><span class="sxs-lookup"><span data-stu-id="bc407-113">Paste Data</span></span>](#bkmk_paste_data)  
  
-   [<span data-ttu-id="bc407-114">Boîte de dialogue Aperçu avant collage</span><span class="sxs-lookup"><span data-stu-id="bc407-114">Paste Preview Dialog Box</span></span>](#bkmk_paste_preview)  
  
##  <a name="prerequisites"></a><a name="bkmk_prerequisites"></a> <span data-ttu-id="bc407-115">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="bc407-115">Prerequisites</span></span>  
 <span data-ttu-id="bc407-116">Certaines restrictions s'appliquent lorsque vous collez des données :</span><span class="sxs-lookup"><span data-stu-id="bc407-116">There are some restrictions when pasting data:</span></span>  
  
-   <span data-ttu-id="bc407-117">Les tables collées ne peuvent pas compter plus de 10 000 lignes.</span><span class="sxs-lookup"><span data-stu-id="bc407-117">Pasted tables cannot have more than 10,000 rows.</span></span>  
  
-   <span data-ttu-id="bc407-118">Les tables collées ne peuvent pas être partitionnées.</span><span class="sxs-lookup"><span data-stu-id="bc407-118">Pasted tables cannot be partitioned.</span></span>  
  
-   <span data-ttu-id="bc407-119">Les tables collées ne sont pas prises en charge en mode DirectQuery.</span><span class="sxs-lookup"><span data-stu-id="bc407-119">Pasted tables are not supported in DirectQuery mode.</span></span>  
  
-   <span data-ttu-id="bc407-120">Les options **Coller par ajout** et **Coller par remplacement** sont disponibles uniquement lors de l'utilisation d'une table créée initialement en collant des données à partir du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="bc407-120">The **Paste Append** and **Paste Replace** options are only available when working with a table that was initially created by pasting data from the Clipboard.</span></span> <span data-ttu-id="bc407-121">Vous ne pouvez pas utiliser **Coller par ajout** ou **Coller par remplacement** pour ajouter des données dans une table de données importées provenant d'un autre type de source de données.</span><span class="sxs-lookup"><span data-stu-id="bc407-121">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data from another type of data source.</span></span>  
  
-   <span data-ttu-id="bc407-122">Lorsque vous utilisez **Coller par ajout** ou **Coller par remplacement**, les nouvelles données doivent contenir exactement le même nombre de colonnes que les données originales.</span><span class="sxs-lookup"><span data-stu-id="bc407-122">When you use **Paste Append** or **Paste Replace**, the new data must contain exactly the same number of columns as the original data.</span></span> <span data-ttu-id="bc407-123">De préférence, les colonnes de données que vous collez ou ajoutez doivent également être du même type ou d'un type de données compatible avec celui figurant dans la table de destination.</span><span class="sxs-lookup"><span data-stu-id="bc407-123">Preferably, the columns of data that you paste or append should also be of the same or compatible data type as those in the destination table.</span></span> <span data-ttu-id="bc407-124">Dans certains cas, vous pouvez utiliser un type de données différent, mais une erreur **Incompatibilité de type** peut s’afficher.</span><span class="sxs-lookup"><span data-stu-id="bc407-124">In some cases you can use a different data type, but a **Type mismatch** error may be displayed.</span></span>  
  
##  <a name="paste-data"></a><a name="bkmk_paste_data"></a><span data-ttu-id="bc407-125">Coller des données</span><span class="sxs-lookup"><span data-stu-id="bc407-125">Paste Data</span></span>  
  
#### <a name="to-paste-data-into-the-designer"></a><span data-ttu-id="bc407-126">Pour coller des données dans le générateur</span><span class="sxs-lookup"><span data-stu-id="bc407-126">To paste data into the designer</span></span>  
  
-   <span data-ttu-id="bc407-127">Dans [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], cliquez sur le menu **Édition** , puis sur l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="bc407-127">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Edit** menu, and then clicke of the following:</span></span>  
  
    -   <span data-ttu-id="bc407-128">Cliquez sur **Coller** pour coller le contenu du Presse-papiers dans une nouvelle table.</span><span class="sxs-lookup"><span data-stu-id="bc407-128">Click **Paste** to paste the contents of the Clipboard into a new table.</span></span>  
  
    -   <span data-ttu-id="bc407-129">Cliquez sur **Coller par ajout** pour coller le contenu du Presse-papiers sous forme de lignes supplémentaires dans la table sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="bc407-129">Click **Paste Append** to paste the contents of the Clipboard as additional rows into the selected table.</span></span> <span data-ttu-id="bc407-130">Les nouvelles lignes sont ajoutées à la fin de la table.</span><span class="sxs-lookup"><span data-stu-id="bc407-130">The new rows will be added to the end of the table.</span></span>  
  
    -   <span data-ttu-id="bc407-131">Cliquez sur **Coller par remplacement** pour remplacer la table sélectionnée par le contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="bc407-131">Click **Paste Replace** to replace the selected table with the contents of the Clipboard.</span></span> <span data-ttu-id="bc407-132">Tous les noms d'en-têtes de colonnes existants restent dans la table, et les relations sont conservées.</span><span class="sxs-lookup"><span data-stu-id="bc407-132">All existing column header names will remain in the table, and relationships are preserved.</span></span>  
  
##  <a name="paste-preview-dialog-box"></a><a name="bkmk_paste_preview"></a><span data-ttu-id="bc407-133">Boîte de dialogue Aperçu avant collage</span><span class="sxs-lookup"><span data-stu-id="bc407-133">Paste Preview Dialog Box</span></span>  
 <span data-ttu-id="bc407-134">La boîte de dialogue **Aperçu avant collage** vous permet d'afficher un aperçu des données copiées dans la fenêtre du concepteur et de vérifier qu'elles sont correctement copiées.</span><span class="sxs-lookup"><span data-stu-id="bc407-134">The **Paste Preview** dialog box enables you to see a preview of data that is copied into the designer window and to ensure that the data is copied correctly.</span></span> <span data-ttu-id="bc407-135">Pour accéder à cette boîte de dialogue, copiez les données basées sur une table au format HTML dans le Presse-papiers puis, dans le générateur, dans le menu **Modifier** , cliquez sur **Coller**, **Coller par ajout**ou **Coller par remplacement**.</span><span class="sxs-lookup"><span data-stu-id="bc407-135">To access this dialog box, copy table-based data in the HTML format to the clipboard, and then in the designer, click on the **Edit** menu, and then click **Paste**, **Paste Append**, or **Paste Replace**.</span></span> <span data-ttu-id="bc407-136">Les options **Coller par ajout** et **Coller par remplacement** sont disponibles uniquement lorsque vous ajoutez ou remplacez des données dans une table qui a été créée par copier-coller depuis le Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="bc407-136">The **Paste Append** and **Paste Replace** options are only available when you add or replace data in a table that was created by copying and pasting from the Clipboard.</span></span> <span data-ttu-id="bc407-137">Vous ne pouvez pas utiliser **Coller par ajout** ou **Coller par remplacement** pour ajouter des données dans une table de données importées.</span><span class="sxs-lookup"><span data-stu-id="bc407-137">You cannot use **Paste Append** or **Paste Replace** to add data into a table of imported data.</span></span>  
  
 <span data-ttu-id="bc407-138">Les options proposées dans cette boîte de dialogue diffèrent selon que vous collez des données dans une table complètement nouvelle, collez des données dans une table existante et remplacez les données existantes par les nouvelles, ou ajoutez des données à une table existante.</span><span class="sxs-lookup"><span data-stu-id="bc407-138">The options for this dialog box are different depending on whether you paste data into a completely new table, paste data into an existing table and then replace the existing data with the new data, or whether you append data to an existing table.</span></span>  
  
### <a name="paste-to-new-table"></a><span data-ttu-id="bc407-139">Coller dans une nouvelle table</span><span class="sxs-lookup"><span data-stu-id="bc407-139">Paste to New Table</span></span>  
 <span data-ttu-id="bc407-140">**Nom de la table**</span><span class="sxs-lookup"><span data-stu-id="bc407-140">**Table name**</span></span>  
 <span data-ttu-id="bc407-141">Spécifiez le nom de la table qui sera créée dans le concepteur.</span><span class="sxs-lookup"><span data-stu-id="bc407-141">Specify the name of the table that will be created in the designer.</span></span>  
  
 <span data-ttu-id="bc407-142">**Données à coller**</span><span class="sxs-lookup"><span data-stu-id="bc407-142">**Data to be pasted**</span></span>  
 <span data-ttu-id="bc407-143">Affiche un exemple du contenu du Presse-papiers qui sera ajouté à la table de destination.</span><span class="sxs-lookup"><span data-stu-id="bc407-143">Shows a sample of the Clipboard contents that will be added to the destination table.</span></span>  
  
### <a name="paste-append"></a><span data-ttu-id="bc407-144">Coller par ajout</span><span class="sxs-lookup"><span data-stu-id="bc407-144">Paste Append</span></span>  
 <span data-ttu-id="bc407-145">**Données existantes dans la table**</span><span class="sxs-lookup"><span data-stu-id="bc407-145">**Existing data in the table**</span></span>  
 <span data-ttu-id="bc407-146">Affiche un exemple des données existantes dans la table afin que vous puissiez vérifier les colonnes, les types de données, etc.</span><span class="sxs-lookup"><span data-stu-id="bc407-146">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="bc407-147">**Données à coller**</span><span class="sxs-lookup"><span data-stu-id="bc407-147">**Data to be pasted**</span></span>  
 <span data-ttu-id="bc407-148">Affiche un exemple de contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="bc407-148">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="bc407-149">Les données existantes seront ajoutées par ces données.</span><span class="sxs-lookup"><span data-stu-id="bc407-149">The existing data will be appended by this data.</span></span>  
  
### <a name="paste-replace"></a><span data-ttu-id="bc407-150">Coller par remplacement</span><span class="sxs-lookup"><span data-stu-id="bc407-150">Paste Replace</span></span>  
 <span data-ttu-id="bc407-151">**Données existantes dans la table**</span><span class="sxs-lookup"><span data-stu-id="bc407-151">**Existing data in the table**</span></span>  
 <span data-ttu-id="bc407-152">Affiche un exemple des données existantes dans la table afin que vous puissiez vérifier les colonnes, les types de données, etc.</span><span class="sxs-lookup"><span data-stu-id="bc407-152">Shows a sample of the existing data in the table so that you can verify the columns, data types, etc.</span></span>  
  
 <span data-ttu-id="bc407-153">**Données à coller**</span><span class="sxs-lookup"><span data-stu-id="bc407-153">**Data to be pasted**</span></span>  
 <span data-ttu-id="bc407-154">Affiche un exemple de contenu du Presse-papiers.</span><span class="sxs-lookup"><span data-stu-id="bc407-154">Shows a sample of the Clipboard contents.</span></span> <span data-ttu-id="bc407-155">Les données existantes dans la table de destination sont supprimées et les nouvelles lignes sont insérées dans la table.</span><span class="sxs-lookup"><span data-stu-id="bc407-155">The existing data in the destination table will be deleted and the new rows will be inserted into the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc407-156">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bc407-156">See Also</span></span>  
 <span data-ttu-id="bc407-157">[Importer des données &#40;&#41;tabulaire SSAS](import-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bc407-157">[Import Data &#40;SSAS Tabular&#41;](import-data-ssas-tabular.md) </span></span>  
 <span data-ttu-id="bc407-158">[Sources de données prises en charge &#40;&#41;tabulaire SSAS](tabular-models/data-sources-supported-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="bc407-158">[Data Sources Supported &#40;SSAS Tabular&#41;](tabular-models/data-sources-supported-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="bc407-159">Définir le type de données d’une colonne &#40;SSAS Tabulaire&#41;</span><span class="sxs-lookup"><span data-stu-id="bc407-159">Set the Data Type of a Column &#40;SSAS Tabular&#41;</span></span>](tabular-models/set-the-data-type-of-a-column-ssas-tabular.md)  
  
  
