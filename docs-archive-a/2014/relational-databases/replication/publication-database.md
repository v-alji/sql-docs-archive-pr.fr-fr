---
title: Base de données de publication | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.publicationdatabase.f1
ms.assetid: a9fafc9b-9963-4b59-97a0-3472158fa665
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 511e5f2e2caa934313ba96fb3dbc4cadddace968
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87600798"
---
# <a name="publication-database"></a><span data-ttu-id="f5a3d-102">Base de données de publication</span><span class="sxs-lookup"><span data-stu-id="f5a3d-102">Publication Database</span></span>
  <span data-ttu-id="f5a3d-103">La base de données de publication est la base de données située sur le serveur de publication, qui sert de source aux données et aux objets de base de données à répliquer.</span><span class="sxs-lookup"><span data-stu-id="f5a3d-103">The publication database is the database on the Publisher that is the source of data and database objects to be replicated.</span></span> <span data-ttu-id="f5a3d-104">Chaque base de données de publication mise en œuvre lors de la réplication doit obligatoirement être activée.</span><span class="sxs-lookup"><span data-stu-id="f5a3d-104">Each publication database used in replication must be enabled.</span></span> <span data-ttu-id="f5a3d-105">La base de données est activée lorsqu'un membre du rôle serveur fixe **sysadmin** :</span><span class="sxs-lookup"><span data-stu-id="f5a3d-105">The database is enabled when a member of the **sysadmin** fixed server role:</span></span>  
  
-   <span data-ttu-id="f5a3d-106">crée une publication relative à la base de données par le biais de l'Assistant Nouvelle publication ;</span><span class="sxs-lookup"><span data-stu-id="f5a3d-106">Creates a publication on that database using the New Publication Wizard.</span></span>  
  
-   <span data-ttu-id="f5a3d-107">sélectionne la base de données dans la boîte de dialogue **Propriétés du serveur de publication** ;</span><span class="sxs-lookup"><span data-stu-id="f5a3d-107">Selects the database in the **Publisher Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="f5a3d-108">exécute **sp_replicationdboption** et attribue à l'option **publish** (dans le cas de publications d'instantanés ou de publications transactionnelles) ou à l'option **merge publish** (dans le cas de publications de fusion) la valeur **True**.</span><span class="sxs-lookup"><span data-stu-id="f5a3d-108">Executes **sp_replicationdboption** and sets the option **publish** (for snapshot or transactional publications) or **merge publish** (for merge publications) to **True**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f5a3d-109">Options</span><span class="sxs-lookup"><span data-stu-id="f5a3d-109">Options</span></span>  
 <span data-ttu-id="f5a3d-110">**Bases de données**</span><span class="sxs-lookup"><span data-stu-id="f5a3d-110">**Databases**</span></span>  
 <span data-ttu-id="f5a3d-111">Permet de choisir le nom de la base de données contenant les données et les objets de base de données à publier.</span><span class="sxs-lookup"><span data-stu-id="f5a3d-111">Select the name of the database that contains the data and database objects that you want to publish.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a3d-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5a3d-112">See Also</span></span>  
 <span data-ttu-id="f5a3d-113">[Publier des données et des objets de base de données](publish/publish-data-and-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f5a3d-113">[Publish Data and Database Objects](publish/publish-data-and-database-objects.md) </span></span>  
 <span data-ttu-id="f5a3d-114">[Create a Publication](publish/create-a-publication.md) </span><span class="sxs-lookup"><span data-stu-id="f5a3d-114">[Create a Publication](publish/create-a-publication.md) </span></span>  
 <span data-ttu-id="f5a3d-115">[Afficher et modifier les propriétés d’un serveur de distribution et d’un serveur de publication](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f5a3d-115">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="f5a3d-116">sp_replicationdboption &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f5a3d-116">sp_replicationdboption &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-replicationdboption-transact-sql)  
  
  
