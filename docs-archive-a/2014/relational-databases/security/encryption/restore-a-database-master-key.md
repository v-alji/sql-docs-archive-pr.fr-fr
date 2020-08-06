---
title: Restaurer une clé principale de base de données | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- database master key [SQL Server], importing
ms.assetid: 16897cc5-db8f-43bb-a38e-6855c82647cf
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 614ba8bdc494ae7e7e5b3ed7b62390721ef642a3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87710524"
---
# <a name="restore-a-database-master-key"></a><span data-ttu-id="74cb6-102">Restaurer une clé principale de base de données</span><span class="sxs-lookup"><span data-stu-id="74cb6-102">Restore a Database Master Key</span></span>
  <span data-ttu-id="74cb6-103">Cette rubrique décrit la restauration de la clé principale de base de données dans [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] à l'aide de [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74cb6-103">This topic describes how to restore the database master key in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="74cb6-104">**Dans cette rubrique**</span><span class="sxs-lookup"><span data-stu-id="74cb6-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="74cb6-105">**Avant de commencer :**</span><span class="sxs-lookup"><span data-stu-id="74cb6-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="74cb6-106">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="74cb6-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="74cb6-107">Sécurité</span><span class="sxs-lookup"><span data-stu-id="74cb6-107">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="74cb6-108">Pour restaurer la clé principale de base de donnée à l'aide de Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74cb6-108">To restore the database master key using Transact-SQL</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="74cb6-109">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="74cb6-109">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="74cb6-110">Limitations et restrictions</span><span class="sxs-lookup"><span data-stu-id="74cb6-110">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="74cb6-111">Une fois la clé principale restaurée, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] déchiffre toutes les clés chiffrées au moyen de la clé principale active, puis chiffre ces clés au moyen de la clé principale restaurée.</span><span class="sxs-lookup"><span data-stu-id="74cb6-111">When the master key is restored, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] decrypts all the keys that are encrypted with the currently active master key, and then encrypts these keys with the restored master key.</span></span> <span data-ttu-id="74cb6-112">Cette opération gourmande en ressources doit être planifiée au cours d'une période de faible demande.</span><span class="sxs-lookup"><span data-stu-id="74cb6-112">This resource-intensive operation should be scheduled during a period of low demand.</span></span> <span data-ttu-id="74cb6-113">Si la clé principale de base de données en cours n'est pas ouverte ou ne peut pas être ouverte, ou si une clé chiffrée à l'aide de cette clé principale ne peut pas être déchiffrée, l'opération de restauration échoue.</span><span class="sxs-lookup"><span data-stu-id="74cb6-113">If the current database master key is not open or cannot be opened, or if any of the keys that are encrypted by it cannot be decrypted, the restore operation fails.</span></span>  
  
-   <span data-ttu-id="74cb6-114">Si l'un des déchiffrements échoue, la restauration échoue.</span><span class="sxs-lookup"><span data-stu-id="74cb6-114">If any one of the decryptions fails, the restore will fail.</span></span> <span data-ttu-id="74cb6-115">Vous pouvez utiliser l'option FORCE pour ignorer les erreurs, mais cette option entraîne la perte de toutes les données ne pouvant pas être déchiffrées.</span><span class="sxs-lookup"><span data-stu-id="74cb6-115">You can use the FORCE option to ignore errors, but this option will cause the loss of any data that cannot be decrypted.</span></span>  
  
-   <span data-ttu-id="74cb6-116">Si la clé principale a été chiffrée à l'aide de la clé principale du service, la clé principale restaurée sera également chiffrée à l'aide de la clé principale du service.</span><span class="sxs-lookup"><span data-stu-id="74cb6-116">If the master key was encrypted by the service master key, the restored master key will also be encrypted by the service master key.</span></span>  
  
-   <span data-ttu-id="74cb6-117">S'il n'existe aucune clé principale dans la base de données en cours, l'instruction RESTORE MASTER KEY crée une clé principale.</span><span class="sxs-lookup"><span data-stu-id="74cb6-117">If there is no master key in the current database, RESTORE MASTER KEY creates a master key.</span></span> <span data-ttu-id="74cb6-118">La nouvelle clé principale n'est pas automatiquement chiffrée au moyen de la clé principale du service.</span><span class="sxs-lookup"><span data-stu-id="74cb6-118">The new master key will not be automatically encrypted with the service master key.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="74cb6-119">Sécurité</span><span class="sxs-lookup"><span data-stu-id="74cb6-119">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="74cb6-120">Autorisations</span><span class="sxs-lookup"><span data-stu-id="74cb6-120">Permissions</span></span>  
 <span data-ttu-id="74cb6-121">Requiert l'autorisation CONTROL sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="74cb6-121">Requires CONTROL permission on the database.</span></span>  
  
##  <a name="using-sql-server-management-studio-with-transact-sql"></a><a name="SSMSProcedure"></a><span data-ttu-id="74cb6-122">Utilisation de SQL Server Management Studio avec Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="74cb6-122">Using SQL Server Management Studio with Transact-SQL</span></span>  
  
#### <a name="to-restore-the-database-master-key"></a><span data-ttu-id="74cb6-123">Pour restaurer la clé principale de base de données</span><span class="sxs-lookup"><span data-stu-id="74cb6-123">To restore the database master key</span></span>  
  
1.  <span data-ttu-id="74cb6-124">Récupérez une copie de la clé principale de base de données sauvegardée, à partir d'un support de sauvegarde physique ou d'un répertoire sur le système de fichiers local.</span><span class="sxs-lookup"><span data-stu-id="74cb6-124">Retrieve a copy of the backed-up database master key, either from a physical backup medium or a directory on the local file system.</span></span>  
  
2.  <span data-ttu-id="74cb6-125">Dans l' **Explorateur d'objets**, connectez-vous à une instance du [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="74cb6-125">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="74cb6-126">Dans la barre d'outils standard, cliquez sur **Nouvelle requête**.</span><span class="sxs-lookup"><span data-stu-id="74cb6-126">On the Standard bar, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="74cb6-127">Copiez et collez l'exemple suivant dans la fenêtre de requête, puis cliquez sur **Exécuter**.</span><span class="sxs-lookup"><span data-stu-id="74cb6-127">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Restores the database master key of the AdventureWorks2012 database.  
    USE AdventureWorks2012;  
    GO  
    RESTORE MASTER KEY   
        FROM FILE = 'c:\backups\keys\AdventureWorks2012_master_key'   
        DECRYPTION BY PASSWORD = '3dH85Hhk003#GHkf02597gheij04'   
        ENCRYPTION BY PASSWORD = '259087M#MyjkFkjhywiyedfgGDFD';  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="74cb6-128">Le chemin d'accès à la clé et le mot de passe de la clé (s'il existe) seront différents de ce qui est indiqué ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="74cb6-128">The file path to the key and the key's password (if it exists) will be different than what is indicated above.</span></span> <span data-ttu-id="74cb6-129">Assurez-vous que les deux sont spécifiques à votre installation de serveur et de clé.</span><span class="sxs-lookup"><span data-stu-id="74cb6-129">Please make sure that both are specific to your server and key set-up.</span></span>  
  
 <span data-ttu-id="74cb6-130">Pour plus d’informations, consultez [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="74cb6-130">For more information, see [RESTORE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/restore-master-key-transact-sql)</span></span>  
  
  
