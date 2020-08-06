---
title: Utilisation de la clause OUTPUT avec OLE DB dans SQL Server Native Client | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 53deeb99-c088-4fde-844b-b2d91d6de1eb
author: rothja
ms.author: jroth
ms.openlocfilehash: a425ec6269040c72836571b8fa8b51bba4ed8c32
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87706416"
---
# <a name="using-the-output-clause-with-ole-db-in-sql-server-native-client"></a><span data-ttu-id="e2403-102">Utilisation de la clause OUTPUT avec OLE DB dans SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e2403-102">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>
  <span data-ttu-id="e2403-103">Si vous utilisez une clause OUTPUT dans une commande INSERT, UPDATE, DELETE ou MERGE, le nombre de lignes affectées n’est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="e2403-103">If you use an OUTPUT clause in an INSERT, UPDATE, DELETE, or MERGE command, the count of affected rows is not available.</span></span> <span data-ttu-id="e2403-104">L’application doit compter le nombre de lignes de l’ensemble de lignes retourné par la clause OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="e2403-104">The application must count the number of rows in the rowset that is returned by the OUTPUT clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2403-105">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e2403-105">See Also</span></span>  
 [<span data-ttu-id="e2403-106">Création d'une application de fournisseur OLE DB de SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e2403-106">Creating a SQL Server Native Client OLE DB Provider Application</span></span>](creating-a-sql-server-native-client-ole-db-provider-application.md)  
  
  
