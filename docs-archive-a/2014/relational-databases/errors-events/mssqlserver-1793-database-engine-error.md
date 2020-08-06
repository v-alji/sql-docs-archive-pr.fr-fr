---
title: MSSQLSERVER_1793 | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
ms.assetid: 808db1d0-acc1-41d0-9287-8a5455001a02
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 54172adb957c3cbc1dbc221d1cae2a583830a1cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699690"
---
# <a name="mssqlserver_1793"></a><span data-ttu-id="e207f-102">MSSQLSERVER_1793</span><span class="sxs-lookup"><span data-stu-id="e207f-102">MSSQLSERVER_1793</span></span>
    
## <a name="details"></a><span data-ttu-id="e207f-103">Détails</span><span class="sxs-lookup"><span data-stu-id="e207f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e207f-104">Nom du produit</span><span class="sxs-lookup"><span data-stu-id="e207f-104">Product Name</span></span>|<span data-ttu-id="e207f-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="e207f-105">SQL Server</span></span>|  
|<span data-ttu-id="e207f-106">ID de l’événement</span><span class="sxs-lookup"><span data-stu-id="e207f-106">Event ID</span></span>|<span data-ttu-id="e207f-107">1793</span><span class="sxs-lookup"><span data-stu-id="e207f-107">1793</span></span>|  
|<span data-ttu-id="e207f-108">Source de l’événement</span><span class="sxs-lookup"><span data-stu-id="e207f-108">Event Source</span></span>|<span data-ttu-id="e207f-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="e207f-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="e207f-110">Composant</span><span class="sxs-lookup"><span data-stu-id="e207f-110">Component</span></span>|<span data-ttu-id="e207f-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="e207f-111">SQLEngine</span></span>|  
|<span data-ttu-id="e207f-112">Nom symbolique</span><span class="sxs-lookup"><span data-stu-id="e207f-112">Symbolic Name</span></span>|<span data-ttu-id="e207f-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span><span class="sxs-lookup"><span data-stu-id="e207f-113">FILESTREAM_BASEDATA_NEED_SAME_PARTITION</span></span>|  
|<span data-ttu-id="e207f-114">Texte du message</span><span class="sxs-lookup"><span data-stu-id="e207f-114">Message Text</span></span>|<span data-ttu-id="e207f-115">Impossible de supprimer l'index '%.\*ls' car aucun schéma de partition n'est spécifié pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e207f-115">Cannot drop index '%.\*ls' since a partition scheme is not specified for FILESTREAM data.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="e207f-116">Explication</span><span class="sxs-lookup"><span data-stu-id="e207f-116">Explanation</span></span>  
 <span data-ttu-id="e207f-117">Ce message apparaît quand vous essayez de supprimer un index cluster sur une table qui contient des données FILESTREAM et que vous spécifiez une clause **MOVE TO** pour les données de base sans spécifier de clause **FILESTREAM_ON** pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e207f-117">This message occurs when you try to drop a clustered index on a table that contains FILESTREAM data, and you specify a **MOVE TO** clause for the base data, but you do not specify a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e207f-118">Action de l'utilisateur</span><span class="sxs-lookup"><span data-stu-id="e207f-118">User Action</span></span>  
 <span data-ttu-id="e207f-119">Pour supprimer un index cluster sur une table qui contient des données FILESTREAM, utilisez l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="e207f-119">When dropping a clustered index on a table that contains FILESTREAM data, use one of the following options:</span></span>  
  
-   <span data-ttu-id="e207f-120">Spécifiez à la fois une clause **MOVE TO** pour les données de base et une clause **FILESTREAM_ON** pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e207f-120">Specify both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
-   <span data-ttu-id="e207f-121">Ne spécifiez pas de clause **MOVE TO** pour les données de base ni de clause **FILESTREAM_ON** pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e207f-121">Do not specify either a **MOVE TO** clause for the base data or a **FILESTREAM_ON** clause for the FILESTREAM data.</span></span>  
  
 <span data-ttu-id="e207f-122">L'exemple suivant échoue car un schéma de partition est spécifié pour les données de base, mais n'est pas spécifié pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e207f-122">The following example fails because a partition scheme is specified for the base data, but is not specified for the FILESTREAM data.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY] )  
GO  
```  
  
 <span data-ttu-id="e207f-123">L’exemple ci-dessous réussit, car une clause **MOVE TO** pour les données de base et une clause **FILESTREAM_ON** pour les données FILESTREAM sont spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e207f-123">The following example succeeds because both a **MOVE TO** clause for the base data and a **FILESTREAM_ON** clause for the FILESTREAM data are specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF, MOVE TO [PRIMARY], filestream_on 'default' )  
GO  
```  
  
 <span data-ttu-id="e207f-124">L’exemple ci-dessous réussit également, car aucune clause **MOVE TO** n’est spécifiée pour les données de base et aucune clause **FILESTREAM_ON** n’est spécifiée pour les données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e207f-124">The following example also succeeds because neither a **MOVE TO** clause for the base data nor a **FILESTREAM_ON** clause for the FILESTREAM data is specified.</span></span>  
  
```sql  
DROP INDEX [<clustered_index_name>] ON [<table_name>]   
WITH ( ONLINE = OFF )  
GO  
```  
  
  
