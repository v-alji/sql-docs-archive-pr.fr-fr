---
title: Collections de schémas XML volumineuses et conditions de mémoire insuffisante | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443207bbbdff5db7e54d61fcebabe70e34cc540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710408"
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a><span data-ttu-id="8fe6e-102">Collections de schémas XML volumineuses et conditions de mémoire insuffisante</span><span class="sxs-lookup"><span data-stu-id="8fe6e-102">Large XML Schema Collections and Out-of-Memory Conditions</span></span>
  <span data-ttu-id="8fe6e-103">Lors d'un appel à la fonction intégrée XML_SCHEMA_NAMESPACE() sur une collection de schémas XML de grande taille ou si vous tentez de supprimer une telle collection, une condition de mémoire insuffisante peut se produire.</span><span class="sxs-lookup"><span data-stu-id="8fe6e-103">During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur.</span></span> <span data-ttu-id="8fe6e-104">Pour pallier ce problème, envisagez les solutions suivantes :</span><span class="sxs-lookup"><span data-stu-id="8fe6e-104">The following are solutions you can use to handle this:</span></span>  
  
-   <span data-ttu-id="8fe6e-105">Si la charge imposée au système est faible, utilisez la commande DROP_XML_SCHEMA_COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="8fe6e-105">When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command.</span></span> <span data-ttu-id="8fe6e-106">Si cette mesure ne permet pas de résoudre le problème, placez la base de données en mode mono-utilisateur à l'aide de l'instruction ALTER DATABASE et réexécutez DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="8fe6e-106">If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again.</span></span> <span data-ttu-id="8fe6e-107">Si la collection de schémas XML existe dans **master**, **model**ou **tempdb**, un redémarrage du serveur est requis pour passer en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8fe6e-107">If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.</span></span>  
  
-   <span data-ttu-id="8fe6e-108">Quand vous appelez XML_SCHEMA_NAMESPACE, essayez d'extraire un espace de noms de schéma XML, tentez l'appel à un moment où la charge système est moindre ou alors en mode mono-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8fe6e-108">When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe6e-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8fe6e-109">See Also</span></span>  
 [<span data-ttu-id="8fe6e-110">Spécifications et limitations relatives aux collections de schémas XML sur le serveur</span><span class="sxs-lookup"><span data-stu-id="8fe6e-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
