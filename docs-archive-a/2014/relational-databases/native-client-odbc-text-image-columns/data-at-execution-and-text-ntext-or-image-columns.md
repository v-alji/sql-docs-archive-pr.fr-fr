---
title: Données en cours d’exécution et colonnes text, ntext ou image | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- text columns [ODBC]
- SQL Server Native Client ODBC driver, image columns
- SQL Server Native Client ODBC driver, text columns
- data types [ODBC], image
- data types [ODBC], text
- columns [ODBC]
- ODBC data types, image columns
- ODBC data types, text columns
- data-at-execution
- ODBC data-at-execution
- image columns [ODBC]
ms.assetid: 67ffb1a6-f38d-4712-ba64-96bdd41ec2b2
author: rothja
ms.author: jroth
ms.openlocfilehash: 404fade34862fe4705ec440eef7f466a9073250b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709320"
---
# <a name="data-at-execution-and-text-ntext-or-image-columns"></a><span data-ttu-id="cac5b-102">Données en cours d'exécution et colonnes text, ntext ou image</span><span class="sxs-lookup"><span data-stu-id="cac5b-102">Data-at-Execution and Text, ntext, or Image Columns</span></span>
  <span data-ttu-id="cac5b-103">Les données en cours d'exécution sont une fonctionnalité ODBC qui permet aux applications d'utiliser des quantités de données extrêmement importantes sur les colonnes dépendantes ou les paramètres.</span><span class="sxs-lookup"><span data-stu-id="cac5b-103">ODBC data-at-execution is a feature that enables applications to work with extremely large amounts of data on bound columns or parameters.</span></span> <span data-ttu-id="cac5b-104">Lorsque vous récupérez des colonnes **Text**, **ntext**ou **image** très volumineuses, il est possible qu’une application ne soit pas en mesure d’allouer une mémoire tampon volumineuse, de lier la colonne dans la mémoire tampon et d’extraire la ligne.</span><span class="sxs-lookup"><span data-stu-id="cac5b-104">When retrieving very large **text**, **ntext**, or **image** columns, an application may not be able to simply allocate a huge buffer, bind the column into the buffer, and fetch the row.</span></span> <span data-ttu-id="cac5b-105">Lors de la mise à jour de colonnes **Text**, **ntext**ou **image** de très grande taille, l’application peut ne pas être en mesure d’allouer simplement une mémoire tampon volumineuse, de la lier à un marqueur de paramètre dans une instruction SQL, puis d’exécuter l’instruction.</span><span class="sxs-lookup"><span data-stu-id="cac5b-105">When updating very large **text**, **ntext**, or **image** columns, the application might not be able to simply allocate a huge buffer, bind it to a parameter marker in an SQL statement, and then execute the statement.</span></span> <span data-ttu-id="cac5b-106">Dans ce cas, l’application doit utiliser [SQLGetData](../native-client-odbc-api/sqlgetdata.md) ou [SQLPutData](../native-client-odbc-api/sqlputdata.md) avec ses options de données en cours d’exécution.</span><span class="sxs-lookup"><span data-stu-id="cac5b-106">In these cases, the application must use [SQLGetData](../native-client-odbc-api/sqlgetdata.md) or [SQLPutData](../native-client-odbc-api/sqlputdata.md) with its data-at-execution options.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac5b-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cac5b-107">See Also</span></span>  
 [<span data-ttu-id="cac5b-108">Gestion des colonnes texte et image</span><span class="sxs-lookup"><span data-stu-id="cac5b-108">Managing Text and Image Columns</span></span>](managing-text-and-image-columns.md)  
  
  
