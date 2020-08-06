---
title: Prise en charge de FOR XML pour les types de données définis par l’utilisateur (UDT) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- UDTs [SQL Server], XML
- user-defined types [SQL Server], XML
ms.assetid: 354e2150-fa2a-4583-b1aa-6b78ae4378b6
author: rothja
ms.author: jroth
ms.openlocfilehash: b668ad2da13fdfc880ab26cb2b2759ff3693f7d7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710447"
---
# <a name="for-xml-support-for-the-user-defined-data-types-udt"></a><span data-ttu-id="727a5-102">Prise en charge de FOR XML pour les types de données définis par l'utilisateur (UDT)</span><span class="sxs-lookup"><span data-stu-id="727a5-102">FOR XML Support for the User-Defined Data Types (UDT)</span></span>
  <span data-ttu-id="727a5-103">FOR XML ne prend pas en charge les types de données définis par l'utilisateur (UDT) du Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="727a5-103">FOR XML does not support common language runtime (CLR) user-defined data types (UDTs).</span></span>  
  
 <span data-ttu-id="727a5-104">Pour utiliser FOR XML avec des types de données CLR définis par l'utilisateur, assurez-vous que le type de données a une sérialisation XML et utilisez un cast explicite en XML dans la clause select FOR XML.</span><span class="sxs-lookup"><span data-stu-id="727a5-104">To use FOR XML with CLR user-defined data types, make sure that the data type has an XML serialization, and use an explicit cast to XML in the FOR XML select clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="727a5-105">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="727a5-105">See Also</span></span>  
 [<span data-ttu-id="727a5-106">Prise en charge de FOR XML pour différents types de données SQL Server</span><span class="sxs-lookup"><span data-stu-id="727a5-106">FOR XML Support for Various SQL Server Data Types</span></span>](for-xml-support-for-various-sql-server-data-types.md)  
  
  
