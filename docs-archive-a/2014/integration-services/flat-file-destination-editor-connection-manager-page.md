---
title: Éditeur de destination de fichier plat (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6997b72851c2b7bfc56445e6ddb01cfe6e9b04cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601600"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a><span data-ttu-id="5e77a-102">Éditeur de destination de fichier plat (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="5e77a-102">Flat File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="5e77a-103">Utilisez la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de destination de fichier plat** pour sélectionner la connexion de fichier plat de la destination et spécifier si elle doit remplacer le fichier de destination existant ou lui être ajoutée.</span><span class="sxs-lookup"><span data-stu-id="5e77a-103">Use the **Connection Manager** page of the **Flat File Destination Editor** dialog box to select the flat file connection for the destination, and to specify whether to overwrite or append to the existing destination file.</span></span> <span data-ttu-id="5e77a-104">La destination de fichier plat écrit ses données dans un fichier texte.</span><span class="sxs-lookup"><span data-stu-id="5e77a-104">The flat file destination writes data to a text file.</span></span> <span data-ttu-id="5e77a-105">Ce fichier texte peut être d'un format délimité, à largeur fixe avec séparateur de lignes, ou en drapeau à droite.</span><span class="sxs-lookup"><span data-stu-id="5e77a-105">This text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="5e77a-106">Pour en savoir plus sur la destination de fichier plat, consultez [Flat File Destination](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="5e77a-106">To learn more about the Flat File destination, see [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="5e77a-107">Options</span><span class="sxs-lookup"><span data-stu-id="5e77a-107">Options</span></span>  
 <span data-ttu-id="5e77a-108">**Gestionnaire de connexions de fichiers plats**</span><span class="sxs-lookup"><span data-stu-id="5e77a-108">**Flat File connection manager**</span></span>  
 <span data-ttu-id="5e77a-109">Sélectionnez un gestionnaire de connexions existant dans la zone de liste ou créez une connexion en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="5e77a-109">Select an existing connection manager by using the list box, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="5e77a-110">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="5e77a-110">**New**</span></span>  
 <span data-ttu-id="5e77a-111">Créez une connexion à l’aide des boîtes de dialogue **Format de fichier plat** et **Éditeur du gestionnaire de connexions de fichiers plats** .</span><span class="sxs-lookup"><span data-stu-id="5e77a-111">Create a new connection by using the **Flat File Format** and **Flat File Connection Manager Editor** dialog boxes.</span></span>  
  
 <span data-ttu-id="5e77a-112">En plus des formats de fichier plat standard (délimité, largeur fixe et en drapeau à droite), la boîte de dialogue **Format de fichier plat** contient une quatrième option : **Largeur fixe avec séparateurs de lignes**.</span><span class="sxs-lookup"><span data-stu-id="5e77a-112">In addition to the standard flat file formats of delimited, fixed width, and ragged right, the **Flat File Format** dialog box has a fourth option, **Fixed width with row delimiters**.</span></span> <span data-ttu-id="5e77a-113">Cette option représente un cas particulier du format en drapeau à droite dans lequel [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] ajoute une colonne factice comme dernière colonne de données.</span><span class="sxs-lookup"><span data-stu-id="5e77a-113">This option represents a special case of the ragged-right format in which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adds a dummy column as the final column of data.</span></span> <span data-ttu-id="5e77a-114">Cette colonne factice garantit que la dernière colonne a une largeur fixe.</span><span class="sxs-lookup"><span data-stu-id="5e77a-114">This dummy column ensures that the final column has a fixed width.</span></span>  
  
 <span data-ttu-id="5e77a-115">L'option **Largeur fixe avec séparateurs de lignes** n'est pas disponible dans l' **éditeur du gestionnaire de connexions de fichiers plats**.</span><span class="sxs-lookup"><span data-stu-id="5e77a-115">The **Fixed width with row delimiters** option is not available in the **Flat File Connection Manager Editor**.</span></span> <span data-ttu-id="5e77a-116">Le cas échéant, vous pouvez émuler cette option dans l'éditeur.</span><span class="sxs-lookup"><span data-stu-id="5e77a-116">If necessary, you can emulate this option in the editor.</span></span> <span data-ttu-id="5e77a-117">Pour émuler cette option, dans la page **Général** de l' **éditeur du gestionnaire de connexions de fichiers plats**, pour **Format**, sélectionnez **En drapeau à droite**.</span><span class="sxs-lookup"><span data-stu-id="5e77a-117">To emulate this option, on the **General** page of the **Flat File Connection Manager Editor**, for **Format**, select **Ragged right**.</span></span> <span data-ttu-id="5e77a-118">Puis, dans la page **Avancé** de l'éditeur, ajoutez une colonne factice comme dernière colonne de données.</span><span class="sxs-lookup"><span data-stu-id="5e77a-118">Then on the **Advanced** page of the editor, add a new dummy column as the final column of data.</span></span>  
  
 <span data-ttu-id="5e77a-119">**Remplacer les données du fichier**</span><span class="sxs-lookup"><span data-stu-id="5e77a-119">**Overwrite data in the file**</span></span>  
 <span data-ttu-id="5e77a-120">Précisez si le fichier existant doit être remplacé ou si les données doivent lui être ajoutées.</span><span class="sxs-lookup"><span data-stu-id="5e77a-120">Indicate whether to overwrite an existing file, or to append data to it.</span></span>  
  
 <span data-ttu-id="5e77a-121">**En-tête**</span><span class="sxs-lookup"><span data-stu-id="5e77a-121">**Header**</span></span>  
 <span data-ttu-id="5e77a-122">Tapez un bloc de texte à insérer dans le fichier avant l'écriture des données.</span><span class="sxs-lookup"><span data-stu-id="5e77a-122">Type a block of text to insert into the file before any data is written.</span></span> <span data-ttu-id="5e77a-123">Utilisez cette option pour inclure des informations supplémentaires, telles que des titres de colonne.</span><span class="sxs-lookup"><span data-stu-id="5e77a-123">Use this option to include additional information, such as column headings.</span></span>  
  
 <span data-ttu-id="5e77a-124">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="5e77a-124">**Preview**</span></span>  
 <span data-ttu-id="5e77a-125">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Vue de données** .</span><span class="sxs-lookup"><span data-stu-id="5e77a-125">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="5e77a-126">L'aperçu peut afficher jusqu'à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="5e77a-126">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e77a-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5e77a-127">See Also</span></span>  
 <span data-ttu-id="5e77a-128">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="5e77a-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="5e77a-129">Éditeur de destination de fichier plat &#40;page Mappages&#41;</span><span class="sxs-lookup"><span data-stu-id="5e77a-129">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
