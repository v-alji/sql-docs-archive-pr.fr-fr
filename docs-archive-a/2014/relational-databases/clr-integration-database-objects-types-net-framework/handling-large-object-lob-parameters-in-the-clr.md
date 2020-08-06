---
title: Gestion des paramètres Large Object (LOB) dans le CLR | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- large data, CLR integration
- LOB data [SQL Server], CLR integration
- SqlBytes data type
- SqlChars data type
ms.assetid: d07956f6-9543-4476-9426-536f95991150
author: rothja
ms.author: jroth
ms.openlocfilehash: ee791c73a6610761c2086723f9e41c2351b37dd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87709636"
---
# <a name="handling-large-object-lob-parameters-in-the-clr"></a><span data-ttu-id="48a08-102">Gestion des paramètres LOB dans le CLR</span><span class="sxs-lookup"><span data-stu-id="48a08-102">Handling Large Object (LOB) Parameters in the CLR</span></span>
  <span data-ttu-id="48a08-103">Utilisez `SqlBytes` et `SqlChars` pour passer des paramètres de type binaire LOB (`varbinary(max)`) et de type caractère LOB (`nvarchar(max)`), respectivement.</span><span class="sxs-lookup"><span data-stu-id="48a08-103">Use `SqlBytes` and `SqlChars` to pass large object (LOB) binary type (`varbinary(max)`) and LOB character type (`nvarchar(max)`) parameters, respectively.</span></span> <span data-ttu-id="48a08-104">Ces types autorisent la diffusion en continu des valeurs LOB de la base de données à la routine CLR (Common Language Runtime), au lieu de copier la valeur entière dans l'espace managé.</span><span class="sxs-lookup"><span data-stu-id="48a08-104">These types allow streaming the LOB values from the database to the common language runtime (CLR) routine, instead of copying the entire value into managed space.</span></span> <span data-ttu-id="48a08-105">`SqlBinary` et `SqlString` doivent être utilisés uniquement pour les valeurs des petites chaînes binaires et des chaînes de caractères.</span><span class="sxs-lookup"><span data-stu-id="48a08-105">`SqlBinary` and `SqlString` should be used only for small binary and character string values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48a08-106">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48a08-106">See Also</span></span>  
 [<span data-ttu-id="48a08-107">Types de données SQL Server dans le .NET Framework</span><span class="sxs-lookup"><span data-stu-id="48a08-107">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
