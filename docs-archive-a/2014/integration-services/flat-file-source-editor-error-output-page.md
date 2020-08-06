---
title: Éditeur de source de fichier plat (page sortie d’erreur) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfilesourceadapter.errorhandling.f1
helpviewer_keywords:
- Flat File Source Editor
ms.assetid: c50500e7-0c74-42a0-865f-301f03feffab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 096de22c65d605fc1beea06cbb6ad5909788b408
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601595"
---
# <a name="flat-file-source-editor-error-output-page"></a><span data-ttu-id="372c5-102">Éditeur de source de fichier plat (page Sortie d'erreur)</span><span class="sxs-lookup"><span data-stu-id="372c5-102">Flat File Source Editor (Error Output Page)</span></span>
  <span data-ttu-id="372c5-103">Utilisez la page **Sortie d’erreur** de la boîte de dialogue **Éditeur de source de fichier plat** pour sélectionner les options de gestion des erreurs et définir les propriétés des colonnes de sortie d’erreur.</span><span class="sxs-lookup"><span data-stu-id="372c5-103">Use the **Error Output** page of the **Flat File Source Editor** dialog box to select error-handling options and to set properties on error output columns.</span></span>\  
  
 <span data-ttu-id="372c5-104">Pour en savoir plus sur la source de fichier plat, consultez [Flat File Source](data-flow/flat-file-source.md).</span><span class="sxs-lookup"><span data-stu-id="372c5-104">To learn more about the Flat File source, see [Flat File Source](data-flow/flat-file-source.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="372c5-105">Options</span><span class="sxs-lookup"><span data-stu-id="372c5-105">Options</span></span>  
 <span data-ttu-id="372c5-106">**Entrée/sortie**</span><span class="sxs-lookup"><span data-stu-id="372c5-106">**Input/Output**</span></span>  
 <span data-ttu-id="372c5-107">Affichez le nom de la source de données.</span><span class="sxs-lookup"><span data-stu-id="372c5-107">View the name of the data source.</span></span>  
  
 <span data-ttu-id="372c5-108">**Colonne**</span><span class="sxs-lookup"><span data-stu-id="372c5-108">**Column**</span></span>  
 <span data-ttu-id="372c5-109">Affiche les colonnes externes (sources) que vous avez sélectionnées dans la page **Gestionnaire de connexions** de la boîte de dialogue **Éditeur de source de fichier plat**.</span><span class="sxs-lookup"><span data-stu-id="372c5-109">View the external (source) columns that you selected on the **Connection Manager** page of the **Flat File Source Editor**dialog box.</span></span>  
  
 <span data-ttu-id="372c5-110">**Error**</span><span class="sxs-lookup"><span data-stu-id="372c5-110">**Error**</span></span>  
 <span data-ttu-id="372c5-111">Indiquez ce qui doit se produire lorsqu'une erreur se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="372c5-111">Specify what should happen when an error occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="372c5-112">**Rubriques connexes :** [Gestion des erreurs dans les données](data-flow/error-handling-in-data.md)</span><span class="sxs-lookup"><span data-stu-id="372c5-112">**Related Topics:** [Error Handling in Data](data-flow/error-handling-in-data.md)</span></span>  
  
 <span data-ttu-id="372c5-113">**Troncation**</span><span class="sxs-lookup"><span data-stu-id="372c5-113">**Truncation**</span></span>  
 <span data-ttu-id="372c5-114">Indiquez ce qui doit se produire lorsqu'une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="372c5-114">Specify what should happen when a truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="372c5-115">**Description**</span><span class="sxs-lookup"><span data-stu-id="372c5-115">**Description**</span></span>  
 <span data-ttu-id="372c5-116">Affiche la description de l'erreur.</span><span class="sxs-lookup"><span data-stu-id="372c5-116">View the description of the error.</span></span>  
  
 <span data-ttu-id="372c5-117">**Définir cette valeur sur les cellules sélectionnées**</span><span class="sxs-lookup"><span data-stu-id="372c5-117">**Set this value to selected cells**</span></span>  
 <span data-ttu-id="372c5-118">Indiquez ce qui doit se produire pour l'ensemble des cellules sélectionnées lorsqu'une erreur ou une troncation se produit : ignorer l'échec, rediriger la ligne ou faire échouer le composant.</span><span class="sxs-lookup"><span data-stu-id="372c5-118">Specify what should happen to all the selected cells when an error or truncation occurs: ignore the failure, redirect the row, or fail the component.</span></span>  
  
 <span data-ttu-id="372c5-119">**Appliquer**</span><span class="sxs-lookup"><span data-stu-id="372c5-119">**Apply**</span></span>  
 <span data-ttu-id="372c5-120">Appliquez l'option de gestion des erreurs aux cellules sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="372c5-120">Apply the error handling option to the selected cells.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372c5-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="372c5-121">See Also</span></span>  
 <span data-ttu-id="372c5-122">[Guide de référence des erreurs et des messages propres à Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="372c5-122">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="372c5-123">[Éditeur de source de fichier plat &#40;page Gestionnaire de connexions&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span><span class="sxs-lookup"><span data-stu-id="372c5-123">[Flat File Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/flat-file-source-editor-connection-manager-page.md) </span></span>  
 <span data-ttu-id="372c5-124">[Éditeur de source de fichier plat &#40;page colonnes&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="372c5-124">[Flat File Source Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="372c5-125">Gestionnaire de connexions de fichiers plats</span><span class="sxs-lookup"><span data-stu-id="372c5-125">Flat File Connection Manager</span></span>](connection-manager/file-connection-manager.md)  
  
  
