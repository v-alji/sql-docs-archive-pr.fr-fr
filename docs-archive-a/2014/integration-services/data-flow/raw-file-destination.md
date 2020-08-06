---
title: Destination de fichier brut | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledest.f1
helpviewer_keywords:
- append options [Integration Services]
- destinations [Integration Services], Raw File
- raw data [Integration Services]
- writing raw data
- Raw File destination
ms.assetid: d311b458-aefc-4b4d-b1a1-4c0ebbb34214
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fc5ce99be6e467ba323137ef885cbb13bfb328ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87602913"
---
# <a name="raw-file-destination"></a><span data-ttu-id="74955-102">Destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="74955-102">Raw File Destination</span></span>
  <span data-ttu-id="74955-103">La destination de fichier brut écrit des données brutes dans un fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-103">The Raw File destination writes raw data to a file.</span></span> <span data-ttu-id="74955-104">Le format des données étant natif pour la destination, les données ne requièrent aucune traduction et peu d'analyse.</span><span class="sxs-lookup"><span data-stu-id="74955-104">Because the format of the data is native to the destination, the data requires no translation and little parsing.</span></span> <span data-ttu-id="74955-105">Cela signifie que la destination de fichier brut peut écrire des données plus rapidement que d'autres destinations telles que les destinations de fichier plat et OLE DB.</span><span class="sxs-lookup"><span data-stu-id="74955-105">This means that the Raw File destination can write data more quickly than other destinations such as the Flat File and the OLE DB destinations.</span></span>  
  
 <span data-ttu-id="74955-106">Outre l'écriture de données brutes dans un fichier, vous pouvez également utiliser la destination de fichier brut pour générer un fichier brut vide qui contient uniquement les colonnes (fichier réservé aux métadonnées), sans avoir à exécuter le package.</span><span class="sxs-lookup"><span data-stu-id="74955-106">In addition to writing raw data to a file, you can also use the Raw File destination to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="74955-107">La source de fichier brut vous permet de récupérer les données brutes précédemment écrites par la destination.</span><span class="sxs-lookup"><span data-stu-id="74955-107">You use the Raw File source to retrieve raw data that was previously written by the destination.</span></span> <span data-ttu-id="74955-108">Vous pouvez également faire pointer la source de fichier brut vers le fichier réservé aux métadonnées.</span><span class="sxs-lookup"><span data-stu-id="74955-108">You can also point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="74955-109">Le format de fichier brut contient les informations de tri.</span><span class="sxs-lookup"><span data-stu-id="74955-109">The raw file format contains sort information.</span></span> <span data-ttu-id="74955-110">La destination de fichier brut enregistre toutes les informations de tri, y compris les indicateurs de comparaison des colonnes de chaîne.</span><span class="sxs-lookup"><span data-stu-id="74955-110">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="74955-111">La source de fichier brut lit et applique les informations de tri.</span><span class="sxs-lookup"><span data-stu-id="74955-111">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="74955-112">Vous avez la possibilité de configurer la source de fichier brut pour ignorer les indicateurs de tri du fichier, à l'aide de l'éditeur avancé.</span><span class="sxs-lookup"><span data-stu-id="74955-112">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="74955-113">Pour plus d’informations sur les indicateurs de comparaison, consultez [Comparaison de données de type chaîne](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="74955-113">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="74955-114">Vous pouvez configurer la destination de fichier brut de plusieurs manières :</span><span class="sxs-lookup"><span data-stu-id="74955-114">You can configure the Raw File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="74955-115">Spécifiez un mode d'accès qui est soit le nom du fichier, soit une variable contenant le nom du fichier dans lequel la destination de fichier brut écrit.</span><span class="sxs-lookup"><span data-stu-id="74955-115">Specify an access mode which is either the name of the file or a variable that contains the name of the file to which the Raw File destination writes.</span></span>  
  
-   <span data-ttu-id="74955-116">Indiquez si la destination de fichier brut ajoute des données à un fichier existant qui possède le même nom ou si elle crée un fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-116">Indicate whether the Raw File destination appends data to an existing file that has the same name or creates a new file.</span></span>  
  
 <span data-ttu-id="74955-117">On utilise fréquemment la destination de fichier brut pour écrire des résultats intermédiaires de données partiellement traitées entre des exécutions de packages.</span><span class="sxs-lookup"><span data-stu-id="74955-117">The Raw File destination is frequently used to write intermediary results of partly processed data between package executions.</span></span> <span data-ttu-id="74955-118">Le stockage de données brutes signifie qu'elles peuvent être lues rapidement par une source de fichier brut, puis davantage transformées avant d'être chargées dans leur destination finale.</span><span class="sxs-lookup"><span data-stu-id="74955-118">Storing raw data means that the data can be read quickly by a Raw File source and then further transformed before it is loaded into its final destination.</span></span> <span data-ttu-id="74955-119">Par exemple, un package peut s'exécuter à plusieurs reprises et à chaque fois écrire des données brutes dans des fichiers.</span><span class="sxs-lookup"><span data-stu-id="74955-119">For example, a package might run several times, and each time write raw data to files.</span></span> <span data-ttu-id="74955-120">Ultérieurement, un package différent peut utiliser la source de fichier brut pour lire à partir de chaque fichier, utiliser une transformation d'union totale pour fusionner les données en un jeu de données, puis appliquer des transformations supplémentaires qui résument les données avant de les charger dans leur destination finale, telle qu'une table [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="74955-120">Later, a different package can use the Raw File source to read from each file, use a Union All transformation to merge the data into one data set, and then apply additional transformations that summarize the data before loading the data into its final destination such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74955-121">La destination de fichier brut prend en charge les données nulles mais non les données d'objets BLOB (Binary Large Objects).</span><span class="sxs-lookup"><span data-stu-id="74955-121">The Raw File destination supports null data but not binary large object (BLOB) data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="74955-122">La destination de fichier brut n'utilise pas de gestionnaire de connexions.</span><span class="sxs-lookup"><span data-stu-id="74955-122">The Raw File destination does not use a connection manager.</span></span>  
  
 <span data-ttu-id="74955-123">Cette source possède une entrée régulière.</span><span class="sxs-lookup"><span data-stu-id="74955-123">This source has one regular input.</span></span> <span data-ttu-id="74955-124">Elle ne prend pas en charge de sortie d'erreur.</span><span class="sxs-lookup"><span data-stu-id="74955-124">It does not support an error output.</span></span>  
  
## <a name="append-and-new-file-options"></a><span data-ttu-id="74955-125">Options d'ajout et de nouveau fichier</span><span class="sxs-lookup"><span data-stu-id="74955-125">Append and New File Options</span></span>  
 <span data-ttu-id="74955-126">La propriété WriteOption inclut des options permettant d’ajouter des données à un fichier existant ou de créer un fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-126">The WriteOption property includes options to append data to an existing file or create a new file.</span></span>  
  
 <span data-ttu-id="74955-127">Le tableau suivant décrit les options disponibles pour la propriété WriteOption.</span><span class="sxs-lookup"><span data-stu-id="74955-127">The following table describes the available options for the WriteOption property.</span></span>  
  
|<span data-ttu-id="74955-128">Option</span><span class="sxs-lookup"><span data-stu-id="74955-128">Option</span></span>|<span data-ttu-id="74955-129">Description</span><span class="sxs-lookup"><span data-stu-id="74955-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="74955-130">Ajouter</span><span class="sxs-lookup"><span data-stu-id="74955-130">Append</span></span>|<span data-ttu-id="74955-131">Ajoute les données à un fichier existant.</span><span class="sxs-lookup"><span data-stu-id="74955-131">Appends data to an existing file.</span></span> <span data-ttu-id="74955-132">Les métadonnées des données ajoutées doivent correspondre au format de fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-132">The metadata of the appended data must match the file format.</span></span>|  
|<span data-ttu-id="74955-133">Toujours créer</span><span class="sxs-lookup"><span data-stu-id="74955-133">Create always</span></span>|<span data-ttu-id="74955-134">Crée toujours un nouveau fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-134">Always creates a new file.</span></span>|  
|<span data-ttu-id="74955-135">Créer une fois</span><span class="sxs-lookup"><span data-stu-id="74955-135">Create once</span></span>|<span data-ttu-id="74955-136">Crée un nouveau fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-136">Creates a new file.</span></span> <span data-ttu-id="74955-137">Si le fichier existe, le composant échoue.</span><span class="sxs-lookup"><span data-stu-id="74955-137">If the file exists, the component fails.</span></span>|  
|<span data-ttu-id="74955-138">Tronquer et ajouter</span><span class="sxs-lookup"><span data-stu-id="74955-138">Truncate and append</span></span>|<span data-ttu-id="74955-139">Tronque un fichier existant, puis écrit les données dans le fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-139">Truncates an existing file and then writes the data to the file.</span></span> <span data-ttu-id="74955-140">Les métadonnées des données ajoutées doivent correspondre au format de fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-140">The metadata of the appended data must match the file format.</span></span>|  
  
 <span data-ttu-id="74955-141">Voici des éléments importants relatifs à l'ajout de données :</span><span class="sxs-lookup"><span data-stu-id="74955-141">The following are important items about appending data:</span></span>  
  
-   <span data-ttu-id="74955-142">L'ajout de données à un fichier brut existant n'entraîne pas un nouveau tri des données.</span><span class="sxs-lookup"><span data-stu-id="74955-142">Appending data to an existing raw file does not re-sort the data.</span></span>  
  
     <span data-ttu-id="74955-143">Vous devez vous assurer que les clés triées restent dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="74955-143">You need to make certain that the sorted keys remain in the correct order.</span></span>  
  
-   <span data-ttu-id="74955-144">L'ajout de données à un fichier brut existant n'entraîne pas de modification des métadonnées du fichier (informations de tri).</span><span class="sxs-lookup"><span data-stu-id="74955-144">Appending data to an existing raw file does not change the file metadata (sort information).</span></span>  
  
 <span data-ttu-id="74955-145">Par exemple, un package lit les données triées sur ProductKey (PK).</span><span class="sxs-lookup"><span data-stu-id="74955-145">For example, a package reads data sorted on the ProductKey (PK).</span></span> <span data-ttu-id="74955-146">Le flux de données du package ajoute les données à un fichier brut existant.</span><span class="sxs-lookup"><span data-stu-id="74955-146">The package data flow appends the data to an existing raw file.</span></span> <span data-ttu-id="74955-147">Lors de la première exécution du package, trois lignes sont reçues (PK 1000, 1100, 1200).</span><span class="sxs-lookup"><span data-stu-id="74955-147">The first time the package runs, three rows are received (PK 1000, 1100, 1200).</span></span> <span data-ttu-id="74955-148">Le fichier brut contient désormais les données ci-après.</span><span class="sxs-lookup"><span data-stu-id="74955-148">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="74955-149">1000, productA</span><span class="sxs-lookup"><span data-stu-id="74955-149">1000, productA</span></span>  
  
-   <span data-ttu-id="74955-150">1100, productB</span><span class="sxs-lookup"><span data-stu-id="74955-150">1100, productB</span></span>  
  
-   <span data-ttu-id="74955-151">1200, productC</span><span class="sxs-lookup"><span data-stu-id="74955-151">1200, productC</span></span>  
  
 <span data-ttu-id="74955-152">Lors de la seconde exécution du package, deux nouvelles lignes sont reçues (PK 1001, 1300).</span><span class="sxs-lookup"><span data-stu-id="74955-152">The second time the package runs, two new rows are received (PK 1001, 1300).</span></span> <span data-ttu-id="74955-153">Le fichier brut contient désormais les données ci-après.</span><span class="sxs-lookup"><span data-stu-id="74955-153">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="74955-154">1000, productA</span><span class="sxs-lookup"><span data-stu-id="74955-154">1000, productA</span></span>  
  
-   <span data-ttu-id="74955-155">1100, productB</span><span class="sxs-lookup"><span data-stu-id="74955-155">1100, productB</span></span>  
  
-   <span data-ttu-id="74955-156">1200, productC</span><span class="sxs-lookup"><span data-stu-id="74955-156">1200, productC</span></span>  
  
-   <span data-ttu-id="74955-157">1001, productD</span><span class="sxs-lookup"><span data-stu-id="74955-157">1001, productD</span></span>  
  
-   <span data-ttu-id="74955-158">1300, productE</span><span class="sxs-lookup"><span data-stu-id="74955-158">1300, productE</span></span>  
  
 <span data-ttu-id="74955-159">Les nouvelles données sont ajoutées à la fin du fichier brut et les clés triées (PK) ne sont pas ordonnées.</span><span class="sxs-lookup"><span data-stu-id="74955-159">The new data is appended to the end of the raw file, and the sorted keys (PK) are out of order.</span></span> <span data-ttu-id="74955-160">Par ailleurs, l’opération d’ajout n’a pas changé les métadonnées du fichier (informations de tri).</span><span class="sxs-lookup"><span data-stu-id="74955-160">In addition, the append operation didn't change the file metadata (sort information).</span></span> <span data-ttu-id="74955-161">Si vous lisez le fichier à l'aide de la source de fichier brut, le composant indique que le fichier est toujours trié sur PK même si les données du fichier ne sont plus dans le bon ordre.</span><span class="sxs-lookup"><span data-stu-id="74955-161">If you read the file by using the Raw File source, the component indicates that the file is still sorted on PK even though the data in the file is no longer in the correct order.</span></span>  
  
 <span data-ttu-id="74955-162">Pour conserver les clés triées dans le bon ordre lors de l'ajout de données, concevez le flux de données du package comme suit :</span><span class="sxs-lookup"><span data-stu-id="74955-162">To keep the sorted keys in the correct order while appending data, you can design the package data flow as follows:</span></span>  
  
1.  <span data-ttu-id="74955-163">Récupérez les nouvelles lignes via Source A.</span><span class="sxs-lookup"><span data-stu-id="74955-163">Retrieve new rows by using Source A.</span></span>  
  
2.  <span data-ttu-id="74955-164">Récupérez les lignes existantes de RawFile1 via Source B.</span><span class="sxs-lookup"><span data-stu-id="74955-164">Retrieve existing rows from RawFile1 using Source B.</span></span>  
  
3.  <span data-ttu-id="74955-165">Combinez les entrées de Source A et Source B à l'aide de la transformation Union All.</span><span class="sxs-lookup"><span data-stu-id="74955-165">Combine the inputs from Source A and Source B by using the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="74955-166">Triez sur PK.</span><span class="sxs-lookup"><span data-stu-id="74955-166">Sort on PK.</span></span>  
  
5.  <span data-ttu-id="74955-167">Écrivez dans RawFile2 à l'aide de la destination de fichier brut.</span><span class="sxs-lookup"><span data-stu-id="74955-167">Write to RawFile2 by using the Raw File destination.</span></span>  
  
     <span data-ttu-id="74955-168">RawFile1 est verrouillé, car il est lu dans le flux de données.</span><span class="sxs-lookup"><span data-stu-id="74955-168">RawFile1 is locked because it's being read from, in the data flow.</span></span>  
  
6.  <span data-ttu-id="74955-169">Remplacez RawFile1 par RawFile2.</span><span class="sxs-lookup"><span data-stu-id="74955-169">Replace RawFile1 with RawFile2.</span></span>  
  
### <a name="using-the-raw-file-destination-in-a-loop"></a><span data-ttu-id="74955-170">Utilisation de la destination de fichier brut dans une boucle</span><span class="sxs-lookup"><span data-stu-id="74955-170">Using the Raw File Destination in a Loop</span></span>  
 <span data-ttu-id="74955-171">Si le flux de données qui utilise la destination de fichier brut est dans une boucle, vous pouvez créer le fichier une fois puis ajouter les données au fichier lorsque la boucle se répète.</span><span class="sxs-lookup"><span data-stu-id="74955-171">If the data flow that uses the Raw File destination is in a loop, you may want to create the file once and then append data to the file when the loop repeats.</span></span> <span data-ttu-id="74955-172">Pour ajouter des données au fichier, les données ajoutées doivent correspondre au format du fichier existant.</span><span class="sxs-lookup"><span data-stu-id="74955-172">To append data to the file, the data that is appended must match the format of the existing file.</span></span>  
  
 <span data-ttu-id="74955-173">Pour créer le fichier dans la première itération de la boucle puis ajouter des lignes dans les itérations ultérieures de la boucle, procédez comme suit lors de la conception :</span><span class="sxs-lookup"><span data-stu-id="74955-173">To create the file in the first iteration of the loop, and then append rows in the subsequent iterations of the loop, you need to do the following at design time:</span></span>  
  
1.  <span data-ttu-id="74955-174">Définissez la propriété sur **CreateOnce** ou **CreateAlways**, et effectuez une itération de la boucle.</span><span class="sxs-lookup"><span data-stu-id="74955-174">Set the WriteOption property to **CreateOnce** or **CreateAlways**and run one iteration of the loop.</span></span> <span data-ttu-id="74955-175">Le fichier est créé.</span><span class="sxs-lookup"><span data-stu-id="74955-175">The file is created.</span></span> <span data-ttu-id="74955-176">Cette opération permet de s'assurer de la correspondance entre les métadonnées des données ajoutées et le fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-176">This ensures that the metadata of appended data and the file matches.</span></span>  
  
2.  <span data-ttu-id="74955-177">Réinitialisez la propriété WriteOption à **Append** et affectez à la propriété ValidateExternalMetadata la valeur `False` .</span><span class="sxs-lookup"><span data-stu-id="74955-177">Reset the WriteOption property to **Append** and set the ValidateExternalMetadata property to `False`.</span></span>  
  
 <span data-ttu-id="74955-178">Si vous utilisez l’option **TruncateAppend** au lieu de l’option **Append** , celle-ci tronque les lignes ajoutées dans les itérations précédentes, puis ajoute de nouvelles lignes.</span><span class="sxs-lookup"><span data-stu-id="74955-178">If you use the **TruncateAppend** option instead of the **Append** option, it will truncate rows that were added in any previous iteration, and then append new rows.</span></span> <span data-ttu-id="74955-179">L’utilisation de l’option **TruncateAppend** nécessite également que les données correspondent au format du fichier.</span><span class="sxs-lookup"><span data-stu-id="74955-179">Using the **TruncateAppend** option also requires that the data matches the file format.</span></span>  
  
## <a name="configuration-of-the-raw-file-destination"></a><span data-ttu-id="74955-180">Configuration de la destination de fichier brut</span><span class="sxs-lookup"><span data-stu-id="74955-180">Configuration of the Raw File Destination</span></span>  
 <span data-ttu-id="74955-181">Vous pouvez définir les propriétés par le biais du concepteur [!INCLUDE[ssIS](../../includes/ssis-md.md)] ou par programmation.</span><span class="sxs-lookup"><span data-stu-id="74955-181">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="74955-182">La boîte de dialogue **Éditeur avancé** reflète les propriétés qui peuvent être définies par programmation.</span><span class="sxs-lookup"><span data-stu-id="74955-182">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="74955-183">Pour plus d'informations sur les propriétés définissables dans la boîte de dialogue **Éditeur avancé** ou par programmation, cliquez sur l'une des rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="74955-183">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="74955-184">Propriétés communes</span><span class="sxs-lookup"><span data-stu-id="74955-184">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="74955-185">Propriétés personnalisées des fichiers bruts</span><span class="sxs-lookup"><span data-stu-id="74955-185">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="74955-186">Tâches associées</span><span class="sxs-lookup"><span data-stu-id="74955-186">Related Tasks</span></span>  
 <span data-ttu-id="74955-187">Pour plus d’informations sur la définition des propriétés du composant, consultez [Définir les propriétés d’un composant de flux de données](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="74955-187">For information about how to set properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="74955-188">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="74955-188">Related Content</span></span>  
 <span data-ttu-id="74955-189">Entrée de blog, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), sur sqlservercentral.com.</span><span class="sxs-lookup"><span data-stu-id="74955-189">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74955-190">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74955-190">See Also</span></span>  
 <span data-ttu-id="74955-191">[Source de fichier brut](raw-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="74955-191">[Raw File Source](raw-file-source.md) </span></span>  
 [<span data-ttu-id="74955-192">Flux de données</span><span class="sxs-lookup"><span data-stu-id="74955-192">Data Flow</span></span>](data-flow.md)  
  
  
