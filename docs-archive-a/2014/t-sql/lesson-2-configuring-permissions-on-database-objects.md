---
title: 'Leçon 2 : Configuration des autorisations sur des objets de base de données | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- database permissions
ms.assetid: f964b66a-ec32-44c2-a185-6a0f173bfa22
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fcc6ee3ddf9be072b51bd568fd3e72eb6c871785
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87708012"
---
# <a name="lesson-2-configuring-permissions-on-database-objects"></a><span data-ttu-id="273cb-102">Leçon 2 : Configuration des autorisations sur des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="273cb-102">Lesson 2: Configuring Permissions on Database Objects</span></span>
  <span data-ttu-id="273cb-103">L'octroi à un utilisateur de l'accès à une base de données implique trois étapes.</span><span class="sxs-lookup"><span data-stu-id="273cb-103">Granting a user access to a database involves three steps.</span></span> <span data-ttu-id="273cb-104">Commencez par créer une connexion.</span><span class="sxs-lookup"><span data-stu-id="273cb-104">First, you create a login.</span></span> <span data-ttu-id="273cb-105">La connexion permet à l’utilisateur de se connecter au [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="273cb-105">The login lets the user connect to the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="273cb-106">Puis, configurez la connexion en tant qu'utilisateur dans la base de données spécifiée.</span><span class="sxs-lookup"><span data-stu-id="273cb-106">Then you configure the login as a user in the specified database.</span></span> <span data-ttu-id="273cb-107">Enfin, accordez à cet utilisateur l'autorisation sur les objets de base de données.</span><span class="sxs-lookup"><span data-stu-id="273cb-107">And finally, you grant that user permission to database objects.</span></span> <span data-ttu-id="273cb-108">Cette leçon illustre ces trois étapes et vous montre comment créer une vue et une procédure stockée comme objet.</span><span class="sxs-lookup"><span data-stu-id="273cb-108">This lesson shows you these three steps, and shows you how to create a view and a stored procedure as the object.</span></span>  
  
 <span data-ttu-id="273cb-109">Cette leçon contient les rubriques suivantes :</span><span class="sxs-lookup"><span data-stu-id="273cb-109">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="273cb-110">Création d'une connexion</span><span class="sxs-lookup"><span data-stu-id="273cb-110">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
-   [<span data-ttu-id="273cb-111">Octroi de l'accès à une base de données</span><span class="sxs-lookup"><span data-stu-id="273cb-111">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
-   [<span data-ttu-id="273cb-112">Création des vues et des procédures stockées</span><span class="sxs-lookup"><span data-stu-id="273cb-112">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
-   [<span data-ttu-id="273cb-113">Octroi de l'accès à un objet de base de données</span><span class="sxs-lookup"><span data-stu-id="273cb-113">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
-   [<span data-ttu-id="273cb-114">Résumé : Configuration des autorisations sur des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="273cb-114">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="273cb-115">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="273cb-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="273cb-116">Création d'une connexion</span><span class="sxs-lookup"><span data-stu-id="273cb-116">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
  
