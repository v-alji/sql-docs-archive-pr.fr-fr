---
title: Données blob (Binary Large Object) (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], design and implementation
ms.assetid: 97509274-c3f8-43e5-a37c-52f1ffe0961a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a663dedf34d75a21ee8df6b97979548c04abf7ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87612982"
---
# <a name="binary-large-object-blob-data-sql-server"></a><span data-ttu-id="adb7b-102">Données blob (Binary Large Object) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="adb7b-102">Binary Large Object (Blob) Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="adb7b-103">fournit des solutions pour stocker des fichiers et des documents dans la base de données ou sur des dispositifs de stockage distants.</span><span class="sxs-lookup"><span data-stu-id="adb7b-103">provides solutions for storing files and documents in the database or on remote storage devices.</span></span>  
  
##  <a name="in-this-section"></a><a name="section"></a> <span data-ttu-id="adb7b-104">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="adb7b-104">In This Section</span></span>  
 [<span data-ttu-id="adb7b-105">Comparer les options pour le stockage des objets blob &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="adb7b-105">Compare Options for Storing Blobs &#40;SQL Server&#41;</span></span>](compare-options-for-storing-blobs-sql-server.md)  
 <span data-ttu-id="adb7b-106">Comparez les avantages de FILESTREAM, de FileTables et de magasin d'objets BLOB distants (RBS).</span><span class="sxs-lookup"><span data-stu-id="adb7b-106">Compare the advantages of FILESTREAM, FileTables, and Remote Blob Store.</span></span>  
  
 [<span data-ttu-id="adb7b-107">FILESTREAM &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="adb7b-107">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 <span data-ttu-id="adb7b-108">FILESTREAM permet aux applications [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]de stocker des données non structurées, telles que des documents et des images, dans le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="adb7b-108">FILESTREAM enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-based applications to store unstructured data, such as documents and images, on the file system.</span></span> <span data-ttu-id="adb7b-109">Les applications peuvent tirer parti des API de diffusion et des performances du système de fichiers, et en même temps maintenir la cohérence transactionnelle entre les données non structurées et les données structurées correspondantes.</span><span class="sxs-lookup"><span data-stu-id="adb7b-109">Applications can leverage the rich streaming APIs and performance of the file system and at the same time maintain transactional consistency between the unstructured data and corresponding structured data.</span></span>  
  
 [<span data-ttu-id="adb7b-110">FileTables &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="adb7b-110">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 <span data-ttu-id="adb7b-111">La fonctionnalité FileTable apporte une prise en charge de l'espace de noms de fichier Windows et la compatibilité des applications Windows avec les données de fichier stockées dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="adb7b-111">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="adb7b-112">FileTable permet à une application d'intégrer ses composants de stockage et de gestion des données, et fournit des services [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] intégrés (notamment la recherche sémantique et en texte intégral) sur des données et des métadonnées non structurées.</span><span class="sxs-lookup"><span data-stu-id="adb7b-112">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="adb7b-113">En d'autres termes, vous pouvez maintenant stocker des fichiers et des documents dans des tables spéciales dans [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , appelées FileTables, mais y accéder à partir d'applications Windows comme si ils avaient été stockés dans le système de fichiers, sans apporter de modifications à vos applications clientes.</span><span class="sxs-lookup"><span data-stu-id="adb7b-113">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 [<span data-ttu-id="adb7b-114">Magasin d’objets blob distants &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="adb7b-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
 <span data-ttu-id="adb7b-115">Le magasin d'objets blob distants (RBS) pour [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] permet aux administrateurs de base de données de stocker des objets blob (Binary Large Object) dans des solutions de stockage de marchandises et non pas directement sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="adb7b-115">Remote BLOB store (RBS) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lets database administrators store binary large objects (BLOBs) in commodity storage solutions instead of directly on the server.</span></span> <span data-ttu-id="adb7b-116">Cela permet d'économiser une grande quantité d'espace et d'éviter le gaspillage des précieuses ressources matérielles du serveur.</span><span class="sxs-lookup"><span data-stu-id="adb7b-116">This saves a significant amount of space and avoids wasting expensive server hardware resources.</span></span> <span data-ttu-id="adb7b-117">RBS fournit un ensemble de bibliothèques API qui définissent un modèle standardisé d'accès aux données BLOB pour les applications.</span><span class="sxs-lookup"><span data-stu-id="adb7b-117">RBS provides a set of API libraries that define a standardized model for applications to access BLOB data.</span></span> <span data-ttu-id="adb7b-118">RBS comprend également des outils de maintenance, tels que le nettoyage de la mémoire, permettant de gérer les données BLOB distantes.</span><span class="sxs-lookup"><span data-stu-id="adb7b-118">RBS also includes maintenance tools, such as garbage collection, to help manage remote BLOB data.</span></span>  
  
 <span data-ttu-id="adb7b-119">RBS est inclus dans le CD d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , mais n'est pas installé par le programme d'installation de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="adb7b-119">RBS is included on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
  
