---
title: Programmation de procédures stockées étendues | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- gateway applications [SQL Server]
- extended stored procedures [SQL Server], about extended stored procedures
- Open Data Services [SQL Server]
- ODS [SQL Server]
ms.assetid: 561305cd-c803-48af-9eec-2c19f4d311ce
author: rothja
ms.author: jroth
ms.openlocfilehash: 30792cc2b431e35a8f7df5ff7bbb2c228892d5c5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612351"
---
# <a name="programming-extended-stored-procedures"></a><span data-ttu-id="71000-102">Programmation de procédures stockées étendues</span><span class="sxs-lookup"><span data-stu-id="71000-102">Programming Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="71000-103">Utilisez l’intégration CLR à la place.</span><span class="sxs-lookup"><span data-stu-id="71000-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="71000-104">Par le passé, les services ODS (Open Data Services) permettaient d'écrire des applications serveur, telles que des passerelles à des environnements de base de données non-SQL Server.</span><span class="sxs-lookup"><span data-stu-id="71000-104">In the past, Open Data Services was used to write server applications, such as gateways to non-SQL Server database environments.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="71000-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ne prend pas en charge les parties obsolètes de l’API Open Data Services.</span><span class="sxs-lookup"><span data-stu-id="71000-105">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support the obsolete portions of the Open Data Services API.</span></span> <span data-ttu-id="71000-106">Les seuls éléments de l'API ODS d'origine encore pris en charge par [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sont les fonctions de procédure stockée étendue ; c'est pourquoi l'API a été renommée « API de procédure stockée étendue ».</span><span class="sxs-lookup"><span data-stu-id="71000-106">The only part of the original Open Data Services API still supported by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are the extended stored procedure functions, so the API has been renamed to the Extended Stored Procedure API.</span></span>  
  
 <span data-ttu-id="71000-107">Avec l'apparition de nouvelles technologies plus puissantes telles que les requêtes distribuées et l'intégration du CLR, les besoins en termes d'applications de l'API de procédure stockée étendue ont été en grande partie éliminés.</span><span class="sxs-lookup"><span data-stu-id="71000-107">With the emergence of newer and more powerful technologies, such as distributed queries and CLR Integration, the need for Extended Stored Procedure API applications has largely been replaced.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="71000-108">Si vous possédez des applications de passerelle existantes, vous ne pouvez pas utiliser le fichier opends60.dll fourni avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour exécuter les applications.</span><span class="sxs-lookup"><span data-stu-id="71000-108">If you have existing gateway applications, you cannot use the opends60.dll that ships with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run the applications.</span></span> <span data-ttu-id="71000-109">Les applications de passerelle ne sont plus prises en charge.</span><span class="sxs-lookup"><span data-stu-id="71000-109">Gateway applications are no longer supported.</span></span>  
  
## <a name="extended-stored-procedures-vs-clr-integration"></a><span data-ttu-id="71000-110">Procédures stockées étendues et intégration du CLR</span><span class="sxs-lookup"><span data-stu-id="71000-110">Extended Stored Procedures vs. CLR Integration</span></span>  
 <span data-ttu-id="71000-111">Dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], les procédures stockées étendues constituaient pour les développeurs d'applications de base de données le seul mécanisme leur permettant d'écrire une logique côté serveur difficile à exprimer voire impossible à écrire en [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="71000-111">In earlier releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], extended stored procedures (XPs) provided the only mechanism that was available for database application developers to write server-side logic that was either hard to express or impossible to write in [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="71000-112">L'intégration du CLR offre une alternative plus robuste à l'écriture de telles procédures stockées.</span><span class="sxs-lookup"><span data-stu-id="71000-112">CLR Integration provides a more robust alternative to writing such stored procedures.</span></span> <span data-ttu-id="71000-113">Qui plus est, la logique, auparavant écrite sous forme de procédures stockées, est souvent mieux exprimée sous forme de fonctions table avec l'intégration du CLR. Ces dernières vous permettent d'interroger les résultats construits par la fonction dans des instructions SELECT en les incorporant dans la clause FROM.</span><span class="sxs-lookup"><span data-stu-id="71000-113">Furthermore, with CLR Integration, logic that used to be written in the form of stored procedures is often better expressed as table-valued functions, which allow the results constructed by the function to be queried in SELECT statements by embedding them in the FROM clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71000-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="71000-114">See Also</span></span>  
 <span data-ttu-id="71000-115">[Vue d’ensemble de l’intégration du Common Language Runtime &#40;CLR&#41;](../clr-integration/common-language-runtime-integration-overview.md) </span><span class="sxs-lookup"><span data-stu-id="71000-115">[Common Language Runtime &#40;CLR&#41; Integration Overview](../clr-integration/common-language-runtime-integration-overview.md) </span></span>  
 [<span data-ttu-id="71000-116">Fonctions table CLR</span><span class="sxs-lookup"><span data-stu-id="71000-116">CLR Table-Valued Functions</span></span>](../clr-integration-database-objects-user-defined-functions/clr-table-valued-functions.md)  
  
  
