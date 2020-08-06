---
title: Types CLR volumineux définis par l'utilisateur | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- large CLR user-defined types
ms.assetid: b65eb61d-ccf6-49c0-98e7-9a4ef4b2f790
author: rothja
ms.author: jroth
ms.openlocfilehash: 27f0c13caea8c4aca63d78238509c6d05f1bf7bf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698081"
---
# <a name="large-clr-user-defined-types"></a><span data-ttu-id="9225a-102">Types CLR volumineux définis par l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="9225a-102">Large CLR User-Defined Types</span></span>
  <span data-ttu-id="9225a-103">Dans SQL Server 2005, les types définis par l'utilisateur (UDT) dans le CLR (Common Language Runtime) se limitaient à une taille de 8 000 octets.</span><span class="sxs-lookup"><span data-stu-id="9225a-103">In SQL Server 2005, user-defined types (UDTs) in the common language runtime (CLR) were restricted to 8,000 bytes in size.</span></span> <span data-ttu-id="9225a-104">Cette limite n'est plus d'actualité dans [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] et versions ultérieures.</span><span class="sxs-lookup"><span data-stu-id="9225a-104">This restriction has been lifted in [!INCLUDE[ssKatmai](../../../includes/sskatmai-md.md)] and later versions.</span></span> <span data-ttu-id="9225a-105">Les types CLR définis par l'utilisateur sont désormais traités de la même manière que les objets LOB.</span><span class="sxs-lookup"><span data-stu-id="9225a-105">CLR UDTs are now treated in a similar way to large object (LOB) types.</span></span> <span data-ttu-id="9225a-106">Ainsi, les types définis par l'utilisateur dont la taille est inférieure ou égale à 8 000 octets adoptent le même comportement que dans SQL Server 2005 mais les types définis par l'utilisateur plus volumineux sont pris en charge et affichent une taille « illimitée ».</span><span class="sxs-lookup"><span data-stu-id="9225a-106">That is, UDTs less than or equal to 8,000 bytes behave the same way as in SQL Server 2005, but larger UDTs are supported and report their size as "unlimited".</span></span>  
  
 <span data-ttu-id="9225a-107">Pour plus d’informations, consultez [types CLR volumineux définis par l’utilisateur &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) et [types CLR volumineux définis par l’utilisateur &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="9225a-107">For more information, see [Large CLR User-Defined Types &#40;OLE DB&#41;](../ole-db/large-clr-user-defined-types-ole-db.md) and [Large CLR User-Defined Types &#40;ODBC&#41;](../odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="use-cases"></a><span data-ttu-id="9225a-108">Cas d'utilisation</span><span class="sxs-lookup"><span data-stu-id="9225a-108">Use Cases</span></span>  
 <span data-ttu-id="9225a-109">Pour ODBC, la prise en charge des types définis par l'utilisateur volumineux incluent la possibilité de transmettre des valeurs UDT en fragments sous forme de paramètres de données en cours d'exécution.</span><span class="sxs-lookup"><span data-stu-id="9225a-109">For ODBC, support for large UDTs includes the ability to send UDT values in pieces as data-at-execution parameters.</span></span> <span data-ttu-id="9225a-110">Pour ce faire, utilisez SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="9225a-110">This is done by using SQLPutData.</span></span>  
  
 <span data-ttu-id="9225a-111">Pour OLE DB, la prise en charge des types définis par l’utilisateur volumineux offre la possibilité de diffuser des valeurs UDT vers et depuis le serveur au moyen d’une liaison ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="9225a-111">For OLE DB, support for large UDTs includes the ability to stream UDT values to and from the server by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="9225a-112">Les types définis par l'utilisateur dont la taille est inférieure ou égale à 8 000 octets se comporteront de la même manière que dans SQL Server 2005.</span><span class="sxs-lookup"><span data-stu-id="9225a-112">UDTs less than or equal to 8,000 bytes will behave as they did in SQL Server 2005.</span></span> <span data-ttu-id="9225a-113">Pour OLE DB, vous pouvez toujours transmettre en continu des types définis par l'utilisateur de petite taille à l'aide de la liaison ISequentialStream.</span><span class="sxs-lookup"><span data-stu-id="9225a-113">For OLE DB, you can still stream small UDTs by using ISequentialStream binding.</span></span>  
  
 <span data-ttu-id="9225a-114">Le code natif doit quelquefois comprendre le contenu des types CLR définis par l'utilisateur mais n'a pas besoin d'instancier les objets managés.</span><span class="sxs-lookup"><span data-stu-id="9225a-114">Sometimes native code will have to understand the contents of CLR UDTs, but will not have to instantiate managed objects.</span></span> <span data-ttu-id="9225a-115">Dans ce cas, vous pouvez utiliser la sérialisation personnalisée pour convertir des valeurs de type défini par l'utilisateur (UDT) sur le serveur dans un format bien connu des clients.</span><span class="sxs-lookup"><span data-stu-id="9225a-115">If this is the case, you can use custom serialization to convert UDT values on the server into a well known format for clients.</span></span>  
  
 <span data-ttu-id="9225a-116">Pour les applications qui disposent d'un code d'accès aux données existant, vous pouvez exploiter le comportement des types CLR définis par l'utilisateur sur le client en extrayant des types définis par l'utilisateur via des API natives et en les instanciant au moyen de l'interopérabilité C++/CLI dans des applications en mode mixte.</span><span class="sxs-lookup"><span data-stu-id="9225a-116">For applications that have existing data access code, you can exploit CLR UDT behavior on the client by retrieving UDTs through native APIs and instantiating them by using C++ CLI interop in mixed mode applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9225a-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9225a-117">See Also</span></span>  
 [<span data-ttu-id="9225a-118">Fonctionnalités de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="9225a-118">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
