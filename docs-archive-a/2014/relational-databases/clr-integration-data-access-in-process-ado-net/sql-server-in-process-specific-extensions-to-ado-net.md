---
title: SQL Server des extensions spécifiques in-process à ADO.NET | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- data access [CLR integration]
- ADO.NET [CLR integration]
- common language runtime [SQL Server], ADO.NET
- database objects [CLR integration], in-process extensions
- in-process data access providers [CLR integration]
- extensions [CLR integration]
ms.assetid: 781b812e-eb14-472a-85fa-aa4cdb929bee
author: rothja
ms.author: jroth
ms.openlocfilehash: 37d8aedc1d8f93739c2e9386665adfc67b43e312
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87614124"
---
# <a name="sql-server-in-process-specific-extensions-to-adonet"></a><span data-ttu-id="b28d7-102">Extensions spécifiques in-process de SQL Server à ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b28d7-102">SQL Server In-Process Specific Extensions to ADO.NET</span></span>
  <span data-ttu-id="b28d7-103">Quatre extensions fonctionnelles principales à ADO.NET sont spécifiquement destinées à une utilisation in-process.</span><span class="sxs-lookup"><span data-stu-id="b28d7-103">There are four main functional extensions to ADO.NET that are specifically for in-process use.</span></span> <span data-ttu-id="b28d7-104">Les rubriques suivantes traitent ces extensions en détail.</span><span class="sxs-lookup"><span data-stu-id="b28d7-104">The following topics will cover these extensions in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b28d7-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="b28d7-105">In This Section</span></span>  
 [<span data-ttu-id="b28d7-106">Objet SqlContext</span><span class="sxs-lookup"><span data-stu-id="b28d7-106">SqlContext Object</span></span>](sqlcontext-object.md)  
 <span data-ttu-id="b28d7-107">Cette classe fournit l'accès aux autres extensions en faisant abstraction du contexte d'un appelant d'une routine SQL Server qui exécute le code managé in-process.</span><span class="sxs-lookup"><span data-stu-id="b28d7-107">This class provides access to the other extensions by abstracting the context of a caller of a SQL Server routine that executes managed code in-process.</span></span>  
  
 [<span data-ttu-id="b28d7-108">Objet SqlPipe</span><span class="sxs-lookup"><span data-stu-id="b28d7-108">SqlPipe Object</span></span>](sqlpipe-object.md)  
 <span data-ttu-id="b28d7-109">Cette classe contient les routines pour envoyer les messages et les résultats tabulaires au client.</span><span class="sxs-lookup"><span data-stu-id="b28d7-109">This class contains routines to send tabular results and messages to the client.</span></span>  
  
 [<span data-ttu-id="b28d7-110">Objet SqlTriggerContext</span><span class="sxs-lookup"><span data-stu-id="b28d7-110">SqlTriggerContext Object</span></span>](sqltriggercontext-object.md)  
 <span data-ttu-id="b28d7-111">Cette classe fournit des informations sur le contexte dans lequel un déclencheur est exécuté.</span><span class="sxs-lookup"><span data-stu-id="b28d7-111">This class provides information on the context in which a trigger is run.</span></span>  
  
 [<span data-ttu-id="b28d7-112">Objet SqlDataRecord</span><span class="sxs-lookup"><span data-stu-id="b28d7-112">SqlDataRecord Object</span></span>](sqldatarecord-object.md)  
 <span data-ttu-id="b28d7-113">La classe SqlDataRecord représente une ligne unique de données, avec ses métadonnées connexes, et permet que les procédures stockées retournent des jeux de résultats personnalisés au client.</span><span class="sxs-lookup"><span data-stu-id="b28d7-113">The SqlDataRecord class represents a single row of data, along with its related metadata, and allows stored procedures to return custom result sets to the client.</span></span>  
  
  
