---
title: Environnements multi-utilisateurs (Visual Database Tools) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- users [SQL Server], multiuser environments
- conflict resolution [Visual Database Tools]
- multiple users making database changes
- multiuser environments [Visual Database Tools]
- database modifications [SQL Server]
- version control [Visual Database Tools]
- Visual Database Tools [SQL Server], multiuser environments
ms.assetid: 330bd48c-9427-4967-b58e-b7c492d5ee36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2e219ecda25f477aa459de674a43d9c2360376ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87603193"
---
# <a name="multiuser-environments-visual-database-tools"></a><span data-ttu-id="c0eca-102">Environnements multi-utilisateurs (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="c0eca-102">Multiuser Environments (Visual Database Tools)</span></span>
  <span data-ttu-id="c0eca-103">Dans un environnement multi-utilisateur, d'autres personnes peuvent se connecter et apporter des modifications à la base de données sur laquelle vous travaillez.</span><span class="sxs-lookup"><span data-stu-id="c0eca-103">A multiuser environment is one in which other users can connect and make changes to the same database that you are working with.</span></span> <span data-ttu-id="c0eca-104">Il en résulte que plusieurs personnes peuvent utiliser les mêmes objets d'une même base de données en même temps.</span><span class="sxs-lookup"><span data-stu-id="c0eca-104">As a result, several users might be working with the same database objects at the same time.</span></span> <span data-ttu-id="c0eca-105">Par conséquent, dans un environnement multi-utilisateur, vous ne devez pas oublier que d'autres utilisateurs peuvent modifier des bases de données en même temps que vous.</span><span class="sxs-lookup"><span data-stu-id="c0eca-105">Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.</span></span>  
  
 <span data-ttu-id="c0eca-106">Les autorisations d'accès sont un problème clé des bases de données dans un environnement multi-utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c0eca-106">A key issue when working with databases in a multiuser environment is access permissions.</span></span> <span data-ttu-id="c0eca-107">Les autorisations qui vous sont accordées sur la base de données déterminent l'étendue de l'utilisation que vous pouvez en faire.</span><span class="sxs-lookup"><span data-stu-id="c0eca-107">The permissions you have for the database determine the extent of the work you can do with the database.</span></span> <span data-ttu-id="c0eca-108">Par exemple, pour apporter des modifications à des objets d'une base de données, vous devez avoir sur cette base des autorisations d'écriture appropriées.</span><span class="sxs-lookup"><span data-stu-id="c0eca-108">For example, to make changes to objects in a database, you must have the appropriate write permissions for the database.</span></span> <span data-ttu-id="c0eca-109">Pour plus d'informations sur les autorisations d'accès à votre base de données, consultez sa documentation.</span><span class="sxs-lookup"><span data-stu-id="c0eca-109">For more information about permissions in your database, see your database documentation.</span></span> <span data-ttu-id="c0eca-110">Pour plus d’informations, consultez [Autorisations et Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0eca-110">For more information see [Permissions and Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="c0eca-111">Lorsque vous enregistrez les modifications apportées à des tables, le Concepteur de tables vérifie que la base de données n'a pas été modifiée depuis le précédent enregistrement des modifications.</span><span class="sxs-lookup"><span data-stu-id="c0eca-111">When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes.</span></span> <span data-ttu-id="c0eca-112">Si un autre utilisateur y a apporté des modifications, vous êtes averti que la base de données a changé.</span><span class="sxs-lookup"><span data-stu-id="c0eca-112">If another user has made changes, you will be notified that the database has been modified.</span></span> <span data-ttu-id="c0eca-113">Vous serez peut-être obligé d'harmoniser ces modifications.</span><span class="sxs-lookup"><span data-stu-id="c0eca-113">You may need to reconcile these changes.</span></span> <span data-ttu-id="c0eca-114">Pour plus d’informations, consultez [Réconcilier les modifications effectuées par plusieurs utilisateurs &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0eca-114">For more information, see [Reconcile Changes Made by Multiple Users &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="c0eca-115">Dans un environnement multi-utilisateur, vous devez tenir compte de certaines considérations afin d'éviter les conflits entre les modifications.</span><span class="sxs-lookup"><span data-stu-id="c0eca-115">In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes.</span></span> <span data-ttu-id="c0eca-116">Pour plus d’informations, consultez [Problèmes liés à l’évolution d’une base de données &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0eca-116">For more information, see [Issues of Database Evolution &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="c0eca-117">Pour éviter les problèmes, vous pouvez modifier une copie de la base de données, à l'instar d'une base de données test, puis créer un script de modification que vous exécutez ensuite pour appliquer ces modifications à la base de données d'origine après avoir résolu les conflits hors connexion.</span><span class="sxs-lookup"><span data-stu-id="c0eca-117">One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline.</span></span> <span data-ttu-id="c0eca-118">Pour plus d’informations, consultez [Bases de données de développement, de test et de production &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c0eca-118">For more information see [Development, Test, and Production Databases &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span></span>  
  
  
