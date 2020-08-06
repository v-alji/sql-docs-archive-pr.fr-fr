---
title: Octroi de l’accès à une base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- database access
ms.assetid: 686edfe2-3650-48a6-a2da-9d46fa211ad8
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 45b6d6c8dcd9c04d18489807271802aafee785b9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613734"
---
# <a name="granting-access-to-a-database"></a><span data-ttu-id="4a2d9-102">Octroi de l'accès à une base de données</span><span class="sxs-lookup"><span data-stu-id="4a2d9-102">Granting Access to a Database</span></span>
  <span data-ttu-id="4a2d9-103">Mary a désormais accès à cette instance de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], mais elle n'est pas autorisée à accéder aux bases de données.</span><span class="sxs-lookup"><span data-stu-id="4a2d9-103">Mary now has access to this instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], but does not have permission to access the databases.</span></span> <span data-ttu-id="4a2d9-104">Elle ne peut pas non plus accéder à sa base de données par défaut **TestData** tant que vous ne l'avez pas autorisée en tant qu'utilisateur de base de données.</span><span class="sxs-lookup"><span data-stu-id="4a2d9-104">She does not even have access to her default database **TestData** until you authorize her as a database user.</span></span>  
  
 <span data-ttu-id="4a2d9-105">Pour octroyer l'accès à Mary, basculez vers la base de données **TestData** , et à l'aide de l'instruction CREATE USER mappez sa connexion à un utilisateur appelée Marie.</span><span class="sxs-lookup"><span data-stu-id="4a2d9-105">To grant Mary access, switch to the **TestData** database, and then use the CREATE USER statement to map her login to a user named Mary.</span></span>  
  
### <a name="to-create-a-user-in-a-database"></a><span data-ttu-id="4a2d9-106">Pour créer un utilisateur dans une base de données</span><span class="sxs-lookup"><span data-stu-id="4a2d9-106">To create a user in a database</span></span>  
  
1.  <span data-ttu-id="4a2d9-107">Tapez et exécutez les instructions suivantes ( `computer_name` est remplacé par le nom de votre ordinateur) pour octroyer à `Mary` l'accès à la base de données `TestData` .</span><span class="sxs-lookup"><span data-stu-id="4a2d9-107">Type and execute the following statements (replacing `computer_name` with the name of your computer) to grant `Mary` access to the `TestData` database.</span></span>  
  
    ```  
    USE [TestData];  
    GO  
  
    CREATE USER [Mary] FOR LOGIN [computer_name\Mary];  
    GO  
  
    ```  
  
     <span data-ttu-id="4a2d9-108">Mary a désormais accès à [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] et à la base de données `TestData` .</span><span class="sxs-lookup"><span data-stu-id="4a2d9-108">Now, Mary has access to both [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and the `TestData` database.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="4a2d9-109">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="4a2d9-109">Next Task in Lesson</span></span>  
 [<span data-ttu-id="4a2d9-110">Création des vues et des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="4a2d9-110">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
  
