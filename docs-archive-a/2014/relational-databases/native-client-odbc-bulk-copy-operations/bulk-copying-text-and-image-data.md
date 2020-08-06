---
title: Copie en bloc de données text et image | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], text data
- SQL Server Native Client ODBC driver, bulk copy
- bulk copy [ODBC], image data
- ODBC, bulk copy operations
ms.assetid: 87155bfa-3a73-4158-9d4d-cb7435dac201
author: rothja
ms.author: jroth
ms.openlocfilehash: 9240fd0eb8c32ed39613824ea5a07764e277160c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614579"
---
# <a name="bulk-copying-text-and-image-data"></a><span data-ttu-id="faa3c-102">Copie en bloc de données Text et Image</span><span class="sxs-lookup"><span data-stu-id="faa3c-102">Bulk Copying Text and Image Data</span></span>
  <span data-ttu-id="faa3c-103">Les valeurs **Text**, **ntext**et **image** volumineuses sont copiées en bloc à l’aide de la fonction [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) .</span><span class="sxs-lookup"><span data-stu-id="faa3c-103">Large **text**, **ntext**, and **image** values are bulk copied using the [bcp_moretext](../native-client-odbc-extensions-bulk-copy-functions/bcp-moretext.md) function.</span></span> <span data-ttu-id="faa3c-104">Vous codez [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) pour la colonne **Text**, **ntext**ou **image** avec un pointeur *pData* défini sur null, indiquant que les données seront fournies avec **bcp_moretext**.</span><span class="sxs-lookup"><span data-stu-id="faa3c-104">You code [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) for the **text**, **ntext**, or **image** column with a *pData* pointer set to NULL indicating the data will be provided with **bcp_moretext**.</span></span> <span data-ttu-id="faa3c-105">Il est important de spécifier la longueur exacte des données fournies pour chaque colonne **Text**, **ntext**ou **image** dans chaque ligne copiée en bloc.</span><span class="sxs-lookup"><span data-stu-id="faa3c-105">It is important to specify the exact length of data supplied for each **text**, **ntext**,or **image** column in each bulk-copied row.</span></span> <span data-ttu-id="faa3c-106">Si la longueur des données d’une colonne est différente de la longueur de colonne spécifiée dans [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), utilisez [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) pour définir la longueur à la valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="faa3c-106">If the length of the data for a column is different from the column length specified in [bcp_bind](../native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md), use [bcp_collen](../native-client-odbc-extensions-bulk-copy-functions/bcp-collen.md) to set the length to the proper value.</span></span> <span data-ttu-id="faa3c-107">Une [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) envoie toutes les données non**textuelles**, non**ntext**et non-**image** . vous appelez ensuite **bcp_moretext** pour envoyer les données **Text**, **ntext**ou **image** dans des unités distinctes.</span><span class="sxs-lookup"><span data-stu-id="faa3c-107">A [bcp_sendrow](../native-client-odbc-extensions-bulk-copy-functions/bcp-sendrow.md) sends all the non-**text**, non-**ntext**, and non-**image** data; you then call **bcp_moretext** to send the **text**, **ntext**, or **image** data in separate units.</span></span> <span data-ttu-id="faa3c-108">Les fonctions de copie en bloc déterminent que toutes les données ont été envoyées pour la colonne **Text**, **ntext**ou **image** actuelle lorsque la somme des longueurs des données envoyées via **bcp_moretext** est égale à la longueur spécifiée dans la dernière **bcp_collen** ou **bcp_bind**.</span><span class="sxs-lookup"><span data-stu-id="faa3c-108">Bulk copy functions determine that all data has been sent for the current **text**, **ntext**, or **image** column when the sum of the lengths of data sent through **bcp_moretext** equals the length specified in the latest **bcp_collen** or **bcp_bind**.</span></span>  
  
 <span data-ttu-id="faa3c-109">**bcp_moretext** n’a aucun paramètre pour identifier une colonne.</span><span class="sxs-lookup"><span data-stu-id="faa3c-109">**bcp_moretext** has no parameter to identify a column.</span></span> <span data-ttu-id="faa3c-110">Lorsqu’il existe plusieurs colonnes **Text**, **ntext**ou **image** dans une ligne, **bcp_moretext** opère sur les colonnes **Text**, **ntext**ou **image** en commençant par la colonne ayant le nombre ordinal le plus faible et en poursuivant à la colonne ayant le nombre ordinal le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="faa3c-110">When there are multiple **text**, **ntext**, or **image** columns in a row, **bcp_moretext** operates on the **text**, **ntext**, or **image** columns starting with the column having the lowest ordinal number and proceeding to the column with the highest ordinal number.</span></span> <span data-ttu-id="faa3c-111">**bcp_moretext** passe d’une colonne à la suivante lorsque la somme des longueurs des données envoyées est égale à la longueur spécifiée dans la dernière **bcp_collen** ou **bcp_bind** pour la colonne actuelle.</span><span class="sxs-lookup"><span data-stu-id="faa3c-111">**bcp_moretext** goes from one column to the next when the sum of the lengths of data sent equals the length specified in the latest **bcp_collen** or **bcp_bind** for the current column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa3c-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="faa3c-112">See Also</span></span>  
 [<span data-ttu-id="faa3c-113">Exécution d’opérations de copie en bloc &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="faa3c-113">Performing Bulk Copy Operations &#40;ODBC&#41;</span></span>](performing-bulk-copy-operations-odbc.md)  
  
  
