---
title: Éditeur de source de fichier plat (page Gestionnaire de connexions) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.connection.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: 2efd6baa-ed75-4f3f-b667-514024cebdb8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 03c1693c001dad2c8e90211b065eda208c42a07b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601593"
---
# <a name="flat-file-source-editor-connection-manager-page"></a><span data-ttu-id="65976-102">Éditeur de source de fichier plat (page Gestionnaire de connexions)</span><span class="sxs-lookup"><span data-stu-id="65976-102">Flat File Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="65976-103">Utilisez la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source de fichier plat** pour sélectionner le gestionnaire de connexions de fichiers plats qui sera utilisé par la source de fichier plat.</span><span class="sxs-lookup"><span data-stu-id="65976-103">Use the **Connection Manager** page of the **Flat File Source Editor** dialog box to select the connection manager that the Flat File source will use.</span></span> <span data-ttu-id="65976-104">La source de fichier plat lit les données d'un fichier texte qui peut être au format délimité, à largeur fixe ou mixte.</span><span class="sxs-lookup"><span data-stu-id="65976-104">The Flat File source reads data from a text file, which can be in a delimited, fixed width, or mixed format.</span></span>  
  
 <span data-ttu-id="65976-105">Une source de fichier plat peut utiliser l'un des types de gestionnaires de connexions suivants :</span><span class="sxs-lookup"><span data-stu-id="65976-105">A Flat File source can use one of the following types of connection managers:</span></span>  
  
-   <span data-ttu-id="65976-106">Un gestionnaire de connexions de fichiers plats si la source est un fichier plat unique.</span><span class="sxs-lookup"><span data-stu-id="65976-106">A Flat File connection manager if the source is a single flat file.</span></span> <span data-ttu-id="65976-107">Pour plus d'informations, consultez [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="65976-107">For more information, see [Flat File Connection Manager](connection-manager/file-connection-manager.md).</span></span>  
  
-   <span data-ttu-id="65976-108">Un gestionnaire de connexions de fichiers plats multiples si la source se compose de fichiers plats multiples et si la tâche de flux de données se trouve dans un conteneur de boucles (conteneur de boucles For, par exemple).</span><span class="sxs-lookup"><span data-stu-id="65976-108">A Multiple Flat Files connection manager if the source is multiple flat files and the Data Flow task is inside a loop container, such as the For Loop container.</span></span> <span data-ttu-id="65976-109">Dans chaque boucle du conteneur, la source de fichier plat charge les données à partir du nom de fichier suivant fourni par le gestionnaire de connexions de fichiers plats multiples.</span><span class="sxs-lookup"><span data-stu-id="65976-109">On each loop of the container, the Flat File source loads data from the next file name that the Multiple Flat Files connection manager provides.</span></span> <span data-ttu-id="65976-110">Pour plus d’informations, consultez [Gestionnaire de connexion de fichiers plats multiples](connection-manager/multiple-flat-files-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="65976-110">For more information, see [Multiple Flat Files Connection Manager](connection-manager/multiple-flat-files-connection-manager.md).</span></span>  
  
 <span data-ttu-id="65976-111">Pour en savoir plus sur la source de fichier plat, consultez [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="65976-111">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="65976-112">Options</span><span class="sxs-lookup"><span data-stu-id="65976-112">Options</span></span>  
 <span data-ttu-id="65976-113">**Gestionnaire de connexions de fichiers plats**</span><span class="sxs-lookup"><span data-stu-id="65976-113">**Flat file connection manager**</span></span>  
 <span data-ttu-id="65976-114">Sélectionnez un gestionnaire de connexions existant dans la liste ou créez un gestionnaire de connexions en cliquant sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="65976-114">Select an existing connection manager from the list, or create a new connection manager by clicking **New**.</span></span>  
  
 <span data-ttu-id="65976-115">**Nouveau**</span><span class="sxs-lookup"><span data-stu-id="65976-115">**New**</span></span>  
 <span data-ttu-id="65976-116">Créez un gestionnaire de connexions à l’aide de la boîte de dialogue **Éditeur du gestionnaire de connexions de fichiers plats** .</span><span class="sxs-lookup"><span data-stu-id="65976-116">Create a new connection manager by using the **Flat File Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="65976-117">**Conserver les valeurs NULL de la source comme valeurs NULL dans le flux de données**</span><span class="sxs-lookup"><span data-stu-id="65976-117">**Retain null values from the source as null values in the data flow**</span></span>  
 <span data-ttu-id="65976-118">Indique s'il faut conserver les valeurs NULL lorsque les données sont extraites.</span><span class="sxs-lookup"><span data-stu-id="65976-118">Specify whether to keep null values when data is extracted.</span></span> <span data-ttu-id="65976-119">La valeur par défaut de cette propriété est **false**.</span><span class="sxs-lookup"><span data-stu-id="65976-119">The default value of this property is **false**.</span></span> <span data-ttu-id="65976-120">Lorsque cette propriété a la valeur `alse`, la source de fichier plat remplace les valeurs NULL des données sources par les valeurs par défaut appropriées pour chaque colonne, par exemple des chaînes vides pour les colonnes de chaînes et zéro pour les colonnes numériques.</span><span class="sxs-lookup"><span data-stu-id="65976-120">When this value is f`alse`, the Flat File source replaces null values from the source data with appropriate default values for each column, such as empty strings for string columns and zero for numeric columns.</span></span>  
  
 <span data-ttu-id="65976-121">**Préversion**</span><span class="sxs-lookup"><span data-stu-id="65976-121">**Preview**</span></span>  
 <span data-ttu-id="65976-122">Affichez un aperçu des résultats à l’aide de la boîte de dialogue **Vue de données** .</span><span class="sxs-lookup"><span data-stu-id="65976-122">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="65976-123">L'aperçu peut afficher jusqu'à 200 lignes.</span><span class="sxs-lookup"><span data-stu-id="65976-123">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65976-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65976-124">See Also</span></span>  
 <span data-ttu-id="65976-125">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="65976-125">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="65976-126">[Éditeur de source de fichier plat &#40;page colonnes&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="65976-126">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="65976-127">[Éditeur de source de fichier plat &#40;page sortie d’erreur&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="65976-127">[Flat File Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/flat-file-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="65976-128">Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="65976-128">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
