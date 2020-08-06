---
title: Utilisation de codes pour modifier des données dans SQLXML 4,0 | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- data insertions [SQLXML]
- data deletions [SQLXML]
- updating data [SQLXML]
- modifying data [SQLXML]
- OPENXML function
- updategrams [SQLXML]
- database modifications [SQLXML]
- data updates [SQLXML]
- modifying databases
- data modifications [SQLXML]
- deleting data
- inserting data
ms.assetid: b8b3b892-cb73-41d0-b945-bce148d81d9b
author: rothja
ms.author: jroth
ms.openlocfilehash: a4a2397668ed08df91377cc35dea22fd52788580
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87611686"
---
# <a name="using-updategrams-to-modify-data-in-sqlxml-40"></a><span data-ttu-id="9e2bf-102">Utilisation de codes de mise à jour (updategrams) pour modifier des données dans SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="9e2bf-102">Using Updategrams to Modify Data in SQLXML 4.0</span></span>
  <span data-ttu-id="9e2bf-103">Vous pouvez modifier (insérer, mettre à jour ou supprimer) une base de données dans [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à partir d’un document XML existant à l’aide d’un mise à jour ou de la [!INCLUDE[tsql](../../../includes/tsql-md.md)] fonction OpenXml.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="9e2bf-104">Cette section fournit des informations sur les codes de mise à jour (updategrams) et propose des exemples pour leur utilisation.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-104">This section provides information about updategrams and examples of their usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e2bf-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="9e2bf-105">In This Section</span></span>  
 [<span data-ttu-id="9e2bf-106">Présentation de codes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-106">Introduction to Updategrams &#40;SQLXML 4.0&#41;</span></span>](introduction-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-107">Fournit des informations de base et des exemples de codes de mise à jour (updategrams).</span><span class="sxs-lookup"><span data-stu-id="9e2bf-107">Provides basic information and examples of updategrams.</span></span>  
  
 [<span data-ttu-id="9e2bf-108">Spécification d’un schéma de mappage annoté dans un mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-108">Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;</span></span>](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-109">Décrit et fournit des exemples de schémas de mappage annotés dans les codes de mise à jour (updategrams).</span><span class="sxs-lookup"><span data-stu-id="9e2bf-109">Explains and provides examples of annotated mapping schemas in updategrams.</span></span>  
  
 [<span data-ttu-id="9e2bf-110">Gestion des valeurs NULL &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-110">NULL Handling &#40;SQLXML 4.0&#41;</span></span>](null-handling-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-111">Décrit comment spécifier la valeur NULL pour des valeurs d'élément et d'attribut.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-111">Describes how to specify NULL for element and attribute values.</span></span>  
  
 [<span data-ttu-id="9e2bf-112">Insertion de données à l’aide de XML codes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-112">Inserting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](inserting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-113">Décrit et fournit des exemples d'utilisation de codes de mise à jour (updategrams) pour insérer des données.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-113">Describes and provides examples of using updategrams to insert data.</span></span>  
  
 [<span data-ttu-id="9e2bf-114">Suppression de données à l’aide de XML codes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-114">Deleting Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](deleting-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-115">Décrit et fournit des exemples d'utilisation de codes de mise à jour (updategrams) pour supprimer des données.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-115">Describes and provides examples of using updategrams to delete data.</span></span>  
  
 [<span data-ttu-id="9e2bf-116">Mise à jour des données à l’aide de codes XML &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-116">Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](updating-data-using-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-117">Décrit et fournit des exemples d'utilisation de codes de mise à jour (updategrams) pour modifier des données existantes.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-117">Describes and provides examples of using updategrams to modify existing data.</span></span>  
  
 [<span data-ttu-id="9e2bf-118">Passage de paramètres à codes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-118">Passing Parameters to Updategrams &#40;SQLXML 4.0&#41;</span></span>](passing-parameters-to-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-119">Décrit et fournit des exemples de transmission de paramètres aux codes de mise à jour (updategrams).</span><span class="sxs-lookup"><span data-stu-id="9e2bf-119">Describes and provides examples of passing parameters to updategrams.</span></span>  
  
 [<span data-ttu-id="9e2bf-120">Gestion des problèmes d’accès concurrentiel de la base de données dans codes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-120">Handling Database Concurrency Issues in Updategrams &#40;SQLXML 4.0&#41;</span></span>](handling-database-concurrency-issues-in-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-121">Décrit les divers niveaux de protection possibles pour gérer des problèmes d'accès concurrentiel dans les codes de mise à jour (updategrams) et fournit des exemples.</span><span class="sxs-lookup"><span data-stu-id="9e2bf-121">Describes the various levels of protection possible for handling concurrency issues in updategrams, and provides examples.</span></span>  
  
 [<span data-ttu-id="9e2bf-122">Exemples d’applications mise à jour &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-122">Updategram Sample Applications &#40;SQLXML 4.0&#41;</span></span>](../../../database-engine/dev-guide/updategram-sample-applications-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-123">Fournit des exemples d'applications qui utilisent des codes de mise à jour (updategrams).</span><span class="sxs-lookup"><span data-stu-id="9e2bf-123">Provides sample applications that use updategrams.</span></span>  
  
 [<span data-ttu-id="9e2bf-124">Instructions et limitations de XML codes &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="9e2bf-124">Guidelines and Limitations of XML Updategrams &#40;SQLXML 4.0&#41;</span></span>](guidelines-and-limitations-of-xml-updategrams-sqlxml-4-0.md)  
 <span data-ttu-id="9e2bf-125">Répertorie certains éléments à retenir lors de l'utilisation de codes de mise à jour (updategrams).</span><span class="sxs-lookup"><span data-stu-id="9e2bf-125">Lists some things to remember when working with updategrams.</span></span>  
  
  
