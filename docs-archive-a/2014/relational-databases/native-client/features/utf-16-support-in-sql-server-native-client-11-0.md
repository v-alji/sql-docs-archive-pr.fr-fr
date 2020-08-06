---
title: Prise en charge d’UTF-16 dans SQL Server Native Client 11,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: f2520424-8ef4-409f-8147-d83da5076e96
author: rothja
ms.author: jroth
ms.openlocfilehash: af8581071400db888fb508b88f8e8ae93bc71f70
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612267"
---
# <a name="utf-16-support-in-sql-server-native-client-110"></a><span data-ttu-id="26500-102">Prise en charge de UTF-16 dans SQL Server Native Client 11.0</span><span class="sxs-lookup"><span data-stu-id="26500-102">UTF-16 Support in SQL Server Native Client 11.0</span></span>
  <span data-ttu-id="26500-103">À compter de [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , si vous fournissez une mémoire tampon de longueur fixe lors de la liaison d’un paramètre de sortie ou de résultat de colonne et si le `wchar` caractère écrit dans la mémoire tampon avant le caractère de fin est un point de code de substitution étendu d’une paire de substitution, et si le `wchar` caractère suivant est un point de code de substitution faible, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client n’ajoute pas le point de code de</span><span class="sxs-lookup"><span data-stu-id="26500-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], if you supply a fixed-length buffer when binding a column result or output parameter and if the `wchar` character written into the buffer before the terminating character is a high surrogate code point of a surrogate pair, and if the next `wchar` character is a low surrogate code point, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not add the high surrogate code point to the buffer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26500-104">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="26500-104">See Also</span></span>  
 [<span data-ttu-id="26500-105">Fonctionnalités de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="26500-105">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
