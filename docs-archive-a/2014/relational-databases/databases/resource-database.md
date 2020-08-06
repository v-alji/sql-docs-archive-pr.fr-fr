---
title: Base de données Resource | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- system objects [SQL Server]
- read-only databases
- mssqlsystemresource.mdf file
- Resource database [SQL Server]
ms.assetid: d592b2b4-bc36-4eb9-9385-8fe4dff0dced
author: stevestein
ms.author: sstein
ms.openlocfilehash: cca2f9e1ff6069a608beb1df1880b37e15f4e869
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87604544"
---
# <a name="resource-database"></a><span data-ttu-id="67611-102">Base de données Resource</span><span class="sxs-lookup"><span data-stu-id="67611-102">Resource Database</span></span>
  <span data-ttu-id="67611-103">La base de données Resource est une base de données en lecture seule qui contient tous les objets système fournis avec [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67611-103">The Resource database is a read-only database that contains all the system objects that are included with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="67611-104">Les objets système, tels que sys.objects, sont conservés physiquement dans la base de données Resource, mais ils figurent logiquement dans le schéma sys de chaque base de données.</span><span class="sxs-lookup"><span data-stu-id="67611-104">system objects, such as sys.objects, are physically persisted in the Resource database, but they logically appear in the sys schema of every database.</span></span> <span data-ttu-id="67611-105">La base de données Resource ne contient ni données utilisateur, ni métadonnées utilisateur.</span><span class="sxs-lookup"><span data-stu-id="67611-105">The Resource database does not contain user data or user metadata.</span></span>  
  
 <span data-ttu-id="67611-106">La base de données Resource facilite et accélère la procédure de mise à niveau vers une nouvelle version de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="67611-106">The Resource database makes upgrading to a new version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an easier and faster procedure.</span></span> <span data-ttu-id="67611-107">Dans les versions antérieures de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], la mise à niveau nécessitait la suppression et la création d'objets système.</span><span class="sxs-lookup"><span data-stu-id="67611-107">In earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], upgrading required dropping and creating system objects.</span></span> <span data-ttu-id="67611-108">Étant donné que le fichier de la base de données Resource contient tous les objets système, il suffit désormais tout simplement de copier le seul fichier de la base de données Resource sur le serveur local pour effectuer une mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="67611-108">Because the Resource database file contains all system objects, an upgrade is now accomplished simply by copying the single Resource database file to the local server.</span></span>  
  
## <a name="physical-properties-of-resource"></a><span data-ttu-id="67611-109">Propriétés physiques de la base de données Resource</span><span class="sxs-lookup"><span data-stu-id="67611-109">Physical Properties of Resource</span></span>  
 <span data-ttu-id="67611-110">Les noms de fichiers physiques de la base de données Resource sont mssqlsystemresource.mdf et mssqlsystemresource.ldf.</span><span class="sxs-lookup"><span data-stu-id="67611-110">The physical file names of the Resource database are mssqlsystemresource.mdf and mssqlsystemresource.ldf.</span></span> <span data-ttu-id="67611-111">Ces fichiers se trouvent dans \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ et ne doivent pas être déplacés.</span><span class="sxs-lookup"><span data-stu-id="67611-111">These files are located in \<*drive*>:\Program Files\Microsoft SQL Server\MSSQL\<version>.\<*instance_name*>\MSSQL\Binn\ and should not be moved.</span></span> <span data-ttu-id="67611-112">Chaque instance de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] possède un seul fichier mssqlsystemresource.mdf associé et les instances ne partagent pas ce fichier.</span><span class="sxs-lookup"><span data-stu-id="67611-112">Each instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has one and only one associated mssqlsystemresource.mdf file, and instances do not share this file.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="67611-113">Les Service Packs et les mises à niveau fournissent parfois une nouvelle base de données de ressources qui est installée dans le dossier BINN.</span><span class="sxs-lookup"><span data-stu-id="67611-113">Upgrades and service packs sometimes provide a new resource database which is installed to the BINN folder.</span></span> <span data-ttu-id="67611-114">La modification de l'emplacement de la base de données de ressources n'est ni prise en charge, ni recommandée.</span><span class="sxs-lookup"><span data-stu-id="67611-114">Changing the location of the resource database is not supported or recommended.</span></span>  
  
## <a name="backing-up-and-restoring-the-resource-database"></a><span data-ttu-id="67611-115">Sauvegarde et restauration de la base de données Resource</span><span class="sxs-lookup"><span data-stu-id="67611-115">Backing Up and Restoring the Resource Database</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="67611-116">ne peut pas sauvegarder la base de données Resource.</span><span class="sxs-lookup"><span data-stu-id="67611-116">cannot back up the Resource database.</span></span> <span data-ttu-id="67611-117">Vous pouvez effectuer votre propre sauvegarde sur fichiers ou sur disque en traitant le fichier mssqlsystemresource.mdf comme un fichier binaire (.EXE), et non comme un fichier de base de données, mais vous ne pouvez pas utiliser [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pour restaurer vos sauvegardes.</span><span class="sxs-lookup"><span data-stu-id="67611-117">You can perform your own file-based or a disk-based backup by treating the mssqlsystemresource.mdf file as if it were a binary (.EXE) file, rather than a database file, but you cannot use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to restore your backups.</span></span> <span data-ttu-id="67611-118">La restauration d'une copie de sauvegarde du fichier mssqlsystemresource.mdf peut uniquement être effectuée manuellement et vous devez alors veiller à ne pas remplacer la version actuelle de la base de données Resource par une version obsolète ou potentiellement instable.</span><span class="sxs-lookup"><span data-stu-id="67611-118">Restoring a backup copy of mssqlsystemresource.mdf can only be done manually, and you must be careful not to overwrite the current Resource database with an out-of-date or potentially insecure version.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="67611-119">Après avoir restauré une sauvegarde de mssqlsystemresource.mdf, vous devez réappliquer toutes les mises à jour ultérieures.</span><span class="sxs-lookup"><span data-stu-id="67611-119">After restoring a backup of mssqlsystemresource.mdf, you must reapply any subsequent updates.</span></span>  
  
## <a name="accessing-the-resource-database"></a><span data-ttu-id="67611-120">Accès à la base de données Resource</span><span class="sxs-lookup"><span data-stu-id="67611-120">Accessing the Resource Database</span></span>  
 <span data-ttu-id="67611-121">La base de données Resource doit uniquement être modifiée par un spécialiste du support technique Microsoft, ou à l'initiative de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="67611-121">The Resource database should only be modified by or at the direction of a Microsoft Customer Support Services (CSS) specialist.</span></span> <span data-ttu-id="67611-122">L'ID de la base de données Resource est toujours 32767.</span><span class="sxs-lookup"><span data-stu-id="67611-122">The ID of the Resource database is always 32767.</span></span> <span data-ttu-id="67611-123">Les autres valeurs importantes associées à la base de données Resource sont le numéro de version, ainsi que la date et l'heure de la dernière mise à jour de la base de données.</span><span class="sxs-lookup"><span data-stu-id="67611-123">Other important values associated with the Resource database are the version number and the last time that the database was updated.</span></span>  
  
 <span data-ttu-id="67611-124">**Pour déterminer le numéro de version de la base de données** Resource **, utilisez**:</span><span class="sxs-lookup"><span data-stu-id="67611-124">**To determine the version number of the** Resource **database, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceVersion');  
GO  
```  
  
 <span data-ttu-id="67611-125">**Pour déterminer la date et l’heure auxquelles la base de données** Resource **a été mise à jour pour la dernière fois, utilisez**:</span><span class="sxs-lookup"><span data-stu-id="67611-125">**To determine when the** Resource **database was last updated, use**:</span></span>  
  
```  
SELECT SERVERPROPERTY('ResourceLastUpdateDateTime');  
GO  
```  
  
 <span data-ttu-id="67611-126">**Pour accéder aux définitions SQL des objets système, utilisez la fonction OBJECT_DEFINITION :**</span><span class="sxs-lookup"><span data-stu-id="67611-126">**To access SQL definitions of system objects, use the OBJECT_DEFINITION function:**</span></span>  
  
```  
SELECT OBJECT_DEFINITION(OBJECT_ID('sys.objects'));  
GO  
```  
  
## <a name="related-content"></a><span data-ttu-id="67611-127">Contenu associé</span><span class="sxs-lookup"><span data-stu-id="67611-127">Related Content</span></span>  
 [<span data-ttu-id="67611-128">Bases de données système</span><span class="sxs-lookup"><span data-stu-id="67611-128">System Databases</span></span>](system-databases.md)  
  
 [<span data-ttu-id="67611-129">Connexion de diagnostic pour les administrateurs de base de données</span><span class="sxs-lookup"><span data-stu-id="67611-129">Diagnostic Connection for Database Administrators</span></span>](../../database-engine/configure-windows/diagnostic-connection-for-database-administrators.md)  
  
 [<span data-ttu-id="67611-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-130">OBJECT_DEFINITION &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/object-definition-transact-sql)  
  
 [<span data-ttu-id="67611-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="67611-131">SERVERPROPERTY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/serverproperty-transact-sql)  
  
 [<span data-ttu-id="67611-132">Démarrer SQL Server en mode mono-utilisateur</span><span class="sxs-lookup"><span data-stu-id="67611-132">Start SQL Server in Single-User Mode</span></span>](../../database-engine/configure-windows/start-sql-server-in-single-user-mode.md)  
  
  
