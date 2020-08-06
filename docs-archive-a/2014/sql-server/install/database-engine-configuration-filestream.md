---
title: Configuration de la Moteur de base de données-FILESTREAM | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], about FILESTREAM
ms.assetid: 641a10a1-ae52-4d26-8f1c-a032a4aeff02
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ab12b507246a3e13ac59be213813604d531d9a28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87704739"
---
# <a name="database-engine-configuration---filestream"></a><span data-ttu-id="e6cd3-102">Configuration du moteur de base de données - Filestream</span><span class="sxs-lookup"><span data-stu-id="e6cd3-102">Database Engine Configuration - Filestream</span></span>
  <span data-ttu-id="e6cd3-103">Utilisez cette page pour activer FILESTREAM pour cette installation de [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e6cd3-103">Use this page to enable FILESTREAM for this installation of [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].</span></span> <span data-ttu-id="e6cd3-104">FILESTREAM intègre le [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] avec un système de fichiers NTFS en stockant les `varbinary(max)` données BLOB (Binary Large Object) en tant que fichiers sur le système de fichiers.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-104">FILESTREAM integrates the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] with an NTFS file system by storing `varbinary(max)` binary large object (BLOB) data as files on the file system.</span></span> <span data-ttu-id="e6cd3-105">Les instructions [!INCLUDE[tsql](../../includes/tsql-md.md)] peuvent insérer, mettre à jour, interroger, rechercher et sauvegarder des données FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-105">[!INCLUDE[tsql](../../includes/tsql-md.md)] statements can insert, update, query, search, and back up FILESTREAM data.</span></span> <span data-ttu-id="e6cd3-106">Les interfaces de système de fichiers Win32 fournissent l'accès de diffusion en continu aux données.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-106">Win32 file system interfaces provide streaming access to the data.</span></span>  
  
## <a name="ui-element-list"></a><span data-ttu-id="e6cd3-107">Liste d’éléments d’interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="e6cd3-107">UI element list</span></span>  
 <span data-ttu-id="e6cd3-108">**Activer FILESTREAM pour l'accès Transact-SQL**</span><span class="sxs-lookup"><span data-stu-id="e6cd3-108">**Enable FILESTREAM for Transact-SQL access**</span></span>  
 <span data-ttu-id="e6cd3-109">Sélectionnez cette option pour activer FILESTREAM pour l'accès [!INCLUDE[tsql](../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e6cd3-109">Select to enable FILESTREAM for [!INCLUDE[tsql](../../includes/tsql-md.md)] access.</span></span> <span data-ttu-id="e6cd3-110">Ce contrôle doit être activé pour que les autres options de contrôle soient disponibles.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-110">This control must be checked before the other control options will be available.</span></span>  
  
 <span data-ttu-id="e6cd3-111">**Activer FILESTREAM pour l'accès en continu des E/S de fichier**</span><span class="sxs-lookup"><span data-stu-id="e6cd3-111">**Enable FILESTREAM for file I/O streaming access**</span></span>  
 <span data-ttu-id="e6cd3-112">Sélectionnez cette option pour activer l'accès en continu Win32 pour FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-112">Select to enable Win32 streaming access for FILESTREAM.</span></span>  
  
 <span data-ttu-id="e6cd3-113">**Nom du partage Windows**</span><span class="sxs-lookup"><span data-stu-id="e6cd3-113">**Windows share name**</span></span>  
 <span data-ttu-id="e6cd3-114">Utilisez ce contrôle pour entrer le nom du partage Windows dans lequel les données FILESTREAM doivent être stockées.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-114">Use this control to enter the name of the Windows share in which the FILESTREAM data will be stored.</span></span>  
  
 <span data-ttu-id="e6cd3-115">**Permettre aux clients distants d'avoir un accès en continu aux données FILESTREAM**</span><span class="sxs-lookup"><span data-stu-id="e6cd3-115">**Allow remote clients to have streaming access to FILESTREAM data**</span></span>  
 <span data-ttu-id="e6cd3-116">Sélectionnez ce contrôle pour permettre aux clients distants d'accéder à ces données FILESTREAM sur ce serveur.</span><span class="sxs-lookup"><span data-stu-id="e6cd3-116">Select this control to allow remote clients to access this FILESTREAM data on this server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6cd3-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6cd3-117">See Also</span></span>  
 <span data-ttu-id="e6cd3-118">[Activer et configurer FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span><span class="sxs-lookup"><span data-stu-id="e6cd3-118">[Enable and Configure FILESTREAM](../../relational-databases/blob/enable-and-configure-filestream.md) </span></span>  
 [<span data-ttu-id="e6cd3-119">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="e6cd3-119">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
