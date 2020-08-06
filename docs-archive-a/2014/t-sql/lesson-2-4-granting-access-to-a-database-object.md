---
title: Octroi de l’accès à un objet de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- granting access to database objects
ms.assetid: a44d9bbf-f58e-4734-b7f4-eb3b492b777b
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 22bd0bb1f01e59ec30f7cf1bbf128c890d3d5d64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87613726"
---
# <a name="granting-access-to-a-database-object"></a><span data-ttu-id="65177-102">Octroi de l'accès à un objet de base de données</span><span class="sxs-lookup"><span data-stu-id="65177-102">Granting Access to a Database Object</span></span>
  <span data-ttu-id="65177-103"> En tant qu’administrateur, vous pouvez exécuter l’instruction SELECT à partir de la table **Products** et de la vue **vw_Names**, puis vous pouvez exécuter la procédure **pr_Names**. Toutefois, Mary ne peut pas le faire.</span><span class="sxs-lookup"><span data-stu-id="65177-103">As an administrator, you can execute the SELECT from the **Products** table and the **vw_Names** view, and execute the **pr_Names** procedure; however, Mary cannot.</span></span> <span data-ttu-id="65177-104">Pour lui octroyer les autorisations nécessaires, utilisez l'instruction GRANT.</span><span class="sxs-lookup"><span data-stu-id="65177-104">To grant Mary the necessary permissions, use the GRANT statement.</span></span>  
  
### <a name="procedure-title"></a><span data-ttu-id="65177-105">Titre de la procédure</span><span class="sxs-lookup"><span data-stu-id="65177-105">Procedure Title</span></span>  
  
1.  <span data-ttu-id="65177-106">Exécutez l'instruction suivante pour donner à `Mary` l'autorisation `EXECUTE` pour la procédure stockée `pr_Names` .</span><span class="sxs-lookup"><span data-stu-id="65177-106">Execute the following statement to give `Mary` the `EXECUTE` permission for the `pr_Names` stored procedure.</span></span>  
  
    ```  
    GRANT EXECUTE ON pr_Names TO Mary;  
    GO  
    ```  
  
 <span data-ttu-id="65177-107">Dans ce scénario, Mary peut accéder uniquement à la table **Products** à l'aide de la procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="65177-107">In this scenario, Mary can only access the **Products** table by using the stored procedure.</span></span> <span data-ttu-id="65177-108">Pour que Mary puisse exécuter une instruction SELECT sur la vue, vous devez exécuter aussi `GRANT SELECT ON vw_Names TO Mary`.</span><span class="sxs-lookup"><span data-stu-id="65177-108">If you want Mary to be able to execute a SELECT statement against the view, then you must also execute `GRANT SELECT ON vw_Names TO Mary`.</span></span> <span data-ttu-id="65177-109">Pour supprimer l'accès aux objets de base de données, utilisez l'instruction REVOKE.</span><span class="sxs-lookup"><span data-stu-id="65177-109">To remove access to database objects, use the REVOKE statement.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65177-110">Si la table, la vue et la procédure stockée n'appartiennent pas au même schéma, l'octroi des autorisations devient plus complexe.</span><span class="sxs-lookup"><span data-stu-id="65177-110">If the table, the view, and the stored procedure are not owned by the same schema, granting permissions becomes more complex.</span></span>  
  
## <a name="about-grant"></a><span data-ttu-id="65177-111">À propos de GRANT</span><span class="sxs-lookup"><span data-stu-id="65177-111">About GRANT</span></span>  
 <span data-ttu-id="65177-112">Vous devez avoir l'autorisation EXECUTE pour exécuter une procédure stockée.</span><span class="sxs-lookup"><span data-stu-id="65177-112">You must have EXECUTE permission to execute a stored procedure.</span></span> <span data-ttu-id="65177-113">Vous devez avoir les autorisations SELECT, INSERT, UPDATE, et DELETE pour accéder et modifier des données.</span><span class="sxs-lookup"><span data-stu-id="65177-113">You must have SELECT, INSERT, UPDATE, and DELETE permissions to access and change data.</span></span> <span data-ttu-id="65177-114">L'instruction GRANT sert également à d'autres autorisations, telles que les autorisations de créer des tables.</span><span class="sxs-lookup"><span data-stu-id="65177-114">The GRANT statement is also used for other permissions, such as permission to create tables.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="65177-115">Tâche suivante de la leçon</span><span class="sxs-lookup"><span data-stu-id="65177-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="65177-116">Résumé : Configuration des autorisations sur des objets de base de données</span><span class="sxs-lookup"><span data-stu-id="65177-116">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="see-also"></a><span data-ttu-id="65177-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="65177-117">See Also</span></span>  
 <span data-ttu-id="65177-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="65177-118">[GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql) </span></span>  
 [<span data-ttu-id="65177-119">REVOKE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="65177-119">REVOKE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/revoke-transact-sql)  
  
  
