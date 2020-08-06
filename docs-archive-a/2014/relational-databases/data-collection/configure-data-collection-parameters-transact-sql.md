---
title: Configurer des paramètres de collecte de données (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- data collection [SQL Server]
ms.assetid: 850905b6-35d2-4ed1-ab51-de64daa832b2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a8333b47612b4fbd933ef132e886b8125ffb58a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87702983"
---
# <a name="configure-data-collection-parameters-transact-sql"></a><span data-ttu-id="746df-102">Configurer des paramètres de collecte de données (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="746df-102">Configure Data Collection Parameters (Transact-SQL)</span></span>
  <span data-ttu-id="746df-103">Avant de créer un jeu d'éléments de collecte personnalisé, vous devez d'abord configurer des paramètres de collecte de données.</span><span class="sxs-lookup"><span data-stu-id="746df-103">Before you create a custom collection set, you must first configure data collection parameters.</span></span> <span data-ttu-id="746df-104">Pour cela, vous devez vous servir des procédures stockées fournies avec le collecteur de données.</span><span class="sxs-lookup"><span data-stu-id="746df-104">You can do this by using the stored procedures that are provided with the data collector.</span></span> <span data-ttu-id="746df-105">L’utilisation de l'éditeur de requêtes dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] est nécessaire pour effectuer la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="746df-105">Accomplishing this task involves using Query Editor in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to carry out the following procedure.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="746df-106">Vous ne configurez des paramètres de collecte de données qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="746df-106">You only configure data collection parameters once.</span></span> <span data-ttu-id="746df-107">Lorsque la configuration est terminée, ces paramètres servent pour tous les jeux d'éléments de collecte supplémentaires que vous créez.</span><span class="sxs-lookup"><span data-stu-id="746df-107">After configuration, these parameters are used for any additional collection sets that you create.</span></span>  
  
### <a name="configure-data-collection-parameters"></a><span data-ttu-id="746df-108">Configurer des paramètres de collecte de données</span><span class="sxs-lookup"><span data-stu-id="746df-108">Configure data collection parameters</span></span>  
  
1.  <span data-ttu-id="746df-109">Dans [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connectez-vous à la base de données dans laquelle vous souhaitez créer un jeu d'éléments de collecte personnalisé.</span><span class="sxs-lookup"><span data-stu-id="746df-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], connect to the database where you want to create a custom collection set.</span></span>  
  
2.  <span data-ttu-id="746df-110">Dans l'éditeur de requêtes, émettez les instructions suivantes.</span><span class="sxs-lookup"><span data-stu-id="746df-110">In Query Editor, issue the following statements.</span></span>  
  
    ```sql  
    USE msdb;  
    EXEC sp_syscollector_set_warehouse_instance_name N'INSTANCE_NAME';-- where instance name is the name of the SQL Server instance  
    EXEC sp_syscollector_set_warehouse_database_name N'MDW';  
    EXEC sp_syscollector_set_cache_directory N'D:\tempdata';  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="746df-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="746df-111">See Also</span></span>  
 <span data-ttu-id="746df-112">[Collecte de données](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="746df-112">[Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="746df-113">Procédures stockées du collecteur de données &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="746df-113">Data Collector Stored Procedures &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/data-collector-stored-procedures-transact-sql)  
  
  
