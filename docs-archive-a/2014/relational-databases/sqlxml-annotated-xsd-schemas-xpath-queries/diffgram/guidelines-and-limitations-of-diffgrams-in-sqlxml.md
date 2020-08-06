---
title: Instructions et limitations des DiffGrams dans SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], about DiffGrams
ms.assetid: cf8689c4-2a63-4d05-b202-21b5ff187d7f
author: rothja
ms.author: jroth
ms.openlocfilehash: 0f2901f02f8b4a8fc7b77dcb6c1cb166cb6af6ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610556"
---
# <a name="guidelines-and-limitations-of-diffgrams-in-sqlxml"></a><span data-ttu-id="d809e-102">Instructions et limitations de DiffGrams dans SQLXML</span><span class="sxs-lookup"><span data-stu-id="d809e-102">Guidelines and Limitations of DiffGrams in SQLXML</span></span>
  <span data-ttu-id="d809e-103">Souvenez-vous des éléments suivants lors de l'utilisation de DiffGrams avec SQLXML 4.0 :</span><span class="sxs-lookup"><span data-stu-id="d809e-103">Remember the following when using DiffGrams with SQLXML 4.0:</span></span>  
  
-   <span data-ttu-id="d809e-104">Les types de données BLOB tels que `text/ntext` et les images ne doivent pas être utilisés dans le bloc `<diffgr:before>` lors de l'utilisation de DiffGrams, car cela les inclura dans le contrôle d'accès concurrentiel.</span><span class="sxs-lookup"><span data-stu-id="d809e-104">Binary large object (BLOB) types like `text/ntext` and images should not be used in the `<diffgr:before>` block in when working with DiffGrams, because this will include them for use in concurrency control.</span></span> <span data-ttu-id="d809e-105">Cela peut entraîner des problèmes avec [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] en raison des limitations sur la comparaison pour les types BLOB.</span><span class="sxs-lookup"><span data-stu-id="d809e-105">This can cause problems with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="d809e-106">Par exemple, le mot clé LIKE est utilisé dans la clause WHERE pour effectuer une comparaison entre les colonnes du type de données `text` ; toutefois, les comparaisons échouent dans le cas de types BLOB lorsque la taille des données dépasse 8 Ko.</span><span class="sxs-lookup"><span data-stu-id="d809e-106">For example, the LIKE keyword is used in the WHERE clause for comparing between columns of the `text` data type; however, comparisons will fail in the case of BLOB types where the size of the data is greater than 8K.</span></span>  
  
-   <span data-ttu-id="d809e-107">Les caractères spéciaux dans les données `ntext` peuvent entraîner des problèmes avec SQLXML 4.0 en raison des limitations sur la comparaison pour les types BLOB.</span><span class="sxs-lookup"><span data-stu-id="d809e-107">Special characters in `ntext` data can cause problems with SQLXML 4.0 because of the limitations on comparison for BLOB types.</span></span> <span data-ttu-id="d809e-108">Par exemple, l'utilisation de "[Serializable]" dans le bloc `<diffgr:before>` d'un DiffGram, s'il est utilisé dans le contrôle d'accès concurrentiel d'une colonne de type `ntext`, échouera avec la description d'erreur SQLOLEDB suivante :</span><span class="sxs-lookup"><span data-stu-id="d809e-108">For example, the use of "[Serializable]" in the `<diffgr:before>` block of a DiffGram when used in concurrency checking of a column of `ntext` type will fail with the following SQLOLEDB error description:</span></span>  
  
    ```  
    Empty update, no updatable rows found   Transaction aborted  
    ```  
  
  
