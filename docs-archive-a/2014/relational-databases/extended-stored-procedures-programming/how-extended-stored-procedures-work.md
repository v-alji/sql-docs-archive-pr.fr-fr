---
title: Fonctionnement des procédures stockées étendues | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], about extended stored procedures
ms.assetid: 6e946d8c-3268-4b59-8a1c-1637909cd701
author: rothja
ms.author: jroth
ms.openlocfilehash: 75082fed6b70c214b4f55b85034ffa371824d24f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612348"
---
# <a name="how-extended-stored-procedures-work"></a><span data-ttu-id="6bc29-102">Fonctionnement des procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="6bc29-102">How Extended Stored Procedures Work</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6bc29-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="6bc29-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="6bc29-104">Le processus de fonctionnement d'une procédure stockée étendue est le suivant :</span><span class="sxs-lookup"><span data-stu-id="6bc29-104">The process by which an extended stored procedure works is:</span></span>  
  
1.  <span data-ttu-id="6bc29-105">Lorsqu’un client exécute une procédure stockée étendue, la demande est transmise au format tabular data stream (TDS) ou SOAP (Simple Object Access Protocol) à partir de l’application cliente vers [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6bc29-105">When a client executes an extended stored procedure, the request is transmitted in tabular data stream (TDS) or Simple Object Access Protocol (SOAP) format from the client application to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
2.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6bc29-106">recherche la DLL associée à la procédure stockée étendue et la charge si elle ne l'est déjà.</span><span class="sxs-lookup"><span data-stu-id="6bc29-106">searches for the DLL associated with the extended stored procedure, and loads the DLL if it is not already loaded.</span></span>  
  
3.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="6bc29-107">appelle la procédure stockée étendue demandée (implémentée comme fonction à l'intérieur de la DLL).</span><span class="sxs-lookup"><span data-stu-id="6bc29-107">calls the requested extended stored procedure (implemented as a function inside the DLL).</span></span>  
  
4.  <span data-ttu-id="6bc29-108">La procédure stockée étendue transmet les jeux de résultats et retourne les paramètres au serveur via l'API de la procédure stockée étendue.</span><span class="sxs-lookup"><span data-stu-id="6bc29-108">The extended stored procedure passes result sets and return parameters back to the server by through the Extended Stored Procedure API.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bc29-109">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6bc29-109">See Also</span></span>  
 [<span data-ttu-id="6bc29-110">Programmation de procédure stockée étendue de moteur de base de données</span><span class="sxs-lookup"><span data-stu-id="6bc29-110">Database Engine Extended Stored Procedure Programming</span></span>](../database-engine-extended-stored-procedure-programming.md)  
  
  
