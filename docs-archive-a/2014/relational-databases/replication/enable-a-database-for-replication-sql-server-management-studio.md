---
title: Activer une base de données pour la réplication (SQL Server Management Studio) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- databases [SQL Server replication]
ms.assetid: 8092faa3-9cff-4f81-926c-6a0070d1ce2c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 307d52e24187e35c1c30f609facd13bfad569216
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87601358"
---
# <a name="enable-a-database-for-replication-sql-server-management-studio"></a><span data-ttu-id="2a426-102">activer une base de données pour la réplication (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="2a426-102">Enable a Database for Replication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="2a426-103">Une base de données est activée implicitement pour la réplication lorsqu'un membre du rôle serveur fixe **sysadmin** crée une publication à l'aide de l'Assistant Nouvelle publication.</span><span class="sxs-lookup"><span data-stu-id="2a426-103">A database is implicitly enabled for replication when a member of the **sysadmin** fixed server role creates a publication with the New Publication Wizard.</span></span> <span data-ttu-id="2a426-104">Un membre du rôle serveur fixe **sysadmin** peut également activer une base de données de manière explicite, afin qu'un membre du rôle de base de données fixe **db_owner** puisse créer une ou plusieurs publications dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="2a426-104">A member of the **sysadmin** fixed server role can also enable a database for replication explicitly, so that a member of the **db_owner** fixed database role can create one or more publications in that database.</span></span> <span data-ttu-id="2a426-105">Pour activer une base de données de manière explicite, utilisez la page **Bases de données de publication** de la boîte de dialogue **Propriétés du serveur de publication - \<Publisher>** .</span><span class="sxs-lookup"><span data-stu-id="2a426-105">To enable a database explicitly, use the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box.</span></span> <span data-ttu-id="2a426-106">Pour plus d'informations sur l'accès à cette boîte de dialogue, consultez [Create a Publication](publish/create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="2a426-106">For more information about accessing this dialog box, see [Create a Publication](publish/create-a-publication.md).</span></span>  
  
### <a name="to-enable-a-database-for-replication"></a><span data-ttu-id="2a426-107">Pour activer une base de données pour la réplication</span><span class="sxs-lookup"><span data-stu-id="2a426-107">To enable a database for replication</span></span>  
  
1.  <span data-ttu-id="2a426-108">Dans la page **Bases de données de publication** de la boîte de dialogue **Propriétés du serveur de publication - \<Publisher>** , cochez la case **Transactionnelle** et/ou **Fusionner** pour chaque base de données à répliquer.</span><span class="sxs-lookup"><span data-stu-id="2a426-108">On the **Publication Databases** page of the **Publisher Properties - \<Publisher>** dialog box, select the **Transactional** and/or **Merge** check box for each database you want to replicate.</span></span> <span data-ttu-id="2a426-109">Sélectionnez **Transactionnel** pour activer la base de données pour la réplication d'instantané.</span><span class="sxs-lookup"><span data-stu-id="2a426-109">Select **Transactional** to enable the database for snapshot replication.</span></span>  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
  
