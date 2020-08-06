---
title: Signets | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bookmarks [OLE DB]
- SQL Server Native Client OLE DB provider, bookmarks
- rowsets [OLE DB], bookmarks
- OLE DB rowsets, bookmarks
ms.assetid: 7d9076f2-bf9c-452e-b816-70371a0c1644
author: rothja
ms.author: jroth
ms.openlocfilehash: be8e5486e5a442ddafa133a9cbd3f408d30a50d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706412"
---
# <a name="bookmarks"></a><span data-ttu-id="ca90f-102">Signets</span><span class="sxs-lookup"><span data-stu-id="ca90f-102">Bookmarks</span></span>
  <span data-ttu-id="ca90f-103">Les signets permettent aux consommateurs de revenir rapidement à une ligne.</span><span class="sxs-lookup"><span data-stu-id="ca90f-103">Bookmarks let consumers quickly return to a row.</span></span> <span data-ttu-id="ca90f-104">Avec les signets, les consommateurs peuvent accéder aléatoirement aux lignes selon la valeur du signet.</span><span class="sxs-lookup"><span data-stu-id="ca90f-104">With bookmarks, consumers can access rows randomly based on the bookmark value.</span></span> <span data-ttu-id="ca90f-105">La colonne du signet est la colonne 0 dans l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="ca90f-105">The bookmark column is column 0 in the rowset.</span></span> <span data-ttu-id="ca90f-106">Le consommateur attribue la valeur de champ dwFlag de la structure de liaison à DBCOLUMNSINFO_ISBOOKMARK pour indiquer que la colonne est utilisée comme signet.</span><span class="sxs-lookup"><span data-stu-id="ca90f-106">The consumer sets the dwFlag field value of the binding structure to DBCOLUMNSINFO_ISBOOKMARK to indicate that the column is used as a bookmark.</span></span> <span data-ttu-id="ca90f-107">Le consommateur définit également la propriété d'ensemble de lignes DBPROP_BOOKMARKS avec la valeur VARIANT_TRUE.</span><span class="sxs-lookup"><span data-stu-id="ca90f-107">The consumer also sets the rowset property DBPROP_BOOKMARKS to VARIANT_TRUE.</span></span> <span data-ttu-id="ca90f-108">La colonne 0 peut ainsi être présente dans l'ensemble de lignes.</span><span class="sxs-lookup"><span data-stu-id="ca90f-108">This lets column 0 be present in the rowset.</span></span> <span data-ttu-id="ca90f-109">Puis, la méthode **IRowsetLocate::GetRowsAt** est utilisée pour récupérer (fetch) les lignes, en commençant par la ligne spécifiée comme offset d’un signet.</span><span class="sxs-lookup"><span data-stu-id="ca90f-109">The **IRowsetLocate::GetRowsAt** method is then used to fetch rows, starting with the row specified as an offset from a bookmark.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca90f-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca90f-110">See Also</span></span>  
 [<span data-ttu-id="ca90f-111">Ensembles de lignes</span><span class="sxs-lookup"><span data-stu-id="ca90f-111">Rowsets</span></span>](rowsets.md)  
  
  
