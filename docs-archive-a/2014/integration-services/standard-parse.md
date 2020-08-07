---
title: Analyse standard | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- standard parse [Integration Services]
- locales [Integration Services]
ms.assetid: dfe835b1-ea52-4e18-a23a-5188c5b6f013
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7cacff710870d372d6bbf8345e05397857c13a00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87703139"
---
# <a name="standard-parse"></a><span data-ttu-id="508f5-102">Analyse standard</span><span class="sxs-lookup"><span data-stu-id="508f5-102">Standard Parse</span></span>
  <span data-ttu-id="508f5-103">L'analyse standard est un ensemble de routines d'analyse spécifique à un pays qui prend en charge toutes les conversions de type de données fournies par les API de conversion de type de données Automation disponibles dans Oleaut32.dll et Ole2dsip.dll.</span><span class="sxs-lookup"><span data-stu-id="508f5-103">Standard parse is a locale-sensitive set of parsing routines that support all the data type conversions provided by the Automation data type conversion APIs that are available in Oleaut32.dll and Ole2dsip.dll.</span></span> <span data-ttu-id="508f5-104">Elle est équivalente aux API d'analyse OLE DB.</span><span class="sxs-lookup"><span data-stu-id="508f5-104">Standard parse is equivalent to the OLE DB parsing APIs.</span></span>  
  
 <span data-ttu-id="508f5-105">L'analyse standard assure la prise en charge de la conversion de type de données pour les données internationales et doit être utilisée si le format de données n'est pas pris en charge par l'analyse rapide.</span><span class="sxs-lookup"><span data-stu-id="508f5-105">Standard parse provides support for data type conversion of international data, and it should be used if the data format is not supported by Fast parse.</span></span> <span data-ttu-id="508f5-106">Pour plus d'informations sur l'API de conversion de type de données Automation, consultez « API de conversion de type de données » dans [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=79427).</span><span class="sxs-lookup"><span data-stu-id="508f5-106">For more information about the Automation data type conversion API, see "Data Type Conversion APIs" in the [MSDN Library](https://go.microsoft.com/fwlink/?LinkId=79427).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508f5-107">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="508f5-107">See Also</span></span>  
 [<span data-ttu-id="508f5-108">Analyse rapide</span><span class="sxs-lookup"><span data-stu-id="508f5-108">Fast Parse</span></span>](../../2014/integration-services/fast-parse.md)  
  
  
